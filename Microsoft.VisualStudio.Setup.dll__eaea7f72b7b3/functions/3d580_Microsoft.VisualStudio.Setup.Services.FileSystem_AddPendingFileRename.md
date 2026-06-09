# Microsoft.VisualStudio.Setup.Services.FileSystem::AddPendingFileRename

- ea: `0x3d580`
- end: `0x3d6df`
- name: `Microsoft.VisualStudio.Setup.Services.FileSystem::AddPendingFileRename`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x3d4c0`

## callees

- `0x3d580`

## string_xrefs

- `0x3d65b`: `' updated successfully with source '`
- `0x3d69a`: `Failed to update '`

## pseudocode

```c

```

## disassembly

```asm
0x3d580  ldarg.0
0x3d581  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Services.FileSystem::services
0x3d586  dup
0x3d587  brtrue.s loc_3D58D
0x3d589  pop
0x3d58a  ldnull
0x3d58b  br.s     loc_3D593
0x3d58d  ldc.i4.0
0x3d58e  call     T0x2B00005B
0x3d593  stloc.0
0x3d594  ldloc.0
0x3d595  brtrue.s loc_3D599
0x3d597  ldc.i4.0
0x3d598  ret
0x3d599  nop
0x3d59a  ldloc.0
0x3d59b  ldsfld   valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive Microsoft.VisualStudio.Setup.Services.FileSystem::Hive
0x3d5a0  ldc.i4.0
0x3d5a1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x3d5a6  stloc.1
0x3d5a7  ldloc.1
0x3d5a8  ldsfld   string Microsoft.VisualStudio.Setup.Services.FileSystem::Root
0x3d5ad  ldc.i4.0
0x3d5ae  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::CreateSubKey(string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryOptions)
0x3d5b3  stloc.2
0x3d5b4  ldstr    asc_975CE// "\\??\\"
0x3d5b9  ldarg.1
0x3d5ba  ldstr    asc_975D8// ""
0x3d5bf  call     string [mscorlib]System.String::Concat(string, string, string)
0x3d5c4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x3d5c9  stloc.3
0x3d5ca  ldarg.2
0x3d5cb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d5d0  brtrue.s loc_3D5E4
0x3d5d2  ldloc.3
0x3d5d3  ldstr    asc_975CE// "\\??\\"
0x3d5d8  ldarg.2
0x3d5d9  call     string [mscorlib]System.String::Concat(string, string)
0x3d5de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3d5e3  pop
0x3d5e4  ldloc.2
0x3d5e5  ldsfld   string Microsoft.VisualStudio.Setup.Services.FileSystem::Name
0x3d5ea  callvirt instance object [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::GetValue(string)
0x3d5ef  isinst   string[]
0x3d5f4  stloc.s  5
0x3d5f6  ldloc.s  5
0x3d5f8  dup
0x3d5f9  brtrue.s loc_3D601
0x3d5fb  pop
0x3d5fc  call     T0x2B0000B9
0x3d601  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x3d606  dup
0x3d607  ldloc.3
0x3d608  callvirt instance string [mscorlib]System.Object::ToString()
0x3d60d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3d612  stloc.s  4
0x3d614  ldloc.2
0x3d615  ldsfld   string Microsoft.VisualStudio.Setup.Services.FileSystem::Name
0x3d61a  ldloc.s  4
0x3d61c  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x3d621  ldc.i4.0
0x3d622  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::SetValue(string, object, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryValueKind)
0x3d627  leave.s  loc_3D633
0x3d629  ldloc.2
0x3d62a  brfalse.s loc_3D632
0x3d62c  ldloc.2
0x3d62d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d632  endfinally
0x3d633  leave.s  loc_3D63F
0x3d635  ldloc.1
0x3d636  brfalse.s loc_3D63E
0x3d638  ldloc.1
0x3d639  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d63e  endfinally
0x3d63f  ldarg.3
0x3d640  brfalse.s loc_3D688
0x3d642  ldarg.3
0x3d643  ldc.i4.7
0x3d644  newarr   [mscorlib]System.String
0x3d649  dup
0x3d64a  ldc.i4.0
0x3d64b  ldstr    asc_7FEB6// "'"
0x3d650  stelem.ref
0x3d651  dup
0x3d652  ldc.i4.1
0x3d653  ldsfld   string Microsoft.VisualStudio.Setup.Services.FileSystem::Name
0x3d658  stelem.ref
0x3d659  dup
0x3d65a  ldc.i4.2
0x3d65b  ldstr    aUpdatedSuccess// "' updated successfully with source '"
0x3d660  stelem.ref
0x3d661  dup
0x3d662  ldc.i4.3
0x3d663  ldarg.1
0x3d664  stelem.ref
0x3d665  dup
0x3d666  ldc.i4.4
0x3d667  ldstr    aAndDestination// "' and destination '"
0x3d66c  stelem.ref
0x3d66d  dup
0x3d66e  ldc.i4.5
0x3d66f  ldarg.2
0x3d670  stelem.ref
0x3d671  dup
0x3d672  ldc.i4.6
0x3d673  ldstr    asc_7F7FA// "'."
0x3d678  stelem.ref
0x3d679  call     string [mscorlib]System.String::Concat(string[])
0x3d67e  call     T0x2B000003
0x3d683  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3d688  ldc.i4.1
0x3d689  stloc.s  6
0x3d68b  leave.s  loc_3D6DC
0x3d68d  pop
0x3d68e  ldarg.3
0x3d68f  brfalse.s loc_3D6D7
0x3d691  ldarg.3
0x3d692  ldc.i4.7
0x3d693  newarr   [mscorlib]System.String
0x3d698  dup
0x3d699  ldc.i4.0
0x3d69a  ldstr    aFailedToUpdate_1// "Failed to update '"
0x3d69f  stelem.ref
0x3d6a0  dup
0x3d6a1  ldc.i4.1
0x3d6a2  ldsfld   string Microsoft.VisualStudio.Setup.Services.FileSystem::Name
0x3d6a7  stelem.ref
0x3d6a8  dup
0x3d6a9  ldc.i4.2
0x3d6aa  ldstr    aWithSource// "' with source '"
0x3d6af  stelem.ref
0x3d6b0  dup
0x3d6b1  ldc.i4.3
0x3d6b2  ldarg.1
0x3d6b3  stelem.ref
0x3d6b4  dup
0x3d6b5  ldc.i4.4
0x3d6b6  ldstr    aAndDestination// "' and destination '"
0x3d6bb  stelem.ref
0x3d6bc  dup
0x3d6bd  ldc.i4.5
0x3d6be  ldarg.2
0x3d6bf  stelem.ref
0x3d6c0  dup
0x3d6c1  ldc.i4.6
0x3d6c2  ldstr    asc_7F7FA// "'."
0x3d6c7  stelem.ref
0x3d6c8  call     string [mscorlib]System.String::Concat(string[])
0x3d6cd  call     T0x2B000003
0x3d6d2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x3d6d7  ldc.i4.0
0x3d6d8  stloc.s  6
0x3d6da  leave.s  loc_3D6DC
0x3d6dc  ldloc.s  6
0x3d6de  ret
```
