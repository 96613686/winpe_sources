# __scrt_dllmain_exception_filter

- ea: `0x180001e2c`
- end: `0x180001e74`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001ba4`

## callees

- `0x180001e2c`
- `0x180002628`
- `0x180002798`
- `0x18002a010`

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
0x180001e2c  push    rbx
0x180001e2e  push    rbp
0x180001e2f  push    rsi
0x180001e30  push    rdi
0x180001e31  sub     rsp, 28h
0x180001e35  mov     rdi, r9
0x180001e38  mov     rsi, r8
0x180001e3b  mov     ebx, edx
0x180001e3d  mov     rbp, rcx
0x180001e40  call    __scrt_is_ucrt_dll_in_use
0x180001e45  test    eax, eax
0x180001e47  jnz     short loc_180001E5E
0x180001e49  cmp     ebx, 1
0x180001e4c  jnz     short loc_180001E5E
0x180001e4e  mov     r8, rsi
0x180001e51  xor     edx, edx
0x180001e53  mov     rcx, rbp
0x180001e56  mov     rax, rdi
0x180001e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e5e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001e63  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001e67  add     rsp, 28h
0x180001e6b  pop     rdi
0x180001e6c  pop     rsi
0x180001e6d  pop     rbp
0x180001e6e  pop     rbx
0x180001e6f  jmp     _o__seh_filter_dll_0
```
