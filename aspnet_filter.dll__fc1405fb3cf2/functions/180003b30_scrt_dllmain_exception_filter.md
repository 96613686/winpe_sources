# __scrt_dllmain_exception_filter

- ea: `0x180003b30`
- end: `0x180003b90`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000347c`

## callees

- `0x180003b30`
- `0x1800042e4`
- `0x180004332`
- `0x1800043b0`

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
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  mov     [rsp+arg_8], rbp
0x180003b3a  mov     [rsp+arg_10], rsi
0x180003b3f  push    rdi
0x180003b40  sub     rsp, 20h
0x180003b44  mov     rdi, r9
0x180003b47  mov     rsi, r8
0x180003b4a  mov     ebx, edx
0x180003b4c  mov     rbp, rcx
0x180003b4f  call    __scrt_is_ucrt_dll_in_use
0x180003b54  test    eax, eax
0x180003b56  jnz     short loc_180003B6E
0x180003b58  cmp     ebx, 1
0x180003b5b  jnz     short loc_180003B6E
0x180003b5d  mov     r8, rsi
0x180003b60  xor     edx, edx
0x180003b62  mov     rcx, rbp
0x180003b65  mov     rax, rdi
0x180003b68  call    cs:__guard_dispatch_icall_fptr
0x180003b6e  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180003b73  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180003b77  mov     rbx, [rsp+28h+arg_0]
0x180003b7c  mov     rbp, [rsp+28h+arg_8]
0x180003b81  mov     rsi, [rsp+28h+arg_10]
0x180003b86  add     rsp, 20h
0x180003b8a  pop     rdi
0x180003b8b  jmp     _seh_filter_dll_0
```
