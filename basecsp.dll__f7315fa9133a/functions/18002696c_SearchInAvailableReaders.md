# SearchInAvailableReaders

- ea: `0x18002696c`
- end: `0x180026fd5`
- name: `SearchInAvailableReaders`
- size: `1641`
- prototype: `__int64 __fastcall(__int64, struct _CARD_STATE **, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180026728`

## callees

- `0x18000a772`
- `0x18000c67c`
- `0x18000ccb0`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x18001d470`
- `0x18001de28`
- `0x180025880`
- `0x180026064`
- `0x18002696c`
- `0x18002bf84`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180026afa`
- `msvcrt!wcsnlen` at `0x180026c48`
- `msvcrt!wcsnlen` at `0x180026afa`
- `msvcrt!wcsnlen` at `0x180026c48`
- `WinSCard!SCardEstablishContext` at `0x180026a21`
- `WinSCard!SCardEstablishContext` at `0x180026a21`
- `WinSCard!SCardListCardsW` at `0x180026d52`
- `WinSCard!SCardListCardsW` at `0x180026d52`
- `WinSCard!SCardGetStatusChangeW` at `0x180026c65`
- `WinSCard!SCardGetStatusChangeW` at `0x180026c65`
- `WinSCard!SCardReleaseContext` at `0x180026f5c`
- `WinSCard!SCardReleaseContext` at `0x180026f5c`
- `WinSCard!SCardFreeMemory` at `0x180026f1e`
- `WinSCard!SCardFreeMemory` at `0x180026f4d`
- `WinSCard!SCardFreeMemory` at `0x180026f1e`
- `WinSCard!SCardFreeMemory` at `0x180026f4d`
- `WinSCard!SCardListReadersW` at `0x180026a92`
- `WinSCard!SCardListReadersW` at `0x180026a92`

## pseudocode

