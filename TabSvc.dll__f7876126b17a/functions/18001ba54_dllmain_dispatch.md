# dllmain_dispatch

- ea: `0x18001ba54`
- end: `0x18001bb7b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001bb90`

## callees

- `0x18001b870`
- `0x18001ba54`
- `0x18001bd1c`
- `0x18002e41c`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800418D0 <= 0 )
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
0x18001ba54  mov     rax, rsp
0x18001ba57  mov     [rax+20h], rbx
0x18001ba5b  mov     [rax+18h], r8
0x18001ba5f  mov     [rax+10h], edx
0x18001ba62  mov     [rax+8], rcx
0x18001ba66  push    rsi
0x18001ba67  push    rdi
0x18001ba68  push    r14
0x18001ba6a  sub     rsp, 40h
0x18001ba6e  mov     rsi, r8
0x18001ba71  mov     edi, edx
0x18001ba73  mov     r14, rcx
0x18001ba76  test    edx, edx
0x18001ba78  jnz     short loc_18001BA89
0x18001ba7a  cmp     cs:dword_1800418D0, edx
0x18001ba80  jg      short loc_18001BA89
0x18001ba82  xor     eax, eax
0x18001ba84  jmp     loc_18001BB6D
0x18001ba89  lea     eax, [rdx-1]
0x18001ba8c  cmp     eax, 1
0x18001ba8f  ja      short loc_18001BAD0
0x18001ba91  mov     rax, cs:_pRawDllMain
0x18001ba98  test    rax, rax
0x18001ba9b  jnz     short loc_18001BAA2
0x18001ba9d  lea     ebx, [rax+1]
0x18001baa0  jmp     short loc_18001BAA9
0x18001baa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa7  mov     ebx, eax
0x18001baa9  mov     [rsp+58h+var_28], ebx
0x18001baad  test    ebx, ebx
0x18001baaf  jz      loc_18001BB63
0x18001bab5  mov     r8, rsi
0x18001bab8  mov     edx, edi
0x18001baba  mov     rcx, r14
0x18001babd  call    dllmain_crt_dispatch
0x18001bac2  mov     ebx, eax
0x18001bac4  mov     [rsp+58h+var_28], eax
0x18001bac8  test    eax, eax
0x18001baca  jz      loc_18001BB63
0x18001bad0  mov     r8, rsi; lpvReserved
0x18001bad3  mov     edx, edi; fdwReason
0x18001bad5  mov     rcx, r14; hinstDLL
0x18001bad8  call    DllMain
0x18001badd  mov     ebx, eax
0x18001badf  mov     [rsp+58h+var_28], eax
0x18001bae3  cmp     edi, 1
0x18001bae6  jnz     short loc_18001BB1F
0x18001bae8  test    eax, eax
0x18001baea  jnz     short loc_18001BB1F
0x18001baec  mov     r8, rsi; lpvReserved
0x18001baef  xor     edx, edx; fdwReason
0x18001baf1  mov     rcx, r14; hinstDLL
0x18001baf4  call    DllMain
0x18001baf9  mov     r8, rsi
0x18001bafc  xor     edx, edx
0x18001bafe  mov     rcx, r14
0x18001bb01  call    dllmain_crt_dispatch
0x18001bb06  mov     rax, cs:_pRawDllMain
0x18001bb0d  test    rax, rax
0x18001bb10  jz      short loc_18001BB1F
0x18001bb12  mov     r8, rsi
0x18001bb15  xor     edx, edx
0x18001bb17  mov     rcx, r14
0x18001bb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb1f  test    edi, edi
0x18001bb21  jz      short loc_18001BB28
0x18001bb23  cmp     edi, 3
0x18001bb26  jnz     short loc_18001BB63
0x18001bb28  mov     r8, rsi
0x18001bb2b  mov     edx, edi
0x18001bb2d  mov     rcx, r14
0x18001bb30  call    dllmain_crt_dispatch
0x18001bb35  mov     ebx, eax
0x18001bb37  mov     [rsp+58h+var_28], eax
0x18001bb3b  test    eax, eax
0x18001bb3d  jz      short loc_18001BB63
0x18001bb3f  mov     rax, cs:_pRawDllMain
0x18001bb46  test    rax, rax
0x18001bb49  jnz     short loc_18001BB50
0x18001bb4b  lea     ebx, [rax+1]
0x18001bb4e  jmp     short loc_18001BB5F
0x18001bb50  mov     r8, rsi
0x18001bb53  mov     edx, edi
0x18001bb55  mov     rcx, r14
0x18001bb58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb5d  mov     ebx, eax
0x18001bb5f  mov     [rsp+58h+var_28], ebx
0x18001bb63  jmp     short loc_18001BB6B
0x18001bb65  xor     ebx, ebx
0x18001bb67  mov     [rsp+58h+var_28], ebx
0x18001bb6b  mov     eax, ebx
0x18001bb6d  mov     rbx, [rsp+58h+arg_18]
0x18001bb72  add     rsp, 40h
0x18001bb76  pop     r14
0x18001bb78  pop     rdi
0x18001bb79  pop     rsi
0x18001bb7a  retn
0x18002ffb0  push    rbp
0x18002ffb2  sub     rsp, 30h
0x18002ffb6  mov     rbp, rdx
0x18002ffb9  mov     rax, [rcx]
0x18002ffbc  mov     edx, [rax]
0x18002ffbe  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002ffc3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18002ffc7  lea     r9, dllmain_crt_dispatch; int
0x18002ffce  mov     r8, [rbp+70h]; int
0x18002ffd2  mov     edx, [rbp+68h]; int
0x18002ffd5  mov     rcx, [rbp+60h]; int
0x18002ffd9  call    __scrt_dllmain_exception_filter
0x18002ffde  nop
0x18002ffdf  add     rsp, 30h
0x18002ffe3  pop     rbp
0x18002ffe4  retn
```
