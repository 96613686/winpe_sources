# CspQueryCardCacheForItem

- ea: `0x180021bc8`
- end: `0x180021dd3`
- name: `CspQueryCardCacheForItem`
- size: `523`
- prototype: `__int64 __fastcall(struct _CARD_CACHE_QUERY_INFO *)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d568`
- `0x18001eaa8`
- `0x1800212b0`
- `0x180021e64`
- `0x18002217c`
- `0x180022304`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001f3a4`
- `0x18002140c`
- `0x180021724`
- `0x180021bc8`
- `0x1800226f8`

## pseudocode

```c
__int64 __fastcall CspQueryCardCacheForItem(struct _CARD_CACHE_QUERY_INFO *a1)
{
  __int64 v2; // rcx
  _DWORD *v3; // rax
  unsigned int CardCacheFile; // edi
  int v5; // r9d
  PVOID v6; // rcx
  BYTE *pbData; // rsi
  BOOL v9; // edx
  struct _CRYPTOAPI_BLOB v10; // [rsp+30h] [rbp-38h] BYREF

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  v2 = *(_QWORD *)a1;
  v3 = *(_DWORD **)(*(_QWORD *)a1 + 8LL);
  if ( !v3 )
  {
    CardCacheFile = 87;
    WppTraceIndent(v2, 2u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
        v5,
        (__int64)"pInfo->pCardState->pCardData");
    }
    goto LABEL_36;
  }
  if ( *v3 >= 6u && *(_DWORD *)(v2 + 696) == 3 && *((_DWORD *)a1 + 2) != 1 )
    return 1168;
  if ( *((_DWORD *)a1 + 3) == 1 && !*((_DWORD *)a1 + 137) )
  {
    CardCacheFile = I_CspReadCardCacheFile(
                      (struct _CARD_STATE *)v2,
                      (struct _CARD_CACHE_QUERY_INFO *)((char *)a1 + 540));
    if ( CardCacheFile )
      goto LABEL_36;
    *((_DWORD *)a1 + 137) = 1;
  }
  *((_QWORD *)a1 + 69) = 0;
  v10 = 0;
  CardCacheFile = MyCacheLookupItem(a1, &v10);
  if ( !CardCacheFile )
  {
    pbData = v10.pbData;
    if ( v10.cbData < 0x10
      || (v6 = (PVOID)(*((unsigned int *)v10.pbData + 3) + 16LL), (unsigned __int64)v6 > v10.cbData) )
    {
      CardCacheFile = 24;
LABEL_34:
      if ( pbData )
        CspFreeH(pbData);
      goto LABEL_36;
    }
    if ( *((_DWORD *)a1 + 3) == 1 )
    {
      v9 = 1;
      if ( (*((_BYTE *)a1 + 8) & 1) != 0 )
      {
        v6 = 0;
        v9 = v10.pbData[1] == *((_BYTE *)a1 + 541);
      }
      if ( (*((_BYTE *)a1 + 8) & 2) != 0 )
      {
        v6 = 0;
        if ( *((_WORD *)v10.pbData + 1) != *((_WORD *)a1 + 271) )
          v9 = 0;
      }
      if ( (*((_BYTE *)a1 + 8) & 4) != 0 && *((_WORD *)v10.pbData + 2) != *((_WORD *)a1 + 272) || !v9 )
      {
        *((_DWORD *)a1 + 140) = 1;
        CardCacheFile = MyCacheDeleteItem(a1);
        if ( !CardCacheFile )
          CardCacheFile = 1168;
        goto LABEL_34;
      }
    }
    *((_QWORD *)a1 + 69) = v10.pbData;
  }
LABEL_36:
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardCacheFile);
  }
  return CardCacheFile;
}

