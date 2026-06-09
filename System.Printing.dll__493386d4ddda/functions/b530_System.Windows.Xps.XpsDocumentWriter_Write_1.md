# System.Windows.Xps.XpsDocumentWriter::Write_1

- ea: `0xb530`
- end: `0xb557`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb530`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb530  ldarg.0
0xb531  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb536  ldarg.2
0xb537  ldnull
0xb538  bne.un.s loc_B53D
0xb53a  ldc.i4.0
0xb53b  br.s     loc_B53E
0xb53d  ldc.i4.1
0xb53e  stloc.0
0xb53f  ldarg.0
0xb540  ldc.i4.0
0xb541  ldc.i4.0
0xb542  ldloc.0
0xb543  ldarg.2
0xb544  ldc.i4.2
0xb545  ldc.i4.0
0xb546  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb54b  ldc.i4.1
0xb54c  bne.un.s loc_B556
0xb54e  ldarg.0
0xb54f  ldarg.1
0xb550  ldc.i4.1
0xb551  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb556  ret
```
