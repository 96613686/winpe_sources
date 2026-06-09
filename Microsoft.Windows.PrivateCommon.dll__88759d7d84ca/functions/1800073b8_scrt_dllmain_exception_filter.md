# __scrt_dllmain_exception_filter

- ea: `0x1800073b8`
- end: `0x180007418`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000788c`

## callees

- `0x1800073b8`
- `0x180007ec8`
- `0x18000b5c2`
- `0x18000b930`

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
0x1800073b8  mov     [rsp+arg_0], rbx
0x1800073bd  mov     [rsp+arg_8], rbp
0x1800073c2  mov     [rsp+arg_10], rsi
0x1800073c7  push    rdi
0x1800073c8  sub     rsp, 20h
0x1800073cc  mov     rdi, r9
0x1800073cf  mov     rsi, r8
0x1800073d2  mov     ebx, edx
0x1800073d4  mov     rbp, rcx
0x1800073d7  call    __scrt_is_ucrt_dll_in_use
0x1800073dc  test    eax, eax
0x1800073de  jnz     short loc_1800073F6
0x1800073e0  cmp     ebx, 1
0x1800073e3  jnz     short loc_1800073F6
0x1800073e5  mov     r8, rsi
0x1800073e8  xor     edx, edx
0x1800073ea  mov     rcx, rbp
0x1800073ed  mov     rax, rdi
0x1800073f0  call    cs:__guard_dispatch_icall_fptr
0x1800073f6  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x1800073fb  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x1800073ff  mov     rbx, [rsp+28h+arg_0]
0x180007404  mov     rbp, [rsp+28h+arg_8]
0x180007409  mov     rsi, [rsp+28h+arg_10]
0x18000740e  add     rsp, 20h
0x180007412  pop     rdi
0x180007413  jmp     _seh_filter_dll_0
```
