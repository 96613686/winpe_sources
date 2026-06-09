# RSManagedCrypto.RSCrypto::ImportSymmetricKey

- ea: `0x21d0`
- end: `0x2252`
- name: `RSManagedCrypto.RSCrypto::ImportSymmetricKey`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x2540`

## callees

- `0x1040`
- `0x10c0`
- `0x13c0`
- `0x1600`
- `0x1630`
- `0x1640`
- `0x16d0`
- `0x1790`
- `0x21d0`
- `0x25c0`

## pseudocode

```c

```

## disassembly

```asm
0x21d0  ldnull
0x21d1  stloc.1
0x21d2  ldnull
0x21d3  stloc.0
0x21d4  ldc.i4.0
0x21d5  conv.i8
0x21d6  stloc.2
0x21d7  ldc.i4.0
0x21d8  conv.i8
0x21d9  stloc.s  5
0x21db  ldnull
0x21dc  stloc.3
0x21dd  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x21e2  ldarg.1
0x21e3  call     class Util.SafeByteArray Util.SafeByteArray::Create(unsigned int8[] managedArray)
0x21e8  stloc.1
0x21e9  ldarg.2
0x21ea  call     class Util.SafeStringToHGlobalUni Util.SafeStringToHGlobalUni::Create(string s)
0x21ef  stloc.0
0x21f0  ldloc.0
0x21f1  call     instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x21f6  ldloca.s 5
0x21f8  call     void Util.StringUtilities::GetStringSize(native int nativeString, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) unsigned int64* cchSize)
0x21fd  ldc.i4.0
0x21fe  stloc.s  4
0x2200  ldarg.0
0x2201  ldfld    valuetype RSNativeCrypto* RSManagedCrypto.RSCrypto::m_pNativeCrypto
0x2206  ldloc.1
0x2207  call     instance unsigned int8* Util.SafeByteArray::ToPointer()
0x220c  ldarg.1
0x220d  ldlen
0x220e  ldloc.0
0x220f  call     instance unsigned int16* Util.SafeStringToHGlobalUni::ToPointer()
0x2214  ldloca.s 2
0x2216  ldloca.s 4
0x2218  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 RSNativeCrypto.ImportSymmetricKey([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype RSNativeCrypto*, unsigned int8* nativeString, int32 cchSize, [hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int16* value, [hasfieldmarshal] unsigned int8** value, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) int32* managedArray)
0x221d  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x2222  ldarg.0
0x2223  ldloc.2
0x2224  ldloc.s  4
0x2226  call     instance unsigned int8[] RSManagedCrypto.RSCrypto::ConvertNativeArrayToManaged(unsigned int8* pNativeArray, int32 numBytes)
0x222b  stloc.3
0x222c  leave.s  loc_2250
0x222e  ldloc.1
0x222f  brfalse.s loc_2237
0x2231  ldloc.1
0x2232  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x2237  ldloc.0
0x2238  brfalse.s loc_2246
0x223a  ldloc.0
0x223b  call     instance void Util.SafeStringToHGlobalUni::ZeroString()
0x2240  ldloc.0
0x2241  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x2246  ldloc.2
0x2247  brfalse.s loc_224F
0x2249  ldloc.2
0x224a  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void delete[](void* nativeString)
0x224f  endfinally
0x2250  ldloc.3
0x2251  ret
```
