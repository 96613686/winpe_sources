# dllmain_dispatch

- ea: `0x18001cdc4`
- end: `0x18001ceeb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cf00`

## callees

- `0x180012b20`
- `0x18001cbe0`
- `0x18001cdc4`
- `0x18001d090`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180036D58 <= 0 )
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
0x18001cdc4  mov     rax, rsp
0x18001cdc7  mov     [rax+20h], rbx
0x18001cdcb  mov     [rax+18h], r8
0x18001cdcf  mov     [rax+10h], edx
0x18001cdd2  mov     [rax+8], rcx
0x18001cdd6  push    rsi
0x18001cdd7  push    rdi
0x18001cdd8  push    r14
0x18001cdda  sub     rsp, 40h
0x18001cdde  mov     rsi, r8
0x18001cde1  mov     edi, edx
0x18001cde3  mov     r14, rcx
0x18001cde6  test    edx, edx
0x18001cde8  jnz     short loc_18001CDF9
0x18001cdea  cmp     cs:dword_180036D58, edx
0x18001cdf0  jg      short loc_18001CDF9
0x18001cdf2  xor     eax, eax
0x18001cdf4  jmp     loc_18001CEDD
0x18001cdf9  lea     eax, [rdx-1]
0x18001cdfc  cmp     eax, 1
0x18001cdff  ja      short loc_18001CE40
0x18001ce01  mov     rax, cs:_pRawDllMain
0x18001ce08  test    rax, rax
0x18001ce0b  jnz     short loc_18001CE12
0x18001ce0d  lea     ebx, [rax+1]
0x18001ce10  jmp     short loc_18001CE19
0x18001ce12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce17  mov     ebx, eax
0x18001ce19  mov     [rsp+58h+var_28], ebx
0x18001ce1d  test    ebx, ebx
0x18001ce1f  jz      loc_18001CED3
0x18001ce25  mov     r8, rsi
0x18001ce28  mov     edx, edi
0x18001ce2a  mov     rcx, r14
0x18001ce2d  call    dllmain_crt_dispatch
0x18001ce32  mov     ebx, eax
0x18001ce34  mov     [rsp+58h+var_28], eax
0x18001ce38  test    eax, eax
0x18001ce3a  jz      loc_18001CED3
0x18001ce40  mov     r8, rsi; lpvReserved
0x18001ce43  mov     edx, edi; fdwReason
0x18001ce45  mov     rcx, r14; hinstDLL
0x18001ce48  call    DllMain
0x18001ce4d  mov     ebx, eax
0x18001ce4f  mov     [rsp+58h+var_28], eax
0x18001ce53  cmp     edi, 1
0x18001ce56  jnz     short loc_18001CE8F
0x18001ce58  test    eax, eax
0x18001ce5a  jnz     short loc_18001CE8F
0x18001ce5c  mov     r8, rsi; lpvReserved
0x18001ce5f  xor     edx, edx; fdwReason
0x18001ce61  mov     rcx, r14; hinstDLL
0x18001ce64  call    DllMain
0x18001ce69  mov     r8, rsi
0x18001ce6c  xor     edx, edx
0x18001ce6e  mov     rcx, r14
0x18001ce71  call    dllmain_crt_dispatch
0x18001ce76  mov     rax, cs:_pRawDllMain
0x18001ce7d  test    rax, rax
0x18001ce80  jz      short loc_18001CE8F
0x18001ce82  mov     r8, rsi
0x18001ce85  xor     edx, edx
0x18001ce87  mov     rcx, r14
0x18001ce8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce8f  test    edi, edi
0x18001ce91  jz      short loc_18001CE98
0x18001ce93  cmp     edi, 3
0x18001ce96  jnz     short loc_18001CED3
0x18001ce98  mov     r8, rsi
0x18001ce9b  mov     edx, edi
0x18001ce9d  mov     rcx, r14
0x18001cea0  call    dllmain_crt_dispatch
0x18001cea5  mov     ebx, eax
0x18001cea7  mov     [rsp+58h+var_28], eax
0x18001ceab  test    eax, eax
0x18001cead  jz      short loc_18001CED3
0x18001ceaf  mov     rax, cs:_pRawDllMain
0x18001ceb6  test    rax, rax
0x18001ceb9  jnz     short loc_18001CEC0
0x18001cebb  lea     ebx, [rax+1]
0x18001cebe  jmp     short loc_18001CECF
0x18001cec0  mov     r8, rsi
0x18001cec3  mov     edx, edi
0x18001cec5  mov     rcx, r14
0x18001cec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cecd  mov     ebx, eax
0x18001cecf  mov     [rsp+58h+var_28], ebx
0x18001ced3  jmp     short loc_18001CEDB
0x18001ced5  xor     ebx, ebx
0x18001ced7  mov     [rsp+58h+var_28], ebx
0x18001cedb  mov     eax, ebx
0x18001cedd  mov     rbx, [rsp+58h+arg_18]
0x18001cee2  add     rsp, 40h
0x18001cee6  pop     r14
0x18001cee8  pop     rdi
0x18001cee9  pop     rsi
0x18001ceea  retn
0x180025be7  push    rbp
0x180025be9  sub     rsp, 30h
0x180025bed  mov     rbp, rdx
0x180025bf0  mov     rax, [rcx]
0x180025bf3  mov     edx, [rax]
0x180025bf5  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180025bfa  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180025bfe  lea     r9, dllmain_crt_dispatch; int
0x180025c05  mov     r8, [rbp+70h]; int
0x180025c09  mov     edx, [rbp+68h]; int
0x180025c0c  mov     rcx, [rbp+60h]; int
0x180025c10  call    __scrt_dllmain_exception_filter
0x180025c15  nop
0x180025c16  add     rsp, 30h
0x180025c1a  pop     rbp
0x180025c1b  retn
```
