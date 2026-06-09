# __scrt_dllmain_exception_filter

- ea: `0x180001ee0`
- end: `0x180001f28`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001c34`

## callees

- `0x180001ee0`
- `0x18000269c`
- `0x180002778`
- `0x180019010`

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
0x180001ee0  push    rbx
0x180001ee2  push    rbp
0x180001ee3  push    rsi
0x180001ee4  push    rdi
0x180001ee5  sub     rsp, 28h
0x180001ee9  mov     rdi, r9
0x180001eec  mov     rsi, r8
0x180001eef  mov     ebx, edx
0x180001ef1  mov     rbp, rcx
0x180001ef4  call    __scrt_is_ucrt_dll_in_use
0x180001ef9  test    eax, eax
0x180001efb  jnz     short loc_180001F12
0x180001efd  cmp     ebx, 1
0x180001f00  jnz     short loc_180001F12
0x180001f02  mov     r8, rsi
0x180001f05  xor     edx, edx
0x180001f07  mov     rcx, rbp
0x180001f0a  mov     rax, rdi
0x180001f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f12  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001f17  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001f1b  add     rsp, 28h
0x180001f1f  pop     rdi
0x180001f20  pop     rsi
0x180001f21  pop     rbp
0x180001f22  pop     rbx
0x180001f23  jmp     _o__seh_filter_dll_0
```
