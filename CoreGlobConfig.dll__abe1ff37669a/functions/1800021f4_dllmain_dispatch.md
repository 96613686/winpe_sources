# dllmain_dispatch

- ea: `0x1800021f4`
- end: `0x18000231b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002330`

## callees

- `0x180002010`
- `0x1800021f4`
- `0x18000247c`
- `0x180021cb4`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_1800329F0 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = pRawDllMain()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch(hinstDLL, 0, lpvReserved);
      if ( pRawDllMain )
        pRawDllMain();
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved);
      if ( v7 )
      {
        if ( pRawDllMain )
          return (unsigned int)pRawDllMain();
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
0x1800021f4  mov     rax, rsp
0x1800021f7  mov     [rax+20h], rbx
0x1800021fb  mov     [rax+18h], r8
0x1800021ff  mov     [rax+10h], edx
0x180002202  mov     [rax+8], rcx
0x180002206  push    rsi
0x180002207  push    rdi
0x180002208  push    r14
0x18000220a  sub     rsp, 40h
0x18000220e  mov     rsi, r8
0x180002211  mov     edi, edx
0x180002213  mov     r14, rcx
0x180002216  test    edx, edx
0x180002218  jnz     short loc_180002229
0x18000221a  cmp     cs:dword_1800329F0, edx
0x180002220  jg      short loc_180002229
0x180002222  xor     eax, eax
0x180002224  jmp     loc_18000230D
0x180002229  lea     eax, [rdx-1]
0x18000222c  cmp     eax, 1
0x18000222f  ja      short loc_180002270
0x180002231  mov     rax, cs:_pRawDllMain
0x180002238  test    rax, rax
0x18000223b  jnz     short loc_180002242
0x18000223d  lea     ebx, [rax+1]
0x180002240  jmp     short loc_180002249
0x180002242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002247  mov     ebx, eax
0x180002249  mov     [rsp+58h+var_28], ebx
0x18000224d  test    ebx, ebx
0x18000224f  jz      loc_180002303
0x180002255  mov     r8, rsi
0x180002258  mov     edx, edi
0x18000225a  mov     rcx, r14
0x18000225d  call    dllmain_crt_dispatch
0x180002262  mov     ebx, eax
0x180002264  mov     [rsp+58h+var_28], eax
0x180002268  test    eax, eax
0x18000226a  jz      loc_180002303
0x180002270  mov     r8, rsi; lpvReserved
0x180002273  mov     edx, edi; fdwReason
0x180002275  mov     rcx, r14; hinstDLL
0x180002278  call    DllMain
0x18000227d  mov     ebx, eax
0x18000227f  mov     [rsp+58h+var_28], eax
0x180002283  cmp     edi, 1
0x180002286  jnz     short loc_1800022BF
0x180002288  test    eax, eax
0x18000228a  jnz     short loc_1800022BF
0x18000228c  mov     r8, rsi; lpvReserved
0x18000228f  xor     edx, edx; fdwReason
0x180002291  mov     rcx, r14; hinstDLL
0x180002294  call    DllMain
0x180002299  mov     r8, rsi
0x18000229c  xor     edx, edx
0x18000229e  mov     rcx, r14
0x1800022a1  call    dllmain_crt_dispatch
0x1800022a6  mov     rax, cs:_pRawDllMain
0x1800022ad  test    rax, rax
0x1800022b0  jz      short loc_1800022BF
0x1800022b2  mov     r8, rsi
0x1800022b5  xor     edx, edx
0x1800022b7  mov     rcx, r14
0x1800022ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bf  test    edi, edi
0x1800022c1  jz      short loc_1800022C8
0x1800022c3  cmp     edi, 3
0x1800022c6  jnz     short loc_180002303
0x1800022c8  mov     r8, rsi
0x1800022cb  mov     edx, edi
0x1800022cd  mov     rcx, r14
0x1800022d0  call    dllmain_crt_dispatch
0x1800022d5  mov     ebx, eax
0x1800022d7  mov     [rsp+58h+var_28], eax
0x1800022db  test    eax, eax
0x1800022dd  jz      short loc_180002303
0x1800022df  mov     rax, cs:_pRawDllMain
0x1800022e6  test    rax, rax
0x1800022e9  jnz     short loc_1800022F0
0x1800022eb  lea     ebx, [rax+1]
0x1800022ee  jmp     short loc_1800022FF
0x1800022f0  mov     r8, rsi
0x1800022f3  mov     edx, edi
0x1800022f5  mov     rcx, r14
0x1800022f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fd  mov     ebx, eax
0x1800022ff  mov     [rsp+58h+var_28], ebx
0x180002303  jmp     short loc_18000230B
0x180002305  xor     ebx, ebx
0x180002307  mov     [rsp+58h+var_28], ebx
0x18000230b  mov     eax, ebx
0x18000230d  mov     rbx, [rsp+58h+arg_18]
0x180002312  add     rsp, 40h
0x180002316  pop     r14
0x180002318  pop     rdi
0x180002319  pop     rsi
0x18000231a  retn
0x1800228c0  push    rbp
0x1800228c2  sub     rsp, 30h
0x1800228c6  mov     rbp, rdx
0x1800228c9  mov     rax, [rcx]
0x1800228cc  mov     edx, [rax]
0x1800228ce  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800228d3  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800228d7  lea     r9, dllmain_crt_dispatch; int
0x1800228de  mov     r8, [rbp+70h]; int
0x1800228e2  mov     edx, [rbp+68h]; int
0x1800228e5  mov     rcx, [rbp+60h]; int
0x1800228e9  call    __scrt_dllmain_exception_filter
0x1800228ee  nop
0x1800228ef  add     rsp, 30h
0x1800228f3  pop     rbp
0x1800228f4  retn
```
