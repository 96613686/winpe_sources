# dllmain_dispatch

- ea: `0x180002044`
- end: `0x18000216b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002180`

## callees

- `0x180001d50`
- `0x180001e60`
- `0x180002044`
- `0x180002304`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18002E650 <= 0 )
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
0x180002044  mov     rax, rsp
0x180002047  mov     [rax+20h], rbx
0x18000204b  mov     [rax+18h], r8
0x18000204f  mov     [rax+10h], edx
0x180002052  mov     [rax+8], rcx
0x180002056  push    rsi
0x180002057  push    rdi
0x180002058  push    r14
0x18000205a  sub     rsp, 40h
0x18000205e  mov     rsi, r8
0x180002061  mov     edi, edx
0x180002063  mov     r14, rcx
0x180002066  test    edx, edx
0x180002068  jnz     short loc_180002079
0x18000206a  cmp     cs:dword_18002E650, edx
0x180002070  jg      short loc_180002079
0x180002072  xor     eax, eax
0x180002074  jmp     loc_18000215D
0x180002079  lea     eax, [rdx-1]
0x18000207c  cmp     eax, 1
0x18000207f  ja      short loc_1800020C0
0x180002081  mov     rax, cs:_pRawDllMain
0x180002088  test    rax, rax
0x18000208b  jnz     short loc_180002092
0x18000208d  lea     ebx, [rax+1]
0x180002090  jmp     short loc_180002099
0x180002092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002097  mov     ebx, eax
0x180002099  mov     [rsp+58h+var_28], ebx
0x18000209d  test    ebx, ebx
0x18000209f  jz      loc_180002153
0x1800020a5  mov     r8, rsi
0x1800020a8  mov     edx, edi
0x1800020aa  mov     rcx, r14
0x1800020ad  call    dllmain_crt_dispatch
0x1800020b2  mov     ebx, eax
0x1800020b4  mov     [rsp+58h+var_28], eax
0x1800020b8  test    eax, eax
0x1800020ba  jz      loc_180002153
0x1800020c0  mov     r8, rsi; lpvReserved
0x1800020c3  mov     edx, edi; fdwReason
0x1800020c5  mov     rcx, r14; hinstDLL
0x1800020c8  call    DllMain
0x1800020cd  mov     ebx, eax
0x1800020cf  mov     [rsp+58h+var_28], eax
0x1800020d3  cmp     edi, 1
0x1800020d6  jnz     short loc_18000210F
0x1800020d8  test    eax, eax
0x1800020da  jnz     short loc_18000210F
0x1800020dc  mov     r8, rsi; lpvReserved
0x1800020df  xor     edx, edx; fdwReason
0x1800020e1  mov     rcx, r14; hinstDLL
0x1800020e4  call    DllMain
0x1800020e9  mov     r8, rsi
0x1800020ec  xor     edx, edx
0x1800020ee  mov     rcx, r14
0x1800020f1  call    dllmain_crt_dispatch
0x1800020f6  mov     rax, cs:_pRawDllMain
0x1800020fd  test    rax, rax
0x180002100  jz      short loc_18000210F
0x180002102  mov     r8, rsi
0x180002105  xor     edx, edx
0x180002107  mov     rcx, r14
0x18000210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000210f  test    edi, edi
0x180002111  jz      short loc_180002118
0x180002113  cmp     edi, 3
0x180002116  jnz     short loc_180002153
0x180002118  mov     r8, rsi
0x18000211b  mov     edx, edi
0x18000211d  mov     rcx, r14
0x180002120  call    dllmain_crt_dispatch
0x180002125  mov     ebx, eax
0x180002127  mov     [rsp+58h+var_28], eax
0x18000212b  test    eax, eax
0x18000212d  jz      short loc_180002153
0x18000212f  mov     rax, cs:_pRawDllMain
0x180002136  test    rax, rax
0x180002139  jnz     short loc_180002140
0x18000213b  lea     ebx, [rax+1]
0x18000213e  jmp     short loc_18000214F
0x180002140  mov     r8, rsi
0x180002143  mov     edx, edi
0x180002145  mov     rcx, r14
0x180002148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000214d  mov     ebx, eax
0x18000214f  mov     [rsp+58h+var_28], ebx
0x180002153  jmp     short loc_18000215B
0x180002155  xor     ebx, ebx
0x180002157  mov     [rsp+58h+var_28], ebx
0x18000215b  mov     eax, ebx
0x18000215d  mov     rbx, [rsp+58h+arg_18]
0x180002162  add     rsp, 40h
0x180002166  pop     r14
0x180002168  pop     rdi
0x180002169  pop     rsi
0x18000216a  retn
0x18002201c  push    rbp
0x18002201e  sub     rsp, 30h
0x180022022  mov     rbp, rdx
0x180022025  mov     rax, [rcx]
0x180022028  mov     edx, [rax]
0x18002202a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18002202f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180022033  lea     r9, dllmain_crt_dispatch; int
0x18002203a  mov     r8, [rbp+70h]; int
0x18002203e  mov     edx, [rbp+68h]; int
0x180022041  mov     rcx, [rbp+60h]; int
0x180022045  call    __scrt_dllmain_exception_filter
0x18002204a  nop
0x18002204b  add     rsp, 30h
0x18002204f  pop     rbp
0x180022050  retn
```
