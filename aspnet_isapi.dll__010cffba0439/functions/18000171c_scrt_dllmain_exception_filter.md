# __scrt_dllmain_exception_filter

- ea: `0x18000171c`
- end: `0x18000177c`
- name: `__scrt_dllmain_exception_filter`
- size: `96`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int ExceptionNum, struct _EXCEPTION_POINTERS *ExceptionPtr)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000133c`

## callees

- `0x18000171c`
- `0x180001e94`
- `0x180001ebe`
- `0x180001f00`

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
  return seh_filter_dll_0(ExceptionNum, ExceptionPtr);
}

```

## disassembly

```asm
0x18000171c  mov     [rsp+arg_0], rbx
0x180001721  mov     [rsp+arg_8], rbp
0x180001726  mov     [rsp+arg_10], rsi
0x18000172b  push    rdi
0x18000172c  sub     rsp, 20h
0x180001730  mov     rdi, r9
0x180001733  mov     rsi, r8
0x180001736  mov     ebx, edx
0x180001738  mov     rbp, rcx
0x18000173b  call    __scrt_is_ucrt_dll_in_use
0x180001740  test    eax, eax
0x180001742  jnz     short loc_18000175A
0x180001744  cmp     ebx, 1
0x180001747  jnz     short loc_18000175A
0x180001749  mov     r8, rsi
0x18000174c  xor     edx, edx
0x18000174e  mov     rcx, rbp
0x180001751  mov     rax, rdi
0x180001754  call    cs:__guard_dispatch_icall_fptr
0x18000175a  mov     rdx, [rsp+28h+ExceptionPtr]; ExceptionPtr
0x18000175f  mov     ecx, [rsp+28h+ExceptionNum]; ExceptionNum
0x180001763  mov     rbx, [rsp+28h+arg_0]
0x180001768  mov     rbp, [rsp+28h+arg_8]
0x18000176d  mov     rsi, [rsp+28h+arg_10]
0x180001772  add     rsp, 20h
0x180001776  pop     rdi
0x180001777  jmp     _seh_filter_dll_0
```
