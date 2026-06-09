# System.Windows.Xps.XpsDocumentWriter::Write_4

- ea: `0xb5b0`
- end: `0xb5ce`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_4`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb670`

## callees

- `0xb5b0`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb5b0  ldarg.0
0xb5b1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb5b6  ldarg.0
0xb5b7  ldc.i4.0
0xb5b8  ldc.i4.0
0xb5b9  ldc.i4.1
0xb5ba  ldnull
0xb5bb  ldc.i4.0
0xb5bc  ldc.i4.0
0xb5bd  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb5c2  ldc.i4.1
0xb5c3  bne.un.s loc_B5CD
0xb5c5  ldarg.0
0xb5c6  ldarg.1
0xb5c7  ldc.i4.1
0xb5c8  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb5cd  ret
```
