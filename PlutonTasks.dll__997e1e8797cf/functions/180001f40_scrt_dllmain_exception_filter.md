# __scrt_dllmain_exception_filter

- ea: `0x180001f40`
- end: `0x180001f88`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001c74`

## callees

- `0x180001f40`
- `0x180002720`
- `0x180002828`
- `0x18000a010`

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
0x180001f40  push    rbx
0x180001f42  push    rbp
0x180001f43  push    rsi
0x180001f44  push    rdi
0x180001f45  sub     rsp, 28h
0x180001f49  mov     rdi, r9
0x180001f4c  mov     rsi, r8
0x180001f4f  mov     ebx, edx
0x180001f51  mov     rbp, rcx
0x180001f54  call    __scrt_is_ucrt_dll_in_use
0x180001f59  test    eax, eax
0x180001f5b  jnz     short loc_180001F72
0x180001f5d  cmp     ebx, 1
0x180001f60  jnz     short loc_180001F72
0x180001f62  mov     r8, rsi
0x180001f65  xor     edx, edx
0x180001f67  mov     rcx, rbp
0x180001f6a  mov     rax, rdi
0x180001f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f72  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001f77  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001f7b  add     rsp, 28h
0x180001f7f  pop     rdi
0x180001f80  pop     rsi
0x180001f81  pop     rbp
0x180001f82  pop     rbx
0x180001f83  jmp     _o__seh_filter_dll_0
```
