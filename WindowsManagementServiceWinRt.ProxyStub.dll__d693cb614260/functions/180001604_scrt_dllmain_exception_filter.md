# __scrt_dllmain_exception_filter

- ea: `0x180001604`
- end: `0x18000164c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001604`
- `0x180001bd8`
- `0x180001c66`
- `0x180002010`

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
0x180001604  push    rbx
0x180001606  push    rbp
0x180001607  push    rsi
0x180001608  push    rdi
0x180001609  sub     rsp, 28h
0x18000160d  mov     rdi, r9
0x180001610  mov     rsi, r8
0x180001613  mov     ebx, edx
0x180001615  mov     rbp, rcx
0x180001618  call    __scrt_is_ucrt_dll_in_use
0x18000161d  test    eax, eax
0x18000161f  jnz     short loc_180001636
0x180001621  cmp     ebx, 1
0x180001624  jnz     short loc_180001636
0x180001626  mov     r8, rsi
0x180001629  xor     edx, edx
0x18000162b  mov     rcx, rbp
0x18000162e  mov     rax, rdi
0x180001631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001636  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000163b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000163f  add     rsp, 28h
0x180001643  pop     rdi
0x180001644  pop     rsi
0x180001645  pop     rbp
0x180001646  pop     rbx
0x180001647  jmp     _o__seh_filter_dll_0
```
