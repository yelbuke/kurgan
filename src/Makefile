CC      = g++
PROF    = -O -g
NOCRYPT =
C_FLAGS = -Wall $(PROF) $(NOCRYPT)
L_FLAGS =  $(PROF)
LIBS	= -lcrypt -lm -lmysqlclient -lnsl -lz
LDFLAGS = -L/usr/lib64/mysql -I/usr/include/mysql

O_FILES = act_comm.o act_enter.o act_info.o act_move.o act_obj.o act_wiz.o \
    alias.o ban.o comm.o const.o db.o db2.o effects.o fight.o \
	  flags.o handler.o healer.o ini.o interp.o note.o lookup.o magic.o magic2.o \
	  music.o protocol.o recycle.o save.o scan.o skills.o special.o tables.o \
	  update.o -lcrypt

kurgan: $(O_FILES)
	rm -f kurgan
	$(CC) $(L_FLAGS) -o kurgan $(O_FILES) $(LIBS)

.c.o: merc.h
	$(CC) -c $(C_FLAGS) $<

clean:
	@rm -f *.o
	make
