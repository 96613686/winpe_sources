# System.Xml.Xsl.Xslt.XsltLoader::ProcessOutputSettings

- ea: `0x223d0`
- end: `0x22444`
- name: `System.Xml.Xsl.Xslt.XsltLoader::ProcessOutputSettings`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x211c0`

## callees

- `0x223d0`

## string_xrefs

- `0x22439`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x223d0  ldarg.0
0x223d1  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x223d6  ldfld    class System.Xml.Xsl.Xslt.Output System.Xml.Xsl.Xslt.Compiler::Output
0x223db  stloc.0
0x223dc  ldloc.0
0x223dd  ldfld    class [System.Xml]System.Xml.XmlWriterSettings System.Xml.Xsl.Xslt.Output::Settings
0x223e2  stloc.1
0x223e3  ldloc.1
0x223e4  callvirt instance valuetype [System.Xml]System.Xml.XmlOutputMethod [System.Xml]System.Xml.XmlWriterSettings::get_OutputMethod()
0x223e9  ldc.i4.1
0x223ea  bne.un.s loc_22400
0x223ec  ldloc.0
0x223ed  ldfld    int32 System.Xml.Xsl.Xslt.Output::IndentPrec
0x223f2  ldc.i4   0x80000000
0x223f7  bne.un.s loc_22400
0x223f9  ldloc.1
0x223fa  ldc.i4.1
0x223fb  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x22400  ldloc.0
0x22401  ldfld    int32 System.Xml.Xsl.Xslt.Output::MediaTypePrec
0x22406  ldc.i4   0x80000000
0x2240b  bne.un.s loc_22443
0x2240d  ldloc.1
0x2240e  ldloc.1
0x2240f  callvirt instance valuetype [System.Xml]System.Xml.XmlOutputMethod [System.Xml]System.Xml.XmlWriterSettings::get_OutputMethod()
0x22414  brfalse.s loc_22439
0x22416  ldloc.1
0x22417  callvirt instance valuetype [System.Xml]System.Xml.XmlOutputMethod [System.Xml]System.Xml.XmlWriterSettings::get_OutputMethod()
0x2241c  ldc.i4.1
0x2241d  beq.s    loc_22432
0x2241f  ldloc.1
0x22420  callvirt instance valuetype [System.Xml]System.Xml.XmlOutputMethod [System.Xml]System.Xml.XmlWriterSettings::get_OutputMethod()
0x22425  ldc.i4.2
0x22426  beq.s    loc_2242B
0x22428  ldnull
0x22429  br.s     loc_2243E
0x2242b  ldstr    aTextPlain// "text/plain"
0x22430  br.s     loc_2243E
0x22432  ldstr    aTextHtml// "text/html"
0x22437  br.s     loc_2243E
0x22439  ldstr    aTextXml// "text/xml"
0x2243e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_MediaType(string)
0x22443  ret
```
