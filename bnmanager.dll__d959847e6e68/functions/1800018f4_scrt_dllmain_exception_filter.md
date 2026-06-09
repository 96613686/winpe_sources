# __scrt_dllmain_exception_filter

- ea: `0x1800018f4`
- end: `0x18000193c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001634`

## callees

- `0x1800018f4`
- `0x18000212c`
- `0x180002248`
- `0x18000d010`

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
0x1800018f4  push    rbx
0x1800018f6  push    rbp
0x1800018f7  push    rsi
0x1800018f8  push    rdi
0x1800018f9  sub     rsp, 28h
0x1800018fd  mov     rdi, r9
0x180001900  mov     rsi, r8
0x180001903  mov     ebx, edx
0x180001905  mov     rbp, rcx
0x180001908  call    __scrt_is_ucrt_dll_in_use
0x18000190d  test    eax, eax
0x18000190f  jnz     short loc_180001926
0x180001911  cmp     ebx, 1
0x180001914  jnz     short loc_180001926
0x180001916  mov     r8, rsi
0x180001919  xor     edx, edx
0x18000191b  mov     rcx, rbp
0x18000191e  mov     rax, rdi
0x180001921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001926  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000192b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000192f  add     rsp, 28h
0x180001933  pop     rdi
0x180001934  pop     rsi
0x180001935  pop     rbp
0x180001936  pop     rbx
0x180001937  jmp     _o__seh_filter_dll_0
```
