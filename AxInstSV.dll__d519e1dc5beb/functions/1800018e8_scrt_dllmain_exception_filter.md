# __scrt_dllmain_exception_filter

- ea: `0x1800018e8`
- end: `0x180001930`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001584`

## callees

- `0x1800018e8`
- `0x18000207c`
- `0x180002188`
- `0x180015010`

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
0x1800018e8  push    rbx
0x1800018ea  push    rbp
0x1800018eb  push    rsi
0x1800018ec  push    rdi
0x1800018ed  sub     rsp, 28h
0x1800018f1  mov     rdi, r9
0x1800018f4  mov     rsi, r8
0x1800018f7  mov     ebx, edx
0x1800018f9  mov     rbp, rcx
0x1800018fc  call    __scrt_is_ucrt_dll_in_use
0x180001901  test    eax, eax
0x180001903  jnz     short loc_18000191A
0x180001905  cmp     ebx, 1
0x180001908  jnz     short loc_18000191A
0x18000190a  mov     r8, rsi
0x18000190d  xor     edx, edx
0x18000190f  mov     rcx, rbp
0x180001912  mov     rax, rdi
0x180001915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000191a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000191f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001923  add     rsp, 28h
0x180001927  pop     rdi
0x180001928  pop     rsi
0x180001929  pop     rbp
0x18000192a  pop     rbx
0x18000192b  jmp     _o__seh_filter_dll_0
```
