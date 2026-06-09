# __scrt_dllmain_exception_filter

- ea: `0x180009a54`
- end: `0x180009a9c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800096c4`

## callees

- `0x180009a54`
- `0x18000a088`
- `0x18000a15e`
- `0x180012010`

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
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180009a54  push    rbx
0x180009a56  push    rbp
0x180009a57  push    rsi
0x180009a58  push    rdi
0x180009a59  sub     rsp, 28h
0x180009a5d  mov     rdi, r9
0x180009a60  mov     rsi, r8
0x180009a63  mov     ebx, edx
0x180009a65  mov     rbp, rcx
0x180009a68  call    __scrt_is_ucrt_dll_in_use
0x180009a6d  test    eax, eax
0x180009a6f  jnz     short loc_180009A86
0x180009a71  cmp     ebx, 1
0x180009a74  jnz     short loc_180009A86
0x180009a76  mov     r8, rsi
0x180009a79  xor     edx, edx
0x180009a7b  mov     rcx, rbp
0x180009a7e  mov     rax, rdi
0x180009a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a86  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180009a8b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180009a8f  add     rsp, 28h
0x180009a93  pop     rdi
0x180009a94  pop     rsi
0x180009a95  pop     rbp
0x180009a96  pop     rbx
0x180009a97  jmp     _o__seh_filter_dll_0
```
