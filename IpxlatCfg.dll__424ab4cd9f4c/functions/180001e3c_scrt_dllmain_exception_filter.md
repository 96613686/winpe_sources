# __scrt_dllmain_exception_filter

- ea: `0x180001e3c`
- end: `0x180001e84`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001bb4`

## callees

- `0x180001e3c`
- `0x1800028a8`
- `0x1800029f8`
- `0x180019010`

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
0x180001e3c  push    rbx
0x180001e3e  push    rbp
0x180001e3f  push    rsi
0x180001e40  push    rdi
0x180001e41  sub     rsp, 28h
0x180001e45  mov     rdi, r9
0x180001e48  mov     rsi, r8
0x180001e4b  mov     ebx, edx
0x180001e4d  mov     rbp, rcx
0x180001e50  call    __scrt_is_ucrt_dll_in_use
0x180001e55  test    eax, eax
0x180001e57  jnz     short loc_180001E6E
0x180001e59  cmp     ebx, 1
0x180001e5c  jnz     short loc_180001E6E
0x180001e5e  mov     r8, rsi
0x180001e61  xor     edx, edx
0x180001e63  mov     rcx, rbp
0x180001e66  mov     rax, rdi
0x180001e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e6e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001e73  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001e77  add     rsp, 28h
0x180001e7b  pop     rdi
0x180001e7c  pop     rsi
0x180001e7d  pop     rbp
0x180001e7e  pop     rbx
0x180001e7f  jmp     _o__seh_filter_dll_0
```
