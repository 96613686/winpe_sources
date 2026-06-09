# System.Windows.Xps.XpsDocumentWriter::WriteAsync_5

- ea: `0xb830`
- end: `0xb862`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_5`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb7f0`

## callees

- `0xb830`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb830  ldarg.0
0xb831  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb836  ldarg.2
0xb837  ldnull
0xb838  bne.un.s loc_B83D
0xb83a  ldc.i4.0
0xb83b  br.s     loc_B83E
0xb83d  ldc.i4.1
0xb83e  stloc.0
0xb83f  ldarg.0
0xb840  ldc.i4.0
0xb841  ldc.i4.1
0xb842  ldloc.0
0xb843  ldarg.2
0xb844  ldc.i4.2
0xb845  ldc.i4.0
0xb846  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb84b  ldc.i4.1
0xb84c  bne.un.s loc_B861
0xb84e  ldarg.0
0xb84f  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb854  ldarg.1
0xb855  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb85a  ldarg.0
0xb85b  ldc.i4.0
0xb85c  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb861  ret
```
