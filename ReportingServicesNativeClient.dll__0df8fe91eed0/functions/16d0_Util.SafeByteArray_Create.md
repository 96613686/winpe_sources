# Util.SafeByteArray::Create

- ea: `0x16d0`
- end: `0x1788`
- name: `Util.SafeByteArray::Create`
- size: `184`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x21d0`
- `0x2260`
- `0x2310`
- `0x23c0`
- `0x2440`
- `0x24b0`

## callees

- `0x1180`
- `0x1190`
- `0x11a0`
- `0x11b0`
- `0x11c0`
- `0x11d0`
- `0x11e0`
- `0x16b0`
- `0x16d0`

## pseudocode

```c

```

## disassembly

```asm
0x16d0  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 __CxxQueryExceptionSize()
0x16d5  localloc
0x16d7  stloc.3
0x16d8  newobj   instance void Util.SafeByteArray::.ctor()
0x16dd  stloc.0
0x16de  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x16e3  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x16e8  leave.s  loc_170A
0x16ea  ldarg.0
0x16eb  ldlen
0x16ec  conv.i8
0x16ed  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void* new[](unsigned int64 nativeString)
0x16f2  stloc.2
0x16f3  ldloc.2
0x16f4  stloc.s  6
0x16f6  ldloc.2
0x16f7  brfalse.s loc_1709
0x16f9  ldloca.s 5
0x16fb  ldloc.2
0x16fc  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x1701  ldloc.0
0x1702  ldloc.s  5
0x1704  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::SetHandle(native int)
0x1709  endfinally
0x170a  ldloc.0
0x170b  ldarg.0
0x170c  ldlen
0x170d  conv.i8
0x170e  stfld    unsigned int64 Util.SafeByteArray::m_cb
0x1713  ldloc.s  6
0x1715  call     native int [mscorlib]System.IntPtr::op_Explicit(void*)
0x171a  stloc.s  4
0x171c  ldarg.0
0x171d  ldc.i4.0
0x171e  ldloc.s  4
0x1720  ldarg.0
0x1721  ldlen
0x1722  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(unsigned int8[], int32, native int, int32)
0x1727  leave.s  loc_1786
0x1729  pop
0x172a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionCode()
0x172f  stloc.s  7
0x1731  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionPointers()
0x1736  ldc.i4.0
0x1737  conv.i8
0x1738  ldc.i4.0
0x1739  ldc.i4.0
0x173a  conv.i8
0x173b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 __CxxExceptionFilter(void* nativeString, void* cchSize, [hasfieldmarshal] int32 value, [hasfieldmarshal] void* value)
0x1740  endfilter
0x1742  pop
0x1743  ldc.i4.0
0x1744  stloc.1
0x1745  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionPointers()
0x174a  ldloc.3
0x174b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 __CxxRegisterExceptionObject(void* nativeString, void* cchSize)
0x1750  pop
0x1751  ldloc.0
0x1752  brfalse.s loc_175A
0x1754  ldloc.0
0x1755  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x175a  ldc.i4.0
0x175b  ldc.i4.0
0x175c  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void _CxxThrowException(void* nativeString, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype _s__ThrowInfo* cchSize)
0x1761  leave.s  loc_177A
0x1763  pop
0x1764  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionPointers()
0x1769  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 __CxxDetectRethrow(void* nativeString)
0x176e  stloc.1
0x176f  ldloc.1
0x1770  endfilter
0x1772  pop
0x1773  leave.s  loc_1775
0x1775  ldloc.1
0x1776  brfalse.s loc_177A
0x1778  rethrow
0x177a  leave.s  loc_1784
0x177c  ldloc.3
0x177d  ldloc.1
0x177e  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void __CxxUnregisterExceptionObject(void* nativeString, int32 cchSize)
0x1783  endfinally
0x1784  leave.s  loc_1786
0x1786  ldloc.0
0x1787  ret
```
