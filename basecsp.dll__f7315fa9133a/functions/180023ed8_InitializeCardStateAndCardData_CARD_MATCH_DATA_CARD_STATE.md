# InitializeCardStateAndCardData(_CARD_MATCH_DATA *,_CARD_STATE * *)

- ea: `0x180023ed8`
- end: `0x1800247ca`
- name: `?InitializeCardStateAndCardData@@YAKPEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@@Z`
- size: `2290`
- prototype: `unsigned int __fastcall(struct _CARD_MATCH_DATA *, struct _CARD_STATE **)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x180023954`

## callees

- `0x18000a772`
- `0x18000c67c`
- `0x18000ccb0`
- `0x18000de80`
- `0x180016e0c`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x18001d470`
- `0x18001de28`
- `0x18001ed64`
- `0x18001f3a4`
- `0x180022304`
- `0x180022640`
- `0x180023504`
- `0x180023d3c`
- `0x180023ed8`
- `0x1800258d4`
- `0x180025a40`
- `0x18002614c`
- `0x18002bf00`
- `0x18002bf64`
- `0x18002bf84`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002422c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024245`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002422c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024254`
- `WinSCard!SCardEstablishContext` at `0x180023f93`
- `WinSCard!SCardEstablishContext` at `0x180023f93`
- `WinSCard!SCardReleaseContext` at `0x18002473e`
- `WinSCard!SCardReleaseContext` at `0x18002473e`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18002401f`
- `WinSCard!SCardGetCardTypeProviderNameW` at `0x18002401f`

## string_xrefs

- `0x180024461`: `Read Only Mode`
- `0x1800244f1`: `Cache Mode`

## pseudocode

