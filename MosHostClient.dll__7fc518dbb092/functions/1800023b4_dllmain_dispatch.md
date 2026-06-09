# dllmain_dispatch

- ea: `0x1800023b4`
- end: `0x1800024db`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800024f0`

## callees

- `0x1800021d0`
- `0x1800023b4`
- `0x18000264c`
- `0x180007368`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001C530 <= 0 )
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
0x1800023b4  mov     rax, rsp
0x1800023b7  mov     [rax+20h], rbx
0x1800023bb  mov     [rax+18h], r8
0x1800023bf  mov     [rax+10h], edx
0x1800023c2  mov     [rax+8], rcx
0x1800023c6  push    rsi
0x1800023c7  push    rdi
0x1800023c8  push    r14
0x1800023ca  sub     rsp, 40h
0x1800023ce  mov     rsi, r8
0x1800023d1  mov     edi, edx
0x1800023d3  mov     r14, rcx
0x1800023d6  test    edx, edx
0x1800023d8  jnz     short loc_1800023E9
0x1800023da  cmp     cs:dword_18001C530, edx
0x1800023e0  jg      short loc_1800023E9
0x1800023e2  xor     eax, eax
0x1800023e4  jmp     loc_1800024CD
0x1800023e9  lea     eax, [rdx-1]
0x1800023ec  cmp     eax, 1
0x1800023ef  ja      short loc_180002430
0x1800023f1  mov     rax, cs:_pRawDllMain
0x1800023f8  test    rax, rax
0x1800023fb  jnz     short loc_180002402
0x1800023fd  lea     ebx, [rax+1]
0x180002400  jmp     short loc_180002409
0x180002402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002407  mov     ebx, eax
0x180002409  mov     [rsp+58h+var_28], ebx
0x18000240d  test    ebx, ebx
0x18000240f  jz      loc_1800024C3
0x180002415  mov     r8, rsi
0x180002418  mov     edx, edi
0x18000241a  mov     rcx, r14
0x18000241d  call    dllmain_crt_dispatch
0x180002422  mov     ebx, eax
0x180002424  mov     [rsp+58h+var_28], eax
0x180002428  test    eax, eax
0x18000242a  jz      loc_1800024C3
0x180002430  mov     r8, rsi; lpvReserved
0x180002433  mov     edx, edi; fdwReason
0x180002435  mov     rcx, r14; hinstDLL
0x180002438  call    DllMain
0x18000243d  mov     ebx, eax
0x18000243f  mov     [rsp+58h+var_28], eax
0x180002443  cmp     edi, 1
0x180002446  jnz     short loc_18000247F
0x180002448  test    eax, eax
0x18000244a  jnz     short loc_18000247F
0x18000244c  mov     r8, rsi; lpvReserved
0x18000244f  xor     edx, edx; fdwReason
0x180002451  mov     rcx, r14; hinstDLL
0x180002454  call    DllMain
0x180002459  mov     r8, rsi
0x18000245c  xor     edx, edx
0x18000245e  mov     rcx, r14
0x180002461  call    dllmain_crt_dispatch
0x180002466  mov     rax, cs:_pRawDllMain
0x18000246d  test    rax, rax
0x180002470  jz      short loc_18000247F
0x180002472  mov     r8, rsi
0x180002475  xor     edx, edx
0x180002477  mov     rcx, r14
0x18000247a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247f  test    edi, edi
0x180002481  jz      short loc_180002488
0x180002483  cmp     edi, 3
0x180002486  jnz     short loc_1800024C3
0x180002488  mov     r8, rsi
0x18000248b  mov     edx, edi
0x18000248d  mov     rcx, r14
0x180002490  call    dllmain_crt_dispatch
0x180002495  mov     ebx, eax
0x180002497  mov     [rsp+58h+var_28], eax
0x18000249b  test    eax, eax
0x18000249d  jz      short loc_1800024C3
0x18000249f  mov     rax, cs:_pRawDllMain
0x1800024a6  test    rax, rax
0x1800024a9  jnz     short loc_1800024B0
0x1800024ab  lea     ebx, [rax+1]
0x1800024ae  jmp     short loc_1800024BF
0x1800024b0  mov     r8, rsi
0x1800024b3  mov     edx, edi
0x1800024b5  mov     rcx, r14
0x1800024b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bd  mov     ebx, eax
0x1800024bf  mov     [rsp+58h+var_28], ebx
0x1800024c3  jmp     short loc_1800024CB
0x1800024c5  xor     ebx, ebx
0x1800024c7  mov     [rsp+58h+var_28], ebx
0x1800024cb  mov     eax, ebx
0x1800024cd  mov     rbx, [rsp+58h+arg_18]
0x1800024d2  add     rsp, 40h
0x1800024d6  pop     r14
0x1800024d8  pop     rdi
0x1800024d9  pop     rsi
0x1800024da  retn
0x18001116c  push    rbp
0x18001116e  sub     rsp, 30h
0x180011172  mov     rbp, rdx
0x180011175  mov     rax, [rcx]
0x180011178  mov     edx, [rax]
0x18001117a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001117f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180011183  lea     r9, dllmain_crt_dispatch; int
0x18001118a  mov     r8, [rbp+70h]; int
0x18001118e  mov     edx, [rbp+68h]; int
0x180011191  mov     rcx, [rbp+60h]; int
0x180011195  call    __scrt_dllmain_exception_filter
0x18001119a  nop
0x18001119b  add     rsp, 30h
0x18001119f  pop     rbp
0x1800111a0  retn
```
