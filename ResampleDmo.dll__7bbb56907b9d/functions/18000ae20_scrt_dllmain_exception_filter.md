# __scrt_dllmain_exception_filter

- ea: `0x18000ae20`
- end: `0x18000ae68`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000aa04`

## callees

- `0x18000ae20`
- `0x18000b5d0`
- `0x18000b6e8`
- `0x180085010`

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
0x18000ae20  push    rbx
0x18000ae22  push    rbp
0x18000ae23  push    rsi
0x18000ae24  push    rdi
0x18000ae25  sub     rsp, 28h
0x18000ae29  mov     rdi, r9
0x18000ae2c  mov     rsi, r8
0x18000ae2f  mov     ebx, edx
0x18000ae31  mov     rbp, rcx
0x18000ae34  call    __scrt_is_ucrt_dll_in_use
0x18000ae39  test    eax, eax
0x18000ae3b  jnz     short loc_18000AE52
0x18000ae3d  cmp     ebx, 1
0x18000ae40  jnz     short loc_18000AE52
0x18000ae42  mov     r8, rsi
0x18000ae45  xor     edx, edx
0x18000ae47  mov     rcx, rbp
0x18000ae4a  mov     rax, rdi
0x18000ae4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae52  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000ae57  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000ae5b  add     rsp, 28h
0x18000ae5f  pop     rdi
0x18000ae60  pop     rsi
0x18000ae61  pop     rbp
0x18000ae62  pop     rbx
0x18000ae63  jmp     _o__seh_filter_dll_0
```
