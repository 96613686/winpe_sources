# dllmain_dispatch

- ea: `0x180003234`
- end: `0x18000335b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003370`

## callees

- `0x180003050`
- `0x180003234`
- `0x18000353c`
- `0x18000b514`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001A410 <= 0 )
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
0x180003234  mov     rax, rsp
0x180003237  mov     [rax+20h], rbx
0x18000323b  mov     [rax+18h], r8
0x18000323f  mov     [rax+10h], edx
0x180003242  mov     [rax+8], rcx
0x180003246  push    rsi
0x180003247  push    rdi
0x180003248  push    r14
0x18000324a  sub     rsp, 40h
0x18000324e  mov     rsi, r8
0x180003251  mov     edi, edx
0x180003253  mov     r14, rcx
0x180003256  test    edx, edx
0x180003258  jnz     short loc_180003269
0x18000325a  cmp     cs:dword_18001A410, edx
0x180003260  jg      short loc_180003269
0x180003262  xor     eax, eax
0x180003264  jmp     loc_18000334D
0x180003269  lea     eax, [rdx-1]
0x18000326c  cmp     eax, 1
0x18000326f  ja      short loc_1800032B0
0x180003271  mov     rax, cs:_pRawDllMain
0x180003278  test    rax, rax
0x18000327b  jnz     short loc_180003282
0x18000327d  lea     ebx, [rax+1]
0x180003280  jmp     short loc_180003289
0x180003282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003287  mov     ebx, eax
0x180003289  mov     [rsp+58h+var_28], ebx
0x18000328d  test    ebx, ebx
0x18000328f  jz      loc_180003343
0x180003295  mov     r8, rsi
0x180003298  mov     edx, edi
0x18000329a  mov     rcx, r14
0x18000329d  call    dllmain_crt_dispatch
0x1800032a2  mov     ebx, eax
0x1800032a4  mov     [rsp+58h+var_28], eax
0x1800032a8  test    eax, eax
0x1800032aa  jz      loc_180003343
0x1800032b0  mov     r8, rsi; lpvReserved
0x1800032b3  mov     edx, edi; fdwReason
0x1800032b5  mov     rcx, r14; hinstDLL
0x1800032b8  call    DllMain
0x1800032bd  mov     ebx, eax
0x1800032bf  mov     [rsp+58h+var_28], eax
0x1800032c3  cmp     edi, 1
0x1800032c6  jnz     short loc_1800032FF
0x1800032c8  test    eax, eax
0x1800032ca  jnz     short loc_1800032FF
0x1800032cc  mov     r8, rsi; lpvReserved
0x1800032cf  xor     edx, edx; fdwReason
0x1800032d1  mov     rcx, r14; hinstDLL
0x1800032d4  call    DllMain
0x1800032d9  mov     r8, rsi
0x1800032dc  xor     edx, edx
0x1800032de  mov     rcx, r14
0x1800032e1  call    dllmain_crt_dispatch
0x1800032e6  mov     rax, cs:_pRawDllMain
0x1800032ed  test    rax, rax
0x1800032f0  jz      short loc_1800032FF
0x1800032f2  mov     r8, rsi
0x1800032f5  xor     edx, edx
0x1800032f7  mov     rcx, r14
0x1800032fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ff  test    edi, edi
0x180003301  jz      short loc_180003308
0x180003303  cmp     edi, 3
0x180003306  jnz     short loc_180003343
0x180003308  mov     r8, rsi
0x18000330b  mov     edx, edi
0x18000330d  mov     rcx, r14
0x180003310  call    dllmain_crt_dispatch
0x180003315  mov     ebx, eax
0x180003317  mov     [rsp+58h+var_28], eax
0x18000331b  test    eax, eax
0x18000331d  jz      short loc_180003343
0x18000331f  mov     rax, cs:_pRawDllMain
0x180003326  test    rax, rax
0x180003329  jnz     short loc_180003330
0x18000332b  lea     ebx, [rax+1]
0x18000332e  jmp     short loc_18000333F
0x180003330  mov     r8, rsi
0x180003333  mov     edx, edi
0x180003335  mov     rcx, r14
0x180003338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333d  mov     ebx, eax
0x18000333f  mov     [rsp+58h+var_28], ebx
0x180003343  jmp     short loc_18000334B
0x180003345  xor     ebx, ebx
0x180003347  mov     [rsp+58h+var_28], ebx
0x18000334b  mov     eax, ebx
0x18000334d  mov     rbx, [rsp+58h+arg_18]
0x180003352  add     rsp, 40h
0x180003356  pop     r14
0x180003358  pop     rdi
0x180003359  pop     rsi
0x18000335a  retn
0x1800120ac  push    rbp
0x1800120ae  sub     rsp, 30h
0x1800120b2  mov     rbp, rdx
0x1800120b5  mov     rax, [rcx]
0x1800120b8  mov     edx, [rax]
0x1800120ba  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800120bf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800120c3  lea     r9, dllmain_crt_dispatch; int
0x1800120ca  mov     r8, [rbp+70h]; int
0x1800120ce  mov     edx, [rbp+68h]; int
0x1800120d1  mov     rcx, [rbp+60h]; int
0x1800120d5  call    __scrt_dllmain_exception_filter
0x1800120da  nop
0x1800120db  add     rsp, 30h
0x1800120df  pop     rbp
0x1800120e0  retn
```
