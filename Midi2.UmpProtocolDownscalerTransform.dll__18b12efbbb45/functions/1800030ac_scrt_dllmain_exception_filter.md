# __scrt_dllmain_exception_filter

- ea: `0x1800030ac`
- end: `0x1800030f4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002cd4`

## callees

- `0x1800030ac`
- `0x1800038d0`
- `0x1800039d8`
- `0x180013010`

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
0x1800030ac  push    rbx
0x1800030ae  push    rbp
0x1800030af  push    rsi
0x1800030b0  push    rdi
0x1800030b1  sub     rsp, 28h
0x1800030b5  mov     rdi, r9
0x1800030b8  mov     rsi, r8
0x1800030bb  mov     ebx, edx
0x1800030bd  mov     rbp, rcx
0x1800030c0  call    __scrt_is_ucrt_dll_in_use
0x1800030c5  test    eax, eax
0x1800030c7  jnz     short loc_1800030DE
0x1800030c9  cmp     ebx, 1
0x1800030cc  jnz     short loc_1800030DE
0x1800030ce  mov     r8, rsi
0x1800030d1  xor     edx, edx
0x1800030d3  mov     rcx, rbp
0x1800030d6  mov     rax, rdi
0x1800030d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030de  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800030e3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800030e7  add     rsp, 28h
0x1800030eb  pop     rdi
0x1800030ec  pop     rsi
0x1800030ed  pop     rbp
0x1800030ee  pop     rbx
0x1800030ef  jmp     _o__seh_filter_dll_0
```
