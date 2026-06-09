# SspirCallRpc2

- ea: `0x1800029d0`
- end: `0x180002a26`
- name: `SspirCallRpc2`
- size: `86`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const void *, _DWORD *, __int16 **, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800012b0`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirCallRpc2(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const void *a4,
        _DWORD *a5,
        __int16 **a6,
        __int64 a7)
{
  SspiSrvCallBegin(a2);
  return SspirCallRpc(a1, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_0], rbx
0x1800029d5  mov     [rsp+arg_8], rsi
0x1800029da  push    rdi
0x1800029db  sub     rsp, 30h
0x1800029df  mov     rbx, rcx
0x1800029e2  mov     rdi, r9
0x1800029e5  mov     rcx, rdx
0x1800029e8  mov     esi, r8d
0x1800029eb  call    SspiSrvCallBegin
0x1800029f0  mov     rax, [rsp+38h+arg_30]
0x1800029f5  mov     r8, rdi
0x1800029f8  mov     r9, [rsp+38h+arg_20]
0x1800029fd  mov     edx, esi
0x1800029ff  mov     [rsp+38h+var_10], rax
0x180002a04  mov     rcx, rbx
0x180002a07  mov     rax, [rsp+38h+arg_28]
0x180002a0c  mov     [rsp+38h+var_18], rax
0x180002a11  call    SspirCallRpc
0x180002a16  mov     rbx, [rsp+38h+arg_0]
0x180002a1b  mov     rsi, [rsp+38h+arg_8]
0x180002a20  add     rsp, 30h
0x180002a24  pop     rdi
0x180002a25  retn
```
