# BlankDataBlock::Read

- ea: `0x2bfc0`
- end: `0x2bffe`
- name: `BlankDataBlock::Read`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x23020`
- `0x2bfc0`

## string_xrefs

- `0x2bfd8`: `Ex_InvalidCopyRequest`

## pseudocode

```c

```

## disassembly

```asm
0x2bfc0  ldc.i4.0
0x2bfc1  stloc.0
0x2bfc2  ldarg.s  4
0x2bfc4  conv.i8
0x2bfc5  ldarg.0
0x2bfc6  ldfld    int64 BlankDataBlock::_size
0x2bfcb  ldarg.3
0x2bfcc  sub
0x2bfcd  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x2bfd2  conv.i4
0x2bfd3  stloc.0
0x2bfd4  ldloc.0
0x2bfd5  ldc.i4.0
0x2bfd6  bge.s    loc_2BFE8
0x2bfd8  ldstr    aExInvalidcopyr// "Ex_InvalidCopyRequest"
0x2bfdd  call     string System.Deployment.Application.Resources::GetString(string s)
0x2bfe2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2bfe7  throw
0x2bfe8  ldc.i4.0
0x2bfe9  stloc.1
0x2bfea  ldc.i4.0
0x2bfeb  stloc.1
0x2bfec  br.s     loc_2BFF8
0x2bfee  ldarg.1
0x2bfef  ldarg.2
0x2bff0  ldloc.1
0x2bff1  add
0x2bff2  ldc.i4.0
0x2bff3  stelem.i1
0x2bff4  ldloc.1
0x2bff5  ldc.i4.1
0x2bff6  add
0x2bff7  stloc.1
0x2bff8  ldloc.1
0x2bff9  ldloc.0
0x2bffa  blt.s    loc_2BFEE
0x2bffc  ldloc.0
0x2bffd  ret
```
