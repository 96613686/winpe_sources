# __scrt_dllmain_exception_filter

- ea: `0x18002acd0`
- end: `0x18002ad18`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002a934`

## callees

- `0x18002acd0`
- `0x18002b298`
- `0x18002b34c`
- `0x180046010`

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
0x18002acd0  push    rbx
0x18002acd2  push    rbp
0x18002acd3  push    rsi
0x18002acd4  push    rdi
0x18002acd5  sub     rsp, 28h
0x18002acd9  mov     rdi, r9
0x18002acdc  mov     rsi, r8
0x18002acdf  mov     ebx, edx
0x18002ace1  mov     rbp, rcx
0x18002ace4  call    __scrt_is_ucrt_dll_in_use
0x18002ace9  test    eax, eax
0x18002aceb  jnz     short loc_18002AD02
0x18002aced  cmp     ebx, 1
0x18002acf0  jnz     short loc_18002AD02
0x18002acf2  mov     r8, rsi
0x18002acf5  xor     edx, edx
0x18002acf7  mov     rcx, rbp
0x18002acfa  mov     rax, rdi
0x18002acfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad02  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18002ad07  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18002ad0b  add     rsp, 28h
0x18002ad0f  pop     rdi
0x18002ad10  pop     rsi
0x18002ad11  pop     rbp
0x18002ad12  pop     rbx
0x18002ad13  jmp     _o__seh_filter_dll_0
```
