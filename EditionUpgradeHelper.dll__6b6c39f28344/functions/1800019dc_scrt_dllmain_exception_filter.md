# __scrt_dllmain_exception_filter

- ea: `0x1800019dc`
- end: `0x180001a24`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001754`

## callees

- `0x1800019dc`
- `0x180002198`
- `0x180002498`
- `0x180027010`

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
0x1800019dc  push    rbx
0x1800019de  push    rbp
0x1800019df  push    rsi
0x1800019e0  push    rdi
0x1800019e1  sub     rsp, 28h
0x1800019e5  mov     rdi, r9
0x1800019e8  mov     rsi, r8
0x1800019eb  mov     ebx, edx
0x1800019ed  mov     rbp, rcx
0x1800019f0  call    __scrt_is_ucrt_dll_in_use
0x1800019f5  test    eax, eax
0x1800019f7  jnz     short loc_180001A0E
0x1800019f9  cmp     ebx, 1
0x1800019fc  jnz     short loc_180001A0E
0x1800019fe  mov     r8, rsi
0x180001a01  xor     edx, edx
0x180001a03  mov     rcx, rbp
0x180001a06  mov     rax, rdi
0x180001a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a0e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001a13  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001a17  add     rsp, 28h
0x180001a1b  pop     rdi
0x180001a1c  pop     rsi
0x180001a1d  pop     rbp
0x180001a1e  pop     rbx
0x180001a1f  jmp     _o__seh_filter_dll_0
```
