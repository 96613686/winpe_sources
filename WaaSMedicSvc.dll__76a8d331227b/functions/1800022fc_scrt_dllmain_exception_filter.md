# __scrt_dllmain_exception_filter

- ea: `0x1800022fc`
- end: `0x180002344`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002074`

## callees

- `0x1800022fc`
- `0x180002e08`
- `0x180002f58`
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
  if ( !(unsigned int)_scrt_is_ucrt_dll_in_use() && a2 == 1 )
    a4(a1, 0, a3);
  return o__seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x1800022fc  push    rbx
0x1800022fe  push    rbp
0x1800022ff  push    rsi
0x180002300  push    rdi
0x180002301  sub     rsp, 28h
0x180002305  mov     rdi, r9
0x180002308  mov     rsi, r8
0x18000230b  mov     ebx, edx
0x18000230d  mov     rbp, rcx
0x180002310  call    __scrt_is_ucrt_dll_in_use
0x180002315  test    eax, eax
0x180002317  jnz     short loc_18000232E
0x180002319  cmp     ebx, 1
0x18000231c  jnz     short loc_18000232E
0x18000231e  mov     r8, rsi
0x180002321  xor     edx, edx
0x180002323  mov     rcx, rbp
0x180002326  mov     rax, rdi
0x180002329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000232e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002333  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002337  add     rsp, 28h
0x18000233b  pop     rdi
0x18000233c  pop     rsi
0x18000233d  pop     rbp
0x18000233e  pop     rbx
0x18000233f  jmp     _o__seh_filter_dll_0
```
