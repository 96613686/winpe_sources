# __scrt_dllmain_exception_filter

- ea: `0x1800017ec`
- end: `0x180001834`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001394`

## callees

- `0x1800017ec`
- `0x180001e80`
- `0x180001f98`
- `0x18001f010`

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
0x1800017ec  push    rbx
0x1800017ee  push    rbp
0x1800017ef  push    rsi
0x1800017f0  push    rdi
0x1800017f1  sub     rsp, 28h
0x1800017f5  mov     rdi, r9
0x1800017f8  mov     rsi, r8
0x1800017fb  mov     ebx, edx
0x1800017fd  mov     rbp, rcx
0x180001800  call    __scrt_is_ucrt_dll_in_use
0x180001805  test    eax, eax
0x180001807  jnz     short loc_18000181E
0x180001809  cmp     ebx, 1
0x18000180c  jnz     short loc_18000181E
0x18000180e  mov     r8, rsi
0x180001811  xor     edx, edx
0x180001813  mov     rcx, rbp
0x180001816  mov     rax, rdi
0x180001819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001823  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180001827  add     rsp, 28h
0x18000182b  pop     rdi
0x18000182c  pop     rsi
0x18000182d  pop     rbp
0x18000182e  pop     rbx
0x18000182f  jmp     _o__seh_filter_dll_0
```
