# System.Xml.Xsl.XmlQueryType::get_IsNode

- ea: `0x23d0`
- end: `0x23e2`
- name: `System.Xml.Xsl.XmlQueryType::get_IsNode`
- size: `18`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x2820`
- `0x18290`
- `0x1a290`
- `0x1a900`
- `0x1b310`
- `0x1b7d0`
- `0x1bdb0`
- `0x1bde0`
- `0x27000`
- `0x273c0`
- `0x27490`
- `0x294f0`
- `0x295c0`
- `0x297d0`
- `0x298a0`
- `0x299c0`
- `0x29a90`
- `0x29ad0`
- `0x29b00`
- `0x41cf0`
- `0x49890`
- `0x4e900`
- `0x4faf0`
- `0x510e0`
- `0x511e0`

## callees

- `0x1f80`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  ldsfld   valuetype TypeFlags[] System.Xml.Xsl.XmlQueryType::TypeCodeToFlags
0x23d5  ldarg.0
0x23d6  callvirt instance valuetype [System.Xml]System.Xml.Schema.XmlTypeCode System.Xml.Xsl.XmlQueryType::get_TypeCode()
0x23db  ldelem.i4
0x23dc  ldc.i4.1
0x23dd  and
0x23de  ldc.i4.0
0x23df  cgt.un
0x23e1  ret
```
