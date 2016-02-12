HTML Questions
------

* **What does a doctype do?**  
The <!DOCTYPE> declaration must be the very first thing in your HTML document, before the <html> tag.  
The <!DOCTYPE> declaration is not an HTML tag; it is an instruction to the web browser about what version of HTML the page is written in.  
In HTML 4.01, the <!DOCTYPE> declaration refers to a DTD, because HTML 4.01 was based on SGML. The DTD specifies the rules for the markup language, so that the browsers render the content correctly.  
HTML5 is not based on SGML, and therefore does not require a reference to a DTD.  
Tip: Always add the <!DOCTYPE> declaration to your HTML documents, so that the browser knows what type of document to expect.  
The doctype is the first thing that appears in a standards-compliant page. This tells the browser which DTD we are going to validate against when rendering our page. The W3C has set forth specifications that lay out the rules of which (x)HTML tags are acceptable and in which places. One of these specifications is called a DTD (Document Type Definition) and may be one of the following:  
  * HTML 5   
  `<!DOCTYPE html>`
  * HTML 4.01 Transitional  
  This DTD contains all HTML elements and attributes, INCLUDING presentational and deprecated elements (like font). Framesets are not allowed.  
  `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">` 
  * HTML 4.01 Strict  
  This DTD contains all HTML elements and attributes, but does NOT INCLUDE presentational or deprecated elements (like font). Framesets are not allowed.  
  `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">`
  * HTML 4.01 Frameset    
  This DTD is equal to HTML 4.01 Transitional, but allows the use of frameset content.  
  `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">`
  * XHTML 1.0 Transitional  
  This DTD contains all HTML elements and attributes, INCLUDING presentational and deprecated elements (like font). Framesets are not allowed. The markup must also be written as well-formed XML.  
  `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">`
  * XHTML 1.0 Strict  
  This DTD contains all HTML elements and attributes, but does NOT INCLUDE presentational or deprecated elements (like font). Framesets are not allowed. The markup must also be written as well-formed XML.  
  `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">`
  * XHTML 1.0 Frameset  
  This DTD is equal to XHTML 1.0 Transitional, but allows the use of frameset content.  
  `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">`
  * XHTML 1.1  
  This DTD is equal to XHTML 1.0 Strict, but allows you to add modules (for example to provide ruby support for East-Asian languages).  
  `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">`

  A doctype has a reference to which DTD this document will validate to. We may specify a doctype in our xHTML page which is targeting XHTML 1.0 Transitional compliance. In this case our doctype will look something like this:   
`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">`

* **What's the difference between standards mode and quirks mode?**  
  In computing, quirks mode refers to a technique used by some web browsers for the sake of maintaining backward compatibility with web pages designed for Internet Explorer 5 and earlier, instead of strictly complying with W3C and IETF standards in standards mode.
