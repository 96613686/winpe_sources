# __scrt_dllmain_exception_filter

- ea: `0x180001774`
- end: `0x1800017bc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800012d4`

## callees

- `0x180001774`
- `0x180001d9c`
- `0x180001e68`
- `0x180034010`

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
0x180001774  push    rbx
0x180001776  push    rbp
0x180001777  push    rsi
0x180001778  push    rdi
0x180001779  sub     rsp, 28h
0x18000177d  mov     rdi, r9
0x180001780  mov     rsi, r8
0x180001783  mov     ebx, edx
0x180001785  mov     rbp, rcx
0x180001788  call    __scrt_is_ucrt_dll_in_use
0x18000178d  test    eax, eax
0x18000178f  jnz     short loc_1800017A6
0x180001791  cmp     ebx, 1
0x180001794  jnz     short loc_1800017A6
0x180001796  mov     r8, rsi
0x180001799  xor     edx, edx
0x18000179b  mov     rcx, rbp
0x18000179e  mov     rax, rdi
0x1800017a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017a6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800017ab  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800017af  add     rsp, 28h
0x1800017b3  pop     rdi
0x1800017b4  pop     rsi
0x1800017b5  pop     rbp
0x1800017b6  pop     rbx
0x1800017b7  jmp     _o__seh_filter_dll_0
```
