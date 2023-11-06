<!DOCTYPE html>
<html>
<head>
  <style>
    body { margin: 0; }
    #video-player {
      width: 100%;
      height: 100vh;
    }
  </style>
</head>
<body>
  <div id="video-player"></div>

  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <script>
    var video = document.getElementById('video-player');

    if (Hls.isSupported()) {
      var hls = new Hls();
      hls.loadSource('https://feeds.intoday.in/aajtak/api/master.m3u8');
      hls.attachMedia(video);
    }
    else if (video.canPlayType('application/vnd.apple.mpegurl')) {
      video.src = 'https://feeds.intoday.in/aajtak/api/master.m3u8';
    }
  </script>
</body>
</html>

