# __scrt_dllmain_exception_filter

- ea: `0x180004d90`
- end: `0x180004dd8`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004ae4`

## callees

- `0x180004d90`
- `0x18000554c`
- `0x180005698`
- `0x180014010`

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
0x180004d90  push    rbx
0x180004d92  push    rbp
0x180004d93  push    rsi
0x180004d94  push    rdi
0x180004d95  sub     rsp, 28h
0x180004d99  mov     rdi, r9
0x180004d9c  mov     rsi, r8
0x180004d9f  mov     ebx, edx
0x180004da1  mov     rbp, rcx
0x180004da4  call    __scrt_is_ucrt_dll_in_use
0x180004da9  test    eax, eax
0x180004dab  jnz     short loc_180004DC2
0x180004dad  cmp     ebx, 1
0x180004db0  jnz     short loc_180004DC2
0x180004db2  mov     r8, rsi
0x180004db5  xor     edx, edx
0x180004db7  mov     rcx, rbp
0x180004dba  mov     rax, rdi
0x180004dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc2  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180004dc7  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180004dcb  add     rsp, 28h
0x180004dcf  pop     rdi
0x180004dd0  pop     rsi
0x180004dd1  pop     rbp
0x180004dd2  pop     rbx
0x180004dd3  jmp     _o__seh_filter_dll_0
```
