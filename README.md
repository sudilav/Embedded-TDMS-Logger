
# Embedded TDMS Logger

## Overview

The Embedded TDMS Logger Custom Device is a plugin for logging data directly on the real time system of a VeriStand target, logging both Waveform and Channel data into one TDMS file with the flexibility to control the logged meta data.

## Software Dependencies

- NI LabVIEW 2023 Development Environment or later
- NI VeriStand 2023 or later
- VeriStand Development Tools VIPC

## Features

- Ability to control the meta data logged into the TDMS file
- Control fo the grouping of channels within the TDMS file
- Control to segment files either by size or time
- Triggering functionality (one time use per deployment)
- Can log immediately upon deployment

## Build Availability

Users are encouraged to build this code using the Build Specifications within the LabVIEW project(s). However certain releases will be made, corresponding to our internal setup and LabVIEW/VeriStand versionings

## Support

This custom device has been created by UKAEA for a project within the organisation. We do not intend to officially support this and are publishing it to the wider community as it would have been nice if it existed before we created it.

## Quality, Limitations

The intended use is not extreme and it will miss samples if the file operations become large as it is asynchronous and does not use RT FIFOs (The benefit is an easier configuration as it avoids connecting signals although this may change in future to utilise the FIFOs). Waveform data will not be lost however.

If you want to see the data on the host, you can manually transfer this to the host via FTP or WebDAV. We recommend to set up a mapped drive on the host of the WebDAV location on the target so the two are mirroring each other.

Our intended use as an example is that we will be using this custom device with a LabVIEW based UI for the VeriStand control. It will inject into the system definition some user prompted meta data and automate the configuration of this logger. Then be captured at the end via the WebDAV and consumed in a later data processing pipeline.

The overall reason for the production of this custom device is to produce one file, regardless of logging waveforms or channels.