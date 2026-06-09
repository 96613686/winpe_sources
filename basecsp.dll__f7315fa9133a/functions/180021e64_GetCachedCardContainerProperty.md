# GetCachedCardContainerProperty

- ea: `0x180021e64`
- end: `0x180022174`
- name: `GetCachedCardContainerProperty`
- size: `784`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180020824`
- `0x180023758`

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
- `0x180021e64`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x180021edd`: `Cached_ContainerProperty`

## pseudocode

```c
__int64 __fastcall GetCachedCardContainerProperty(__int64 a1, unsigned __int8 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  int v6; // r12d
  _DWORD *v8; // rsi
  unsigned int CardCacheForItem; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rbx
  int v13; // r9d
  __int64 v14; // rdx
  void *v15; // rdi
  unsigned int v16; // eax
  void *v17; // rcx
  __int64 v18; // rcx
  void *v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  size_t Size[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  _BYTE v27[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[266]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v29; // [rsp+278h] [rbp+178h]

  v6 = a2;
  LODWORD(Size[0]) = 0;
  memset_0(v27, 0, 0x228u);
  if ( !a4 || !a5 )
    return 2148532228LL;
  v8 = 0;
  *a4 = 0;
  *a5 = 0;
  v25 = 7;
  v26 = 1;
  v24 = a1;
  StringCbPrintfW(pszDest, 0x208u, L"%s_%s_%d", L"Cached_ContainerProperty", L"PIN Identifier", v6);
  CardCacheForItem = CspQueryCardCacheForItem((struct _CARD_CACHE_QUERY_INFO *)&v24);
  v11 = CardCacheForItem;
  if ( !CardCacheForItem )
  {
    LODWORD(Size[0]) = *(_DWORD *)(v29 + 12);
    v19 = MIDL_user_allocate(LODWORD(Size[0]));
    v15 = v19;
    if ( !v19 )
    {
      WppTraceIndent(v20, 2u);
      v11 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_34;
    }
    memcpy_0(v19, (const void *)(v29 + 16), LODWORD(Size[0]));
    goto LABEL_31;
  }
  if ( CardCacheForItem == 1168 )
  {
    v12 = *(_QWORD *)(a1 + 8);
    if ( !v12 )
    {
      v11 = 87;
      WppTraceIndent(v10, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          v13,
          (__int64)"pCardState->pCardData");
      }
      goto LABEL_34;
    }
    v15 = MIDL_user_allocate(4u);
    if ( !v15 )
    {
      v11 = 14;
      goto LABEL_23;
    }
    LOBYTE(v14) = v6;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, void *, int, size_t *, _DWORD))(v12 + 384))(
            v12,
            v14,
            L"PIN Identifier",
            v15,
            4,
            Size,
            0);
    v17 = 0;
    v11 = v16;
    if ( v16 )
    {
      v17 = v15;
      v15 = 0;
    }
    if ( v17 )
      CspFreeH(v17);
    if ( v11 )
      goto LABEL_23;
    v8 = MIDL_user_allocate(LODWORD(Size[0]) + 16LL);
    if ( !v8 )
    {
      WppTraceIndent(v18, 2u);
      v11 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_23;
    }
    v8[3] = Size[0];
    memcpy_0(v8 + 4, v15, LODWORD(Size[0]));
    v11 = CspAddCardCacheItem((struct _CARD_CACHE_QUERY_INFO *)&v24, v8);
    if ( v11 )
    {
LABEL_23:
      if ( v15 )
        CspFreeH(v15);
      goto LABEL_32;
    }
LABEL_31:
    v21 = Size[0];
    *a4 = v15;
    *a5 = v21;
LABEL_32:
    if ( v8 )
      CspFreeH(v8);
  }
LABEL_34:
  if ( v29 )
    CspFreeH(v29);
  return v11;
}

```

## disassembly

