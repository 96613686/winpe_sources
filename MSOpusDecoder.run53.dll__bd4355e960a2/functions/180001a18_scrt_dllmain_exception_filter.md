# __scrt_dllmain_exception_filter

- ea: `0x180001a18`
- end: `0x180001a60`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001764`

## callees

- `0x180001a18`
- `0x180002154`
- `0x180002228`
- `0x180024010`

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
0x180001a18  push    rbx
0x180001a1a  push    rbp
0x180001a1b  push    rsi
0x180001a1c  push    rdi
0x180001a1d  sub     rsp, 28h
0x180001a21  mov     rdi, r9
0x180001a24  mov     rsi, r8
0x180001a27  mov     ebx, edx
0x180001a29  mov     rbp, rcx
0x180001a2c  call    __scrt_is_ucrt_dll_in_use
0x180001a31  test    eax, eax
0x180001a33  jnz     short loc_180001A4A
0x180001a35  cmp     ebx, 1
0x180001a38  jnz     short loc_180001A4A
0x180001a3a  mov     r8, rsi
0x180001a3d  xor     edx, edx
0x180001a3f  mov     rcx, rbp
0x180001a42  mov     rax, rdi
0x180001a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a4a  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001a4f  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001a53  add     rsp, 28h
0x180001a57  pop     rdi
0x180001a58  pop     rsi
0x180001a59  pop     rbp
0x180001a5a  pop     rbx
0x180001a5b  jmp     _o__seh_filter_dll_0
```
