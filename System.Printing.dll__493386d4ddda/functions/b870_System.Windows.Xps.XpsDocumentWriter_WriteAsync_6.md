# System.Windows.Xps.XpsDocumentWriter::WriteAsync_6

- ea: `0xb870`
- end: `0xb899`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_6`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb810`

## callees

- `0xb870`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb870  ldarg.0
0xb871  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb876  ldarg.0
0xb877  ldc.i4.0
0xb878  ldc.i4.1
0xb879  ldc.i4.1
0xb87a  ldnull
0xb87b  ldc.i4.0
0xb87c  ldc.i4.0
0xb87d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb882  ldc.i4.1
0xb883  bne.un.s loc_B898
0xb885  ldarg.0
0xb886  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb88b  ldarg.1
0xb88c  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb891  ldarg.0
0xb892  ldc.i4.0
0xb893  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb898  ret
```
