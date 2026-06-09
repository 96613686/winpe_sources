# System.Deployment.Application.Utilities::SetMarkOfTheWeb

- ea: `0x231e0`
- end: `0x232a2`
- name: `System.Deployment.Application.Utilities::SetMarkOfTheWeb`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0xba10`

## callees

- `0x17cb0`
- `0x17d40`
- `0x1a300`
- `0x231e0`

## string_xrefs

- `0x2325a`: `Failed to create alternate file stream, with error {0}`

## pseudocode

```c

```

## disassembly

```asm
0x231e0  ldarg.0
0x231e1  call     bool [mscorlib]System.IO.File::Exists(string)
0x231e6  brtrue.s loc_231E9
0x231e8  ret
0x231e9  ldarg.0
0x231ea  ldstr    aZoneIdentifier// ":Zone.Identifier"
0x231ef  call     string [mscorlib]System.String::Concat(string, string)
0x231f4  stloc.0
0x231f5  ldnull
0x231f6  stloc.1
0x231f7  ldnull
0x231f8  stloc.2
0x231f9  ldnull
0x231fa  stloc.3
0x231fb  ldloc.0
0x231fc  ldc.i4   0x40000000
0x23201  ldc.i4.2
0x23202  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x23207  ldc.i4.2
0x23208  ldc.i4.0
0x23209  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2320e  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle System.Deployment.Application.NativeMethods::CreateFile(string lpFileName, unsigned int32 dwDesiredAccess, unsigned int32 dwShareMode, native int lpSecurityAttributes, unsigned int32 dwCreationDisposition, unsigned int32 dwFlagsAndAttributes, native int hTemplateFile)
0x23213  stloc.1
0x23214  ldloc.1
0x23215  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x2321a  brtrue.s loc_23253
0x2321c  ldloc.1
0x2321d  ldc.i4.2
0x2321e  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle, valuetype [mscorlib]System.IO.FileAccess)
0x23223  stloc.2
0x23224  ldloc.2
0x23225  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x2322a  stloc.3
0x2322b  ldloc.3
0x2322c  ldstr    aZonetransfer// "[ZoneTransfer]"
0x23231  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x23236  ldloc.3
0x23237  ldstr    aZoneid3// "ZoneId=3"
0x2323c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x23241  ldstr    aSetMotwForFile// "Set \"MOTW\" for file: {0}"
0x23246  ldarg.0
0x23247  call     string [mscorlib]System.String::Format(string, object)
0x2324c  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x23251  br.s     loc_23270
0x23253  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x23258  stloc.s  4
0x2325a  ldstr    aFailedToCreate// "Failed to create alternate file stream,"...
0x2325f  ldloc.s  4
0x23261  box      [mscorlib]System.Int32
0x23266  call     string [mscorlib]System.String::Format(string, object)
0x2326b  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x23270  leave.s  loc_232A1
0x23272  pop
0x23273  ldstr    aFailedToSetMot// "Failed to set \"MOTW\" for file: {0}"
0x23278  ldarg.0
0x23279  call     string [mscorlib]System.String::Format(string, object)
0x2327e  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x23283  leave.s  loc_232A1
0x23285  ldloc.3
0x23286  brfalse.s loc_2328E
0x23288  ldloc.3
0x23289  callvirt instance void [mscorlib]System.IO.TextWriter::Close()
0x2328e  ldloc.2
0x2328f  brfalse.s loc_23297
0x23291  ldloc.2
0x23292  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x23297  ldloc.1
0x23298  brfalse.s loc_232A0
0x2329a  ldloc.1
0x2329b  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x232a0  endfinally
0x232a1  ret
```
