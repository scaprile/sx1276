#  Fork and adaptation of Semtech driver for SX1276/8

The chip related parts of the original driver have been copied and modified for usage on our intended environments

## Example App

On the 'src' directory there is 'pingpong.c', which contains a modified version of one of the original applications contained in the bundle.
It has been conceived to run on a main loop or equivalent, it is provided here as an example to grasp the usage of the driver functions, and a convenient demo to test ports to different architectures.

## Required framework

The original work relied on a proprietary framework to provide timer related functions. We have slightly modified this to be less coupled to the actual environment used.

This repository by itself is missing the rest of the implementation; which can be remedied by observing a port to a similar framework or environment, of which this repo is a submodule.

The user is responsible for providing the header 'thissystem.h' and its functions, in the Mongoose-OS port, for example, we provide a working example of 'thissystem.h' and the corresponding implementation in 'thissystem.c'.

The user is also responsible for providing the specifics for the particular hardware related to the radio chip, as outlined at 'include/sx1276-board.h' (in this repository), and the 'Radio' structure itself, declared at 'include/radio.h' (in this repository) as well.
In the Mongoose-OS port, for example, we provide a working example of this as a single file: 'sx1276-board-radio.c'.

## Disclaimer

Original work is licensed as revised BSD and so this repo carries over this license, which is provided here as it was referenced from the files.
Copyright has been kept and these files are still the property of their respective owners, as indicated.
