# System.Windows.Xps.XpsDocumentWriter::WriteAsync_17

- ea: `0xba40`
- end: `0xba72`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_17`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xba00`

## callees

- `0xba40`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xba40  ldarg.0
0xba41  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xba46  ldarg.2
0xba47  ldnull
0xba48  bne.un.s loc_BA4D
0xba4a  ldc.i4.0
0xba4b  br.s     loc_BA4E
0xba4d  ldc.i4.1
0xba4e  stloc.0
0xba4f  ldarg.0
0xba50  ldc.i4.0
0xba51  ldc.i4.1
0xba52  ldloc.0
0xba53  ldarg.2
0xba54  ldc.i4.2
0xba55  ldc.i4.0
0xba56  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xba5b  ldc.i4.1
0xba5c  bne.un.s loc_BA71
0xba5e  ldarg.0
0xba5f  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xba64  ldarg.1
0xba65  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xba6a  ldarg.0
0xba6b  ldc.i4.0
0xba6c  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xba71  ret
```
