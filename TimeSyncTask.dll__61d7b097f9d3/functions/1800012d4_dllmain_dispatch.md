# dllmain_dispatch

- ea: `0x1800012d4`
- end: `0x1800013fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001410`

## callees

- `0x1800010f0`
- `0x1800012d4`
- `0x180001670`
- `0x180002e18`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180007090 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x1800012d4  mov     rax, rsp
0x1800012d7  mov     [rax+20h], rbx
0x1800012db  mov     [rax+18h], r8
0x1800012df  mov     [rax+10h], edx
0x1800012e2  mov     [rax+8], rcx
0x1800012e6  push    rsi
0x1800012e7  push    rdi
0x1800012e8  push    r14
0x1800012ea  sub     rsp, 40h
0x1800012ee  mov     rsi, r8
0x1800012f1  mov     edi, edx
0x1800012f3  mov     r14, rcx
0x1800012f6  test    edx, edx
0x1800012f8  jnz     short loc_180001309
0x1800012fa  cmp     cs:dword_180007090, edx
0x180001300  jg      short loc_180001309
0x180001302  xor     eax, eax
0x180001304  jmp     loc_1800013ED
0x180001309  lea     eax, [rdx-1]
0x18000130c  cmp     eax, 1
0x18000130f  ja      short loc_180001350
0x180001311  mov     rax, cs:_pRawDllMain
0x180001318  test    rax, rax
0x18000131b  jnz     short loc_180001322
0x18000131d  lea     ebx, [rax+1]
0x180001320  jmp     short loc_180001329
0x180001322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001327  mov     ebx, eax
0x180001329  mov     [rsp+58h+var_28], ebx
0x18000132d  test    ebx, ebx
0x18000132f  jz      loc_1800013E3
0x180001335  mov     r8, rsi
0x180001338  mov     edx, edi
0x18000133a  mov     rcx, r14
0x18000133d  call    dllmain_crt_dispatch
0x180001342  mov     ebx, eax
0x180001344  mov     [rsp+58h+var_28], eax
0x180001348  test    eax, eax
0x18000134a  jz      loc_1800013E3
0x180001350  mov     r8, rsi; lpvReserved
0x180001353  mov     edx, edi; fdwReason
0x180001355  mov     rcx, r14; hinstDLL
0x180001358  call    DllMain
0x18000135d  mov     ebx, eax
0x18000135f  mov     [rsp+58h+var_28], eax
0x180001363  cmp     edi, 1
0x180001366  jnz     short loc_18000139F
0x180001368  test    eax, eax
0x18000136a  jnz     short loc_18000139F
0x18000136c  mov     r8, rsi; lpvReserved
0x18000136f  xor     edx, edx; fdwReason
0x180001371  mov     rcx, r14; hinstDLL
0x180001374  call    DllMain
0x180001379  mov     r8, rsi
0x18000137c  xor     edx, edx
0x18000137e  mov     rcx, r14
0x180001381  call    dllmain_crt_dispatch
0x180001386  mov     rax, cs:_pRawDllMain
0x18000138d  test    rax, rax
0x180001390  jz      short loc_18000139F
0x180001392  mov     r8, rsi
0x180001395  xor     edx, edx
0x180001397  mov     rcx, r14
0x18000139a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000139f  test    edi, edi
0x1800013a1  jz      short loc_1800013A8
0x1800013a3  cmp     edi, 3
0x1800013a6  jnz     short loc_1800013E3
0x1800013a8  mov     r8, rsi
0x1800013ab  mov     edx, edi
0x1800013ad  mov     rcx, r14
0x1800013b0  call    dllmain_crt_dispatch
0x1800013b5  mov     ebx, eax
0x1800013b7  mov     [rsp+58h+var_28], eax
0x1800013bb  test    eax, eax
0x1800013bd  jz      short loc_1800013E3
0x1800013bf  mov     rax, cs:_pRawDllMain
0x1800013c6  test    rax, rax
0x1800013c9  jnz     short loc_1800013D0
0x1800013cb  lea     ebx, [rax+1]
0x1800013ce  jmp     short loc_1800013DF
0x1800013d0  mov     r8, rsi
0x1800013d3  mov     edx, edi
0x1800013d5  mov     rcx, r14
0x1800013d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013dd  mov     ebx, eax
0x1800013df  mov     [rsp+58h+var_28], ebx
0x1800013e3  jmp     short loc_1800013EB
0x1800013e5  xor     ebx, ebx
0x1800013e7  mov     [rsp+58h+var_28], ebx
0x1800013eb  mov     eax, ebx
0x1800013ed  mov     rbx, [rsp+58h+arg_18]
0x1800013f2  add     rsp, 40h
0x1800013f6  pop     r14
0x1800013f8  pop     rdi
0x1800013f9  pop     rsi
0x1800013fa  retn
0x18000319c  push    rbp
0x18000319e  sub     rsp, 30h
0x1800031a2  mov     rbp, rdx
0x1800031a5  mov     rax, [rcx]
0x1800031a8  mov     edx, [rax]
0x1800031aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800031af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800031b3  lea     r9, dllmain_crt_dispatch; int
0x1800031ba  mov     r8, [rbp+70h]; int
0x1800031be  mov     edx, [rbp+68h]; int
0x1800031c1  mov     rcx, [rbp+60h]; int
0x1800031c5  call    __scrt_dllmain_exception_filter
0x1800031ca  nop
0x1800031cb  add     rsp, 30h
0x1800031cf  pop     rbp
0x1800031d0  retn
```
