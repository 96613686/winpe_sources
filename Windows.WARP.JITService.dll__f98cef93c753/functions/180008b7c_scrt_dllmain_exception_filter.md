# __scrt_dllmain_exception_filter

- ea: `0x180008b7c`
- end: `0x180008bc4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800088f4`

## callees

- `0x180008b7c`
- `0x1800092e8`
- `0x1800093f8`
- `0x18000a010`

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
0x180008b7c  push    rbx
0x180008b7e  push    rbp
0x180008b7f  push    rsi
0x180008b80  push    rdi
0x180008b81  sub     rsp, 28h
0x180008b85  mov     rdi, r9
0x180008b88  mov     rsi, r8
0x180008b8b  mov     ebx, edx
0x180008b8d  mov     rbp, rcx
0x180008b90  call    __scrt_is_ucrt_dll_in_use
0x180008b95  test    eax, eax
0x180008b97  jnz     short loc_180008BAE
0x180008b99  cmp     ebx, 1
0x180008b9c  jnz     short loc_180008BAE
0x180008b9e  mov     r8, rsi
0x180008ba1  xor     edx, edx
0x180008ba3  mov     rcx, rbp
0x180008ba6  mov     rax, rdi
0x180008ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180008bb3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180008bb7  add     rsp, 28h
0x180008bbb  pop     rdi
0x180008bbc  pop     rsi
0x180008bbd  pop     rbp
0x180008bbe  pop     rbx
0x180008bbf  jmp     _o__seh_filter_dll_0
```
