# __scrt_dllmain_exception_filter

- ea: `0x18000e920`
- end: `0x18000e968`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000e5b4`

## callees

- `0x18000e920`
- `0x18000eed0`
- `0x18000ef8c`
- `0x180012010`

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
0x18000e920  push    rbx
0x18000e922  push    rbp
0x18000e923  push    rsi
0x18000e924  push    rdi
0x18000e925  sub     rsp, 28h
0x18000e929  mov     rdi, r9
0x18000e92c  mov     rsi, r8
0x18000e92f  mov     ebx, edx
0x18000e931  mov     rbp, rcx
0x18000e934  call    __scrt_is_ucrt_dll_in_use
0x18000e939  test    eax, eax
0x18000e93b  jnz     short loc_18000E952
0x18000e93d  cmp     ebx, 1
0x18000e940  jnz     short loc_18000E952
0x18000e942  mov     r8, rsi
0x18000e945  xor     edx, edx
0x18000e947  mov     rcx, rbp
0x18000e94a  mov     rax, rdi
0x18000e94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e952  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x18000e957  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000e95b  add     rsp, 28h
0x18000e95f  pop     rdi
0x18000e960  pop     rsi
0x18000e961  pop     rbp
0x18000e962  pop     rbx
0x18000e963  jmp     _o__seh_filter_dll_0
```
