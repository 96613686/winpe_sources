# dllmain_dispatch

- ea: `0x180003514`
- end: `0x18000363b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003650`

## callees

- `0x180003330`
- `0x180003514`
- `0x18000379c`
- `0x18000b0b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800253F0 <= 0 )
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
0x180003514  mov     rax, rsp
0x180003517  mov     [rax+20h], rbx
0x18000351b  mov     [rax+18h], r8
0x18000351f  mov     [rax+10h], edx
0x180003522  mov     [rax+8], rcx
0x180003526  push    rsi
0x180003527  push    rdi
0x180003528  push    r14
0x18000352a  sub     rsp, 40h
0x18000352e  mov     rsi, r8
0x180003531  mov     edi, edx
0x180003533  mov     r14, rcx
0x180003536  test    edx, edx
0x180003538  jnz     short loc_180003549
0x18000353a  cmp     cs:dword_1800253F0, edx
0x180003540  jg      short loc_180003549
0x180003542  xor     eax, eax
0x180003544  jmp     loc_18000362D
0x180003549  lea     eax, [rdx-1]
0x18000354c  cmp     eax, 1
0x18000354f  ja      short loc_180003590
0x180003551  mov     rax, cs:_pRawDllMain
0x180003558  test    rax, rax
0x18000355b  jnz     short loc_180003562
0x18000355d  lea     ebx, [rax+1]
0x180003560  jmp     short loc_180003569
0x180003562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003567  mov     ebx, eax
0x180003569  mov     [rsp+58h+var_28], ebx
0x18000356d  test    ebx, ebx
0x18000356f  jz      loc_180003623
0x180003575  mov     r8, rsi
0x180003578  mov     edx, edi
0x18000357a  mov     rcx, r14
0x18000357d  call    dllmain_crt_dispatch
0x180003582  mov     ebx, eax
0x180003584  mov     [rsp+58h+var_28], eax
0x180003588  test    eax, eax
0x18000358a  jz      loc_180003623
0x180003590  mov     r8, rsi; lpvReserved
0x180003593  mov     edx, edi; fdwReason
0x180003595  mov     rcx, r14; hinstDLL
0x180003598  call    DllMain
0x18000359d  mov     ebx, eax
0x18000359f  mov     [rsp+58h+var_28], eax
0x1800035a3  cmp     edi, 1
0x1800035a6  jnz     short loc_1800035DF
0x1800035a8  test    eax, eax
0x1800035aa  jnz     short loc_1800035DF
0x1800035ac  mov     r8, rsi; lpvReserved
0x1800035af  xor     edx, edx; fdwReason
0x1800035b1  mov     rcx, r14; hinstDLL
0x1800035b4  call    DllMain
0x1800035b9  mov     r8, rsi
0x1800035bc  xor     edx, edx
0x1800035be  mov     rcx, r14
0x1800035c1  call    dllmain_crt_dispatch
0x1800035c6  mov     rax, cs:_pRawDllMain
0x1800035cd  test    rax, rax
0x1800035d0  jz      short loc_1800035DF
0x1800035d2  mov     r8, rsi
0x1800035d5  xor     edx, edx
0x1800035d7  mov     rcx, r14
0x1800035da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035df  test    edi, edi
0x1800035e1  jz      short loc_1800035E8
0x1800035e3  cmp     edi, 3
0x1800035e6  jnz     short loc_180003623
0x1800035e8  mov     r8, rsi
0x1800035eb  mov     edx, edi
0x1800035ed  mov     rcx, r14
0x1800035f0  call    dllmain_crt_dispatch
0x1800035f5  mov     ebx, eax
0x1800035f7  mov     [rsp+58h+var_28], eax
0x1800035fb  test    eax, eax
0x1800035fd  jz      short loc_180003623
0x1800035ff  mov     rax, cs:_pRawDllMain
0x180003606  test    rax, rax
0x180003609  jnz     short loc_180003610
0x18000360b  lea     ebx, [rax+1]
0x18000360e  jmp     short loc_18000361F
0x180003610  mov     r8, rsi
0x180003613  mov     edx, edi
0x180003615  mov     rcx, r14
0x180003618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000361d  mov     ebx, eax
0x18000361f  mov     [rsp+58h+var_28], ebx
0x180003623  jmp     short loc_18000362B
0x180003625  xor     ebx, ebx
0x180003627  mov     [rsp+58h+var_28], ebx
0x18000362b  mov     eax, ebx
0x18000362d  mov     rbx, [rsp+58h+arg_18]
0x180003632  add     rsp, 40h
0x180003636  pop     r14
0x180003638  pop     rdi
0x180003639  pop     rsi
0x18000363a  retn
0x18001b520  push    rbp
0x18001b522  sub     rsp, 30h
0x18001b526  mov     rbp, rdx
0x18001b529  mov     rax, [rcx]
0x18001b52c  mov     edx, [rax]
0x18001b52e  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001b533  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001b537  lea     r9, dllmain_crt_dispatch; int
0x18001b53e  mov     r8, [rbp+70h]; int
0x18001b542  mov     edx, [rbp+68h]; int
0x18001b545  mov     rcx, [rbp+60h]; int
0x18001b549  call    __scrt_dllmain_exception_filter
0x18001b54e  nop
0x18001b54f  add     rsp, 30h
0x18001b553  pop     rbp
0x18001b554  retn
```
