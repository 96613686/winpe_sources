# dllmain_dispatch

- ea: `0x180003274`
- end: `0x18000339b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800033b0`

## callees

- `0x180003090`
- `0x180003274`
- `0x180003518`
- `0x18000b300`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800353D0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain(hinstDLL, fdwReason, lpvReserved);
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
0x180003274  mov     rax, rsp
0x180003277  mov     [rax+20h], rbx
0x18000327b  mov     [rax+18h], r8
0x18000327f  mov     [rax+10h], edx
0x180003282  mov     [rax+8], rcx
0x180003286  push    rsi
0x180003287  push    rdi
0x180003288  push    r14
0x18000328a  sub     rsp, 40h
0x18000328e  mov     rsi, r8
0x180003291  mov     edi, edx
0x180003293  mov     r14, rcx
0x180003296  test    edx, edx
0x180003298  jnz     short loc_1800032A9
0x18000329a  cmp     cs:dword_1800353D0, edx
0x1800032a0  jg      short loc_1800032A9
0x1800032a2  xor     eax, eax
0x1800032a4  jmp     loc_18000338D
0x1800032a9  lea     eax, [rdx-1]
0x1800032ac  cmp     eax, 1
0x1800032af  ja      short loc_1800032F0
0x1800032b1  mov     rax, cs:_pRawDllMain
0x1800032b8  test    rax, rax
0x1800032bb  jnz     short loc_1800032C2
0x1800032bd  lea     ebx, [rax+1]
0x1800032c0  jmp     short loc_1800032C9
0x1800032c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032c7  mov     ebx, eax
0x1800032c9  mov     [rsp+58h+var_28], ebx
0x1800032cd  test    ebx, ebx
0x1800032cf  jz      loc_180003383
0x1800032d5  mov     r8, rsi
0x1800032d8  mov     edx, edi
0x1800032da  mov     rcx, r14
0x1800032dd  call    dllmain_crt_dispatch
0x1800032e2  mov     ebx, eax
0x1800032e4  mov     [rsp+58h+var_28], eax
0x1800032e8  test    eax, eax
0x1800032ea  jz      loc_180003383
0x1800032f0  mov     r8, rsi; lpvReserved
0x1800032f3  mov     edx, edi; fdwReason
0x1800032f5  mov     rcx, r14; hinstDLL
0x1800032f8  call    DllMain
0x1800032fd  mov     ebx, eax
0x1800032ff  mov     [rsp+58h+var_28], eax
0x180003303  cmp     edi, 1
0x180003306  jnz     short loc_18000333F
0x180003308  test    eax, eax
0x18000330a  jnz     short loc_18000333F
0x18000330c  mov     r8, rsi; lpvReserved
0x18000330f  xor     edx, edx; fdwReason
0x180003311  mov     rcx, r14; hinstDLL
0x180003314  call    DllMain
0x180003319  mov     r8, rsi
0x18000331c  xor     edx, edx
0x18000331e  mov     rcx, r14
0x180003321  call    dllmain_crt_dispatch
0x180003326  mov     rax, cs:_pRawDllMain
0x18000332d  test    rax, rax
0x180003330  jz      short loc_18000333F
0x180003332  mov     r8, rsi
0x180003335  xor     edx, edx
0x180003337  mov     rcx, r14
0x18000333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333f  test    edi, edi
0x180003341  jz      short loc_180003348
0x180003343  cmp     edi, 3
0x180003346  jnz     short loc_180003383
0x180003348  mov     r8, rsi
0x18000334b  mov     edx, edi
0x18000334d  mov     rcx, r14
0x180003350  call    dllmain_crt_dispatch
0x180003355  mov     ebx, eax
0x180003357  mov     [rsp+58h+var_28], eax
0x18000335b  test    eax, eax
0x18000335d  jz      short loc_180003383
0x18000335f  mov     rax, cs:_pRawDllMain
0x180003366  test    rax, rax
0x180003369  jnz     short loc_180003370
0x18000336b  lea     ebx, [rax+1]
0x18000336e  jmp     short loc_18000337F
0x180003370  mov     r8, rsi
0x180003373  mov     edx, edi
0x180003375  mov     rcx, r14
0x180003378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000337d  mov     ebx, eax
0x18000337f  mov     [rsp+58h+var_28], ebx
0x180003383  jmp     short loc_18000338B
0x180003385  xor     ebx, ebx
0x180003387  mov     [rsp+58h+var_28], ebx
0x18000338b  mov     eax, ebx
0x18000338d  mov     rbx, [rsp+58h+arg_18]
0x180003392  add     rsp, 40h
0x180003396  pop     r14
0x180003398  pop     rdi
0x180003399  pop     rsi
0x18000339a  retn
0x180022ffc  push    rbp
0x180022ffe  sub     rsp, 30h
0x180023002  mov     rbp, rdx
0x180023005  mov     rax, [rcx]
0x180023008  mov     edx, [rax]
0x18002300a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002300f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180023013  lea     r9, dllmain_crt_dispatch; int
0x18002301a  mov     r8, [rbp+70h]; int
0x18002301e  mov     edx, [rbp+68h]; int
0x180023021  mov     rcx, [rbp+60h]; int
0x180023025  call    __scrt_dllmain_exception_filter
0x18002302a  nop
0x18002302b  add     rsp, 30h
0x18002302f  pop     rbp
0x180023030  retn
```
