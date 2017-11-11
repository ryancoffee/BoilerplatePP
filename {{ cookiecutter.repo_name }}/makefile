CC=g++
CFLAGS=-Wall -I/usr/local/include -I$(HOME){{ cookiecutter.personal_include_dir }} -I$(HOME)/computing/boost -std=gnu++14 -c -D_USE_MATH_DEFINES -DHAVE_INLINE -O3 -fopenmp
LDFLAGS=-L/usr/local/lib -lgsl -lgslcblas -lm -fopenmp
SOURCES={{ cookiecutter.main_name }}.cpp
HEADERS={{ cookiecutter.main_name }}.hpp 
OBJECTS=$(SOURCES:.cpp=.o)
EXECUTABLE={{ cookiecutter.main_name }}

all: $(SOURCES) $(EXECUTABLE)
	
$(EXECUTABLE): $(OBJECTS) $(HEADERS)
	$(CC) $(OBJECTS) $(LDFLAGS) -o $@

{{ cookiecutter.main_name }}.o: $(HEADERS) {{ cookiecutter.main_name }}.*pp
	$(CC) $(CFLAGS) $(LDFLAGS) {{ cookiecutter.main_name }}.cpp

.PHONY: clean
clean:
	rm $(OBJECTS) $(EXECUTABLE)

# DO NOT DELETE
