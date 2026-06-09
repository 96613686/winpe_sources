# System.Windows.Xps.XpsDocumentWriter::Write_6

- ea: `0xb600`
- end: `0xb61e`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_6`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb600`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb600  ldarg.0
0xb601  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb606  ldarg.0
0xb607  ldc.i4.0
0xb608  ldc.i4.0
0xb609  ldc.i4.1
0xb60a  ldnull
0xb60b  ldc.i4.0
0xb60c  ldc.i4.0
0xb60d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb612  ldc.i4.1
0xb613  bne.un.s loc_B61D
0xb615  ldarg.0
0xb616  ldarg.1
0xb617  ldc.i4.1
0xb618  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb61d  ret
```
