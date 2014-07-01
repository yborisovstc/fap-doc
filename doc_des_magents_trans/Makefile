SOURCE = des_magents_trans.xml
STYLESHEETS_DIR = /usr/share/xml/docbook/stylesheet/nwalsh

html: $(SOURCE)
	xsltproc /usr/share/xml/docbook/stylesheet/nwalsh/html/onechunk.xsl $(SOURCE)

pdf: $(SOURCE)
	xsltproc -o intermediate-fo-file.fo --stringparam  paper.type  A4 \
	    --stringparam  page.orientation portrait \
	    --stringparam  page.margin.inner 20mm \
	    --stringparam  page.margin.outer 15mm \
	    --stringparam  body.start.indent 5mm \
	    /usr/share/xml/docbook/stylesheet/nwalsh/fo/docbook.xsl $(SOURCE)
	fop -pdf final-pdf-file.pdf -fo intermediate-fo-file.fo

clean:
	rm -rf index.html intermediate-fo-file.fo final-pdf-file.pdf
