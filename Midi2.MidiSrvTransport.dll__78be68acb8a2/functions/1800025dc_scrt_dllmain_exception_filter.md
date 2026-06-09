# __scrt_dllmain_exception_filter

- ea: `0x1800025dc`
- end: `0x180002624`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800022d4`

## callees

- `0x1800025dc`
- `0x180002ec0`
- `0x180002fc8`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x1800025dc  push    rbx
0x1800025de  push    rbp
0x1800025df  push    rsi
0x1800025e0  push    rdi
0x1800025e1  sub     rsp, 28h
0x1800025e5  mov     rdi, r9
0x1800025e8  mov     rsi, r8
0x1800025eb  mov     ebx, edx
0x1800025ed  mov     rbp, rcx
0x1800025f0  call    __scrt_is_ucrt_dll_in_use
0x1800025f5  test    eax, eax
0x1800025f7  jnz     short loc_18000260E
0x1800025f9  cmp     ebx, 1
0x1800025fc  jnz     short loc_18000260E
0x1800025fe  mov     r8, rsi
0x180002601  xor     edx, edx
0x180002603  mov     rcx, rbp
0x180002606  mov     rax, rdi
0x180002609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000260e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002613  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002617  add     rsp, 28h
0x18000261b  pop     rdi
0x18000261c  pop     rsi
0x18000261d  pop     rbp
0x18000261e  pop     rbx
0x18000261f  jmp     _o__seh_filter_dll_0
```
