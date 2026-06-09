# __scrt_dllmain_exception_filter

- ea: `0x180003e84`
- end: `0x180003ecc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003af4`

## callees

- `0x180003e84`
- `0x1800044b8`
- `0x18000458a`
- `0x18000c010`

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
0x180003e84  push    rbx
0x180003e86  push    rbp
0x180003e87  push    rsi
0x180003e88  push    rdi
0x180003e89  sub     rsp, 28h
0x180003e8d  mov     rdi, r9
0x180003e90  mov     rsi, r8
0x180003e93  mov     ebx, edx
0x180003e95  mov     rbp, rcx
0x180003e98  call    __scrt_is_ucrt_dll_in_use
0x180003e9d  test    eax, eax
0x180003e9f  jnz     short loc_180003EB6
0x180003ea1  cmp     ebx, 1
0x180003ea4  jnz     short loc_180003EB6
0x180003ea6  mov     r8, rsi
0x180003ea9  xor     edx, edx
0x180003eab  mov     rcx, rbp
0x180003eae  mov     rax, rdi
0x180003eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180003ebb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180003ebf  add     rsp, 28h
0x180003ec3  pop     rdi
0x180003ec4  pop     rsi
0x180003ec5  pop     rbp
0x180003ec6  pop     rbx
0x180003ec7  jmp     _o__seh_filter_dll_0
```
