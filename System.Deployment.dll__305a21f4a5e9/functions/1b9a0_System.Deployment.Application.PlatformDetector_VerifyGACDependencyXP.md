# System.Deployment.Application.PlatformDetector::VerifyGACDependencyXP

- ea: `0x1b9a0`
- end: `0x1b9fb`
- name: `System.Deployment.Application.PlatformDetector::VerifyGACDependencyXP`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1b880`

## callees

- `0x18fd0`
- `0x1a360`
- `0x1a370`
- `0x1b9a0`
- `0x1c6b0`
- `0x20aa0`
- `0x20b30`
- `0x2a7f0`

## string_xrefs

- `0x1b9aa`: `.manifest`

## pseudocode

```c

```

## disassembly

```asm
0x1b9a0  call     bool System.Deployment.Application.PlatformSpecific::get_OnXPOrAbove()
0x1b9a5  brtrue.s loc_1B9A9
0x1b9a7  ldc.i4.0
0x1b9a8  ret
0x1b9a9  ldarg.1
0x1b9aa  ldstr    aManifest// ".manifest"
0x1b9af  newobj   instance void System.Deployment.Application.TempFile::.ctor(string basePath, string suffix)
0x1b9b4  stloc.0
0x1b9b5  ldarg.0
0x1b9b6  ldloc.0
0x1b9b7  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x1b9bc  call     void System.Deployment.Application.ManifestGenerator::GenerateGACDetectionManifest(class System.Deployment.Application.ReferenceIdentity refId, string outputManifest)
0x1b9c1  ldloc.0
0x1b9c2  callvirt instance string System.Deployment.Application.TempFile::get_Path()
0x1b9c7  newobj   instance void ACTCTXW::.ctor(string manifestPath)
0x1b9cc  stloc.1
0x1b9cd  ldloc.1
0x1b9ce  call     native int System.Deployment.Application.NativeMethods::CreateActCtxW([in] class ACTCTXW actCtx)
0x1b9d3  stloc.2
0x1b9d4  ldloc.2
0x1b9d5  ldsfld   native int System.Deployment.Application.NativeMethods::INVALID_HANDLE_VALUE
0x1b9da  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1b9df  brfalse.s loc_1B9EB
0x1b9e1  ldloc.2
0x1b9e2  call     void System.Deployment.Application.NativeMethods::ReleaseActCtx([in] native int hActCtx)
0x1b9e7  ldc.i4.1
0x1b9e8  stloc.3
0x1b9e9  leave.s  loc_1B9F9
0x1b9eb  ldc.i4.0
0x1b9ec  stloc.3
0x1b9ed  leave.s  loc_1B9F9
0x1b9ef  ldloc.0
0x1b9f0  brfalse.s loc_1B9F8
0x1b9f2  ldloc.0
0x1b9f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b9f8  endfinally
0x1b9f9  ldloc.3
0x1b9fa  ret
```
