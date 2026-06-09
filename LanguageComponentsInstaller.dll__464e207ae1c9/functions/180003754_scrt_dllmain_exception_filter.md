# __scrt_dllmain_exception_filter

- ea: `0x180003754`
- end: `0x18000379c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003394`

## callees

- `0x180003754`
- `0x180003fac`
- `0x1800040b8`
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
0x180003754  push    rbx
0x180003756  push    rbp
0x180003757  push    rsi
0x180003758  push    rdi
0x180003759  sub     rsp, 28h
0x18000375d  mov     rdi, r9
0x180003760  mov     rsi, r8
0x180003763  mov     ebx, edx
0x180003765  mov     rbp, rcx
0x180003768  call    __scrt_is_ucrt_dll_in_use
0x18000376d  test    eax, eax
0x18000376f  jnz     short loc_180003786
0x180003771  cmp     ebx, 1
0x180003774  jnz     short loc_180003786
0x180003776  mov     r8, rsi
0x180003779  xor     edx, edx
0x18000377b  mov     rcx, rbp
0x18000377e  mov     rax, rdi
0x180003781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003786  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000378b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000378f  add     rsp, 28h
0x180003793  pop     rdi
0x180003794  pop     rsi
0x180003795  pop     rbp
0x180003796  pop     rbx
0x180003797  jmp     _o__seh_filter_dll_0
```
