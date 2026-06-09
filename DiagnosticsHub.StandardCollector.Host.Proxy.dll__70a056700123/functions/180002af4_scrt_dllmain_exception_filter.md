# __scrt_dllmain_exception_filter

- ea: `0x180002af4`
- end: `0x180002b54`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000268c`

## callees

- `0x180002af4`
- `0x1800035c4`
- `0x1800036b8`
- `0x180060110`

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
  return seh_filter_dll(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180002af4  mov     [rsp+arg_0], rbx
0x180002af9  mov     [rsp+arg_8], rbp
0x180002afe  mov     [rsp+arg_10], rsi
0x180002b03  push    rdi
0x180002b04  sub     rsp, 20h
0x180002b08  mov     rdi, r9
0x180002b0b  mov     rsi, r8
0x180002b0e  mov     ebx, edx
0x180002b10  mov     rbp, rcx
0x180002b13  call    __scrt_is_ucrt_dll_in_use
0x180002b18  test    eax, eax
0x180002b1a  jnz     short loc_180002B32
0x180002b1c  cmp     ebx, 1
0x180002b1f  jnz     short loc_180002B32
0x180002b21  mov     r8, rsi
0x180002b24  xor     edx, edx
0x180002b26  mov     rcx, rbp
0x180002b29  mov     rax, rdi
0x180002b2c  call    cs:__guard_dispatch_icall_fptr
0x180002b32  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x180002b37  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180002b3b  mov     rbx, [rsp+28h+arg_0]
0x180002b40  mov     rbp, [rsp+28h+arg_8]
0x180002b45  mov     rsi, [rsp+28h+arg_10]
0x180002b4a  add     rsp, 20h
0x180002b4e  pop     rdi
0x180002b4f  jmp     _seh_filter_dll
```
