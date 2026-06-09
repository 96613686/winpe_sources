# dllmain_dispatch

- ea: `0x1800013c4`
- end: `0x1800014eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001500`

## callees

- `0x1800011e0`
- `0x1800013c4`
- `0x180001678`
- `0x180007420`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18000F2B0 <= 0 )
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
0x1800013c4  mov     rax, rsp
0x1800013c7  mov     [rax+20h], rbx
0x1800013cb  mov     [rax+18h], r8
0x1800013cf  mov     [rax+10h], edx
0x1800013d2  mov     [rax+8], rcx
0x1800013d6  push    rsi
0x1800013d7  push    rdi
0x1800013d8  push    r14
0x1800013da  sub     rsp, 40h
0x1800013de  mov     rsi, r8
0x1800013e1  mov     edi, edx
0x1800013e3  mov     r14, rcx
0x1800013e6  test    edx, edx
0x1800013e8  jnz     short loc_1800013F9
0x1800013ea  cmp     cs:dword_18000F2B0, edx
0x1800013f0  jg      short loc_1800013F9
0x1800013f2  xor     eax, eax
0x1800013f4  jmp     loc_1800014DD
0x1800013f9  lea     eax, [rdx-1]
0x1800013fc  cmp     eax, 1
0x1800013ff  ja      short loc_180001440
0x180001401  mov     rax, cs:_pRawDllMain
0x180001408  test    rax, rax
0x18000140b  jnz     short loc_180001412
0x18000140d  lea     ebx, [rax+1]
0x180001410  jmp     short loc_180001419
0x180001412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001417  mov     ebx, eax
0x180001419  mov     [rsp+58h+var_28], ebx
0x18000141d  test    ebx, ebx
0x18000141f  jz      loc_1800014D3
0x180001425  mov     r8, rsi
0x180001428  mov     edx, edi
0x18000142a  mov     rcx, r14
0x18000142d  call    dllmain_crt_dispatch
0x180001432  mov     ebx, eax
0x180001434  mov     [rsp+58h+var_28], eax
0x180001438  test    eax, eax
0x18000143a  jz      loc_1800014D3
0x180001440  mov     r8, rsi; lpvReserved
0x180001443  mov     edx, edi; fdwReason
0x180001445  mov     rcx, r14; hinstDLL
0x180001448  call    DllMain
0x18000144d  mov     ebx, eax
0x18000144f  mov     [rsp+58h+var_28], eax
0x180001453  cmp     edi, 1
0x180001456  jnz     short loc_18000148F
0x180001458  test    eax, eax
0x18000145a  jnz     short loc_18000148F
0x18000145c  mov     r8, rsi; lpvReserved
0x18000145f  xor     edx, edx; fdwReason
0x180001461  mov     rcx, r14; hinstDLL
0x180001464  call    DllMain
0x180001469  mov     r8, rsi
0x18000146c  xor     edx, edx
0x18000146e  mov     rcx, r14
0x180001471  call    dllmain_crt_dispatch
0x180001476  mov     rax, cs:_pRawDllMain
0x18000147d  test    rax, rax
0x180001480  jz      short loc_18000148F
0x180001482  mov     r8, rsi
0x180001485  xor     edx, edx
0x180001487  mov     rcx, r14
0x18000148a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000148f  test    edi, edi
0x180001491  jz      short loc_180001498
0x180001493  cmp     edi, 3
0x180001496  jnz     short loc_1800014D3
0x180001498  mov     r8, rsi
0x18000149b  mov     edx, edi
0x18000149d  mov     rcx, r14
0x1800014a0  call    dllmain_crt_dispatch
0x1800014a5  mov     ebx, eax
0x1800014a7  mov     [rsp+58h+var_28], eax
0x1800014ab  test    eax, eax
0x1800014ad  jz      short loc_1800014D3
0x1800014af  mov     rax, cs:_pRawDllMain
0x1800014b6  test    rax, rax
0x1800014b9  jnz     short loc_1800014C0
0x1800014bb  lea     ebx, [rax+1]
0x1800014be  jmp     short loc_1800014CF
0x1800014c0  mov     r8, rsi
0x1800014c3  mov     edx, edi
0x1800014c5  mov     rcx, r14
0x1800014c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014cd  mov     ebx, eax
0x1800014cf  mov     [rsp+58h+var_28], ebx
0x1800014d3  jmp     short loc_1800014DB
0x1800014d5  xor     ebx, ebx
0x1800014d7  mov     [rsp+58h+var_28], ebx
0x1800014db  mov     eax, ebx
0x1800014dd  mov     rbx, [rsp+58h+arg_18]
0x1800014e2  add     rsp, 40h
0x1800014e6  pop     r14
0x1800014e8  pop     rdi
0x1800014e9  pop     rsi
0x1800014ea  retn
0x18000a04c  push    rbp
0x18000a04e  sub     rsp, 30h
0x18000a052  mov     rbp, rdx
0x18000a055  mov     rax, [rcx]
0x18000a058  mov     edx, [rax]
0x18000a05a  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18000a05f  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18000a063  lea     r9, dllmain_crt_dispatch; int
0x18000a06a  mov     r8, [rbp+70h]; int
0x18000a06e  mov     edx, [rbp+68h]; int
0x18000a071  mov     rcx, [rbp+60h]; int
0x18000a075  call    __scrt_dllmain_exception_filter
0x18000a07a  nop
0x18000a07b  add     rsp, 30h
0x18000a07f  pop     rbp
0x18000a080  retn
```
