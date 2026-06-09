# __scrt_dllmain_exception_filter

- ea: `0x18000379c`
- end: `0x1800037e4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003514`

## callees

- `0x18000379c`
- `0x180003f08`
- `0x180004018`
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
0x18000379c  push    rbx
0x18000379e  push    rbp
0x18000379f  push    rsi
0x1800037a0  push    rdi
0x1800037a1  sub     rsp, 28h
0x1800037a5  mov     rdi, r9
0x1800037a8  mov     rsi, r8
0x1800037ab  mov     ebx, edx
0x1800037ad  mov     rbp, rcx
0x1800037b0  call    __scrt_is_ucrt_dll_in_use
0x1800037b5  test    eax, eax
0x1800037b7  jnz     short loc_1800037CE
0x1800037b9  cmp     ebx, 1
0x1800037bc  jnz     short loc_1800037CE
0x1800037be  mov     r8, rsi
0x1800037c1  xor     edx, edx
0x1800037c3  mov     rcx, rbp
0x1800037c6  mov     rax, rdi
0x1800037c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037ce  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800037d3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800037d7  add     rsp, 28h
0x1800037db  pop     rdi
0x1800037dc  pop     rsi
0x1800037dd  pop     rbp
0x1800037de  pop     rbx
0x1800037df  jmp     _o__seh_filter_dll_0
```
