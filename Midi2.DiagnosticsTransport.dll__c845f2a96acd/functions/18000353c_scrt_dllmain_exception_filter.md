# __scrt_dllmain_exception_filter

- ea: `0x18000353c`
- end: `0x180003584`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003234`

## callees

- `0x18000353c`
- `0x180004018`
- `0x180004128`
- `0x180013010`

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
0x18000353c  push    rbx
0x18000353e  push    rbp
0x18000353f  push    rsi
0x180003540  push    rdi
0x180003541  sub     rsp, 28h
0x180003545  mov     rdi, r9
0x180003548  mov     rsi, r8
0x18000354b  mov     ebx, edx
0x18000354d  mov     rbp, rcx
0x180003550  call    __scrt_is_ucrt_dll_in_use
0x180003555  test    eax, eax
0x180003557  jnz     short loc_18000356E
0x180003559  cmp     ebx, 1
0x18000355c  jnz     short loc_18000356E
0x18000355e  mov     r8, rsi
0x180003561  xor     edx, edx
0x180003563  mov     rcx, rbp
0x180003566  mov     rax, rdi
0x180003569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180003573  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180003577  add     rsp, 28h
0x18000357b  pop     rdi
0x18000357c  pop     rsi
0x18000357d  pop     rbp
0x18000357e  pop     rbx
0x18000357f  jmp     _o__seh_filter_dll_0
```
