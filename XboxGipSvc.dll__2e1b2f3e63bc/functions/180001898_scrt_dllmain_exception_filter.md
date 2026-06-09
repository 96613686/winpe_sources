# __scrt_dllmain_exception_filter

- ea: `0x180001898`
- end: `0x1800018e0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001534`

## callees

- `0x180001898`
- `0x180001fe8`
- `0x1800020f8`
- `0x180012010`

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
0x180001898  push    rbx
0x18000189a  push    rbp
0x18000189b  push    rsi
0x18000189c  push    rdi
0x18000189d  sub     rsp, 28h
0x1800018a1  mov     rdi, r9
0x1800018a4  mov     rsi, r8
0x1800018a7  mov     ebx, edx
0x1800018a9  mov     rbp, rcx
0x1800018ac  call    __scrt_is_ucrt_dll_in_use
0x1800018b1  test    eax, eax
0x1800018b3  jnz     short loc_1800018CA
0x1800018b5  cmp     ebx, 1
0x1800018b8  jnz     short loc_1800018CA
0x1800018ba  mov     r8, rsi
0x1800018bd  xor     edx, edx
0x1800018bf  mov     rcx, rbp
0x1800018c2  mov     rax, rdi
0x1800018c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018ca  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800018cf  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800018d3  add     rsp, 28h
0x1800018d7  pop     rdi
0x1800018d8  pop     rsi
0x1800018d9  pop     rbp
0x1800018da  pop     rbx
0x1800018db  jmp     _o__seh_filter_dll_0
```
