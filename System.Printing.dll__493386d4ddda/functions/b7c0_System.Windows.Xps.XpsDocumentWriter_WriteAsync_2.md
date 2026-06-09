# System.Windows.Xps.XpsDocumentWriter::WriteAsync_2

- ea: `0xb7c0`
- end: `0xb7e9`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_2`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb760`

## callees

- `0xb7c0`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb7c0  ldarg.0
0xb7c1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb7c6  ldarg.0
0xb7c7  ldc.i4.0
0xb7c8  ldc.i4.1
0xb7c9  ldc.i4.1
0xb7ca  ldnull
0xb7cb  ldc.i4.0
0xb7cc  ldc.i4.0
0xb7cd  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb7d2  ldc.i4.1
0xb7d3  bne.un.s loc_B7E8
0xb7d5  ldarg.0
0xb7d6  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb7db  ldarg.1
0xb7dc  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb7e1  ldarg.0
0xb7e2  ldc.i4.0
0xb7e3  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb7e8  ret
```