```c
__int64 __fastcall SearchInAvailableReaders(__int64 a1, struct _CARD_STATE **a2, int a3)
{
  DWORD v3; // r14d
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v4; // r13
  char *v5; // r15
  struct _CARD_STATE *v6; // rdi
  __int64 v8; // rcx
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  int v11; // edx
  __int64 v12; // rcx
  DWORD v13; // edx
  DWORD v14; // ebx
  const wchar_t *v15; // rcx
  int v16; // eax
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  char *v21; // rax
  __int64 v22; // rcx
  DWORD v23; // ebx
  unsigned int i; // esi
  const WCHAR *v25; // rdx
  unsigned __int64 v26; // rax
  const wchar_t *v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  int v30; // r8d
  unsigned int v31; // esi
  DWORD j; // edx
  int v33; // eax
  unsigned int v34; // r15d
  unsigned __int64 v35; // r14
  WCHAR *mszCards; // r12
  unsigned int v37; // eax
  int v38; // ecx
  unsigned int v39; // eax
  DWORD k; // edi
  const void *v41; // rdx
  SCARDCONTEXT v42; // rcx
  DWORD v44; // [rsp+38h] [rbp-39h]
  struct _CARD_STATE *v45; // [rsp+40h] [rbp-31h] BYREF
  char *v46; // [rsp+48h] [rbp-29h]
  SCARDCONTEXT phContext; // [rsp+50h] [rbp-21h] BYREF
  DWORD pcchCards; // [rsp+58h] [rbp-19h] BYREF
  unsigned int v49; // [rsp+5Ch] [rbp-15h]
  WCHAR mszReaders[4]; // [rsp+60h] [rbp-11h] BYREF
  void **v51; // [rsp+68h] [rbp-9h] BYREF
  __int64 v52; // [rsp+70h] [rbp-1h]
  int v53; // [rsp+78h] [rbp+7h]
  DWORD pcchReaders; // [rsp+F0h] [rbp+7Fh] BYREF

  pcchReaders = -1;
  phContext = 0;
  *(_QWORD *)mszReaders = 0;
  v3 = 0;
  pcchCards = 0;
  v4 = 0;
  v45 = 0;
  v5 = 0;
  v51 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v6 = 0;
  v52 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  *(_DWORD *)(a1 + 1196) = 0;
  v9 = SCardEstablishContext(0, 0, 0, &phContext);
  if ( v9 )
  {
    WppTraceIndent(v8, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v11 = 114;
    goto LABEL_10;
  }
  v9 = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
  if ( v9 )
  {
    WppTraceIndent(v12, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v11 = 115;
    goto LABEL_10;
  }
  v13 = pcchReaders;
  v14 = 0;
  if ( !pcchReaders )
    goto LABEL_87;
  do
  {
    v15 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * v14);
    if ( !*v15 )
      break;
    ++v3;
    v16 = wcsnlen(v15, v13 - v14);
    v13 = pcchReaders;
    v14 += v16 + 1;
  }
  while ( v14 < pcchReaders );
  v44 = v3;
  if ( v14 >= v13 )
  {
LABEL_87:
    v9 = -2146435041;
    goto LABEL_88;
  }
  if ( !v3 )
  {
    v9 = -2146435026;
    goto LABEL_88;
  }
  v17 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)MIDL_user_allocate((unsigned __int64)v3 << 6);
  v4 = v17;
  if ( !v17 )
  {
    WppTraceIndent(v18, 2);
    v9 = 8;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v20 = 116;
    goto LABEL_27;
  }
  memset_0(v17, 0, (unsigned __int64)v3 << 6);
  v21 = (char *)MIDL_user_allocate(8LL * v3);
  v46 = v21;
  v5 = v21;
  if ( !v21 )
  {
    WppTraceIndent(v22, 2);
    v9 = 8;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v20 = 117;
LABEL_27:
    WPP_SF_s(v19[2], v20, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
    goto LABEL_88;
  }
  memset_0(v21, 0, 8LL * v3);
  v23 = 0;
  for ( i = 0; v23 < pcchReaders; v23 += v28 + 1 )
  {
    v25 = (const WCHAR *)(*(_QWORD *)mszReaders + 2LL * v23);
    if ( !*v25 )
      break;
    v26 = (unsigned __int64)i << 6;
    *(LPCWSTR *)((char *)&v4->szReader + v26) = v25;
    *(DWORD *)((char *)&v4->dwCurrentState + v26) = 0;
    v27 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * v23);
    v28 = v27 ? wcsnlen(v27, pcchReaders - v23) : 0;
    ++i;
  }
  v9 = SCardGetStatusChangeW(phContext, 0, v4, v3);
  if ( v9 )
  {
    WppTraceIndent(v29, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_88;
    }
    v11 = 118;
LABEL_10:
    WPP_SF_sD(v10[2], v11, (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, (_DWORD)WPP_pszIndent, v9);
    goto LABEL_88;
  }
  v49 = 0;
  v30 = 0;
  v31 = 0;
  for ( j = 0; j < v3; ++j )
  {
    v33 = v30 + 1;
    if ( (v4[(unsigned __int64)j].dwEventState & 0xA0) != 0x20 )
      v33 = v30;
    v30 = v33;
  }
  v53 = v33;
  v34 = 0;
  while ( 1 )
  {
    v35 = (unsigned __int64)v34 << 6;
    if ( (*(DWORD *)((_BYTE *)&v4->dwEventState + v35) & 0xA0) != 0x20 )
      goto LABEL_61;
    if ( !(unsigned int)MatchesRequiredReaderName(
                          *(unsigned __int16 **)(a1 + 1160),
                          *(unsigned __int16 **)((char *)&v4->szReader + v35)) )
      goto LABEL_61;
    pcchCards = -1;
    mszCards = (WCHAR *)&v46[8 * v34];
    v9 = SCardListCardsW(phContext, &v4->rgbAtr[v35], 0, 0, mszCards, &pcchCards);
    if ( v9 )
      goto LABEL_61;
    if ( v6 )
    {
      if ( *((_DWORD *)v6 + 148) )
        CspEndTransaction(v6);
      v52 = 0;
      CspLeaveCriticalSection((char *)v6 + 624);
      CardStateReleaseRef(v6, 0);
      v45 = 0;
    }
    v37 = VerifyCard(
            *(unsigned __int16 **)((char *)&v4->szReader + v35),
            *(unsigned __int16 **)mszCards,
            (struct _CARD_MATCH_DATA *)a1,
            &v45);
    v6 = v45;
    v9 = v37;
    if ( v37 )
    {
LABEL_61:
      v38 = a3;
      goto LABEL_62;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v51, (char *)v45 + 624);
    v38 = a3;
    ++v31;
    if ( !a3 )
      goto LABEL_64;
    if ( a3 == 1 )
      break;
LABEL_62:
    v3 = v44;
    if ( ++v34 >= v44 )
      goto LABEL_65;
  }
  if ( v31 <= 1 )
  {
    v49 = v34;
    goto LABEL_62;
  }
LABEL_64:
  v3 = v44;
LABEL_65:
  if ( !v53 )
  {
    v5 = v46;
    v9 = -2146435060;
LABEL_83:
    if ( v6 )
    {
      if ( *((_DWORD *)v6 + 148) )
        CspEndTransaction(v6);
      v52 = 0;
      CspLeaveCriticalSection((char *)v6 + 624);
      CardStateReleaseRef(v6, 0);
    }
    goto LABEL_88;
  }
  if ( v31 || v53 != 1 )
  {
    if ( v38 )
    {
      if ( v31 == 1 )
      {
        if ( v6 )
        {
          if ( *((_DWORD *)v6 + 148) )
            CspEndTransaction(v6);
          v52 = 0;
          CspLeaveCriticalSection((char *)v6 + 624);
          CardStateReleaseRef(v6, 0);
          v45 = 0;
        }
        v5 = v46;
        v39 = VerifyCard(
                (unsigned __int16 *)v4[(unsigned __int64)v49].szReader,
                *(unsigned __int16 **)&v46[8 * v49],
                (struct _CARD_MATCH_DATA *)a1,
                &v45);
        v6 = v45;
        v9 = v39;
        if ( !v39 )
        {
          Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v51, (char *)v45 + 624);
          goto LABEL_80;
        }
      }
      else
      {
        v5 = v46;
        v9 = -2146435024;
      }
    }
    else
    {
      v5 = v46;
      if ( v31 == 1 )
      {
        v9 = 0;
        goto LABEL_80;
      }
LABEL_69:
      v9 = -2146435024;
    }
    goto LABEL_83;
  }
  v5 = v46;
  if ( !v9 )
    goto LABEL_69;
LABEL_80:
  *a2 = v6;
LABEL_88:
  v52 = 0;
  if ( v5 )
  {
    for ( k = 0; k < v3; ++k )
    {
      v41 = *(const void **)&v5[8 * k];
      if ( v41 )
        SCardFreeMemory(phContext, v41);
    }
    CspFreeH(v5);
  }
  if ( v4 )
    CspFreeH(v4);
  if ( *(_QWORD *)mszReaders )
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
  v42 = phContext;
  if ( phContext )
    SCardReleaseContext(phContext);
  WppTraceIndent(v42, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v9);
  }
  v51 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v51);
  return v9;
}

```

