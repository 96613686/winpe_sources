# __scrt_dllmain_exception_filter

- ea: `0x180002b2c`
- end: `0x180002b8b`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000287c`

## callees

- `0x180002b2c`
- `0x180003330`
- `0x180005c5b`
- `0x1800b4010`

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
0x180002b2c  mov     [rsp+arg_0], rbx
0x180002b31  mov     [rsp+arg_8], rbp
0x180002b36  mov     [rsp+arg_10], rsi
0x180002b3b  push    rdi
0x180002b3c  sub     rsp, 20h
0x180002b40  mov     rdi, r9
0x180002b43  mov     rsi, r8
0x180002b46  mov     ebx, edx
0x180002b48  mov     rbp, rcx
0x180002b4b  call    __scrt_is_ucrt_dll_in_use
0x180002b50  test    eax, eax
0x180002b52  jnz     short loc_180002B69
0x180002b54  cmp     ebx, 1
0x180002b57  jnz     short loc_180002B69
0x180002b59  mov     r8, rsi
0x180002b5c  xor     edx, edx
0x180002b5e  mov     rcx, rbp
0x180002b61  mov     rax, rdi
0x180002b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b69  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180002b6e  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180002b72  mov     rbx, [rsp+28h+arg_0]
0x180002b77  mov     rbp, [rsp+28h+arg_8]
0x180002b7c  mov     rsi, [rsp+28h+arg_10]
0x180002b81  add     rsp, 20h
0x180002b85  pop     rdi
0x180002b86  jmp     _seh_filter_dll_0
```
