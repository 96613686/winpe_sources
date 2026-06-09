# dllmain_dispatch

- ea: `0x1800086a4`
- end: `0x1800087cb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800087e0`

## callees

- `0x1800084c0`
- `0x1800086a4`
- `0x180008970`
- `0x180009a5c`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180057410 <= 0 )
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
0x1800086a4  mov     rax, rsp
0x1800086a7  mov     [rax+20h], rbx
0x1800086ab  mov     [rax+18h], r8
0x1800086af  mov     [rax+10h], edx
0x1800086b2  mov     [rax+8], rcx
0x1800086b6  push    rsi
0x1800086b7  push    rdi
0x1800086b8  push    r14
0x1800086ba  sub     rsp, 40h
0x1800086be  mov     rsi, r8
0x1800086c1  mov     edi, edx
0x1800086c3  mov     r14, rcx
0x1800086c6  test    edx, edx
0x1800086c8  jnz     short loc_1800086D9
0x1800086ca  cmp     cs:dword_180057410, edx
0x1800086d0  jg      short loc_1800086D9
0x1800086d2  xor     eax, eax
0x1800086d4  jmp     loc_1800087BD
0x1800086d9  lea     eax, [rdx-1]
0x1800086dc  cmp     eax, 1
0x1800086df  ja      short loc_180008720
0x1800086e1  mov     rax, cs:_pRawDllMain
0x1800086e8  test    rax, rax
0x1800086eb  jnz     short loc_1800086F2
0x1800086ed  lea     ebx, [rax+1]
0x1800086f0  jmp     short loc_1800086F9
0x1800086f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f7  mov     ebx, eax
0x1800086f9  mov     [rsp+58h+var_28], ebx
0x1800086fd  test    ebx, ebx
0x1800086ff  jz      loc_1800087B3
0x180008705  mov     r8, rsi
0x180008708  mov     edx, edi
0x18000870a  mov     rcx, r14
0x18000870d  call    dllmain_crt_dispatch
0x180008712  mov     ebx, eax
0x180008714  mov     [rsp+58h+var_28], eax
0x180008718  test    eax, eax
0x18000871a  jz      loc_1800087B3
0x180008720  mov     r8, rsi; lpvReserved
0x180008723  mov     edx, edi; fdwReason
0x180008725  mov     rcx, r14; hinstDLL
0x180008728  call    DllMain
0x18000872d  mov     ebx, eax
0x18000872f  mov     [rsp+58h+var_28], eax
0x180008733  cmp     edi, 1
0x180008736  jnz     short loc_18000876F
0x180008738  test    eax, eax
0x18000873a  jnz     short loc_18000876F
0x18000873c  mov     r8, rsi; lpvReserved
0x18000873f  xor     edx, edx; fdwReason
0x180008741  mov     rcx, r14; hinstDLL
0x180008744  call    DllMain
0x180008749  mov     r8, rsi
0x18000874c  xor     edx, edx
0x18000874e  mov     rcx, r14
0x180008751  call    dllmain_crt_dispatch
0x180008756  mov     rax, cs:_pRawDllMain
0x18000875d  test    rax, rax
0x180008760  jz      short loc_18000876F
0x180008762  mov     r8, rsi
0x180008765  xor     edx, edx
0x180008767  mov     rcx, r14
0x18000876a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000876f  test    edi, edi
0x180008771  jz      short loc_180008778
0x180008773  cmp     edi, 3
0x180008776  jnz     short loc_1800087B3
0x180008778  mov     r8, rsi
0x18000877b  mov     edx, edi
0x18000877d  mov     rcx, r14
0x180008780  call    dllmain_crt_dispatch
0x180008785  mov     ebx, eax
0x180008787  mov     [rsp+58h+var_28], eax
0x18000878b  test    eax, eax
0x18000878d  jz      short loc_1800087B3
0x18000878f  mov     rax, cs:_pRawDllMain
0x180008796  test    rax, rax
0x180008799  jnz     short loc_1800087A0
0x18000879b  lea     ebx, [rax+1]
0x18000879e  jmp     short loc_1800087AF
0x1800087a0  mov     r8, rsi
0x1800087a3  mov     edx, edi
0x1800087a5  mov     rcx, r14
0x1800087a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ad  mov     ebx, eax
0x1800087af  mov     [rsp+58h+var_28], ebx
0x1800087b3  jmp     short loc_1800087BB
0x1800087b5  xor     ebx, ebx
0x1800087b7  mov     [rsp+58h+var_28], ebx
0x1800087bb  mov     eax, ebx
0x1800087bd  mov     rbx, [rsp+58h+arg_18]
0x1800087c2  add     rsp, 40h
0x1800087c6  pop     r14
0x1800087c8  pop     rdi
0x1800087c9  pop     rsi
0x1800087ca  retn
0x18004727c  push    rbp
0x18004727e  sub     rsp, 30h
0x180047282  mov     rbp, rdx
0x180047285  mov     rax, [rcx]
0x180047288  mov     edx, [rax]
0x18004728a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18004728f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180047293  lea     r9, dllmain_crt_dispatch; int
0x18004729a  mov     r8, [rbp+70h]; int
0x18004729e  mov     edx, [rbp+68h]; int
0x1800472a1  mov     rcx, [rbp+60h]; int
0x1800472a5  call    __scrt_dllmain_exception_filter
0x1800472aa  nop
0x1800472ab  add     rsp, 30h
0x1800472af  pop     rbp
0x1800472b0  retn
```
