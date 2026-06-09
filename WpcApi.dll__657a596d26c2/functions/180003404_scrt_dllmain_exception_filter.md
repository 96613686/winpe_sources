# __scrt_dllmain_exception_filter

- ea: `0x180003404`
- end: `0x18000344c`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003114`

## callees

- `0x180003404`
- `0x180003bc8`
- `0x180003cd8`
- `0x18002c010`

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
0x180003404  push    rbx
0x180003406  push    rbp
0x180003407  push    rsi
0x180003408  push    rdi
0x180003409  sub     rsp, 28h
0x18000340d  mov     rdi, r9
0x180003410  mov     rsi, r8
0x180003413  mov     ebx, edx
0x180003415  mov     rbp, rcx
0x180003418  call    __scrt_is_ucrt_dll_in_use
0x18000341d  test    eax, eax
0x18000341f  jnz     short loc_180003436
0x180003421  cmp     ebx, 1
0x180003424  jnz     short loc_180003436
0x180003426  mov     r8, rsi
0x180003429  xor     edx, edx
0x18000342b  mov     rcx, rbp
0x18000342e  mov     rax, rdi
0x180003431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003436  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000343b  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000343f  add     rsp, 28h
0x180003443  pop     rdi
0x180003444  pop     rsi
0x180003445  pop     rbp
0x180003446  pop     rbx
0x180003447  jmp     _o__seh_filter_dll_0
```
