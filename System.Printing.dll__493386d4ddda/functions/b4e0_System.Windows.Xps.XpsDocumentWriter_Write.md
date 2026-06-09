# System.Windows.Xps.XpsDocumentWriter::Write

- ea: `0xb4e0`
- end: `0xb507`
- name: `System.Windows.Xps.XpsDocumentWriter::Write`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xb4e0`
- `0xc6e0`
- `0xc9f0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb4e0  ldarg.0
0xb4e1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb4e6  ldarg.2
0xb4e7  ldnull
0xb4e8  bne.un.s loc_B4ED
0xb4ea  ldc.i4.0
0xb4eb  br.s     loc_B4EE
0xb4ed  ldc.i4.1
0xb4ee  stloc.0
0xb4ef  ldarg.0
0xb4f0  ldc.i4.0
0xb4f1  ldc.i4.0
0xb4f2  ldloc.0
0xb4f3  ldarg.2
0xb4f4  ldc.i4.3
0xb4f5  ldc.i4.0
0xb4f6  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb4fb  ldc.i4.1
0xb4fc  bne.un.s loc_B506
0xb4fe  ldarg.0
0xb4ff  ldarg.1
0xb500  ldc.i4.1
0xb501  call     instance void System.Windows.Xps.XpsDocumentWriter::SaveAsXaml(object serializedObject, [hasfieldmarshal] bool isSync)
0xb506  ret
```
