# System.Xml.Xsl.XsltOld.Compiler::ValidateExtensionNamespace

- ea: `0x66b0`
- end: `0x66de`
- name: `System.Xml.Xsl.XsltOld.Compiler::ValidateExtensionNamespace`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x6600`

## callees

- `0x66b0`

## string_xrefs

- `0x66c5`: `Xslt_InvalidExtensionNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x66b0  ldarg.0
0x66b1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x66b6  brfalse.s loc_66C5
0x66b8  ldarg.0
0x66b9  ldstr    aHttpWwwW3Org19// "http://www.w3.org/1999/XSL/Transform"
0x66be  call     bool [mscorlib]System.String::op_Equality(string, string)
0x66c3  brfalse.s loc_66D6
0x66c5  ldstr    aXsltInvalidext// "Xslt_InvalidExtensionNamespace"
0x66ca  ldc.i4.0
0x66cb  newarr   [mscorlib]System.String
0x66d0  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0x66d5  throw
0x66d6  ldarg.0
0x66d7  call     class [System]System.Uri [System.Xml]System.Xml.XmlConvert::ToUri(string)
0x66dc  pop
0x66dd  ret
```
