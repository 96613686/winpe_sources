# std::vector<void *,std::allocator<void *>>::_Xlen(void)

- ea: `0x18002da30`
- end: `0x18002da41`
- name: `?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn(void)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b070`
- `0x18002b1c0`
- `0x18002c6f0`
- `0x18002ca70`
- `0x18002cc70`
- `0x1800607f0`
- `0x180060950`
- `0x180062640`
- `0x180067940`
- `0x180067e40`
- `0x1800704a0`
- `0x180070670`
- `0x1800707d0`
- `0x180088360`
- `0x1800884e0`
- `0x1800aaf70`
- `0x1800ad550`

## callees

- `0x18000e418`

## pseudocode

```c
void __noreturn std::vector<void *>::_Xlen()
{
  sub_18000E418("vector too long");
}

```

## disassembly

```asm
0x18002da30  sub     rsp, 28h
0x18002da34  lea     rcx, aVectorTooLong
0x18002da3b  call    sub_18000E418
```
