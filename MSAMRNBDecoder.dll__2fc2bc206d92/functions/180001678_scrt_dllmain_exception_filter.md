# __scrt_dllmain_exception_filter

- ea: `0x180001678`
- end: `0x1800016c0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001678`
- `0x180001e4c`
- `0x180001f2a`
- `0x180014010`

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
0x180001678  push    rbx
0x18000167a  push    rbp
0x18000167b  push    rsi
0x18000167c  push    rdi
0x18000167d  sub     rsp, 28h
0x180001681  mov     rdi, r9
0x180001684  mov     rsi, r8
0x180001687  mov     ebx, edx
0x180001689  mov     rbp, rcx
0x18000168c  call    __scrt_is_ucrt_dll_in_use
0x180001691  test    eax, eax
0x180001693  jnz     short loc_1800016AA
0x180001695  cmp     ebx, 1
0x180001698  jnz     short loc_1800016AA
0x18000169a  mov     r8, rsi
0x18000169d  xor     edx, edx
0x18000169f  mov     rcx, rbp
0x1800016a2  mov     rax, rdi
0x1800016a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016aa  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016af  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016b3  add     rsp, 28h
0x1800016b7  pop     rdi
0x1800016b8  pop     rsi
0x1800016b9  pop     rbp
0x1800016ba  pop     rbx
0x1800016bb  jmp     _o__seh_filter_dll_0
```