## disassembly

```asm
0x18002696c  mov     rax, rsp
0x18002696f  mov     [rax+18h], r8d
0x180026973  mov     [rax+10h], rdx
0x180026977  mov     [rax+8], rcx
0x18002697b  push    rbp
0x18002697c  push    rbx
0x18002697d  push    rsi
0x18002697e  push    rdi
0x18002697f  push    r12
0x180026981  push    r13
0x180026983  push    r14
0x180026985  push    r15
0x180026987  lea     rbp, [rax-5Fh]
0x18002698b  sub     rsp, 88h
0x180026992  xor     r12d, r12d
0x180026995  mov     [rbp+57h+pcchReaders], 0FFFFFFFFh
0x18002699c  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800269a3  mov     [rbp+57h+phContext], r12
0x1800269a7  xor     edx, edx
0x1800269a9  mov     qword ptr [rbp+57h+mszReaders], r12
0x1800269ad  mov     r14d, r12d
0x1800269b0  mov     [rbp+57h+pcchCards], r12d
0x1800269b4  mov     r13d, r12d
0x1800269b7  mov     [rbp+57h+var_88], r12
0x1800269bb  mov     r15d, r12d
0x1800269be  mov     [rbp+57h+var_60], rax
0x1800269c2  mov     edi, r12d
0x1800269c5  mov     [rbp+57h+var_58], r12
0x1800269c9  mov     rbx, rcx
0x1800269cc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800269d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269d8  lea     rax, WPP_GLOBAL_Control
0x1800269df  lea     esi, [r12+2]
0x1800269e4  cmp     rcx, rax
0x1800269e7  jz      short loc_180026A0F
0x1800269e9  test    [rcx+1Ch], sil
0x1800269ed  jz      short loc_180026A0F
0x1800269ef  cmp     byte ptr [rcx+19h], 5
0x1800269f3  jb      short loc_180026A0F
0x1800269f5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800269fc  lea     edx, [rsi+6Fh]
0x1800269ff  mov     rcx, [rcx+10h]
0x180026a03  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180026a0a  call    WPP_SF_s
0x180026a0f  lea     r9, [rbp+57h+phContext]; phContext
0x180026a13  mov     [rbx+4ACh], r12d
0x180026a1a  xor     r8d, r8d; pvReserved2
0x180026a1d  xor     edx, edx; pvReserved1
0x180026a1f  xor     ecx, ecx; dwScope
0x180026a21  call    cs:__imp_SCardEstablishContext
0x180026a27  mov     ebx, eax
0x180026a29  test    eax, eax
0x180026a2b  jz      short loc_180026A84
0x180026a2d  mov     edx, esi
0x180026a2f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026a34  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a3b  lea     rax, WPP_GLOBAL_Control
0x180026a42  cmp     rcx, rax
0x180026a45  jz      loc_180026EFE
0x180026a4b  test    byte ptr [rcx+1Ch], 1
0x180026a4f  jz      loc_180026EFE
0x180026a55  cmp     [rcx+19h], sil
0x180026a59  jb      loc_180026EFE
0x180026a5f  mov     edx, 72h ; 'r'
0x180026a64  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180026a6b  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180026a72  mov     rcx, [rcx+10h]
0x180026a76  mov     dword ptr [rsp+0C0h+mszCards], ebx
0x180026a7a  call    WPP_SF_sD
0x180026a7f  jmp     loc_180026EFE
0x180026a84  mov     rcx, [rbp+57h+phContext]; hContext
0x180026a88  lea     r9, [rbp+57h+pcchReaders]; pcchReaders
0x180026a8c  lea     r8, [rbp+57h+mszReaders]; mszReaders
0x180026a90  xor     edx, edx; mszGroups
0x180026a92  call    cs:__imp_SCardListReadersW
0x180026a98  mov     ebx, eax
0x180026a9a  test    eax, eax
0x180026a9c  jz      short loc_180026AD7
0x180026a9e  mov     edx, esi
0x180026aa0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180026aac  lea     rax, WPP_GLOBAL_Control
0x180026ab3  cmp     rcx, rax
0x180026ab6  jz      loc_180026EFE
0x180026abc  test    byte ptr [rcx+1Ch], 1
0x180026ac0  jz      loc_180026EFE
0x180026ac6  cmp     [rcx+19h], sil
0x180026aca  jb      loc_180026EFE
0x180026ad0  mov     edx, 73h ; 's'
0x180026ad5  jmp     short loc_180026A64
0x180026ad7  mov     edx, [rbp+57h+pcchReaders]
0x180026ada  mov     ebx, r12d
0x180026add  test    edx, edx
0x180026adf  jz      loc_180026EF9
0x180026ae5  mov     rax, qword ptr [rbp+57h+mszReaders]
0x180026ae9  mov     ecx, ebx
0x180026aeb  lea     rcx, [rax+rcx*2]; Source
0x180026aef  cmp     r12w, [rcx]
0x180026af3  jz      short loc_180026B0B
0x180026af5  sub     edx, ebx; MaxCount
0x180026af7  inc     r14d
0x180026afa  call    cs:__imp_wcsnlen
0x180026b00  mov     edx, [rbp+57h+pcchReaders]
0x180026b03  inc     ebx
0x180026b05  add     ebx, eax
0x180026b07  cmp     ebx, edx
0x180026b09  jb      short loc_180026AE5
0x180026b0b  mov     [rbp+57h+var_90], r14d
0x180026b0f  cmp     ebx, edx
0x180026b11  jnb     loc_180026EF9
0x180026b17  test    r14d, r14d
0x180026b1a  jnz     short loc_180026B26
0x180026b1c  mov     ebx, 8010002Eh
0x180026b21  jmp     loc_180026EFE
0x180026b26  mov     ebx, r14d
0x180026b29  shl     rbx, 6
0x180026b2d  mov     rcx, rbx; size
0x180026b30  mov     esi, r14d
0x180026b33  call    MIDL_user_allocate
0x180026b38  mov     r13, rax
0x180026b3b  test    rax, rax
0x180026b3e  jnz     short loc_180026B97
0x180026b40  lea     esi, [rax+2]
0x180026b43  mov     edx, esi
0x180026b45  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026b4a  lea     ebx, [rsi+6]
0x180026b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b54  lea     rax, WPP_GLOBAL_Control
0x180026b5b  cmp     rcx, rax
0x180026b5e  jz      loc_180026EFE
0x180026b64  test    byte ptr [rcx+1Ch], 1
0x180026b68  jz      loc_180026EFE
0x180026b6e  cmp     [rcx+19h], sil
0x180026b72  jb      loc_180026EFE
0x180026b78  lea     edx, [rsi+72h]
0x180026b7b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180026b82  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180026b89  mov     rcx, [rcx+10h]
0x180026b8d  call    WPP_SF_s
0x180026b92  jmp     loc_180026EFE
0x180026b97  mov     r8, rbx; Size
0x180026b9a  xor     edx, edx; Val
0x180026b9c  mov     rcx, r13; void *
0x180026b9f  call    memset_0
0x180026ba4  shl     rsi, 3
0x180026ba8  mov     rcx, rsi; size
0x180026bab  call    MIDL_user_allocate
0x180026bb0  mov     [rbp+57h+var_80], rax
0x180026bb4  mov     r15, rax
0x180026bb7  test    rax, rax
0x180026bba  jnz     short loc_180026BF9
0x180026bbc  lea     esi, [rax+2]
0x180026bbf  mov     edx, esi
0x180026bc1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026bc6  lea     ebx, [rsi+6]
0x180026bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bd0  lea     rax, WPP_GLOBAL_Control
0x180026bd7  cmp     rcx, rax
0x180026bda  jz      loc_180026EFE
0x180026be0  test    byte ptr [rcx+1Ch], 1
0x180026be4  jz      loc_180026EFE
0x180026bea  cmp     [rcx+19h], sil
0x180026bee  jb      loc_180026EFE
0x180026bf4  lea     edx, [rsi+73h]
0x180026bf7  jmp     short loc_180026B7B
0x180026bf9  mov     r8, rsi; Size
0x180026bfc  xor     edx, edx; Val
0x180026bfe  mov     rcx, rax; void *
0x180026c01  call    memset_0
0x180026c06  mov     ebx, r12d
0x180026c09  mov     esi, r12d
0x180026c0c  cmp     [rbp+57h+pcchReaders], r12d
0x180026c10  jbe     short loc_180026C59
0x180026c12  mov     rax, qword ptr [rbp+57h+mszReaders]
0x180026c16  mov     ecx, ebx
0x180026c18  lea     rdx, [rax+rcx*2]
0x180026c1c  cmp     r12w, [rdx]
0x180026c20  jz      short loc_180026C59
0x180026c22  mov     eax, esi
0x180026c24  shl     rax, 6
0x180026c28  mov     [rax+r13], rdx
0x180026c2c  mov     [rax+r13+10h], r12d
0x180026c31  mov     rax, qword ptr [rbp+57h+mszReaders]
0x180026c35  lea     rcx, [rax+rcx*2]; Source
0x180026c39  test    rcx, rcx
0x180026c3c  jnz     short loc_180026C43
0x180026c3e  mov     rax, r12
0x180026c41  jmp     short loc_180026C4E
0x180026c43  mov     edx, [rbp+57h+pcchReaders]
0x180026c46  sub     edx, ebx; MaxCount
0x180026c48  call    cs:__imp_wcsnlen
0x180026c4e  inc     ebx
0x180026c50  inc     esi
0x180026c52  add     ebx, eax
0x180026c54  cmp     ebx, [rbp+57h+pcchReaders]
0x180026c57  jb      short loc_180026C12
0x180026c59  mov     rcx, [rbp+57h+phContext]; hContext
0x180026c5d  mov     r9d, r14d; cReaders
0x180026c60  mov     r8, r13; rgReaderStates
0x180026c63  xor     edx, edx; dwTimeout
0x180026c65  call    cs:__imp_SCardGetStatusChangeW
0x180026c6b  mov     ebx, eax
0x180026c6d  test    eax, eax
0x180026c6f  jz      short loc_180026CB0
0x180026c71  mov     esi, 2
0x180026c76  mov     edx, esi
0x180026c78  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180026c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c84  lea     rax, WPP_GLOBAL_Control
0x180026c8b  cmp     rcx, rax
0x180026c8e  jz      loc_180026EFE
0x180026c94  test    byte ptr [rcx+1Ch], 1
0x180026c98  jz      loc_180026EFE
0x180026c9e  cmp     [rcx+19h], sil
0x180026ca2  jb      loc_180026EFE
0x180026ca8  lea     edx, [rsi+74h]
0x180026cab  jmp     loc_180026A64
0x180026cb0  mov     [rbp+57h+var_6C], r12d
0x180026cb4  mov     r8d, r12d
0x180026cb7  mov     esi, r12d
0x180026cba  mov     edx, r12d
0x180026cbd  test    r14d, r14d
0x180026cc0  jz      loc_180026EC2
0x180026cc6  mov     eax, edx
0x180026cc8  shl     rax, 6
0x180026ccc  mov     ecx, [rax+r13+14h]
0x180026cd1  lea     eax, [r8+1]
0x180026cd5  and     cl, 0A0h
0x180026cd8  cmp     cl, 20h ; ' '
0x180026cdb  cmovnz  eax, r8d
0x180026cdf  inc     edx
0x180026ce1  mov     r8d, eax
0x180026ce4  cmp     edx, r14d
0x180026ce7  jb      short loc_180026CC6
0x180026ce9  mov     [rbp+57h+var_50], eax
0x180026cec  mov     r15d, r12d
0x180026cef  mov     r14d, r15d
0x180026cf2  shl     r14, 6
0x180026cf6  mov     r12d, r15d
0x180026cf9  mov     eax, [r14+r13+14h]
0x180026cfe  and     al, 0A0h
0x180026d00  cmp     al, 20h ; ' '
0x180026d02  jnz     loc_180026DDD
0x180026d08  mov     rax, [rbp+57h+arg_0]
0x180026d0c  mov     rdx, [r14+r13]; unsigned __int16 *
0x180026d10  mov     rcx, [rax+488h]; unsigned __int16 *
0x180026d17  call    ?MatchesRequiredReaderName@@YAHPEAG0@Z; MatchesRequiredReaderName(ushort *,ushort *)
0x180026d1c  test    eax, eax
0x180026d1e  jz      loc_180026DDD
0x180026d24  mov     rax, [rbp+57h+var_80]
0x180026d28  lea     rdx, [r13+1Ch]
0x180026d2c  mov     rcx, [rbp+57h+phContext]; hContext
0x180026d30  add     rdx, r14; pbAtr
0x180026d33  xor     r9d, r9d; cguidInterfaceCount
0x180026d36  mov     [rbp+57h+pcchCards], 0FFFFFFFFh
0x180026d3d  xor     r8d, r8d; rgquidInterfaces
0x180026d40  lea     r12, [rax+r12*8]
0x180026d44  lea     rax, [rbp+57h+pcchCards]
0x180026d48  mov     [rsp+28h], rax; pcchCards
0x180026d4d  mov     [rsp+0C0h+mszCards], r12; mszCards
0x180026d52  call    cs:__imp_SCardListCardsW
0x180026d58  mov     ebx, eax
0x180026d5a  test    eax, eax
0x180026d5c  jnz     short loc_180026DDD
0x180026d5e  xor     ebx, ebx
0x180026d60  test    rdi, rdi
0x180026d63  jz      short loc_180026D93
0x180026d65  cmp     [rdi+250h], ebx
0x180026d6b  jz      short loc_180026D75
0x180026d6d  mov     rcx, rdi; struct _CARD_STATE *
0x180026d70  call    CspEndTransaction
0x180026d75  lea     rcx, [rdi+270h]
0x180026d7c  mov     [rbp+57h+var_58], rbx
0x180026d80  call    CspLeaveCriticalSection
0x180026d85  xor     edx, edx
0x180026d87  mov     rcx, rdi
0x180026d8a  call    CardStateReleaseRef
0x180026d8f  mov     [rbp+57h+var_88], rbx
0x180026d93  mov     r8, [rbp+57h+arg_0]; struct _CARD_MATCH_DATA *
0x180026d97  lea     r9, [rbp+57h+var_88]; struct _CARD_STATE **
0x180026d9b  mov     rdx, [r12]; unsigned __int16 *
0x180026d9f  mov     rcx, [r14+r13]; unsigned __int16 *
0x180026da3  call    ?VerifyCard@@YAKPEAG0PEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@@Z; VerifyCard(ushort *,ushort *,_CARD_MATCH_DATA *,_CARD_STATE * *)
0x180026da8  mov     rdi, [rbp+57h+var_88]
0x180026dac  xor     r12d, r12d
0x180026daf  mov     ebx, eax
0x180026db1  test    eax, eax
0x180026db3  jnz     short loc_180026DE0
0x180026db5  lea     rdx, [rdi+270h]
0x180026dbc  lea     rcx, [rbp+57h+var_60]
0x180026dc0  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180026dc5  mov     ecx, [rbp+57h+arg_10]
0x180026dc8  inc     esi
0x180026dca  test    ecx, ecx
0x180026dcc  jz      short loc_180026DF5
0x180026dce  cmp     ecx, 1
0x180026dd1  jnz     short loc_180026DE3
0x180026dd3  cmp     esi, ecx
0x180026dd5  ja      short loc_180026DF5
0x180026dd7  mov     [rbp+57h+var_6C], r15d
  ... truncated ...
```
