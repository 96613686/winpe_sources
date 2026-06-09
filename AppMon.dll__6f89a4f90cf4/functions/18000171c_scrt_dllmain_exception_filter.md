# __scrt_dllmain_exception_filter

- ea: `0x18000171c`
- end: `0x180001764`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001494`

## callees

- `0x18000171c`
- `0x180001e7c`
- `0x180001f88`
- `0x180010010`

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
0x18000171c  push    rbx
0x18000171e  push    rbp
0x18000171f  push    rsi
0x180001720  push    rdi
0x180001721  sub     rsp, 28h
0x180001725  mov     rdi, r9
0x180001728  mov     rsi, r8
0x18000172b  mov     ebx, edx
0x18000172d  mov     rbp, rcx
0x180001730  call    __scrt_is_ucrt_dll_in_use
0x180001735  test    eax, eax
0x180001737  jnz     short loc_18000174E
0x180001739  cmp     ebx, 1
0x18000173c  jnz     short loc_18000174E
0x18000173e  mov     r8, rsi
0x180001741  xor     edx, edx
0x180001743  mov     rcx, rbp
0x180001746  mov     rax, rdi
0x180001749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000174e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001753  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001757  add     rsp, 28h
0x18000175b  pop     rdi
0x18000175c  pop     rsi
0x18000175d  pop     rbp
0x18000175e  pop     rbx
0x18000175f  jmp     _o__seh_filter_dll_0
```
