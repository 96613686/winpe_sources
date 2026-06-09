# __scrt_dllmain_exception_filter

- ea: `0x18000167c`
- end: `0x1800016c4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012b4`

## callees

- `0x18000167c`
- `0x180001c54`
- `0x180001cf2`
- `0x180003010`

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
0x18000167c  push    rbx
0x18000167e  push    rbp
0x18000167f  push    rsi
0x180001680  push    rdi
0x180001681  sub     rsp, 28h
0x180001685  mov     rdi, r9
0x180001688  mov     rsi, r8
0x18000168b  mov     ebx, edx
0x18000168d  mov     rbp, rcx
0x180001690  call    __scrt_is_ucrt_dll_in_use
0x180001695  test    eax, eax
0x180001697  jnz     short loc_1800016AE
0x180001699  cmp     ebx, 1
0x18000169c  jnz     short loc_1800016AE
0x18000169e  mov     r8, rsi
0x1800016a1  xor     edx, edx
0x1800016a3  mov     rcx, rbp
0x1800016a6  mov     rax, rdi
0x1800016a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016ae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016b3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016b7  add     rsp, 28h
0x1800016bb  pop     rdi
0x1800016bc  pop     rsi
0x1800016bd  pop     rbp
0x1800016be  pop     rbx
0x1800016bf  jmp     _o__seh_filter_dll_0
```
