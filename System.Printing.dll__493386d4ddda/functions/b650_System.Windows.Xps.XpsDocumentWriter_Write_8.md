# System.Windows.Xps.XpsDocumentWriter::Write_8

- ea: `0xb650`
- end: `0xb66e`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_8`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb650`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb650  ldarg.0
0xb651  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb656  ldarg.0
0xb657  ldc.i4.0
0xb658  ldc.i4.0
0xb659  ldc.i4.1
0xb65a  ldnull
0xb65b  ldc.i4.0
0xb65c  ldc.i4.0
0xb65d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb662  ldc.i4.1
0xb663  bne.un.s loc_B66D
0xb665  ldarg.0
0xb666  ldarg.1
0xb667  ldc.i4.1
0xb668  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb66d  ret
```
