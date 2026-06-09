# System.Windows.Xps.XpsDocumentWriter::Write_5

- ea: `0xb5d0`
- end: `0xb5f7`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_5`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb5d0`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb5d0  ldarg.0
0xb5d1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb5d6  ldarg.2
0xb5d7  ldnull
0xb5d8  bne.un.s loc_B5DD
0xb5da  ldc.i4.0
0xb5db  br.s     loc_B5DE
0xb5dd  ldc.i4.1
0xb5de  stloc.0
0xb5df  ldarg.0
0xb5e0  ldc.i4.0
0xb5e1  ldc.i4.0
0xb5e2  ldloc.0
0xb5e3  ldarg.2
0xb5e4  ldc.i4.3
0xb5e5  ldc.i4.0
0xb5e6  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb5eb  ldc.i4.1
0xb5ec  bne.un.s loc_B5F6
0xb5ee  ldarg.0
0xb5ef  ldarg.1
0xb5f0  ldc.i4.1
0xb5f1  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb5f6  ret
```
