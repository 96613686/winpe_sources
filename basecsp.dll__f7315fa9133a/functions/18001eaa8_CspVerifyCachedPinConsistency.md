# CspVerifyCachedPinConsistency

- ea: `0x18001eaa8`
- end: `0x18001ebee`
- name: `CspVerifyCachedPinConsistency`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800102a8`

## callees

- `0x18000a772`
- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001c71c`
- `0x18001eaa8`
- `0x180021bc8`
- `0x18002cfa0`

## string_xrefs

- `0x18001eb37`: `Cached_Pin`

## pseudocode

```c
__int64 __fastcall CspVerifyCachedPinConsistency(__int64 a1, int a2)
{
  __int64 v4; // rcx
  unsigned int CardCacheForItem; // eax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-268h]
  __int64 v10; // [rsp+30h] [rbp-258h] BYREF
  int v11; // [rsp+38h] [rbp-250h]
  int v12; // [rsp+3Ch] [rbp-24Ch]
  wchar_t pszDest[266]; // [rsp+44h] [rbp-244h] BYREF
  __int64 v14; // [rsp+258h] [rbp-30h]

  memset_0(&v10, 0, 0x238u);
  WppTraceIndent(v4, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids, WPP_pszIndent);
  }
  memset_0(&v10, 0, 0x238u);
  v9 = a2;
  StringCbPrintfW(pszDest, 0x104u, L"%s\\%d", L"Cached_Pin", v9);
  v10 = a1;
  v11 = 1;
  v12 = 1;
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v10);
  v6 = v14;
  v7 = CardCacheForItem;
  if ( v14 )
    CspFreeH(v14);
  WppTraceIndent(v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18001eaa8  mov     [rsp+arg_0], rbx
0x18001eaad  mov     [rsp+arg_10], rsi
0x18001eab2  push    rdi
0x18001eab3  sub     rsp, 280h
0x18001eaba  mov     rax, cs:__security_cookie
0x18001eac1  xor     rax, rsp
0x18001eac4  mov     [rsp+288h+var_18], rax
0x18001eacc  mov     edi, edx
0x18001eace  mov     rbx, rcx
0x18001ead1  xor     edx, edx; Val
0x18001ead3  lea     rcx, [rsp+288h+var_258]; void *
0x18001ead8  mov     r8d, 238h; Size
0x18001eade  call    memset_0
0x18001eae3  xor     edx, edx
0x18001eae5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001eaea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaf1  lea     rsi, WPP_GLOBAL_Control
0x18001eaf8  cmp     rcx, rsi
0x18001eafb  jz      short loc_18001EB25
0x18001eafd  test    byte ptr [rcx+1Ch], 2
0x18001eb01  jz      short loc_18001EB25
0x18001eb03  cmp     byte ptr [rcx+19h], 5
0x18001eb07  jb      short loc_18001EB25
0x18001eb09  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001eb10  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001eb17  mov     rcx, [rcx+10h]
0x18001eb1b  mov     edx, 14h
0x18001eb20  call    WPP_SF_s
0x18001eb25  xor     edx, edx; Val
0x18001eb27  lea     rcx, [rsp+288h+var_258]; void *
0x18001eb2c  mov     r8d, 238h; Size
0x18001eb32  call    memset_0
0x18001eb37  lea     r9, aCachedPin; "Cached_Pin"
0x18001eb3e  mov     [rsp+288h+var_268], edi
0x18001eb42  lea     r8, aSD; "%s\\%d"
0x18001eb49  mov     edx, 104h; cbDest
0x18001eb4e  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18001eb53  call    StringCbPrintfW
0x18001eb58  mov     edi, 1
0x18001eb5d  mov     [rsp+288h+var_258], rbx
0x18001eb62  lea     rcx, [rsp+288h+var_258]; struct _CARD_CACHE_QUERY_INFO *
0x18001eb67  mov     [rsp+288h+var_250], edi
0x18001eb6b  mov     [rsp+288h+var_24C], edi
0x18001eb6f  call    CspQueryCardCacheForItem
0x18001eb74  mov     rcx, [rsp+288h+var_30]
0x18001eb7c  mov     ebx, eax
0x18001eb7e  test    rcx, rcx
0x18001eb81  jz      short loc_18001EB88
0x18001eb83  call    CspFreeH
0x18001eb88  mov     edx, edi
0x18001eb8a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001eb8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb96  cmp     rcx, rsi
0x18001eb99  jz      short loc_18001EBC7
0x18001eb9b  test    byte ptr [rcx+1Ch], 2
0x18001eb9f  jz      short loc_18001EBC7
0x18001eba1  cmp     byte ptr [rcx+19h], 5
0x18001eba5  jb      short loc_18001EBC7
0x18001eba7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ebae  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001ebb5  mov     rcx, [rcx+10h]
0x18001ebb9  mov     edx, 15h
0x18001ebbe  mov     [rsp+288h+var_268], ebx
0x18001ebc2  call    WPP_SF_sD
0x18001ebc7  mov     eax, ebx
0x18001ebc9  mov     rcx, [rsp+288h+var_18]
0x18001ebd1  xor     rcx, rsp; StackCookie
0x18001ebd4  call    __security_check_cookie
0x18001ebd9  lea     r11, [rsp+288h+var_8]
0x18001ebe1  mov     rbx, [r11+10h]
0x18001ebe5  mov     rsi, [r11+20h]
0x18001ebe9  mov     rsp, r11
0x18001ebec  pop     rdi
0x18001ebed  retn
```
