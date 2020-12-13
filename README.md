# automation

Home Automation Projects

## door camera

raspberry pi zero w

```bash
sudo sed -i 's/gpu_mem=128/gpu_mem=256/g' /boot/config.txt
curl http://www.linux-projects.org/listing/uv4l_repo/lpkey.asc | sudo apt-key add -
echo 'deb http://www.linux-projects.org/listing/uv4l_repo/raspbian/stretch stretch main' | sudo tee -a /etc/apt/sources.list.d/uv4l.list
sudo apt-get update
sudo apt-get install uv4l uv4l-raspicam uv4l-raspicam-extras
sudo apt-get install uv4l-webrtc
sudo apt-get update && sudo apt-get install libjpeg8-dev cmake
mkdir -p git/github.com/jacksonliam
cd git/github.com/jacksonliam/
git clone git clone https://github.com/jacksonliam/mjpg-streamer.git
git clone https://github.com/jacksonliam/mjpg-streamer.git
cd mjpg-streamer/mjpg-streamer-experimental
make
sudo modprobe bcm2835-v4l2
./mjpg_streamer -i "input_uvc.so -d /dev/video0 -r 1640x1232" -o "output_http.so -w ./www"
./mjpg_streamer -i "input_raspicam.so -x 1920 -y 1080" -o "output_http.so -w ./www"
./mjpg_streamer -i "input_raspicam.so -x 1640 -y 1232" -o "output_http.so -w ./www"
sudo make install
chmod +x postinstall.sh
sudo ./postinstall.sh
sudo cp -v scripts/mjpg-streamer.service /etc/systemd/system/mjpg-streamer.service
sudo systemctl  daemon-reload
sudo systemctl  enable mjpg-streamer.service
sudo systemctl  start mjpg-streamer.service
```
