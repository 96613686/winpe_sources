# __scrt_dllmain_exception_filter

- ea: `0x180003a5c`
- end: `0x180003aa4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003754`

## callees

- `0x180003a5c`
- `0x180004550`
- `0x180004658`
- `0x180021010`

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
0x180003a5c  push    rbx
0x180003a5e  push    rbp
0x180003a5f  push    rsi
0x180003a60  push    rdi
0x180003a61  sub     rsp, 28h
0x180003a65  mov     rdi, r9
0x180003a68  mov     rsi, r8
0x180003a6b  mov     ebx, edx
0x180003a6d  mov     rbp, rcx
0x180003a70  call    __scrt_is_ucrt_dll_in_use
0x180003a75  test    eax, eax
0x180003a77  jnz     short loc_180003A8E
0x180003a79  cmp     ebx, 1
0x180003a7c  jnz     short loc_180003A8E
0x180003a7e  mov     r8, rsi
0x180003a81  xor     edx, edx
0x180003a83  mov     rcx, rbp
0x180003a86  mov     rax, rdi
0x180003a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180003a93  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180003a97  add     rsp, 28h
0x180003a9b  pop     rdi
0x180003a9c  pop     rsi
0x180003a9d  pop     rbp
0x180003a9e  pop     rbx
0x180003a9f  jmp     _o__seh_filter_dll_0
```
