CC=g++
CFLAGS=-c -Wall
LDFLAGS=
SOURCES=adduser.cpp crypto/sha512/sha512.cpp getpass.cpp cutil/strutil.c checkuser.cpp
OBJECTS=$(SOURCES:.cpp=.o)
EXECUTABLE=login
BIN=/data/data/com.termux/files/usr/bin
FSROOT=/data/data/com.termux/files
all:compile install clean

compile: $(SOURCES) $(EXECUTABLE)

install: compile
	cp $(EXECUTABLE) $(BIN)/adduser
	mkdir -p $(FSROOT)/etc
clean:
	rm -f *.o
	rm -f .*.swp
	rm -f adduser
	rm -rf crypto/sha512/sha512.o
$(EXECUTABLE): $(OBJECTS) 
	$(CC) $(LDFLAGS) $(OBJECTS) -o $@

.cpp.o:
	$(CC) $(CFLAGS) $< -o $@
