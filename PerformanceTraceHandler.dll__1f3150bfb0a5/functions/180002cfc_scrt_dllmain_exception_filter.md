# __scrt_dllmain_exception_filter

- ea: `0x180002cfc`
- end: `0x180002d44`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002a74`

## callees

- `0x180002cfc`
- `0x180003570`
- `0x1800036c8`
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
0x180002cfc  push    rbx
0x180002cfe  push    rbp
0x180002cff  push    rsi
0x180002d00  push    rdi
0x180002d01  sub     rsp, 28h
0x180002d05  mov     rdi, r9
0x180002d08  mov     rsi, r8
0x180002d0b  mov     ebx, edx
0x180002d0d  mov     rbp, rcx
0x180002d10  call    __scrt_is_ucrt_dll_in_use
0x180002d15  test    eax, eax
0x180002d17  jnz     short loc_180002D2E
0x180002d19  cmp     ebx, 1
0x180002d1c  jnz     short loc_180002D2E
0x180002d1e  mov     r8, rsi
0x180002d21  xor     edx, edx
0x180002d23  mov     rcx, rbp
0x180002d26  mov     rax, rdi
0x180002d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002d33  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002d37  add     rsp, 28h
0x180002d3b  pop     rdi
0x180002d3c  pop     rsi
0x180002d3d  pop     rbp
0x180002d3e  pop     rbx
0x180002d3f  jmp     _o__seh_filter_dll_0
```
