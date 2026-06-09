# __scrt_dllmain_exception_filter

- ea: `0x18000176c`
- end: `0x1800017b4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001494`

## callees

- `0x18000176c`
- `0x180001f78`
- `0x180002088`
- `0x18000e010`

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
0x18000176c  push    rbx
0x18000176e  push    rbp
0x18000176f  push    rsi
0x180001770  push    rdi
0x180001771  sub     rsp, 28h
0x180001775  mov     rdi, r9
0x180001778  mov     rsi, r8
0x18000177b  mov     ebx, edx
0x18000177d  mov     rbp, rcx
0x180001780  call    __scrt_is_ucrt_dll_in_use
0x180001785  test    eax, eax
0x180001787  jnz     short loc_18000179E
0x180001789  cmp     ebx, 1
0x18000178c  jnz     short loc_18000179E
0x18000178e  mov     r8, rsi
0x180001791  xor     edx, edx
0x180001793  mov     rcx, rbp
0x180001796  mov     rax, rdi
0x180001799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000179e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800017a3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800017a7  add     rsp, 28h
0x1800017ab  pop     rdi
0x1800017ac  pop     rsi
0x1800017ad  pop     rbp
0x1800017ae  pop     rbx
0x1800017af  jmp     _o__seh_filter_dll_0
```
