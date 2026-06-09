# dllmain_dispatch

- ea: `0x18000133c`
- end: `0x18000146d`
- name: `dllmain_dispatch`
- size: `305`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180001470`

## callees

- `0x180001058`
- `0x180001150`
- `0x1800012b8`
- `0x18000133c`
- `0x18000171c`
- `0x180001f00`

## pseudocode

```c
__int64 __fastcall dllmain_dispatch(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  unsigned int v7; // ebx
  BOOL v8; // eax

  if ( !fdwReason && dword_180003048 <= 0 )
    return 0;
  if ( fdwReason - 1 > 1
    || (!pRawDllMain || (v7 = ((__int64 (*)(void))pRawDllMain)()) != 0)
    && (v7 = dllmain_crt_dispatch(hinstDLL, fdwReason, lpvReserved)) != 0 )
  {
    v8 = DllMain(hinstDLL, fdwReason, lpvReserved);
    v7 = v8;
    if ( fdwReason == 1 && !v8 )
    {
      DllMain(hinstDLL, 0, lpvReserved);
      dllmain_crt_process_detach(lpvReserved != 0);
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
0x18000133c  mov     rax, rsp
0x18000133f  mov     [rax+20h], rbx
0x180001343  mov     [rax+18h], r8
0x180001347  mov     [rax+10h], edx
0x18000134a  mov     [rax+8], rcx
0x18000134e  push    rsi
0x18000134f  push    rdi
0x180001350  push    r14
0x180001352  sub     rsp, 40h
0x180001356  mov     rsi, r8
0x180001359  mov     edi, edx
0x18000135b  mov     r14, rcx
0x18000135e  test    edx, edx
0x180001360  jnz     short loc_180001371
0x180001362  cmp     cs:dword_180003048, edx
0x180001368  jg      short loc_180001371
0x18000136a  xor     eax, eax
0x18000136c  jmp     loc_18000145F
0x180001371  lea     eax, [rdx-1]
0x180001374  cmp     eax, 1
0x180001377  ja      short loc_1800013BE
0x180001379  mov     rax, cs:_pRawDllMain
0x180001380  test    rax, rax
0x180001383  jnz     short loc_18000138F
0x180001385  mov     [rsp+58h+var_28], 1
0x18000138d  jmp     short loc_1800013A3
0x18000138f  call    cs:__guard_dispatch_icall_fptr
0x180001395  mov     ebx, eax
0x180001397  mov     [rsp+58h+var_28], eax
0x18000139b  test    eax, eax
0x18000139d  jz      loc_180001455
0x1800013a3  mov     r8, rsi
0x1800013a6  mov     edx, edi
0x1800013a8  mov     rcx, r14
0x1800013ab  call    dllmain_crt_dispatch
0x1800013b0  mov     ebx, eax
0x1800013b2  mov     [rsp+58h+var_28], eax
0x1800013b6  test    eax, eax
0x1800013b8  jz      loc_180001455
0x1800013be  mov     r8, rsi; lpvReserved
0x1800013c1  mov     edx, edi; fdwReason
0x1800013c3  mov     rcx, r14; hinstDLL
0x1800013c6  call    DllMain
0x1800013cb  mov     ebx, eax
0x1800013cd  mov     [rsp+58h+var_28], eax
0x1800013d1  cmp     edi, 1
0x1800013d4  jnz     short loc_18000140C
0x1800013d6  test    eax, eax
0x1800013d8  jnz     short loc_18000140C
0x1800013da  mov     r8, rsi; lpvReserved
0x1800013dd  xor     edx, edx; fdwReason
0x1800013df  mov     rcx, r14; hinstDLL
0x1800013e2  call    DllMain
0x1800013e7  test    rsi, rsi
0x1800013ea  setnz   cl
0x1800013ed  call    dllmain_crt_process_detach
0x1800013f2  mov     rax, cs:_pRawDllMain
0x1800013f9  test    rax, rax
0x1800013fc  jz      short loc_18000140C
0x1800013fe  mov     r8, rsi
0x180001401  xor     edx, edx
0x180001403  mov     rcx, r14
0x180001406  call    cs:__guard_dispatch_icall_fptr
0x18000140c  test    edi, edi
0x18000140e  jz      short loc_180001415
0x180001410  cmp     edi, 3
0x180001413  jnz     short loc_180001455
0x180001415  mov     r8, rsi
0x180001418  mov     edx, edi
0x18000141a  mov     rcx, r14
0x18000141d  call    dllmain_crt_dispatch
0x180001422  mov     ebx, eax
0x180001424  mov     [rsp+58h+var_28], eax
0x180001428  test    eax, eax
0x18000142a  jz      short loc_180001455
0x18000142c  mov     rax, cs:_pRawDllMain
0x180001433  test    rax, rax
0x180001436  jnz     short loc_180001441
0x180001438  lea     ebx, [rax+1]
0x18000143b  mov     [rsp+58h+var_28], ebx
0x18000143f  jmp     short loc_180001455
0x180001441  mov     r8, rsi
0x180001444  mov     edx, edi
0x180001446  mov     rcx, r14
0x180001449  call    cs:__guard_dispatch_icall_fptr
0x18000144f  mov     ebx, eax
0x180001451  mov     [rsp+58h+var_28], eax
0x180001455  jmp     short loc_18000145D
0x180001457  xor     ebx, ebx
0x180001459  mov     [rsp+58h+var_28], ebx
0x18000145d  mov     eax, ebx
0x18000145f  mov     rbx, [rsp+58h+arg_18]
0x180001464  add     rsp, 40h
0x180001468  pop     r14
0x18000146a  pop     rdi
0x18000146b  pop     rsi
0x18000146c  retn
0x180001f6a  push    rbp
0x180001f6c  sub     rsp, 30h
0x180001f70  mov     rbp, rdx
0x180001f73  mov     rax, [rcx]
0x180001f76  mov     edx, [rax]
0x180001f78  mov     [rsp+38h+ExceptionPtr], rcx; ExceptionPtr
0x180001f7d  mov     [rsp+38h+ExceptionNum], edx; ExceptionNum
0x180001f81  lea     r9, dllmain_crt_dispatch; int
0x180001f88  mov     r8, [rbp+70h]; int
0x180001f8c  mov     edx, [rbp+68h]; int
0x180001f8f  mov     rcx, [rbp+60h]; int
0x180001f93  call    __scrt_dllmain_exception_filter
0x180001f98  nop
0x180001f99  add     rsp, 30h
0x180001f9d  pop     rbp
0x180001f9e  retn
```
