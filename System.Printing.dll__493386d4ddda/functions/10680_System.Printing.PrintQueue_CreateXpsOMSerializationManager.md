# System.Printing.PrintQueue::CreateXpsOMSerializationManager

- ea: `0x10680`
- end: `0x10728`
- name: `System.Printing.PrintQueue::CreateXpsOMSerializationManager`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x10410`
- `0x10550`

## callees

- `0x3190`
- `0x7760`
- `0x77a0`
- `0x7910`
- `0xa730`
- `0xb130`
- `0xe550`
- `0xeef0`
- `0xf080`
- `0xf600`
- `0x10680`

## pseudocode

```c

```

## disassembly

```asm
0x10680  ldnull
0x10681  stloc.2
0x10682  ldarg.0
0x10683  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x10688  brfalse.s loc_10695
0x1068a  ldc.i4.2
0x1068b  newobj   instance void [System.Drawing]System.Drawing.Printing.PrintingPermission::.ctor(valuetype [System.Drawing]System.Drawing.Printing.PrintingPermissionLevel)
0x10690  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x10695  nop
0x10696  ldarg.0
0x10697  dup
0x10698  call     instance string System.Printing.PrintQueue::get_FullName()
0x1069d  newobj   instance void MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter::.ctor(string printerName)
0x106a2  stfld    class MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter System.Printing.PrintQueue::xpsCompatiblePrinter
0x106a7  ldarg.0
0x106a8  call     instance class System.Printing.PrintJobSettings System.Printing.PrintQueue::get_CurrentJobSettings()
0x106ad  call     instance string System.Printing.PrintJobSettings::get_Description()
0x106b2  stloc.1
0x106b3  ldloc.1
0x106b4  ldnull
0x106b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x106ba  brfalse.s loc_106C2
0x106bc  ldsfld   string System.Printing.PrintQueue::defaultXpsJobName
0x106c1  stloc.1
0x106c2  ldloc.1
0x106c3  ldarg.0
0x106c4  callvirt instance class System.Printing.PrintPort System.Printing.PrintQueue::get_QueuePort()
0x106c9  callvirt instance string System.Printing.PrintSystemObject::get_Name()
0x106ce  ldsfld   string MS.Internal.PrintWin32Thunk.DocInfoThree::defaultDataType
0x106d3  ldc.i4.0
0x106d4  newobj   instance void MS.Internal.PrintWin32Thunk.DocInfoThree::.ctor(string name, string outputFile, string dataType, int32 flags)
0x106d9  stloc.3
0x106da  ldarg.0
0x106db  ldfld    class MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter System.Printing.PrintQueue::xpsCompatiblePrinter
0x106e0  ldloc.3
0x106e1  ldarg.3
0x106e2  ldarg.s  4
0x106e4  callvirt instance void MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter::StartDocPrinterW(class MS.Internal.PrintWin32Thunk.DocInfoThree docInfo, class [ReachFramework]System.Printing.PrintTicket printTicket, [hasfieldmarshal] bool mustSetPrintJobIdentifier)
0x106e9  ldarg.0
0x106ea  ldfld    class MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter System.Printing.PrintQueue::xpsCompatiblePrinter
0x106ef  call     instance class [ReachFramework]System.Windows.Xps.Serialization.RCW.IXpsDocumentPackageTarget MS.Internal.PrintWin32Thunk.XpsCompatiblePrinter::get_XpsPackageTarget()
0x106f4  newobj   instance void [ReachFramework]System.Windows.Xps.Packaging.XpsOMPackagingPolicy::.ctor(class [ReachFramework]System.Windows.Xps.Serialization.RCW.IXpsDocumentPackageTarget)
0x106f9  stloc.0
0x106fa  ldloc.0
0x106fb  ldarg.0
0x106fc  call     instance void [ReachFramework]System.Windows.Xps.Packaging.XpsOMPackagingPolicy::set_PrintQueueReference(object)
0x10701  ldarg.2
0x10702  brfalse.s loc_1070E
0x10704  ldloc.0
0x10705  ldarg.1
0x10706  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync::.ctor(class [ReachFramework]System.Windows.Xps.Packaging.XpsOMPackagingPolicy, bool)
0x1070b  stloc.2
0x1070c  br.s     loc_10716
0x1070e  ldloc.0
0x1070f  ldarg.1
0x10710  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::.ctor(class [ReachFramework]System.Windows.Xps.Packaging.XpsOMPackagingPolicy, bool)
0x10715  stloc.2
0x10716  leave.s  loc_10726
0x10718  ldarg.0
0x10719  call     instance bool System.Printing.PrintQueue::get_InPartialTrust()
0x1071e  brfalse.s loc_10725
0x10720  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x10725  endfinally
0x10726  ldloc.2
0x10727  ret
```
