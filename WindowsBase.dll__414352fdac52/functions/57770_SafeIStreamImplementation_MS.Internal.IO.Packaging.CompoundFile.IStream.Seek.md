# SafeIStreamImplementation::MS.Internal.IO.Packaging.CompoundFile.IStream.Seek

- ea: `0x57770`
- end: `0x577ea`
- name: `SafeIStreamImplementation::MS.Internal.IO.Packaging.CompoundFile.IStream.Seek`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2b710`
- `0x2c130`
- `0x57770`
- `0x581b0`

## string_xrefs

- `0x577bb`: `dlibMove`

## pseudocode

```c

```

## disassembly

```asm
0x57770  call     void MS.Internal.WindowsBase.SecurityHelper::DemandCompoundFileIOPermission()
0x57775  ldarg.2
0x57776  ldc.i4.0
0x57777  bge.s    loc_577A6
0x57779  ldstr    aInvalidargumen// "InvalidArgumentValue"
0x5777e  ldc.i4.2
0x5777f  newarr   [mscorlib]System.Object
0x57784  dup
0x57785  ldc.i4.0
0x57786  ldstr    aDworigin// "dwOrigin"
0x5778b  stelem.ref
0x5778c  dup
0x5778d  ldc.i4.1
0x5778e  ldarga.s 2
0x57790  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57795  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5779a  stelem.ref
0x5779b  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x577a0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x577a5  throw
0x577a6  ldarg.1
0x577a7  ldc.i4.0
0x577a8  conv.i8
0x577a9  bge.s    loc_577DB
0x577ab  ldarg.2
0x577ac  brtrue.s loc_577DB
0x577ae  ldstr    aInvalidargumen// "InvalidArgumentValue"
0x577b3  ldc.i4.2
0x577b4  newarr   [mscorlib]System.Object
0x577b9  dup
0x577ba  ldc.i4.0
0x577bb  ldstr    aDlibmove// "dlibMove"
0x577c0  stelem.ref
0x577c1  dup
0x577c2  ldc.i4.1
0x577c3  ldarga.s 1
0x577c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x577ca  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x577cf  stelem.ref
0x577d0  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x577d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x577da  throw
0x577db  ldarg.0
0x577dc  ldfld    class UnsafeNativeIStream SafeIStreamImplementation::_unsafeStream
0x577e1  ldarg.1
0x577e2  ldarg.2
0x577e3  ldarg.3
0x577e4  callvirt instance void UnsafeNativeIStream::Seek(int64 dlibMove, int32 dwOrigin, [out] int64& plibNewPosition)
0x577e9  ret
```
