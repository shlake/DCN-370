# DCN-370
working space to capture changes to curation

I assume I download the zip file and unzip it?

No documentation of what to do with the files, maybe it is the readme?

## Missing ##
- how to run docker, if not familiar with it (At least Sherry wasn't)

- When trying following manual install of **Download CPA-Checker** - "ant" program wasn't installed on my Mac - and there was no mention that this is needed or where to get it. The CPA-Checker github has further instructions for intalling this that are not in this README.md file: https://github.com/sosy-lab/cpachecker/blob/trunk/INSTALL.md OR add "ant" to this line in the README.md (to install it)?

`sudo apt-get install python3 wget openjdk-11-jre`


## Manual Install ##
installing ShadowDP worked per instructions

But could not get it to "run" because the CPA-Checker (see above) would not install.

## Concerns ##
The CPA-Checker is very important and necessary for this code to run. It is available on github, which I am concerned not "reliable". If this github goes away, this program - scripts will not work. According to this.....

_As pre-compiled CPA-Checker binaries are relatively large, we don't include them as part of this project, you'll have to download them yourself._

Even if using "Docker", the docker image still has to go out and find that github.

## Problem with Docker ##

<rawtext>
docker build -t shadowdp .
[+] Building 7.8s (11/15)                                                                                      docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                                           0.0s
 => => transferring dockerfile: 2.44kB                                                                                         0.0s
 => [internal] load .dockerignore                                                                                              0.0s
 => => transferring context: 215B                                                                                              0.0s
 => [internal] load metadata for docker.io/library/openjdk:11-jre-slim                                                         1.1s
 => [internal] load metadata for docker.io/library/debian:stable-slim                                                          1.1s
 => [builder 1/5] FROM docker.io/library/debian:stable-slim@sha256:bfb338bbc84031a32bb0d4ba61025728ac725968b562707716c0fcc427  3.8s
 => => resolve docker.io/library/debian:stable-slim@sha256:bfb338bbc84031a32bb0d4ba61025728ac725968b562707716c0fcc42775d26b    0.0s
 => => sha256:bfb338bbc84031a32bb0d4ba61025728ac725968b562707716c0fcc42775d26b 1.85kB / 1.85kB                                 0.0s
 => => sha256:f73f45543a3709cb45c168712997954ea805ab774f7160bda7e2b44c0235d012 529B / 529B                                     0.0s
 => => sha256:fdbde89f2ae949a03d19c42dda472f3956ed191202fb566e0b6ebd47fd9a4d10 1.48kB / 1.48kB                                 0.0s
 => => sha256:6244b9232be94cf8cbf7648479e9c5a6e5832c22e10d15f7e438b7aabeceb280 29.15MB / 29.15MB                               2.9s
 => => extracting sha256:6244b9232be94cf8cbf7648479e9c5a6e5832c22e10d15f7e438b7aabeceb280                                      0.9s
 => [stage-1 1/6] FROM docker.io/library/openjdk:11-jre-slim@sha256:93af7df2308c5141a751c4830e6b6c5717db102b3b31f012ea29d842d  4.9s
 => => resolve docker.io/library/openjdk:11-jre-slim@sha256:93af7df2308c5141a751c4830e6b6c5717db102b3b31f012ea29d842dc4f2b02   0.0s
 => => sha256:93af7df2308c5141a751c4830e6b6c5717db102b3b31f012ea29d842dc4f2b02 549B / 549B                                     0.0s
 => => sha256:4e762c7129be5d5a3d04c51e6e15f9dc8168506775055c8ce5ed023f7688fe2b 1.16kB / 1.16kB                                 0.0s
 => => sha256:a1aef51062387fc731472d3257e9086f72497dcb7a3f94c2e6487708c51584ad 7.57kB / 7.57kB                                 0.0s
 => => sha256:a9fe95647e78b5516c7e2327355b6996e2ea295cd76ae242cbfe87f016b4e760 30.05MB / 30.05MB                               3.3s
 => => sha256:4015b6e8cc8db11af172df5c0369552bc2a74cd69094b0756d21fc6b0b2a5393 1.57MB / 1.57MB                                 0.8s
 => => sha256:fd343789f78f94e3d0fa4df3267fdadbc18138ad5785aa9a8afec60ec0407136 212B / 212B                                     0.9s
 => => sha256:5e8df94248cfc56b40d896855ef271976224c34fbfbe8a456006be727a3635c0 45.13MB / 45.13MB                               4.4s
 => => extracting sha256:a9fe95647e78b5516c7e2327355b6996e2ea295cd76ae242cbfe87f016b4e760                                      0.9s
 => => extracting sha256:4015b6e8cc8db11af172df5c0369552bc2a74cd69094b0756d21fc6b0b2a5393                                      0.1s
 => => extracting sha256:fd343789f78f94e3d0fa4df3267fdadbc18138ad5785aa9a8afec60ec0407136                                      0.0s
 => => extracting sha256:5e8df94248cfc56b40d896855ef271976224c34fbfbe8a456006be727a3635c0                                      0.5s
 => [internal] load build context                                                                                              0.1s
 => => transferring context: 142.34kB                                                                                          0.1s
 => ERROR [builder 2/5] RUN apt-get update -y &&     mkdir -p /usr/share/man/man1 &&     apt-get install -y --no-install-reco  2.9s
 => [stage-1 2/6] COPY . /shadowdp                                                                                             0.2s
 => [stage-1 3/6] WORKDIR /shadowdp                                                                                            0.0s
 => CANCELED [stage-1 4/6] RUN apt-get update -y &&     apt-get install -y --no-install-recommends     python3     python3-pi  1.5s
------                                                                                                                              
 > [builder 2/5] RUN apt-get update -y &&     mkdir -p /usr/share/man/man1 &&     apt-get install -y --no-install-recommends     unzip     git     ant     openjdk-11-jdk-headless:
0.228 Get:1 http://deb.debian.org/debian stable InRelease [151 kB]
0.346 Get:2 http://deb.debian.org/debian stable-updates InRelease [52.1 kB]
0.394 Get:3 http://deb.debian.org/debian-security stable-security InRelease [48.0 kB]
0.445 Get:4 http://deb.debian.org/debian stable/main arm64 Packages [8803 kB]
1.539 Get:5 http://deb.debian.org/debian stable-updates/main arm64 Packages [4736 B]
1.539 Get:6 http://deb.debian.org/debian-security stable-security/main arm64 Packages [47.8 kB]
2.221 Fetched 9107 kB in 2s (4309 kB/s)
2.221 Reading package lists...
2.494 Reading package lists...
2.750 Building dependency tree...
2.817 Reading state information...
2.820 Package openjdk-11-jdk-headless is not available, but is referred to by another package.
2.820 This may mean that the package is missing, has been obsoleted, or
2.820 is only available from another source
2.820 However the following packages replace it:
2.820   openjdk-17-jre-headless
2.820 
2.822 E: Package 'openjdk-11-jdk-headless' has no installation candidate
------
Dockerfile:25
--------------------
  24 |     FROM debian:stable-slim AS builder
  25 | >>> RUN apt-get update -y && \
  26 | >>>     # Fixes error creating symbolic link issue
  27 | >>>     mkdir -p /usr/share/man/man1 && \
  28 | >>>     apt-get install -y --no-install-recommends \
  29 | >>>     unzip \
  30 | >>>     git \
  31 | >>>     ant \
  32 | >>>     openjdk-11-jdk-headless
  33 |     
--------------------
ERROR: failed to solve: process "/bin/sh -c apt-get update -y &&     mkdir -p /usr/share/man/man1 &&     apt-get install -y --no-install-recommends     unzip     git     ant     openjdk-11-jdk-headless" did not complete successfully: exit code: 100
</rawtext>
