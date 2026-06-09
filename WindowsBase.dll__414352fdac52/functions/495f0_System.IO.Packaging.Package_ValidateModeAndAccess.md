# System.IO.Packaging.Package::ValidateModeAndAccess

- ea: `0x495f0`
- end: `0x4965e`
- name: `System.IO.Packaging.Package::ValidateModeAndAccess`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x493b0`

## callees

- `0x2c100`
- `0x492c0`
- `0x492e0`
- `0x495f0`
- `0x5a4e0`

## string_xrefs

- `0x4960c`: `IncompatibleModeOrAccess`
- `0x4962c`: `IncompatibleModeOrAccess`

## pseudocode

```c

```

## disassembly

```asm
0x495f0  ldarg.1
0x495f1  call     void System.IO.Packaging.Package::ThrowIfFileModeInvalid(valuetype [mscorlib]System.IO.FileMode mode)
0x495f6  ldarg.2
0x495f7  call     void System.IO.Packaging.Package::ThrowIfFileAccessInvalid(valuetype [mscorlib]System.IO.FileAccess access)
0x495fc  ldarg.0
0x495fd  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x49602  brtrue.s loc_4961C
0x49604  ldarg.2
0x49605  ldc.i4.3
0x49606  beq.s    loc_4960C
0x49608  ldarg.2
0x49609  ldc.i4.2
0x4960a  bne.un.s loc_4961C
0x4960c  ldstr    aIncompatiblemo// "IncompatibleModeOrAccess"
0x49611  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49616  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x4961b  throw
0x4961c  ldarg.0
0x4961d  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x49622  brtrue.s loc_4963C
0x49624  ldarg.2
0x49625  ldc.i4.3
0x49626  beq.s    loc_4962C
0x49628  ldarg.2
0x49629  ldc.i4.1
0x4962a  bne.un.s loc_4963C
0x4962c  ldstr    aIncompatiblemo// "IncompatibleModeOrAccess"
0x49631  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x49636  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x4963b  throw
0x4963c  ldarg.0
0x4963d  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x49642  brfalse.s loc_4965C
0x49644  ldarg.0
0x49645  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x4964a  brfalse.s loc_4965C
0x4964c  ldarg.2
0x4964d  ldc.i4.1
0x4964e  beq.s    loc_49654
0x49650  ldarg.2
0x49651  ldc.i4.2
0x49652  bne.un.s loc_4965C
0x49654  ldarg.0
0x49655  ldarg.2
0x49656  newobj   instance void RestrictedStream::.ctor(class [mscorlib]System.IO.Stream stream, valuetype [mscorlib]System.IO.FileAccess access)
0x4965b  ret
0x4965c  ldarg.0
0x4965d  ret
```
