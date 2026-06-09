# CspAuthenticatePin

- ea: `0x18001d568`
- end: `0x18001d883`
- name: `CspAuthenticatePin`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18002b730`

## callees

- `0x18000a772`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x18001c71c`
- `0x18001d568`
- `0x18001f3a4`
- `0x180021a4c`
- `0x180021bc8`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001d5fe`: `Cached_Pin`

## pseudocode

```c
__int64 __fastcall CspAuthenticatePin(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  void *v8; // rdi
  __int64 v9; // rcx
  unsigned int CardCacheForItem; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rcx
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r10
  int v18; // r9d
  const wchar_t *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // [rsp+50h] [rbp-278h] BYREF
  int v23; // [rsp+58h] [rbp-270h]
  int v24; // [rsp+5Ch] [rbp-26Ch]
  wchar_t pszDest[266]; // [rsp+64h] [rbp-264h] BYREF
  __int64 v26; // [rsp+278h] [rbp-50h]
  int v27; // [rsp+280h] [rbp-48h]

  memset_0(&v22, 0, 0x238u);
  v8 = 0;
  WppTraceIndent(v9, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v22, 0, 0x238u);
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%d", L"Cached_Pin", a2);
  v23 = 1;
  v24 = 1;
  v22 = a1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v22);
  v12 = CardCacheForItem;
  if ( CardCacheForItem )
  {
    if ( CardCacheForItem != 1168 )
      goto LABEL_9;
    if ( v27 == 1 )
    {
      v12 = -2146434965;
      goto LABEL_9;
    }
    v15 = MIDL_user_allocate(0x10u);
    v8 = v15;
    if ( !v15 )
    {
      WppTraceIndent(v16, 2u);
      v12 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_9;
    }
    v12 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v22, v15);
    if ( v12 )
      goto LABEL_36;
  }
  v17 = *(_QWORD *)(a1 + 8);
  if ( v17 )
  {
    if ( *(_DWORD *)v17 >= 6u )
    {
      v21 = (*(_DWORD *)(a3 + 4) != 0 ? 0x20000000 : 0) | 0x40u;
      if ( (a4 & 0x40) == 0 )
        v21 = *(_DWORD *)(a3 + 4) != 0 ? 0x20000000 : 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, __int64, __int64, _QWORD))(v17 + 360))(
              v17,
              a2,
              v21,
              *(_QWORD *)(a3 + 16),
              *(_DWORD *)(a3 + 12),
              a3 + 48,
              a3 + 40,
              0);
    }
    else
    {
      v19 = L"user";
      if ( a2 != 1 )
        v19 = L"admin";
      v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD))(v17 + 160))(
              v17,
              v19,
              *(_QWORD *)(a3 + 16),
              *(unsigned int *)(a3 + 12),
              0);
    }
    v12 = v20;
  }
  else
  {
    v12 = 87;
    WppTraceIndent(v11, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v18,
        (__int64)"pCardState->pCardData");
    }
  }
  if ( v8 )
LABEL_36:
    CspFreeH(v8);
LABEL_9:
  v13 = v26;
  if ( v26 )
    CspFreeH(v26);
  WppTraceIndent(v13, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      v12);
  }
  return v12;
}

