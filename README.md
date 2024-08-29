# 👀 Segment Anything 2 + ROS Noetic ![image](https://github.com/user-attachments/assets/973b4fa5-915d-4d49-8ac0-e24b408b0af8) + Docker  🐳

## Quickstart

Read instructions on the main branch first. To use with ROS, run:
```bash
docker run -it -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY --gpus all sam2-ros-docker bash
```
Inside the container, run
```bash
source ~/.bashrc
gnome-terminal
```

## Connecting to ROS running on the local host

Run `roscore` in both machines to find the port being used. Then close the container and rerun with the `-p` flag: 
```bash
docker run -it -p [HOST_PORT]:[CONTAINER_PORT] -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY --gpus all sam2-ros-docker bash
```

To test, run `roscore` in the docker container and `rostopic list` on the local host. The local host should show
```
/rosout
/rosout_agg
```
