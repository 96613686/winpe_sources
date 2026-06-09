# __scrt_dllmain_exception_filter

- ea: `0x18000226c`
- end: `0x1800022b4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001fe4`

## callees

- `0x18000226c`
- `0x180002a68`
- `0x180002c78`
- `0x18000f010`

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
0x18000226c  push    rbx
0x18000226e  push    rbp
0x18000226f  push    rsi
0x180002270  push    rdi
0x180002271  sub     rsp, 28h
0x180002275  mov     rdi, r9
0x180002278  mov     rsi, r8
0x18000227b  mov     ebx, edx
0x18000227d  mov     rbp, rcx
0x180002280  call    __scrt_is_ucrt_dll_in_use
0x180002285  test    eax, eax
0x180002287  jnz     short loc_18000229E
0x180002289  cmp     ebx, 1
0x18000228c  jnz     short loc_18000229E
0x18000228e  mov     r8, rsi
0x180002291  xor     edx, edx
0x180002293  mov     rcx, rbp
0x180002296  mov     rax, rdi
0x180002299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000229e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800022a3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800022a7  add     rsp, 28h
0x1800022ab  pop     rdi
0x1800022ac  pop     rsi
0x1800022ad  pop     rbp
0x1800022ae  pop     rbx
0x1800022af  jmp     _o__seh_filter_dll_0
```