```

## disassembly

```asm
0x18001d568  mov     [rsp+arg_18], rbx
0x18001d56d  push    rbp
0x18001d56e  push    rsi
0x18001d56f  push    rdi
0x18001d570  push    r14
0x18001d572  push    r15
0x18001d574  sub     rsp, 2A0h
0x18001d57b  mov     rax, cs:__security_cookie
0x18001d582  xor     rax, rsp
0x18001d585  mov     [rsp+2C8h+var_38], rax
0x18001d58d  mov     rsi, r8
0x18001d590  mov     r14d, edx
0x18001d593  mov     rbp, rcx
0x18001d596  mov     ebx, 238h
0x18001d59b  mov     r8d, ebx; Size
0x18001d59e  lea     rcx, [rsp+2C8h+var_278]; void *
0x18001d5a3  xor     edx, edx; Val
0x18001d5a5  mov     r15d, r9d
0x18001d5a8  call    memset_0
0x18001d5ad  xor     edx, edx
0x18001d5af  xor     edi, edi
0x18001d5b1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d5bd  lea     rax, WPP_GLOBAL_Control
0x18001d5c4  cmp     rcx, rax
0x18001d5c7  jz      short loc_18001D5EF
0x18001d5c9  test    byte ptr [rcx+1Ch], 2
0x18001d5cd  jz      short loc_18001D5EF
0x18001d5cf  cmp     byte ptr [rcx+19h], 5
0x18001d5d3  jb      short loc_18001D5EF
0x18001d5d5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d5dc  lea     edx, [rdi+16h]
0x18001d5df  mov     rcx, [rcx+10h]
0x18001d5e3  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d5ea  call    WPP_SF_s
0x18001d5ef  mov     r8, rbx; Size
0x18001d5f2  lea     rcx, [rsp+2C8h+var_278]; void *
0x18001d5f7  xor     edx, edx; Val
0x18001d5f9  call    memset_0
0x18001d5fe  lea     r9, aCachedPin; "Cached_Pin"
0x18001d605  mov     dword ptr [rsp+2C8h+var_2A8], r14d
0x18001d60a  lea     r8, aSD; "%s\\%d"
0x18001d611  mov     edx, 104h; cbDest
0x18001d616  lea     rcx, [rsp+2C8h+pszDest]; pszDest
0x18001d61b  call    StringCbPrintfW
0x18001d620  lea     rcx, [rsp+2C8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x18001d625  mov     [rsp+2C8h+var_270], 1
0x18001d62d  mov     [rsp+2C8h+var_26C], 1
0x18001d635  mov     [rsp+2C8h+var_278], rbp
0x18001d63a  call    CspQueryCardCacheForItem
0x18001d63f  mov     ebx, eax
0x18001d641  test    eax, eax
0x18001d643  jz      loc_18001D765
0x18001d649  cmp     eax, 490h
0x18001d64e  jnz     short loc_18001D663
0x18001d650  cmp     [rsp+2C8h+var_48], 1
0x18001d658  jnz     loc_18001D6E7
0x18001d65e  mov     ebx, 8010006Bh
0x18001d663  lea     rsi, WPP_GLOBAL_Control
0x18001d66a  mov     rcx, [rsp+2C8h+var_50]
0x18001d672  test    rcx, rcx
0x18001d675  jz      short loc_18001D67C
0x18001d677  call    CspFreeH
0x18001d67c  mov     edx, 1
0x18001d681  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d686  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d68d  cmp     rcx, rsi
0x18001d690  jz      short loc_18001D6BE
0x18001d692  test    byte ptr [rcx+1Ch], 2
0x18001d696  jz      short loc_18001D6BE
0x18001d698  cmp     byte ptr [rcx+19h], 5
0x18001d69c  jb      short loc_18001D6BE
0x18001d69e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d6a5  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d6ac  mov     rcx, [rcx+10h]
0x18001d6b0  mov     edx, 19h
0x18001d6b5  mov     dword ptr [rsp+2C8h+var_2A8], ebx
0x18001d6b9  call    WPP_SF_sD
0x18001d6be  mov     eax, ebx
0x18001d6c0  mov     rcx, [rsp+2C8h+var_38]
0x18001d6c8  xor     rcx, rsp; StackCookie
0x18001d6cb  call    __security_check_cookie
0x18001d6d0  mov     rbx, [rsp+2C8h+arg_18]
0x18001d6d8  add     rsp, 2A0h
0x18001d6df  pop     r15
0x18001d6e1  pop     r14
0x18001d6e3  pop     rdi
0x18001d6e4  pop     rsi
0x18001d6e5  pop     rbp
0x18001d6e6  retn
0x18001d6e7  mov     ecx, 10h; size
0x18001d6ec  call    MIDL_user_allocate
0x18001d6f1  mov     rdi, rax
0x18001d6f4  test    rax, rax
0x18001d6f7  jnz     short loc_18001D74E
0x18001d6f9  lea     edx, [rax+2]
0x18001d6fc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d701  lea     ebx, [rdi+8]
0x18001d704  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d70b  lea     rsi, WPP_GLOBAL_Control
0x18001d712  cmp     rcx, rsi
0x18001d715  jz      loc_18001D66A
0x18001d71b  test    byte ptr [rcx+1Ch], 1
0x18001d71f  jz      loc_18001D66A
0x18001d725  cmp     byte ptr [rcx+19h], 2
0x18001d729  jb      loc_18001D66A
0x18001d72f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001d736  lea     edx, [rdi+17h]
0x18001d739  mov     rcx, [rcx+10h]
0x18001d73d  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d744  call    WPP_SF_s
0x18001d749  jmp     loc_18001D66A
0x18001d74e  mov     rdx, rax; Destination
0x18001d751  lea     rcx, [rsp+2C8h+var_278]; struct _CARD_CACHE_QUERY_INFO *
0x18001d756  call    CspAddCardCacheItem
0x18001d75b  mov     ebx, eax
0x18001d75d  test    eax, eax
0x18001d75f  jnz     loc_18001D86F
0x18001d765  mov     r10, [rbp+8]
0x18001d769  test    r10, r10
0x18001d76c  jnz     short loc_18001D7C9
0x18001d76e  lea     ebx, [r10+57h]
0x18001d772  lea     edx, [rbx-55h]
0x18001d775  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001d77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d781  lea     rsi, WPP_GLOBAL_Control
0x18001d788  cmp     rcx, rsi
0x18001d78b  jz      loc_18001D864
0x18001d791  test    byte ptr [rcx+1Ch], 1
0x18001d795  jz      loc_18001D864
0x18001d79b  cmp     byte ptr [rcx+19h], 2
0x18001d79f  jb      loc_18001D864
0x18001d7a5  mov     rcx, [rcx+10h]
0x18001d7a9  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001d7b0  lea     edx, [rbx-3Fh]
0x18001d7b3  mov     [rsp+2C8h+var_2A8], rax
0x18001d7b8  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001d7bf  call    WPP_SF_ss
0x18001d7c4  jmp     loc_18001D864
0x18001d7c9  cmp     dword ptr [r10], 6
0x18001d7cd  jnb     short loc_18001D807
0x18001d7cf  mov     r9d, [rsi+0Ch]
0x18001d7d3  lea     rax, aAdmin; "admin"
0x18001d7da  mov     r8, [rsi+10h]
0x18001d7de  lea     rdx, aUser; "user"
0x18001d7e5  cmp     r14d, 1
0x18001d7e9  mov     [rsp+2C8h+var_2A8], 0
0x18001d7f2  mov     rcx, r10
0x18001d7f5  cmovnz  rdx, rax
0x18001d7f9  mov     rax, [r10+0A0h]
0x18001d800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d805  jmp     short loc_18001D85B
0x18001d807  mov     eax, [rsi+4]
0x18001d80a  lea     r9, [rsi+30h]
0x18001d80e  neg     eax
0x18001d810  mov     [rsp+2C8h+var_290], 0
0x18001d819  lea     rax, [rsi+28h]
0x18001d81d  mov     edx, r14d
0x18001d820  sbb     ecx, ecx
0x18001d822  mov     [rsp+2C8h+var_298], rax
0x18001d827  mov     rax, [r10+168h]
0x18001d82e  and     ecx, 20000000h
0x18001d834  mov     r8d, ecx
0x18001d837  mov     [rsp+2C8h+var_2A0], r9
0x18001d83c  mov     r9, [rsi+10h]
0x18001d840  or      r8d, 40h
0x18001d844  test    r15b, 40h
0x18001d848  cmovz   r8d, ecx
0x18001d84c  mov     ecx, [rsi+0Ch]
0x18001d84f  mov     dword ptr [rsp+2C8h+var_2A8], ecx
0x18001d853  mov     rcx, r10
0x18001d856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85b  lea     rsi, WPP_GLOBAL_Control
0x18001d862  mov     ebx, eax
0x18001d864  test    rdi, rdi
0x18001d867  jz      loc_18001D66A
0x18001d86d  jmp     short loc_18001D876
0x18001d86f  lea     rsi, WPP_GLOBAL_Control
0x18001d876  mov     rcx, rdi
0x18001d879  call    CspFreeH
0x18001d87e  jmp     loc_18001D66A
```
