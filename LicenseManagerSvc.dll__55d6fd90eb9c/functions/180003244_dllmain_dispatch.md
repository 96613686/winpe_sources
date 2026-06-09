# dllmain_dispatch

- ea: `0x180003244`
- end: `0x18000336b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003380`

## callees

- `0x180001df8`
- `0x180003060`
- `0x180003244`
- `0x18000378c`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180021610 <= 0 )
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
0x180003244  mov     rax, rsp
0x180003247  mov     [rax+20h], rbx
0x18000324b  mov     [rax+18h], r8
0x18000324f  mov     [rax+10h], edx
0x180003252  mov     [rax+8], rcx
0x180003256  push    rsi
0x180003257  push    rdi
0x180003258  push    r14
0x18000325a  sub     rsp, 40h
0x18000325e  mov     rsi, r8
0x180003261  mov     edi, edx
0x180003263  mov     r14, rcx
0x180003266  test    edx, edx
0x180003268  jnz     short loc_180003279
0x18000326a  cmp     cs:dword_180021610, edx
0x180003270  jg      short loc_180003279
0x180003272  xor     eax, eax
0x180003274  jmp     loc_18000335D
0x180003279  lea     eax, [rdx-1]
0x18000327c  cmp     eax, 1
0x18000327f  ja      short loc_1800032C0
0x180003281  mov     rax, cs:_pRawDllMain
0x180003288  test    rax, rax
0x18000328b  jnz     short loc_180003292
0x18000328d  lea     ebx, [rax+1]
0x180003290  jmp     short loc_180003299
0x180003292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003297  mov     ebx, eax
0x180003299  mov     [rsp+58h+var_28], ebx
0x18000329d  test    ebx, ebx
0x18000329f  jz      loc_180003353
0x1800032a5  mov     r8, rsi
0x1800032a8  mov     edx, edi
0x1800032aa  mov     rcx, r14
0x1800032ad  call    dllmain_crt_dispatch
0x1800032b2  mov     ebx, eax
0x1800032b4  mov     [rsp+58h+var_28], eax
0x1800032b8  test    eax, eax
0x1800032ba  jz      loc_180003353
0x1800032c0  mov     r8, rsi; lpvReserved
0x1800032c3  mov     edx, edi; fdwReason
0x1800032c5  mov     rcx, r14; hinstDLL
0x1800032c8  call    DllMain
0x1800032cd  mov     ebx, eax
0x1800032cf  mov     [rsp+58h+var_28], eax
0x1800032d3  cmp     edi, 1
0x1800032d6  jnz     short loc_18000330F
0x1800032d8  test    eax, eax
0x1800032da  jnz     short loc_18000330F
0x1800032dc  mov     r8, rsi; lpvReserved
0x1800032df  xor     edx, edx; fdwReason
0x1800032e1  mov     rcx, r14; hinstDLL
0x1800032e4  call    DllMain
0x1800032e9  mov     r8, rsi
0x1800032ec  xor     edx, edx
0x1800032ee  mov     rcx, r14
0x1800032f1  call    dllmain_crt_dispatch
0x1800032f6  mov     rax, cs:_pRawDllMain
0x1800032fd  test    rax, rax
0x180003300  jz      short loc_18000330F
0x180003302  mov     r8, rsi
0x180003305  xor     edx, edx
0x180003307  mov     rcx, r14
0x18000330a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000330f  test    edi, edi
0x180003311  jz      short loc_180003318
0x180003313  cmp     edi, 3
0x180003316  jnz     short loc_180003353
0x180003318  mov     r8, rsi
0x18000331b  mov     edx, edi
0x18000331d  mov     rcx, r14
0x180003320  call    dllmain_crt_dispatch
0x180003325  mov     ebx, eax
0x180003327  mov     [rsp+58h+var_28], eax
0x18000332b  test    eax, eax
0x18000332d  jz      short loc_180003353
0x18000332f  mov     rax, cs:_pRawDllMain
0x180003336  test    rax, rax
0x180003339  jnz     short loc_180003340
0x18000333b  lea     ebx, [rax+1]
0x18000333e  jmp     short loc_18000334F
0x180003340  mov     r8, rsi
0x180003343  mov     edx, edi
0x180003345  mov     rcx, r14
0x180003348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334d  mov     ebx, eax
0x18000334f  mov     [rsp+58h+var_28], ebx
0x180003353  jmp     short loc_18000335B
0x180003355  xor     ebx, ebx
0x180003357  mov     [rsp+58h+var_28], ebx
0x18000335b  mov     eax, ebx
0x18000335d  mov     rbx, [rsp+58h+arg_18]
0x180003362  add     rsp, 40h
0x180003366  pop     r14
0x180003368  pop     rdi
0x180003369  pop     rsi
0x18000336a  retn
0x18001755e  push    rbp
0x180017560  sub     rsp, 30h
0x180017564  mov     rbp, rdx
0x180017567  mov     rax, [rcx]
0x18001756a  mov     edx, [rax]
0x18001756c  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180017571  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180017575  lea     r9, dllmain_crt_dispatch; int
0x18001757c  mov     r8, [rbp+70h]; int
0x180017580  mov     edx, [rbp+68h]; int
0x180017583  mov     rcx, [rbp+60h]; int
0x180017587  call    __scrt_dllmain_exception_filter
0x18001758c  nop
0x18001758d  add     rsp, 30h
0x180017591  pop     rbp
0x180017592  retn
```
