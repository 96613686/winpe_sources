# RSManagedCrypto.RSCrypto::ConvertNativeArrayToManaged

- ea: `0x25c0`
- end: `0x25d7`
- name: `RSManagedCrypto.RSCrypto::ConvertNativeArrayToManaged`
- size: `23`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x2190`
- `0x21d0`
- `0x22a0`
- `0x2310`
- `0x2380`
- `0x23c0`
- `0x2440`
- `0x24b0`

## pseudocode

```c

```

## disassembly

```asm
0x25c0  ldarg.2
0x25c1  newarr   [mscorlib]System.Byte
0x25c6  stloc.0
0x25c7  ldarg.1
0x25c8  call     native int [mscorlib]System.IntPtr::op_Explicit(void*)
0x25cd  ldloc.0
0x25ce  ldc.i4.0
0x25cf  ldarg.2
0x25d0  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x25d5  ldloc.0
0x25d6  ret
```
