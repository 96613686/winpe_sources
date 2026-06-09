# dllmain_dispatch

- ea: `0x1800016d4`
- end: `0x1800017fb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001810`

## callees

- `0x1800014f0`
- `0x1800016d4`
- `0x180001a98`
- `0x180001e28`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180036DD0 <= 0 )
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
0x1800016d4  mov     rax, rsp
0x1800016d7  mov     [rax+20h], rbx
0x1800016db  mov     [rax+18h], r8
0x1800016df  mov     [rax+10h], edx
0x1800016e2  mov     [rax+8], rcx
0x1800016e6  push    rsi
0x1800016e7  push    rdi
0x1800016e8  push    r14
0x1800016ea  sub     rsp, 40h
0x1800016ee  mov     rsi, r8
0x1800016f1  mov     edi, edx
0x1800016f3  mov     r14, rcx
0x1800016f6  test    edx, edx
0x1800016f8  jnz     short loc_180001709
0x1800016fa  cmp     cs:dword_180036DD0, edx
0x180001700  jg      short loc_180001709
0x180001702  xor     eax, eax
0x180001704  jmp     loc_1800017ED
0x180001709  lea     eax, [rdx-1]
0x18000170c  cmp     eax, 1
0x18000170f  ja      short loc_180001750
0x180001711  mov     rax, cs:_pRawDllMain
0x180001718  test    rax, rax
0x18000171b  jnz     short loc_180001722
0x18000171d  lea     ebx, [rax+1]
0x180001720  jmp     short loc_180001729
0x180001722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001727  mov     ebx, eax
0x180001729  mov     [rsp+58h+var_28], ebx
0x18000172d  test    ebx, ebx
0x18000172f  jz      loc_1800017E3
0x180001735  mov     r8, rsi
0x180001738  mov     edx, edi
0x18000173a  mov     rcx, r14
0x18000173d  call    dllmain_crt_dispatch
0x180001742  mov     ebx, eax
0x180001744  mov     [rsp+58h+var_28], eax
0x180001748  test    eax, eax
0x18000174a  jz      loc_1800017E3
0x180001750  mov     r8, rsi; lpvReserved
0x180001753  mov     edx, edi; fdwReason
0x180001755  mov     rcx, r14; hinstDLL
0x180001758  call    DllMain
0x18000175d  mov     ebx, eax
0x18000175f  mov     [rsp+58h+var_28], eax
0x180001763  cmp     edi, 1
0x180001766  jnz     short loc_18000179F
0x180001768  test    eax, eax
0x18000176a  jnz     short loc_18000179F
0x18000176c  mov     r8, rsi; lpvReserved
0x18000176f  xor     edx, edx; fdwReason
0x180001771  mov     rcx, r14; hinstDLL
0x180001774  call    DllMain
0x180001779  mov     r8, rsi
0x18000177c  xor     edx, edx
0x18000177e  mov     rcx, r14
0x180001781  call    dllmain_crt_dispatch
0x180001786  mov     rax, cs:_pRawDllMain
0x18000178d  test    rax, rax
0x180001790  jz      short loc_18000179F
0x180001792  mov     r8, rsi
0x180001795  xor     edx, edx
0x180001797  mov     rcx, r14
0x18000179a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000179f  test    edi, edi
0x1800017a1  jz      short loc_1800017A8
0x1800017a3  cmp     edi, 3
0x1800017a6  jnz     short loc_1800017E3
0x1800017a8  mov     r8, rsi
0x1800017ab  mov     edx, edi
0x1800017ad  mov     rcx, r14
0x1800017b0  call    dllmain_crt_dispatch
0x1800017b5  mov     ebx, eax
0x1800017b7  mov     [rsp+58h+var_28], eax
0x1800017bb  test    eax, eax
0x1800017bd  jz      short loc_1800017E3
0x1800017bf  mov     rax, cs:_pRawDllMain
0x1800017c6  test    rax, rax
0x1800017c9  jnz     short loc_1800017D0
0x1800017cb  lea     ebx, [rax+1]
0x1800017ce  jmp     short loc_1800017DF
0x1800017d0  mov     r8, rsi
0x1800017d3  mov     edx, edi
0x1800017d5  mov     rcx, r14
0x1800017d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017dd  mov     ebx, eax
0x1800017df  mov     [rsp+58h+var_28], ebx
0x1800017e3  jmp     short loc_1800017EB
0x1800017e5  xor     ebx, ebx
0x1800017e7  mov     [rsp+58h+var_28], ebx
0x1800017eb  mov     eax, ebx
0x1800017ed  mov     rbx, [rsp+58h+arg_18]
0x1800017f2  add     rsp, 40h
0x1800017f6  pop     r14
0x1800017f8  pop     rdi
0x1800017f9  pop     rsi
0x1800017fa  retn
0x180027cbc  push    rbp
0x180027cbe  sub     rsp, 30h
0x180027cc2  mov     rbp, rdx
0x180027cc5  mov     rax, [rcx]
0x180027cc8  mov     edx, [rax]
0x180027cca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180027ccf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180027cd3  lea     r9, dllmain_crt_dispatch; int
0x180027cda  mov     r8, [rbp+70h]; int
0x180027cde  mov     edx, [rbp+68h]; int
0x180027ce1  mov     rcx, [rbp+60h]; int
0x180027ce5  call    __scrt_dllmain_exception_filter
0x180027cea  nop
0x180027ceb  add     rsp, 30h
0x180027cef  pop     rbp
0x180027cf0  retn
```
