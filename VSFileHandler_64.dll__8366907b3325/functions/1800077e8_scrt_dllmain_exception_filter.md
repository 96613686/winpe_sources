# __scrt_dllmain_exception_filter

- ea: `0x1800077e8`
- end: `0x180007848`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007578`

## callees

- `0x1800077e8`
- `0x180008344`
- `0x18000d750`
- `0x1800241c0`

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
0x1800077e8  mov     [rsp+arg_0], rbx
0x1800077ed  mov     [rsp+arg_8], rbp
0x1800077f2  mov     [rsp+arg_10], rsi
0x1800077f7  push    rdi
0x1800077f8  sub     rsp, 20h
0x1800077fc  mov     rdi, r9
0x1800077ff  mov     rsi, r8
0x180007802  mov     ebx, edx
0x180007804  mov     rbp, rcx
0x180007807  call    __scrt_is_ucrt_dll_in_use
0x18000780c  test    eax, eax
0x18000780e  jnz     short loc_180007826
0x180007810  cmp     ebx, 1
0x180007813  jnz     short loc_180007826
0x180007815  mov     r8, rsi
0x180007818  xor     edx, edx
0x18000781a  mov     rcx, rbp
0x18000781d  mov     rax, rdi
0x180007820  call    cs:__guard_dispatch_icall_fptr
0x180007826  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000782b  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18000782f  mov     rbx, [rsp+28h+arg_0]
0x180007834  mov     rbp, [rsp+28h+arg_8]
0x180007839  mov     rsi, [rsp+28h+arg_10]
0x18000783e  add     rsp, 20h
0x180007842  pop     rdi
0x180007843  jmp     _seh_filter_dll
```
