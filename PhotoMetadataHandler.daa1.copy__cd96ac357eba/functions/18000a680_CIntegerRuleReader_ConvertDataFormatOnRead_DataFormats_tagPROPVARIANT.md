# CIntegerRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x18000a680`
- end: `0x18000ab1e`
- name: `?ConvertDataFormatOnRead@CIntegerRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `1182`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a680`
- `0x18000ab24`
- `0x18000ac88`
- `0x1800129d8`
- `0x18001e434`
- `0x18001e644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000aa8a`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000aaa6`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000aa8a`
- `api-ms-win-crt-private-l1-1-0!_o_strtol` at `0x18000aaa6`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000aa52`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000aa71`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000aa52`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x18000aa71`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000a775`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18000a775`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a756`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a93e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aa11`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a756`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a93e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000aa11`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a769`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a7db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a803`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a853`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a8c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a8e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a931`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a9a0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aa24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aabd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aae5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a769`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a7db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a803`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a853`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a8c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a8e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a931`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a9a0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aa24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aabd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000aae5`
- `PROPSYS!PropVariantChangeType` at `0x18000a7b7`
- `PROPSYS!PropVariantChangeType` at `0x18000a7b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIntegerRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, PROPVARIANT *a3)
{
  HRESULT v5; // ebx
  VARTYPE v6; // r9
  int vt; // eax
  __int64 v8; // rdx
  int v10; // r8d
  int v11; // r14d
  double v12; // xmm0_8
  double v13; // xmm1_8
  HRESULT v14; // eax
  double v15; // xmm1_8
  int v16; // eax
  HRESULT v17; // eax
  SHORT v18; // ax
  PROPVARIANT pvarDest; // [rsp+30h] [rbp-20h] BYREF

  if ( a2 == 13 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v14 = ConstructIntegerPropvarFromXMPSeq(a3, *(_WORD *)(*(_QWORD *)(a1 + 32) + 52LL), &pvarDest);
    v5 = v14;
    if ( v14 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_47;
      goto LABEL_46;
    }
    PropVariantClear(a3);
    *a3 = pvarDest;
    memset(&pvarDest, 0, sizeof(pvarDest));
    goto LABEL_64;
  }
  if ( a2 == 16 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v17 = ConstructExifFlashValueFromXMPFlash(a3, &pvarDest.bVal);
    v5 = v17;
    if ( v17 >= 0 )
    {
      pvarDest.vt = 17;
      PropVariantClear(a3);
      v17 = PropVariantCopy(a3, &pvarDest);
      v5 = v17;
      if ( v17 >= 0 )
        goto LABEL_64;
      if ( !g_doStackCaptures )
        goto LABEL_47;
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_47;
    }
    DoStackCapture(v17);
    goto LABEL_47;
  }
  if ( a3->vt == 19 )
  {
LABEL_4:
    v5 = 0;
    goto LABEL_9;
  }
  v5 = -2147418113;
  v11 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 52LL);
  switch ( a3->vt )
  {
    case 2u:
    case 3u:
    case 0x10u:
    case 0x11u:
    case 0x12u:
      goto LABEL_4;
    case 0x1Eu:
      memset(&pvarDest, 0, sizeof(pvarDest));
      v5 = PropVariantCopy(&pvarDest, a3);
      if ( v5 < 0 )
        goto LABEL_6;
      PropVariantClear(a3);
      switch ( v11 )
      {
        case 2:
          a3->vt = 2;
          v18 = strtol(pvarDest.pszVal, 0, 10);
          break;
        case 3:
          a3->vt = 3;
          a3->lVal = strtol(pvarDest.pszVal, 0, 10);
          goto LABEL_64;
        case 19:
          a3->vt = 19;
          a3->lVal = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)(
                       (LARGE_INTEGER)pvarDest.hVal.QuadPart,
                       0,
                       10);
          goto LABEL_64;
        default:
          a3->vt = 18;
          v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))_o_strtoul)(
                  (LARGE_INTEGER)pvarDest.hVal.QuadPart,
                  0,
                  10);
          break;
      }
      a3->iVal = v18;
      break;
    case 0x1Fu:
      memset(&pvarDest, 0, sizeof(pvarDest));
      v5 = PropVariantCopy(&pvarDest, a3);
      if ( v5 < 0 )
        goto LABEL_6;
      PropVariantClear(a3);
      v12 = ((double (__fastcall *)(_QWORD, _QWORD))_o_wcstod)((LARGE_INTEGER)pvarDest.hVal.QuadPart, 0);
      if ( v12 > 0.0 )
        v13 = DOUBLE_0_5;
      else
        v13 = DOUBLE_N0_5;
      v15 = v13 + v12;
      switch ( v11 )
      {
        case 3:
          a3->vt = 3;
          v16 = (int)v15;
LABEL_27:
          a3->lVal = v16;
          PropVariantClear(&pvarDest);
          goto LABEL_9;
        case 2:
          a3->vt = 2;
          a3->iVal = (int)v15;
          break;
        case 19:
          a3->vt = 19;
          v16 = (int)fmax(0.0, v15);
          goto LABEL_27;
        default:
          a3->vt = 18;
          a3->iVal = (int)fmax(0.0, v15);
          break;
      }
      break;
    default:
