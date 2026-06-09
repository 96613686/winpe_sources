# System.Windows.Xps.XpsDocumentWriter::Write_7

- ea: `0xb620`
- end: `0xb647`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_7`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb620`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb620  ldarg.0
0xb621  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb626  ldarg.2
0xb627  ldnull
0xb628  bne.un.s loc_B62D
0xb62a  ldc.i4.0
0xb62b  br.s     loc_B62E
0xb62d  ldc.i4.1
0xb62e  stloc.0
0xb62f  ldarg.0
0xb630  ldc.i4.0
0xb631  ldc.i4.0
0xb632  ldloc.0
0xb633  ldarg.2
0xb634  ldc.i4.2
0xb635  ldc.i4.0
0xb636  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb63b  ldc.i4.1
0xb63c  bne.un.s loc_B646
0xb63e  ldarg.0
0xb63f  ldarg.1
0xb640  ldc.i4.1
0xb641  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb646  ret
```
