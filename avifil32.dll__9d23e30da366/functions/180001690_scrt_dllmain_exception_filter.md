# __scrt_dllmain_exception_filter

- ea: `0x180001690`
- end: `0x1800016d8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x180001690`
- `0x180001c40`
- `0x180001cdc`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001690  push    rbx
0x180001692  push    rbp
0x180001693  push    rsi
0x180001694  push    rdi
0x180001695  sub     rsp, 28h
0x180001699  mov     rdi, r9
0x18000169c  mov     rsi, r8
0x18000169f  mov     ebx, edx
0x1800016a1  mov     rbp, rcx
0x1800016a4  call    __scrt_is_ucrt_dll_in_use
0x1800016a9  test    eax, eax
0x1800016ab  jnz     short loc_1800016C2
0x1800016ad  cmp     ebx, 1
0x1800016b0  jnz     short loc_1800016C2
0x1800016b2  mov     r8, rsi
0x1800016b5  xor     edx, edx
0x1800016b7  mov     rcx, rbp
0x1800016ba  mov     rax, rdi
0x1800016bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016c2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016c7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016cb  add     rsp, 28h
0x1800016cf  pop     rdi
0x1800016d0  pop     rsi
0x1800016d1  pop     rbp
0x1800016d2  pop     rbx
0x1800016d3  jmp     _o__seh_filter_dll_0
```
