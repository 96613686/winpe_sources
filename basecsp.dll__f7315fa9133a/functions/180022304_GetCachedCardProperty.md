# GetCachedCardProperty

- ea: `0x180022304`
- end: `0x1800225cb`
- name: `GetCachedCardProperty`
- size: `711`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x18001e398`
- `0x18001e480`
- `0x18001e560`
- `0x180023ed8`

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x18001c71c`
- `0x18001f3a4`
- `0x180021a4c`
- `0x180021bc8`
- `0x180022304`
- `0x180027d0c`
- `0x18002cfa0`

## string_xrefs

- `0x180022373`: `Cached_CardProperty`

## pseudocode

```c
__int64 __fastcall GetCachedCardProperty(__int64 a1, const wchar_t *a2, _QWORD *a3, _DWORD *a4, int a5)
{
  _DWORD *v9; // rsi
  unsigned int CardCacheForItem; // eax
  unsigned int CardProperty; // edi
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx
  void *v15; // rbx
  void *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+4Ch] [rbp-B4h]
  _BYTE v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[266]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v27; // [rsp+268h] [rbp+168h]

  Src = 0;
  LODWORD(Size) = 0;
  memset_0(v25, 0, 0x228u);
  if ( !a3 || !a4 )
    return 2148532228LL;
  *a3 = 0;
  v9 = 0;
  *a4 = 0;
  v23 = 7;
  v24 = 1;
  v22 = a1;
  StringCbPrintfW(pszDest, 0x208u, L"%s_%s_%x", L"Cached_CardProperty", a2, a5);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v22);
  CardProperty = CardCacheForItem;
  if ( !CardCacheForItem )
  {
    LODWORD(Size) = *(_DWORD *)(v27 + 12);
    v16 = MIDL_user_allocate((unsigned int)Size);
    v15 = v16;
    if ( !v16 )
    {
      WppTraceIndent(v17, 2u);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_26;
    }
    memcpy_0(v16, (const void *)(v27 + 16), (unsigned int)Size);
    goto LABEL_25;
  }
  if ( CardCacheForItem == 1168 )
  {
    v12 = *(_QWORD *)(a1 + 8);
    if ( !v12 )
    {
      CardProperty = 87;
      WppTraceIndent(0, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          v13,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_30;
    }
    CardProperty = GetCardProperty(v12, a2, &Src, (__int64)&Size, a5);
    if ( CardProperty )
      goto LABEL_16;
    v9 = MIDL_user_allocate((unsigned int)Size + 16LL);
    if ( !v9 )
    {
      WppTraceIndent(v14, 2u);
      CardProperty = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
LABEL_16:
      v15 = Src;
LABEL_26:
      if ( v15 )
        CspFreeH(v15);
      if ( v9 )
        CspFreeH(v9);
      goto LABEL_30;
    }
    v15 = Src;
    v9[3] = Size;
    memcpy_0(v9 + 4, v15, (unsigned int)Size);
    CardProperty = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v22, v9);
    if ( CardProperty )
      goto LABEL_26;
LABEL_25:
    v18 = Size;
    *a3 = v15;
    v15 = 0;
    *a4 = v18;
    goto LABEL_26;
  }
LABEL_30:
  if ( v27 )
    CspFreeH(v27);
  return CardProperty;
}

```

## disassembly

