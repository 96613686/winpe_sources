# System.Printing.PrintQueue::IsXpsOMPrintingDisabled

- ea: `0xde10`
- end: `0xde9c`
- name: `System.Printing.PrintQueue::IsXpsOMPrintingDisabled`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0xdea0`

## callees

- `0xac40`
- `0xde10`

## string_xrefs

- `0xde27`: `RegKeyBasePath`

## pseudocode

```c

```

## disassembly

```asm
0xde10  ldc.i4.0
0xde11  stloc.s  5
0xde13  newobj   instance void System.Printing.InternalExceptionResourceManager::.ctor()
0xde18  stloc.s  4
0xde1a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xde1f  call     instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0xde24  stloc.3
0xde25  ldloc.s  4
0xde27  ldstr    aRegkeybasepath// "RegKeyBasePath"
0xde2c  ldloc.3
0xde2d  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xde32  stloc.2
0xde33  ldloc.s  4
0xde35  ldstr    aPrintsystemjob// "PrintSystemJobInfo_disableXPSOMPrinting"...
0xde3a  ldloc.3
0xde3b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xde40  stloc.s  6
0xde42  ldc.i4.1
0xde43  ldloc.2
0xde44  newobj   instance void [mscorlib]System.Security.Permissions.RegistryPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.RegistryPermissionAccess, string)
0xde49  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0xde4e  ldc.i4.0
0xde4f  stloc.s  7
0xde51  ldloc.2
0xde52  ldloc.s  6
0xde54  ldc.i4.0
0xde55  box      [mscorlib]System.UInt32
0xde5a  call     object [mscorlib]Microsoft.Win32.Registry::GetValue(string, string, object)
0xde5f  stloc.0
0xde60  ldloc.0
0xde61  brfalse.s loc_DE79
0xde63  ldloc.0
0xde64  isinst   [mscorlib]System.Int32
0xde69  brfalse.s loc_DE79
0xde6b  ldloc.0
0xde6c  unbox    [mscorlib]System.Int32
0xde71  ldind.i4
0xde72  brfalse.s loc_DE79
0xde74  ldc.i4.1
0xde75  stloc.s  5
0xde77  br.s     loc_DE7D
0xde79  ldc.i4.1
0xde7a  stloc.1
0xde7b  br.s     loc_DE7F
0xde7d  ldc.i4.0
0xde7e  stloc.1
0xde7f  ldloc.1
0xde80  call     void [PresentationCore]MS.Internal.Telemetry.PresentationCore.XpsOMPrintingTraceLogger::LogXpsOMStatus(bool)
0xde85  leave.s  loc_DE91
0xde87  pop
0xde88  leave.s  loc_DE8D
0xde8a  pop
0xde8b  leave.s  loc_DE8F
0xde8d  leave.s  loc_DE99
0xde8f  leave.s  loc_DE99
0xde91  leave.s  loc_DE99
0xde93  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xde98  endfinally
0xde99  ldloc.s  5
0xde9b  ret
```
