# System.IO.Packaging.PackagePart::ThrowIfOpenAccessModesAreIncompatible

- ea: `0x49e70`
- end: `0x49ed5`
- name: `System.IO.Packaging.PackagePart::ThrowIfOpenAccessModesAreIncompatible`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x49ad0`

## callees

- `0x2c100`
- `0x48b30`
- `0x492c0`
- `0x492e0`
- `0x49e70`

## string_xrefs

- `0x49e90`: `UnsupportedCombinationOfModeAccess`
- `0x49ec4`: `ContainerAndPartModeIncompatible`

## pseudocode

```c

```

## disassembly

```asm
0x49e70  ldarg.1
0x49e71  call     void System.IO.Packaging.Package::ThrowIfFileModeInvalid(valuetype [mscorlib]System.IO.FileMode mode)
0x49e76  ldarg.2
0x49e77  call     void System.IO.Packaging.Package::ThrowIfFileAccessInvalid(valuetype [mscorlib]System.IO.FileAccess access)
0x49e7c  ldarg.2
0x49e7d  ldc.i4.1
0x49e7e  bne.un.s loc_49EA0
0x49e80  ldarg.1
0x49e81  ldc.i4.2
0x49e82  beq.s    loc_49E90
0x49e84  ldarg.1
0x49e85  ldc.i4.1
0x49e86  beq.s    loc_49E90
0x49e88  ldarg.1
0x49e89  ldc.i4.5
0x49e8a  beq.s    loc_49E90
0x49e8c  ldarg.1
0x49e8d  ldc.i4.6
0x49e8e  bne.un.s loc_49EA0
0x49e90  ldstr    aUnsupportedcom_0// "UnsupportedCombinationOfModeAccess"
0x49e95  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49e9a  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x49e9f  throw
0x49ea0  ldarg.0
0x49ea1  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackagePart::_container
0x49ea6  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.Package::get_FileOpenAccess()
0x49eab  ldc.i4.1
0x49eac  bne.un.s loc_49EB2
0x49eae  ldarg.2
0x49eaf  ldc.i4.1
0x49eb0  bne.un.s loc_49EC4
0x49eb2  ldarg.0
0x49eb3  ldfld    class System.IO.Packaging.Package System.IO.Packaging.PackagePart::_container
0x49eb8  callvirt instance valuetype [mscorlib]System.IO.FileAccess System.IO.Packaging.Package::get_FileOpenAccess()
0x49ebd  ldc.i4.2
0x49ebe  bne.un.s loc_49ED4
0x49ec0  ldarg.2
0x49ec1  ldc.i4.2
0x49ec2  beq.s    loc_49ED4
0x49ec4  ldstr    aContainerandpa// "ContainerAndPartModeIncompatible"
0x49ec9  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49ece  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x49ed3  throw
0x49ed4  ret
```
