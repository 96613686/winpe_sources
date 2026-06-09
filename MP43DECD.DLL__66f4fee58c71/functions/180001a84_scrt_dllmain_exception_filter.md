# __scrt_dllmain_exception_filter

- ea: `0x180001a84`
- end: `0x180001acc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800016f4`

## callees

- `0x180001a84`
- `0x180002058`
- `0x1800020fc`
- `0x180022010`

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
0x180001a84  push    rbx
0x180001a86  push    rbp
0x180001a87  push    rsi
0x180001a88  push    rdi
0x180001a89  sub     rsp, 28h
0x180001a8d  mov     rdi, r9
0x180001a90  mov     rsi, r8
0x180001a93  mov     ebx, edx
0x180001a95  mov     rbp, rcx
0x180001a98  call    __scrt_is_ucrt_dll_in_use
0x180001a9d  test    eax, eax
0x180001a9f  jnz     short loc_180001AB6
0x180001aa1  cmp     ebx, 1
0x180001aa4  jnz     short loc_180001AB6
0x180001aa6  mov     r8, rsi
0x180001aa9  xor     edx, edx
0x180001aab  mov     rcx, rbp
0x180001aae  mov     rax, rdi
0x180001ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001abb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001abf  add     rsp, 28h
0x180001ac3  pop     rdi
0x180001ac4  pop     rsi
0x180001ac5  pop     rbp
0x180001ac6  pop     rbx
0x180001ac7  jmp     _o__seh_filter_dll_0
```
