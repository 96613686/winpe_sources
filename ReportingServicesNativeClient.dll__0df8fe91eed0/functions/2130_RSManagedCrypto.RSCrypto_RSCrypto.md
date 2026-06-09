# RSManagedCrypto.RSCrypto::!RSCrypto

- ea: `0x2130`
- end: `0x2147`
- name: `RSManagedCrypto.RSCrypto::!RSCrypto`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x2120`
- `0x25e0`

## callees

- `0xfe0`
- `0x1000`
- `0x2130`

## pseudocode

```c

```

## disassembly

```asm
0x2130  ldarg.0
0x2131  ldfld    valuetype RSNativeCrypto* RSManagedCrypto.RSCrypto::m_pNativeCrypto
0x2136  stloc.0
0x2137  ldloc.0
0x2138  brfalse.s loc_2146
0x213a  ldloc.0
0x213b  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void RSNativeCrypto.{dtor}([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype RSNativeCrypto*)
0x2140  ldloc.0
0x2141  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) void delete([hasfieldmarshal] void*)
0x2146  ret
```