```c
__int64 __fastcall InitializeCardStateAndCardData(WCHAR *a1, struct _CARD_STATE **a2)
{
  __int64 v4; // rcx
  unsigned int CardTypeProviderNameW; // ebx
  _QWORD *v6; // rcx
  int v7; // edx
  _OWORD *v8; // rsi
  __int64 v9; // rcx
  char *v10; // rax
  __int64 v11; // rcx
  char *v12; // rdi
  unsigned int v13; // r14d
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  int v16; // edx
  __int64 v17; // rcx
  HMODULE *v18; // r14
  __int64 v19; // rcx
  FARPROC ProcAddress; // rax
  FARPROC v21; // rax
  __int64 v22; // rbx
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  __int64 v25; // rcx
  int v26; // r9d
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  _DWORD *v30; // rcx
  __int64 v31; // rcx
  _DWORD *v32; // rcx
  __int64 v33; // rcx
  int v34; // ecx
  unsigned int CardContainerMap; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  SCARDCONTEXT v38; // rcx
  int v40; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v41; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchProvider; // [rsp+40h] [rbp-C0h] BYREF
  SCARDCONTEXT phContext; // [rsp+48h] [rbp-B8h] BYREF
  void **v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h]
  WCHAR szProvider[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcchProvider = 0;
  phContext = 0;
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v41 = 0;
  v40 = 0;
  v45 = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  CardTypeProviderNameW = SCardEstablishContext(0, 0, 0, &phContext);
  if ( CardTypeProviderNameW )
  {
    WppTraceIndent(v4, 2u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 82;
LABEL_10:
      WPP_SF_sD(
        v6[2],
        v7,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardTypeProviderNameW);
      goto LABEL_105;
    }
    goto LABEL_105;
  }
  v8 = a1 + 28;
  pcchProvider = 260;
  CardTypeProviderNameW = SCardGetCardTypeProviderNameW(phContext, a1 + 310, 0x80000001, szProvider, &pcchProvider);
  if ( !CardTypeProviderNameW )
  {
    v10 = (char *)MIDL_user_allocate(0x718u);
    v12 = v10;
    if ( !v10 )
    {
      WppTraceIndent(v11, 2u);
      CardTypeProviderNameW = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_103;
    }
    memset_0(v10, 0, 0x718u);
    *(_DWORD *)v12 = 1;
    v13 = CspInitializeCriticalSection(v12 + 624);
    if ( v13 )
    {
      DeleteCardState((struct _CARD_STATE *)v12, 0);
      CardTypeProviderNameW = v13;
      WppTraceIndent(v37, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          v13);
      }
      goto LABEL_98;
    }
    *((_DWORD *)v12 + 166) = 1;
    _InterlockedExchange((volatile __int32 *)v12 + 173, 1);
    CardTypeProviderNameW = CspEnterCriticalSection(v12 + 624);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v14, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 86;
      goto LABEL_92;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v44, v12 + 624);
    CardTypeProviderNameW = GetSessionID((unsigned int *)v12 + 179, (union _LARGE_INTEGER *)v12 + 90);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v17, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 87;
      goto LABEL_92;
    }
    StringCbCopyW((unsigned __int16 *)v12 + 16, 0x208u, a1 + 48);
    v18 = (HMODULE *)(v12 + 16);
    CardTypeProviderNameW = GetCardModuleHandle((LPCRITICAL_SECTION *)a1, szProvider, (HINSTANCE *)v12 + 2);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v19, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 88;
      goto LABEL_92;
    }
    ProcAddress = GetProcAddress(*v18, "CardAcquireContextInternal");
    *((_QWORD *)v12 + 3) = ProcAddress;
    if ( !ProcAddress )
    {
      v21 = GetProcAddress(*v18, "CardAcquireContext");
      *((_QWORD *)v12 + 3) = v21;
      if ( !v21 )
      {
        CardTypeProviderNameW = GetLastError();
        if ( CardTypeProviderNameW )
          goto LABEL_98;
LABEL_103:
        if ( v41 )
          CspFreeH(v41);
        goto LABEL_105;
      }
    }
    v22 = 8;
    v23 = v12 + 728;
    do
    {
      *v23 = *v8;
      v23[1] = v8[1];
      v23[2] = v8[2];
      v23[3] = v8[3];
      v23[4] = v8[4];
      v23[5] = v8[5];
      v23[6] = v8[6];
      v24 = v8[7];
      v8 += 8;
      v23[7] = v24;
      v23 += 8;
      --v22;
    }
    while ( v22 );
    *v23 = *v8;
    v23[1] = v8[1];
    v23[2] = v8[2];
    v23[3] = v8[3];
    CardTypeProviderNameW = AcquireCardContext(v12);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v25, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 89;
      goto LABEL_92;
    }
    if ( !*((_QWORD *)v12 + 1) )
    {
      CardTypeProviderNameW = 87;
      WppTraceIndent(v25, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          v26,
          (__int64)"pLocalCardState->pCardData");
      }
      goto LABEL_98;
    }
    CardTypeProviderNameW = InitializeCspCaching(v25, v12);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v27, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 91;
      goto LABEL_92;
    }
    CardTypeProviderNameW = ReadCardSerialNumber(
                              (struct _CARD_STATE *)v12,
                              (unsigned __int8 **)v12 + 69,
                              (unsigned int *)v12 + 140);
    if ( CardTypeProviderNameW )
    {
      WppTraceIndent(v28, 2u);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_98;
      }
      v16 = 92;
      goto LABEL_92;
    }
    if ( **((_DWORD **)v12 + 1) < 6u )
    {
      *((_QWORD *)v12 + 87) = 1;
      v34 = 1;
    }
    else
    {
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Read Only Mode",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v29, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 93;
        goto LABEL_92;
      }
      if ( v40 != 4 )
      {
LABEL_70:
        CardTypeProviderNameW = -2146893820;
LABEL_98:
        if ( *((_DWORD *)v12 + 148) )
          CspEndTransaction((struct _CARD_STATE *)v12);
        if ( v45 )
        {
          v45 = 0;
          CspLeaveCriticalSection(v12 + 624);
        }
        CardStateReleaseRef(v12, 0);
        goto LABEL_103;
      }
      v30 = v41;
      *((_DWORD *)v12 + 175) = *(unsigned __int8 *)v41;
      CspFreeH(v30);
      v41 = 0;
      v40 = 0;
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Cache Mode",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v31, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 94;
        goto LABEL_92;
      }
      if ( v40 != 4 )
        goto LABEL_70;
      v32 = v41;
      *((_DWORD *)v12 + 174) = *v41;
      CspFreeH(v32);
      v41 = 0;
      v40 = 0;
      CardTypeProviderNameW = GetCachedCardProperty(
                                (_DWORD)v12,
                                (unsigned int)L"Supports Windows x.509 Enrollment",
                                (unsigned int)&v41,
                                (unsigned int)&v40,
                                0);
      if ( CardTypeProviderNameW )
      {
        WppTraceIndent(v33, 2u);
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_98;
        }
        v16 = 95;
        goto LABEL_92;
      }
      if ( v40 != 4 )
        goto LABEL_70;
      v34 = *(unsigned __int8 *)v41;
    }
    *((_DWORD *)v12 + 177) = v34;
    CardContainerMap = ReadCardContainerMap((struct _CARD_STATE *)v12);
    CardTypeProviderNameW = 0;
    if ( CardContainerMap != -2146435036 )
      CardTypeProviderNameW = CardContainerMap;
    if ( !CardTypeProviderNameW )
    {
      *a2 = (struct _CARD_STATE *)v12;
      CardTypeProviderNameW = 0;
      goto LABEL_103;
    }
    WppTraceIndent(v36, 2u);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_98;
    }
    v16 = 96;
LABEL_92:
    WPP_SF_sD(
      v15[2],
      v16,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardTypeProviderNameW);
    goto LABEL_98;
  }
  WppTraceIndent(v9, 2u);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 83;
    goto LABEL_10;
  }
LABEL_105:
  v38 = phContext;
  if ( phContext )
    SCardReleaseContext(phContext);
  v45 = 0;
  WppTraceIndent(v38, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardTypeProviderNameW);
  }
  v44 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v44);
  return CardTypeProviderNameW;
}

```

