# dllmain_dispatch

- ea: `0x180003394`
- end: `0x1800034bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800034d0`

## callees

- `0x1800031b0`
- `0x180003394`
- `0x180003754`
- `0x180022e90`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180037518 <= 0 )
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
0x180003394  mov     rax, rsp
0x180003397  mov     [rax+20h], rbx
0x18000339b  mov     [rax+18h], r8
0x18000339f  mov     [rax+10h], edx
0x1800033a2  mov     [rax+8], rcx
0x1800033a6  push    rsi
0x1800033a7  push    rdi
0x1800033a8  push    r14
0x1800033aa  sub     rsp, 40h
0x1800033ae  mov     rsi, r8
0x1800033b1  mov     edi, edx
0x1800033b3  mov     r14, rcx
0x1800033b6  test    edx, edx
0x1800033b8  jnz     short loc_1800033C9
0x1800033ba  cmp     cs:dword_180037518, edx
0x1800033c0  jg      short loc_1800033C9
0x1800033c2  xor     eax, eax
0x1800033c4  jmp     loc_1800034AD
0x1800033c9  lea     eax, [rdx-1]
0x1800033cc  cmp     eax, 1
0x1800033cf  ja      short loc_180003410
0x1800033d1  mov     rax, cs:_pRawDllMain
0x1800033d8  test    rax, rax
0x1800033db  jnz     short loc_1800033E2
0x1800033dd  lea     ebx, [rax+1]
0x1800033e0  jmp     short loc_1800033E9
0x1800033e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e7  mov     ebx, eax
0x1800033e9  mov     [rsp+58h+var_28], ebx
0x1800033ed  test    ebx, ebx
0x1800033ef  jz      loc_1800034A3
0x1800033f5  mov     r8, rsi
0x1800033f8  mov     edx, edi
0x1800033fa  mov     rcx, r14
0x1800033fd  call    dllmain_crt_dispatch
0x180003402  mov     ebx, eax
0x180003404  mov     [rsp+58h+var_28], eax
0x180003408  test    eax, eax
0x18000340a  jz      loc_1800034A3
0x180003410  mov     r8, rsi; lpvReserved
0x180003413  mov     edx, edi; fdwReason
0x180003415  mov     rcx, r14; hinstDLL
0x180003418  call    DllMain
0x18000341d  mov     ebx, eax
0x18000341f  mov     [rsp+58h+var_28], eax
0x180003423  cmp     edi, 1
0x180003426  jnz     short loc_18000345F
0x180003428  test    eax, eax
0x18000342a  jnz     short loc_18000345F
0x18000342c  mov     r8, rsi; lpvReserved
0x18000342f  xor     edx, edx; fdwReason
0x180003431  mov     rcx, r14; hinstDLL
0x180003434  call    DllMain
0x180003439  mov     r8, rsi
0x18000343c  xor     edx, edx
0x18000343e  mov     rcx, r14
0x180003441  call    dllmain_crt_dispatch
0x180003446  mov     rax, cs:_pRawDllMain
0x18000344d  test    rax, rax
0x180003450  jz      short loc_18000345F
0x180003452  mov     r8, rsi
0x180003455  xor     edx, edx
0x180003457  mov     rcx, r14
0x18000345a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345f  test    edi, edi
0x180003461  jz      short loc_180003468
0x180003463  cmp     edi, 3
0x180003466  jnz     short loc_1800034A3
0x180003468  mov     r8, rsi
0x18000346b  mov     edx, edi
0x18000346d  mov     rcx, r14
0x180003470  call    dllmain_crt_dispatch
0x180003475  mov     ebx, eax
0x180003477  mov     [rsp+58h+var_28], eax
0x18000347b  test    eax, eax
0x18000347d  jz      short loc_1800034A3
0x18000347f  mov     rax, cs:_pRawDllMain
0x180003486  test    rax, rax
0x180003489  jnz     short loc_180003490
0x18000348b  lea     ebx, [rax+1]
0x18000348e  jmp     short loc_18000349F
0x180003490  mov     r8, rsi
0x180003493  mov     edx, edi
0x180003495  mov     rcx, r14
0x180003498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349d  mov     ebx, eax
0x18000349f  mov     [rsp+58h+var_28], ebx
0x1800034a3  jmp     short loc_1800034AB
0x1800034a5  xor     ebx, ebx
0x1800034a7  mov     [rsp+58h+var_28], ebx
0x1800034ab  mov     eax, ebx
0x1800034ad  mov     rbx, [rsp+58h+arg_18]
0x1800034b2  add     rsp, 40h
0x1800034b6  pop     r14
0x1800034b8  pop     rdi
0x1800034b9  pop     rsi
0x1800034ba  retn
0x180027dbc  push    rbp
0x180027dbe  sub     rsp, 30h
0x180027dc2  mov     rbp, rdx
0x180027dc5  mov     rax, [rcx]
0x180027dc8  mov     edx, [rax]
0x180027dca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180027dcf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180027dd3  lea     r9, dllmain_crt_dispatch; int
0x180027dda  mov     r8, [rbp+70h]; int
0x180027dde  mov     edx, [rbp+68h]; int
0x180027de1  mov     rcx, [rbp+60h]; int
0x180027de5  call    __scrt_dllmain_exception_filter
0x180027dea  nop
0x180027deb  add     rsp, 30h
0x180027def  pop     rbp
0x180027df0  retn
```