LABEL_6:
      if ( g_doStackCaptures )
        DoStackCapture(v5);
      return (unsigned int)v5;
  }
LABEL_64:
  PropVariantClear(&pvarDest);
LABEL_9:
  v6 = *(_WORD *)(*(_QWORD *)(a1 + 32) + 52LL);
  vt = a3->vt;
  if ( (_WORD)vt == v6 )
    goto LABEL_10;
  if ( vt == 3 || vt == 2 || vt == 16 || vt == 17 || (unsigned int)(vt - 18) < 2 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v14 = PropVariantChangeType(&pvarDest, a3, 0, v6);
    v5 = v14;
    if ( v14 >= 0 )
    {
      PropVariantClear(a3);
      *a3 = pvarDest;
      memset(&pvarDest, 0, sizeof(pvarDest));
      PropVariantClear(&pvarDest);
LABEL_10:
      v8 = *(_QWORD *)(a1 + 32);
      if ( *(_DWORD *)(v8 + 12) )
      {
        v10 = *(_DWORD *)(v8 + 48);
        if ( *(_DWORD *)(v8 + 16) )
          return (unsigned int)ClipToRange(a3, *(_DWORD *)(v8 + 44), v10, *(_WORD *)(v8 + 52), 0);
        else
          return (unsigned int)CheckRange(a3, *(_DWORD *)(v8 + 44), v10);
      }
      return (unsigned int)v5;
    }
    if ( !g_doStackCaptures )
      goto LABEL_47;
LABEL_46:
    DoStackCapture(v14);
LABEL_47:
    PropVariantClear(&pvarDest);
    return (unsigned int)v5;
  }
  v5 = -2003292274;
  if ( !g_doStackCaptures )
    return (unsigned int)v5;
  DoStackCapture(-2003292274);
  return 2291675022LL;
}

