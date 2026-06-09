# __scrt_dllmain_exception_filter

- ea: `0x180002cbc`
- end: `0x180002d04`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002a34`

## callees

- `0x180002cbc`
- `0x180003428`
- `0x180003528`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x180002cbc  push    rbx
0x180002cbe  push    rbp
0x180002cbf  push    rsi
0x180002cc0  push    rdi
0x180002cc1  sub     rsp, 28h
0x180002cc5  mov     rdi, r9
0x180002cc8  mov     rsi, r8
0x180002ccb  mov     ebx, edx
0x180002ccd  mov     rbp, rcx
0x180002cd0  call    __scrt_is_ucrt_dll_in_use
0x180002cd5  test    eax, eax
0x180002cd7  jnz     short loc_180002CEE
0x180002cd9  cmp     ebx, 1
0x180002cdc  jnz     short loc_180002CEE
0x180002cde  mov     r8, rsi
0x180002ce1  xor     edx, edx
0x180002ce3  mov     rcx, rbp
0x180002ce6  mov     rax, rdi
0x180002ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cee  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002cf3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002cf7  add     rsp, 28h
0x180002cfb  pop     rdi
0x180002cfc  pop     rsi
0x180002cfd  pop     rbp
0x180002cfe  pop     rbx
0x180002cff  jmp     _o__seh_filter_dll_0
```
