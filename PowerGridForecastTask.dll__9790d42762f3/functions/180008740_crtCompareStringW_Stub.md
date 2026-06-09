# __crtCompareStringW_Stub

- ea: `0x180008740`
- end: `0x18000877d`
- name: `__crtCompareStringW_Stub`
- size: `61`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022e8c`

## callees

- `0x1800268fb`

## pseudocode

```c
__int64 _crtCompareStringW_Stub()
{
  return _crtCompareStringW_0();
}

```

## disassembly

```asm
0x180008740  sub     rsp, 48h
0x180008744  mov     eax, [rsp+48h+arg_30]
0x18000874b  mov     r10d, edx
0x18000874e  mov     [rsp+48h+var_10], eax
0x180008752  mov     edx, ecx
0x180008754  mov     eax, [rsp+48h+arg_28]
0x180008758  xor     ecx, ecx
0x18000875a  mov     [rsp+48h+var_18], eax
0x18000875e  mov     rax, [rsp+48h+arg_20]
0x180008763  mov     [rsp+48h+var_20], rax
0x180008768  mov     [rsp+48h+var_28], r9d
0x18000876d  mov     r9, r8
0x180008770  mov     r8d, r10d
0x180008773  call    __crtCompareStringW_0
0x180008778  add     rsp, 48h
0x18000877c  retn
```
