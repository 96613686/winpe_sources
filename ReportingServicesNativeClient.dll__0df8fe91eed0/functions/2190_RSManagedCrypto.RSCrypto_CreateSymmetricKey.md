# RSManagedCrypto.RSCrypto::CreateSymmetricKey

- ea: `0x2190`
- end: `0x21cf`
- name: `RSManagedCrypto.RSCrypto::CreateSymmetricKey`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1030`
- `0x10c0`
- `0x2190`
- `0x2530`
- `0x25c0`

## pseudocode

```c

```

## disassembly

```asm
0x2190  ldc.i4.0
0x2191  conv.i8
0x2192  stloc.0
0x2193  ldnull
0x2194  stloc.1
0x2195  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x219a  ldarg.0
0x219b  call     instance bool RSManagedCrypto.RSCrypto::IsInit()
0x21a0  brtrue.s loc_21C1
0x21a2  ldc.i4.0
0x21a3  stloc.2
0x21a4  ldarg.0
0x21a5  ldfld    valuetype RSNativeCrypto* RSManagedCrypto.RSCrypto::m_pNativeCrypto
0x21aa  ldloca.s 0
0x21ac  ldloca.s 2
0x21ae  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 RSNativeCrypto.CreateSymmetricKey([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype RSNativeCrypto*, unsigned int8** nativeString, modopt([mscorlib]System.Runtime.CompilerServices.IsImplicitlyDereferenced) int32* cchSize)
0x21b3  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x21b8  ldarg.0
0x21b9  ldloc.0
0x21ba  ldloc.2
0x21bb  call     instance unsigned int8[] RSManagedCrypto.RSCrypto::ConvertNativeArrayToManaged(unsigned int8* pNativeArray, int32 numBytes)
0x21c0  stloc.1
0x21c1  leave.s  loc_21CD
0x21c3  ldloc.0
0x21c4  brfalse.s loc_21CC
0x21c6  ldloc.0
0x21c7  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void delete[](void* nativeString)
0x21cc  endfinally
0x21cd  ldloc.1
0x21ce  ret
```
