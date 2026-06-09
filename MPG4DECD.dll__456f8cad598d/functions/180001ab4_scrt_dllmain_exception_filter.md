# __scrt_dllmain_exception_filter

- ea: `0x180001ab4`
- end: `0x180001afc`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001724`

## callees

- `0x180001ab4`
- `0x180002088`
- `0x18000212c`
- `0x180022010`

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
0x180001ab4  push    rbx
0x180001ab6  push    rbp
0x180001ab7  push    rsi
0x180001ab8  push    rdi
0x180001ab9  sub     rsp, 28h
0x180001abd  mov     rdi, r9
0x180001ac0  mov     rsi, r8
0x180001ac3  mov     ebx, edx
0x180001ac5  mov     rbp, rcx
0x180001ac8  call    __scrt_is_ucrt_dll_in_use
0x180001acd  test    eax, eax
0x180001acf  jnz     short loc_180001AE6
0x180001ad1  cmp     ebx, 1
0x180001ad4  jnz     short loc_180001AE6
0x180001ad6  mov     r8, rsi
0x180001ad9  xor     edx, edx
0x180001adb  mov     rcx, rbp
0x180001ade  mov     rax, rdi
0x180001ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ae6  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001aeb  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001aef  add     rsp, 28h
0x180001af3  pop     rdi
0x180001af4  pop     rsi
0x180001af5  pop     rbp
0x180001af6  pop     rbx
0x180001af7  jmp     _o__seh_filter_dll_0
```
