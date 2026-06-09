# __scrt_dllmain_exception_filter

- ea: `0x180001d7c`
- end: `0x180001dc4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001ae4`

## callees

- `0x180001d7c`
- `0x180002670`
- `0x1800027ba`
- `0x180010010`

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
0x180001d7c  push    rbx
0x180001d7e  push    rbp
0x180001d7f  push    rsi
0x180001d80  push    rdi
0x180001d81  sub     rsp, 28h
0x180001d85  mov     rdi, r9
0x180001d88  mov     rsi, r8
0x180001d8b  mov     ebx, edx
0x180001d8d  mov     rbp, rcx
0x180001d90  call    __scrt_is_ucrt_dll_in_use
0x180001d95  test    eax, eax
0x180001d97  jnz     short loc_180001DAE
0x180001d99  cmp     ebx, 1
0x180001d9c  jnz     short loc_180001DAE
0x180001d9e  mov     r8, rsi
0x180001da1  xor     edx, edx
0x180001da3  mov     rcx, rbp
0x180001da6  mov     rax, rdi
0x180001da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dae  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001db3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001db7  add     rsp, 28h
0x180001dbb  pop     rdi
0x180001dbc  pop     rsi
0x180001dbd  pop     rbp
0x180001dbe  pop     rbx
0x180001dbf  jmp     _o__seh_filter_dll_0
```
