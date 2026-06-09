# ActivateRouteRequest

- ea: `0x180010520`
- end: `0x1800116a4`
- name: `ActivateRouteRequest`
- size: `4484`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18000c00c`
- `0x180010520`
- `0x180027c00`
- `0x18002ee78`
- `0x180032560`
- `0x180032c28`
- `0x18003f6bc`
- `0x1800454b4`
- `0x180046fe8`
- `0x180064ae4`
- `0x180065c34`
- `0x180093958`
- `0x180093b44`
- `0x1800e71e2`
- `0x1800e71ee`
- `0x1800e7206`
- `0x1800e7260`
- `0x1800e7320`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x18001148d`
- `msvcrt!mbstowcs_s` at `0x18001148d`
- `msvcrt!wcstombs_s` at `0x1800112dd`
- `msvcrt!wcstombs_s` at `0x1800112dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011014`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800114e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180011006`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180011006`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010c81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010ddc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010ddc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010a61`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180010a61`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010d3a`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010eb2`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010f0e`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010d3a`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010eb2`
- `FirewallAPI!NetworkIsolationCreateInterfaceContainer` at `0x180010f0e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010c91`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010c91`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010cde`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180010cde`
- `NduProv!__imp_NduOpenHandle` at `0x180011387`
- `NduProv!__imp_NduOpenHandle` at `0x180011387`
- `NduProv!__imp_NduRegisterVpnInnerInterface` at `0x1800113e1`
- `NduProv!__imp_NduRegisterVpnInnerInterface` at `0x1800113e1`

## pseudocode

