# RSManagedCrypto.RSCrypto::IsInit

- ea: `0x2530`
- end: `0x253c`
- name: `RSManagedCrypto.RSCrypto::IsInit`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x2190`
- `0x2260`
- `0x2310`
- `0x23c0`
- `0x2440`
- `0x24b0`

## callees

- `0xfd0`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldarg.0
0x2531  ldfld    valuetype RSNativeCrypto* RSManagedCrypto.RSCrypto::m_pNativeCrypto
0x2536  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) bool RSNativeCrypto.HasSymmetricKey([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype RSNativeCrypto*)
0x253b  ret
```
