# __scrt_dllmain_exception_filter

- ea: `0x18000eec4`
- end: `0x18000ef23`
- name: `__scrt_dllmain_exception_filter`
- size: `95`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f3dc`

## callees

- `0x18000ece8`
- `0x18000eec4`
- `0x18000f9e0`
- `0x180015430`

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
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000eec4  mov     [rsp+arg_0], rbx
0x18000eec9  mov     [rsp+arg_8], rbp
0x18000eece  mov     [rsp+arg_10], rsi
0x18000eed3  push    rdi
0x18000eed4  sub     rsp, 20h
0x18000eed8  mov     rdi, r9
0x18000eedb  mov     rsi, r8
0x18000eede  mov     ebx, edx
0x18000eee0  mov     rbp, rcx
0x18000eee3  call    __scrt_is_ucrt_dll_in_use
0x18000eee8  test    eax, eax
0x18000eeea  jnz     short loc_18000EF01
0x18000eeec  cmp     ebx, 1
0x18000eeef  jnz     short loc_18000EF01
0x18000eef1  mov     r8, rsi
0x18000eef4  xor     edx, edx
0x18000eef6  mov     rcx, rbp
0x18000eef9  mov     rax, rdi
0x18000eefc  call    _guard_dispatch_icall
0x18000ef01  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000ef06  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x18000ef0a  mov     rbx, [rsp+28h+arg_0]
0x18000ef0f  mov     rbp, [rsp+28h+arg_8]
0x18000ef14  mov     rsi, [rsp+28h+arg_10]
0x18000ef19  add     rsp, 20h
0x18000ef1d  pop     rdi
0x18000ef1e  jmp     _o__seh_filter_dll_0
```
