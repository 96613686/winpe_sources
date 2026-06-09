# __scrt_dllmain_exception_filter

- ea: `0x180001fec`
- end: `0x180002034`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001c94`

## callees

- `0x180001fec`
- `0x18000277c`
- `0x180002a68`
- `0x180011010`

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
0x180001fec  push    rbx
0x180001fee  push    rbp
0x180001fef  push    rsi
0x180001ff0  push    rdi
0x180001ff1  sub     rsp, 28h
0x180001ff5  mov     rdi, r9
0x180001ff8  mov     rsi, r8
0x180001ffb  mov     ebx, edx
0x180001ffd  mov     rbp, rcx
0x180002000  call    __scrt_is_ucrt_dll_in_use
0x180002005  test    eax, eax
0x180002007  jnz     short loc_18000201E
0x180002009  cmp     ebx, 1
0x18000200c  jnz     short loc_18000201E
0x18000200e  mov     r8, rsi
0x180002011  xor     edx, edx
0x180002013  mov     rcx, rbp
0x180002016  mov     rax, rdi
0x180002019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000201e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002023  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002027  add     rsp, 28h
0x18000202b  pop     rdi
0x18000202c  pop     rsi
0x18000202d  pop     rbp
0x18000202e  pop     rbx
0x18000202f  jmp     _o__seh_filter_dll_0
```
