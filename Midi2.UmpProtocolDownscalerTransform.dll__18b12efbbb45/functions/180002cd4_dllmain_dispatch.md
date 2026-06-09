# dllmain_dispatch

- ea: `0x180002cd4`
- end: `0x180002dfb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002e10`

## callees

- `0x180002af0`
- `0x180002cd4`
- `0x1800030ac`
- `0x18000aed4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001B770 <= 0 )
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
0x180002cd4  mov     rax, rsp
0x180002cd7  mov     [rax+20h], rbx
0x180002cdb  mov     [rax+18h], r8
0x180002cdf  mov     [rax+10h], edx
0x180002ce2  mov     [rax+8], rcx
0x180002ce6  push    rsi
0x180002ce7  push    rdi
0x180002ce8  push    r14
0x180002cea  sub     rsp, 40h
0x180002cee  mov     rsi, r8
0x180002cf1  mov     edi, edx
0x180002cf3  mov     r14, rcx
0x180002cf6  test    edx, edx
0x180002cf8  jnz     short loc_180002D09
0x180002cfa  cmp     cs:dword_18001B770, edx
0x180002d00  jg      short loc_180002D09
0x180002d02  xor     eax, eax
0x180002d04  jmp     loc_180002DED
0x180002d09  lea     eax, [rdx-1]
0x180002d0c  cmp     eax, 1
0x180002d0f  ja      short loc_180002D50
0x180002d11  mov     rax, cs:_pRawDllMain
0x180002d18  test    rax, rax
0x180002d1b  jnz     short loc_180002D22
0x180002d1d  lea     ebx, [rax+1]
0x180002d20  jmp     short loc_180002D29
0x180002d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d27  mov     ebx, eax
0x180002d29  mov     [rsp+58h+var_28], ebx
0x180002d2d  test    ebx, ebx
0x180002d2f  jz      loc_180002DE3
0x180002d35  mov     r8, rsi
0x180002d38  mov     edx, edi
0x180002d3a  mov     rcx, r14
0x180002d3d  call    dllmain_crt_dispatch
0x180002d42  mov     ebx, eax
0x180002d44  mov     [rsp+58h+var_28], eax
0x180002d48  test    eax, eax
0x180002d4a  jz      loc_180002DE3
0x180002d50  mov     r8, rsi; lpvReserved
0x180002d53  mov     edx, edi; fdwReason
0x180002d55  mov     rcx, r14; hinstDLL
0x180002d58  call    DllMain
0x180002d5d  mov     ebx, eax
0x180002d5f  mov     [rsp+58h+var_28], eax
0x180002d63  cmp     edi, 1
0x180002d66  jnz     short loc_180002D9F
0x180002d68  test    eax, eax
0x180002d6a  jnz     short loc_180002D9F
0x180002d6c  mov     r8, rsi; lpvReserved
0x180002d6f  xor     edx, edx; fdwReason
0x180002d71  mov     rcx, r14; hinstDLL
0x180002d74  call    DllMain
0x180002d79  mov     r8, rsi
0x180002d7c  xor     edx, edx
0x180002d7e  mov     rcx, r14
0x180002d81  call    dllmain_crt_dispatch
0x180002d86  mov     rax, cs:_pRawDllMain
0x180002d8d  test    rax, rax
0x180002d90  jz      short loc_180002D9F
0x180002d92  mov     r8, rsi
0x180002d95  xor     edx, edx
0x180002d97  mov     rcx, r14
0x180002d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d9f  test    edi, edi
0x180002da1  jz      short loc_180002DA8
0x180002da3  cmp     edi, 3
0x180002da6  jnz     short loc_180002DE3
0x180002da8  mov     r8, rsi
0x180002dab  mov     edx, edi
0x180002dad  mov     rcx, r14
0x180002db0  call    dllmain_crt_dispatch
0x180002db5  mov     ebx, eax
0x180002db7  mov     [rsp+58h+var_28], eax
0x180002dbb  test    eax, eax
0x180002dbd  jz      short loc_180002DE3
0x180002dbf  mov     rax, cs:_pRawDllMain
0x180002dc6  test    rax, rax
0x180002dc9  jnz     short loc_180002DD0
0x180002dcb  lea     ebx, [rax+1]
0x180002dce  jmp     short loc_180002DDF
0x180002dd0  mov     r8, rsi
0x180002dd3  mov     edx, edi
0x180002dd5  mov     rcx, r14
0x180002dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ddd  mov     ebx, eax
0x180002ddf  mov     [rsp+58h+var_28], ebx
0x180002de3  jmp     short loc_180002DEB
0x180002de5  xor     ebx, ebx
0x180002de7  mov     [rsp+58h+var_28], ebx
0x180002deb  mov     eax, ebx
0x180002ded  mov     rbx, [rsp+58h+arg_18]
0x180002df2  add     rsp, 40h
0x180002df6  pop     r14
0x180002df8  pop     rdi
0x180002df9  pop     rsi
0x180002dfa  retn
0x18001219c  push    rbp
0x18001219e  sub     rsp, 30h
0x1800121a2  mov     rbp, rdx
0x1800121a5  mov     rax, [rcx]
0x1800121a8  mov     edx, [rax]
0x1800121aa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800121af  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800121b3  lea     r9, dllmain_crt_dispatch; int
0x1800121ba  mov     r8, [rbp+70h]; int
0x1800121be  mov     edx, [rbp+68h]; int
0x1800121c1  mov     rcx, [rbp+60h]; int
0x1800121c5  call    __scrt_dllmain_exception_filter
0x1800121ca  nop
0x1800121cb  add     rsp, 30h
0x1800121cf  pop     rbp
0x1800121d0  retn
```
