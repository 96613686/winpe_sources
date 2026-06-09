# dllmain_dispatch

- ea: `0x1800187bc`
- end: `0x1800188e4`
- name: `dllmain_dispatch`
- size: `296`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800188f0`

## callees

- `0x180018308`
- `0x1800185d0`
- `0x180018738`
- `0x1800187bc`
- `0x180018ee0`
- `0x18001cdf0`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _crt_argv_mode startup_argv_mode; // eax

  if ( !a2 && dword_18002DEC8 <= 0 )
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
0x1800187bc  mov     rax, rsp
0x1800187bf  mov     [rax+20h], rbx
0x1800187c3  mov     [rax+18h], r8
0x1800187c7  mov     [rax+10h], edx
0x1800187ca  mov     [rax+8], rcx
0x1800187ce  push    rsi
0x1800187cf  push    rdi
0x1800187d0  push    r14
0x1800187d2  sub     rsp, 40h
0x1800187d6  mov     rsi, r8
0x1800187d9  mov     edi, edx
0x1800187db  mov     r14, rcx
0x1800187de  test    edx, edx
0x1800187e0  jnz     short loc_1800187F1
0x1800187e2  cmp     cs:dword_18002DEC8, edx
0x1800187e8  jg      short loc_1800187F1
0x1800187ea  xor     eax, eax
0x1800187ec  jmp     loc_1800188D6
0x1800187f1  lea     eax, [rdx-1]
0x1800187f4  cmp     eax, 1
0x1800187f7  ja      short loc_180018839
0x1800187f9  mov     rax, cs:_pRawDllMain
0x180018800  test    rax, rax
0x180018803  jnz     short loc_18001880A
0x180018805  lea     ebx, [rax+1]
0x180018808  jmp     short loc_180018812
0x18001880a  call    cs:__guard_dispatch_icall_fptr
0x180018810  mov     ebx, eax
0x180018812  mov     [rsp+58h+var_28], ebx
0x180018816  test    ebx, ebx
0x180018818  jz      loc_1800188CC
0x18001881e  mov     r8, rsi
0x180018821  mov     edx, edi
0x180018823  mov     rcx, r14
0x180018826  call    dllmain_crt_dispatch
0x18001882b  mov     ebx, eax
0x18001882d  mov     [rsp+58h+var_28], eax
0x180018831  test    eax, eax
0x180018833  jz      loc_1800188CC
0x180018839  mov     r8, rsi
0x18001883c  mov     edx, edi
0x18001883e  mov     rcx, r14
0x180018841  call    _get_startup_argv_mode
0x180018846  mov     ebx, eax
0x180018848  mov     [rsp+58h+var_28], eax
0x18001884c  cmp     edi, 1
0x18001884f  jnz     short loc_180018887
0x180018851  test    eax, eax
0x180018853  jnz     short loc_180018887
0x180018855  mov     r8, rsi
0x180018858  xor     edx, edx
0x18001885a  mov     rcx, r14
0x18001885d  call    _get_startup_argv_mode
0x180018862  test    rsi, rsi
0x180018865  setnz   cl
0x180018868  call    dllmain_crt_process_detach
0x18001886d  mov     rax, cs:_pRawDllMain
0x180018874  test    rax, rax
0x180018877  jz      short loc_180018887
0x180018879  mov     r8, rsi
0x18001887c  xor     edx, edx
0x18001887e  mov     rcx, r14
0x180018881  call    cs:__guard_dispatch_icall_fptr
0x180018887  test    edi, edi
0x180018889  jz      short loc_180018890
0x18001888b  cmp     edi, 3
0x18001888e  jnz     short loc_1800188CC
0x180018890  mov     r8, rsi
0x180018893  mov     edx, edi
0x180018895  mov     rcx, r14
0x180018898  call    dllmain_crt_dispatch
0x18001889d  mov     ebx, eax
0x18001889f  mov     [rsp+58h+var_28], eax
0x1800188a3  test    eax, eax
0x1800188a5  jz      short loc_1800188CC
0x1800188a7  mov     rax, cs:_pRawDllMain
0x1800188ae  test    rax, rax
0x1800188b1  jnz     short loc_1800188B8
0x1800188b3  lea     ebx, [rax+1]
0x1800188b6  jmp     short loc_1800188C8
0x1800188b8  mov     r8, rsi
0x1800188bb  mov     edx, edi
0x1800188bd  mov     rcx, r14
0x1800188c0  call    cs:__guard_dispatch_icall_fptr
0x1800188c6  mov     ebx, eax
0x1800188c8  mov     [rsp+58h+var_28], ebx
0x1800188cc  jmp     short loc_1800188D4
0x1800188ce  xor     ebx, ebx
0x1800188d0  mov     [rsp+58h+var_28], ebx
0x1800188d4  mov     eax, ebx
0x1800188d6  mov     rbx, [rsp+58h+arg_18]
0x1800188db  add     rsp, 40h
0x1800188df  pop     r14
0x1800188e1  pop     rdi
0x1800188e2  pop     rsi
0x1800188e3  retn
0x18001f58c  push    rbp
0x18001f58e  sub     rsp, 30h
0x18001f592  mov     rbp, rdx
0x18001f595  mov     rax, [rcx]
0x18001f598  mov     edx, [rax]
0x18001f59a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001f59f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001f5a3  lea     r9, dllmain_crt_dispatch; int
0x18001f5aa  mov     r8, [rbp+70h]; int
0x18001f5ae  mov     edx, [rbp+68h]; int
0x18001f5b1  mov     rcx, [rbp+60h]; int
0x18001f5b5  call    __scrt_dllmain_exception_filter
0x18001f5ba  nop
0x18001f5bb  add     rsp, 30h
0x18001f5bf  pop     rbp
0x18001f5c0  retn
```
