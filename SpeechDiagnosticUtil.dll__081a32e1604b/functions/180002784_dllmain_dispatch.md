# dllmain_dispatch

- ea: `0x180002784`
- end: `0x1800028ab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800028c0`

## callees

- `0x1800025a0`
- `0x180002784`
- `0x180002a0c`
- `0x180006ce0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800181F0 <= 0 )
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
0x180002784  mov     rax, rsp
0x180002787  mov     [rax+20h], rbx
0x18000278b  mov     [rax+18h], r8
0x18000278f  mov     [rax+10h], edx
0x180002792  mov     [rax+8], rcx
0x180002796  push    rsi
0x180002797  push    rdi
0x180002798  push    r14
0x18000279a  sub     rsp, 40h
0x18000279e  mov     rsi, r8
0x1800027a1  mov     edi, edx
0x1800027a3  mov     r14, rcx
0x1800027a6  test    edx, edx
0x1800027a8  jnz     short loc_1800027B9
0x1800027aa  cmp     cs:dword_1800181F0, edx
0x1800027b0  jg      short loc_1800027B9
0x1800027b2  xor     eax, eax
0x1800027b4  jmp     loc_18000289D
0x1800027b9  lea     eax, [rdx-1]
0x1800027bc  cmp     eax, 1
0x1800027bf  ja      short loc_180002800
0x1800027c1  mov     rax, cs:_pRawDllMain
0x1800027c8  test    rax, rax
0x1800027cb  jnz     short loc_1800027D2
0x1800027cd  lea     ebx, [rax+1]
0x1800027d0  jmp     short loc_1800027D9
0x1800027d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d7  mov     ebx, eax
0x1800027d9  mov     [rsp+58h+var_28], ebx
0x1800027dd  test    ebx, ebx
0x1800027df  jz      loc_180002893
0x1800027e5  mov     r8, rsi
0x1800027e8  mov     edx, edi
0x1800027ea  mov     rcx, r14
0x1800027ed  call    dllmain_crt_dispatch
0x1800027f2  mov     ebx, eax
0x1800027f4  mov     [rsp+58h+var_28], eax
0x1800027f8  test    eax, eax
0x1800027fa  jz      loc_180002893
0x180002800  mov     r8, rsi; lpvReserved
0x180002803  mov     edx, edi; fdwReason
0x180002805  mov     rcx, r14; hinstDLL
0x180002808  call    DllMain
0x18000280d  mov     ebx, eax
0x18000280f  mov     [rsp+58h+var_28], eax
0x180002813  cmp     edi, 1
0x180002816  jnz     short loc_18000284F
0x180002818  test    eax, eax
0x18000281a  jnz     short loc_18000284F
0x18000281c  mov     r8, rsi; lpvReserved
0x18000281f  xor     edx, edx; fdwReason
0x180002821  mov     rcx, r14; hinstDLL
0x180002824  call    DllMain
0x180002829  mov     r8, rsi
0x18000282c  xor     edx, edx
0x18000282e  mov     rcx, r14
0x180002831  call    dllmain_crt_dispatch
0x180002836  mov     rax, cs:_pRawDllMain
0x18000283d  test    rax, rax
0x180002840  jz      short loc_18000284F
0x180002842  mov     r8, rsi
0x180002845  xor     edx, edx
0x180002847  mov     rcx, r14
0x18000284a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000284f  test    edi, edi
0x180002851  jz      short loc_180002858
0x180002853  cmp     edi, 3
0x180002856  jnz     short loc_180002893
0x180002858  mov     r8, rsi
0x18000285b  mov     edx, edi
0x18000285d  mov     rcx, r14
0x180002860  call    dllmain_crt_dispatch
0x180002865  mov     ebx, eax
0x180002867  mov     [rsp+58h+var_28], eax
0x18000286b  test    eax, eax
0x18000286d  jz      short loc_180002893
0x18000286f  mov     rax, cs:_pRawDllMain
0x180002876  test    rax, rax
0x180002879  jnz     short loc_180002880
0x18000287b  lea     ebx, [rax+1]
0x18000287e  jmp     short loc_18000288F
0x180002880  mov     r8, rsi
0x180002883  mov     edx, edi
0x180002885  mov     rcx, r14
0x180002888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288d  mov     ebx, eax
0x18000288f  mov     [rsp+58h+var_28], ebx
0x180002893  jmp     short loc_18000289B
0x180002895  xor     ebx, ebx
0x180002897  mov     [rsp+58h+var_28], ebx
0x18000289b  mov     eax, ebx
0x18000289d  mov     rbx, [rsp+58h+arg_18]
0x1800028a2  add     rsp, 40h
0x1800028a6  pop     r14
0x1800028a8  pop     rdi
0x1800028a9  pop     rsi
0x1800028aa  retn
0x18001063c  push    rbp
0x18001063e  sub     rsp, 30h
0x180010642  mov     rbp, rdx
0x180010645  mov     rax, [rcx]
0x180010648  mov     edx, [rax]
0x18001064a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001064f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180010653  lea     r9, dllmain_crt_dispatch; int
0x18001065a  mov     r8, [rbp+70h]; int
0x18001065e  mov     edx, [rbp+68h]; int
0x180010661  mov     rcx, [rbp+60h]; int
0x180010665  call    __scrt_dllmain_exception_filter
0x18001066a  nop
0x18001066b  add     rsp, 30h
0x18001066f  pop     rbp
0x180010670  retn
```
