# __scrt_dllmain_exception_filter

- ea: `0x18000216c`
- end: `0x1800021b4`
- name: `__scrt_dllmain_exception_filter`
- size: `72`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001e64`

## callees

- `0x18000216c`
- `0x180002934`
- `0x180002a38`
- `0x18000e010`

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
0x18000216c  push    rbx
0x18000216e  push    rbp
0x18000216f  push    rsi
0x180002170  push    rdi
0x180002171  sub     rsp, 28h
0x180002175  mov     rdi, r9
0x180002178  mov     rsi, r8
0x18000217b  mov     ebx, edx
0x18000217d  mov     rbp, rcx
0x180002180  call    __scrt_is_ucrt_dll_in_use
0x180002185  test    eax, eax
0x180002187  jnz     short loc_18000219E
0x180002189  cmp     ebx, 1
0x18000218c  jnz     short loc_18000219E
0x18000218e  mov     r8, rsi
0x180002191  xor     edx, edx
0x180002193  mov     rcx, rbp
0x180002196  mov     rax, rdi
0x180002199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219e  mov     rdx, [rsp+48h+ExceptionPtr]; ExceptionPtr
0x1800021a3  mov     ecx, [rsp+48h+ExceptionNum]; ExceptionNum
0x1800021a7  add     rsp, 28h
0x1800021ab  pop     rdi
0x1800021ac  pop     rsi
0x1800021ad  pop     rbp
0x1800021ae  pop     rbx
0x1800021af  jmp     _o__seh_filter_dll_0
```
