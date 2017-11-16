Imaging sonar simulation 
==========================

This repository contains the Rock build system for imaging sonar simulation as presented in the paper:

**[A novel GPU-based sonar simulator for real-time applications](http://www.sciencedirect.com/science/article/pii/S0097849317301371)** <br>
R. Cerqueira, T. Trocoli, G. Neves, S. Joyeux, J. Albiez and L. Oliveira <br>
Elsevier Computers & Graphics Journal <br>
Special Section on SIBGRAPI 2017 <br>

How to install
==========================
The following steps are performed using Ubuntu 16.04 64 bits and Ruby 2.3.1.
```sh
$ sudo apt-get install ruby
$ mkdir sonar_simulation
$ cd sonar_simulation
$ wget https://raw.githubusercontent.com/romulogcerqueira/sonar_simulation-buildconf/master/bootstrap.sh
$ sh bootstrap.sh
```

Packages
==========================
The imaging sonar simulation is split in four main packages, as follows:
* `simulation/uwmodels`: contains the underwater scenario models;
* `simulation/normal_depth_map`: samples each OSG frame and computes the sonar rendering parameters during rasterization pipeline on GPU: sonar field-of-view, echo intensity and pulse distance;
* `simulation/gpu_sonar_simulation`: decodes the sonar rendering parameters into simulated sonar data;
* `simulation/orogen/imaging_sonar_simulation`: simulates the operation of two kind of sonar devices: Mechanical scanning imaging sonar (MSIS) and Forward-looking sonar (FLS); controls the virtual sonar device in the underwater scene; handles sonar properties; and provides I/O ports to interact with other Rock components.

How to run
==========================
```sh
$ cd sonar_simulation/orogen/imaging_sonar_simulation/scripts
```

To simulate the FLS device operation:
```sh
$ ruby sonar_multibeam-run.rb
```

To simulate the MSIS device operation:
```sh
$ ruby sonar_scanning-run.rb
```

Citation
==========================
Please cite our paper if you find this code useful for your research:
```
@article{CERQUEIRA2017,
    title = "A novel GPU-based sonar simulator for real-time applications",
    journal = "Computers & Graphics",
    volume = "68",
    number = "Supplement C",
    pages = "66 - 76",
    year = "2017",
    issn = "0097-8493",
    doi = "http://dx.doi.org/10.1016/j.cag.2017.08.008",
    url = "http://www.sciencedirect.com/science/article/pii/S0097849317301371",
    author = "Rômulo Cerqueira and Tiago Trocoli and Gustavo Neves and Sylvain Joyeux and Jan Albiez and Luciano Oliveira"
}
```
