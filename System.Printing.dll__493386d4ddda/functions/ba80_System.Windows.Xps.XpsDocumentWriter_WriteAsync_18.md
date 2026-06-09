# System.Windows.Xps.XpsDocumentWriter::WriteAsync_18

- ea: `0xba80`
- end: `0xbaa9`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_18`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xba20`

## callees

- `0xba80`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xba80  ldarg.0
0xba81  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xba86  ldarg.0
0xba87  ldc.i4.0
0xba88  ldc.i4.1
0xba89  ldc.i4.1
0xba8a  ldnull
0xba8b  ldc.i4.0
0xba8c  ldc.i4.0
0xba8d  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xba92  ldc.i4.1
0xba93  bne.un.s loc_BAA8
0xba95  ldarg.0
0xba96  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xba9b  ldarg.1
0xba9c  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xbaa1  ldarg.0
0xbaa2  ldc.i4.0
0xbaa3  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xbaa8  ret
```
