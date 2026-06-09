# __scrt_dllmain_exception_filter

- ea: `0x180002160`
- end: `0x1800021a8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001e94`

## callees

- `0x180002160`
- `0x180002a18`
- `0x180002b18`
- `0x180018010`

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
0x180002160  push    rbx
0x180002162  push    rbp
0x180002163  push    rsi
0x180002164  push    rdi
0x180002165  sub     rsp, 28h
0x180002169  mov     rdi, r9
0x18000216c  mov     rsi, r8
0x18000216f  mov     ebx, edx
0x180002171  mov     rbp, rcx
0x180002174  call    __scrt_is_ucrt_dll_in_use
0x180002179  test    eax, eax
0x18000217b  jnz     short loc_180002192
0x18000217d  cmp     ebx, 1
0x180002180  jnz     short loc_180002192
0x180002182  mov     r8, rsi
0x180002185  xor     edx, edx
0x180002187  mov     rcx, rbp
0x18000218a  mov     rax, rdi
0x18000218d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002192  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002197  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000219b  add     rsp, 28h
0x18000219f  pop     rdi
0x1800021a0  pop     rsi
0x1800021a1  pop     rbp
0x1800021a2  pop     rbx
0x1800021a3  jmp     _o__seh_filter_dll_0
```
