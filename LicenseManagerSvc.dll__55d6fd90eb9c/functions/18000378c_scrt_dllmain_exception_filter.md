# __scrt_dllmain_exception_filter

- ea: `0x18000378c`
- end: `0x1800037d4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003244`

## callees

- `0x18000378c`
- `0x180003f4c`
- `0x180004148`
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
  if ( !_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000378c  push    rbx
0x18000378e  push    rbp
0x18000378f  push    rsi
0x180003790  push    rdi
0x180003791  sub     rsp, 28h
0x180003795  mov     rdi, r9
0x180003798  mov     rsi, r8
0x18000379b  mov     ebx, edx
0x18000379d  mov     rbp, rcx
0x1800037a0  call    __scrt_is_ucrt_dll_in_use
0x1800037a5  test    eax, eax
0x1800037a7  jnz     short loc_1800037BE
0x1800037a9  cmp     ebx, 1
0x1800037ac  jnz     short loc_1800037BE
0x1800037ae  mov     r8, rsi
0x1800037b1  xor     edx, edx
0x1800037b3  mov     rcx, rbp
0x1800037b6  mov     rax, rdi
0x1800037b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037be  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800037c3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800037c7  add     rsp, 28h
0x1800037cb  pop     rdi
0x1800037cc  pop     rsi
0x1800037cd  pop     rbp
0x1800037ce  pop     rbx
0x1800037cf  jmp     _o__seh_filter_dll_0
```
