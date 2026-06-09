# __scrt_dllmain_exception_filter

- ea: `0x180001bbc`
- end: `0x180001c04`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001934`

## callees

- `0x180001bbc`
- `0x180002378`
- `0x180002678`
- `0x180023010`

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
0x180001bbc  push    rbx
0x180001bbe  push    rbp
0x180001bbf  push    rsi
0x180001bc0  push    rdi
0x180001bc1  sub     rsp, 28h
0x180001bc5  mov     rdi, r9
0x180001bc8  mov     rsi, r8
0x180001bcb  mov     ebx, edx
0x180001bcd  mov     rbp, rcx
0x180001bd0  call    __scrt_is_ucrt_dll_in_use
0x180001bd5  test    eax, eax
0x180001bd7  jnz     short loc_180001BEE
0x180001bd9  cmp     ebx, 1
0x180001bdc  jnz     short loc_180001BEE
0x180001bde  mov     r8, rsi
0x180001be1  xor     edx, edx
0x180001be3  mov     rcx, rbp
0x180001be6  mov     rax, rdi
0x180001be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001bf3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001bf7  add     rsp, 28h
0x180001bfb  pop     rdi
0x180001bfc  pop     rsi
0x180001bfd  pop     rbp
0x180001bfe  pop     rbx
0x180001bff  jmp     _o__seh_filter_dll_0
```
