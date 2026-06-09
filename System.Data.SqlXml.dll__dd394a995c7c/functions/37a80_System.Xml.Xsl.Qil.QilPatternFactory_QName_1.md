# System.Xml.Xsl.Qil.QilPatternFactory::QName_1

- ea: `0x37a80`
- end: `0x37a97`
- name: `System.Xml.Xsl.Qil.QilPatternFactory::QName_1`
- size: `23`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x26480`
- `0x264b0`
- `0x264e0`
- `0x26510`
- `0x26540`
- `0x26570`
- `0x265a0`
- `0x265d0`
- `0x26600`
- `0x26640`
- `0x266c0`
- `0x26720`
- `0x26750`
- `0x26790`
- `0x267c0`
- `0x26800`
- `0x26840`
- `0x26870`
- `0x268a0`
- `0x268d0`
- `0x26900`
- `0x29630`
- `0x29660`
- `0x296d0`
- `0x29b50`
- `0x29bc0`
- `0x29bf0`
- `0x29c20`
- `0x29c50`
- `0x29c80`
- `0x29cb0`
- `0x29ce0`
- `0x29d10`
- `0x29d40`
- `0x29d70`
- `0x29da0`
- `0x29dd0`

## callees

- `0x36390`

## pseudocode

```c

```

## disassembly

```asm
0x37a80  ldarg.0
0x37a81  ldfld    class System.Xml.Xsl.Qil.QilFactory System.Xml.Xsl.Qil.QilPatternFactory::f
0x37a86  ldarg.1
0x37a87  ldsfld   string [mscorlib]System.String::Empty
0x37a8c  ldsfld   string [mscorlib]System.String::Empty
0x37a91  callvirt instance class System.Xml.Xsl.Qil.QilName System.Xml.Xsl.Qil.QilFactory::LiteralQName(string localName, string namespaceUri, string prefix)
0x37a96  ret
```
