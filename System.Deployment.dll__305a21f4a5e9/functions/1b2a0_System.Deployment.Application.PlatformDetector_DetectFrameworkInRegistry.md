# System.Deployment.Application.PlatformDetector::DetectFrameworkInRegistry

- ea: `0x1b2a0`
- end: `0x1b353`
- name: `System.Deployment.Application.PlatformDetector::DetectFrameworkInRegistry`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1b390`

## callees

- `0x17cd0`
- `0x1b2a0`

## string_xrefs

- `0x1b2a9`: `DetectFrameworkInRegistry(`

## pseudocode

```c

```

## disassembly

```asm
0x1b2a0  ldc.i4.s 9
0x1b2a2  newarr   [mscorlib]System.String
0x1b2a7  dup
0x1b2a8  ldc.i4.0
0x1b2a9  ldstr    aDetectframewor// "DetectFrameworkInRegistry("
0x1b2ae  stelem.ref
0x1b2af  dup
0x1b2b0  ldc.i4.1
0x1b2b1  ldarg.0
0x1b2b2  stelem.ref
0x1b2b3  dup
0x1b2b4  ldc.i4.2
0x1b2b5  ldstr    asc_36928// ", "
0x1b2ba  stelem.ref
0x1b2bb  dup
0x1b2bc  ldc.i4.3
0x1b2bd  ldarg.1
0x1b2be  stelem.ref
0x1b2bf  dup
0x1b2c0  ldc.i4.4
0x1b2c1  ldstr    asc_36928// ", "
0x1b2c6  stelem.ref
0x1b2c7  dup
0x1b2c8  ldc.i4.5
0x1b2c9  ldarg.2
0x1b2ca  callvirt instance string [mscorlib]System.Object::ToString()
0x1b2cf  stelem.ref
0x1b2d0  dup
0x1b2d1  ldc.i4.6
0x1b2d2  ldstr    asc_36928// ", "
0x1b2d7  stelem.ref
0x1b2d8  dup
0x1b2d9  ldc.i4.7
0x1b2da  ldarga.s 3
0x1b2dc  call     instance string [mscorlib]System.Boolean::ToString()
0x1b2e1  stelem.ref
0x1b2e2  dup
0x1b2e3  ldc.i4.8
0x1b2e4  ldstr    aCalled_0// ") called"
0x1b2e9  stelem.ref
0x1b2ea  call     string [mscorlib]System.String::Concat(string[])
0x1b2ef  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x1b2f4  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1b2f9  ldarg.0
0x1b2fa  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1b2ff  stloc.0
0x1b300  ldloc.0
0x1b301  brfalse.s loc_1B343
0x1b303  ldloc.0
0x1b304  ldarg.1
0x1b305  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1b30a  stloc.1
0x1b30b  ldarg.3
0x1b30c  brfalse.s loc_1B322
0x1b30e  ldloc.1
0x1b30f  isinst   [mscorlib]System.Int32
0x1b314  brfalse.s loc_1B343
0x1b316  ldloc.1
0x1b317  unbox.any [mscorlib]System.Int32
0x1b31c  brfalse.s loc_1B343
0x1b31e  ldc.i4.1
0x1b31f  stloc.2
0x1b320  leave.s  loc_1B351
0x1b322  ldloc.1
0x1b323  isinst   [mscorlib]System.String
0x1b328  brfalse.s loc_1B343
0x1b32a  ldloc.1
0x1b32b  castclass [mscorlib]System.String
0x1b330  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x1b335  stloc.3
0x1b336  ldloc.3
0x1b337  ldarg.2
0x1b338  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1b33d  brfalse.s loc_1B343
0x1b33f  ldc.i4.1
0x1b340  stloc.2
0x1b341  leave.s  loc_1B351
0x1b343  leave.s  loc_1B34F
0x1b345  ldloc.0
0x1b346  brfalse.s loc_1B34E
0x1b348  ldloc.0
0x1b349  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b34e  endfinally
0x1b34f  ldc.i4.0
0x1b350  ret
0x1b351  ldloc.2
0x1b352  ret
```
