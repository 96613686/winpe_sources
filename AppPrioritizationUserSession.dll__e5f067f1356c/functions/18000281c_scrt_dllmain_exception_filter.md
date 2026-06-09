# __scrt_dllmain_exception_filter

- ea: `0x18000281c`
- end: `0x180002864`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800024c4`

## callees

- `0x18000281c`
- `0x18000310c`
- `0x180003268`
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
0x18000281c  push    rbx
0x18000281e  push    rbp
0x18000281f  push    rsi
0x180002820  push    rdi
0x180002821  sub     rsp, 28h
0x180002825  mov     rdi, r9
0x180002828  mov     rsi, r8
0x18000282b  mov     ebx, edx
0x18000282d  mov     rbp, rcx
0x180002830  call    __scrt_is_ucrt_dll_in_use
0x180002835  test    eax, eax
0x180002837  jnz     short loc_18000284E
0x180002839  cmp     ebx, 1
0x18000283c  jnz     short loc_18000284E
0x18000283e  mov     r8, rsi
0x180002841  xor     edx, edx
0x180002843  mov     rcx, rbp
0x180002846  mov     rax, rdi
0x180002849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002853  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002857  add     rsp, 28h
0x18000285b  pop     rdi
0x18000285c  pop     rsi
0x18000285d  pop     rbp
0x18000285e  pop     rbx
0x18000285f  jmp     _o__seh_filter_dll_0
```
