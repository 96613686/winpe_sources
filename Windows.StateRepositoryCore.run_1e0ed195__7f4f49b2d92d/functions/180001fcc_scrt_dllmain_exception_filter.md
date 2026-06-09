# __scrt_dllmain_exception_filter

- ea: `0x180001fcc`
- end: `0x180002014`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001d44`

## callees

- `0x180001fcc`
- `0x180002738`
- `0x180002848`
- `0x180011010`

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
0x180001fcc  push    rbx
0x180001fce  push    rbp
0x180001fcf  push    rsi
0x180001fd0  push    rdi
0x180001fd1  sub     rsp, 28h
0x180001fd5  mov     rdi, r9
0x180001fd8  mov     rsi, r8
0x180001fdb  mov     ebx, edx
0x180001fdd  mov     rbp, rcx
0x180001fe0  call    __scrt_is_ucrt_dll_in_use
0x180001fe5  test    eax, eax
0x180001fe7  jnz     short loc_180001FFE
0x180001fe9  cmp     ebx, 1
0x180001fec  jnz     short loc_180001FFE
0x180001fee  mov     r8, rsi
0x180001ff1  xor     edx, edx
0x180001ff3  mov     rcx, rbp
0x180001ff6  mov     rax, rdi
0x180001ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ffe  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002003  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002007  add     rsp, 28h
0x18000200b  pop     rdi
0x18000200c  pop     rsi
0x18000200d  pop     rbp
0x18000200e  pop     rbx
0x18000200f  jmp     _o__seh_filter_dll_0
```
