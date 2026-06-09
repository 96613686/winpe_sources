# RSManagedCrypto.RSCrypto::Dispose

- ea: `0x25e0`
- end: `0x25fc`
- name: `RSManagedCrypto.RSCrypto::Dispose`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x2600`
- `0x2610`

## callees

- `0x2120`
- `0x2130`
- `0x25e0`

## pseudocode

```c

```

## disassembly

```asm
0x25e0  ldarg.1
0x25e1  brfalse.s loc_25EB
0x25e3  ldarg.0
0x25e4  call     instance void RSManagedCrypto.RSCrypto::~RSCrypto()
0x25e9  br.s     loc_25FB
0x25eb  nop
0x25ec  ldarg.0
0x25ed  call     instance void RSManagedCrypto.RSCrypto::!RSCrypto()
0x25f2  leave.s  loc_25FB
0x25f4  ldarg.0
0x25f5  call     instance void [mscorlib]System.Runtime.ConstrainedExecution.CriticalFinalizerObject::Finalize()
0x25fa  endfinally
0x25fb  ret
```