```c
int __fastcall ActivateRouteRequest(__int64 a1, __int64 a2, wchar_t *a3)
{
  wchar_t *v3; // r14
  __int64 v4; // rdi
  struct _LIST_ENTRY *v5; // rbx
  struct _LIST_ENTRY **p_Flink; // rax
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // esi
  struct _LIST_ENTRY *v10; // r12
  int v11; // ecx
  unsigned int v12; // ebx
  unsigned int v13; // eax
  struct _LIST_ENTRY *Flink; // rax
  bool v15; // zf
  unsigned int v16; // r13d
  __int64 v17; // rcx
  __int128 v18; // xmm0
  __int64 v19; // rcx
  int v20; // esi
  int v21; // eax
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // r8
  struct _LIST_ENTRY *v24; // rax
  size_t v25; // rcx
  unsigned int v26; // edx
  int v27; // r8d
  __int64 v28; // rsi
  __int64 v29; // rbx
  HRESULT v30; // eax
  __int64 i; // rsi
  __int64 v32; // rax
  struct _LIST_ENTRY *v33; // rcx
  __int64 v34; // rdx
  struct _LIST_ENTRY **v35; // rdx
  int v36; // r8d
  struct _LIST_ENTRY *v37; // rcx
  int v38; // r15d
  int INetCfgLock; // eax
  struct _LIST_ENTRY *v40; // rcx
  struct _LIST_ENTRY *v41; // rcx
  unsigned __int16 v42; // ax
  __int64 v43; // rcx
  _QWORD *v44; // r15
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  struct _LIST_ENTRY *v48; // rcx
  struct _LIST_ENTRY *v49; // r9
  __int64 v50; // rdi
  unsigned int v51; // edi
  struct _LIST_ENTRY *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r9
  unsigned int v56; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-BCh] BYREF
  size_t PtNumOfCharConverted; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h]
  int v60; // [rsp+54h] [rbp-ACh]
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  struct _LIST_ENTRY *v62; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h]
  wchar_t *v64; // [rsp+70h] [rbp-90h]
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v66[16]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD lpsz[500]; // [rsp+A0h] [rbp-60h]
  __int64 OutBuffer; // [rsp+870h] [rbp+770h] BYREF
  wchar_t v69; // [rsp+878h] [rbp+778h]
  __int16 v70; // [rsp+87Ah] [rbp+77Ah]
  WCHAR WideCharStr[256]; // [rsp+87Ch] [rbp+77Ch] BYREF
  __int16 v72; // [rsp+A7Ch] [rbp+97Ch]
  wchar_t Src[4]; // [rsp+A7Eh] [rbp+97Eh] BYREF
  __int64 v74; // [rsp+A86h] [rbp+986h]
  unsigned int v75; // [rsp+C80h] [rbp+B80h]
  unsigned int v76; // [rsp+C84h] [rbp+B84h]
  unsigned int v77[6]; // [rsp+C88h] [rbp+B88h] BYREF
  unsigned __int64 v78; // [rsp+CA0h] [rbp+BA0h]
  __int128 v79; // [rsp+CA8h] [rbp+BA8h]
  int v80; // [rsp+CB8h] [rbp+BB8h]
  wchar_t pszDest[258]; // [rsp+CBCh] [rbp+BBCh] BYREF
  __int128 v82; // [rsp+EC0h] [rbp+DC0h]
  _BYTE Buf1[24]; // [rsp+1128h] [rbp+1028h] BYREF

  v3 = a3;
  v64 = a3;
  v4 = a1;
  v63 = a1;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 444, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  BytesReturned = 0;
  LODWORD(p_Flink) = (unsigned int)memset_0(&OutBuffer, 0, 0x8D0u);
  if ( !v4 )
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_(v5[1].Flink, 446, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    }
    goto LABEL_237;
  }
  if ( *(_DWORD *)(v4 + 24) == 2 )
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_q(v5[1].Flink, 445, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *(_QWORD *)v4);
    }
LABEL_237:
    *(_DWORD *)v3 = 615;
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return (int)p_Flink;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      LODWORD(p_Flink) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 447, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
      v52 = WPP_GLOBAL_Control;
    }
    if ( v52 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v52[1].Blink) & 0x2000) == 0
      || BYTE1(v52[1].Blink) < 6u )
    {
      return (int)p_Flink;
    }
    v53 = 448;
    v54 = 615;
LABEL_245:
    LODWORD(p_Flink) = WPP_SF_d(v52[1].Flink, v53, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v54);
    return (int)p_Flink;
  }
  if ( *(_DWORD *)(v4 + 28) != 2 )
  {
    *(_DWORD *)v3 = 606;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        LODWORD(p_Flink) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 449, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v7[1].Blink) & 0x2000) != 0
        && BYTE1(v7[1].Blink) >= 6u )
      {
        v8 = 450;
LABEL_16:
        LODWORD(p_Flink) = WPP_SF_(v7[1].Flink, v8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        return (int)p_Flink;
      }
    }
    return (int)p_Flink;
  }
  p_Flink = *(struct _LIST_ENTRY ***)(v4 + 1048);
  LastError = 612;
  if ( p_Flink )
    v10 = p_Flink[4];
  else
    v10 = *(struct _LIST_ENTRY **)(v4 + 240);
  v62 = v10;
  if ( !v10 )
    goto LABEL_225;
  v11 = *(_DWORD *)v3;
  while ( 1 )
  {
    p_Flink = &v10[1].Flink->Flink;
    if ( *(_DWORD *)p_Flink == v11 )
      break;
    v10 = v10->Flink;
    v62 = v10;
    if ( !v10 )
      goto LABEL_225;
  }
  OutBuffer = *(_QWORD *)(v4 + 256);
  v12 = 0;
  v69 = *v3;
  v13 = *((_DWORD *)v3 + 136);
  if ( v13 > 0x4B8 )
    v13 = 1208;
  v76 = v13;
  memcpy_0(v77, v3 + 274, v13);
  LODWORD(v10[1].Flink[18].Flink) = *(_QWORD *)(v4 + 1064) != 0;
  Flink = v10[1].Flink;
  if ( LODWORD(Flink->Flink) != 2048 )
  {
    v15 = LODWORD(Flink->Flink) == 34525;
    v16 = 0;
    v57 = 0;
    if ( !v15 )
    {
LABEL_74:
      v23 = *(_QWORD *)(v4 + 1064);
      if ( !v23 )
        goto LABEL_111;
      v70 = 2 * MultiByteToWideChar(0xFDE9u, 0, (LPCCH)(v23 + 445), -1, WideCharStr, 256);
      v24 = v10[1].Flink;
      if ( LODWORD(v24->Flink) == 2048 || LODWORD(v24->Flink) == 34525 )
      {
        memset_0(pszDest, 0, 0x101u);
        StringCchCopyExW(pszDest, 0x101u, WideCharStr, 0, 0, 0xC00u);
      }
      v25 = 0;
      v26 = 0;
      PtNumOfCharConverted = 0;
      v56 = 0;
      if ( *((_DWORD *)v3 + 138) != 1 )
      {
        LODWORD(p_Flink) = RasPerAppTrafficRuleBlobToList(
                             (unsigned int)*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL)
                           + *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 100LL),
                             *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 56LL),
                             *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 1064) + 912LL) + 52LL),
                             (unsigned int)&PtNumOfCharConverted,
                             (__int64)&v56);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            LODWORD(p_Flink) = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 457,
                                 WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                 (unsigned int)p_Flink);
          }
          *(_DWORD *)v3 = v12;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v8 = 458;
            goto LABEL_16;
          }
          return (int)p_Flink;
        }
        v25 = PtNumOfCharConverted;
        v26 = v56;
      }
      *(_DWORD *)(v4 + 1376) = 0;
      v27 = *((_DWORD *)v3 + 138);
      if ( v27 == 2 && (!v26 || !v25) )
      {
        if ( (unsigned int)LockDownPolicyExists() )
        {
          v59 = 1;
          pguid = 0;
          PtNumOfCharConverted = 0x100000000LL;
          v60 = -1;
          v28 = 0;
          v29 = 0;
          do
          {
            memset_0(&v66[v29 * 4], 0, 0x1F8u);
            LOWORD(lpsz[v29 + 69]) |= 1u;
            *(_WORD *)&v66[v29 * 4 + 8] = 545;
            *(_QWORD *)&lpsz[v29 + 2] = L"LockDownIsolationVPN";
            *(_QWORD *)&lpsz[v29 + 30] = &PtNumOfCharConverted;
            LOWORD(lpsz[v29 + 8]) = 256;
            *(_QWORD *)&lpsz[v29 + 4] = L"An interface container to allow traffic to flow over the VPN when a lockdown pro"
                                         "file is connected";
            lpsz[v29 + 28] = 2;
            lpsz[v29 + 58] = 0;
            *(_QWORD *)&lpsz[v29 + 60] = 0;
            lpsz[v29 + 6] = 0x7FFFFFFF;
            lpsz[v29 + 68] = 3;
            lpsz[v29 + 80] = 0x10000;
            *(_QWORD *)&lpsz[v29] = LocalAlloc(0x40u, 0x4Eu);
            v30 = CoCreateGuid(&pguid);
            if ( v30 < 0
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                463,
                WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned int)v30);
            }
            StringFromGUID2(&pguid, *(LPOLESTR *)&lpsz[v29], 39);
            ++v28;
            v29 += 126;
          }
          while ( v28 != 2 );
          lpsz[7] = 1;
          v4 = v63;
          lpsz[133] = 2;
          LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(
                               *(_QWORD *)(v63 + 1064) + 144LL,
                               L"LockDownIsolationVPN",
                               L"An interface container to allow traffic to flow over the VPN when a lockdown profile is connected",
                               0,
                               3,
                               2,
                               v66);
          v3 = v64;
          v12 = (unsigned int)p_Flink;
          v10 = v62;
          v16 = v57;
          if ( (_DWORD)p_Flink )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(
                                   WPP_GLOBAL_Control[1].Flink,
                                   465,
                                   WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                   (unsigned int)p_Flink);
            }
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 466;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
          *(_DWORD *)(v4 + 1376) = 1;
          for ( i = 0; i != 2; ++i )
            LocalFree(*(HLOCAL *)&lpsz[126 * i]);
        }
LABEL_111:
        if ( *(_DWORD *)(v4 + 1376) )
        {
          LODWORD(p_Flink) = RefCountNetworkIsolationContainers(1);
          v12 = (unsigned int)p_Flink;
          if ( (_DWORD)p_Flink )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(
                                   WPP_GLOBAL_Control[1].Flink,
                                   467,
                                   WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                   (unsigned int)p_Flink);
            }
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 468;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
        }
        if ( DeviceIoControl(RasHubHandle, 0x12000Cu, &OutBuffer, 0x8D0u, &OutBuffer, 0x8D0u, &BytesReturned, 0) )
        {
          LastError = 0;
        }
        else
        {
          LastError = GetLastError();
          v37 = WPP_GLOBAL_Control;
          p_Flink = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 469, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
            v37 = WPP_GLOBAL_Control;
            p_Flink = &WPP_GLOBAL_Control;
          }
          if ( LastError )
          {
            if ( v37 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v37[1].Blink) & 0x2000) != 0
              && BYTE1(v37[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_sd(
                                   v37[1].Flink,
                                   475,
                                   (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                   (int)v4 + 8,
                                   LastError);
            }
LABEL_225:
            *(_DWORD *)v3 = LastError;
            v52 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
            {
              return (int)p_Flink;
            }
            v53 = 484;
            v54 = LastError;
            goto LABEL_245;
          }
        }
        if ( v16 == 2 && !*(_QWORD *)(v4 + 1064) )
        {
          PtNumOfCharConverted = 0;
          *(_QWORD *)&pguid.Data1 = 0;
          v57 = 0;
          v38 = 1;
          INetCfgLock = GetINetCfgLock(&PtNumOfCharConverted, &pguid, 0, &v57);
          if ( INetCfgLock >= 0 )
          {
            v40 = WPP_GLOBAL_Control;
          }
          else
          {
            v40 = WPP_GLOBAL_Control;
            v35 = &WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                471,
                WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                (unsigned __int16)INetCfgLock);
              v40 = WPP_GLOBAL_Control;
            }
            v38 = 0;
          }
          if ( v40 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v40[1].Blink) & 0x2000) != 0
            && BYTE1(v40[1].Blink) >= 4u )
          {
            WPP_SF_d(v40[1].Flink, 472, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, *(unsigned int *)(v4 + 32));
            v40 = WPP_GLOBAL_Control;
          }
          if ( v38 )
          {
            if ( PtNumOfCharConverted )
            {
              LODWORD(v35) = pguid.Data1;
              if ( *(_QWORD *)&pguid.Data1 )
              {
                ReleaseINetCfgLock(PtNumOfCharConverted, *(_QWORD *)&pguid.Data1, v57);
                v40 = WPP_GLOBAL_Control;
              }
            }
          }
          if ( v12
            && v40 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v40[1].Blink) & 0x2000) != 0
            && BYTE1(v40[1].Blink) >= 2u )
          {
            WPP_SF_sd(v40[1].Flink, 473, (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v4 + 8, v12);
          }
          *(_OWORD *)(v4 + 1344) = v82;
        }
        LODWORD(v10[1].Flink[18].Flink) = 1;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_sqqdD(WPP_GLOBAL_Control[1].Flink, (_DWORD)v35, v36, v4 + 8, v4, OutBuffer, v69, 0);
        }
        v41 = v10[1].Flink;
        PtNumOfCharConverted = 0;
        if ( LODWORD(v41->Flink) == 2048 || LODWORD(v41->Flink) == 34525 )
        {
          memset_0((char *)&v41->Flink + 4, 0, 0x80u);
          v42 = 510;
          if ( (unsigned __int16)v72 <= 0x1FEu )
            v42 = v72;
          else
            v72 = 510;
          *(wchar_t *)((char *)Src + v42) = 0;
          wcstombs_s(&PtNumOfCharConverted, (char *)&v10[1].Flink->Flink + 4, 0x80u, Src, 0x100u);
          v43 = *(_QWORD *)(v4 + 1064);
          if ( v43 )
          {
            *(_DWORD *)(v43 + 852) = v75;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 476, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v75);
            }
          }
          if ( v16 == 2 )
          {
            *((_DWORD *)v3 + 131) = (v78 >> 24) & 0xFFFFFF;
            goto LABEL_211;
          }
          if ( v16 > 1 || *(_WORD *)(*(_QWORD *)(v4 + 1232) + 96LL) != 14 )
            goto LABEL_211;
          v44 = (_QWORD *)(v4 + 1368);
          if ( *(_QWORD *)(v4 + 1368) == -1 )
          {
            v12 = NduOpenHandle(v4 + 1368);
            if ( v12
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 477, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v12);
            }
            if ( *v44 == -1 )
              goto LABEL_211;
          }
          v45 = NduRegisterVpnInnerInterface(*v44, v78);
          v12 = v45;
          if ( !v45 )
            goto LABEL_206;
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_207:
              if ( v48 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v48[1].Blink) & 0x2000) != 0
                && BYTE1(v48[1].Blink) >= 4u )
              {
                WPP_SF_iD(v48[1].Flink, v46, v47, v78, v12);
              }
              goto LABEL_211;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 478, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v45);
LABEL_206:
            v48 = WPP_GLOBAL_Control;
            goto LABEL_207;
          }
        }
LABEL_211:
        v49 = v10[1].Flink;
        LODWORD(v10->Blink) = 1;
        LODWORD(p_Flink) = mbstowcs_s(&PtNumOfCharConverted, v3 + 133, 0x80u, (const char *)&v49->Flink + 4, 0x80u);
        v50 = *(_QWORD *)(v4 + 1064);
        if ( v50 )
        {
          v51 = (*(_DWORD *)(v50 + 168) >> 1) & 1;
          if ( v10[1].Flink->Flink == (struct _LIST_ENTRY *)2048 && (v16 != 2 || !memcmp_0(Buf1, &GUID_NULL, 0x10u)) )
          {
            LeaveCriticalSection(&g_csSubmitRequest);
            v12 = DwBindServerToAdapter(v3 + 141, v51, v10[1].Flink->Flink);
            if ( v12
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 480, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v12);
            }
            EnterCriticalSection(&g_csSubmitRequest);
          }
          p_Flink = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            LODWORD(p_Flink) = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 481,
                                 WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                 v12);
          }
        }
        goto LABEL_225;
      }
      v32 = *(_QWORD *)(v4 + 1064);
      if ( v27 == 1 )
      {
        LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(v32 + 144, WideCharStr, WideCharStr, 0, 7, 0, 0);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_137;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_133:
            if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v33[1].Blink) & 0x2000) != 0
              && BYTE1(v33[1].Blink) >= 2u )
            {
              LODWORD(p_Flink) = WPP_SF_d(v33[1].Flink, 461, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v12);
            }
LABEL_137:
            *(_DWORD *)v3 = v12;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v8 = 462;
              goto LABEL_16;
            }
            return (int)p_Flink;
          }
          v34 = 459;
LABEL_132:
          LODWORD(p_Flink) = WPP_SF_d(
                               v33[1].Flink,
                               v34,
                               WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                               (unsigned int)p_Flink);
          v33 = WPP_GLOBAL_Control;
          goto LABEL_133;
        }
      }
      else
      {
        LODWORD(p_Flink) = NetworkIsolationCreateInterfaceContainer(v32 + 144, WideCharStr, WideCharStr, 0, 7, v26, v25);
        v12 = (unsigned int)p_Flink;
        if ( (_DWORD)p_Flink )
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_137;
          if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_133;
          v34 = 460;
          goto LABEL_132;
        }
      }
      *(_DWORD *)(v4 + 1376) = 1;
      goto LABEL_111;
    }
  }
  v16 = v77[0];
  v57 = v77[0];
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control[1].Flink,
      451,
      (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
      v4 + 8,
      v77[0]);
  }
  if ( v16 <= 1 )
  {
    v17 = *((unsigned int *)v3 + 1);
    HIWORD(v78) = 23;
    v78 = (v17 << 24) ^ ((v17 << 24) ^ v78) & 0xFFFF000000000000uLL;
  }
  if ( v10[1].Flink->Flink == (struct _LIST_ENTRY *)34525 && v16 == 2 )
  {
    if ( *(_QWORD *)(v4 + 1064) )
      *((_DWORD *)v3 + 266) = 1;
    goto LABEL_50;
  }
  if ( v16 != 1 )
  {
LABEL_50:
    v19 = *(_QWORD *)(v4 + 1064);
    if ( v19 )
    {
      v72 = 16;
      *(_QWORD *)Src = *(_QWORD *)(v19 + 144);
      v74 = *(_QWORD *)(v19 + 152);
      *(_QWORD *)&pguid.Data1 = 0;
      PtNumOfCharConverted = 0;
      v56 = 0;
      if ( !g_RasMobileCore && (v16 != 2 || !memcmp_0(Buf1, &GUID_NULL, 0x10u)) )
      {
        v20 = 1;
        v21 = GetINetCfgLock(&pguid, &PtNumOfCharConverted, 0, &v56);
        if ( v21 >= 0 )
        {
          v22 = WPP_GLOBAL_Control;
        }
        else
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control[1].Flink,
              454,
              WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
              (unsigned __int16)v21);
            v22 = WPP_GLOBAL_Control;
          }
          v20 = 0;
        }
        if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v22[1].Blink) & 0x2000) != 0
          && BYTE1(v22[1].Blink) >= 4u )
        {
          WPP_SF_(v22[1].Flink, 455, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
        }
        v12 = DwAddLegacyKeysForInterface(Src);
        if ( v12
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 456, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v12);
        }
        if ( v20 && *(_QWORD *)&pguid.Data1 && PtNumOfCharConverted )
          ReleaseINetCfgLock(*(_QWORD *)&pguid.Data1, PtNumOfCharConverted, v56);
      }
    }
    goto LABEL_74;
  }
  *(_DWORD *)(*(_QWORD *)(v4 + 1064) + 172LL) = *((_DWORD *)v3 + 1);
  LODWORD(p_Flink) = SetCompartmentNetworkMapping(*(_QWORD *)(v4 + 1064) + 144LL, 1);
  v12 = (unsigned int)p_Flink;
  if ( !(_DWORD)p_Flink )
  {
    v18 = *(_OWORD *)(*(_QWORD *)(v4 + 1064) + 144LL);
    v80 = 1;
    v79 = v18;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    LODWORD(p_Flink) = WPP_SF_d(
                         WPP_GLOBAL_Control[1].Flink,
                         452,
                         WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                         (unsigned int)p_Flink);
  }
  *(_DWORD *)v3 = v12;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v8 = 453;
    goto LABEL_16;
  }
  return (int)p_Flink;
}

```

