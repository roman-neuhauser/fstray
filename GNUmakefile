# vim: sw=2 sts=2 ts=8 noet fdm=marker cms=\ #\ %s
PREFIX ?=		/usr/local
BINDIR ?=		$(PREFIX)/bin
MANDIR ?=		$(PREFIX)/share/man
MAN1DIR ?=		$(MANDIR)/man1

GZIP ?=			gzip
INSTALL ?=		install
INSTALL_DATA ?=		$(INSTALL) -m 0644
INSTALL_DIR ?=		$(INSTALL) -m 0755 -d
INSTALL_SCRIPT ?=	$(INSTALL) -m 0755

all: fstray fstray.1.gz

clean:
	rm -f fstray fstray.1.gz *.o

fstray: fstray.in
	$(INSTALL_SCRIPT) $< $@

fstray.1.gz: fstray.1
	$(GZIP) < $< > $@

install: all
	$(INSTALL_DIR) $(DESTDIR)$(BINDIR)
	$(INSTALL_DIR) $(DESTDIR)$(MAN1DIR)
	$(INSTALL_SCRIPT) fstray $(DESTDIR)$(BINDIR)/fstray
	$(INSTALL_DATA) fstray.1.gz $(DESTDIR)$(MAN1DIR)/fstray.1.gz


.PHONY: all
.PHONY: clean
.PHONY: install
