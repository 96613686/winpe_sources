# __scrt_dllmain_exception_filter

- ea: `0x180001c84`
- end: `0x180001ccc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800018f4`

## callees

- `0x180001c84`
- `0x18000224c`
- `0x1800022d6`
- `0x18001c010`

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
0x180001c84  push    rbx
0x180001c86  push    rbp
0x180001c87  push    rsi
0x180001c88  push    rdi
0x180001c89  sub     rsp, 28h
0x180001c8d  mov     rdi, r9
0x180001c90  mov     rsi, r8
0x180001c93  mov     ebx, edx
0x180001c95  mov     rbp, rcx
0x180001c98  call    __scrt_is_ucrt_dll_in_use
0x180001c9d  test    eax, eax
0x180001c9f  jnz     short loc_180001CB6
0x180001ca1  cmp     ebx, 1
0x180001ca4  jnz     short loc_180001CB6
0x180001ca6  mov     r8, rsi
0x180001ca9  xor     edx, edx
0x180001cab  mov     rcx, rbp
0x180001cae  mov     rax, rdi
0x180001cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cb6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001cbb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001cbf  add     rsp, 28h
0x180001cc3  pop     rdi
0x180001cc4  pop     rsi
0x180001cc5  pop     rbp
0x180001cc6  pop     rbx
0x180001cc7  jmp     _o__seh_filter_dll_0
```
