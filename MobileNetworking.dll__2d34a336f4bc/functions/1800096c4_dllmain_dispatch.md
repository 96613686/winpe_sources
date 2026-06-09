# dllmain_dispatch

- ea: `0x1800096c4`
- end: `0x1800097eb`
- name: `dllmain_dispatch`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180009800`

## callees

- `0x1800094e0`
- `0x1800096c4`
- `0x180009a54`
- `0x18000af3c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_18001B230 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (pRawDllMain ? (v7 = ((__int64 (*)(void))pRawDllMain)()) : (v7 = 1),
        v7 && (v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved)) != 0) )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_dispatch((__int64)hinstDLL, 0, (__int64)lpvReserved);
      if ( pRawDllMain )
        pRawDllMain(hinstDLL, 0, lpvReserved);
    }
    if ( !fdwReason || fdwReason == 3 )
    {
      v7 = dllmain_crt_dispatch((__int64)hinstDLL, fdwReason, (__int64)lpvReserved);
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
0x1800096c4  mov     rax, rsp
0x1800096c7  mov     [rax+20h], rbx
0x1800096cb  mov     [rax+18h], r8
0x1800096cf  mov     [rax+10h], edx
0x1800096d2  mov     [rax+8], rcx
0x1800096d6  push    rsi
0x1800096d7  push    rdi
0x1800096d8  push    r14
0x1800096da  sub     rsp, 40h
0x1800096de  mov     rsi, r8
0x1800096e1  mov     edi, edx
0x1800096e3  mov     r14, rcx
0x1800096e6  test    edx, edx
0x1800096e8  jnz     short loc_1800096F9
0x1800096ea  cmp     cs:dword_18001B230, edx
0x1800096f0  jg      short loc_1800096F9
0x1800096f2  xor     eax, eax
0x1800096f4  jmp     loc_1800097DD
0x1800096f9  lea     eax, [rdx-1]
0x1800096fc  cmp     eax, 1
0x1800096ff  ja      short loc_180009740
0x180009701  mov     rax, cs:_pRawDllMain
0x180009708  test    rax, rax
0x18000970b  jnz     short loc_180009712
0x18000970d  lea     ebx, [rax+1]
0x180009710  jmp     short loc_180009719
0x180009712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009717  mov     ebx, eax
0x180009719  mov     [rsp+58h+var_28], ebx
0x18000971d  test    ebx, ebx
0x18000971f  jz      loc_1800097D3
0x180009725  mov     r8, rsi
0x180009728  mov     edx, edi
0x18000972a  mov     rcx, r14
0x18000972d  call    dllmain_crt_dispatch
0x180009732  mov     ebx, eax
0x180009734  mov     [rsp+58h+var_28], eax
0x180009738  test    eax, eax
0x18000973a  jz      loc_1800097D3
0x180009740  mov     r8, rsi; lpvReserved
0x180009743  mov     edx, edi; fdwReason
0x180009745  mov     rcx, r14; hinstDLL
0x180009748  call    DllMain
0x18000974d  mov     ebx, eax
0x18000974f  mov     [rsp+58h+var_28], eax
0x180009753  cmp     edi, 1
0x180009756  jnz     short loc_18000978F
0x180009758  test    eax, eax
0x18000975a  jnz     short loc_18000978F
0x18000975c  mov     r8, rsi; lpvReserved
0x18000975f  xor     edx, edx; fdwReason
0x180009761  mov     rcx, r14; hinstDLL
0x180009764  call    DllMain
0x180009769  mov     r8, rsi
0x18000976c  xor     edx, edx
0x18000976e  mov     rcx, r14
0x180009771  call    dllmain_crt_dispatch
0x180009776  mov     rax, cs:_pRawDllMain
0x18000977d  test    rax, rax
0x180009780  jz      short loc_18000978F
0x180009782  mov     r8, rsi
0x180009785  xor     edx, edx
0x180009787  mov     rcx, r14
0x18000978a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000978f  test    edi, edi
0x180009791  jz      short loc_180009798
0x180009793  cmp     edi, 3
0x180009796  jnz     short loc_1800097D3
0x180009798  mov     r8, rsi
0x18000979b  mov     edx, edi
0x18000979d  mov     rcx, r14
0x1800097a0  call    dllmain_crt_dispatch
0x1800097a5  mov     ebx, eax
0x1800097a7  mov     [rsp+58h+var_28], eax
0x1800097ab  test    eax, eax
0x1800097ad  jz      short loc_1800097D3
0x1800097af  mov     rax, cs:_pRawDllMain
0x1800097b6  test    rax, rax
0x1800097b9  jnz     short loc_1800097C0
0x1800097bb  lea     ebx, [rax+1]
0x1800097be  jmp     short loc_1800097CF
0x1800097c0  mov     r8, rsi
0x1800097c3  mov     edx, edi
0x1800097c5  mov     rcx, r14
0x1800097c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097cd  mov     ebx, eax
0x1800097cf  mov     [rsp+58h+var_28], ebx
0x1800097d3  jmp     short loc_1800097DB
0x1800097d5  xor     ebx, ebx
0x1800097d7  mov     [rsp+58h+var_28], ebx
0x1800097db  mov     eax, ebx
0x1800097dd  mov     rbx, [rsp+58h+arg_18]
0x1800097e2  add     rsp, 40h
0x1800097e6  pop     r14
0x1800097e8  pop     rdi
0x1800097e9  pop     rsi
0x1800097ea  retn
0x1800119e5  push    rbp
0x1800119e7  sub     rsp, 30h
0x1800119eb  mov     rbp, rdx
0x1800119ee  mov     rax, [rcx]
0x1800119f1  mov     edx, [rax]
0x1800119f3  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x1800119f8  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x1800119fc  lea     r9, dllmain_crt_dispatch; int
0x180011a03  mov     r8, [rbp+70h]; int
0x180011a07  mov     edx, [rbp+68h]; int
0x180011a0a  mov     rcx, [rbp+60h]; int
0x180011a0e  call    __scrt_dllmain_exception_filter
0x180011a13  nop
0x180011a14  add     rsp, 30h
0x180011a18  pop     rbp
0x180011a19  retn
```