```asm
0x180021e64  push    rbp
0x180021e66  push    rbx
0x180021e67  push    rsi
0x180021e68  push    rdi
0x180021e69  push    r12
0x180021e6b  push    r14
0x180021e6d  push    r15
0x180021e6f  lea     rbp, [rsp-1A0h]
0x180021e77  sub     rsp, 2A0h
0x180021e7e  mov     rax, cs:__security_cookie
0x180021e85  xor     rax, rsp
0x180021e88  mov     [rbp+1D0h+var_40], rax
0x180021e8f  mov     r14, [rbp+1D0h+arg_20]
0x180021e96  mov     rdi, rcx
0x180021e99  movzx   r12d, dl
0x180021e9d  lea     rcx, [rsp+2D0h+var_270]; void *
0x180021ea2  xor     edx, edx; Val
0x180021ea4  mov     dword ptr [rsp+2D0h+Size], 0
0x180021eac  mov     r8d, 228h; Size
0x180021eb2  mov     r15, r9
0x180021eb5  call    memset_0
0x180021eba  test    r15, r15
0x180021ebd  jz      loc_18002214E
0x180021ec3  test    r14, r14
0x180021ec6  jz      loc_18002214E
0x180021ecc  xor     esi, esi
0x180021ece  mov     dword ptr [rsp+2D0h+var_2A8], r12d
0x180021ed3  lea     rax, aPinIdentifier; "PIN Identifier"
0x180021eda  mov     [r15], rsi
0x180021edd  lea     r9, aCachedContaine; "Cached_ContainerProperty"
0x180021ee4  mov     [r14], esi
0x180021ee7  lea     r8, aSSD; "%s_%s_%d"
0x180021eee  mov     [rsp+2D0h+var_278], 7
0x180021ef6  mov     edx, 208h; cbDest
0x180021efb  mov     [rsp+2D0h+var_274], 1
0x180021f03  lea     rcx, [rsp+2D0h+pszDest]; pszDest
0x180021f08  mov     [rsp+2D0h+var_280], rdi
0x180021f0d  mov     [rsp+2D0h+var_2B0], rax
0x180021f12  call    StringCbPrintfW
0x180021f17  lea     rcx, [rsp+2D0h+var_280]; struct _CARD_CACHE_QUERY_INFO *
0x180021f1c  call    CspQueryCardCacheForItem
0x180021f21  mov     ebx, eax
0x180021f23  test    eax, eax
0x180021f25  jz      loc_1800220A9
0x180021f2b  cmp     eax, 490h
0x180021f30  jnz     loc_180022139
0x180021f36  mov     rbx, [rdi+8]
0x180021f3a  test    rbx, rbx
0x180021f3d  jnz     short loc_180021F99
0x180021f3f  lea     edx, [rsi+2]
0x180021f42  lea     ebx, [rsi+57h]
0x180021f45  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f51  lea     rax, WPP_GLOBAL_Control
0x180021f58  cmp     rcx, rax
0x180021f5b  jz      loc_180022139
0x180021f61  test    byte ptr [rcx+1Ch], 1
0x180021f65  jz      loc_180022139
0x180021f6b  cmp     byte ptr [rcx+19h], 2
0x180021f6f  jb      loc_180022139
0x180021f75  mov     rcx, [rcx+10h]
0x180021f79  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x180021f80  lea     edx, [rsi+19h]
0x180021f83  mov     [rsp+2D0h+var_2B0], rax
0x180021f88  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021f8f  call    WPP_SF_ss
0x180021f94  jmp     loc_180022139
0x180021f99  mov     ecx, 4; size
0x180021f9e  call    MIDL_user_allocate
0x180021fa3  mov     rdi, rax
0x180021fa6  test    rax, rax
0x180021fa9  jnz     short loc_180021FB3
0x180021fab  lea     ebx, [rax+0Eh]
0x180021fae  jmp     loc_180022093
0x180021fb3  lea     rax, [rsp+2D0h+Size]
0x180021fb8  mov     [rsp+2D0h+var_2A0], esi
0x180021fbc  mov     [rsp+2D0h+var_2A8], rax
0x180021fc1  lea     r8, aPinIdentifier; "PIN Identifier"
0x180021fc8  mov     rax, [rbx+180h]
0x180021fcf  mov     r9, rdi
0x180021fd2  mov     dl, r12b
0x180021fd5  mov     dword ptr [rsp+2D0h+var_2B0], 4
0x180021fdd  mov     rcx, rbx
0x180021fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fe5  xor     ecx, ecx
0x180021fe7  mov     ebx, eax
0x180021fe9  test    eax, eax
0x180021feb  cmovnz  rcx, rdi
0x180021fef  xor     eax, eax
0x180021ff1  test    ebx, ebx
0x180021ff3  cmovnz  rdi, rax
0x180021ff7  test    rcx, rcx
0x180021ffa  jz      short loc_180022001
0x180021ffc  call    CspFreeH
0x180022001  test    ebx, ebx
0x180022003  jnz     loc_180022093
0x180022009  mov     ecx, dword ptr [rsp+2D0h+Size]
0x18002200d  add     rcx, 10h; size
0x180022011  call    MIDL_user_allocate
0x180022016  mov     rsi, rax
0x180022019  test    rax, rax
0x18002201c  jnz     short loc_180022064
0x18002201e  lea     edx, [rbx+2]
0x180022021  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022026  lea     ebx, [rsi+8]
0x180022029  mov     rcx, cs:WPP_GLOBAL_Control
0x180022030  lea     rax, WPP_GLOBAL_Control
0x180022037  cmp     rcx, rax
0x18002203a  jz      short loc_180022093
0x18002203c  test    byte ptr [rcx+1Ch], 1
0x180022040  jz      short loc_180022093
0x180022042  cmp     byte ptr [rcx+19h], 2
0x180022046  jb      short loc_180022093
0x180022048  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002204f  lea     edx, [rsi+1Ah]
0x180022052  mov     rcx, [rcx+10h]
0x180022056  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002205d  call    WPP_SF_s
0x180022062  jmp     short loc_180022093
0x180022064  mov     eax, dword ptr [rsp+2D0h+Size]
0x180022068  lea     rcx, [rsi+10h]; void *
0x18002206c  mov     [rsi+0Ch], eax
0x18002206f  mov     rdx, rdi; Src
0x180022072  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x180022077  call    memcpy_0
0x18002207c  mov     rdx, rsi; Destination
0x18002207f  lea     rcx, [rsp+2D0h+var_280]; struct _CARD_CACHE_QUERY_INFO *
0x180022084  call    CspAddCardCacheItem
0x180022089  mov     ebx, eax
0x18002208b  test    eax, eax
0x18002208d  jz      loc_180022122
0x180022093  test    rdi, rdi
0x180022096  jz      loc_18002212C
0x18002209c  mov     rcx, rdi
0x18002209f  call    CspFreeH
0x1800220a4  jmp     loc_18002212C
0x1800220a9  mov     rax, [rbp+1D0h+var_58]
0x1800220b0  mov     ecx, [rax+0Ch]; size
0x1800220b3  mov     dword ptr [rsp+2D0h+Size], ecx
0x1800220b7  call    MIDL_user_allocate
0x1800220bc  mov     rdi, rax
0x1800220bf  test    rax, rax
0x1800220c2  jnz     short loc_18002210A
0x1800220c4  lea     edx, [rax+2]
0x1800220c7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800220cc  lea     ebx, [rdi+8]
0x1800220cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220d6  lea     rax, WPP_GLOBAL_Control
0x1800220dd  cmp     rcx, rax
0x1800220e0  jz      short loc_180022139
0x1800220e2  test    byte ptr [rcx+1Ch], 1
0x1800220e6  jz      short loc_180022139
0x1800220e8  cmp     byte ptr [rcx+19h], 2
0x1800220ec  jb      short loc_180022139
0x1800220ee  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800220f5  lea     edx, [rdi+18h]
0x1800220f8  mov     rcx, [rcx+10h]
0x1800220fc  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022103  call    WPP_SF_s
0x180022108  jmp     short loc_180022139
0x18002210a  mov     rdx, [rbp+1D0h+var_58]
0x180022111  mov     rcx, rax; void *
0x180022114  mov     r8d, dword ptr [rsp+2D0h+Size]; Size
0x180022119  add     rdx, 10h; Src
0x18002211d  call    memcpy_0
0x180022122  mov     eax, dword ptr [rsp+2D0h+Size]
0x180022126  mov     [r15], rdi
0x180022129  mov     [r14], eax
0x18002212c  test    rsi, rsi
0x18002212f  jz      short loc_180022139
0x180022131  mov     rcx, rsi
0x180022134  call    CspFreeH
0x180022139  mov     rcx, [rbp+1D0h+var_58]
0x180022140  test    rcx, rcx
0x180022143  jz      short loc_18002214A
0x180022145  call    CspFreeH
0x18002214a  mov     eax, ebx
0x18002214c  jmp     short loc_180022153
0x18002214e  mov     eax, 80100004h
0x180022153  mov     rcx, [rbp+1D0h+var_40]
0x18002215a  xor     rcx, rsp; StackCookie
0x18002215d  call    __security_check_cookie
0x180022162  add     rsp, 2A0h
0x180022169  pop     r15
0x18002216b  pop     r14
0x18002216d  pop     r12
0x18002216f  pop     rdi
0x180022170  pop     rsi
0x180022171  pop     rbx
0x180022172  pop     rbp
0x180022173  retn
```
