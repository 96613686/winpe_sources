# __scrt_dllmain_exception_filter

- ea: `0x180001f1c`
- end: `0x180001f64`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001ad4`

## callees

- `0x180001f1c`
- `0x180002580`
- `0x1800026a8`
- `0x18001e010`

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
0x180001f1c  push    rbx
0x180001f1e  push    rbp
0x180001f1f  push    rsi
0x180001f20  push    rdi
0x180001f21  sub     rsp, 28h
0x180001f25  mov     rdi, r9
0x180001f28  mov     rsi, r8
0x180001f2b  mov     ebx, edx
0x180001f2d  mov     rbp, rcx
0x180001f30  call    __scrt_is_ucrt_dll_in_use
0x180001f35  test    eax, eax
0x180001f37  jnz     short loc_180001F4E
0x180001f39  cmp     ebx, 1
0x180001f3c  jnz     short loc_180001F4E
0x180001f3e  mov     r8, rsi
0x180001f41  xor     edx, edx
0x180001f43  mov     rcx, rbp
0x180001f46  mov     rax, rdi
0x180001f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f4e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001f53  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001f57  add     rsp, 28h
0x180001f5b  pop     rdi
0x180001f5c  pop     rsi
0x180001f5d  pop     rbp
0x180001f5e  pop     rbx
0x180001f5f  jmp     _o__seh_filter_dll_0
```
