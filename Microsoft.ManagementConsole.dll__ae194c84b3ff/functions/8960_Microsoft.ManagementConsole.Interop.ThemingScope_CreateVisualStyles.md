# Microsoft.ManagementConsole.Interop.ThemingScope::CreateVisualStyles

- ea: `0x8960`
- end: `0x89a2`
- name: `Microsoft.ManagementConsole.Interop.ThemingScope::CreateVisualStyles`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8770`

## callees

- `0x8830`
- `0x8960`

## pseudocode

```c

```

## disassembly

```asm
0x8960  ldnull
0x8961  stloc.0
0x8962  ldc.i4.0
0x8963  stloc.1
0x8964  ldc.i4.0
0x8965  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x896a  stloc.2
0x896b  ldloc.2
0x896c  ldc.i4.8
0x896d  callvirt instance void [mscorlib]System.Security.Permissions.FileIOPermission::set_AllFiles(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess)
0x8972  ldloc.2
0x8973  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x8978  ldtoken  [System.Windows.Forms]System.Windows.Forms.Application
0x897d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8982  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x8987  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x898c  stloc.0
0x898d  leave.s  loc_8995
0x898f  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x8994  endfinally
0x8995  ldloc.0
0x8996  brfalse.s loc_89A0
0x8998  ldarg.0
0x8999  ldloc.0
0x899a  call     instance bool Microsoft.ManagementConsole.Interop.ThemingScope::CreateActivationContext(string dllPath)
0x899f  stloc.1
0x89a0  ldloc.1
0x89a1  ret
```
