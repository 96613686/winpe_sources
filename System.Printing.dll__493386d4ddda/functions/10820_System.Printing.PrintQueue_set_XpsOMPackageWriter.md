# System.Printing.PrintQueue::set_XpsOMPackageWriter

- ea: `0x10820`
- end: `0x10851`
- name: `System.Printing.PrintQueue::set_XpsOMPackageWriter`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x7920`
- `0xf600`
- `0x10820`

## pseudocode

```c

```

## disassembly

```asm
0x10820  ldarg.0
0x10821  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x10826  brfalse.s loc_10833
0x10828  ldc.i4.2
0x10829  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x1082e  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x10833  nop
0x10834  ldarg.0
0x10835  ldfld    class MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter System.Printing.PrintQueue::xpsCompatiblePrinter
0x1083a  ldarg.1
0x1083b  call     instance void MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter::set_XpsOMPackageWriter(class [ReachFramework]System.Windows.Xps.Serialization.RCW.IXpsOMPackageWriter packageWriter)
0x10840  leave.s  loc_10850
0x10842  ldarg.0
0x10843  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x10848  brfalse.s loc_1084F
0x1084a  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x1084f  endfinally
0x10850  ret
```
