# __scrt_dllmain_exception_filter

- ea: `0x18000ec6c`
- end: `0x18000ecb4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e9e4`

## callees

- `0x18000ec6c`
- `0x18000f3f8`
- `0x18000f4b8`
- `0x180029010`

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
0x18000ec6c  push    rbx
0x18000ec6e  push    rbp
0x18000ec6f  push    rsi
0x18000ec70  push    rdi
0x18000ec71  sub     rsp, 28h
0x18000ec75  mov     rdi, r9
0x18000ec78  mov     rsi, r8
0x18000ec7b  mov     ebx, edx
0x18000ec7d  mov     rbp, rcx
0x18000ec80  call    __scrt_is_ucrt_dll_in_use
0x18000ec85  test    eax, eax
0x18000ec87  jnz     short loc_18000EC9E
0x18000ec89  cmp     ebx, 1
0x18000ec8c  jnz     short loc_18000EC9E
0x18000ec8e  mov     r8, rsi
0x18000ec91  xor     edx, edx
0x18000ec93  mov     rcx, rbp
0x18000ec96  mov     rax, rdi
0x18000ec99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec9e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000eca3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000eca7  add     rsp, 28h
0x18000ecab  pop     rdi
0x18000ecac  pop     rsi
0x18000ecad  pop     rbp
0x18000ecae  pop     rbx
0x18000ecaf  jmp     _o__seh_filter_dll_0
```
