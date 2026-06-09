# dllmain_dispatch

- ea: `0x180002764`
- end: `0x18000288b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800028a0`

## callees

- `0x180002580`
- `0x180002764`
- `0x1800029ec`
- `0x180002eb0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18003AAF0 <= 0 )
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
0x180002764  mov     rax, rsp
0x180002767  mov     [rax+20h], rbx
0x18000276b  mov     [rax+18h], r8
0x18000276f  mov     [rax+10h], edx
0x180002772  mov     [rax+8], rcx
0x180002776  push    rsi
0x180002777  push    rdi
0x180002778  push    r14
0x18000277a  sub     rsp, 40h
0x18000277e  mov     rsi, r8
0x180002781  mov     edi, edx
0x180002783  mov     r14, rcx
0x180002786  test    edx, edx
0x180002788  jnz     short loc_180002799
0x18000278a  cmp     cs:dword_18003AAF0, edx
0x180002790  jg      short loc_180002799
0x180002792  xor     eax, eax
0x180002794  jmp     loc_18000287D
0x180002799  lea     eax, [rdx-1]
0x18000279c  cmp     eax, 1
0x18000279f  ja      short loc_1800027E0
0x1800027a1  mov     rax, cs:_pRawDllMain
0x1800027a8  test    rax, rax
0x1800027ab  jnz     short loc_1800027B2
0x1800027ad  lea     ebx, [rax+1]
0x1800027b0  jmp     short loc_1800027B9
0x1800027b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b7  mov     ebx, eax
0x1800027b9  mov     [rsp+58h+var_28], ebx
0x1800027bd  test    ebx, ebx
0x1800027bf  jz      loc_180002873
0x1800027c5  mov     r8, rsi
0x1800027c8  mov     edx, edi
0x1800027ca  mov     rcx, r14
0x1800027cd  call    dllmain_crt_dispatch
0x1800027d2  mov     ebx, eax
0x1800027d4  mov     [rsp+58h+var_28], eax
0x1800027d8  test    eax, eax
0x1800027da  jz      loc_180002873
0x1800027e0  mov     r8, rsi; lpvReserved
0x1800027e3  mov     edx, edi; fdwReason
0x1800027e5  mov     rcx, r14; hinstDLL
0x1800027e8  call    DllMain
0x1800027ed  mov     ebx, eax
0x1800027ef  mov     [rsp+58h+var_28], eax
0x1800027f3  cmp     edi, 1
0x1800027f6  jnz     short loc_18000282F
0x1800027f8  test    eax, eax
0x1800027fa  jnz     short loc_18000282F
0x1800027fc  mov     r8, rsi; lpvReserved
0x1800027ff  xor     edx, edx; fdwReason
0x180002801  mov     rcx, r14; hinstDLL
0x180002804  call    DllMain
0x180002809  mov     r8, rsi
0x18000280c  xor     edx, edx
0x18000280e  mov     rcx, r14
0x180002811  call    dllmain_crt_dispatch
0x180002816  mov     rax, cs:_pRawDllMain
0x18000281d  test    rax, rax
0x180002820  jz      short loc_18000282F
0x180002822  mov     r8, rsi
0x180002825  xor     edx, edx
0x180002827  mov     rcx, r14
0x18000282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282f  test    edi, edi
0x180002831  jz      short loc_180002838
0x180002833  cmp     edi, 3
0x180002836  jnz     short loc_180002873
0x180002838  mov     r8, rsi
0x18000283b  mov     edx, edi
0x18000283d  mov     rcx, r14
0x180002840  call    dllmain_crt_dispatch
0x180002845  mov     ebx, eax
0x180002847  mov     [rsp+58h+var_28], eax
0x18000284b  test    eax, eax
0x18000284d  jz      short loc_180002873
0x18000284f  mov     rax, cs:_pRawDllMain
0x180002856  test    rax, rax
0x180002859  jnz     short loc_180002860
0x18000285b  lea     ebx, [rax+1]
0x18000285e  jmp     short loc_18000286F
0x180002860  mov     r8, rsi
0x180002863  mov     edx, edi
0x180002865  mov     rcx, r14
0x180002868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286d  mov     ebx, eax
0x18000286f  mov     [rsp+58h+var_28], ebx
0x180002873  jmp     short loc_18000287B
0x180002875  xor     ebx, ebx
0x180002877  mov     [rsp+58h+var_28], ebx
0x18000287b  mov     eax, ebx
0x18000287d  mov     rbx, [rsp+58h+arg_18]
0x180002882  add     rsp, 40h
0x180002886  pop     r14
0x180002888  pop     rdi
0x180002889  pop     rsi
0x18000288a  retn
0x180027710  push    rbp
0x180027712  sub     rsp, 30h
0x180027716  mov     rbp, rdx
0x180027719  mov     rax, [rcx]
0x18002771c  mov     edx, [rax]
0x18002771e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180027723  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180027727  lea     r9, dllmain_crt_dispatch; int
0x18002772e  mov     r8, [rbp+70h]; int
0x180027732  mov     edx, [rbp+68h]; int
0x180027735  mov     rcx, [rbp+60h]; int
0x180027739  call    __scrt_dllmain_exception_filter
0x18002773e  nop
0x18002773f  add     rsp, 30h
0x180027743  pop     rbp
0x180027744  retn
```
