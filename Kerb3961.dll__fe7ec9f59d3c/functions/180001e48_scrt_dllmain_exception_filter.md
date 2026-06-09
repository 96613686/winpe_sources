# __scrt_dllmain_exception_filter

- ea: `0x180001e48`
- end: `0x180001e90`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001bb4`

## callees

- `0x180001e48`
- `0x18000259c`
- `0x1800028f8`
- `0x18001e010`

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
0x180001e48  push    rbx
0x180001e4a  push    rbp
0x180001e4b  push    rsi
0x180001e4c  push    rdi
0x180001e4d  sub     rsp, 28h
0x180001e51  mov     rdi, r9
0x180001e54  mov     rsi, r8
0x180001e57  mov     ebx, edx
0x180001e59  mov     rbp, rcx
0x180001e5c  call    __scrt_is_ucrt_dll_in_use
0x180001e61  test    eax, eax
0x180001e63  jnz     short loc_180001E7A
0x180001e65  cmp     ebx, 1
0x180001e68  jnz     short loc_180001E7A
0x180001e6a  mov     r8, rsi
0x180001e6d  xor     edx, edx
0x180001e6f  mov     rcx, rbp
0x180001e72  mov     rax, rdi
0x180001e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e7a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001e7f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001e83  add     rsp, 28h
0x180001e87  pop     rdi
0x180001e88  pop     rsi
0x180001e89  pop     rbp
0x180001e8a  pop     rbx
0x180001e8b  jmp     _o__seh_filter_dll_0
```
