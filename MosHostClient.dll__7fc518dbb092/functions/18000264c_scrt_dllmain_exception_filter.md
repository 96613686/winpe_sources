# __scrt_dllmain_exception_filter

- ea: `0x18000264c`
- end: `0x180002694`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `int __fastcall(__int64, int, __int64, void (__fastcall *)(__int64, _QWORD, __int64), unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800023b4`

## callees

- `0x18000264c`
- `0x180002e28`
- `0x180002f88`
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
0x18000264c  push    rbx
0x18000264e  push    rbp
0x18000264f  push    rsi
0x180002650  push    rdi
0x180002651  sub     rsp, 28h
0x180002655  mov     rdi, r9
0x180002658  mov     rsi, r8
0x18000265b  mov     ebx, edx
0x18000265d  mov     rbp, rcx
0x180002660  call    __scrt_is_ucrt_dll_in_use
0x180002665  test    eax, eax
0x180002667  jnz     short loc_18000267E
0x180002669  cmp     ebx, 1
0x18000266c  jnz     short loc_18000267E
0x18000266e  mov     r8, rsi
0x180002671  xor     edx, edx
0x180002673  mov     rcx, rbp
0x180002676  mov     rax, rdi
0x180002679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000267e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x180002683  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x180002687  add     rsp, 28h
0x18000268b  pop     rdi
0x18000268c  pop     rsi
0x18000268d  pop     rbp
0x18000268e  pop     rbx
0x18000268f  jmp     _o__seh_filter_dll_0
```
