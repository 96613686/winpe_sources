# __scrt_dllmain_exception_filter

- ea: `0x18000170c`
- end: `0x180001754`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001484`

## callees

- `0x18000170c`
- `0x180001ea8`
- `0x180002048`
- `0x18000b010`

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
0x18000170c  push    rbx
0x18000170e  push    rbp
0x18000170f  push    rsi
0x180001710  push    rdi
0x180001711  sub     rsp, 28h
0x180001715  mov     rdi, r9
0x180001718  mov     rsi, r8
0x18000171b  mov     ebx, edx
0x18000171d  mov     rbp, rcx
0x180001720  call    __scrt_is_ucrt_dll_in_use
0x180001725  test    eax, eax
0x180001727  jnz     short loc_18000173E
0x180001729  cmp     ebx, 1
0x18000172c  jnz     short loc_18000173E
0x18000172e  mov     r8, rsi
0x180001731  xor     edx, edx
0x180001733  mov     rcx, rbp
0x180001736  mov     rax, rdi
0x180001739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000173e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001743  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001747  add     rsp, 28h
0x18000174b  pop     rdi
0x18000174c  pop     rsi
0x18000174d  pop     rbp
0x18000174e  pop     rbx
0x18000174f  jmp     _o__seh_filter_dll_0
```
