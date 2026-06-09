# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x18000155a`
- `0x180001738`
- `0x180006640`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_18000C0E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000C0E4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18000C0E4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180001324  mov     [rsp+lpvReserved], r8
0x180001329  mov     [rsp+arg_8], edx
0x18000132d  mov     [rsp+arg_0], rcx
0x180001332  push    rbx
0x180001333  push    rsi
0x180001334  push    rdi
0x180001335  sub     rsp, 0F0h
0x18000133c  mov     edi, edx
0x18000133e  mov     rsi, rcx
0x180001341  mov     ebx, 1
0x180001346  cmp     edx, ebx
0x180001348  ja      short loc_180001350
0x18000134a  mov     cs:__native_dllmain_reason, edx
0x180001350  test    edx, edx
0x180001352  jnz     short loc_180001367
0x180001354  cmp     cs:dword_18000C0E0, edx
0x18000135a  jnz     short loc_180001367
0x18000135c  xor     ebx, ebx
0x18000135e  mov     [rsp+108h+var_E8], ebx
0x180001362  jmp     loc_180001514
0x180001367  lea     eax, [rdx-1]
0x18000136a  cmp     eax, 1
0x18000136d  ja      loc_1800013F4
0x180001373  mov     rax, cs:_pRawDllMain
0x18000137a  test    rax, rax
0x18000137d  jz      short loc_1800013B5
0x18000137f  cmp     edx, 1
0x180001382  jnz     short loc_18000138A
0x180001384  mov     cs:dword_18000C0E4, edx
0x18000138a  mov     r8, [rsp+108h+lpvReserved]
0x180001392  call    cs:__guard_dispatch_icall_fptr
0x180001398  mov     ebx, eax
0x18000139a  mov     [rsp+108h+var_E8], eax
0x18000139e  jmp     short loc_1800013B5
0x1800013a0  xor     ebx, ebx
0x1800013a2  mov     [rsp+108h+var_E8], ebx
0x1800013a6  mov     edi, [rsp+108h+arg_8]
0x1800013ad  mov     rsi, [rsp+108h+arg_0]
0x1800013b5  test    ebx, ebx
0x1800013b7  jz      loc_180001514
0x1800013bd  mov     r8, [rsp+108h+lpvReserved]
0x1800013c5  mov     edx, edi
0x1800013c7  mov     rcx, rsi
0x1800013ca  call    _CRT_INIT
0x1800013cf  mov     ebx, eax
0x1800013d1  mov     [rsp+108h+var_E8], eax
0x1800013d5  jmp     short loc_1800013EC
0x1800013d7  xor     ebx, ebx
0x1800013d9  mov     [rsp+108h+var_E8], ebx
0x1800013dd  mov     edi, [rsp+108h+arg_8]
0x1800013e4  mov     rsi, [rsp+108h+arg_0]
0x1800013ec  test    ebx, ebx
0x1800013ee  jz      loc_180001514
0x1800013f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800013fc  mov     edx, edi; fdwReason
0x1800013fe  mov     rcx, rsi; hinstDLL
0x180001401  call    DllMain
0x180001406  mov     ebx, eax
0x180001408  mov     [rsp+108h+var_E8], eax
0x18000140c  jmp     short loc_180001423
0x18000140e  xor     ebx, ebx
0x180001410  mov     [rsp+108h+var_E8], ebx
0x180001414  mov     edi, [rsp+108h+arg_8]
0x18000141b  mov     rsi, [rsp+108h+arg_0]
0x180001423  cmp     edi, 1
0x180001426  jnz     short loc_18000149F
0x180001428  test    ebx, ebx
0x18000142a  jnz     short loc_18000149F
0x18000142c  xor     r8d, r8d; lpvReserved
0x18000142f  xor     edx, edx; fdwReason
0x180001431  mov     rcx, rsi; hinstDLL
0x180001434  call    DllMain
0x180001439  jmp     short loc_18000144E
0x18000143b  mov     edi, [rsp+108h+arg_8]
0x180001442  mov     rsi, [rsp+108h+arg_0]
0x18000144a  mov     ebx, [rsp+108h+var_E8]
0x18000144e  xor     r8d, r8d
0x180001451  xor     edx, edx
0x180001453  mov     rcx, rsi
0x180001456  call    _CRT_INIT
0x18000145b  jmp     short loc_180001470
0x18000145d  mov     edi, [rsp+108h+arg_8]
0x180001464  mov     rsi, [rsp+108h+arg_0]
0x18000146c  mov     ebx, [rsp+108h+var_E8]
0x180001470  mov     rax, cs:_pRawDllMain
0x180001477  test    rax, rax
0x18000147a  jz      short loc_18000149F
0x18000147c  xor     r8d, r8d
0x18000147f  xor     edx, edx
0x180001481  mov     rcx, rsi
0x180001484  call    cs:__guard_dispatch_icall_fptr
0x18000148a  jmp     short loc_18000149F
0x18000148c  mov     edi, [rsp+108h+arg_8]
0x180001493  mov     rsi, [rsp+108h+arg_0]
0x18000149b  mov     ebx, [rsp+108h+var_E8]
0x18000149f  test    edi, edi
0x1800014a1  jz      short loc_1800014A8
0x1800014a3  cmp     edi, 3
0x1800014a6  jnz     short loc_180001514
0x1800014a8  mov     r8, [rsp+108h+lpvReserved]
0x1800014b0  mov     edx, edi
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    _CRT_INIT
0x1800014ba  mov     ebx, eax
0x1800014bc  mov     [rsp+108h+var_E8], eax
0x1800014c0  jmp     short loc_1800014D7
0x1800014c2  xor     ebx, ebx
0x1800014c4  mov     [rsp+108h+var_E8], ebx
0x1800014c8  mov     edi, [rsp+108h+arg_8]
0x1800014cf  mov     rsi, [rsp+108h+arg_0]
0x1800014d7  mov     rax, cs:_pRawDllMain
0x1800014de  test    rax, rax
0x1800014e1  jz      short loc_180001514
0x1800014e3  cmp     cs:dword_18000C0E4, 0
0x1800014ea  jz      short loc_180001514
0x1800014ec  mov     r8, [rsp+108h+lpvReserved]
0x1800014f4  mov     edx, edi
0x1800014f6  mov     rcx, rsi
0x1800014f9  call    cs:__guard_dispatch_icall_fptr
0x1800014ff  mov     ebx, eax
0x180001501  mov     [rsp+108h+var_E8], eax
0x180001505  jmp     short loc_180001514
0x180001507  xor     ebx, ebx
0x180001509  mov     [rsp+108h+var_E8], ebx
0x18000150d  mov     edi, [rsp+108h+arg_8]
0x180001514  cmp     edi, 1
0x180001517  ja      short loc_180001523
0x180001519  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001523  mov     eax, ebx
0x180001525  add     rsp, 0F0h
0x18000152c  pop     rdi
0x18000152d  pop     rsi
0x18000152e  pop     rbx
0x18000152f  retn
0x1800066b0  push    rbp
0x1800066b2  sub     rsp, 20h
0x1800066b6  mov     rbp, rdx
0x1800066b9  mov     rax, [rcx]
0x1800066bc  mov     edx, [rax]
0x1800066be  mov     [rbp+0A8h], rcx
0x1800066c5  mov     [rbp+28h], edx
0x1800066c8  mov     eax, [rbp+28h]
0x1800066cb  cmp     eax, 0E06D7363h
0x1800066d0  jnz     short loc_1800066E6
0x1800066d2  mov     rdx, [rbp+0A8h]
0x1800066d9  mov     ecx, [rbp+28h]
0x1800066dc  call    _XcptFilter_0
0x1800066e1  mov     [rbp+30h], eax
0x1800066e4  jmp     short loc_1800066ED
0x1800066e6  mov     dword ptr [rbp+30h], 0
0x1800066ed  mov     eax, [rbp+30h]
0x1800066f0  add     rsp, 20h
0x1800066f4  pop     rbp
0x1800066f5  retn
0x1800066f7  push    rbp
0x1800066f9  sub     rsp, 20h
0x1800066fd  mov     rbp, rdx
0x180006700  mov     rax, [rcx]
0x180006703  mov     edx, [rax]
0x180006705  mov     [rbp+0B0h], rcx
0x18000670c  mov     [rbp+38h], edx
0x18000670f  mov     eax, [rbp+38h]
0x180006712  cmp     eax, 0E06D7363h
0x180006717  jnz     short loc_18000672D
0x180006719  mov     rdx, [rbp+0B0h]
0x180006720  mov     ecx, [rbp+38h]
0x180006723  call    _XcptFilter_0
0x180006728  mov     [rbp+40h], eax
0x18000672b  jmp     short loc_180006734
0x18000672d  mov     dword ptr [rbp+40h], 0
0x180006734  mov     eax, [rbp+40h]
0x180006737  add     rsp, 20h
0x18000673b  pop     rbp
0x18000673c  retn
0x18000673e  push    rbp
0x180006740  sub     rsp, 20h
0x180006744  mov     rbp, rdx
0x180006747  mov     rax, [rcx]
0x18000674a  mov     edx, [rax]
0x18000674c  mov     [rbp+0B8h], rcx
0x180006753  mov     [rbp+48h], edx
0x180006756  mov     eax, [rbp+48h]
0x180006759  cmp     eax, 0E06D7363h
0x18000675e  jnz     short loc_180006774
0x180006760  mov     rdx, [rbp+0B8h]
0x180006767  mov     ecx, [rbp+48h]
0x18000676a  call    _XcptFilter_0
0x18000676f  mov     [rbp+50h], eax
0x180006772  jmp     short loc_18000677B
0x180006774  mov     dword ptr [rbp+50h], 0
0x18000677b  mov     eax, [rbp+50h]
0x18000677e  add     rsp, 20h
0x180006782  pop     rbp
0x180006783  retn
0x180006785  push    rbp
0x180006787  sub     rsp, 20h
0x18000678b  mov     rbp, rdx
0x18000678e  mov     rax, [rcx]
0x180006791  mov     edx, [rax]
0x180006793  mov     [rbp+0C0h], rcx
0x18000679a  mov     [rbp+58h], edx
0x18000679d  mov     eax, [rbp+58h]
0x1800067a0  cmp     eax, 0E06D7363h
0x1800067a5  jnz     short loc_1800067BB
0x1800067a7  mov     rdx, [rbp+0C0h]
0x1800067ae  mov     ecx, [rbp+58h]
0x1800067b1  call    _XcptFilter_0
0x1800067b6  mov     [rbp+60h], eax
0x1800067b9  jmp     short loc_1800067C2
0x1800067bb  mov     dword ptr [rbp+60h], 0
0x1800067c2  mov     eax, [rbp+60h]
0x1800067c5  add     rsp, 20h
0x1800067c9  pop     rbp
0x1800067ca  retn
0x1800067cc  push    rbp
0x1800067ce  sub     rsp, 20h
0x1800067d2  mov     rbp, rdx
0x1800067d5  mov     rax, [rcx]
0x1800067d8  mov     edx, [rax]
0x1800067da  mov     [rbp+0C8h], rcx
0x1800067e1  mov     [rbp+68h], edx
0x1800067e4  mov     eax, [rbp+68h]
0x1800067e7  cmp     eax, 0E06D7363h
0x1800067ec  jnz     short loc_180006802
0x1800067ee  mov     rdx, [rbp+0C8h]
0x1800067f5  mov     ecx, [rbp+68h]
0x1800067f8  call    _XcptFilter_0
0x1800067fd  mov     [rbp+70h], eax
0x180006800  jmp     short loc_180006809
0x180006802  mov     dword ptr [rbp+70h], 0
0x180006809  mov     eax, [rbp+70h]
0x18000680c  add     rsp, 20h
0x180006810  pop     rbp
0x180006811  retn
0x180006813  push    rbp
0x180006815  sub     rsp, 20h
0x180006819  mov     rbp, rdx
0x18000681c  mov     rax, [rcx]
0x18000681f  mov     edx, [rax]
0x180006821  mov     [rbp+0D0h], rcx
0x180006828  mov     [rbp+78h], edx
0x18000682b  mov     eax, [rbp+78h]
0x18000682e  cmp     eax, 0E06D7363h
0x180006833  jnz     short loc_18000684C
0x180006835  mov     rdx, [rbp+0D0h]
0x18000683c  mov     ecx, [rbp+78h]
0x18000683f  call    _XcptFilter_0
0x180006844  mov     [rbp+80h], eax
0x18000684a  jmp     short loc_180006856
0x18000684c  mov     dword ptr [rbp+80h], 0
0x180006856  mov     eax, [rbp+80h]
0x18000685c  add     rsp, 20h
0x180006860  pop     rbp
0x180006861  retn
0x180006863  push    rbp
0x180006865  sub     rsp, 20h
0x180006869  mov     rbp, rdx
0x18000686c  mov     rax, [rcx]
0x18000686f  mov     edx, [rax]
0x180006871  mov     [rbp+0D8h], rcx
0x180006878  mov     [rbp+88h], edx
0x18000687e  mov     eax, [rbp+88h]
0x180006884  cmp     eax, 0E06D7363h
0x180006889  jnz     short loc_1800068A5
0x18000688b  mov     rdx, [rbp+0D8h]
0x180006892  mov     ecx, [rbp+88h]
0x180006898  call    _XcptFilter_0
0x18000689d  mov     [rbp+90h], eax
0x1800068a3  jmp     short loc_1800068AF
0x1800068a5  mov     dword ptr [rbp+90h], 0
0x1800068af  mov     eax, [rbp+90h]
0x1800068b5  add     rsp, 20h
0x1800068b9  pop     rbp
0x1800068ba  retn
0x1800068bc  push    rbp
0x1800068be  sub     rsp, 20h
0x1800068c2  mov     rbp, rdx
0x1800068c5  mov     rax, [rcx]
0x1800068c8  mov     edx, [rax]
0x1800068ca  mov     [rbp+0E0h], rcx
0x1800068d1  mov     [rbp+98h], edx
0x1800068d7  mov     eax, [rbp+98h]
0x1800068dd  cmp     eax, 0E06D7363h
0x1800068e2  jnz     short loc_1800068FE
0x1800068e4  mov     rdx, [rbp+0E0h]
0x1800068eb  mov     ecx, [rbp+98h]
0x1800068f1  call    _XcptFilter_0
0x1800068f6  mov     [rbp+0A0h], eax
0x1800068fc  jmp     short loc_180006908
0x1800068fe  mov     dword ptr [rbp+0A0h], 0
0x180006908  mov     eax, [rbp+0A0h]
0x18000690e  add     rsp, 20h
0x180006912  pop     rbp
0x180006913  retn
0x180006915  push    rbp
0x180006917  sub     rsp, 20h
0x18000691b  mov     rbp, rdx
0x18000691e  cmp     dword ptr [rbp+118h], 1
0x180006925  ja      short loc_180006931
0x180006927  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
