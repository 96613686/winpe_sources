# __scrt_dllmain_exception_filter

- ea: `0x18000d180`
- end: `0x18000d1e0`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000d91c`

## callees

- `0x18000d180`
- `0x18000dc34`
- `0x18000e0f6`
- `0x18000e4a0`

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
0x18000d180  mov     [rsp+arg_0], rbx
0x18000d185  mov     [rsp+arg_8], rbp
0x18000d18a  mov     [rsp+arg_10], rsi
0x18000d18f  push    rdi
0x18000d190  sub     rsp, 20h
0x18000d194  mov     rdi, r9
0x18000d197  mov     rsi, r8
0x18000d19a  mov     ebx, edx
0x18000d19c  mov     rbp, rcx
0x18000d19f  call    __scrt_is_ucrt_dll_in_use
0x18000d1a4  test    eax, eax
0x18000d1a6  jnz     short loc_18000D1BE
0x18000d1a8  cmp     ebx, 1
0x18000d1ab  jnz     short loc_18000D1BE
0x18000d1ad  mov     r8, rsi
0x18000d1b0  xor     edx, edx
0x18000d1b2  mov     rcx, rbp
0x18000d1b5  mov     rax, rdi
0x18000d1b8  call    cs:__guard_dispatch_icall_fptr
0x18000d1be  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000d1c3  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18000d1c7  mov     rbx, [rsp+28h+arg_0]
0x18000d1cc  mov     rbp, [rsp+28h+arg_8]
0x18000d1d1  mov     rsi, [rsp+28h+arg_10]
0x18000d1d6  add     rsp, 20h
0x18000d1da  pop     rdi
0x18000d1db  jmp     _seh_filter_dll_0
```
