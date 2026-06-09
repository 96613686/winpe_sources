# dllmain_dispatch

- ea: `0x180009644`
- end: `0x18000976b`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009780`

## callees

- `0x1800058a0`
- `0x180009460`
- `0x180009644`
- `0x1800098cc`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001F390 <= 0 )
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
0x180009644  mov     rax, rsp
0x180009647  mov     [rax+20h], rbx
0x18000964b  mov     [rax+18h], r8
0x18000964f  mov     [rax+10h], edx
0x180009652  mov     [rax+8], rcx
0x180009656  push    rsi
0x180009657  push    rdi
0x180009658  push    r14
0x18000965a  sub     rsp, 40h
0x18000965e  mov     rsi, r8
0x180009661  mov     edi, edx
0x180009663  mov     r14, rcx
0x180009666  test    edx, edx
0x180009668  jnz     short loc_180009679
0x18000966a  cmp     cs:dword_18001F390, edx
0x180009670  jg      short loc_180009679
0x180009672  xor     eax, eax
0x180009674  jmp     loc_18000975D
0x180009679  lea     eax, [rdx-1]
0x18000967c  cmp     eax, 1
0x18000967f  ja      short loc_1800096C0
0x180009681  mov     rax, cs:_pRawDllMain
0x180009688  test    rax, rax
0x18000968b  jnz     short loc_180009692
0x18000968d  lea     ebx, [rax+1]
0x180009690  jmp     short loc_180009699
0x180009692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009697  mov     ebx, eax
0x180009699  mov     [rsp+58h+var_28], ebx
0x18000969d  test    ebx, ebx
0x18000969f  jz      loc_180009753
0x1800096a5  mov     r8, rsi
0x1800096a8  mov     edx, edi
0x1800096aa  mov     rcx, r14
0x1800096ad  call    dllmain_crt_dispatch
0x1800096b2  mov     ebx, eax
0x1800096b4  mov     [rsp+58h+var_28], eax
0x1800096b8  test    eax, eax
0x1800096ba  jz      loc_180009753
0x1800096c0  mov     r8, rsi; lpvReserved
0x1800096c3  mov     edx, edi; fdwReason
0x1800096c5  mov     rcx, r14; hinstDLL
0x1800096c8  call    DllMain
0x1800096cd  mov     ebx, eax
0x1800096cf  mov     [rsp+58h+var_28], eax
0x1800096d3  cmp     edi, 1
0x1800096d6  jnz     short loc_18000970F
0x1800096d8  test    eax, eax
0x1800096da  jnz     short loc_18000970F
0x1800096dc  mov     r8, rsi; lpvReserved
0x1800096df  xor     edx, edx; fdwReason
0x1800096e1  mov     rcx, r14; hinstDLL
0x1800096e4  call    DllMain
0x1800096e9  mov     r8, rsi
0x1800096ec  xor     edx, edx
0x1800096ee  mov     rcx, r14
0x1800096f1  call    dllmain_crt_dispatch
0x1800096f6  mov     rax, cs:_pRawDllMain
0x1800096fd  test    rax, rax
0x180009700  jz      short loc_18000970F
0x180009702  mov     r8, rsi
0x180009705  xor     edx, edx
0x180009707  mov     rcx, r14
0x18000970a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970f  test    edi, edi
0x180009711  jz      short loc_180009718
0x180009713  cmp     edi, 3
0x180009716  jnz     short loc_180009753
0x180009718  mov     r8, rsi
0x18000971b  mov     edx, edi
0x18000971d  mov     rcx, r14
0x180009720  call    dllmain_crt_dispatch
0x180009725  mov     ebx, eax
0x180009727  mov     [rsp+58h+var_28], eax
0x18000972b  test    eax, eax
0x18000972d  jz      short loc_180009753
0x18000972f  mov     rax, cs:_pRawDllMain
0x180009736  test    rax, rax
0x180009739  jnz     short loc_180009740
0x18000973b  lea     ebx, [rax+1]
0x18000973e  jmp     short loc_18000974F
0x180009740  mov     r8, rsi
0x180009743  mov     edx, edi
0x180009745  mov     rcx, r14
0x180009748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000974d  mov     ebx, eax
0x18000974f  mov     [rsp+58h+var_28], ebx
0x180009753  jmp     short loc_18000975B
0x180009755  xor     ebx, ebx
0x180009757  mov     [rsp+58h+var_28], ebx
0x18000975b  mov     eax, ebx
0x18000975d  mov     rbx, [rsp+58h+arg_18]
0x180009762  add     rsp, 40h
0x180009766  pop     r14
0x180009768  pop     rdi
0x180009769  pop     rsi
0x18000976a  retn
0x1800157bc  push    rbp
0x1800157be  sub     rsp, 30h
0x1800157c2  mov     rbp, rdx
0x1800157c5  mov     rax, [rcx]
0x1800157c8  mov     edx, [rax]
0x1800157ca  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800157cf  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800157d3  lea     r9, dllmain_crt_dispatch; int
0x1800157da  mov     r8, [rbp+70h]; int
0x1800157de  mov     edx, [rbp+68h]; int
0x1800157e1  mov     rcx, [rbp+60h]; int
0x1800157e5  call    __scrt_dllmain_exception_filter
0x1800157ea  nop
0x1800157eb  add     rsp, 30h
0x1800157ef  pop     rbp
0x1800157f0  retn
```