```

## disassembly

```asm
0x180021bc8  push    rbx
0x180021bca  push    rbp
0x180021bcb  push    rsi
0x180021bcc  push    rdi
0x180021bcd  push    r15
0x180021bcf  sub     rsp, 40h
0x180021bd3  xor     edx, edx
0x180021bd5  mov     rbx, rcx
0x180021bd8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021be4  lea     r15, WPP_GLOBAL_Control
0x180021beb  cmp     rcx, r15
0x180021bee  jz      short loc_180021C18
0x180021bf0  test    byte ptr [rcx+1Ch], 2
0x180021bf4  jz      short loc_180021C18
0x180021bf6  cmp     byte ptr [rcx+19h], 5
0x180021bfa  jb      short loc_180021C18
0x180021bfc  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021c03  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021c0a  mov     rcx, [rcx+10h]
0x180021c0e  mov     edx, 10h
0x180021c13  call    WPP_SF_s
0x180021c18  mov     rcx, [rbx]; struct _CARD_STATE *
0x180021c1b  mov     ebp, 1
0x180021c20  mov     rax, [rcx+8]
0x180021c24  test    rax, rax
0x180021c27  jnz     short loc_180021C7C
0x180021c29  lea     edx, [rax+2]
0x180021c2c  lea     edi, [rax+57h]
0x180021c2f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021c34  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c3b  cmp     rcx, r15
0x180021c3e  jz      loc_180021D87
0x180021c44  test    [rcx+1Ch], bpl
0x180021c48  jz      loc_180021D87
0x180021c4e  cmp     byte ptr [rcx+19h], 2
0x180021c52  jb      loc_180021D87
0x180021c58  mov     rcx, [rcx+10h]
0x180021c5c  lea     rax, aPinfoPcardstat; "pInfo->pCardState->pCardData"
0x180021c63  lea     edx, [rbp+10h]
0x180021c66  mov     [rsp+68h+var_48], rax
0x180021c6b  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021c72  call    WPP_SF_ss
0x180021c77  jmp     loc_180021D87
0x180021c7c  cmp     dword ptr [rax], 6
0x180021c7f  jb      short loc_180021C99
0x180021c81  cmp     dword ptr [rcx+2B8h], 3
0x180021c88  jnz     short loc_180021C99
0x180021c8a  cmp     [rbx+8], ebp
0x180021c8d  jz      short loc_180021C99
0x180021c8f  mov     eax, 490h
0x180021c94  jmp     loc_180021DC8
0x180021c99  cmp     [rbx+0Ch], ebp
0x180021c9c  jnz     short loc_180021CC3
0x180021c9e  cmp     dword ptr [rbx+224h], 0
0x180021ca5  jnz     short loc_180021CC3
0x180021ca7  lea     rdx, [rbx+21Ch]; struct _CARD_CACHE_FILE_FORMAT *
0x180021cae  call    ?I_CspReadCardCacheFile@@YAKPEAU_CARD_STATE@@PEAU_CARD_CACHE_FILE_FORMAT@@@Z; I_CspReadCardCacheFile(_CARD_STATE *,_CARD_CACHE_FILE_FORMAT *)
0x180021cb3  mov     edi, eax
0x180021cb5  test    eax, eax
0x180021cb7  jnz     loc_180021D87
0x180021cbd  mov     [rbx+224h], ebp
0x180021cc3  xorps   xmm0, xmm0
0x180021cc6  mov     qword ptr [rbx+228h], 0
0x180021cd1  lea     rdx, [rsp+68h+var_38]; struct _CRYPTOAPI_BLOB *
0x180021cd6  mov     rcx, rbx; struct _CARD_CACHE_QUERY_INFO *
0x180021cd9  movups  xmmword ptr [rsp+68h+var_38.cbData], xmm0
0x180021cde  call    ?MyCacheLookupItem@@YAKPEAU_CARD_CACHE_QUERY_INFO@@PEAU_CRYPTOAPI_BLOB@@@Z; MyCacheLookupItem(_CARD_CACHE_QUERY_INFO *,_CRYPTOAPI_BLOB *)
0x180021ce3  mov     edi, eax
0x180021ce5  test    eax, eax
0x180021ce7  jnz     loc_180021D87
0x180021ced  cmp     [rsp+68h+var_38.cbData], 10h
0x180021cf2  mov     rsi, [rsp+68h+var_38.pbData]
0x180021cf7  jb      short loc_180021D75
0x180021cf9  mov     ecx, [rsi+0Ch]
0x180021cfc  mov     eax, [rsp+68h+var_38.cbData]
0x180021d00  add     rcx, 10h
0x180021d04  cmp     rcx, rax
0x180021d07  ja      short loc_180021D75
0x180021d09  cmp     [rbx+0Ch], ebp
0x180021d0c  jnz     short loc_180021D6C
0x180021d0e  mov     edx, ebp
0x180021d10  test    [rbx+8], bpl
0x180021d14  jz      short loc_180021D24
0x180021d16  mov     al, [rbx+21Dh]
0x180021d1c  xor     ecx, ecx
0x180021d1e  cmp     [rsi+1], al
0x180021d21  cmovnz  edx, ecx
0x180021d24  test    byte ptr [rbx+8], 2
0x180021d28  jz      short loc_180021D3A
0x180021d2a  movzx   eax, word ptr [rbx+21Eh]
0x180021d31  xor     ecx, ecx
0x180021d33  cmp     [rsi+2], ax
0x180021d37  cmovnz  edx, ecx
0x180021d3a  test    byte ptr [rbx+8], 4
0x180021d3e  jz      short loc_180021D4D
0x180021d40  movzx   eax, word ptr [rbx+220h]
0x180021d47  cmp     [rsi+4], ax
0x180021d4b  jnz     short loc_180021D51
0x180021d4d  test    edx, edx
0x180021d4f  jnz     short loc_180021D6C
0x180021d51  mov     rcx, rbx
0x180021d54  mov     [rbx+230h], ebp
0x180021d5a  call    MyCacheDeleteItem
0x180021d5f  mov     edi, eax
0x180021d61  test    eax, eax
0x180021d63  jnz     short loc_180021D7A
0x180021d65  mov     edi, 490h
0x180021d6a  jmp     short loc_180021D7A
0x180021d6c  mov     [rbx+228h], rsi
0x180021d73  jmp     short loc_180021D87
0x180021d75  mov     edi, 18h
0x180021d7a  test    rsi, rsi
0x180021d7d  jz      short loc_180021D87
0x180021d7f  mov     rcx, rsi
0x180021d82  call    CspFreeH
0x180021d87  mov     edx, ebp
0x180021d89  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d95  cmp     rcx, r15
0x180021d98  jz      short loc_180021DC6
0x180021d9a  test    byte ptr [rcx+1Ch], 2
0x180021d9e  jz      short loc_180021DC6
0x180021da0  cmp     byte ptr [rcx+19h], 5
0x180021da4  jb      short loc_180021DC6
0x180021da6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021dad  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180021db4  mov     rcx, [rcx+10h]
0x180021db8  mov     edx, 12h
0x180021dbd  mov     dword ptr [rsp+68h+var_48], edi
0x180021dc1  call    WPP_SF_sD
0x180021dc6  mov     eax, edi
0x180021dc8  add     rsp, 40h
0x180021dcc  pop     r15
0x180021dce  pop     rdi
0x180021dcf  pop     rsi
0x180021dd0  pop     rbp
0x180021dd1  pop     rbx
0x180021dd2  retn
```
