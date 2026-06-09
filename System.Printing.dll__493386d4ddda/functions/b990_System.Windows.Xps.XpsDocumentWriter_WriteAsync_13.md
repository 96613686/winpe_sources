# System.Windows.Xps.XpsDocumentWriter::WriteAsync_13

- ea: `0xb990`
- end: `0xb9c2`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_13`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb950`

## callees

- `0xb990`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb990  ldarg.0
0xb991  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb996  ldarg.2
0xb997  ldnull
0xb998  bne.un.s loc_B99D
0xb99a  ldc.i4.0
0xb99b  br.s     loc_B99E
0xb99d  ldc.i4.1
0xb99e  stloc.0
0xb99f  ldarg.0
0xb9a0  ldc.i4.0
0xb9a1  ldc.i4.1
0xb9a2  ldloc.0
0xb9a3  ldarg.2
0xb9a4  ldc.i4.3
0xb9a5  ldc.i4.0
0xb9a6  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb9ab  ldc.i4.1
0xb9ac  bne.un.s loc_B9C1
0xb9ae  ldarg.0
0xb9af  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb9b4  ldarg.1
0xb9b5  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb9ba  ldarg.0
0xb9bb  ldc.i4.0
0xb9bc  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb9c1  ret
```
