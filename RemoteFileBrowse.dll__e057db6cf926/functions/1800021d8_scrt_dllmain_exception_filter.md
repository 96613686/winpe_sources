# __scrt_dllmain_exception_filter

- ea: `0x1800021d8`
- end: `0x180002220`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001ea4`

## callees

- `0x1800021d8`
- `0x180002c7c`
- `0x180002d88`
- `0x180019010`

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
0x1800021d8  push    rbx
0x1800021da  push    rbp
0x1800021db  push    rsi
0x1800021dc  push    rdi
0x1800021dd  sub     rsp, 28h
0x1800021e1  mov     rdi, r9
0x1800021e4  mov     rsi, r8
0x1800021e7  mov     ebx, edx
0x1800021e9  mov     rbp, rcx
0x1800021ec  call    __scrt_is_ucrt_dll_in_use
0x1800021f1  test    eax, eax
0x1800021f3  jnz     short loc_18000220A
0x1800021f5  cmp     ebx, 1
0x1800021f8  jnz     short loc_18000220A
0x1800021fa  mov     r8, rsi
0x1800021fd  xor     edx, edx
0x1800021ff  mov     rcx, rbp
0x180002202  mov     rax, rdi
0x180002205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000220f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002213  add     rsp, 28h
0x180002217  pop     rdi
0x180002218  pop     rsi
0x180002219  pop     rbp
0x18000221a  pop     rbx
0x18000221b  jmp     _o__seh_filter_dll_0
```
