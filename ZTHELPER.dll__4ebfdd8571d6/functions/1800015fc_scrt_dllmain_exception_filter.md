# __scrt_dllmain_exception_filter

- ea: `0x1800015fc`
- end: `0x180001644`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001324`

## callees

- `0x1800015fc`
- `0x180001f2c`
- `0x18000203a`
- `0x180018010`

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
0x1800015fc  push    rbx
0x1800015fe  push    rbp
0x1800015ff  push    rsi
0x180001600  push    rdi
0x180001601  sub     rsp, 28h
0x180001605  mov     rdi, r9
0x180001608  mov     rsi, r8
0x18000160b  mov     ebx, edx
0x18000160d  mov     rbp, rcx
0x180001610  call    __scrt_is_ucrt_dll_in_use
0x180001615  test    eax, eax
0x180001617  jnz     short loc_18000162E
0x180001619  cmp     ebx, 1
0x18000161c  jnz     short loc_18000162E
0x18000161e  mov     r8, rsi
0x180001621  xor     edx, edx
0x180001623  mov     rcx, rbp
0x180001626  mov     rax, rdi
0x180001629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001633  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001637  add     rsp, 28h
0x18000163b  pop     rdi
0x18000163c  pop     rsi
0x18000163d  pop     rbp
0x18000163e  pop     rbx
0x18000163f  jmp     _o__seh_filter_dll_0
```
