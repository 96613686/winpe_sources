# __scrt_dllmain_exception_filter

- ea: `0x180001870`
- end: `0x1800018b8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001594`

## callees

- `0x180001870`
- `0x180002190`
- `0x18000229a`
- `0x180004010`

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
0x180001870  push    rbx
0x180001872  push    rbp
0x180001873  push    rsi
0x180001874  push    rdi
0x180001875  sub     rsp, 28h
0x180001879  mov     rdi, r9
0x18000187c  mov     rsi, r8
0x18000187f  mov     ebx, edx
0x180001881  mov     rbp, rcx
0x180001884  call    __scrt_is_ucrt_dll_in_use
0x180001889  test    eax, eax
0x18000188b  jnz     short loc_1800018A2
0x18000188d  cmp     ebx, 1
0x180001890  jnz     short loc_1800018A2
0x180001892  mov     r8, rsi
0x180001895  xor     edx, edx
0x180001897  mov     rcx, rbp
0x18000189a  mov     rax, rdi
0x18000189d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800018a7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800018ab  add     rsp, 28h
0x1800018af  pop     rdi
0x1800018b0  pop     rsi
0x1800018b1  pop     rbp
0x1800018b2  pop     rbx
0x1800018b3  jmp     _o__seh_filter_dll_0
```
