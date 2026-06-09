# dllmain_dispatch

- ea: `0x18001bc84`
- end: `0x18001bdab`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001bdc0`

## callees

- `0x180001210`
- `0x18001baa0`
- `0x18001bc84`
- `0x18001bf28`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800452D0 <= 0 )
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
0x18001bc84  mov     rax, rsp
0x18001bc87  mov     [rax+20h], rbx
0x18001bc8b  mov     [rax+18h], r8
0x18001bc8f  mov     [rax+10h], edx
0x18001bc92  mov     [rax+8], rcx
0x18001bc96  push    rsi
0x18001bc97  push    rdi
0x18001bc98  push    r14
0x18001bc9a  sub     rsp, 40h
0x18001bc9e  mov     rsi, r8
0x18001bca1  mov     edi, edx
0x18001bca3  mov     r14, rcx
0x18001bca6  test    edx, edx
0x18001bca8  jnz     short loc_18001BCB9
0x18001bcaa  cmp     cs:dword_1800452D0, edx
0x18001bcb0  jg      short loc_18001BCB9
0x18001bcb2  xor     eax, eax
0x18001bcb4  jmp     loc_18001BD9D
0x18001bcb9  lea     eax, [rdx-1]
0x18001bcbc  cmp     eax, 1
0x18001bcbf  ja      short loc_18001BD00
0x18001bcc1  mov     rax, cs:_pRawDllMain
0x18001bcc8  test    rax, rax
0x18001bccb  jnz     short loc_18001BCD2
0x18001bccd  lea     ebx, [rax+1]
0x18001bcd0  jmp     short loc_18001BCD9
0x18001bcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcd7  mov     ebx, eax
0x18001bcd9  mov     [rsp+58h+var_28], ebx
0x18001bcdd  test    ebx, ebx
0x18001bcdf  jz      loc_18001BD93
0x18001bce5  mov     r8, rsi
0x18001bce8  mov     edx, edi
0x18001bcea  mov     rcx, r14
0x18001bced  call    dllmain_crt_dispatch
0x18001bcf2  mov     ebx, eax
0x18001bcf4  mov     [rsp+58h+var_28], eax
0x18001bcf8  test    eax, eax
0x18001bcfa  jz      loc_18001BD93
0x18001bd00  mov     r8, rsi; lpvReserved
0x18001bd03  mov     edx, edi; fdwReason
0x18001bd05  mov     rcx, r14; hinstDLL
0x18001bd08  call    DllMain
0x18001bd0d  mov     ebx, eax
0x18001bd0f  mov     [rsp+58h+var_28], eax
0x18001bd13  cmp     edi, 1
0x18001bd16  jnz     short loc_18001BD4F
0x18001bd18  test    eax, eax
0x18001bd1a  jnz     short loc_18001BD4F
0x18001bd1c  mov     r8, rsi; lpvReserved
0x18001bd1f  xor     edx, edx; fdwReason
0x18001bd21  mov     rcx, r14; hinstDLL
0x18001bd24  call    DllMain
0x18001bd29  mov     r8, rsi
0x18001bd2c  xor     edx, edx
0x18001bd2e  mov     rcx, r14
0x18001bd31  call    dllmain_crt_dispatch
0x18001bd36  mov     rax, cs:_pRawDllMain
0x18001bd3d  test    rax, rax
0x18001bd40  jz      short loc_18001BD4F
0x18001bd42  mov     r8, rsi
0x18001bd45  xor     edx, edx
0x18001bd47  mov     rcx, r14
0x18001bd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd4f  test    edi, edi
0x18001bd51  jz      short loc_18001BD58
0x18001bd53  cmp     edi, 3
0x18001bd56  jnz     short loc_18001BD93
0x18001bd58  mov     r8, rsi
0x18001bd5b  mov     edx, edi
0x18001bd5d  mov     rcx, r14
0x18001bd60  call    dllmain_crt_dispatch
0x18001bd65  mov     ebx, eax
0x18001bd67  mov     [rsp+58h+var_28], eax
0x18001bd6b  test    eax, eax
0x18001bd6d  jz      short loc_18001BD93
0x18001bd6f  mov     rax, cs:_pRawDllMain
0x18001bd76  test    rax, rax
0x18001bd79  jnz     short loc_18001BD80
0x18001bd7b  lea     ebx, [rax+1]
0x18001bd7e  jmp     short loc_18001BD8F
0x18001bd80  mov     r8, rsi
0x18001bd83  mov     edx, edi
0x18001bd85  mov     rcx, r14
0x18001bd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd8d  mov     ebx, eax
0x18001bd8f  mov     [rsp+58h+var_28], ebx
0x18001bd93  jmp     short loc_18001BD9B
0x18001bd95  xor     ebx, ebx
0x18001bd97  mov     [rsp+58h+var_28], ebx
0x18001bd9b  mov     eax, ebx
0x18001bd9d  mov     rbx, [rsp+58h+arg_18]
0x18001bda2  add     rsp, 40h
0x18001bda6  pop     r14
0x18001bda8  pop     rdi
0x18001bda9  pop     rsi
0x18001bdaa  retn
0x180031a19  push    rbp
0x180031a1b  sub     rsp, 30h
0x180031a1f  mov     rbp, rdx
0x180031a22  mov     rax, [rcx]
0x180031a25  mov     edx, [rax]
0x180031a27  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180031a2c  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180031a30  lea     r9, dllmain_crt_dispatch; int
0x180031a37  mov     r8, [rbp+70h]; int
0x180031a3b  mov     edx, [rbp+68h]; int
0x180031a3e  mov     rcx, [rbp+60h]; int
0x180031a42  call    __scrt_dllmain_exception_filter
0x180031a47  nop
0x180031a48  add     rsp, 30h
0x180031a4c  pop     rbp
0x180031a4d  retn
```
