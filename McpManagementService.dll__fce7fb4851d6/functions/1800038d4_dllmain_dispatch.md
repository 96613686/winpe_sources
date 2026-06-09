# dllmain_dispatch

- ea: `0x1800038d4`
- end: `0x1800039fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003a10`

## callees

- `0x1800036f0`
- `0x1800038d4`
- `0x180003be0`
- `0x18000ed18`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _crt_argv_mode startup_argv_mode; // eax

  if ( !a2 && dword_18003F4D0 <= 0 )
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
      dllmain_crt_dispatch(a1, 0, a3);
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
0x1800038d4  mov     rax, rsp
0x1800038d7  mov     [rax+20h], rbx
0x1800038db  mov     [rax+18h], r8
0x1800038df  mov     [rax+10h], edx
0x1800038e2  mov     [rax+8], rcx
0x1800038e6  push    rsi
0x1800038e7  push    rdi
0x1800038e8  push    r14
0x1800038ea  sub     rsp, 40h
0x1800038ee  mov     rsi, r8
0x1800038f1  mov     edi, edx
0x1800038f3  mov     r14, rcx
0x1800038f6  test    edx, edx
0x1800038f8  jnz     short loc_180003909
0x1800038fa  cmp     cs:dword_18003F4D0, edx
0x180003900  jg      short loc_180003909
0x180003902  xor     eax, eax
0x180003904  jmp     loc_1800039ED
0x180003909  lea     eax, [rdx-1]
0x18000390c  cmp     eax, 1
0x18000390f  ja      short loc_180003950
0x180003911  mov     rax, cs:_pRawDllMain
0x180003918  test    rax, rax
0x18000391b  jnz     short loc_180003922
0x18000391d  lea     ebx, [rax+1]
0x180003920  jmp     short loc_180003929
0x180003922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003927  mov     ebx, eax
0x180003929  mov     [rsp+58h+var_28], ebx
0x18000392d  test    ebx, ebx
0x18000392f  jz      loc_1800039E3
0x180003935  mov     r8, rsi
0x180003938  mov     edx, edi
0x18000393a  mov     rcx, r14
0x18000393d  call    dllmain_crt_dispatch
0x180003942  mov     ebx, eax
0x180003944  mov     [rsp+58h+var_28], eax
0x180003948  test    eax, eax
0x18000394a  jz      loc_1800039E3
0x180003950  mov     r8, rsi
0x180003953  mov     edx, edi
0x180003955  mov     rcx, r14
0x180003958  call    _get_startup_argv_mode
0x18000395d  mov     ebx, eax
0x18000395f  mov     [rsp+58h+var_28], eax
0x180003963  cmp     edi, 1
0x180003966  jnz     short loc_18000399F
0x180003968  test    eax, eax
0x18000396a  jnz     short loc_18000399F
0x18000396c  mov     r8, rsi
0x18000396f  xor     edx, edx
0x180003971  mov     rcx, r14
0x180003974  call    _get_startup_argv_mode
0x180003979  mov     r8, rsi
0x18000397c  xor     edx, edx
0x18000397e  mov     rcx, r14
0x180003981  call    dllmain_crt_dispatch
0x180003986  mov     rax, cs:_pRawDllMain
0x18000398d  test    rax, rax
0x180003990  jz      short loc_18000399F
0x180003992  mov     r8, rsi
0x180003995  xor     edx, edx
0x180003997  mov     rcx, r14
0x18000399a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000399f  test    edi, edi
0x1800039a1  jz      short loc_1800039A8
0x1800039a3  cmp     edi, 3
0x1800039a6  jnz     short loc_1800039E3
0x1800039a8  mov     r8, rsi
0x1800039ab  mov     edx, edi
0x1800039ad  mov     rcx, r14
0x1800039b0  call    dllmain_crt_dispatch
0x1800039b5  mov     ebx, eax
0x1800039b7  mov     [rsp+58h+var_28], eax
0x1800039bb  test    eax, eax
0x1800039bd  jz      short loc_1800039E3
0x1800039bf  mov     rax, cs:_pRawDllMain
0x1800039c6  test    rax, rax
0x1800039c9  jnz     short loc_1800039D0
0x1800039cb  lea     ebx, [rax+1]
0x1800039ce  jmp     short loc_1800039DF
0x1800039d0  mov     r8, rsi
0x1800039d3  mov     edx, edi
0x1800039d5  mov     rcx, r14
0x1800039d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039dd  mov     ebx, eax
0x1800039df  mov     [rsp+58h+var_28], ebx
0x1800039e3  jmp     short loc_1800039EB
0x1800039e5  xor     ebx, ebx
0x1800039e7  mov     [rsp+58h+var_28], ebx
0x1800039eb  mov     eax, ebx
0x1800039ed  mov     rbx, [rsp+58h+arg_18]
0x1800039f2  add     rsp, 40h
0x1800039f6  pop     r14
0x1800039f8  pop     rdi
0x1800039f9  pop     rsi
0x1800039fa  retn
0x180027a3c  push    rbp
0x180027a3e  sub     rsp, 30h
0x180027a42  mov     rbp, rdx
0x180027a45  mov     rax, [rcx]
0x180027a48  mov     edx, [rax]
0x180027a4a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180027a4f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180027a53  lea     r9, dllmain_crt_dispatch; int
0x180027a5a  mov     r8, [rbp+70h]; int
0x180027a5e  mov     edx, [rbp+68h]; int
0x180027a61  mov     rcx, [rbp+60h]; int
0x180027a65  call    __scrt_dllmain_exception_filter
0x180027a6a  nop
0x180027a6b  add     rsp, 30h
0x180027a6f  pop     rbp
0x180027a70  retn
```
