# System.Windows.Interop.DocObjHost::ExtractComStream

- ea: `0x1cc6c0`
- end: `0x1cc71b`
- name: `System.Windows.Interop.DocObjHost::ExtractComStream`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1cc6a0`
- `0x23ee80`

## callees

- `0x1cc6c0`
- `0x27a530`

## string_xrefs

- `0x1cc6ca`: `comIStream`
- `0x1cc70f`: `Error reading journal stream from native IStream`

## pseudocode

```c

```

## disassembly

```asm
0x1cc6c0  ldarg.0
0x1cc6c1  isinst   SecuritySuppressedIStream
0x1cc6c6  stloc.0
0x1cc6c7  ldloc.0
0x1cc6c8  brtrue.s loc_1CC6D5
0x1cc6ca  ldstr    aComistream// "comIStream"
0x1cc6cf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cc6d4  throw
0x1cc6d5  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x1cc6da  stloc.1
0x1cc6db  ldc.i4   0x400
0x1cc6e0  newarr   [mscorlib]System.Byte
0x1cc6e5  stloc.2
0x1cc6e6  ldc.i4.0
0x1cc6e7  stloc.3
0x1cc6e8  ldc.i4.0
0x1cc6e9  stloc.3
0x1cc6ea  ldloc.0
0x1cc6eb  ldloc.2
0x1cc6ec  ldc.i4   0x400
0x1cc6f1  ldloca.s 3
0x1cc6f3  callvirt instance void SecuritySuppressedIStream::Read([out] [hasfieldmarshal] unsigned int8[] pv, int32 cb, [out] int32& pcbRead)
0x1cc6f8  ldloc.1
0x1cc6f9  ldloc.2
0x1cc6fa  ldc.i4.0
0x1cc6fb  ldloc.3
0x1cc6fc  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x1cc701  ldloc.3
0x1cc702  ldc.i4.0
0x1cc703  bgt.s    loc_1CC6E8
0x1cc705  ldloc.1
0x1cc706  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1cc70b  ldc.i4.0
0x1cc70c  conv.i8
0x1cc70d  cgt
0x1cc70f  ldstr    aErrorReadingJo// "Error reading journal stream from nativ"...
0x1cc714  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1cc719  ldloc.1
0x1cc71a  ret
```
