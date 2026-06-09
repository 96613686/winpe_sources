# System.Windows.Xps.XpsDocumentWriter::WriteAsync_9

- ea: `0xb8e0`
- end: `0xb912`
- name: `System.Windows.Xps.XpsDocumentWriter::WriteAsync_9`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xb8a0`

## callees

- `0xb8e0`
- `0xc6e0`
- `0xc9e0`
- `0xcae0`

## pseudocode

```c

```

## disassembly

```asm
0xb8e0  ldarg.0
0xb8e1  call     instance void System.Windows.Xps.XpsDocumentWriter::VerifyAccess()
0xb8e6  ldarg.2
0xb8e7  ldnull
0xb8e8  bne.un.s loc_B8ED
0xb8ea  ldc.i4.0
0xb8eb  br.s     loc_B8EE
0xb8ed  ldc.i4.1
0xb8ee  stloc.0
0xb8ef  ldarg.0
0xb8f0  ldc.i4.0
0xb8f1  ldc.i4.1
0xb8f2  ldloc.0
0xb8f3  ldarg.2
0xb8f4  ldc.i4.1
0xb8f5  ldc.i4.0
0xb8f6  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb8fb  ldc.i4.1
0xb8fc  bne.un.s loc_B911
0xb8fe  ldarg.0
0xb8ff  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb904  ldarg.1
0xb905  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb90a  ldarg.0
0xb90b  ldc.i4.0
0xb90c  call     instance void System.Windows.Xps.XpsDocumentWriter::EndWrite([hasfieldmarshal] bool disposeManager)
0xb911  ret
```
