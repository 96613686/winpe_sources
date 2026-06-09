# SspirApplyControlToken2

- ea: `0x180002980`
- end: `0x1800029c2`
- name: `SspirApplyControlToken2`
- size: `66`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int128 *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001bf0`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirApplyControlToken2(__int64 a1, __int64 a2, _QWORD *a3, __int128 *a4, __int64 a5)
{
  SspiSrvCallBegin(a2);
  return SspirApplyControlToken(a1, a3, a4, a5);
}

```

## disassembly

```asm
0x180002980  mov     [rsp+arg_0], rbx
0x180002985  mov     [rsp+arg_8], rsi
0x18000298a  push    rdi
0x18000298b  sub     rsp, 20h
0x18000298f  mov     rbx, rcx
0x180002992  mov     rdi, r9
0x180002995  mov     rcx, rdx
0x180002998  mov     rsi, r8
0x18000299b  call    SspiSrvCallBegin
0x1800029a0  mov     r9, [rsp+28h+arg_20]
0x1800029a5  mov     r8, rdi
0x1800029a8  mov     rdx, rsi
0x1800029ab  mov     rcx, rbx
0x1800029ae  mov     rbx, [rsp+28h+arg_0]
0x1800029b3  mov     rsi, [rsp+28h+arg_8]
0x1800029b8  add     rsp, 20h
0x1800029bc  pop     rdi
0x1800029bd  jmp     SspirApplyControlToken
```
