# System.Xml.Xsl.Xslt.Scripts::.cctor

- ea: `0x1ca30`
- end: `0x1ca74`
- name: `System.Xml.Xsl.Xslt.Scripts::.cctor`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x1ca58`: `System.Xml`
- `0x1ca60`: `System.Xml.Xsl`
- `0x1ca68`: `System.Xml.XPath`

## pseudocode

```c

```

## disassembly

```asm
0x1ca30  ldc.i4.7
0x1ca31  newarr   [mscorlib]System.String
0x1ca36  dup
0x1ca37  ldc.i4.0
0x1ca38  ldstr    aSystem// "System"
0x1ca3d  stelem.ref
0x1ca3e  dup
0x1ca3f  ldc.i4.1
0x1ca40  ldstr    aSystemCollecti// "System.Collections"
0x1ca45  stelem.ref
0x1ca46  dup
0x1ca47  ldc.i4.2
0x1ca48  ldstr    aSystemText// "System.Text"
0x1ca4d  stelem.ref
0x1ca4e  dup
0x1ca4f  ldc.i4.3
0x1ca50  ldstr    aSystemTextRegu// "System.Text.RegularExpressions"
0x1ca55  stelem.ref
0x1ca56  dup
0x1ca57  ldc.i4.4
0x1ca58  ldstr    aSystemXml// "System.Xml"
0x1ca5d  stelem.ref
0x1ca5e  dup
0x1ca5f  ldc.i4.5
0x1ca60  ldstr    aSystemXmlXsl// "System.Xml.Xsl"
0x1ca65  stelem.ref
0x1ca66  dup
0x1ca67  ldc.i4.6
0x1ca68  ldstr    aSystemXmlXpath// "System.Xml.XPath"
0x1ca6d  stelem.ref
0x1ca6e  stsfld   string[] System.Xml.Xsl.Xslt.Scripts::defaultNamespaces
0x1ca73  ret
```
