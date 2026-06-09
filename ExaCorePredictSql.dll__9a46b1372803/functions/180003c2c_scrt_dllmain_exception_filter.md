# __scrt_dllmain_exception_filter

- ea: `0x180003c2c`
- end: `0x180003c8d`
- name: `__scrt_dllmain_exception_filter`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004180`

## callees

- `0x180003c2c`
- `0x180004498`
- `0x180004670`
- `0x180004978`

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
  return seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180003c2c  mov     [rsp+arg_0], rbx
0x180003c31  mov     [rsp+arg_8], rbp
0x180003c36  mov     [rsp+arg_10], rsi
0x180003c3b  push    rdi
0x180003c3c  sub     rsp, 20h
0x180003c40  mov     rdi, r9
0x180003c43  mov     rsi, r8
0x180003c46  mov     ebx, edx
0x180003c48  mov     rbp, rcx
0x180003c4b  call    __scrt_is_ucrt_dll_in_use
0x180003c50  test    eax, eax
0x180003c52  jnz     short loc_180003C6B
0x180003c54  cmp     ebx, 1
0x180003c57  jnz     short loc_180003C6B
0x180003c59  mov     rcx, rdi; Target
0x180003c5c  call    _guard_check_icall
0x180003c61  mov     r8, rsi
0x180003c64  xor     edx, edx
0x180003c66  mov     rcx, rbp
0x180003c69  call    rdi
0x180003c6b  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180003c70  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180003c74  mov     rbx, [rsp+28h+arg_0]
0x180003c79  mov     rbp, [rsp+28h+arg_8]
0x180003c7e  mov     rsi, [rsp+28h+arg_10]
0x180003c83  add     rsp, 20h
0x180003c87  pop     rdi
0x180003c88  jmp     _seh_filter_dll_0
```
