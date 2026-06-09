# __scrt_dllmain_exception_filter

- ea: `0x180001f08`
- end: `0x180001f50`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001b24`

## callees

- `0x180001f08`
- `0x180002594`
- `0x1800028a8`
- `0x180009010`

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
0x180001f08  push    rbx
0x180001f0a  push    rbp
0x180001f0b  push    rsi
0x180001f0c  push    rdi
0x180001f0d  sub     rsp, 28h
0x180001f11  mov     rdi, r9
0x180001f14  mov     rsi, r8
0x180001f17  mov     ebx, edx
0x180001f19  mov     rbp, rcx
0x180001f1c  call    __scrt_is_ucrt_dll_in_use
0x180001f21  test    eax, eax
0x180001f23  jnz     short loc_180001F3A
0x180001f25  cmp     ebx, 1
0x180001f28  jnz     short loc_180001F3A
0x180001f2a  mov     r8, rsi
0x180001f2d  xor     edx, edx
0x180001f2f  mov     rcx, rbp
0x180001f32  mov     rax, rdi
0x180001f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f3a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001f3f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001f43  add     rsp, 28h
0x180001f47  pop     rdi
0x180001f48  pop     rsi
0x180001f49  pop     rbp
0x180001f4a  pop     rbx
0x180001f4b  jmp     _o__seh_filter_dll_0
```
