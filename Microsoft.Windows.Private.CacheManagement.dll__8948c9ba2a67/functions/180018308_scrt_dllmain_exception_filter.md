# __scrt_dllmain_exception_filter

- ea: `0x180018308`
- end: `0x180018368`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800187bc`

## callees

- `0x180018308`
- `0x180018ee8`
- `0x18001c597`
- `0x18001cdf0`

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
  return seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180018308  mov     [rsp+arg_0], rbx
0x18001830d  mov     [rsp+arg_8], rbp
0x180018312  mov     [rsp+arg_10], rsi
0x180018317  push    rdi
0x180018318  sub     rsp, 20h
0x18001831c  mov     rdi, r9
0x18001831f  mov     rsi, r8
0x180018322  mov     ebx, edx
0x180018324  mov     rbp, rcx
0x180018327  call    __scrt_is_ucrt_dll_in_use
0x18001832c  test    eax, eax
0x18001832e  jnz     short loc_180018346
0x180018330  cmp     ebx, 1
0x180018333  jnz     short loc_180018346
0x180018335  mov     r8, rsi
0x180018338  xor     edx, edx
0x18001833a  mov     rcx, rbp
0x18001833d  mov     rax, rdi
0x180018340  call    cs:__guard_dispatch_icall_fptr
0x180018346  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18001834b  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18001834f  mov     rbx, [rsp+28h+arg_0]
0x180018354  mov     rbp, [rsp+28h+arg_8]
0x180018359  mov     rsi, [rsp+28h+arg_10]
0x18001835e  add     rsp, 20h
0x180018362  pop     rdi
0x180018363  jmp     _seh_filter_dll_0
```
