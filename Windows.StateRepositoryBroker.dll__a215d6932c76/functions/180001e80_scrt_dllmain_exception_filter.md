# __scrt_dllmain_exception_filter

- ea: `0x180001e80`
- end: `0x180001ec8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001bd4`

## callees

- `0x180001e80`
- `0x180002630`
- `0x1800028b8`
- `0x18000b010`

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
0x180001e80  push    rbx
0x180001e82  push    rbp
0x180001e83  push    rsi
0x180001e84  push    rdi
0x180001e85  sub     rsp, 28h
0x180001e89  mov     rdi, r9
0x180001e8c  mov     rsi, r8
0x180001e8f  mov     ebx, edx
0x180001e91  mov     rbp, rcx
0x180001e94  call    __scrt_is_ucrt_dll_in_use
0x180001e99  test    eax, eax
0x180001e9b  jnz     short loc_180001EB2
0x180001e9d  cmp     ebx, 1
0x180001ea0  jnz     short loc_180001EB2
0x180001ea2  mov     r8, rsi
0x180001ea5  xor     edx, edx
0x180001ea7  mov     rcx, rbp
0x180001eaa  mov     rax, rdi
0x180001ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001eb2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001eb7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001ebb  add     rsp, 28h
0x180001ebf  pop     rdi
0x180001ec0  pop     rsi
0x180001ec1  pop     rbp
0x180001ec2  pop     rbx
0x180001ec3  jmp     _o__seh_filter_dll_0
```
