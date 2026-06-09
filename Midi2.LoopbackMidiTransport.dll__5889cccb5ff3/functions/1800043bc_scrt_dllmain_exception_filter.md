# __scrt_dllmain_exception_filter

- ea: `0x1800043bc`
- end: `0x180004404`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003fe4`

## callees

- `0x1800043bc`
- `0x180004eb0`
- `0x180004fb8`
- `0x180032010`

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
0x1800043bc  push    rbx
0x1800043be  push    rbp
0x1800043bf  push    rsi
0x1800043c0  push    rdi
0x1800043c1  sub     rsp, 28h
0x1800043c5  mov     rdi, r9
0x1800043c8  mov     rsi, r8
0x1800043cb  mov     ebx, edx
0x1800043cd  mov     rbp, rcx
0x1800043d0  call    __scrt_is_ucrt_dll_in_use
0x1800043d5  test    eax, eax
0x1800043d7  jnz     short loc_1800043EE
0x1800043d9  cmp     ebx, 1
0x1800043dc  jnz     short loc_1800043EE
0x1800043de  mov     r8, rsi
0x1800043e1  xor     edx, edx
0x1800043e3  mov     rcx, rbp
0x1800043e6  mov     rax, rdi
0x1800043e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800043f3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800043f7  add     rsp, 28h
0x1800043fb  pop     rdi
0x1800043fc  pop     rsi
0x1800043fd  pop     rbp
0x1800043fe  pop     rbx
0x1800043ff  jmp     _o__seh_filter_dll_0
```
