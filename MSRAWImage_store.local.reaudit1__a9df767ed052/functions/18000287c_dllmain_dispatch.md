# dllmain_dispatch

- ea: `0x18000287c`
- end: `0x1800029a3`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800029b0`

## callees

- `0x180002680`
- `0x18000287c`
- `0x180002b2c`
- `0x180096f28`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180126240 <= 0 )
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
0x18000287c  mov     rax, rsp
0x18000287f  mov     [rax+20h], rbx
0x180002883  mov     [rax+18h], r8
0x180002887  mov     [rax+10h], edx
0x18000288a  mov     [rax+8], rcx
0x18000288e  push    rsi
0x18000288f  push    rdi
0x180002890  push    r14
0x180002892  sub     rsp, 40h
0x180002896  mov     rsi, r8
0x180002899  mov     edi, edx
0x18000289b  mov     r14, rcx
0x18000289e  test    edx, edx
0x1800028a0  jnz     short loc_1800028B1
0x1800028a2  cmp     cs:dword_180126240, edx
0x1800028a8  jg      short loc_1800028B1
0x1800028aa  xor     eax, eax
0x1800028ac  jmp     loc_180002995
0x1800028b1  lea     eax, [rdx-1]
0x1800028b4  cmp     eax, 1
0x1800028b7  ja      short loc_1800028F8
0x1800028b9  mov     rax, cs:_pRawDllMain
0x1800028c0  test    rax, rax
0x1800028c3  jnz     short loc_1800028CA
0x1800028c5  lea     ebx, [rax+1]
0x1800028c8  jmp     short loc_1800028D1
0x1800028ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cf  mov     ebx, eax
0x1800028d1  mov     [rsp+58h+var_28], ebx
0x1800028d5  test    ebx, ebx
0x1800028d7  jz      loc_18000298B
0x1800028dd  mov     r8, rsi
0x1800028e0  mov     edx, edi
0x1800028e2  mov     rcx, r14
0x1800028e5  call    dllmain_crt_dispatch
0x1800028ea  mov     ebx, eax
0x1800028ec  mov     [rsp+58h+var_28], eax
0x1800028f0  test    eax, eax
0x1800028f2  jz      loc_18000298B
0x1800028f8  mov     r8, rsi; lpvReserved
0x1800028fb  mov     edx, edi; fdwReason
0x1800028fd  mov     rcx, r14; hinstDLL
0x180002900  call    DllMain
0x180002905  mov     ebx, eax
0x180002907  mov     [rsp+58h+var_28], eax
0x18000290b  cmp     edi, 1
0x18000290e  jnz     short loc_180002947
0x180002910  test    eax, eax
0x180002912  jnz     short loc_180002947
0x180002914  mov     r8, rsi; lpvReserved
0x180002917  xor     edx, edx; fdwReason
0x180002919  mov     rcx, r14; hinstDLL
0x18000291c  call    DllMain
0x180002921  mov     r8, rsi
0x180002924  xor     edx, edx
0x180002926  mov     rcx, r14
0x180002929  call    dllmain_crt_dispatch
0x18000292e  mov     rax, cs:_pRawDllMain
0x180002935  test    rax, rax
0x180002938  jz      short loc_180002947
0x18000293a  mov     r8, rsi
0x18000293d  xor     edx, edx
0x18000293f  mov     rcx, r14
0x180002942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002947  test    edi, edi
0x180002949  jz      short loc_180002950
0x18000294b  cmp     edi, 3
0x18000294e  jnz     short loc_18000298B
0x180002950  mov     r8, rsi
0x180002953  mov     edx, edi
0x180002955  mov     rcx, r14
0x180002958  call    dllmain_crt_dispatch
0x18000295d  mov     ebx, eax
0x18000295f  mov     [rsp+58h+var_28], eax
0x180002963  test    eax, eax
0x180002965  jz      short loc_18000298B
0x180002967  mov     rax, cs:_pRawDllMain
0x18000296e  test    rax, rax
0x180002971  jnz     short loc_180002978
0x180002973  lea     ebx, [rax+1]
0x180002976  jmp     short loc_180002987
0x180002978  mov     r8, rsi
0x18000297b  mov     edx, edi
0x18000297d  mov     rcx, r14
0x180002980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002985  mov     ebx, eax
0x180002987  mov     [rsp+58h+var_28], ebx
0x18000298b  jmp     short loc_180002993
0x18000298d  xor     ebx, ebx
0x18000298f  mov     [rsp+58h+var_28], ebx
0x180002993  mov     eax, ebx
0x180002995  mov     rbx, [rsp+58h+arg_18]
0x18000299a  add     rsp, 40h
0x18000299e  pop     r14
0x1800029a0  pop     rdi
0x1800029a1  pop     rsi
0x1800029a2  retn
0x1800b10e2  push    rbp
0x1800b10e4  sub     rsp, 30h
0x1800b10e8  mov     rbp, rdx
0x1800b10eb  mov     rax, [rcx]
0x1800b10ee  mov     edx, [rax]
0x1800b10f0  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800b10f5  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800b10f9  lea     r9, dllmain_crt_dispatch; int
0x1800b1100  mov     r8, [rbp+70h]; int
0x1800b1104  mov     edx, [rbp+68h]; int
0x1800b1107  mov     rcx, [rbp+60h]; int
0x1800b110b  call    __scrt_dllmain_exception_filter
0x1800b1110  nop
0x1800b1111  add     rsp, 30h
0x1800b1115  pop     rbp
0x1800b1116  retn
```
