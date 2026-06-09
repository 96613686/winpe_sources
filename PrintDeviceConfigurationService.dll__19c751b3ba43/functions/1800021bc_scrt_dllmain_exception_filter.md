# __scrt_dllmain_exception_filter

- ea: `0x1800021bc`
- end: `0x180002204`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001f34`

## callees

- `0x1800021bc`
- `0x180002978`
- `0x180002af8`
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
0x1800021bc  push    rbx
0x1800021be  push    rbp
0x1800021bf  push    rsi
0x1800021c0  push    rdi
0x1800021c1  sub     rsp, 28h
0x1800021c5  mov     rdi, r9
0x1800021c8  mov     rsi, r8
0x1800021cb  mov     ebx, edx
0x1800021cd  mov     rbp, rcx
0x1800021d0  call    __scrt_is_ucrt_dll_in_use
0x1800021d5  test    eax, eax
0x1800021d7  jnz     short loc_1800021EE
0x1800021d9  cmp     ebx, 1
0x1800021dc  jnz     short loc_1800021EE
0x1800021de  mov     r8, rsi
0x1800021e1  xor     edx, edx
0x1800021e3  mov     rcx, rbp
0x1800021e6  mov     rax, rdi
0x1800021e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800021f3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800021f7  add     rsp, 28h
0x1800021fb  pop     rdi
0x1800021fc  pop     rsi
0x1800021fd  pop     rbp
0x1800021fe  pop     rbx
0x1800021ff  jmp     _o__seh_filter_dll_0
```
