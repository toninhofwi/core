ROOT := ../../

include $(TOP)$(ROOT)config/global.mk

PRG_SOURCES := \
   hbmk2.prg \

RC_SOURCES := harbour.rc

PRG_MAIN := hbmk2.prg

ifeq ($(HB_MT),no)
   LIBS = $(HB_LIBS_ST_RDD)
else
   LIBS = $(HB_LIBS_MT_RDD)
endif

HB_PRGFLAGS += -u -i$(TOP)

ifneq ($(HB_HAS_GPM),)
   HB_PRGFLAGS += -DHB_HAS_GPM
endif
ifneq ($(HB_HAS_WATT),)
   HB_PRGFLAGS += -DHB_HAS_WATT
endif

# Not possible to override default entry
# function cleanly when using plain GNU Make
# to build, so we're using _APPMAIN(), which
# is better than Main()
HB_PRGFLAGS += -DHBMK_USE_APPMAIN

HB_PRGFLAGS += -DHBMK_WITH_BUILTIN_HEADERS_ALL

include $(TOP)$(ROOT)config/bin.mk
