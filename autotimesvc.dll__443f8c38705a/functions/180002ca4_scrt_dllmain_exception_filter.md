# __scrt_dllmain_exception_filter

- ea: `0x180002ca4`
- end: `0x180002cec`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800028e4`

## callees

- `0x180002ca4`
- `0x1800034f8`
- `0x180003608`
- `0x180012010`

## pseudocode

```c
int __fastcall _scrt_dllmain_exception_filter(
        __int64 a1,
        int a2,
        __int64 a3,
        void (__fastcall *a4)(__int64, _QWORD, __int64),
        unsigned int ExceptionNum,
        struct _EXCEPTION_POINTERS *ExceptionPtr)
{
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180002ca4  push    rbx
0x180002ca6  push    rbp
0x180002ca7  push    rsi
0x180002ca8  push    rdi
0x180002ca9  sub     rsp, 28h
0x180002cad  mov     rdi, r9
0x180002cb0  mov     rsi, r8
0x180002cb3  mov     ebx, edx
0x180002cb5  mov     rbp, rcx
0x180002cb8  call    __scrt_is_ucrt_dll_in_use
0x180002cbd  test    eax, eax
0x180002cbf  jnz     short loc_180002CD6
0x180002cc1  cmp     ebx, 1
0x180002cc4  jnz     short loc_180002CD6
0x180002cc6  mov     r8, rsi
0x180002cc9  xor     edx, edx
0x180002ccb  mov     rcx, rbp
0x180002cce  mov     rax, rdi
0x180002cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002cdb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002cdf  add     rsp, 28h
0x180002ce3  pop     rdi
0x180002ce4  pop     rsi
0x180002ce5  pop     rbp
0x180002ce6  pop     rbx
0x180002ce7  jmp     _o__seh_filter_dll_0
```
