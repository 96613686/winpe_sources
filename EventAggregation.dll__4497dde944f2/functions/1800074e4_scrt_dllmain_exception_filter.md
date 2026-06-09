# __scrt_dllmain_exception_filter

- ea: `0x1800074e4`
- end: `0x18000752c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007154`

## callees

- `0x1800074e4`
- `0x180007ab8`
- `0x180007b46`
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
0x1800074e4  push    rbx
0x1800074e6  push    rbp
0x1800074e7  push    rsi
0x1800074e8  push    rdi
0x1800074e9  sub     rsp, 28h
0x1800074ed  mov     rdi, r9
0x1800074f0  mov     rsi, r8
0x1800074f3  mov     ebx, edx
0x1800074f5  mov     rbp, rcx
0x1800074f8  call    __scrt_is_ucrt_dll_in_use
0x1800074fd  test    eax, eax
0x1800074ff  jnz     short loc_180007516
0x180007501  cmp     ebx, 1
0x180007504  jnz     short loc_180007516
0x180007506  mov     r8, rsi
0x180007509  xor     edx, edx
0x18000750b  mov     rcx, rbp
0x18000750e  mov     rax, rdi
0x180007511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007516  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000751b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000751f  add     rsp, 28h
0x180007523  pop     rdi
0x180007524  pop     rsi
0x180007525  pop     rbp
0x180007526  pop     rbx
0x180007527  jmp     _o__seh_filter_dll_0
```
