# MS.Internal.FontCache.Util::ThrowWin32Exception

- ea: `0x12cbc0`
- end: `0x12cc72`
- name: `MS.Internal.FontCache.Util::ThrowWin32Exception`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x12cd50`

## callees

- `0x12cba0`
- `0x12cbc0`
- `0x146e70`

## string_xrefs

- `0x12cc04`: `DirectoryNotFoundExceptionWithFileName`
- `0x12cc1e`: `UnauthorizedAccessExceptionWithFileName`
- `0x12cc38`: `PathTooLongExceptionWithFileName`

## pseudocode

```c

```

## disassembly

```asm
0x12cbc0  ldarga.s 1
0x12cbc2  call     void MS.Internal.FontCache.Util::ValidateFileNamePermissions(string& fileName)
0x12cbc7  ldarg.0
0x12cbc8  ldc.i4.2
0x12cbc9  sub
0x12cbca  switch   loc_12CBE9, loc_12CC04, loc_12CC52, loc_12CC1E
0x12cbdf  ldarg.0
0x12cbe0  ldc.i4   0xCE
0x12cbe5  beq.s    loc_12CC38
0x12cbe7  br.s     loc_12CC52
0x12cbe9  ldstr    aFilenotfoundex// "FileNotFoundExceptionWithFileName"
0x12cbee  ldc.i4.1
0x12cbef  newarr   [mscorlib]System.Object
0x12cbf4  dup
0x12cbf5  ldc.i4.0
0x12cbf6  ldarg.1
0x12cbf7  stelem.ref
0x12cbf8  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x12cbfd  ldarg.1
0x12cbfe  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x12cc03  throw
0x12cc04  ldstr    aDirectorynotfo// "DirectoryNotFoundExceptionWithFileName"
0x12cc09  ldc.i4.1
0x12cc0a  newarr   [mscorlib]System.Object
0x12cc0f  dup
0x12cc10  ldc.i4.0
0x12cc11  ldarg.1
0x12cc12  stelem.ref
0x12cc13  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x12cc18  newobj   instance void [mscorlib]System.IO.DirectoryNotFoundException::.ctor(string)
0x12cc1d  throw
0x12cc1e  ldstr    aUnauthorizedac// "UnauthorizedAccessExceptionWithFileName"
0x12cc23  ldc.i4.1
0x12cc24  newarr   [mscorlib]System.Object
0x12cc29  dup
0x12cc2a  ldc.i4.0
0x12cc2b  ldarg.1
0x12cc2c  stelem.ref
0x12cc2d  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x12cc32  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x12cc37  throw
0x12cc38  ldstr    aPathtoolongexc// "PathTooLongExceptionWithFileName"
0x12cc3d  ldc.i4.1
0x12cc3e  newarr   [mscorlib]System.Object
0x12cc43  dup
0x12cc44  ldc.i4.0
0x12cc45  ldarg.1
0x12cc46  stelem.ref
0x12cc47  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x12cc4c  newobj   instance void [mscorlib]System.IO.PathTooLongException::.ctor(string)
0x12cc51  throw
0x12cc52  ldstr    aIoexceptionwit// "IOExceptionWithFileName"
0x12cc57  ldc.i4.1
0x12cc58  newarr   [mscorlib]System.Object
0x12cc5d  dup
0x12cc5e  ldc.i4.0
0x12cc5f  ldarg.1
0x12cc60  stelem.ref
0x12cc61  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x12cc66  ldarg.0
0x12cc67  call     int32 [WindowsBase]MS.Win32.NativeMethods::MakeHRFromErrorCode(int32)
0x12cc6c  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string, int32)
0x12cc71  throw
```