To maintain compatibility with the greatest possible number of web pages, modern web browsers are generally developed with multiple rendering modes: in "standards mode" pages are rendered according to the HTML and CSS specifications, while in "quirks mode" attempts are made to emulate the behavior of older browsers. Some browsers (those based on Mozilla's Gecko rendering engine, or Internet Explorer 8 in strict mode, for example) also use an "almost standards" mode which attempts to compromise between the two, implementing one quirk for table cell sizing while otherwise conforming to the specifications.

  One prominent difference between quirks and standards modes is the handling of the CSS Internet Explorer box model bug. Before version 6, Internet Explorer used an algorithm for determining the width of an element's box which conflicted with the algorithm detailed in the CSS specification, and due to Internet Explorer's popularity many pages were created which relied upon this non-standard algorithm. As of version 6, Internet Explorer uses the CSS specification's algorithm when rendering in standards mode and uses the previous, non-standard algorithm when rendering in quirks mode.

  Another notable difference is the vertical alignment of certain types of inline content; many older browsers aligned images to the bottom border of their containing box, although the CSS specification requires that they be aligned to the baseline of the text within the box. In standards mode, Gecko-based browsers will align to the baseline, and in quirks mode they will align to the bottom.  
Additionally, many older browsers did not implement inheritance of font styles within tables; as a result, font styles had to be specified once for the document as a whole, and again for the table, even though the CSS specification requires that font styling be inherited into the table. If the font sizes are specified using relative units, a standards-compliant browser would inherit the base font size, then apply the relative font size within the table: for example, a page which declared a base font size of 80% and a table font size of 80% (to ensure a size of 80% in browsers which do not properly inherit font sizes) would, in a standards-compliant browser, display tables with a font size of 64% (80% of 80%). As a result, browsers typically do not inherit font sizes into tables in quirks mode.

  A third compatibility mode known as either "almost standards mode" or "strict mode" which maintains the "traditional" vertical sizing of table cells according to the CSS2 specification, has been implemented in these browsers: Safari, Opera 7.5 (and later), all Gecko-based browsers since 1.0.1 (such as Firefox) and Internet Explorer 8.
"Almost standards" mode rendering matches "standards" mode in all details except for one. The layout of images inside table cells is handled the same way "quirks" mode operates, instead, which is fairly consistent with legacy browsers such as Internet Explorer 7 (and earlier). This means that sliced-images-in-tables layouts are less likely to fall apart in browsers when in either "quirks" or "almost standards" mode, rather than "standards" mode.

  **Triggering different rendering modes**  
Most often, browsers determine which rendering mode to use based on the presence of a Document Type Declaration in the page; if a full DOCTYPE is present the browser will use standards mode, and if it is absent the browser will use quirks mode. For example, a web page which began with the following DOCTYPE would trigger standards mode:  
`<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">`  
The following DOCTYPE is syntactically invalid, containing the public identifier keyword "PUBLIC" but no public identifier (indicating the name of the version of HTML in use), and no system identifier URL of an HTML Document Type Definition. This would trigger quirks mode:  
`<!DOCTYPE html PUBLIC>`  
Additionally, a web page which does not include a DOCTYPE at all will render in quirks mode.
One notable exception to this is Microsoft's Internet Explorer 6 browser, which will render a page in quirks mode if the DOCTYPE is preceded by an XML prolog, regardless of whether a full DOCTYPE is specified. Thus an XHTML page which begins with the following code would be rendered in quirks mode by IE 6:  
`<?xml version="1.0" encoding="utf-8"?>`  
`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">`  
The above is useful to an extent as it can be used to trigger quirks mode only in IE 6.  
Quirks mode in any version of IE will also be triggered if anything precedes the DOCTYPE. For example, if a hypertext document contains a comment, space or any tag before the DOCTYPE declaration, IE will use quirks mode:  
`<!-- This comment will put IE 6, 7, 8, and 9 in quirks mode -->`  
`<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">`  
The problem with the XML declaration was fixed in version 7 of Internet Explorer, in which the XML prolog is simply ignored. However, for maximum compatibility with existing and older web browsers, the World Wide Web Consortium, which maintains the XHTML specification, suggests that authors of XHTML documents could consider omitting the XML declaration.

  [Comparison of document types](https://en.wikipedia.org/wiki/Quirks_mode)  
Henri Sivonen compiled a list of various document types and how they are treated in the most common browsers, showing whether pages are rendered in Quirks, Standards, or Almost standards mode. The criterion used for "Almost standards mode" is non-standard table cell height rendering. This table applies to content served with the Content-Type text/html. Content served with the Content-Type application/xhtml+xml is rendered in Standards mode in Chrome, Firefox, Internet Explorer 9, Safari, and Opera. Internet Explorer 6, 7, and 8 do not support Content-Type application/xhtml+xml.


* **What's the difference between HTML and XHTML?**  
	XHTML is HTML written as XML.  
	What Is XHTML?  
	XHTML stands for EXtensible HyperText Markup Language  
	XHTML is almost identical to HTML  
	XHTML is stricter than HTML  
	XHTML is HTML defined as an XML application  
	XHTML is supported by all major browsers  
	The Most Important Differences from HTML:  
    * Document Structure 
      * XHTML DOCTYPE is mandatory  
		*  The xmlns attribute in `<html>` is mandatory  
		*  `<html>`, `<head>`, `<title>`, and `<body>` are mandatory
	  *  XHTML Elements  
			* XHTML elements must be properly nested
			* XHTML elements must always be closed
			* XHTML elements must be in lowercase
			* XHTML documents must have one root element
	  *  XHTML Attributes  
			* Attribute names must be in lower case
			* Attribute values must be quoted
			* Attribute minimization is forbidden

	HTML5 has two parsing modes or syntaxes: HTML and XML. The difference depends on whether the document is served with a Content-type: text/html header or a Content-type: application/xml+xhtml header.

	If it’s served as text/html, the following rules apply:
    
      Start tags are not required for every element.
      End tags are not required for every element.
      Only void elements such as br, img, and link may be “self-closed” with />.
      Tags and attributes are case-insensitive.
      Attributes do not need to be quoted.
      Some attributes may be empty (such as checked and disabled).
      Special characters, or entities, do not have to be escaped.
      The document must include an HTML5 DOCTYPE.

	The following rules apply to “XHTML5″:

		All elements must have a start tag.
		Non-void elements with a start tag must have an end tag (p and li, for example).
		Any element may be “self-closed” using />.
		Tags and attributes are case sensitive, typically lowercase.
		Attribute values must be enclosed in quotes.
		Empty attributes are forbidden (checked must instead be checked="checked" or checked="true").
		Special characters must be escaped using character entities.

* Are there any problems with serving pages as application/xhtml+xml?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are data- attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a cookie, sessionStorage and localStorage.
* Describe the difference between `<script>, <script async> and <script defer>.`
* Why is it generally a good idea to position CSS `<link>s between <head></head> and JS <script>s just before </body>?` Do you know any exceptions?
* What is progressive rendering?
* Have you used different HTML templating languages before?

