# __scrt_dllmain_exception_filter

- ea: `0x180021c40`
- end: `0x180021c88`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800218a4`

## callees

- `0x180021c40`
- `0x18002225c`
- `0x180022318`
- `0x180033010`

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
0x180021c40  push    rbx
0x180021c42  push    rbp
0x180021c43  push    rsi
0x180021c44  push    rdi
0x180021c45  sub     rsp, 28h
0x180021c49  mov     rdi, r9
0x180021c4c  mov     rsi, r8
0x180021c4f  mov     ebx, edx
0x180021c51  mov     rbp, rcx
0x180021c54  call    __scrt_is_ucrt_dll_in_use
0x180021c59  test    eax, eax
0x180021c5b  jnz     short loc_180021C72
0x180021c5d  cmp     ebx, 1
0x180021c60  jnz     short loc_180021C72
0x180021c62  mov     r8, rsi
0x180021c65  xor     edx, edx
0x180021c67  mov     rcx, rbp
0x180021c6a  mov     rax, rdi
0x180021c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c72  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180021c77  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180021c7b  add     rsp, 28h
0x180021c7f  pop     rdi
0x180021c80  pop     rsi
0x180021c81  pop     rbp
0x180021c82  pop     rbx
0x180021c83  jmp     _o__seh_filter_dll_0
```
