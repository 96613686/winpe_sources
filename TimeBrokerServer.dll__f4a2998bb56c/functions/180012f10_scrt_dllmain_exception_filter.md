# __scrt_dllmain_exception_filter

- ea: `0x180012f10`
- end: `0x180012f58`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012c44`

## callees

- `0x180012f10`
- `0x180013818`
- `0x180013918`
- `0x18001c010`

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
0x180012f10  push    rbx
0x180012f12  push    rbp
0x180012f13  push    rsi
0x180012f14  push    rdi
0x180012f15  sub     rsp, 28h
0x180012f19  mov     rdi, r9
0x180012f1c  mov     rsi, r8
0x180012f1f  mov     ebx, edx
0x180012f21  mov     rbp, rcx
0x180012f24  call    __scrt_is_ucrt_dll_in_use
0x180012f29  test    eax, eax
0x180012f2b  jnz     short loc_180012F42
0x180012f2d  cmp     ebx, 1
0x180012f30  jnz     short loc_180012F42
0x180012f32  mov     r8, rsi
0x180012f35  xor     edx, edx
0x180012f37  mov     rcx, rbp
0x180012f3a  mov     rax, rdi
0x180012f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f42  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180012f47  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180012f4b  add     rsp, 28h
0x180012f4f  pop     rdi
0x180012f50  pop     rsi
0x180012f51  pop     rbp
0x180012f52  pop     rbx
0x180012f53  jmp     _o__seh_filter_dll_0
```
