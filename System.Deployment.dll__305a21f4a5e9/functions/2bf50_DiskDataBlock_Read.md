# DiskDataBlock::Read

- ea: `0x2bf50`
- end: `0x2bf9e`
- name: `DiskDataBlock::Read`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x23020`
- `0x2bf50`

## string_xrefs

- `0x2bf68`: `Ex_InvalidCopyRequest`

## pseudocode

```c

```

## disassembly

```asm
0x2bf50  ldc.i4.0
0x2bf51  stloc.0
0x2bf52  ldarg.s  4
0x2bf54  conv.i8
0x2bf55  ldarg.0
0x2bf56  ldfld    int64 DiskDataBlock::_size
0x2bf5b  ldarg.3
0x2bf5c  sub
0x2bf5d  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x2bf62  conv.i4
0x2bf63  stloc.0
0x2bf64  ldloc.0
0x2bf65  ldc.i4.0
0x2bf66  bge.s    loc_2BF78
0x2bf68  ldstr    aExInvalidcopyr// "Ex_InvalidCopyRequest"
0x2bf6d  call     string System.Deployment.Application.Resources::GetString(string s)
0x2bf72  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2bf77  throw
0x2bf78  ldarg.0
0x2bf79  ldfld    class [mscorlib]System.IO.FileStream DiskDataBlock::_file
0x2bf7e  ldarg.0
0x2bf7f  ldfld    int64 DiskDataBlock::_address
0x2bf84  ldarg.3
0x2bf85  add
0x2bf86  ldc.i4.0
0x2bf87  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2bf8c  pop
0x2bf8d  ldarg.0
0x2bf8e  ldfld    class [mscorlib]System.IO.FileStream DiskDataBlock::_file
0x2bf93  ldarg.1
0x2bf94  ldarg.2
0x2bf95  ldloc.0
0x2bf96  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x2bf9b  stloc.0
0x2bf9c  ldloc.0
0x2bf9d  ret
```
