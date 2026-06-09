# dllmain_dispatch

- ea: `0x18000788c`
- end: `0x1800079b4`
- name: `dllmain_dispatch`
- size: `296`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800079c0`

## callees

- `0x1800073b8`
- `0x1800076a0`
- `0x180007808`
- `0x18000788c`
- `0x180007ec0`
- `0x18000b930`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _crt_argv_mode startup_argv_mode; // eax

  if ( !a2 && dword_180015BB8 <= 0 )
    return 0;
  if ( a2 - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(a1, a2, a3)) != 0) )
  {
    startup_argv_mode = get_startup_argv_mode();
    v7 = startup_argv_mode;
    if ( a2 == 1 && startup_argv_mode == _crt_argv_no_arguments )
    {
      get_startup_argv_mode();
      dllmain_crt_process_detach(a3 != 0);
      if ( pRawDllMain )
        pRawDllMain(a1, 0, a3);
    }
    if ( !a2 || a2 == 3 )
    {
      v7 = dllmain_crt_dispatch(a1, a2, a3);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(a1, a2, a3);
        else
          return 1;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000788c  mov     rax, rsp
0x18000788f  mov     [rax+20h], rbx
0x180007893  mov     [rax+18h], r8
0x180007897  mov     [rax+10h], edx
0x18000789a  mov     [rax+8], rcx
0x18000789e  push    rsi
0x18000789f  push    rdi
0x1800078a0  push    r14
0x1800078a2  sub     rsp, 40h
0x1800078a6  mov     rsi, r8
0x1800078a9  mov     edi, edx
0x1800078ab  mov     r14, rcx
0x1800078ae  test    edx, edx
0x1800078b0  jnz     short loc_1800078C1
0x1800078b2  cmp     cs:dword_180015BB8, edx
0x1800078b8  jg      short loc_1800078C1
0x1800078ba  xor     eax, eax
0x1800078bc  jmp     loc_1800079A6
0x1800078c1  lea     eax, [rdx-1]
0x1800078c4  cmp     eax, 1
0x1800078c7  ja      short loc_180007909
0x1800078c9  mov     rax, cs:_pRawDllMain
0x1800078d0  test    rax, rax
0x1800078d3  jnz     short loc_1800078DA
0x1800078d5  lea     ebx, [rax+1]
0x1800078d8  jmp     short loc_1800078E2
0x1800078da  call    cs:__guard_dispatch_icall_fptr
0x1800078e0  mov     ebx, eax
0x1800078e2  mov     [rsp+58h+var_28], ebx
0x1800078e6  test    ebx, ebx
0x1800078e8  jz      loc_18000799C
0x1800078ee  mov     r8, rsi
0x1800078f1  mov     edx, edi
0x1800078f3  mov     rcx, r14
0x1800078f6  call    dllmain_crt_dispatch
0x1800078fb  mov     ebx, eax
0x1800078fd  mov     [rsp+58h+var_28], eax
0x180007901  test    eax, eax
0x180007903  jz      loc_18000799C
0x180007909  mov     r8, rsi
0x18000790c  mov     edx, edi
0x18000790e  mov     rcx, r14
0x180007911  call    _get_startup_argv_mode
0x180007916  mov     ebx, eax
0x180007918  mov     [rsp+58h+var_28], eax
0x18000791c  cmp     edi, 1
0x18000791f  jnz     short loc_180007957
0x180007921  test    eax, eax
0x180007923  jnz     short loc_180007957
0x180007925  mov     r8, rsi
0x180007928  xor     edx, edx
0x18000792a  mov     rcx, r14
0x18000792d  call    _get_startup_argv_mode
0x180007932  test    rsi, rsi
0x180007935  setnz   cl
0x180007938  call    dllmain_crt_process_detach
0x18000793d  mov     rax, cs:_pRawDllMain
0x180007944  test    rax, rax
0x180007947  jz      short loc_180007957
0x180007949  mov     r8, rsi
0x18000794c  xor     edx, edx
0x18000794e  mov     rcx, r14
0x180007951  call    cs:__guard_dispatch_icall_fptr
0x180007957  test    edi, edi
0x180007959  jz      short loc_180007960
0x18000795b  cmp     edi, 3
0x18000795e  jnz     short loc_18000799C
0x180007960  mov     r8, rsi
0x180007963  mov     edx, edi
0x180007965  mov     rcx, r14
0x180007968  call    dllmain_crt_dispatch
0x18000796d  mov     ebx, eax
0x18000796f  mov     [rsp+58h+var_28], eax
0x180007973  test    eax, eax
0x180007975  jz      short loc_18000799C
0x180007977  mov     rax, cs:_pRawDllMain
0x18000797e  test    rax, rax
0x180007981  jnz     short loc_180007988
0x180007983  lea     ebx, [rax+1]
0x180007986  jmp     short loc_180007998
0x180007988  mov     r8, rsi
0x18000798b  mov     edx, edi
0x18000798d  mov     rcx, r14
0x180007990  call    cs:__guard_dispatch_icall_fptr
0x180007996  mov     ebx, eax
0x180007998  mov     [rsp+58h+var_28], ebx
0x18000799c  jmp     short loc_1800079A4
0x18000799e  xor     ebx, ebx
0x1800079a0  mov     [rsp+58h+var_28], ebx
0x1800079a4  mov     eax, ebx
0x1800079a6  mov     rbx, [rsp+58h+arg_18]
0x1800079ab  add     rsp, 40h
0x1800079af  pop     r14
0x1800079b1  pop     rdi
0x1800079b2  pop     rsi
0x1800079b3  retn
0x18000c9f6  push    rbp
0x18000c9f8  sub     rsp, 30h
0x18000c9fc  mov     rbp, rdx
0x18000c9ff  mov     rax, [rcx]
0x18000ca02  mov     edx, [rax]
0x18000ca04  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000ca09  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000ca0d  lea     r9, dllmain_crt_dispatch; int
0x18000ca14  mov     r8, [rbp+70h]; int
0x18000ca18  mov     edx, [rbp+68h]; int
0x18000ca1b  mov     rcx, [rbp+60h]; int
0x18000ca1f  call    __scrt_dllmain_exception_filter
0x18000ca24  nop
0x18000ca25  add     rsp, 30h
0x18000ca29  pop     rbp
0x18000ca2a  retn
```
