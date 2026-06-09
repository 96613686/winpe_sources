# __scrt_dllmain_exception_filter

- ea: `0x180002464`
- end: `0x1800024ac`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002174`

## callees

- `0x180002464`
- `0x180002c94`
- `0x180002d98`
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
0x180002464  push    rbx
0x180002466  push    rbp
0x180002467  push    rsi
0x180002468  push    rdi
0x180002469  sub     rsp, 28h
0x18000246d  mov     rdi, r9
0x180002470  mov     rsi, r8
0x180002473  mov     ebx, edx
0x180002475  mov     rbp, rcx
0x180002478  call    __scrt_is_ucrt_dll_in_use
0x18000247d  test    eax, eax
0x18000247f  jnz     short loc_180002496
0x180002481  cmp     ebx, 1
0x180002484  jnz     short loc_180002496
0x180002486  mov     r8, rsi
0x180002489  xor     edx, edx
0x18000248b  mov     rcx, rbp
0x18000248e  mov     rax, rdi
0x180002491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002496  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000249b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000249f  add     rsp, 28h
0x1800024a3  pop     rdi
0x1800024a4  pop     rsi
0x1800024a5  pop     rbp
0x1800024a6  pop     rbx
0x1800024a7  jmp     _o__seh_filter_dll_0
```
