# I_CspQueryCapabilities(_CARD_STATE *,_CARD_CAPABILITIES *)

- ea: `0x18001cd44`
- end: `0x18001cecd`
- name: `?I_CspQueryCapabilities@@YAKPEAU_CARD_STATE@@PEAU_CARD_CAPABILITIES@@@Z`
- size: `393`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, struct _CARD_CAPABILITIES *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e398`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x18001c71c`
- `0x18001cd44`
- `0x18001f3a4`
- `0x180021928`
- `0x18002217c`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x18001cd86`: `Cached_CardCapabilities`

## pseudocode

```c
__int64 __fastcall I_CspQueryCapabilities(struct _CARD_STATE *a1, struct _CARD_CAPABILITIES *a2)
{
  unsigned int CachedCardData; // eax
  __int64 v5; // rcx
  _QWORD *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // r9d
  int v11; // [rsp+40h] [rbp-248h] BYREF
  _QWORD *v12; // [rsp+48h] [rbp-240h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-238h] BYREF

  v12 = 0;
  v11 = 0;
  StringCbPrintfW(pszDest, 0x104u, L"%s", L"Cached_CardCapabilities");
  CachedCardData = GetCachedCardData(a1, pszDest, 0, 0, &v12, &v11, 0);
  v6 = v12;
  v7 = CachedCardData;
  if ( CachedCardData )
  {
    if ( CachedCardData == 1168 )
    {
      v8 = *((_QWORD *)a1 + 1);
      if ( v8 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, struct _CARD_CAPABILITIES *))(v8 + 128))(*((_QWORD *)a1 + 1), a2);
        if ( !v7 )
          v7 = AddCachedCardData(a1, pszDest, 0, 0, a2, 12, 0);
      }
      else
      {
        v7 = 87;
        WppTraceIndent(v5, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
            v9,
            (__int64)"pCardState->pCardData");
        }
      }
    }
  }
  else if ( v11 == 12 )
  {
    *(_QWORD *)a2 = *v12;
    *((_DWORD *)a2 + 2) = *((_DWORD *)v6 + 2);
  }
  else
  {
    v7 = -2146893820;
  }
  if ( v6 )
    CspFreeH(v6);
  return v7;
}

```

## disassembly

```asm
0x18001cd44  mov     [rsp+arg_10], rbx
0x18001cd49  push    rbp
0x18001cd4a  push    rsi
0x18001cd4b  push    rdi
0x18001cd4c  sub     rsp, 270h
0x18001cd53  mov     rax, cs:__security_cookie
0x18001cd5a  xor     rax, rsp
0x18001cd5d  mov     [rsp+288h+var_28], rax
0x18001cd65  mov     rsi, rdx
0x18001cd68  mov     [rsp+288h+var_240], 0
0x18001cd71  mov     rbp, rcx
0x18001cd74  mov     [rsp+288h+var_248], 0
0x18001cd7c  mov     edx, 104h; cbDest
0x18001cd81  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18001cd86  lea     r9, aCachedCardcapa; "Cached_CardCapabilities"
0x18001cd8d  lea     r8, aS; "%s"
0x18001cd94  call    StringCbPrintfW
0x18001cd99  lea     rax, [rsp+288h+var_248]
0x18001cd9e  mov     [rsp+288h+var_258], 0
0x18001cda7  mov     [rsp+288h+var_260], rax
0x18001cdac  lea     rdx, [rsp+288h+pszDest]
0x18001cdb1  lea     rax, [rsp+288h+var_240]
0x18001cdb6  xor     r9d, r9d
0x18001cdb9  xor     r8d, r8d
0x18001cdbc  mov     [rsp+288h+var_268], rax
0x18001cdc1  mov     rcx, rbp
0x18001cdc4  call    GetCachedCardData
0x18001cdc9  mov     rdi, [rsp+288h+var_240]
0x18001cdce  mov     ebx, eax
0x18001cdd0  test    eax, eax
0x18001cdd2  jz      loc_18001CE7F
0x18001cdd8  cmp     eax, 490h
0x18001cddd  jnz     loc_18001CE9B
0x18001cde3  mov     rax, [rbp+8]
0x18001cde7  test    rax, rax
0x18001cdea  jnz     short loc_18001CE3F
0x18001cdec  lea     edx, [rax+2]
0x18001cdef  lea     ebx, [rax+57h]
0x18001cdf2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001cdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdfe  lea     rax, WPP_GLOBAL_Control
0x18001ce05  cmp     rcx, rax
0x18001ce08  jz      loc_18001CE9B
0x18001ce0e  test    byte ptr [rcx+1Ch], 1
0x18001ce12  jz      loc_18001CE9B
0x18001ce18  cmp     byte ptr [rcx+19h], 2
0x18001ce1c  jb      short loc_18001CE9B
0x18001ce1e  mov     rcx, [rcx+10h]
0x18001ce22  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001ce29  lea     edx, [rbx-4Dh]
0x18001ce2c  mov     [rsp+288h+var_268], rax
0x18001ce31  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001ce38  call    WPP_SF_ss
0x18001ce3d  jmp     short loc_18001CE9B
0x18001ce3f  mov     rcx, rax
0x18001ce42  mov     rdx, rsi
0x18001ce45  mov     rax, [rax+80h]
0x18001ce4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce51  mov     ebx, eax
0x18001ce53  test    eax, eax
0x18001ce55  jnz     short loc_18001CE9B
0x18001ce57  mov     dword ptr [rsp+288h+var_258], eax
0x18001ce5b  lea     rdx, [rsp+288h+pszDest]
0x18001ce60  mov     dword ptr [rsp+288h+var_260], 0Ch
0x18001ce68  xor     r9d, r9d
0x18001ce6b  xor     r8d, r8d
0x18001ce6e  mov     [rsp+288h+var_268], rsi
0x18001ce73  mov     rcx, rbp
0x18001ce76  call    AddCachedCardData
0x18001ce7b  mov     ebx, eax
0x18001ce7d  jmp     short loc_18001CE9B
0x18001ce7f  cmp     [rsp+288h+var_248], 0Ch
0x18001ce84  jz      short loc_18001CE8D
0x18001ce86  mov     ebx, 80090004h
0x18001ce8b  jmp     short loc_18001CE9B
0x18001ce8d  movsd   xmm0, qword ptr [rdi]
0x18001ce91  movsd   qword ptr [rsi], xmm0
0x18001ce95  mov     eax, [rdi+8]
0x18001ce98  mov     [rsi+8], eax
0x18001ce9b  test    rdi, rdi
0x18001ce9e  jz      short loc_18001CEA8
0x18001cea0  mov     rcx, rdi
0x18001cea3  call    CspFreeH
0x18001cea8  mov     eax, ebx
0x18001ceaa  mov     rcx, [rsp+288h+var_28]
0x18001ceb2  xor     rcx, rsp; StackCookie
0x18001ceb5  call    __security_check_cookie
0x18001ceba  mov     rbx, [rsp+288h+arg_10]
0x18001cec2  add     rsp, 270h
0x18001cec9  pop     rdi
0x18001ceca  pop     rsi
0x18001cecb  pop     rbp
0x18001cecc  retn
```
