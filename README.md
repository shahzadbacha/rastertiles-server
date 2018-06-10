# rastertiles-server

## Requirements
  - PostgreSQL & PostGIS </br>
  - osm2pgsql </br>
  - Mapnik </br>
  - Tilemill </br>
  - TileStache </br>
  
  ### Installations
  #### PostgreSQL
  CentOS's default repositories contain Postgres packages but we will add the latest version (10.4 at the time of writing) and then install 
  <pre>
  rpm -Uvh https://yum.postgresql.org/10/redhat/rhel-7-x86_64/pgdg-centos10-10-2.noarch.rpm
  yum install postgresql10-server postgresql10
  /usr/pgsql-10/bin/postgresql-10-setup initdb
  systemctl start postgresql-10.service
  systemctl enable postgresql-10.service
  sudo yum install postgis24_10
  </pre>
  
  #### Osm2pgsql
  <pre>
  git clone git://github.com/openstreetmap/osm2pgsql.git
  sudo yum install cmake make gcc-c++ boost-devel expat-devel zlib-devel bzip2-devel postgresql-devel proj-devel proj-epsg lua-devel
  mkdir build && cd build
  cmake ..
  make
  sudo make install
  cmake .. -G "Unix Makefiles" -DCMAKE_BUILD_TYPE=Debug -DBUILD_TESTS=ON
  </pre>
  
  ### Get Data
  The easiest place to obtain OSM data is Geofabrik (http://download.geofabrik.de/), whch is updated on daily basis. Select your continent and then your country of interest, to download data. OR you can get it simply through a command; </br>
  <pre> wget download.geofabrik.de/pakistan-latest.osm.pbf</pre>
