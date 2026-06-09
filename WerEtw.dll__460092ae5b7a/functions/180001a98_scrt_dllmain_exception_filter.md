# __scrt_dllmain_exception_filter

- ea: `0x180001a98`
- end: `0x180001ae0`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800016d4`

## callees

- `0x180001a98`
- `0x180002258`
- `0x1800023b4`
- `0x18002a010`

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
0x180001a98  push    rbx
0x180001a9a  push    rbp
0x180001a9b  push    rsi
0x180001a9c  push    rdi
0x180001a9d  sub     rsp, 28h
0x180001aa1  mov     rdi, r9
0x180001aa4  mov     rsi, r8
0x180001aa7  mov     ebx, edx
0x180001aa9  mov     rbp, rcx
0x180001aac  call    __scrt_is_ucrt_dll_in_use
0x180001ab1  test    eax, eax
0x180001ab3  jnz     short loc_180001ACA
0x180001ab5  cmp     ebx, 1
0x180001ab8  jnz     short loc_180001ACA
0x180001aba  mov     r8, rsi
0x180001abd  xor     edx, edx
0x180001abf  mov     rcx, rbp
0x180001ac2  mov     rax, rdi
0x180001ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aca  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001acf  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001ad3  add     rsp, 28h
0x180001ad7  pop     rdi
0x180001ad8  pop     rsi
0x180001ad9  pop     rbp
0x180001ada  pop     rbx
0x180001adb  jmp     _o__seh_filter_dll_0
```
