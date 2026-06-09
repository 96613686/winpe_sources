# System.Windows.Xps.XpsDocumentWriter::BeginPrintFixedDocumentSequence

- ea: `0xb470`
- end: `0xb4ba`
- name: `System.Windows.Xps.XpsDocumentWriter::BeginPrintFixedDocumentSequence`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0xb4c0`
- `0x17460`

## callees

- `0xb470`
- `0xc6e0`
- `0x10800`

## pseudocode

```c

```

## disassembly

```asm
0xb470  ldarg.2
0xb471  ldnull
0xb472  beq.s    loc_B477
0xb474  ldc.i4.1
0xb475  br.s     loc_B478
0xb477  ldc.i4.0
0xb478  stloc.1
0xb479  ldarg.0
0xb47a  ldc.i4.0
0xb47b  ldc.i4.0
0xb47c  ldc.i4.1
0xb47d  ldarg.2
0xb47e  ldloca.s 1
0xb480  ldind.i4
0xb481  ldc.i4.1
0xb482  call     instance bool System.Windows.Xps.XpsDocumentWriter::BeginWrite([hasfieldmarshal] bool value, [hasfieldmarshal] bool batchMode, [hasfieldmarshal] bool asyncMode, [hasfieldmarshal] class [ReachFramework]System.Printing.PrintTicket setPrintTicketHandler, valuetype [ReachFramework]System.Windows.Xps.Serialization.PrintTicketLevel printTicket, bool printTicketLevel)
0xb487  ldc.i4.1
0xb488  bne.un.s loc_B4B9
0xb48a  ldarg.0
0xb48b  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb490  ldarg.1
0xb491  callvirt instance void [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::SaveAsXaml(object)
0xb496  ldarg.0
0xb497  ldfld    class System.Printing.PrintQueue System.Windows.Xps.XpsDocumentWriter::destinationPrintQueue
0xb49c  stloc.0
0xb49d  ldloc.0
0xb49e  brfalse.s loc_B4AC
0xb4a0  ldloc.0
0xb4a1  ldarg.0
0xb4a2  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb4a7  call     instance void System.Printing.PrintQueue::EnsureJobId(class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager manager)
0xb4ac  ldarg.3
0xb4ad  ldarg.0
0xb4ae  ldfld    class [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager System.Windows.Xps.XpsDocumentWriter::_manager
0xb4b3  call     instance int32 [ReachFramework]System.Windows.Xps.Serialization.PackageSerializationManager::get_JobIdentifier()
0xb4b8  stind.i4
0xb4b9  ret
```
