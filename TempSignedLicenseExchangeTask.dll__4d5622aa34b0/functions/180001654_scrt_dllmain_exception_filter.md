# __scrt_dllmain_exception_filter

- ea: `0x180001654`
- end: `0x18000169c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001654`
- `0x180001e20`
- `0x180001f2e`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180001654  push    rbx
0x180001656  push    rbp
0x180001657  push    rsi
0x180001658  push    rdi
0x180001659  sub     rsp, 28h
0x18000165d  mov     rdi, r9
0x180001660  mov     rsi, r8
0x180001663  mov     ebx, edx
0x180001665  mov     rbp, rcx
0x180001668  call    __scrt_is_ucrt_dll_in_use
0x18000166d  test    eax, eax
0x18000166f  jnz     short loc_180001686
0x180001671  cmp     ebx, 1
0x180001674  jnz     short loc_180001686
0x180001676  mov     r8, rsi
0x180001679  xor     edx, edx
0x18000167b  mov     rcx, rbp
0x18000167e  mov     rax, rdi
0x180001681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001686  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000168b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000168f  add     rsp, 28h
0x180001693  pop     rdi
0x180001694  pop     rsi
0x180001695  pop     rbp
0x180001696  pop     rbx
0x180001697  jmp     _o__seh_filter_dll_0
```