## disassembly

```asm
0x180023ed8  mov     [rsp-8+arg_10], rbx
0x180023edd  push    rbp
0x180023ede  push    rsi
0x180023edf  push    rdi
0x180023ee0  push    r12
0x180023ee2  push    r13
0x180023ee4  push    r14
0x180023ee6  push    r15
0x180023ee8  lea     rbp, [rsp-180h]
0x180023ef0  sub     rsp, 280h
0x180023ef7  mov     rax, cs:__security_cookie
0x180023efe  xor     rax, rsp
0x180023f01  mov     [rbp+1B0h+var_40], rax
0x180023f08  mov     r12, rdx
0x180023f0b  mov     [rsp+2B0h+var_270], 0
0x180023f13  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180023f1a  mov     [rsp+2B0h+phContext], 0
0x180023f23  xor     edx, edx
0x180023f25  mov     [rsp+2B0h+var_260], rdi
0x180023f2a  mov     r13, rcx
0x180023f2d  mov     [rsp+2B0h+var_278], 0
0x180023f36  mov     [rsp+2B0h+var_280], 0
0x180023f3e  mov     [rsp+2B0h+var_258], 0
0x180023f47  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f53  lea     r14, WPP_GLOBAL_Control
0x180023f5a  cmp     rcx, r14
0x180023f5d  jz      short loc_180023F87
0x180023f5f  test    byte ptr [rcx+1Ch], 2
0x180023f63  jz      short loc_180023F87
0x180023f65  cmp     byte ptr [rcx+19h], 5
0x180023f69  jb      short loc_180023F87
0x180023f6b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023f72  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023f79  mov     rcx, [rcx+10h]
0x180023f7d  mov     edx, 51h ; 'Q'
0x180023f82  call    WPP_SF_s
0x180023f87  lea     r9, [rsp+2B0h+phContext]; phContext
0x180023f8c  xor     r8d, r8d; pvReserved2
0x180023f8f  xor     edx, edx; pvReserved1
0x180023f91  xor     ecx, ecx; dwScope
0x180023f93  call    cs:__imp_SCardEstablishContext
0x180023f99  mov     ebx, eax
0x180023f9b  test    eax, eax
0x180023f9d  jz      short loc_180023FF2
0x180023f9f  mov     edx, 2
0x180023fa4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fb0  cmp     rcx, r14
0x180023fb3  jz      loc_180024734
0x180023fb9  test    byte ptr [rcx+1Ch], 1
0x180023fbd  jz      loc_180024734
0x180023fc3  cmp     byte ptr [rcx+19h], 2
0x180023fc7  jb      loc_180024734
0x180023fcd  mov     edx, 52h ; 'R'
0x180023fd2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023fd9  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023fe0  mov     rcx, [rcx+10h]
0x180023fe4  mov     dword ptr [rsp+2B0h+pcchProvider], ebx
0x180023fe8  call    WPP_SF_sD
0x180023fed  jmp     loc_180024734
0x180023ff2  mov     rcx, [rsp+2B0h+phContext]; hContext
0x180023ff7  lea     rax, [rsp+2B0h+var_270]
0x180023ffc  lea     rsi, [r13+38h]
0x180024000  mov     [rsp+2B0h+var_270], 104h
0x180024008  lea     rdx, [rsi+234h]; szCardName
0x18002400f  mov     [rsp+2B0h+pcchProvider], rax; pcchProvider
0x180024014  lea     r9, [rsp+2B0h+szProvider]; szProvider
0x180024019  mov     r8d, 80000001h; dwProviderId
0x18002401f  call    cs:__imp_SCardGetCardTypeProviderNameW
0x180024025  mov     ebx, eax
0x180024027  test    eax, eax
0x180024029  jz      short loc_180024063
0x18002402b  mov     edx, 2
0x180024030  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024035  mov     rcx, cs:WPP_GLOBAL_Control
0x18002403c  cmp     rcx, r14
0x18002403f  jz      loc_180024734
0x180024045  test    byte ptr [rcx+1Ch], 1
0x180024049  jz      loc_180024734
0x18002404f  cmp     byte ptr [rcx+19h], 2
0x180024053  jb      loc_180024734
0x180024059  mov     edx, 53h ; 'S'
0x18002405e  jmp     loc_180023FD2
0x180024063  mov     ebx, 718h
0x180024068  mov     ecx, ebx; size
0x18002406a  call    MIDL_user_allocate
0x18002406f  mov     rdi, rax
0x180024072  test    rax, rax
0x180024075  jnz     short loc_1800240C5
0x180024077  lea     edx, [rax+2]
0x18002407a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002407f  lea     ebx, [rdi+8]
0x180024082  mov     rcx, cs:WPP_GLOBAL_Control
0x180024089  cmp     rcx, r14
0x18002408c  jz      loc_18002471E
0x180024092  test    byte ptr [rcx+1Ch], 1
0x180024096  jz      loc_18002471E
0x18002409c  cmp     byte ptr [rcx+19h], 2
0x1800240a0  jb      loc_18002471E
0x1800240a6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800240ad  lea     edx, [rdi+54h]
0x1800240b0  mov     rcx, [rcx+10h]
0x1800240b4  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800240bb  call    WPP_SF_s
0x1800240c0  jmp     loc_18002471E
0x1800240c5  mov     r8, rbx; Size
0x1800240c8  xor     edx, edx; Val
0x1800240ca  mov     rcx, rdi; void *
0x1800240cd  call    memset_0
0x1800240d2  lea     r15, [rdi+270h]
0x1800240d9  mov     dword ptr [rdi], 1
0x1800240df  mov     rcx, r15
0x1800240e2  call    CspInitializeCriticalSection
0x1800240e7  mov     r14d, eax
0x1800240ea  test    eax, eax
0x1800240ec  jnz     loc_180024688
0x1800240f2  lea     eax, [r14+1]
0x1800240f6  mov     dword ptr [rdi+298h], 1
0x180024100  xchg    eax, [rdi+2B4h]
0x180024106  mov     rcx, r15
0x180024109  call    CspEnterCriticalSection
0x18002410e  mov     ebx, eax
0x180024110  test    eax, eax
0x180024112  jz      short loc_180024152
0x180024114  lea     edx, [r14+2]
0x180024118  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002411d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024124  lea     r14, WPP_GLOBAL_Control
0x18002412b  cmp     rcx, r14
0x18002412e  jz      loc_1800246E6
0x180024134  test    byte ptr [rcx+1Ch], 1
0x180024138  jz      loc_1800246E6
0x18002413e  cmp     byte ptr [rcx+19h], 2
0x180024142  jb      loc_1800246E6
0x180024148  mov     edx, 56h ; 'V'
0x18002414d  jmp     loc_180024659
0x180024152  mov     rdx, r15
0x180024155  lea     rcx, [rsp+2B0h+var_260]
0x18002415a  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18002415f  lea     rdx, [rdi+2D0h]; union _LARGE_INTEGER *
0x180024166  lea     rcx, [rdi+2CCh]; TokenInformation
0x18002416d  call    ?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z; GetSessionID(ulong *,_LARGE_INTEGER *)
0x180024172  mov     ebx, eax
0x180024174  test    eax, eax
0x180024176  jz      short loc_1800241B7
0x180024178  mov     edx, 2
0x18002417d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024182  mov     rcx, cs:WPP_GLOBAL_Control
0x180024189  lea     r14, WPP_GLOBAL_Control
0x180024190  cmp     rcx, r14
0x180024193  jz      loc_1800246E6
0x180024199  test    byte ptr [rcx+1Ch], 1
0x18002419d  jz      loc_1800246E6
0x1800241a3  cmp     byte ptr [rcx+19h], 2
0x1800241a7  jb      loc_1800246E6
0x1800241ad  mov     edx, 57h ; 'W'
0x1800241b2  jmp     loc_180024659
0x1800241b7  lea     r8, [rsi+28h]; unsigned __int16 *
0x1800241bb  mov     edx, 208h; unsigned __int64
0x1800241c0  lea     rcx, [rdi+20h]; unsigned __int16 *
0x1800241c4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800241c9  lea     r14, [rdi+10h]
0x1800241cd  mov     rcx, r13; struct _CARD_MATCH_DATA *
0x1800241d0  mov     r8, r14; HINSTANCE *
0x1800241d3  lea     rdx, [rsp+2B0h+szProvider]; unsigned __int16 *
0x1800241d8  call    ?GetCardModuleHandle@@YAKPEAU_CARD_MATCH_DATA@@PEAGPEAPEAUHINSTANCE__@@@Z; GetCardModuleHandle(_CARD_MATCH_DATA *,ushort *,HINSTANCE__ * *)
0x1800241dd  mov     ebx, eax
0x1800241df  test    eax, eax
0x1800241e1  jz      short loc_180024222
0x1800241e3  mov     edx, 2
0x1800241e8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800241ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241f4  lea     r14, WPP_GLOBAL_Control
0x1800241fb  cmp     rcx, r14
0x1800241fe  jz      loc_1800246E6
0x180024204  test    byte ptr [rcx+1Ch], 1
0x180024208  jz      loc_1800246E6
0x18002420e  cmp     byte ptr [rcx+19h], 2
0x180024212  jb      loc_1800246E6
0x180024218  mov     edx, 58h ; 'X'
0x18002421d  jmp     loc_180024659
0x180024222  mov     rcx, [r14]; hModule
0x180024225  lea     rdx, aCardacquirecon_0; "CardAcquireContextInternal"
0x18002422c  call    cs:__imp_GetProcAddress
0x180024232  mov     [rdi+18h], rax
0x180024236  test    rax, rax
0x180024239  jnz     short loc_180024270
0x18002423b  mov     rcx, [r14]; hModule
0x18002423e  lea     rdx, aCardacquirecon; "CardAcquireContext"
0x180024245  call    cs:__imp_GetProcAddress
0x18002424b  mov     [rdi+18h], rax
0x18002424f  test    rax, rax
0x180024252  jnz     short loc_180024270
0x180024254  call    cs:__imp_GetLastError
0x18002425a  lea     r14, WPP_GLOBAL_Control
0x180024261  mov     ebx, eax
0x180024263  test    eax, eax
0x180024265  jz      loc_18002471E
0x18002426b  jmp     loc_1800246E6
0x180024270  mov     ebx, 8
0x180024275  lea     rax, [rdi+2D8h]
0x18002427c  lea     ecx, [rbx+78h]
0x18002427f  movups  xmm0, xmmword ptr [rsi]
0x180024282  movups  xmmword ptr [rax], xmm0
0x180024285  movups  xmm1, xmmword ptr [rsi+10h]
0x180024289  movups  xmmword ptr [rax+10h], xmm1
0x18002428d  movups  xmm0, xmmword ptr [rsi+20h]
0x180024291  movups  xmmword ptr [rax+20h], xmm0
0x180024295  movups  xmm1, xmmword ptr [rsi+30h]
0x180024299  movups  xmmword ptr [rax+30h], xmm1
0x18002429d  movups  xmm0, xmmword ptr [rsi+40h]
0x1800242a1  movups  xmmword ptr [rax+40h], xmm0
0x1800242a5  movups  xmm1, xmmword ptr [rsi+50h]
0x1800242a9  movups  xmmword ptr [rax+50h], xmm1
0x1800242ad  movups  xmm0, xmmword ptr [rsi+60h]
0x1800242b1  movups  xmmword ptr [rax+60h], xmm0
0x1800242b5  movups  xmm1, xmmword ptr [rsi+70h]
0x1800242b9  add     rsi, rcx
0x1800242bc  movups  xmmword ptr [rax+70h], xmm1
0x1800242c0  add     rax, rcx
0x1800242c3  sub     rbx, 1
0x1800242c7  jnz     short loc_18002427F
0x1800242c9  movups  xmm0, xmmword ptr [rsi]
0x1800242cc  mov     rcx, rdi
0x1800242cf  movups  xmmword ptr [rax], xmm0
0x1800242d2  movups  xmm1, xmmword ptr [rsi+10h]
0x1800242d6  movups  xmmword ptr [rax+10h], xmm1
0x1800242da  movups  xmm0, xmmword ptr [rsi+20h]
0x1800242de  movups  xmmword ptr [rax+20h], xmm0
0x1800242e2  movups  xmm1, xmmword ptr [rsi+30h]
0x1800242e6  movups  xmmword ptr [rax+30h], xmm1
0x1800242ea  call    AcquireCardContext
0x1800242ef  mov     ebx, eax
0x1800242f1  test    eax, eax
0x1800242f3  jz      short loc_180024334
0x1800242f5  mov     edx, 2
0x1800242fa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800242ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024306  lea     r14, WPP_GLOBAL_Control
0x18002430d  cmp     rcx, r14
0x180024310  jz      loc_1800246E6
0x180024316  test    byte ptr [rcx+1Ch], 1
0x18002431a  jz      loc_1800246E6
0x180024320  cmp     byte ptr [rcx+19h], 2
0x180024324  jb      loc_1800246E6
0x18002432a  mov     edx, 59h ; 'Y'
0x18002432f  jmp     loc_180024659
0x180024334  cmp     qword ptr [rdi+8], 0
0x180024339  jnz     short loc_180024397
0x18002433b  mov     ebx, 57h ; 'W'
0x180024340  lea     edx, [rbx-55h]
0x180024343  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024348  mov     rcx, cs:WPP_GLOBAL_Control
0x18002434f  lea     r14, WPP_GLOBAL_Control
0x180024356  cmp     rcx, r14
0x180024359  jz      loc_1800246E6
0x18002435f  test    byte ptr [rcx+1Ch], 1
0x180024363  jz      loc_1800246E6
0x180024369  cmp     byte ptr [rcx+19h], 2
0x18002436d  jb      loc_1800246E6
0x180024373  mov     rcx, [rcx+10h]
0x180024377  lea     rax, aPlocalcardstat; "pLocalCardState->pCardData"
0x18002437e  lea     edx, [rbx+3]
0x180024381  mov     [rsp+2B0h+pcchProvider], rax
0x180024386  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18002438d  call    WPP_SF_ss
0x180024392  jmp     loc_1800246E6
0x180024397  mov     rdx, rdi
0x18002439a  call    InitializeCspCaching
0x18002439f  mov     ebx, eax
0x1800243a1  test    eax, eax
0x1800243a3  jz      short loc_1800243E4
0x1800243a5  mov     edx, 2
0x1800243aa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800243af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243b6  lea     r14, WPP_GLOBAL_Control
0x1800243bd  cmp     rcx, r14
0x1800243c0  jz      loc_1800246E6
0x1800243c6  test    byte ptr [rcx+1Ch], 1
0x1800243ca  jz      loc_1800246E6
0x1800243d0  cmp     byte ptr [rcx+19h], 2
0x1800243d4  jb      loc_1800246E6
0x1800243da  mov     edx, 5Bh ; '['
0x1800243df  jmp     loc_180024659
0x1800243e4  lea     r8, [rdi+230h]; unsigned int *
0x1800243eb  mov     rcx, rdi; struct _CARD_STATE *
0x1800243ee  lea     rdx, [rdi+228h]; unsigned __int8 **
0x1800243f5  call    ?ReadCardSerialNumber@@YAKPEAU_CARD_STATE@@PEAPEAEPEAK@Z; ReadCardSerialNumber(_CARD_STATE *,uchar * *,ulong *)
0x1800243fa  mov     ebx, eax
0x1800243fc  test    eax, eax
0x1800243fe  jz      short loc_18002443F
0x180024400  mov     edx, 2
0x180024405  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002440a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024411  lea     r14, WPP_GLOBAL_Control
0x180024418  cmp     rcx, r14
0x18002441b  jz      loc_1800246E6
0x180024421  test    byte ptr [rcx+1Ch], 1
0x180024425  jz      loc_1800246E6
  ... truncated ...
```
