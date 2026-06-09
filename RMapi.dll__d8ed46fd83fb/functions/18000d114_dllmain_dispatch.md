# dllmain_dispatch

- ea: `0x18000d114`
- end: `0x18000d23b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d250`

## callees

- `0x180004660`
- `0x18000cf30`
- `0x18000d114`
- `0x18000d4a4`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180037A90 <= 0 )
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
0x18000d114  mov     rax, rsp
0x18000d117  mov     [rax+20h], rbx
0x18000d11b  mov     [rax+18h], r8
0x18000d11f  mov     [rax+10h], edx
0x18000d122  mov     [rax+8], rcx
0x18000d126  push    rsi
0x18000d127  push    rdi
0x18000d128  push    r14
0x18000d12a  sub     rsp, 40h
0x18000d12e  mov     rsi, r8
0x18000d131  mov     edi, edx
0x18000d133  mov     r14, rcx
0x18000d136  test    edx, edx
0x18000d138  jnz     short loc_18000D149
0x18000d13a  cmp     cs:dword_180037A90, edx
0x18000d140  jg      short loc_18000D149
0x18000d142  xor     eax, eax
0x18000d144  jmp     loc_18000D22D
0x18000d149  lea     eax, [rdx-1]
0x18000d14c  cmp     eax, 1
0x18000d14f  ja      short loc_18000D190
0x18000d151  mov     rax, cs:_pRawDllMain
0x18000d158  test    rax, rax
0x18000d15b  jnz     short loc_18000D162
0x18000d15d  lea     ebx, [rax+1]
0x18000d160  jmp     short loc_18000D169
0x18000d162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d167  mov     ebx, eax
0x18000d169  mov     [rsp+58h+var_28], ebx
0x18000d16d  test    ebx, ebx
0x18000d16f  jz      loc_18000D223
0x18000d175  mov     r8, rsi
0x18000d178  mov     edx, edi
0x18000d17a  mov     rcx, r14
0x18000d17d  call    dllmain_crt_dispatch
0x18000d182  mov     ebx, eax
0x18000d184  mov     [rsp+58h+var_28], eax
0x18000d188  test    eax, eax
0x18000d18a  jz      loc_18000D223
0x18000d190  mov     r8, rsi; lpvReserved
0x18000d193  mov     edx, edi; fdwReason
0x18000d195  mov     rcx, r14; hinstDLL
0x18000d198  call    DllMain
0x18000d19d  mov     ebx, eax
0x18000d19f  mov     [rsp+58h+var_28], eax
0x18000d1a3  cmp     edi, 1
0x18000d1a6  jnz     short loc_18000D1DF
0x18000d1a8  test    eax, eax
0x18000d1aa  jnz     short loc_18000D1DF
0x18000d1ac  mov     r8, rsi; lpvReserved
0x18000d1af  xor     edx, edx; fdwReason
0x18000d1b1  mov     rcx, r14; hinstDLL
0x18000d1b4  call    DllMain
0x18000d1b9  mov     r8, rsi
0x18000d1bc  xor     edx, edx
0x18000d1be  mov     rcx, r14
0x18000d1c1  call    dllmain_crt_dispatch
0x18000d1c6  mov     rax, cs:_pRawDllMain
0x18000d1cd  test    rax, rax
0x18000d1d0  jz      short loc_18000D1DF
0x18000d1d2  mov     r8, rsi
0x18000d1d5  xor     edx, edx
0x18000d1d7  mov     rcx, r14
0x18000d1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1df  test    edi, edi
0x18000d1e1  jz      short loc_18000D1E8
0x18000d1e3  cmp     edi, 3
0x18000d1e6  jnz     short loc_18000D223
0x18000d1e8  mov     r8, rsi
0x18000d1eb  mov     edx, edi
0x18000d1ed  mov     rcx, r14
0x18000d1f0  call    dllmain_crt_dispatch
0x18000d1f5  mov     ebx, eax
0x18000d1f7  mov     [rsp+58h+var_28], eax
0x18000d1fb  test    eax, eax
0x18000d1fd  jz      short loc_18000D223
0x18000d1ff  mov     rax, cs:_pRawDllMain
0x18000d206  test    rax, rax
0x18000d209  jnz     short loc_18000D210
0x18000d20b  lea     ebx, [rax+1]
0x18000d20e  jmp     short loc_18000D21F
0x18000d210  mov     r8, rsi
0x18000d213  mov     edx, edi
0x18000d215  mov     rcx, r14
0x18000d218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21d  mov     ebx, eax
0x18000d21f  mov     [rsp+58h+var_28], ebx
0x18000d223  jmp     short loc_18000D22B
0x18000d225  xor     ebx, ebx
0x18000d227  mov     [rsp+58h+var_28], ebx
0x18000d22b  mov     eax, ebx
0x18000d22d  mov     rbx, [rsp+58h+arg_18]
0x18000d232  add     rsp, 40h
0x18000d236  pop     r14
0x18000d238  pop     rdi
0x18000d239  pop     rsi
0x18000d23a  retn
0x180025889  push    rbp
0x18002588b  sub     rsp, 30h
0x18002588f  mov     rbp, rdx
0x180025892  mov     rax, [rcx]
0x180025895  mov     edx, [rax]
0x180025897  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002589c  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800258a0  lea     r9, dllmain_crt_dispatch; int
0x1800258a7  mov     r8, [rbp+70h]; int
0x1800258ab  mov     edx, [rbp+68h]; int
0x1800258ae  mov     rcx, [rbp+60h]; int
0x1800258b2  call    __scrt_dllmain_exception_filter
0x1800258b7  nop
0x1800258b8  add     rsp, 30h
0x1800258bc  pop     rbp
0x1800258bd  retn
```
