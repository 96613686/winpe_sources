# dllmain_dispatch

- ea: `0x180001394`
- end: `0x1800014bb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014d0`

## callees

- `0x1800011b0`
- `0x180001394`
- `0x1800017ec`
- `0x180006348`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180030250 <= 0 )
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
0x180001394  mov     rax, rsp
0x180001397  mov     [rax+20h], rbx
0x18000139b  mov     [rax+18h], r8
0x18000139f  mov     [rax+10h], edx
0x1800013a2  mov     [rax+8], rcx
0x1800013a6  push    rsi
0x1800013a7  push    rdi
0x1800013a8  push    r14
0x1800013aa  sub     rsp, 40h
0x1800013ae  mov     rsi, r8
0x1800013b1  mov     edi, edx
0x1800013b3  mov     r14, rcx
0x1800013b6  test    edx, edx
0x1800013b8  jnz     short loc_1800013C9
0x1800013ba  cmp     cs:dword_180030250, edx
0x1800013c0  jg      short loc_1800013C9
0x1800013c2  xor     eax, eax
0x1800013c4  jmp     loc_1800014AD
0x1800013c9  lea     eax, [rdx-1]
0x1800013cc  cmp     eax, 1
0x1800013cf  ja      short loc_180001410
0x1800013d1  mov     rax, cs:_pRawDllMain
0x1800013d8  test    rax, rax
0x1800013db  jnz     short loc_1800013E2
0x1800013dd  lea     ebx, [rax+1]
0x1800013e0  jmp     short loc_1800013E9
0x1800013e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013e7  mov     ebx, eax
0x1800013e9  mov     [rsp+58h+var_28], ebx
0x1800013ed  test    ebx, ebx
0x1800013ef  jz      loc_1800014A3
0x1800013f5  mov     r8, rsi
0x1800013f8  mov     edx, edi
0x1800013fa  mov     rcx, r14
0x1800013fd  call    dllmain_crt_dispatch
0x180001402  mov     ebx, eax
0x180001404  mov     [rsp+58h+var_28], eax
0x180001408  test    eax, eax
0x18000140a  jz      loc_1800014A3
0x180001410  mov     r8, rsi; lpvReserved
0x180001413  mov     edx, edi; fdwReason
0x180001415  mov     rcx, r14; hinstDLL
0x180001418  call    DllMain
0x18000141d  mov     ebx, eax
0x18000141f  mov     [rsp+58h+var_28], eax
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000145F
0x180001428  test    eax, eax
0x18000142a  jnz     short loc_18000145F
0x18000142c  mov     r8, rsi; lpvReserved
0x18000142f  xor     edx, edx; fdwReason
0x180001431  mov     rcx, r14; hinstDLL
0x180001434  call    DllMain
0x180001439  mov     r8, rsi
0x18000143c  xor     edx, edx
0x18000143e  mov     rcx, r14
0x180001441  call    dllmain_crt_dispatch
0x180001446  mov     rax, cs:_pRawDllMain
0x18000144d  test    rax, rax
0x180001450  jz      short loc_18000145F
0x180001452  mov     r8, rsi
0x180001455  xor     edx, edx
0x180001457  mov     rcx, r14
0x18000145a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000145f  test    edi, edi
0x180001461  jz      short loc_180001468
0x180001463  cmp     edi, 3
0x180001466  jnz     short loc_1800014A3
0x180001468  mov     r8, rsi
0x18000146b  mov     edx, edi
0x18000146d  mov     rcx, r14
0x180001470  call    dllmain_crt_dispatch
0x180001475  mov     ebx, eax
0x180001477  mov     [rsp+58h+var_28], eax
0x18000147b  test    eax, eax
0x18000147d  jz      short loc_1800014A3
0x18000147f  mov     rax, cs:_pRawDllMain
0x180001486  test    rax, rax
0x180001489  jnz     short loc_180001490
0x18000148b  lea     ebx, [rax+1]
0x18000148e  jmp     short loc_18000149F
0x180001490  mov     r8, rsi
0x180001493  mov     edx, edi
0x180001495  mov     rcx, r14
0x180001498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000149d  mov     ebx, eax
0x18000149f  mov     [rsp+58h+var_28], ebx
0x1800014a3  jmp     short loc_1800014AB
0x1800014a5  xor     ebx, ebx
0x1800014a7  mov     [rsp+58h+var_28], ebx
0x1800014ab  mov     eax, ebx
0x1800014ad  mov     rbx, [rsp+58h+arg_18]
0x1800014b2  add     rsp, 40h
0x1800014b6  pop     r14
0x1800014b8  pop     rdi
0x1800014b9  pop     rsi
0x1800014ba  retn
0x18001d5ec  push    rbp
0x18001d5ee  sub     rsp, 30h
0x18001d5f2  mov     rbp, rdx
0x18001d5f5  mov     rax, [rcx]
0x18001d5f8  mov     edx, [rax]
0x18001d5fa  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x18001d5ff  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x18001d603  lea     r9, dllmain_crt_dispatch; int
0x18001d60a  mov     r8, [rbp+70h]; int
0x18001d60e  mov     edx, [rbp+68h]; int
0x18001d611  mov     rcx, [rbp+60h]; int
0x18001d615  call    __scrt_dllmain_exception_filter
0x18001d61a  nop
0x18001d61b  add     rsp, 30h
0x18001d61f  pop     rbp
0x18001d620  retn
```
