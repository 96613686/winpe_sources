# __scrt_dllmain_exception_filter

- ea: `0x18000172c`
- end: `0x180001774`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800014a4`

## callees

- `0x18000172c`
- `0x180001e68`
- `0x180001f58`
- `0x18000d010`

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
0x18000172c  push    rbx
0x18000172e  push    rbp
0x18000172f  push    rsi
0x180001730  push    rdi
0x180001731  sub     rsp, 28h
0x180001735  mov     rdi, r9
0x180001738  mov     rsi, r8
0x18000173b  mov     ebx, edx
0x18000173d  mov     rbp, rcx
0x180001740  call    __scrt_is_ucrt_dll_in_use
0x180001745  test    eax, eax
0x180001747  jnz     short loc_18000175E
0x180001749  cmp     ebx, 1
0x18000174c  jnz     short loc_18000175E
0x18000174e  mov     r8, rsi
0x180001751  xor     edx, edx
0x180001753  mov     rcx, rbp
0x180001756  mov     rax, rdi
0x180001759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000175e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001763  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001767  add     rsp, 28h
0x18000176b  pop     rdi
0x18000176c  pop     rsi
0x18000176d  pop     rbp
0x18000176e  pop     rbx
0x18000176f  jmp     _o__seh_filter_dll_0
```
