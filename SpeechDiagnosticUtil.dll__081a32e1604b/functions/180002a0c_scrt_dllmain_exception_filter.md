# __scrt_dllmain_exception_filter

- ea: `0x180002a0c`
- end: `0x180002a54`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002784`

## callees

- `0x180002a0c`
- `0x180003148`
- `0x180003248`
- `0x180011010`

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
0x180002a0c  push    rbx
0x180002a0e  push    rbp
0x180002a0f  push    rsi
0x180002a10  push    rdi
0x180002a11  sub     rsp, 28h
0x180002a15  mov     rdi, r9
0x180002a18  mov     rsi, r8
0x180002a1b  mov     ebx, edx
0x180002a1d  mov     rbp, rcx
0x180002a20  call    __scrt_is_ucrt_dll_in_use
0x180002a25  test    eax, eax
0x180002a27  jnz     short loc_180002A3E
0x180002a29  cmp     ebx, 1
0x180002a2c  jnz     short loc_180002A3E
0x180002a2e  mov     r8, rsi
0x180002a31  xor     edx, edx
0x180002a33  mov     rcx, rbp
0x180002a36  mov     rax, rdi
0x180002a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a3e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002a43  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002a47  add     rsp, 28h
0x180002a4b  pop     rdi
0x180002a4c  pop     rsi
0x180002a4d  pop     rbp
0x180002a4e  pop     rbx
0x180002a4f  jmp     _o__seh_filter_dll_0
```
