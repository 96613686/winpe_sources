# System.Windows.Xps.XpsDocumentWriter::WriteAsync_14

- ea: `0xb9d0`
- end: `0xb9f9`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_14`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb970`

## callees

- `0xb9d0`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb9d0  ldarg.0
0xb9d1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb9d6  ldarg.0
0xb9d7  ldc.i4.0
0xb9d8  ldc.i4.1
0xb9d9  ldc.i4.1
0xb9da  ldnull
0xb9db  ldc.i4.0
0xb9dc  ldc.i4.0
0xb9dd  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb9e2  ldc.i4.1
0xb9e3  bne.un.s loc_B9F8
0xb9e5  ldarg.0
0xb9e6  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb9eb  ldarg.1
0xb9ec  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb9f1  ldarg.0
0xb9f2  ldc.i4.0
0xb9f3  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb9f8  ret
```
