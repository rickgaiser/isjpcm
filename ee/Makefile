# _____     ___ ____     ___ ____
#  ____|   |    ____|   |        | |____|
# |     ___|   |____ ___|    ____| |    \    PS2DEV Open Source Project.
#-----------------------------------------------------------------------
# Copyright 2001-2004.
# Licenced under Academic Free License version 2.0
# Review ps2sdk README & LICENSE files for further details.


EE_OBJS_DIR = obj/
EE_LIB_DIR = lib/
EE_SRC_DIR = src/

EE_OBJS = sjpcm_rpc.o
EE_OBJS := $(EE_OBJS:%=$(EE_OBJS_DIR)%)

EE_LIB = $(EE_LIB_DIR)libsjpcm.a

#EE_CFLAGS += -I$(PS2DRV)/ee/include -I$(PS2DRV)/common/include
EE_LDFLAGS += -s

all: $(EE_OBJS_DIR) $(EE_LIB_DIR) $(EE_LIB)

$(EE_LIB_DIR):
	$(MKDIR) -p $(EE_LIB_DIR)

$(EE_OBJS_DIR):
	$(MKDIR) -p $(EE_OBJS_DIR)

$(EE_OBJS_DIR)%.o : $(EE_SRC_DIR)%.c
	$(EE_CC) $(EE_CFLAGS) $(EE_INCS) -c $< -o $@

clean:
	rm -f -r $(EE_OBJS_DIR) $(EE_LIB_DIR)

install:
	mkdir -p $(PS2DEV)/isjpcm/include $(PS2DEV)/isjpcm/lib
	cp $(EE_SRC_DIR)*.h $(PS2DEV)/isjpcm/include
	cp $(EE_LIB) $(PS2DEV)/isjpcm/lib

include $(PS2SDK)/Defs.make
#include ./Rules.make
include $(PS2SDK)/samples/Makefile.eeglobal
