# System.Windows.Xps.XpsDocumentWriter::Write_2

- ea: `0xb560`
- end: `0xb57e`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_2`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb560`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb560  ldarg.0
0xb561  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb566  ldarg.0
0xb567  ldc.i4.0
0xb568  ldc.i4.0
0xb569  ldc.i4.1
0xb56a  ldnull
0xb56b  ldc.i4.0
0xb56c  ldc.i4.0
0xb56d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb572  ldc.i4.1
0xb573  bne.un.s loc_B57D
0xb575  ldarg.0
0xb576  ldarg.1
0xb577  ldc.i4.1
0xb578  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb57d  ret
```
