# __scrt_dllmain_exception_filter

- ea: `0x18000166c`
- end: `0x1800016b4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800013e4`

## callees

- `0x18000166c`
- `0x180001e78`
- `0x180001fa2`
- `0x18000d010`

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
0x18000166c  push    rbx
0x18000166e  push    rbp
0x18000166f  push    rsi
0x180001670  push    rdi
0x180001671  sub     rsp, 28h
0x180001675  mov     rdi, r9
0x180001678  mov     rsi, r8
0x18000167b  mov     ebx, edx
0x18000167d  mov     rbp, rcx
0x180001680  call    __scrt_is_ucrt_dll_in_use
0x180001685  test    eax, eax
0x180001687  jnz     short loc_18000169E
0x180001689  cmp     ebx, 1
0x18000168c  jnz     short loc_18000169E
0x18000168e  mov     r8, rsi
0x180001691  xor     edx, edx
0x180001693  mov     rcx, rbp
0x180001696  mov     rax, rdi
0x180001699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000169e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800016a3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800016a7  add     rsp, 28h
0x1800016ab  pop     rdi
0x1800016ac  pop     rsi
0x1800016ad  pop     rbp
0x1800016ae  pop     rbx
0x1800016af  jmp     _o__seh_filter_dll_0
```
