ifndef ARCH
$(error $$ARCH not set)
endif

ifndef BOOTMODE
$(error $$BOOTMODE not set)
endif

# Hardcoded to match ONL File naming conventions.
include $(ONL)/make/versions/version-onl.mk
INSTALLER_NAME=$(FNAME_PRODUCT_VERSION)_ONL-OS_$(FNAME_BUILD_ID)_$(UARCH)_$(BOOTMODE)_INSTALLER

__installer:
	$(ONL)/tools/mkinstaller.py --arch $(ARCH) --boot-config boot-config --add-dir config --initrd onl-loader-initrd:$(ARCH) onl-loader-initrd-$(ARCH).cpio.gz --swi onl-swi:$(ARCH) --out $(INSTALLER_NAME)
	md5sum "$(INSTALLER_NAME)" | awk '{ print $$1 }' > "$(INSTALLER_NAME).md5sum"


