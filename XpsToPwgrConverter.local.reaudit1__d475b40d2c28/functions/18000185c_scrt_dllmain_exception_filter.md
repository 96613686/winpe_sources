# __scrt_dllmain_exception_filter

- ea: `0x18000185c`
- end: `0x1800018a4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800015d4`

## callees

- `0x18000185c`
- `0x180001ff8`
- `0x180002158`
- `0x180011010`

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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000185c  push    rbx
0x18000185e  push    rbp
0x18000185f  push    rsi
0x180001860  push    rdi
0x180001861  sub     rsp, 28h
0x180001865  mov     rdi, r9
0x180001868  mov     rsi, r8
0x18000186b  mov     ebx, edx
0x18000186d  mov     rbp, rcx
0x180001870  call    __scrt_is_ucrt_dll_in_use
0x180001875  test    eax, eax
0x180001877  jnz     short loc_18000188E
0x180001879  cmp     ebx, 1
0x18000187c  jnz     short loc_18000188E
0x18000187e  mov     r8, rsi
0x180001881  xor     edx, edx
0x180001883  mov     rcx, rbp
0x180001886  mov     rax, rdi
0x180001889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000188e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001893  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001897  add     rsp, 28h
0x18000189b  pop     rdi
0x18000189c  pop     rsi
0x18000189d  pop     rbp
0x18000189e  pop     rbx
0x18000189f  jmp     _o__seh_filter_dll_0
```
