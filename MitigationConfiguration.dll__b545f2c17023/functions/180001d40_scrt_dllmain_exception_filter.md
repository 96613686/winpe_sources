# __scrt_dllmain_exception_filter

- ea: `0x180001d40`
- end: `0x180001d88`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001a74`

## callees

- `0x180001d40`
- `0x1800024f4`
- `0x180002618`
- `0x180015010`

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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001d40  push    rbx
0x180001d42  push    rbp
0x180001d43  push    rsi
0x180001d44  push    rdi
0x180001d45  sub     rsp, 28h
0x180001d49  mov     rdi, r9
0x180001d4c  mov     rsi, r8
0x180001d4f  mov     ebx, edx
0x180001d51  mov     rbp, rcx
0x180001d54  call    __scrt_is_ucrt_dll_in_use
0x180001d59  test    eax, eax
0x180001d5b  jnz     short loc_180001D72
0x180001d5d  cmp     ebx, 1
0x180001d60  jnz     short loc_180001D72
0x180001d62  mov     r8, rsi
0x180001d65  xor     edx, edx
0x180001d67  mov     rcx, rbp
0x180001d6a  mov     rax, rdi
0x180001d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d72  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001d77  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001d7b  add     rsp, 28h
0x180001d7f  pop     rdi
0x180001d80  pop     rsi
0x180001d81  pop     rbp
0x180001d82  pop     rbx
0x180001d83  jmp     _o__seh_filter_dll_0
```
