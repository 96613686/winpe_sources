# __DllMainCRTStartup

- ea: `0x180001324`
- end: `0x180001530`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, __int64 fdwReason, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x1800010b0`
- `0x180001324`
- `0x180001542`
- `0x180001ab0`
- `0x180004170`

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
  if ( (_DWORD)fdwReason || dword_1800090E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800090E4 = 1;
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
            if ( dword_1800090E4 )
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
0x180001354  cmp     cs:dword_1800090E0, edx
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
0x180001384  mov     cs:dword_1800090E4, edx
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
0x1800014e3  cmp     cs:dword_1800090E4, 0
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
0x180004240  push    rbp
0x180004242  sub     rsp, 20h
0x180004246  mov     rbp, rdx
0x180004249  mov     rax, [rcx]
0x18000424c  mov     edx, [rax]
0x18000424e  mov     [rbp+0A8h], rcx
0x180004255  mov     [rbp+28h], edx
0x180004258  mov     eax, [rbp+28h]
0x18000425b  cmp     eax, 0E06D7363h
0x180004260  jnz     short loc_180004276
0x180004262  mov     rdx, [rbp+0A8h]
0x180004269  mov     ecx, [rbp+28h]
0x18000426c  call    _XcptFilter_0
0x180004271  mov     [rbp+30h], eax
0x180004274  jmp     short loc_18000427D
0x180004276  mov     dword ptr [rbp+30h], 0
0x18000427d  mov     eax, [rbp+30h]
0x180004280  add     rsp, 20h
0x180004284  pop     rbp
0x180004285  retn
0x180004287  push    rbp
0x180004289  sub     rsp, 20h
0x18000428d  mov     rbp, rdx
0x180004290  mov     rax, [rcx]
0x180004293  mov     edx, [rax]
0x180004295  mov     [rbp+0B0h], rcx
0x18000429c  mov     [rbp+38h], edx
0x18000429f  mov     eax, [rbp+38h]
0x1800042a2  cmp     eax, 0E06D7363h
0x1800042a7  jnz     short loc_1800042BD
0x1800042a9  mov     rdx, [rbp+0B0h]
0x1800042b0  mov     ecx, [rbp+38h]
0x1800042b3  call    _XcptFilter_0
0x1800042b8  mov     [rbp+40h], eax
0x1800042bb  jmp     short loc_1800042C4
0x1800042bd  mov     dword ptr [rbp+40h], 0
0x1800042c4  mov     eax, [rbp+40h]
0x1800042c7  add     rsp, 20h
0x1800042cb  pop     rbp
0x1800042cc  retn
0x1800042ce  push    rbp
0x1800042d0  sub     rsp, 20h
0x1800042d4  mov     rbp, rdx
0x1800042d7  mov     rax, [rcx]
0x1800042da  mov     edx, [rax]
0x1800042dc  mov     [rbp+0B8h], rcx
0x1800042e3  mov     [rbp+48h], edx
0x1800042e6  mov     eax, [rbp+48h]
0x1800042e9  cmp     eax, 0E06D7363h
0x1800042ee  jnz     short loc_180004304
0x1800042f0  mov     rdx, [rbp+0B8h]
0x1800042f7  mov     ecx, [rbp+48h]
0x1800042fa  call    _XcptFilter_0
0x1800042ff  mov     [rbp+50h], eax
0x180004302  jmp     short loc_18000430B
0x180004304  mov     dword ptr [rbp+50h], 0
0x18000430b  mov     eax, [rbp+50h]
0x18000430e  add     rsp, 20h
0x180004312  pop     rbp
0x180004313  retn
0x180004315  push    rbp
0x180004317  sub     rsp, 20h
0x18000431b  mov     rbp, rdx
0x18000431e  mov     rax, [rcx]
0x180004321  mov     edx, [rax]
0x180004323  mov     [rbp+0C0h], rcx
0x18000432a  mov     [rbp+58h], edx
0x18000432d  mov     eax, [rbp+58h]
0x180004330  cmp     eax, 0E06D7363h
0x180004335  jnz     short loc_18000434B
0x180004337  mov     rdx, [rbp+0C0h]
0x18000433e  mov     ecx, [rbp+58h]
0x180004341  call    _XcptFilter_0
0x180004346  mov     [rbp+60h], eax
0x180004349  jmp     short loc_180004352
0x18000434b  mov     dword ptr [rbp+60h], 0
0x180004352  mov     eax, [rbp+60h]
0x180004355  add     rsp, 20h
0x180004359  pop     rbp
0x18000435a  retn
0x18000435c  push    rbp
0x18000435e  sub     rsp, 20h
0x180004362  mov     rbp, rdx
0x180004365  mov     rax, [rcx]
0x180004368  mov     edx, [rax]
0x18000436a  mov     [rbp+0C8h], rcx
0x180004371  mov     [rbp+68h], edx
0x180004374  mov     eax, [rbp+68h]
0x180004377  cmp     eax, 0E06D7363h
0x18000437c  jnz     short loc_180004392
0x18000437e  mov     rdx, [rbp+0C8h]
0x180004385  mov     ecx, [rbp+68h]
0x180004388  call    _XcptFilter_0
0x18000438d  mov     [rbp+70h], eax
0x180004390  jmp     short loc_180004399
0x180004392  mov     dword ptr [rbp+70h], 0
0x180004399  mov     eax, [rbp+70h]
0x18000439c  add     rsp, 20h
0x1800043a0  pop     rbp
0x1800043a1  retn
0x1800043a3  push    rbp
0x1800043a5  sub     rsp, 20h
0x1800043a9  mov     rbp, rdx
0x1800043ac  mov     rax, [rcx]
0x1800043af  mov     edx, [rax]
0x1800043b1  mov     [rbp+0D0h], rcx
0x1800043b8  mov     [rbp+78h], edx
0x1800043bb  mov     eax, [rbp+78h]
0x1800043be  cmp     eax, 0E06D7363h
0x1800043c3  jnz     short loc_1800043DC
0x1800043c5  mov     rdx, [rbp+0D0h]
0x1800043cc  mov     ecx, [rbp+78h]
0x1800043cf  call    _XcptFilter_0
0x1800043d4  mov     [rbp+80h], eax
0x1800043da  jmp     short loc_1800043E6
0x1800043dc  mov     dword ptr [rbp+80h], 0
0x1800043e6  mov     eax, [rbp+80h]
0x1800043ec  add     rsp, 20h
0x1800043f0  pop     rbp
0x1800043f1  retn
0x1800043f3  push    rbp
0x1800043f5  sub     rsp, 20h
0x1800043f9  mov     rbp, rdx
0x1800043fc  mov     rax, [rcx]
0x1800043ff  mov     edx, [rax]
0x180004401  mov     [rbp+0D8h], rcx
0x180004408  mov     [rbp+88h], edx
0x18000440e  mov     eax, [rbp+88h]
0x180004414  cmp     eax, 0E06D7363h
0x180004419  jnz     short loc_180004435
0x18000441b  mov     rdx, [rbp+0D8h]
0x180004422  mov     ecx, [rbp+88h]
0x180004428  call    _XcptFilter_0
0x18000442d  mov     [rbp+90h], eax
0x180004433  jmp     short loc_18000443F
0x180004435  mov     dword ptr [rbp+90h], 0
0x18000443f  mov     eax, [rbp+90h]
0x180004445  add     rsp, 20h
0x180004449  pop     rbp
0x18000444a  retn
0x18000444c  push    rbp
0x18000444e  sub     rsp, 20h
0x180004452  mov     rbp, rdx
0x180004455  mov     rax, [rcx]
0x180004458  mov     edx, [rax]
0x18000445a  mov     [rbp+0E0h], rcx
0x180004461  mov     [rbp+98h], edx
0x180004467  mov     eax, [rbp+98h]
0x18000446d  cmp     eax, 0E06D7363h
0x180004472  jnz     short loc_18000448E
0x180004474  mov     rdx, [rbp+0E0h]
0x18000447b  mov     ecx, [rbp+98h]
0x180004481  call    _XcptFilter_0
0x180004486  mov     [rbp+0A0h], eax
0x18000448c  jmp     short loc_180004498
0x18000448e  mov     dword ptr [rbp+0A0h], 0
0x180004498  mov     eax, [rbp+0A0h]
0x18000449e  add     rsp, 20h
0x1800044a2  pop     rbp
0x1800044a3  retn
0x1800044a5  push    rbp
0x1800044a7  sub     rsp, 20h
0x1800044ab  mov     rbp, rdx
0x1800044ae  cmp     dword ptr [rbp+118h], 1
0x1800044b5  ja      short loc_1800044C1
0x1800044b7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
