# Frame::TryLookupNamespace

- ea: `0x2cc00`
- end: `0x2cc24`
- name: `Frame::TryLookupNamespace`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xfb90`

## callees

- `0x2cc00`

## string_xrefs

- `0x2cc0e`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x2cc00  ldarg.1
0x2cc01  ldstr    aXml// "xml"
0x2cc06  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cc0b  brfalse.s loc_2CC16
0x2cc0d  ldarg.2
0x2cc0e  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x2cc13  stind.ref
0x2cc14  ldc.i4.1
0x2cc15  ret
0x2cc16  ldarg.0
0x2cc17  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::prefixMap
0x2cc1c  ldarg.1
0x2cc1d  ldarg.2
0x2cc1e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x2cc23  ret
```
