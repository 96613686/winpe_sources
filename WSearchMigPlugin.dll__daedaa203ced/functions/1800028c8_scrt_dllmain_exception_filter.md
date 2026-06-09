# __scrt_dllmain_exception_filter

- ea: `0x1800028c8`
- end: `0x180002910`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002554`

## callees

- `0x1800028c8`
- `0x180003124`
- `0x180003248`
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
0x1800028c8  push    rbx
0x1800028ca  push    rbp
0x1800028cb  push    rsi
0x1800028cc  push    rdi
0x1800028cd  sub     rsp, 28h
0x1800028d1  mov     rdi, r9
0x1800028d4  mov     rsi, r8
0x1800028d7  mov     ebx, edx
0x1800028d9  mov     rbp, rcx
0x1800028dc  call    __scrt_is_ucrt_dll_in_use
0x1800028e1  test    eax, eax
0x1800028e3  jnz     short loc_1800028FA
0x1800028e5  cmp     ebx, 1
0x1800028e8  jnz     short loc_1800028FA
0x1800028ea  mov     r8, rsi
0x1800028ed  xor     edx, edx
0x1800028ef  mov     rcx, rbp
0x1800028f2  mov     rax, rdi
0x1800028f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fa  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800028ff  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002903  add     rsp, 28h
0x180002907  pop     rdi
0x180002908  pop     rsi
0x180002909  pop     rbp
0x18000290a  pop     rbx
0x18000290b  jmp     _o__seh_filter_dll_0
```
