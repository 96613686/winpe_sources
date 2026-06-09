# System.Xml.Xsl.Xslt.XsltQilFactory::DefaultValueMarker

- ea: `0x26450`
- end: `0x26461`
- name: `System.Xml.Xsl.Xslt.XsltQilFactory::DefaultValueMarker`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x148d0`

## callees

- `0x37a60`

## string_xrefs

- `0x26456`: `urn:schemas-microsoft-com:xslt-debug`

## pseudocode

```c

```

## disassembly

```asm
0x26450  ldarg.0
0x26451  ldstr    aDefaultValue// "default-value"
0x26456  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:xslt-debug"
0x2645b  call     instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilPatternFactory::QName(string local, string uri)
0x26460  ret
```