```

## disassembly

```asm
0x18000a680  push    rbp
0x18000a682  push    rbx
0x18000a683  push    rsi
0x18000a684  push    rdi
0x18000a685  push    r14
0x18000a687  mov     rbp, rsp
0x18000a68a  sub     rsp, 50h
0x18000a68e  mov     rdi, r8
0x18000a691  mov     rsi, rcx
0x18000a694  cmp     edx, 0Dh
0x18000a697  jz      loc_18000A95C
0x18000a69d  cmp     edx, 10h
0x18000a6a0  jz      loc_18000A8FB
0x18000a6a6  movzx   eax, word ptr [r8]
0x18000a6aa  cmp     eax, 13h
0x18000a6ad  jnz     short loc_18000A6B3
0x18000a6af  xor     ebx, ebx; jumptable 000000018000A740 cases 2,3,16-18
0x18000a6b1  jmp     short loc_18000A6D1
0x18000a6b3  mov     ebx, 8000FFFFh
0x18000a6b8  lea     ecx, [rax-2]; switch 30 cases
0x18000a6bb  cmp     ecx, 1Dh
0x18000a6be  jbe     short loc_18000A71B
0x18000a6c0  cmp     cs:?g_doStackCaptures@@3HA, 0; jumptable 000000018000A740 default case, cases 4-15,19-29
0x18000a6c7  jnz     loc_18000A85E
0x18000a6cd  test    ebx, ebx
0x18000a6cf  js      short loc_18000A6F1
0x18000a6d1  mov     rax, [rsi+20h]
0x18000a6d5  movzx   r9d, word ptr [rax+34h]; vt
0x18000a6da  movzx   eax, word ptr [rdi]
0x18000a6dd  cmp     ax, r9w
0x18000a6e1  jnz     loc_18000A795
0x18000a6e7  mov     rdx, [rsi+20h]
0x18000a6eb  cmp     dword ptr [rdx+0Ch], 0
0x18000a6ef  jnz     short loc_18000A6FE
0x18000a6f1  mov     eax, ebx
0x18000a6f3  add     rsp, 50h
0x18000a6f7  pop     r14
0x18000a6f9  pop     rdi
0x18000a6fa  pop     rsi
0x18000a6fb  pop     rbx
0x18000a6fc  pop     rbp
0x18000a6fd  retn
0x18000a6fe  mov     r8d, [rdx+30h]; int
0x18000a702  mov     rcx, rdi; pvarDest
0x18000a705  cmp     dword ptr [rdx+10h], 0
0x18000a709  jnz     loc_18000A80E
0x18000a70f  mov     edx, [rdx+2Ch]; int
0x18000a712  call    ?CheckRange@@YAJPEBUtagPROPVARIANT@@HH@Z; CheckRange(tagPROPVARIANT const *,int,int)
0x18000a717  mov     ebx, eax
0x18000a719  jmp     short loc_18000A6F1
0x18000a71b  mov     rax, [rsi+20h]
0x18000a71f  movzx   r14d, word ptr [rax+34h]
0x18000a724  movsxd  rax, ecx
0x18000a727  lea     rdx, __ImageBase
0x18000a72e  movzx   eax, ds:(byte_18000AB00 - 180000000h)[rdx+rax]
0x18000a736  mov     ecx, ds:(jpt_18000A740 - 180000000h)[rdx+rax*4]
0x18000a73d  add     rcx, rdx
0x18000a740  jmp     rcx; switch jump
0x18000a742  xorps   xmm0, xmm0; jumptable 000000018000A740 case 31
0x18000a745  xor     eax, eax
0x18000a747  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000a74b  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000a74f  mov     rdx, rdi; pvarSrc
0x18000a752  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000a756  call    cs:__imp_PropVariantCopy
0x18000a75c  mov     ebx, eax
0x18000a75e  test    eax, eax
0x18000a760  js      def_18000A740; jumptable 000000018000A740 default case, cases 4-15,19-29
0x18000a766  mov     rcx, rdi; pvar
0x18000a769  call    cs:__imp_PropVariantClear
0x18000a76f  xor     edx, edx
0x18000a771  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000a775  call    cs:__imp__o_wcstod
0x18000a77b  xorps   xmm2, xmm2
0x18000a77e  comisd  xmm0, xmm2
0x18000a782  ja      loc_18000A82B
0x18000a788  movsd   xmm1, cs:__real@bfe0000000000000
0x18000a790  jmp     loc_18000A833
0x18000a795  mov     ecx, eax
0x18000a797  cmp     eax, 3
0x18000a79a  jnz     loc_18000A86A
0x18000a7a0  xorps   xmm0, xmm0
0x18000a7a3  xor     eax, eax
0x18000a7a5  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000a7a9  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000a7ad  xor     r8d, r8d; flags
0x18000a7b0  mov     rdx, rdi; propvarSrc
0x18000a7b3  lea     rcx, [rbp+pvarDest]; ppropvarDest
0x18000a7b7  call    cs:__imp_PropVariantChangeType
0x18000a7bd  mov     ebx, eax
0x18000a7bf  test    eax, eax
0x18000a7c1  jns     short loc_18000A7D8
0x18000a7c3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a7ca  jnz     loc_18000A8BD
0x18000a7d0  test    eax, eax
0x18000a7d2  js      loc_18000A8C5
0x18000a7d8  mov     rcx, rdi; pvar
0x18000a7db  call    cs:__imp_PropVariantClear
0x18000a7e1  movups  xmm0, xmmword ptr [rbp+pvarDest]
0x18000a7e5  movups  xmmword ptr [rdi], xmm0
0x18000a7e8  movsd   xmm1, qword ptr [rbp+pvarDest+10h]
0x18000a7ed  movsd   qword ptr [rdi+10h], xmm1
0x18000a7f2  xorps   xmm0, xmm0
0x18000a7f5  xor     eax, eax
0x18000a7f7  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000a7fb  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000a7ff  lea     rcx, [rbp+pvarDest]; pvar
0x18000a803  call    cs:__imp_PropVariantClear
0x18000a809  jmp     loc_18000A6E7
0x18000a80e  mov     [rsp+50h+var_30], 0; bool *
0x18000a817  movzx   r9d, word ptr [rdx+34h]; unsigned __int16
0x18000a81c  mov     edx, [rdx+2Ch]; int
0x18000a81f  call    ?ClipToRange@@YAJPEAUtagPROPVARIANT@@HHGPEA_N@Z; ClipToRange(tagPROPVARIANT *,int,int,ushort,bool *)
0x18000a824  mov     ebx, eax
0x18000a826  jmp     loc_18000A6F1
0x18000a82b  movsd   xmm1, cs:__real@3fe0000000000000
0x18000a833  addsd   xmm1, xmm0
0x18000a837  mov     ecx, r14d
0x18000a83a  cmp     r14d, 3
0x18000a83e  jnz     loc_18000A9B3
0x18000a844  mov     [rdi], r14w
0x18000a848  cvttsd2si eax, xmm1
0x18000a84c  mov     [rdi+8], eax
0x18000a84f  lea     rcx, [rbp+pvarDest]; pvar
0x18000a853  call    cs:__imp_PropVariantClear
0x18000a859  jmp     loc_18000A6D1
0x18000a85e  mov     ecx, ebx; int
0x18000a860  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a865  jmp     loc_18000A6CD
0x18000a86a  sub     ecx, 2
0x18000a86d  jz      loc_18000A7A0
0x18000a873  sub     ecx, 0Eh
0x18000a876  jz      loc_18000A7A0
0x18000a87c  sub     ecx, 1
0x18000a87f  jz      loc_18000A7A0
0x18000a885  sub     ecx, 1
0x18000a888  jz      loc_18000A7A0
0x18000a88e  cmp     ecx, 1
0x18000a891  jz      loc_18000A7A0
0x18000a897  mov     ebx, 88982F8Eh
0x18000a89c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a8a3  jz      loc_18000A6F1
0x18000a8a9  mov     ecx, ebx; int
0x18000a8ab  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a8b0  mov     eax, ebx
0x18000a8b2  add     rsp, 50h
0x18000a8b6  pop     r14
0x18000a8b8  pop     rdi
0x18000a8b9  pop     rsi
0x18000a8ba  pop     rbx
0x18000a8bb  pop     rbp
0x18000a8bc  retn
0x18000a8bd  mov     ecx, eax; int
0x18000a8bf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a8c4  nop
0x18000a8c5  lea     rcx, [rbp+pvarDest]; pvar
0x18000a8c9  call    cs:__imp_PropVariantClear
0x18000a8cf  mov     eax, ebx
0x18000a8d1  add     rsp, 50h
0x18000a8d5  pop     r14
0x18000a8d7  pop     rdi
0x18000a8d8  pop     rsi
0x18000a8d9  pop     rbx
0x18000a8da  pop     rbp
0x18000a8db  retn
0x18000a8dc  mov     ecx, eax; int
0x18000a8de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a8e3  nop
0x18000a8e4  lea     rcx, [rbp+pvarDest]; pvar
0x18000a8e8  call    cs:__imp_PropVariantClear
0x18000a8ee  mov     eax, ebx
0x18000a8f0  add     rsp, 50h
0x18000a8f4  pop     r14
0x18000a8f6  pop     rdi
0x18000a8f7  pop     rsi
0x18000a8f8  pop     rbx
0x18000a8f9  pop     rbp
0x18000a8fa  retn
0x18000a8fb  xorps   xmm0, xmm0
0x18000a8fe  xor     eax, eax
0x18000a900  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000a904  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000a908  lea     rdx, [rbp+pvarDest+8]; unsigned __int8 *
0x18000a90c  mov     rcx, rdi; struct tagPROPVARIANT *
0x18000a90f  call    ?ConstructExifFlashValueFromXMPFlash@@YAJPEBUtagPROPVARIANT@@PEAE@Z; ConstructExifFlashValueFromXMPFlash(tagPROPVARIANT const *,uchar *)
0x18000a914  mov     ebx, eax
0x18000a916  test    eax, eax
0x18000a918  jns     short loc_18000A925
0x18000a91a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a921  jz      short loc_18000A8E4
0x18000a923  jmp     short loc_18000A8DC
0x18000a925  mov     eax, 11h
0x18000a92a  mov     word ptr [rbp+pvarDest], ax
0x18000a92e  mov     rcx, rdi; pvar
0x18000a931  call    cs:__imp_PropVariantClear
0x18000a937  lea     rdx, [rbp+pvarDest]; pvarSrc
0x18000a93b  mov     rcx, rdi; pvarDest
0x18000a93e  call    cs:__imp_PropVariantCopy
0x18000a944  mov     ebx, eax
0x18000a946  test    eax, eax
0x18000a948  jns     short loc_18000A957
0x18000a94a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a951  jnz     short loc_18000A8DC
0x18000a953  test    eax, eax
0x18000a955  js      short loc_18000A8E4
0x18000a957  jmp     loc_18000AAE1
0x18000a95c  xorps   xmm0, xmm0
0x18000a95f  xor     eax, eax
0x18000a961  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000a965  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000a969  mov     rdx, [rcx+20h]
0x18000a96d  lea     r8, [rbp+pvarDest]; struct tagPROPVARIANT *
0x18000a971  movzx   edx, word ptr [rdx+34h]; unsigned __int16
0x18000a975  mov     rcx, rdi; struct tagPROPVARIANT *
0x18000a978  call    ?ConstructIntegerPropvarFromXMPSeq@@YAJPEBUtagPROPVARIANT@@GPEAU1@@Z; ConstructIntegerPropvarFromXMPSeq(tagPROPVARIANT const *,ushort,tagPROPVARIANT *)
0x18000a97d  mov     ebx, eax
0x18000a97f  test    eax, eax
0x18000a981  jns     loc_18000AABA
0x18000a987  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a98e  jz      loc_18000AAB2
0x18000a994  mov     ecx, eax; int
0x18000a996  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a99b  nop
0x18000a99c  lea     rcx, [rbp+pvarDest]; pvar
0x18000a9a0  call    cs:__imp_PropVariantClear
0x18000a9a6  mov     eax, ebx
0x18000a9a8  add     rsp, 50h
0x18000a9ac  pop     r14
0x18000a9ae  pop     rdi
0x18000a9af  pop     rsi
0x18000a9b0  pop     rbx
0x18000a9b1  pop     rbp
0x18000a9b2  retn
0x18000a9b3  sub     ecx, 2
0x18000a9b6  jz      short loc_18000A9EB
0x18000a9b8  sub     ecx, 10h
0x18000a9bb  jz      short loc_18000A9D5
0x18000a9bd  cmp     ecx, 1
0x18000a9c0  jnz     short loc_18000A9D5
0x18000a9c2  mov     word ptr [rdi], 13h
0x18000a9c7  maxsd   xmm2, xmm1
0x18000a9cb  cvttsd2si rax, xmm2
0x18000a9d0  jmp     loc_18000A84C
0x18000a9d5  mov     word ptr [rdi], 12h
0x18000a9da  maxsd   xmm2, xmm1
0x18000a9de  cvttsd2si eax, xmm2
0x18000a9e2  mov     [rdi+8], ax
0x18000a9e6  jmp     loc_18000AAE1
0x18000a9eb  mov     word ptr [rdi], 2
0x18000a9f0  cvttsd2si eax, xmm1
0x18000a9f4  mov     [rdi+8], ax
0x18000a9f8  jmp     loc_18000AAE1
0x18000a9fd  xorps   xmm0, xmm0; jumptable 000000018000A740 case 30
0x18000aa00  xor     eax, eax
0x18000aa02  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18000aa06  mov     qword ptr [rbp+pvarDest+10h], rax
0x18000aa0a  mov     rdx, rdi; pvarSrc
0x18000aa0d  lea     rcx, [rbp+pvarDest]; pvarDest
0x18000aa11  call    cs:__imp_PropVariantCopy
0x18000aa17  mov     ebx, eax
0x18000aa19  test    eax, eax
0x18000aa1b  js      def_18000A740; jumptable 000000018000A740 default case, cases 4-15,19-29
0x18000aa21  mov     rcx, rdi; pvar
0x18000aa24  call    cs:__imp_PropVariantClear
0x18000aa2a  mov     ecx, r14d
0x18000aa2d  sub     ecx, 2
0x18000aa30  jz      short loc_18000AA95
0x18000aa32  sub     ecx, 1
0x18000aa35  jz      short loc_18000AA79
0x18000aa37  sub     ecx, 0Fh
0x18000aa3a  jz      short loc_18000AA60
0x18000aa3c  cmp     ecx, 1
0x18000aa3f  jnz     short loc_18000AA60
0x18000aa41  mov     word ptr [rdi], 13h
0x18000aa46  xor     edx, edx
0x18000aa48  mov     r8d, 0Ah
0x18000aa4e  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000aa52  call    cs:__imp__o_strtoul
0x18000aa58  mov     [rdi+8], eax
0x18000aa5b  jmp     loc_18000AAE1
0x18000aa60  mov     word ptr [rdi], 12h
0x18000aa65  xor     edx, edx
0x18000aa67  mov     r8d, 0Ah
0x18000aa6d  mov     rcx, qword ptr [rbp+pvarDest+8]
0x18000aa71  call    cs:__imp__o_strtoul
0x18000aa77  jmp     short loc_18000AAAC
0x18000aa79  mov     word ptr [rdi], 3
0x18000aa7e  xor     edx, edx; EndPtr
0x18000aa80  mov     r8d, 0Ah; Radix
0x18000aa86  mov     rcx, qword ptr [rbp+pvarDest+8]; String
0x18000aa8a  call    cs:__imp_strtol
0x18000aa90  mov     [rdi+8], eax
0x18000aa93  jmp     short loc_18000AAE1
0x18000aa95  mov     word ptr [rdi], 2
0x18000aa9a  xor     edx, edx; EndPtr
0x18000aa9c  mov     r8d, 0Ah; Radix
0x18000aaa2  mov     rcx, qword ptr [rbp+pvarDest+8]; String
0x18000aaa6  call    cs:__imp_strtol
0x18000aaac  mov     [rdi+8], ax
0x18000aab0  jmp     short loc_18000AAE1
  ... truncated ...
```