## disassembly

```asm
0x180010520  mov     [rsp-8+arg_8], rbx
0x180010525  push    rbp
0x180010526  push    rsi
0x180010527  push    rdi
0x180010528  push    r12
0x18001052a  push    r13
0x18001052c  push    r14
0x18001052e  push    r15
0x180010530  lea     rbp, [rsp-1050h]
0x180010538  mov     eax, 1150h
0x18001053d  call    _alloca_probe
0x180010542  sub     rsp, rax
0x180010545  mov     rax, cs:__security_cookie
0x18001054c  xor     rax, rsp
0x18001054f  mov     [rbp+1080h+var_40], rax
0x180010556  mov     r14, r8
0x180010559  mov     [rsp+1180h+var_1110], r8
0x18001055e  mov     rdi, rcx
0x180010561  mov     [rsp+1180h+var_1118], rcx
0x180010566  mov     rbx, cs:WPP_GLOBAL_Control
0x18001056d  lea     rsi, WPP_GLOBAL_Control
0x180010574  lea     r12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001057b  mov     r13d, 2000h
0x180010581  cmp     rbx, rsi
0x180010584  jz      short loc_1800105AA
0x180010586  test    [rbx+1Ch], r13d
0x18001058a  jz      short loc_1800105AA
0x18001058c  cmp     byte ptr [rbx+19h], 6
0x180010590  jb      short loc_1800105AA
0x180010592  mov     rcx, [rbx+10h]
0x180010596  mov     edx, 1BCh
0x18001059b  mov     r8, r12
0x18001059e  call    WPP_SF_
0x1800105a3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800105aa  xor     r15d, r15d
0x1800105ad  lea     rcx, [rbp+1080h+OutBuffer]; void *
0x1800105b4  xor     edx, edx; Val
0x1800105b6  mov     [rsp+1180h+BytesReturned], r15d
0x1800105bb  mov     r8d, 8D0h; Size
0x1800105c1  call    memset_0
0x1800105c6  test    rdi, rdi
0x1800105c9  jz      loc_1800115FB
0x1800105cf  cmp     dword ptr [rdi+18h], 2
0x1800105d3  jz      loc_1800115D4
0x1800105d9  cmp     dword ptr [rdi+1Ch], 2
0x1800105dd  jz      short loc_18001064D
0x1800105df  mov     dword ptr [r14], 25Eh
0x1800105e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105ed  cmp     rcx, rsi
0x1800105f0  jz      loc_18001167A
0x1800105f6  test    [rcx+1Ch], r13d
0x1800105fa  jz      short loc_18001061A
0x1800105fc  cmp     byte ptr [rcx+19h], 2
0x180010600  jb      short loc_18001061A
0x180010602  mov     rcx, [rcx+10h]
0x180010606  mov     edx, 1C1h
0x18001060b  mov     r8, r12
0x18001060e  call    WPP_SF_
0x180010613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001061a  cmp     rcx, rsi
0x18001061d  jz      loc_18001167A
0x180010623  test    [rcx+1Ch], r13d
0x180010627  jz      loc_18001167A
0x18001062d  cmp     byte ptr [rcx+19h], 6
0x180010631  jb      loc_18001167A
0x180010637  mov     edx, 1C2h
0x18001063c  mov     r8, r12
0x18001063f  mov     rcx, [rcx+10h]
0x180010643  call    WPP_SF_
0x180010648  jmp     loc_18001167A
0x18001064d  mov     rax, [rdi+418h]
0x180010654  mov     esi, 264h
0x180010659  test    rax, rax
0x18001065c  jnz     short loc_180010667
0x18001065e  mov     r12, [rdi+0F0h]
0x180010665  jmp     short loc_18001066B
0x180010667  mov     r12, [rax+20h]
0x18001066b  mov     [rsp+1180h+var_1120], r12
0x180010670  test    r12, r12
0x180010673  jz      loc_180011592
0x180010679  mov     ecx, [r14]
0x18001067c  mov     rax, [r12+10h]
0x180010681  cmp     [rax], ecx
0x180010683  jz      short loc_180010698
0x180010685  mov     r12, [r12]
0x180010689  mov     [rsp+1180h+var_1120], r12
0x18001068e  test    r12, r12
0x180010691  jnz     short loc_18001067C
0x180010693  jmp     loc_180011592
0x180010698  mov     rax, [rdi+100h]
0x18001069f  lea     rdx, [r14+224h]; Src
0x1800106a6  mov     [rbp+1080h+OutBuffer], rax
0x1800106ad  mov     ecx, 4B8h
0x1800106b2  movzx   eax, word ptr [r14]
0x1800106b6  mov     ebx, r15d
0x1800106b9  mov     [rbp+1080h+var_908], ax
0x1800106c0  mov     eax, [r14+220h]
0x1800106c7  cmp     eax, ecx
0x1800106c9  cmova   eax, ecx
0x1800106cc  lea     rcx, [rbp+1080h+var_4F8]; void *
0x1800106d3  mov     r8d, eax; Size
0x1800106d6  mov     [rbp+1080h+var_4FC], r8d
0x1800106dd  call    memcpy_0
0x1800106e2  cmp     [rdi+428h], r15
0x1800106e9  mov     ecx, r15d
0x1800106ec  mov     rax, [r12+10h]
0x1800106f1  mov     edx, 1
0x1800106f6  setnz   cl
0x1800106f9  mov     [rax+120h], ecx
0x1800106ff  mov     rax, [r12+10h]
0x180010704  cmp     dword ptr [rax], 800h
0x18001070a  jz      short loc_180010720
0x18001070c  cmp     dword ptr [rax], 86DDh
0x180010712  mov     r13d, r15d
0x180010715  mov     [rsp+1180h+var_113C], r15d
0x18001071a  jnz     loc_180010A2B
0x180010720  mov     r13d, [rbp+1080h+var_4F8]
0x180010727  mov     [rsp+1180h+var_113C], r13d
0x18001072c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010733  lea     rax, WPP_GLOBAL_Control
0x18001073a  mov     esi, 2000h
0x18001073f  cmp     rcx, rax
0x180010742  jz      short loc_180010772
0x180010744  test    [rcx+1Ch], esi
0x180010747  jz      short loc_180010772
0x180010749  cmp     byte ptr [rcx+19h], 4
0x18001074d  jb      short loc_180010772
0x18001074f  mov     rcx, [rcx+10h]
0x180010753  lea     r9, [rdi+8]
0x180010757  mov     edx, 1C3h
0x18001075c  mov     dword ptr [rsp+1180h+lpWideCharStr], r13d
0x180010761  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180010768  call    WPP_SF_sd
0x18001076d  mov     edx, 1
0x180010772  cmp     r13d, edx
0x180010775  ja      short loc_1800107B8
0x180010777  mov     ecx, [r14+4]
0x18001077b  mov     eax, 17h
0x180010780  mov     [rbp+1080h+var_4DA], ax
0x180010787  mov     rdx, 0FFFF000000000000h
0x180010791  mov     rax, [rbp+0BA0h]
0x180010798  shl     rcx, 18h
0x18001079c  xor     rax, rcx
0x18001079f  and     rcx, 0FFFFFFFFFF000000h
0x1800107a6  and     rax, rdx
0x1800107a9  mov     edx, 1
0x1800107ae  xor     rax, rcx
0x1800107b1  mov     [rbp+0BA0h], rax
0x1800107b8  mov     rax, [r12+10h]
0x1800107bd  cmp     dword ptr [rax], 86DDh
0x1800107c3  jnz     short loc_1800107E4
0x1800107c5  cmp     r13d, 2
0x1800107c9  jnz     short loc_1800107E4
0x1800107cb  cmp     [rdi+428h], r15
0x1800107d2  jz      loc_1800108A5
0x1800107d8  mov     [r14+428h], edx
0x1800107df  jmp     loc_1800108A5
0x1800107e4  cmp     r13d, edx
0x1800107e7  jnz     loc_1800108A5
0x1800107ed  mov     rcx, [rdi+428h]
0x1800107f4  mov     eax, [r14+4]
0x1800107f8  mov     [rcx+0ACh], eax
0x1800107fe  mov     rcx, [rdi+428h]
0x180010805  add     rcx, 90h
0x18001080c  call    SetCompartmentNetworkMapping
0x180010811  mov     ebx, eax
0x180010813  test    eax, eax
0x180010815  jz      short loc_180010884
0x180010817  mov     rcx, cs:WPP_GLOBAL_Control
0x18001081e  lea     rdi, WPP_GLOBAL_Control
0x180010825  cmp     rcx, rdi
0x180010828  jz      short loc_18001084D
0x18001082a  test    [rcx+1Ch], esi
0x18001082d  jz      short loc_18001084D
0x18001082f  cmp     byte ptr [rcx+19h], 2
0x180010833  jb      short loc_18001084D
0x180010835  mov     rcx, [rcx+10h]
0x180010839  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180010840  mov     edx, 1C4h
0x180010845  mov     r9d, eax
0x180010848  call    WPP_SF_d
0x18001084d  mov     [r14], ebx
0x180010850  mov     rcx, cs:WPP_GLOBAL_Control
0x180010857  cmp     rcx, rdi
0x18001085a  jz      loc_18001167A
0x180010860  test    [rcx+1Ch], esi
0x180010863  jz      loc_18001167A
0x180010869  cmp     byte ptr [rcx+19h], 6
0x18001086d  jb      loc_18001167A
0x180010873  mov     edx, 1C5h
0x180010878  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001087f  jmp     loc_18001063F
0x180010884  mov     rax, [rdi+428h]
0x18001088b  mov     edx, 1
0x180010890  movups  xmm0, xmmword ptr [rax+90h]
0x180010897  mov     [rbp+1080h+var_4C8], edx
0x18001089d  movdqu  [rbp+1080h+var_4D8], xmm0
0x1800108a5  mov     rcx, [rdi+428h]
0x1800108ac  test    rcx, rcx
0x1800108af  jz      loc_180010A2B
0x1800108b5  cmp     cs:g_RasMobileCore, r15d
0x1800108bc  mov     r9d, 10h
0x1800108c2  mov     [rbp+1080h+var_704], r9w
0x1800108ca  mov     rax, [rcx+90h]
0x1800108d1  mov     qword ptr [rbp+1080h+Src], rax
0x1800108d8  mov     rax, [rcx+98h]
0x1800108df  mov     [rbp+1080h+var_6FA], rax
0x1800108e6  mov     qword ptr [rsp+1180h+pguid.Data1], r15
0x1800108eb  mov     [rsp+1180h+PtNumOfCharConverted], r15
0x1800108f0  mov     [rsp+1180h+var_1140], r15d
0x1800108f5  jnz     loc_180010A2B
0x1800108fb  cmp     r13d, 2
0x1800108ff  jnz     short loc_180010922
0x180010901  mov     r8d, r9d; Size
0x180010904  lea     rdx, GUID_NULL; Buf2
0x18001090b  lea     rcx, [rbp+1080h+Buf1]; Buf1
0x180010912  call    memcmp_0
0x180010917  test    eax, eax
0x180010919  jnz     loc_180010A2B
0x18001091f  lea     edx, [rax+1]
0x180010922  mov     esi, edx
0x180010924  lea     r9, [rsp+1180h+var_1140]
0x180010929  lea     rdx, [rsp+1180h+PtNumOfCharConverted]
0x18001092e  xor     r8d, r8d
0x180010931  lea     rcx, [rsp+1180h+pguid]
0x180010936  call    GetINetCfgLock
0x18001093b  test    eax, eax
0x18001093d  jns     short loc_180010986
0x18001093f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010946  lea     rdx, WPP_GLOBAL_Control
0x18001094d  cmp     rcx, rdx
0x180010950  jz      short loc_180010981
0x180010952  test    dword ptr [rcx+1Ch], 2000h
0x180010959  jz      short loc_180010981
0x18001095b  cmp     byte ptr [rcx+19h], 2
0x18001095f  jb      short loc_180010981
0x180010961  mov     rcx, [rcx+10h]
0x180010965  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x18001096c  movzx   r9d, ax
0x180010970  mov     edx, 1C6h
0x180010975  call    WPP_SF_d
0x18001097a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010981  mov     esi, r15d
0x180010984  jmp     short loc_18001098D
0x180010986  mov     rcx, cs:WPP_GLOBAL_Control
0x18001098d  lea     rax, WPP_GLOBAL_Control
0x180010994  cmp     rcx, rax
0x180010997  jz      short loc_1800109BD
0x180010999  test    dword ptr [rcx+1Ch], 2000h
0x1800109a0  jz      short loc_1800109BD
0x1800109a2  cmp     byte ptr [rcx+19h], 4
0x1800109a6  jb      short loc_1800109BD
0x1800109a8  mov     rcx, [rcx+10h]
0x1800109ac  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800109b3  mov     edx, 1C7h
0x1800109b8  call    WPP_SF_
0x1800109bd  lea     rcx, [rbp+1080h+Src]
0x1800109c4  call    DwAddLegacyKeysForInterface
0x1800109c9  mov     ebx, eax
0x1800109cb  test    eax, eax
0x1800109cd  jz      short loc_180010A09
0x1800109cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109d6  lea     rax, WPP_GLOBAL_Control
0x1800109dd  cmp     rcx, rax
0x1800109e0  jz      short loc_180010A09
0x1800109e2  test    dword ptr [rcx+1Ch], 2000h
0x1800109e9  jz      short loc_180010A09
0x1800109eb  cmp     byte ptr [rcx+19h], 2
0x1800109ef  jb      short loc_180010A09
0x1800109f1  mov     rcx, [rcx+10h]
0x1800109f5  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800109fc  mov     edx, 1C8h
0x180010a01  mov     r9d, ebx
0x180010a04  call    WPP_SF_d
0x180010a09  test    esi, esi
0x180010a0b  jz      short loc_180010A2B
0x180010a0d  mov     rcx, qword ptr [rsp+1180h+pguid.Data1]
0x180010a12  test    rcx, rcx
0x180010a15  jz      short loc_180010A2B
0x180010a17  mov     rdx, [rsp+1180h+PtNumOfCharConverted]
0x180010a1c  test    rdx, rdx
0x180010a1f  jz      short loc_180010A2B
0x180010a21  mov     r8d, [rsp+1180h+var_1140]
0x180010a26  call    ReleaseINetCfgLock
0x180010a2b  mov     r8, [rdi+428h]
0x180010a32  test    r8, r8
0x180010a35  jz      loc_180010DEB
0x180010a3b  lea     rax, [rbp+1080h+WideCharStr]
0x180010a42  mov     [rsp+1180h+cchWideChar], 100h; cchWideChar
0x180010a4a  add     r8, 1BDh; lpMultiByteStr
0x180010a51  mov     [rsp+1180h+lpWideCharStr], rax; lpWideCharStr
0x180010a56  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180010a5a  xor     edx, edx; dwFlags
0x180010a5c  mov     ecx, 0FDE9h; CodePage
0x180010a61  call    cs:__imp_MultiByteToWideChar
0x180010a67  add     ax, ax
0x180010a6a  mov     [rbp+1080h+var_906], ax
0x180010a71  mov     rax, [r12+10h]
0x180010a76  cmp     dword ptr [rax], 800h
0x180010a7c  jz      short loc_180010A86
  ... truncated ...
```
