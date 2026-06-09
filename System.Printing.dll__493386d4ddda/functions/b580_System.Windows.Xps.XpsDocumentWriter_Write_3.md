# System.Windows.Xps.XpsDocumentWriter::Write_3

- ea: `0xb580`
- end: `0xb5a7`
- name: `System.Windows.Xps.XpsDocumentWriter::Write_3`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb580`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb580  ldarg.0
0xb581  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb586  ldarg.2
0xb587  ldnull
0xb588  bne.un.s loc_B58D
0xb58a  ldc.i4.0
0xb58b  br.s     loc_B58E
0xb58d  ldc.i4.1
0xb58e  stloc.0
0xb58f  ldarg.0
0xb590  ldc.i4.0
0xb591  ldc.i4.0
0xb592  ldloc.0
0xb593  ldarg.2
0xb594  ldc.i4.1
0xb595  ldc.i4.0
0xb596  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb59b  ldc.i4.1
0xb59c  bne.un.s loc_B5A6
0xb59e  ldarg.0
0xb59f  ldarg.1
0xb5a0  ldc.i4.1
0xb5a1  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb5a6  ret
```
