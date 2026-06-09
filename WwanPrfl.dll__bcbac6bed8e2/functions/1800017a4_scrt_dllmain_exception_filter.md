# __scrt_dllmain_exception_filter

- ea: `0x1800017a4`
- end: `0x1800017ec`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014d4`

## callees

- `0x1800017a4`
- `0x180001f00`
- `0x180001ff8`
- `0x180014010`

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
0x1800017a4  push    rbx
0x1800017a6  push    rbp
0x1800017a7  push    rsi
0x1800017a8  push    rdi
0x1800017a9  sub     rsp, 28h
0x1800017ad  mov     rdi, r9
0x1800017b0  mov     rsi, r8
0x1800017b3  mov     ebx, edx
0x1800017b5  mov     rbp, rcx
0x1800017b8  call    __scrt_is_ucrt_dll_in_use
0x1800017bd  test    eax, eax
0x1800017bf  jnz     short loc_1800017D6
0x1800017c1  cmp     ebx, 1
0x1800017c4  jnz     short loc_1800017D6
0x1800017c6  mov     r8, rsi
0x1800017c9  xor     edx, edx
0x1800017cb  mov     rcx, rbp
0x1800017ce  mov     rax, rdi
0x1800017d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800017db  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800017df  add     rsp, 28h
0x1800017e3  pop     rdi
0x1800017e4  pop     rsi
0x1800017e5  pop     rbp
0x1800017e6  pop     rbx
0x1800017e7  jmp     _o__seh_filter_dll_0
```
