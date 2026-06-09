# System.Deployment.Application.PlatformDetector::IsNetFX35SP1FullSignatureAsm

- ea: `0x1c010`
- end: `0x1c029`
- name: `System.Deployment.Application.PlatformDetector::IsNetFX35SP1FullSignatureAsm`
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
- `0x1c010`

## string_xrefs

- `0x1c010`: `System.Data.Entity, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089,processorArchitecture=msil`

## pseudocode

```c

```

## disassembly

```asm
0x1c010  ldstr    aSystemDataEnti// "System.Data.Entity, Version=3.5.0.0, Cu"...
0x1c015  newobj   instance void System.Deployment.Application.DefinitionIdentity::.ctor(string text)
0x1c01a  stloc.0
0x1c01b  ldloc.0
0x1c01c  ldarg.0
0x1c01d  ldc.i4.1
0x1c01e  callvirt instance bool System.Deployment.Application.DefinitionIdentity::Matches(class System.Deployment.Application.ReferenceIdentity refId, bool exact)
0x1c023  brfalse.s loc_1C027
0x1c025  ldc.i4.1
0x1c026  ret
0x1c027  ldc.i4.0
0x1c028  ret
```
