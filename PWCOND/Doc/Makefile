HELPDOC=../../dev-tools/helpdoc

doc:  all
all:  defs
clean:
	- rm -f INPUT_*.html INPUT_*.txt INPUT_*.xml
	- rm -rf input_xx.xsl
	- rm -rf ../../Doc/INPUT_PWCOND.*

defs: link_input_xx INPUT_PWCOND.html INPUT_PWCOND.txt link_on_main_doc
link_input_xx:
	@(if test ! -f input_xx.xsl; then \
	(if test -f ../../dev-tools/input_xx.xsl; then \
	(ln -sf ../../dev-tools/input_xx.xsl input_xx.xsl) ; \
	else \
	echo ; \
	echo "  Sorry, can not find input_xx.xsl html style file !!!" ; \
	echo ; \
	fi) ; fi)

INPUT_PWCOND.html: %.html: %.def input_xx.xsl
	$(HELPDOC) $<
INPUT_PWCOND.txt: %.txt: %.def
	$(HELPDOC) $<
link_on_main_doc:
	-@( cd ../../Doc ; ln -fs ../PWCOND/Doc/INPUT_PWCOND.html . ; \
	ln -fs ../PWCOND/Doc/INPUT_PWCOND.xml . ; \
	ln -fs ../PWCOND/Doc/INPUT_PWCOND.txt .)
