# Microsoft.VisualStudio.Setup.Activities.CreateDirectory::SynchronizedInvoke

- ea: `0x5ba80`
- end: `0x5bb8f`
- name: `Microsoft.VisualStudio.Setup.Activities.CreateDirectory::SynchronizedInvoke`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x596d0`
- `0x596f0`
- `0x5ba00`
- `0x5ba80`
- `0x5bb90`

## string_xrefs

- `0x5bac2`: `Will copy access control from '`
- `0x5bb2f`: `Created directory '`
- `0x5bb69`: `Set access control on '`

## pseudocode

```c

```

## disassembly

```asm
0x5ba80  ldarga.s 1
0x5ba82  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x5ba87  ldarg.0
0x5ba88  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Activities.Activity::get_Services()
0x5ba8d  ldc.i4.1
0x5ba8e  call     T0x2B00000C
0x5ba93  stloc.0
0x5ba94  ldnull
0x5ba95  stloc.1
0x5ba96  ldarg.0
0x5ba97  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::GetExistingTemplate()
0x5ba9c  stloc.2
0x5ba9d  ldloc.2
0x5ba9e  brfalse.s loc_5BB09
0x5baa0  ldarg.0
0x5baa1  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5baa6  ldloc.2
0x5baa7  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Utility.Io::ContainsPath(string, string)
0x5baac  brtrue.s loc_5BB09
0x5baae  ldarg.0
0x5baaf  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bab4  dup
0x5bab5  brtrue.s loc_5BABA
0x5bab7  pop
0x5bab8  br.s     loc_5BAF4
0x5baba  ldc.i4.5
0x5babb  newarr   [mscorlib]System.String
0x5bac0  dup
0x5bac1  ldc.i4.0
0x5bac2  ldstr    aWillCopyAccess// "Will copy access control from '"
0x5bac7  stelem.ref
0x5bac8  dup
0x5bac9  ldc.i4.1
0x5baca  ldloc.2
0x5bacb  stelem.ref
0x5bacc  dup
0x5bacd  ldc.i4.2
0x5bace  ldstr    aTo// "' to '"
0x5bad3  stelem.ref
0x5bad4  dup
0x5bad5  ldc.i4.3
0x5bad6  ldarg.0
0x5bad7  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5badc  stelem.ref
0x5badd  dup
0x5bade  ldc.i4.4
0x5badf  ldstr    asc_7F7FA// "'."
0x5bae4  stelem.ref
0x5bae5  call     string [mscorlib]System.String::Concat(string[])
0x5baea  call     T0x2B000003
0x5baef  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5baf4  ldloc.0
0x5baf5  ldloc.2
0x5baf6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IAccessControl [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetDirectorySecurity(string)
0x5bafb  stloc.1
0x5bafc  ldloc.1
0x5bafd  brtrue.s loc_5BB02
0x5baff  ldnull
0x5bb00  br.s     loc_5BB08
0x5bb02  ldloc.1
0x5bb03  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IAccessControl [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IAccessControl::Clone()
0x5bb08  stloc.1
0x5bb09  ldloc.0
0x5bb0a  ldarg.0
0x5bb0b  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5bb10  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x5bb15  brtrue.s loc_5BB4E
0x5bb17  ldloc.0
0x5bb18  ldarg.0
0x5bb19  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5bb1e  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::CreateDirectory(string)
0x5bb23  ldarg.0
0x5bb24  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bb29  dup
0x5bb2a  brtrue.s loc_5BB2F
0x5bb2c  pop
0x5bb2d  br.s     loc_5BB4E
0x5bb2f  ldstr    aCreatedDirecto// "Created directory '"
0x5bb34  ldarg.0
0x5bb35  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5bb3a  ldstr    asc_7F7FA// "'."
0x5bb3f  call     string [mscorlib]System.String::Concat(string, string, string)
0x5bb44  call     T0x2B000003
0x5bb49  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bb4e  ldloc.1
0x5bb4f  brfalse.s loc_5BB8E
0x5bb51  ldloc.0
0x5bb52  ldarg.0
0x5bb53  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5bb58  ldloc.1
0x5bb59  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::SetDirectorySecurity(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IAccessControl)
0x5bb5e  ldarg.0
0x5bb5f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Activities.Activity::get_Log()
0x5bb64  dup
0x5bb65  brtrue.s loc_5BB69
0x5bb67  pop
0x5bb68  ret
0x5bb69  ldstr    aSetAccessContr// "Set access control on '"
0x5bb6e  ldarg.0
0x5bb6f  call     instance string Microsoft.VisualStudio.Setup.Activities.CreateDirectory::get_Path()
0x5bb74  ldstr    asc_9868C// "': "
0x5bb79  ldloc.1
0x5bb7a  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IAccessControl::get_StringForm()
0x5bb7f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x5bb84  call     T0x2B000003
0x5bb89  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x5bb8e  ret
```
