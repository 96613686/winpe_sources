# RSManagedCrypto.RSCrypto::CreateKeyContainer

- ea: `0x2170`
- end: `0x2181`
- name: `RSManagedCrypto.RSCrypto::CreateKeyContainer`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1020`

## pseudocode

```c

```

## disassembly

```asm
0x2170  ldarg.0
0x2171  ldfld    valuetype RSNativeCrypto* RSManagedCrypto.RSCrypto::m_pNativeCrypto
0x2176  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 RSNativeCrypto.CreateKeyContainer([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype RSNativeCrypto*)
0x217b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x2180  ret
```
