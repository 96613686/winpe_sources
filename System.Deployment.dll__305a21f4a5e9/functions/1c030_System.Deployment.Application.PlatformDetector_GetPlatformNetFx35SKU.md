# System.Deployment.Application.PlatformDetector::GetPlatformNetFx35SKU

- ea: `0x1c030`
- end: `0x1c077`
- name: `System.Deployment.Application.PlatformDetector::GetPlatformNetFx35SKU`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1ba20`

## callees

- `0xdce0`
- `0x1b880`
- `0x1c030`

## string_xrefs

- `0x1c030`: `Sentinel.v3.5Client, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,processorArchitecture=msil`
- `0x1c03b`: `System.Data.Entity, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089,processorArchitecture=msil`

## pseudocode

```c

```

## disassembly

```asm
0x1c030  ldstr    aSentinelV35cli// "Sentinel.v3.5Client, Version=3.5.0.0, C"...
0x1c035  newobj   instance void System.Deployment.Application.ReferenceIdentity::.ctor(string text)
0x1c03a  stloc.0
0x1c03b  ldstr    aSystemDataEnti// "System.Data.Entity, Version=3.5.0.0, Cu"...
0x1c040  newobj   instance void System.Deployment.Application.ReferenceIdentity::.ctor(string text)
0x1c045  stloc.1
0x1c046  ldc.i4.0
0x1c047  stloc.2
0x1c048  ldc.i4.0
0x1c049  stloc.3
0x1c04a  ldarg.0
0x1c04b  ldarg.1
0x1c04c  ldarg.2
0x1c04d  ldloc.0
0x1c04e  ldarg.3
0x1c04f  call     bool System.Deployment.Application.PlatformDetector::VerifyGACDependency(class IAssemblyCache AssemblyCache, bool targetOtherClr, class CCorRuntimeHost RuntimeHost, class System.Deployment.Application.ReferenceIdentity refId, string tempDir)
0x1c054  brfalse.s loc_1C058
0x1c056  ldc.i4.1
0x1c057  stloc.2
0x1c058  ldarg.0
0x1c059  ldarg.1
0x1c05a  ldarg.2
0x1c05b  ldloc.1
0x1c05c  ldarg.3
0x1c05d  call     bool System.Deployment.Application.PlatformDetector::VerifyGACDependency(class IAssemblyCache AssemblyCache, bool targetOtherClr, class CCorRuntimeHost RuntimeHost, class System.Deployment.Application.ReferenceIdentity refId, string tempDir)
0x1c062  brfalse.s loc_1C066
0x1c064  ldc.i4.1
0x1c065  stloc.3
0x1c066  ldloc.2
0x1c067  brfalse.s loc_1C06E
0x1c069  ldloc.3
0x1c06a  brtrue.s loc_1C06E
0x1c06c  ldc.i4.1
0x1c06d  ret
0x1c06e  ldloc.2
0x1c06f  ldloc.3
0x1c070  and
0x1c071  brfalse.s loc_1C075
0x1c073  ldc.i4.2
0x1c074  ret
0x1c075  ldc.i4.0
0x1c076  ret
```
