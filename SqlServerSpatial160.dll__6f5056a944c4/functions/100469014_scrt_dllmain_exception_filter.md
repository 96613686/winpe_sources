# __scrt_dllmain_exception_filter

- ea: `0x100469014`
- end: `0x100469074`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x100468db4`

## callees

- `0x100469014`
- `0x1004697f8`
- `0x10046988e`
- `0x100469b20`

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
0x100469014  mov     [rsp+arg_0], rbx
0x100469019  mov     [rsp+arg_8], rbp
0x10046901e  mov     [rsp+arg_10], rsi
0x100469023  push    rdi
0x100469024  sub     rsp, 20h
0x100469028  mov     rdi, r9
0x10046902b  mov     rsi, r8
0x10046902e  mov     ebx, edx
0x100469030  mov     rbp, rcx
0x100469033  call    __scrt_is_ucrt_dll_in_use
0x100469038  test    eax, eax
0x10046903a  jnz     short loc_100469052
0x10046903c  cmp     ebx, 1
0x10046903f  jnz     short loc_100469052
0x100469041  mov     r8, rsi
0x100469044  xor     edx, edx
0x100469046  mov     rcx, rbp
0x100469049  mov     rax, rdi
0x10046904c  call    cs:__guard_dispatch_icall_fptr
0x100469052  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x100469057  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x10046905b  mov     rbx, [rsp+28h+arg_0]
0x100469060  mov     rbp, [rsp+28h+arg_8]
0x100469065  mov     rsi, [rsp+28h+arg_10]
0x10046906a  add     rsp, 20h
0x10046906e  pop     rdi
0x10046906f  jmp     _seh_filter_dll_0
```
