# MS.Internal.IO.Zip.ZipIOLocalFileBlock::CheckFileAccessParameter

- ea: `0x1cec0`
- end: `0x1cf32`
- name: `MS.Internal.IO.Zip.ZipIOLocalFileBlock::CheckFileAccessParameter`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1c940`

## callees

- `0x1cec0`
- `0x2c100`

## string_xrefs

- `0x1cef6`: `CanNotWriteInReadOnlyMode`
- `0x1cede`: `CanNotReadInWriteOnlyMode`
- `0x1cf26`: `access`
- `0x1cf16`: `CanNotReadWriteInReadOnlyWriteOnlyMode`

## pseudocode

```c

```

## disassembly

```asm
0x1cec0  ldarg.1
0x1cec1  ldc.i4.1
0x1cec2  sub
0x1cec3  switch   loc_1CED6, loc_1CEEE, loc_1CF06
0x1ced4  br.s     loc_1CF26
0x1ced6  ldarg.0
0x1ced7  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x1cedc  brtrue.s loc_1CF31
0x1cede  ldstr    aCannotreadinwr// "CanNotReadInWriteOnlyMode"
0x1cee3  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1cee8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1ceed  throw
0x1ceee  ldarg.0
0x1ceef  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x1cef4  brtrue.s loc_1CF31
0x1cef6  ldstr    aCannotwriteinr// "CanNotWriteInReadOnlyMode"
0x1cefb  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1cf00  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1cf05  throw
0x1cf06  ldarg.0
0x1cf07  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x1cf0c  brfalse.s loc_1CF16
0x1cf0e  ldarg.0
0x1cf0f  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x1cf14  brtrue.s loc_1CF31
0x1cf16  ldstr    aCannotreadwrit// "CanNotReadWriteInReadOnlyWriteOnlyMode"
0x1cf1b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x1cf20  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1cf25  throw
0x1cf26  ldstr    aAccess// "access"
0x1cf2b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x1cf30  throw
0x1cf31  ret
```