```asm
0x180022304  push    rbp
0x180022306  push    rbx
0x180022307  push    rsi
0x180022308  push    rdi
0x180022309  push    r12
0x18002230b  push    r13
0x18002230d  push    r14
0x18002230f  push    r15
0x180022311  lea     rbp, [rsp-198h]
0x180022319  sub     rsp, 298h
0x180022320  mov     rax, cs:__security_cookie
0x180022327  xor     rax, rsp
0x18002232a  mov     [rbp+1D0h+var_50], rax
0x180022331  mov     r15, r8
0x180022334  mov     r13, rdx
0x180022337  mov     rbx, rcx
0x18002233a  xor     edi, edi
0x18002233c  xor     edx, edx; Val
0x18002233e  mov     [rsp+2D0h+Src], rdi
0x180022343  mov     r8d, 228h; Size
0x180022349  mov     dword ptr [rsp+2D0h+Size], edi
0x18002234d  lea     rcx, [rsp+2D0h+var_280]; void *
0x180022352  mov     r14, r9
0x180022355  call    memset_0
0x18002235a  test    r15, r15
0x18002235d  jz      loc_1800225A3
0x180022363  test    r14, r14
0x180022366  jz      loc_1800225A3
0x18002236c  mov     r12d, [rbp+1D0h+arg_20]
0x180022373  lea     r9, aCachedCardprop; "Cached_CardProperty"
0x18002237a  mov     [r15], rdi
0x18002237d  lea     r8, aSSX; "%s_%s_%x"
0x180022384  mov     [rsp+2D0h+var_2A8], r12d
0x180022389  lea     rcx, [rsp+2D0h+pszDest]; pszDest
0x18002238e  mov     edx, 208h; cbDest
0x180022393  mov     [rsp+2D0h+var_2B0], r13
0x180022398  mov     esi, edi
0x18002239a  mov     [r14], edi
0x18002239d  mov     [rsp+2D0h+var_288], 7
0x1800223a5  mov     [rsp+2D0h+var_284], 1
0x1800223ad  mov     [rsp+2D0h+var_290], rbx
0x1800223b2  call    StringCbPrintfW
0x1800223b7  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x1800223bc  call    CspQueryCardCacheForItem
0x1800223c1  mov     edi, eax
0x1800223c3  test    eax, eax
0x1800223c5  jz      loc_1800224EF
0x1800223cb  cmp     eax, 490h
0x1800223d0  jnz     loc_18002258E
0x1800223d6  mov     rcx, [rbx+8]
0x1800223da  test    rcx, rcx
0x1800223dd  jnz     short loc_180022439
0x1800223df  lea     edx, [rsi+2]
0x1800223e2  lea     edi, [rsi+57h]
0x1800223e5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800223ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223f1  lea     rax, WPP_GLOBAL_Control
0x1800223f8  cmp     rcx, rax
0x1800223fb  jz      loc_18002258E
0x180022401  test    byte ptr [rcx+1Ch], 1
0x180022405  jz      loc_18002258E
0x18002240b  cmp     byte ptr [rcx+19h], 2
0x18002240f  jb      loc_18002258E
0x180022415  mov     rcx, [rcx+10h]
0x180022419  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x180022420  lea     edx, [rsi+1Ch]
0x180022423  mov     [rsp+2D0h+var_2B0], rax
0x180022428  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002242f  call    WPP_SF_ss
0x180022434  jmp     loc_18002258E
0x180022439  lea     r9, [rsp+2D0h+Size]
0x18002243e  mov     dword ptr [rsp+2D0h+var_2B0], r12d
0x180022443  lea     r8, [rsp+2D0h+Src]
0x180022448  mov     rdx, r13
0x18002244b  call    GetCardProperty
0x180022450  mov     edi, eax
0x180022452  test    eax, eax
0x180022454  jnz     short loc_1800224AF
0x180022456  mov     ecx, dword ptr [rsp+2D0h+Size]
0x18002245a  add     rcx, 10h; size
0x18002245e  call    MIDL_user_allocate
0x180022463  mov     rsi, rax
0x180022466  test    rax, rax
0x180022469  jnz     short loc_1800224B9
0x18002246b  lea     edx, [rdi+2]
0x18002246e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022473  lea     edi, [rsi+8]
0x180022476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247d  lea     rax, WPP_GLOBAL_Control
0x180022484  cmp     rcx, rax
0x180022487  jz      short loc_1800224AF
0x180022489  test    byte ptr [rcx+1Ch], 1
0x18002248d  jz      short loc_1800224AF
0x18002248f  cmp     byte ptr [rcx+19h], 2
0x180022493  jb      short loc_1800224AF
0x180022495  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002249c  lea     edx, [rsi+1Dh]
0x18002249f  mov     rcx, [rcx+10h]
0x1800224a3  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800224aa  call    WPP_SF_s
0x1800224af  mov     rbx, [rsp+2D0h+Src]
0x1800224b4  jmp     loc_180022574
0x1800224b9  mov     eax, dword ptr [rsp+2D0h+Size]
0x1800224bd  lea     rcx, [rsi+10h]; void *
0x1800224c1  mov     rbx, [rsp+2D0h+Src]
0x1800224c6  mov     [rsi+0Ch], eax
0x1800224c9  mov     rdx, rbx; Src
0x1800224cc  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x1800224d1  call    memcpy_0
0x1800224d6  mov     rdx, rsi; Destination
0x1800224d9  lea     rcx, [rsp+2D0h+var_290]; struct _CARD_CACHE_QUERY_INFO *
0x1800224de  call    CspAddCardCacheItem
0x1800224e3  mov     edi, eax
0x1800224e5  test    eax, eax
0x1800224e7  jnz     loc_180022574
0x1800224ed  jmp     short loc_180022568
0x1800224ef  mov     rax, [rbp+1D0h+var_68]
0x1800224f6  mov     ecx, [rax+0Ch]; size
0x1800224f9  mov     dword ptr [rsp+2D0h+Size], ecx
0x1800224fd  call    MIDL_user_allocate
0x180022502  mov     rbx, rax
0x180022505  test    rax, rax
0x180022508  jnz     short loc_180022550
0x18002250a  lea     edx, [rax+2]
0x18002250d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022512  lea     edi, [rbx+8]
0x180022515  mov     rcx, cs:WPP_GLOBAL_Control
0x18002251c  lea     rax, WPP_GLOBAL_Control
0x180022523  cmp     rcx, rax
0x180022526  jz      short loc_180022574
0x180022528  test    byte ptr [rcx+1Ch], 1
0x18002252c  jz      short loc_180022574
0x18002252e  cmp     byte ptr [rcx+19h], 2
0x180022532  jb      short loc_180022574
0x180022534  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002253b  lea     edx, [rbx+1Bh]
0x18002253e  mov     rcx, [rcx+10h]
0x180022542  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022549  call    WPP_SF_s
0x18002254e  jmp     short loc_180022574
0x180022550  mov     rdx, [rbp+1D0h+var_68]
0x180022557  mov     rcx, rax; void *
0x18002255a  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x18002255f  add     rdx, 10h; Src
0x180022563  call    memcpy_0
0x180022568  mov     eax, dword ptr [rsp+2D0h+Size]
0x18002256c  mov     [r15], rbx
0x18002256f  xor     ebx, ebx
0x180022571  mov     [r14], eax
0x180022574  test    rbx, rbx
0x180022577  jz      short loc_180022581
0x180022579  mov     rcx, rbx
0x18002257c  call    CspFreeH
0x180022581  test    rsi, rsi
0x180022584  jz      short loc_18002258E
0x180022586  mov     rcx, rsi
0x180022589  call    CspFreeH
0x18002258e  mov     rcx, [rbp+1D0h+var_68]
0x180022595  test    rcx, rcx
0x180022598  jz      short loc_18002259F
0x18002259a  call    CspFreeH
0x18002259f  mov     eax, edi
0x1800225a1  jmp     short loc_1800225A8
0x1800225a3  mov     eax, 80100004h
0x1800225a8  mov     rcx, [rbp+1D0h+var_50]
0x1800225af  xor     rcx, rsp; StackCookie
0x1800225b2  call    __security_check_cookie
0x1800225b7  add     rsp, 298h
0x1800225be  pop     r15
0x1800225c0  pop     r14
0x1800225c2  pop     r13
0x1800225c4  pop     r12
0x1800225c6  pop     rdi
0x1800225c7  pop     rsi
0x1800225c8  pop     rbx
0x1800225c9  pop     rbp
0x1800225ca  retn
```
