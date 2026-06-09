# __scrt_dllmain_exception_filter

- ea: `0x1800017bc`
- end: `0x180001804`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001464`

## callees

- `0x1800017bc`
- `0x180001f58`
- `0x1800020e8`
- `0x18001f010`

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
0x1800017bc  push    rbx
0x1800017be  push    rbp
0x1800017bf  push    rsi
0x1800017c0  push    rdi
0x1800017c1  sub     rsp, 28h
0x1800017c5  mov     rdi, r9
0x1800017c8  mov     rsi, r8
0x1800017cb  mov     ebx, edx
0x1800017cd  mov     rbp, rcx
0x1800017d0  call    __scrt_is_ucrt_dll_in_use
0x1800017d5  test    eax, eax
0x1800017d7  jnz     short loc_1800017EE
0x1800017d9  cmp     ebx, 1
0x1800017dc  jnz     short loc_1800017EE
0x1800017de  mov     r8, rsi
0x1800017e1  xor     edx, edx
0x1800017e3  mov     rcx, rbp
0x1800017e6  mov     rax, rdi
0x1800017e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017ee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800017f3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800017f7  add     rsp, 28h
0x1800017fb  pop     rdi
0x1800017fc  pop     rsi
0x1800017fd  pop     rbp
0x1800017fe  pop     rbx
0x1800017ff  jmp     _o__seh_filter_dll_0
```
