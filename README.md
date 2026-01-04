<!DOCTYPE html>
<html>
<head>
    <title>Camera Photo Capture Project</title>
    <style>
        body { text-align: center; font-family: Arial; }
        video, canvas { border: 2px solid black; margin-top: 10px; }
        button { padding: 10px 20px; margin-top: 10px; }
    </style>
</head>
<body>

<h2>Camera Photo Capture (With User Permission)</h2>

<video id="video" width="300" autoplay></video><br>
<button onclick="startCamera()">Start Camera</button><br>
<button onclick="capturePhoto()">Capture Photo</button><br><br>

<canvas id="canvas" width="300" height="220"></canvas>

<script>
let video = document.getElementById("video");
let canvas = document.getElementById("canvas");
let context = canvas.getContext("2d");

function startCamera() {
    navigator.mediaDevices.getUserMedia({ video: true })
    .then(stream => {
        video.srcObject = stream;
    })
