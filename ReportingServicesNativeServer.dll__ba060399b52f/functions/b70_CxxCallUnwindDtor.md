# ::___CxxCallUnwindDtor

- ea: `0xb70`
- end: `0xb8a`
- name: `::___CxxCallUnwindDtor`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0xac0`
- `0x1620`

## callees

- `0xb70`
- `0x13b0`

## pseudocode

```c

```

## disassembly

```asm
0xb70  ldarg.1
0xb71  ldarg.0
0xb72  calli    T0x11000042
0xb77  leave.s  loc_B89
0xb79  pop
0xb7a  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionPointers()
0xb7f  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) int32 __FrameUnwindFilter(valuetype _EXCEPTION_POINTERS* rpcEndpointName)
0xb84  endfilter
0xb86  pop
0xb87  leave.s  loc_B89
0xb89  ret
```
