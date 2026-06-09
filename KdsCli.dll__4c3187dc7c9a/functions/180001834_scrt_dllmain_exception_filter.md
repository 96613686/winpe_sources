# __scrt_dllmain_exception_filter

- ea: `0x180001834`
- end: `0x18000187c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014a4`

## callees

- `0x180001834`
- `0x180001e68`
- `0x180001f28`
- `0x18001b010`

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
0x180001834  push    rbx
0x180001836  push    rbp
0x180001837  push    rsi
0x180001838  push    rdi
0x180001839  sub     rsp, 28h
0x18000183d  mov     rdi, r9
0x180001840  mov     rsi, r8
0x180001843  mov     ebx, edx
0x180001845  mov     rbp, rcx
0x180001848  call    __scrt_is_ucrt_dll_in_use
0x18000184d  test    eax, eax
0x18000184f  jnz     short loc_180001866
0x180001851  cmp     ebx, 1
0x180001854  jnz     short loc_180001866
0x180001856  mov     r8, rsi
0x180001859  xor     edx, edx
0x18000185b  mov     rcx, rbp
0x18000185e  mov     rax, rdi
0x180001861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001866  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000186b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000186f  add     rsp, 28h
0x180001873  pop     rdi
0x180001874  pop     rsi
0x180001875  pop     rbp
0x180001876  pop     rbx
0x180001877  jmp     _o__seh_filter_dll_0
```
