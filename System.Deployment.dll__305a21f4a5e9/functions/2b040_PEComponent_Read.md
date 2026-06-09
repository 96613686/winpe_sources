# PEComponent::Read

- ea: `0x2b040`
- end: `0x2b0d4`
- name: `PEComponent::Read`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1a9d0`

## callees

- `0x23020`
- `0x2b040`
- `0x2b0e0`
- `0x2bf00`

## string_xrefs

- `0x2b071`: `Ex_InvalidCopyRequest`
- `0x2b0b1`: `Ex_InvalidCopyRequest`

## pseudocode

```c

```

## disassembly

```asm
0x2b040  ldc.i4.0
0x2b041  stloc.0
0x2b042  ldarg.0
0x2b043  ldfld    object PEComponent::_data
0x2b048  isinst   DataComponent
0x2b04d  brfalse.s loc_2B08F
0x2b04f  ldarg.0
0x2b050  ldfld    object PEComponent::_data
0x2b055  castclass DataComponent
0x2b05a  stloc.1
0x2b05b  ldarg.s  4
0x2b05d  conv.i8
0x2b05e  ldarg.0
0x2b05f  ldfld    int64 PEComponent::_size
0x2b064  ldarg.3
0x2b065  sub
0x2b066  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x2b06b  stloc.2
0x2b06c  ldloc.2
0x2b06d  ldc.i4.0
0x2b06e  conv.i8
0x2b06f  bge.s    loc_2B081
0x2b071  ldstr    aExInvalidcopyr// "Ex_InvalidCopyRequest"
0x2b076  call     string System.Deployment.Application.Resources::GetString(string s)
0x2b07b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2b080  throw
0x2b081  ldloc.1
0x2b082  ldarg.1
0x2b083  ldarg.2
0x2b084  ldarg.3
0x2b085  ldloc.2
0x2b086  conv.i4
0x2b087  callvirt instance int32 DataComponent::Read(unsigned int8[] buffer, int32 bufferOffset, int64 sourceOffset, int32 count)
0x2b08c  stloc.0
0x2b08d  br.s     loc_2B0D2
0x2b08f  ldarg.0
0x2b090  ldfld    object PEComponent::_data
0x2b095  call     unsigned int8[] PEComponent::ToByteArray(object data)
0x2b09a  stloc.3
0x2b09b  ldarg.s  4
0x2b09d  conv.i8
0x2b09e  ldloc.3
0x2b09f  ldlen
0x2b0a0  conv.i4
0x2b0a1  conv.i8
0x2b0a2  ldarg.3
0x2b0a3  sub
0x2b0a4  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x2b0a9  stloc.s  4
0x2b0ab  ldloc.s  4
0x2b0ad  ldc.i4.0
0x2b0ae  conv.i8
0x2b0af  bge.s    loc_2B0C1
0x2b0b1  ldstr    aExInvalidcopyr// "Ex_InvalidCopyRequest"
0x2b0b6  call     string System.Deployment.Application.Resources::GetString(string s)
0x2b0bb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2b0c0  throw
0x2b0c1  ldloc.3
0x2b0c2  ldarg.3
0x2b0c3  conv.i4
0x2b0c4  ldarg.1
0x2b0c5  ldarg.2
0x2b0c6  ldloc.s  4
0x2b0c8  conv.i4
0x2b0c9  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x2b0ce  ldloc.s  4
0x2b0d0  conv.i4
0x2b0d1  stloc.0
0x2b0d2  ldloc.0
0x2b0d3  ret
```
