# SspirAcquireCredentialsHandle2

- ea: `0x1800028b0`
- end: `0x180002976`
- name: `SspirAcquireCredentialsHandle2`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, __int64, int, __int64, __int64, __int64, __int64, int, _OWORD *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001540`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall SspirAcquireCredentialsHandle2(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        int a11,
        _OWORD *a12,
        __int64 a13)
{
  SspiSrvCallBegin(a2);
  return SspirAcquireCredentialsHandle(a1, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13);
}

```

## disassembly

```asm
0x1800028b0  mov     [rsp+arg_0], rbx
0x1800028b5  mov     [rsp+arg_8], rsi
0x1800028ba  push    rdi
0x1800028bb  sub     rsp, 70h
0x1800028bf  mov     rbx, rcx
0x1800028c2  mov     rdi, r9
0x1800028c5  mov     rcx, rdx
0x1800028c8  mov     rsi, r8
0x1800028cb  call    SspiSrvCallBegin
0x1800028d0  mov     rax, [rsp+78h+arg_70]
0x1800028d8  mov     r8, rdi
0x1800028db  mov     r9, [rsp+78h+arg_20]
0x1800028e3  mov     rdx, rsi
0x1800028e6  mov     [rsp+78h+var_10], rax
0x1800028eb  mov     rcx, rbx
0x1800028ee  mov     rax, [rsp+78h+arg_68]
0x1800028f6  mov     [rsp+78h+var_18], rax
0x1800028fb  mov     rax, [rsp+78h+arg_60]
0x180002903  mov     [rsp+78h+var_20], rax
0x180002908  mov     rax, [rsp+78h+arg_58]
0x180002910  mov     [rsp+78h+var_28], rax
0x180002915  mov     eax, [rsp+78h+arg_50]
0x18000291c  mov     [rsp+78h+var_30], eax
0x180002920  mov     rax, [rsp+78h+arg_48]
0x180002928  mov     [rsp+78h+var_38], rax
0x18000292d  mov     rax, [rsp+78h+arg_40]
0x180002935  mov     [rsp+78h+var_40], rax
0x18000293a  mov     rax, [rsp+78h+arg_38]
0x180002942  mov     [rsp+78h+var_48], rax
0x180002947  mov     rax, [rsp+78h+arg_30]
0x18000294f  mov     [rsp+78h+var_50], rax
0x180002954  mov     eax, [rsp+78h+arg_28]
0x18000295b  mov     [rsp+78h+var_58], eax
0x18000295f  call    SspirAcquireCredentialsHandle
0x180002964  lea     r11, [rsp+78h+var_8]
0x180002969  mov     rbx, [r11+10h]
0x18000296d  mov     rsi, [r11+18h]
0x180002971  mov     rsp, r11
0x180002974  pop     rdi
0x180002975  retn
```
