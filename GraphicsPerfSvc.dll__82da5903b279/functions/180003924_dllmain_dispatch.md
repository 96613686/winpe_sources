# dllmain_dispatch

- ea: `0x180003924`
- end: `0x180003a4b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003a60`

## callees

- `0x180003740`
- `0x180003924`
- `0x180003bac`
- `0x18000d990`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800427F0 <= 0 )
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
0x180003924  mov     rax, rsp
0x180003927  mov     [rax+20h], rbx
0x18000392b  mov     [rax+18h], r8
0x18000392f  mov     [rax+10h], edx
0x180003932  mov     [rax+8], rcx
0x180003936  push    rsi
0x180003937  push    rdi
0x180003938  push    r14
0x18000393a  sub     rsp, 40h
0x18000393e  mov     rsi, r8
0x180003941  mov     edi, edx
0x180003943  mov     r14, rcx
0x180003946  test    edx, edx
0x180003948  jnz     short loc_180003959
0x18000394a  cmp     cs:dword_1800427F0, edx
0x180003950  jg      short loc_180003959
0x180003952  xor     eax, eax
0x180003954  jmp     loc_180003A3D
0x180003959  lea     eax, [rdx-1]
0x18000395c  cmp     eax, 1
0x18000395f  ja      short loc_1800039A0
0x180003961  mov     rax, cs:_pRawDllMain
0x180003968  test    rax, rax
0x18000396b  jnz     short loc_180003972
0x18000396d  lea     ebx, [rax+1]
0x180003970  jmp     short loc_180003979
0x180003972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003977  mov     ebx, eax
0x180003979  mov     [rsp+58h+var_28], ebx
0x18000397d  test    ebx, ebx
0x18000397f  jz      loc_180003A33
0x180003985  mov     r8, rsi
0x180003988  mov     edx, edi
0x18000398a  mov     rcx, r14
0x18000398d  call    dllmain_crt_dispatch
0x180003992  mov     ebx, eax
0x180003994  mov     [rsp+58h+var_28], eax
0x180003998  test    eax, eax
0x18000399a  jz      loc_180003A33
0x1800039a0  mov     r8, rsi; lpvReserved
0x1800039a3  mov     edx, edi; fdwReason
0x1800039a5  mov     rcx, r14; hinstDLL
0x1800039a8  call    DllMain
0x1800039ad  mov     ebx, eax
0x1800039af  mov     [rsp+58h+var_28], eax
0x1800039b3  cmp     edi, 1
0x1800039b6  jnz     short loc_1800039EF
0x1800039b8  test    eax, eax
0x1800039ba  jnz     short loc_1800039EF
0x1800039bc  mov     r8, rsi; lpvReserved
0x1800039bf  xor     edx, edx; fdwReason
0x1800039c1  mov     rcx, r14; hinstDLL
0x1800039c4  call    DllMain
0x1800039c9  mov     r8, rsi
0x1800039cc  xor     edx, edx
0x1800039ce  mov     rcx, r14
0x1800039d1  call    dllmain_crt_dispatch
0x1800039d6  mov     rax, cs:_pRawDllMain
0x1800039dd  test    rax, rax
0x1800039e0  jz      short loc_1800039EF
0x1800039e2  mov     r8, rsi
0x1800039e5  xor     edx, edx
0x1800039e7  mov     rcx, r14
0x1800039ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ef  test    edi, edi
0x1800039f1  jz      short loc_1800039F8
0x1800039f3  cmp     edi, 3
0x1800039f6  jnz     short loc_180003A33
0x1800039f8  mov     r8, rsi
0x1800039fb  mov     edx, edi
0x1800039fd  mov     rcx, r14
0x180003a00  call    dllmain_crt_dispatch
0x180003a05  mov     ebx, eax
0x180003a07  mov     [rsp+58h+var_28], eax
0x180003a0b  test    eax, eax
0x180003a0d  jz      short loc_180003A33
0x180003a0f  mov     rax, cs:_pRawDllMain
0x180003a16  test    rax, rax
0x180003a19  jnz     short loc_180003A20
0x180003a1b  lea     ebx, [rax+1]
0x180003a1e  jmp     short loc_180003A2F
0x180003a20  mov     r8, rsi
0x180003a23  mov     edx, edi
0x180003a25  mov     rcx, r14
0x180003a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a2d  mov     ebx, eax
0x180003a2f  mov     [rsp+58h+var_28], ebx
0x180003a33  jmp     short loc_180003A3B
0x180003a35  xor     ebx, ebx
0x180003a37  mov     [rsp+58h+var_28], ebx
0x180003a3b  mov     eax, ebx
0x180003a3d  mov     rbx, [rsp+58h+arg_18]
0x180003a42  add     rsp, 40h
0x180003a46  pop     r14
0x180003a48  pop     rdi
0x180003a49  pop     rsi
0x180003a4a  retn
0x18002f1dc  push    rbp
0x18002f1de  sub     rsp, 30h
0x18002f1e2  mov     rbp, rdx
0x18002f1e5  mov     rax, [rcx]
0x18002f1e8  mov     edx, [rax]
0x18002f1ea  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002f1ef  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002f1f3  lea     r9, dllmain_crt_dispatch; int
0x18002f1fa  mov     r8, [rbp+70h]; int
0x18002f1fe  mov     edx, [rbp+68h]; int
0x18002f201  mov     rcx, [rbp+60h]; int
0x18002f205  call    __scrt_dllmain_exception_filter
0x18002f20a  nop
0x18002f20b  add     rsp, 30h
0x18002f20f  pop     rbp
0x18002f210  retn
```
