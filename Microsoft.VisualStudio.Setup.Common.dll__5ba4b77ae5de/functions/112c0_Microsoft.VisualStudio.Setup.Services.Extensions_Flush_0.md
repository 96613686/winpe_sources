# Microsoft.VisualStudio.Setup.Services.Extensions::Flush_0

- ea: `0x112c0`
- end: `0x112f0`
- name: `Microsoft.VisualStudio.Setup.Services.Extensions::Flush_0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x112c0`
- `0x11480`

## string_xrefs

- `0x112c1`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x112c0  ldarg.0
0x112c1  ldstr    aWriter// "writer"
0x112c6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x112cb  ldarg.0
0x112cc  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x112d1  ldarg.0
0x112d2  isinst   [mscorlib]System.IO.StreamWriter
0x112d7  stloc.0
0x112d8  ldloc.0
0x112d9  brfalse.s loc_112EF
0x112db  ldloc.0
0x112dc  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.StreamWriter::get_BaseStream()
0x112e1  brfalse.s loc_112EF
0x112e3  ldloc.0
0x112e4  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.IO.StreamWriter::get_BaseStream()
0x112e9  ldarg.1
0x112ea  call     void Microsoft.VisualStudio.Setup.Services.Extensions::FlushImpl(class [mscorlib]System.IO.Stream stream, bool flushToDisk)
0x112ef  ret
```
