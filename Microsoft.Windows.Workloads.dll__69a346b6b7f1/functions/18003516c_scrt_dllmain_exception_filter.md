# __scrt_dllmain_exception_filter

- ea: `0x18003516c`
- end: `0x1800351cc`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800356ec`

## callees

- `0x18003516c`
- `0x180035e70`
- `0x18003975d`
- `0x18003bed0`

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
0x18003516c  mov     [rsp+arg_0], rbx
0x180035171  mov     [rsp+arg_8], rbp
0x180035176  mov     [rsp+arg_10], rsi
0x18003517b  push    rdi
0x18003517c  sub     rsp, 20h
0x180035180  mov     rdi, r9
0x180035183  mov     rsi, r8
0x180035186  mov     ebx, edx
0x180035188  mov     rbp, rcx
0x18003518b  call    __scrt_is_ucrt_dll_in_use
0x180035190  test    eax, eax
0x180035192  jnz     short loc_1800351AA
0x180035194  cmp     ebx, 1
0x180035197  jnz     short loc_1800351AA
0x180035199  mov     r8, rsi
0x18003519c  xor     edx, edx
0x18003519e  mov     rcx, rbp
0x1800351a1  mov     rax, rdi
0x1800351a4  call    cs:__guard_dispatch_icall_fptr
0x1800351aa  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x1800351af  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x1800351b3  mov     rbx, [rsp+28h+arg_0]
0x1800351b8  mov     rbp, [rsp+28h+arg_8]
0x1800351bd  mov     rsi, [rsp+28h+arg_10]
0x1800351c2  add     rsp, 20h
0x1800351c6  pop     rdi
0x1800351c7  jmp     _seh_filter_dll_0
```
