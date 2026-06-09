# __scrt_dllmain_exception_filter

- ea: `0x180001670`
- end: `0x1800016b8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x180001670`
- `0x180001c44`
- `0x180001cfa`
- `0x180004010`

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
0x180001670  push    rbx
0x180001672  push    rbp
0x180001673  push    rsi
0x180001674  push    rdi
0x180001675  sub     rsp, 28h
0x180001679  mov     rdi, r9
0x18000167c  mov     rsi, r8
0x18000167f  mov     ebx, edx
0x180001681  mov     rbp, rcx
0x180001684  call    __scrt_is_ucrt_dll_in_use
0x180001689  test    eax, eax
0x18000168b  jnz     short loc_1800016A2
0x18000168d  cmp     ebx, 1
0x180001690  jnz     short loc_1800016A2
0x180001692  mov     r8, rsi
0x180001695  xor     edx, edx
0x180001697  mov     rcx, rbp
0x18000169a  mov     rax, rdi
0x18000169d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016a7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016ab  add     rsp, 28h
0x1800016af  pop     rdi
0x1800016b0  pop     rsi
0x1800016b1  pop     rbp
0x1800016b2  pop     rbx
0x1800016b3  jmp     _o__seh_filter_dll_0
```
