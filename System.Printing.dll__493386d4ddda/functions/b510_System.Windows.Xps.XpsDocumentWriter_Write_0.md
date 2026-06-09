# System.Windows.Xps.XpsDocumentWriter::Write_0

- ea: `0xb510`
- end: `0xb52e`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb510`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb510  ldarg.0
0xb511  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb516  ldarg.0
0xb517  ldc.i4.0
0xb518  ldc.i4.0
0xb519  ldc.i4.1
0xb51a  ldnull
0xb51b  ldc.i4.0
0xb51c  ldc.i4.0
0xb51d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb522  ldc.i4.1
0xb523  bne.un.s loc_B52D
0xb525  ldarg.0
0xb526  ldarg.1
0xb527  ldc.i4.1
0xb528  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb52d  ret
```
