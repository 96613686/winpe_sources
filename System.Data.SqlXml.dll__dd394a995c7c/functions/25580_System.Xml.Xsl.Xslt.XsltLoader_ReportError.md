# System.Xml.Xsl.Xslt.XsltLoader::ReportError

- ea: `0x25580`
- end: `0x25599`
- name: `System.Xml.Xsl.Xslt.XsltLoader::ReportError`
- size: `25`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x21760`
- `0x21890`
- `0x21c10`
- `0x21ca0`
- `0x22530`
- `0x22670`
- `0x229b0`
- `0x22b10`
- `0x22ce0`
- `0x22ee0`
- `0x23220`
- `0x23380`
- `0x237a0`
- `0x238d0`
- `0x23bf0`
- `0x23e80`
- `0x24140`
- `0x24430`
- `0x248d0`
- `0x24990`
- `0x24ac0`
- `0x24b90`
- `0x24fd0`
- `0x25190`
- `0x25200`
- `0x252a0`
- `0x25350`
- `0x255c0`

## callees

- `0x13be0`
- `0x20ff0`

## pseudocode

```c

```

## disassembly

```asm
0x25580  ldarg.0
0x25581  ldfld    class System.Xml.Xsl.Xslt.Compiler System.Xml.Xsl.Xslt.XsltLoader::compiler
0x25586  ldarg.0
0x25587  ldfld    class System.Xml.Xsl.Xslt.XsltInput System.Xml.Xsl.Xslt.XsltLoader::input
0x2558c  callvirt instance class System.Xml.Xsl.ISourceLineInfo System.Xml.Xsl.Xslt.XsltInput::BuildNameLineInfo()
0x25591  ldarg.1
0x25592  ldarg.2
0x25593  callvirt instance void System.Xml.Xsl.Xslt.Compiler::ReportError(class System.Xml.Xsl.ISourceLineInfo lineInfo, string res, string[] args)
0x25598  ret
```
