# System.Deployment.Application.PlatformDetector::IsNetFX35SP1ClientSignatureAsm

- ea: `0x1bff0`
- end: `0x1c009`
- name: `System.Deployment.Application.PlatformDetector::IsNetFX35SP1ClientSignatureAsm`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1ba20`

## callees

- `0xd930`
- `0xdb00`
- `0x1bff0`

## string_xrefs

- `0x1bff0`: `Sentinel.v3.5Client, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,processorArchitecture=msil`

## pseudocode

```c

```

## disassembly

```asm
0x1bff0  ldstr    aSentinelV35cli// "Sentinel.v3.5Client, Version=3.5.0.0, C"...
0x1bff5  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0x1bffa  stloc.0
0x1bffb  ldloc.0
0x1bffc  ldarg.0
0x1bffd  ldc.i4.1
0x1bffe  callvirt instance bool System.Deployment.Application.DefinitionIdentity::Matches(class System.Deployment.Application.ReferenceIdentity refId, bool exact)
0x1c003  brfalse.s loc_1C007
0x1c005  ldc.i4.1
0x1c006  ret
0x1c007  ldc.i4.0
0x1c008  ret
```
