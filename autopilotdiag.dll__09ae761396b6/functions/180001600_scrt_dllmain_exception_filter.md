# __scrt_dllmain_exception_filter

- ea: `0x180001600`
- end: `0x180001648`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001274`

## callees

- `0x180001600`
- `0x180001bb0`
- `0x180001c46`
- `0x180002010`

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
0x180001600  push    rbx
0x180001602  push    rbp
0x180001603  push    rsi
0x180001604  push    rdi
0x180001605  sub     rsp, 28h
0x180001609  mov     rdi, r9
0x18000160c  mov     rsi, r8
0x18000160f  mov     ebx, edx
0x180001611  mov     rbp, rcx
0x180001614  call    __scrt_is_ucrt_dll_in_use
0x180001619  test    eax, eax
0x18000161b  jnz     short loc_180001632
0x18000161d  cmp     ebx, 1
0x180001620  jnz     short loc_180001632
0x180001622  mov     r8, rsi
0x180001625  xor     edx, edx
0x180001627  mov     rcx, rbp
0x18000162a  mov     rax, rdi
0x18000162d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001632  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180001637  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x18000163b  add     rsp, 28h
0x18000163f  pop     rdi
0x180001640  pop     rsi
0x180001641  pop     rbp
0x180001642  pop     rbx
0x180001643  jmp     _o__seh_filter_dll_0
```
