# PEComponent::ReadData

- ea: `0x2b110`
- end: `0x2b181`
- name: `PEComponent::ReadData`
- size: `113`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2b1b0`
- `0x2b2a0`
- `0x2b310`
- `0x2b3c0`
- `0x2b530`
- `0x2b5b0`
- `0x2b6f0`
- `0x2b9d0`
- `0x2bb00`
- `0x2bc60`

## callees

- `0x23020`
- `0x2b110`

## pseudocode

```c

```

## disassembly

```asm
0x2b110  ldarg.2
0x2b111  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x2b116  stloc.0
0x2b117  ldloc.0
0x2b118  newarr   [mscorlib]System.Byte
0x2b11d  stloc.1
0x2b11e  ldarg.0
0x2b11f  ldarg.1
0x2b120  ldc.i4.0
0x2b121  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2b126  stloc.2
0x2b127  ldloc.2
0x2b128  ldarg.1
0x2b129  beq.s    loc_2B13B
0x2b12b  ldstr    aExNotenoughdat// "Ex_NotEnoughDataInFile"
0x2b130  call     string System.Deployment.Application.Resources::GetString(string s)
0x2b135  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x2b13a  throw
0x2b13b  ldarg.0
0x2b13c  ldloc.1
0x2b13d  ldc.i4.0
0x2b13e  ldloc.1
0x2b13f  ldlen
0x2b140  conv.i4
0x2b141  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x2b146  stloc.3
0x2b147  ldloc.3
0x2b148  ldloc.0
0x2b149  bge.s    loc_2B15B
0x2b14b  ldstr    aExNotenoughdat// "Ex_NotEnoughDataInFile"
0x2b150  call     string System.Deployment.Application.Resources::GetString(string s)
0x2b155  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0x2b15a  throw
0x2b15b  ldloc.0
0x2b15c  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocCoTaskMem(int32)
0x2b161  stloc.s  4
0x2b163  ldloc.1
0x2b164  ldc.i4.0
0x2b165  ldloc.s  4
0x2b167  ldloc.0
0x2b168  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(unsigned int8[], int32, native int, int32)
0x2b16d  ldloc.s  4
0x2b16f  ldarg.2
0x2b170  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x2b175  stloc.s  5
0x2b177  ldloc.s  4
0x2b179  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeCoTaskMem(native int)
0x2b17e  ldloc.s  5
0x2b180  ret
```
