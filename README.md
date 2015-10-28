
*ofxDSHapVideoPlayer*

ofxDSHapVideoPlayer is a video player addon for openFrameworks. It plays Hap-encoded videos natively on Windows using Direct Show video playback tools.

Hap is a video codec that is decoded on the GPU. Some of its benefits include fast decompression and low CPU usage. It was written by Tom Butterworth for VidVox/VDMX. For further information on Hap, see http://vdmx.vidvox.net/blog/hap.

*Requirements*

Before encoding videos using Hap codec, install the Hap codec for Direct Show. An installer is available from http://www.renderheads.com/downloads/2015/HapDirectShowCodecSetup.exe

*Usage*

In ofApp.h

```
ofxDSHapVideoPlayer videoPlayer;
```

In ofApp.cpp

```c++
void ofApp::setup(){

	videoPlayer.loadVideo("HapVideo.avi");
	videoPlayer.play();
}

void ofApp::update(){

	videoPlayer.update();
}

void ofApp::draw(){

	ofSetColor(255);
	videoPlayer.draw(0, 0);
}
```

*Notes*

* ofxDSHapVideoPlayer does not currently support snappy compression. Do not use this option when exporting Hap-encoded files. 

* ofxDSHapVideoPlayer plays back Hap videos in .avi containers. It will not play back Hap-encoded video files in QuickTime movie containers. Encode Windows .avi files using Adobe Media Encoder, After Effects or other.

* Sample Hap video files are available on http://renderheads.com/product/hap-for-directshow/