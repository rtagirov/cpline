#FC=mpif90
FC=mpiifort
#FC=mpifort
#FC=ifort
#INCLUDENET=-I/scratch/witzke/Libraries/netcdf-3.6.1/include
#INCLUDENET=-I/home/rtagirov/lib/include
#INCLUDENET=-I/apps/netcdf/3.6.2/include
INCLUDENET=-I${NETCDF}/include
#FFLAGS= -traceback -c -heap-arrays -check bounds #-O2
FFLAGS= -c
#FPPFLAG=""
FPPFLAG="-DMPI"

OBJ = IOnet.o

all: libnet.a

libnet.a: $(OBJ)
	rm -f libnet.a
	ar crv libnet.a $(OBJ)

IOnet.o : IOnet.F90
	$(FC) $(FFLAGS) $(FPPFLAG)  IOnet.F90 $(INCLUDENET)

clean:
	rm -f *.o core *.a *.f *~ work.pc *.mod 
 
