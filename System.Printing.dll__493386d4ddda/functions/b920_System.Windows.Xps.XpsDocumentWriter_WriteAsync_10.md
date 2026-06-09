# System.Windows.Xps.XpsDocumentWriter::WriteAsync_10

- ea: `0xb920`
- end: `0xb949`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_10`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0xb8c0`
- `0xbab0`

## callees

- `0xb920`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb920  ldarg.0
0xb921  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb926  ldarg.0
0xb927  ldc.i4.0
0xb928  ldc.i4.1
0xb929  ldc.i4.1
0xb92a  ldnull
0xb92b  ldc.i4.0
0xb92c  ldc.i4.0
0xb92d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb932  ldc.i4.1
0xb933  bne.un.s loc_B948
0xb935  ldarg.0
0xb936  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb93b  ldarg.1
0xb93c  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb941  ldarg.0
0xb942  ldc.i4.0
0xb943  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb948  ret
```
