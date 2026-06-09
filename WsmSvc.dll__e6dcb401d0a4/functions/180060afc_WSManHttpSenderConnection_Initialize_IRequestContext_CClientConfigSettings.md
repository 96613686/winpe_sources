# WSManHttpSenderConnection::Initialize(IRequestContext *,CClientConfigSettings *)

- ea: `0x180060afc`
- end: `0x1800615ff`
- name: `?Initialize@WSManHttpSenderConnection@@QEAAKPEAVIRequestContext@@PEAVCClientConfigSettings@@@Z`
- size: `2819`
- prototype: `unsigned int __fastcall(WSManHttpSenderConnection *__hidden this, struct IRequestContext *, struct CClientConfigSettings *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800600d0`

## callees

- `0x180005d10`
- `0x180019950`
- `0x18005f258`
- `0x18005f6e0`
- `0x180060afc`
- `0x1800622f0`
- `0x1800672f4`
- `0x18006cb10`
- `0x18007e530`
- `0x1800bac30`
- `0x1800bad58`
- `0x18010e0a8`
- `0x1801123a8`
- `0x1801123e8`
- `0x18011349c`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061002`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006143e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006146d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800610fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006143e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006146d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800614e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061586`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006108d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006108d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060d26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180060d26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cf2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060dab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060dce`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060dab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180060dce`
- `wkscli!NetGetJoinInformation` at `0x180060ba5`
- `wkscli!NetGetJoinInformation` at `0x180060ba5`
- `netutils!NetApiBufferFree` at `0x1800612af`
- `netutils!NetApiBufferFree` at `0x1800612af`
- `WINHTTP!WinHttpSetOption` at `0x180060e7e`
- `WINHTTP!WinHttpSetOption` at `0x180060ea1`
- `WINHTTP!WinHttpSetOption` at `0x180060f5a`
- `WINHTTP!WinHttpSetOption` at `0x1800610f0`
- `WINHTTP!WinHttpSetOption` at `0x180060e7e`
- `WINHTTP!WinHttpSetOption` at `0x180060ea1`
- `WINHTTP!WinHttpSetOption` at `0x180060f5a`
- `WINHTTP!WinHttpSetOption` at `0x1800610f0`
- `WINHTTP!WinHttpConnect` at `0x180060eeb`
- `WINHTTP!WinHttpConnect` at `0x180060eeb`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180060f35`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180060f35`
- `WINHTTP!WinHttpCloseHandle` at `0x1800615db`
- `WINHTTP!WinHttpCloseHandle` at `0x1800615ed`
- `WINHTTP!WinHttpCloseHandle` at `0x1800615db`
- `WINHTTP!WinHttpCloseHandle` at `0x1800615ed`
- `WINHTTP!WinHttpOpen` at `0x180060e54`
- `WINHTTP!WinHttpOpen` at `0x180060e54`

## string_xrefs

- `0x180060d1a`: `BackwardsCompatibleEncryptionFormat`

## pseudocode

```c
unsigned int __fastcall WSManHttpSenderConnection::Initialize(
        WSManHttpSenderConnection *this,
        struct IRequestContext *a2,
        struct CClientConfigSettings *a3)
{
  DWORD v6; // ecx
  DWORD JoinInformation; // r14d
  int v8; // eax
  PVOID *v9; // rcx
  __int64 v10; // rdx
  unsigned int result; // eax
  DWORD inited; // edi
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  _NETSETUP_JOIN_STATUS v18; // eax
  char v19; // cl
  char v20; // al
  LPWSTR v21; // rcx
  PTP_WORK ThreadpoolWork; // rax
  PTP_WORK v23; // rax
  int v24; // eax
  int v25; // ecx
  void *v26; // rax
  void *v27; // rcx
  HINTERNET v28; // rax
  void *v29; // rcx
  _QWORD *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  const unsigned __int16 *v33; // r14
  LPWSTR v34; // rcx
  void *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // ebx
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  LPWSTR NameBuffer; // [rsp+38h] [rbp-18h] BYREF
  WSManHttpSenderConnection *v43; // [rsp+40h] [rbp-10h] BYREF
  int Buffer; // [rsp+98h] [rbp+48h] BYREF
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+A8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 1111, L"1111", 0x54Fu, 0);
    return 1359;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 1112, L"1112", 0x54Fu, a2);
    return 1359;
  }
  v6 = *((_DWORD *)this + 2296);
  if ( v6 )
  {
    SetLastError(v6);
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    return 14;
  }
  if ( WSManHttpSenderConnection::DestinationIsLocalhost(this, a2, (int *)this + 2857, (int *)this + 2858) )
  {
    v37 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return v37;
    v39 = 59;
    goto LABEL_97;
  }
  if ( this == (WSManHttpSenderConnection *)-11436LL )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 4617, L"4617", 0x54Fu, a2);
    v37 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return v37;
    v39 = 60;
    goto LABEL_97;
  }
  if ( !dword_180280C80 )
  {
    BufferType = NetSetupUnknownStatus;
    NameBuffer = 0;
    JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
    if ( NameBuffer )
      NetApiBufferFree(NameBuffer);
    if ( JoinInformation )
    {
      if ( JoinInformation != 50 || (unsigned __int8)IsNetpGetJoinInformationPresent() )
        goto LABEL_12;
      v8 = 0;
    }
    else
    {
      if ( BufferType != NetSetupDomainName )
      {
LABEL_12:
        v8 = dword_180280C7C;
LABEL_16:
        dword_180280C80 = 1;
        goto LABEL_17;
      }
      v8 = 1;
    }
    dword_180280C7C = v8;
    goto LABEL_16;
  }
  v8 = dword_180280C7C;
LABEL_17:
  *((_DWORD *)this + 2859) = v8;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this == (WSManHttpSenderConnection *)-11440LL )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 1757, L"1757", 0x54Fu, a2);
  }
  else
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
    if ( *(_DWORD *)(v10 + 528) == 2 || *((_DWORD *)this + 2857) )
    {
      *((_DWORD *)this + 2860) = 1;
      goto LABEL_24;
    }
    v33 = *(const unsigned __int16 **)(v10 + 536);
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x200000) != 0 )
      WPP_SF_q(v9[2], 15, WPP_2af42882626b3ea0521571d7279c7491_Traceguids, a3);
    if ( !TrustedHosts::IsHostTrusted((struct CClientConfigSettings *)((char *)a3 + 120), a2, v33, (int *)this + 2860)
      && (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2) )
    {
      v37 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        return v37;
      v39 = 61;
LABEL_97:
      WPP_SF_d(v38[2], v39, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v37);
      return v37;
    }
  }
LABEL_24:
  result = WSManHttpSenderConnection::InitializeOptions(this, a2);
  if ( result )
    return result;
  inited = WSManHttpSenderConnection::InitAuthMode(this, a2, a3);
  if ( inited )
  {
LABEL_67:
    v31 = (void *)*((_QWORD *)this + 1036);
    if ( v31 )
    {
      WinHttpCloseHandle(v31);
      *((_QWORD *)this + 1036) = 0;
    }
    v32 = (void *)*((_QWORD *)this + 1035);
    if ( v32 )
    {
      WinHttpCloseHandle(v32);
      *((_QWORD *)this + 1035) = 0;
    }
    return inited;
  }
  v13 = *((_DWORD *)this + 2848);
  if ( v13 == 5 || (v14 = *((_DWORD *)this + 2849), v14 == 5) )
  {
    v15 = 0;
  }
  else if ( v14 == 4 || v13 == 4 )
  {
    v15 = 1;
  }
  else
  {
    v15 = (v13 != 7) + 2;
  }
  if ( !*((_DWORD *)this + 2835) && !*((_DWORD *)this + 2836) )
  {
    if ( v15 == 2 )
    {
      *((_DWORD *)this + 2833) = 0;
      *((_WORD *)this + 5668) = 0;
      *((_BYTE *)this + 11338) = 1;
LABEL_42:
      _InterlockedExchange((volatile __int32 *)this + 2836, 1);
      goto LABEL_43;
    }
    NameBuffer = 0;
    BufferType = NetSetupUnknownStatus;
    cbData = 4;
    Type = 0;
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Client",
            0,
            0x101u,
            (PHKEY)&NameBuffer);
    inited = v16;
    if ( v16 )
    {
      if ( v16 == 2 )
      {
LABEL_37:
        v18 = NetSetupUnknownStatus;
        BufferType = NetSetupUnknownStatus;
LABEL_38:
        if ( v18 )
        {
          v19 = 0;
          v20 = 1;
        }
        else
        {
          v19 = 1;
          v20 = 0;
        }
        *((_BYTE *)this + 11332) = v20;
        *((_BYTE *)this + 11333) = v20;
        *((_BYTE *)this + 11334) = v20;
        *((_BYTE *)this + 11335) = v20;
        *((_BYTE *)this + 11336) = v20;
        *((_BYTE *)this + 11337) = v20;
        *((_BYTE *)this + 11338) = v19;
        v21 = NameBuffer;
        NameBuffer = 0;
        if ( v21 )
          RegCloseKey((HKEY)v21);
        goto LABEL_42;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v16);
      v34 = NameBuffer;
      NameBuffer = 0;
      if ( v34 )
        RegCloseKey((HKEY)v34);
    }
    else
    {
      v17 = RegQueryValueExW(
              (HKEY)NameBuffer,
              L"BackwardsCompatibleEncryptionFormat",
              0,
              &Type,
              (LPBYTE)&BufferType,
              &cbData);
      inited = v17;
      if ( v17 == 2 )
      {
        v18 = NetSetupUnknownStatus;
        BufferType = NetSetupUnknownStatus;
        goto LABEL_36;
      }
      if ( !v17 )
      {
        v18 = BufferType;
LABEL_36:
        if ( Type == 4 )
          goto LABEL_38;
        goto LABEL_37;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v17);
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>((HKEY *)&NameBuffer);
    }
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, inited);
    return inited;
  }
LABEL_43:
  ThreadpoolWork = CreateThreadpoolWork(WSManHttpSenderConnection::_NotifyClientThread, this, 0);
  *((_QWORD *)this + 1425) = ThreadpoolWork;
  if ( !ThreadpoolWork )
  {
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_66;
    v36 = 62;
    goto LABEL_126;
  }
  v23 = CreateThreadpoolWork(WSManHttpSenderConnection::_ShutdownRequestHelper, this, 0);
  *((_QWORD *)this + 1426) = v23;
  if ( !v23 )
  {
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_66;
    v36 = 63;
    goto LABEL_126;
  }
  v24 = *((_DWORD *)this + 2848);
  if ( v24 != 5 )
  {
    v25 = *((_DWORD *)this + 2849);
    if ( v25 != 5 )
    {
      if ( v25 == 4 || v24 == 4 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 528LL) == 2 )
          goto LABEL_49;
      }
      else if ( v24 != 7 )
      {
        goto LABEL_49;
      }
    }
  }
  inited = WSManHttpSenderConnection::GetNegotiateCredentialsHandle(this, a3);
  if ( inited )
    goto LABEL_66;
  inited = WSManHttpSenderConnection::SetNegotiateSPN(this, a3);
  if ( inited )
    goto LABEL_66;
LABEL_49:
  v26 = WinHttpOpen(
          L"Microsoft WinRM Client",
          *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 976LL) != 2,
          0,
          0,
          0x10000000u);
  *((_QWORD *)this + 1035) = v26;
  if ( !v26 )
  {
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_66;
    v36 = 64;
    goto LABEL_126;
  }
  Buffer = 1;
  if ( !WinHttpSetOption(v26, 0x49u, &Buffer, 4u) )
  {
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_66;
    v36 = 65;
    goto LABEL_126;
  }
  v27 = (void *)*((_QWORD *)this + 1035);
  Buffer = 0;
  if ( !WinHttpSetOption(v27, 0x58u, &Buffer, 4u) )
  {
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      goto LABEL_66;
    v36 = 66;
    goto LABEL_126;
  }
  if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 960LL) )
  {
    v35 = (void *)*((_QWORD *)this + 1035);
    Buffer = 2;
    if ( WinHttpSetOption(v35, 0x4Du, &Buffer, 4u) )
    {
      *((_DWORD *)this + 2867) = 2;
      if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_AUTOLOGONPOLICY_HIGH) )
        WSMan::EventHandler::Write(&LOG_WSMAN_AN_AUTOLOGONPOLICY_HIGH, 0, 0);
      goto LABEL_53;
    }
    inited = GetLastError();
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
    {
LABEL_66:
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, inited);
      goto LABEL_67;
    }
    v36 = 67;
LABEL_126:
    WPP_SF_d(v30[2], v36, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, inited);
    goto LABEL_66;
  }
LABEL_53:
  v28 = WinHttpConnect(
          *((HINTERNET *)this + 1035),
          *(LPCWSTR *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
          *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 532LL),
          0);
  *((_QWORD *)this + 1036) = v28;
  if ( !v28 )
  {
    inited = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        (unsigned int)&WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
        inited);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64, _QWORD, _DWORD))(*(_QWORD *)a2 + 64LL))(
      a2,
      inited,
      1077134239,
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 532LL));
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, this, v28);
  v29 = (void *)*((_QWORD *)this + 1036);
  v43 = this;
  if ( WinHttpSetStatusCallback(v29, WSManHttpSenderConnection::_StatusCallback, 0x97F0C30u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL
    || !WinHttpSetOption(*((HINTERNET *)this + 1036), 0x2Du, &v43, 8u) )
  {
    inited = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)&WPP_1a71944546983a3ae75b6cead512f96f_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
        inited);
    goto LABEL_66;
  }
  return 0;
}

```

## disassembly

```asm
0x180060afc  mov     [rsp-38h+arg_0], rbx
0x180060b01  push    rbp
0x180060b02  push    rsi
0x180060b03  push    rdi
0x180060b04  push    r12
0x180060b06  push    r13
0x180060b08  push    r14
0x180060b0a  push    r15
0x180060b0c  mov     rbp, rsp
0x180060b0f  sub     rsp, 50h
0x180060b13  mov     r13, r8
0x180060b16  mov     rsi, rdx
0x180060b19  mov     rbx, rcx
0x180060b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060b23  lea     r14, WPP_GLOBAL_Control
0x180060b2a  cmp     rcx, r14
0x180060b2d  jnz     loc_1800611AC
0x180060b33  xor     r12d, r12d
0x180060b36  test    rsi, rsi
0x180060b39  jz      loc_1800611D6
0x180060b3f  test    r13, r13
0x180060b42  jz      loc_1800611E9
0x180060b48  mov     ecx, [rbx+23E0h]; dwErrCode
0x180060b4e  test    ecx, ecx
0x180060b50  jnz     loc_180061002
0x180060b56  lea     r15, [rbx+2CA4h]
0x180060b5d  mov     rdx, rsi; struct IRequestContext *
0x180060b60  mov     r8, r15; int *
0x180060b63  lea     r9, [rbx+2CA8h]; int *
0x180060b6a  mov     rcx, rbx; this
0x180060b6d  call    ?DestinationIsLocalhost@WSManHttpSenderConnection@@AEAAKPEAVIRequestContext@@PEAH1@Z; WSManHttpSenderConnection::DestinationIsLocalhost(IRequestContext *,int *,int *)
0x180060b72  test    eax, eax
0x180060b74  jnz     loc_180061216
0x180060b7a  lea     rdi, [rbx+2CACh]
0x180060b81  test    rdi, rdi
0x180060b84  jz      loc_180061251
0x180060b8a  cmp     cs:dword_180280C80, r12d
0x180060b91  jnz     short loc_180060BD2
0x180060b93  lea     r8, [rbp+BufferType]; BufferType
0x180060b97  mov     [rbp+BufferType], r12d
0x180060b9b  lea     rdx, [rbp+NameBuffer]; lpNameBuffer
0x180060b9f  mov     [rbp+NameBuffer], r12
0x180060ba3  xor     ecx, ecx; lpServer
0x180060ba5  call    cs:__imp_NetGetJoinInformation
0x180060bab  mov     rcx, [rbp+NameBuffer]; Buffer
0x180060baf  mov     r14d, eax
0x180060bb2  test    rcx, rcx
0x180060bb5  jnz     loc_1800612AF
0x180060bbb  test    r14d, r14d
0x180060bbe  jnz     loc_1800612BA
0x180060bc4  cmp     [rbp+BufferType], 3
0x180060bc8  jz      short loc_180060BDA
0x180060bca  mov     eax, cs:dword_180280C7C
0x180060bd0  jmp     short loc_180060BE5
0x180060bd2  mov     eax, cs:dword_180280C7C
0x180060bd8  jmp     short loc_180060BF6
0x180060bda  mov     eax, 1
0x180060bdf  mov     cs:dword_180280C7C, eax
0x180060be5  mov     cs:dword_180280C80, 1
0x180060bef  lea     r14, WPP_GLOBAL_Control
0x180060bf6  mov     [rdi], eax
0x180060bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180060bff  cmp     rcx, r14
0x180060c02  jz      short loc_180060C11
0x180060c04  test    dword ptr [rcx+1Ch], 400h
0x180060c0b  jnz     loc_1800612D9
0x180060c11  lea     rdi, [rbx+2CB0h]
0x180060c18  test    rdi, rdi
0x180060c1b  jz      loc_1800612FD
0x180060c21  mov     rax, [rbx+28h]
0x180060c25  mov     rdx, [rax+80h]
0x180060c2c  cmp     dword ptr [rdx+210h], 2
0x180060c33  jz      short loc_180060C3E
0x180060c35  cmp     [r15], r12d
0x180060c38  jz      loc_180061021
0x180060c3e  mov     dword ptr [rdi], 1
0x180060c44  mov     rdx, rsi; struct IRequestContext *
0x180060c47  mov     rcx, rbx; this
0x180060c4a  call    ?InitializeOptions@WSManHttpSenderConnection@@AEAAKPEAVIRequestContext@@@Z; WSManHttpSenderConnection::InitializeOptions(IRequestContext *)
0x180060c4f  test    eax, eax
0x180060c51  jnz     loc_180060F6A
0x180060c57  mov     r8, r13; struct CClientConfigSettings *
0x180060c5a  mov     rdx, rsi; struct IRequestContext *
0x180060c5d  mov     rcx, rbx; this
0x180060c60  call    ?InitAuthMode@WSManHttpSenderConnection@@AEAAKPEAVIRequestContext@@PEAVCClientConfigSettings@@@Z; WSManHttpSenderConnection::InitAuthMode(IRequestContext *,CClientConfigSettings *)
0x180060c65  mov     edi, eax
0x180060c67  test    eax, eax
0x180060c69  jnz     loc_180060FDB
0x180060c6f  mov     ecx, [rbx+2C80h]
0x180060c75  lea     r15d, [rax+4]
0x180060c79  cmp     ecx, 5
0x180060c7c  jz      loc_180060FAA
0x180060c82  mov     eax, [rbx+2C84h]
0x180060c88  cmp     eax, 5
0x180060c8b  jz      loc_180060FAA
0x180060c91  cmp     eax, r15d
0x180060c94  jnz     loc_1800610C0
0x180060c9a  mov     eax, 1
0x180060c9f  cmp     [rbx+2C4Ch], r12d
0x180060ca6  jnz     loc_180060D9E
0x180060cac  cmp     [rbx+2C50h], r12d
0x180060cb3  jnz     loc_180060D9E
0x180060cb9  cmp     eax, 2
0x180060cbc  jz      loc_180061342
0x180060cc2  lea     rax, [rbp+NameBuffer]
0x180060cc6  mov     [rbp+NameBuffer], r12
0x180060cca  mov     r9d, 101h; samDesired
0x180060cd0  mov     [rsp+50h+phkResult], rax; phkResult
0x180060cd5  xor     r8d, r8d; ulOptions
0x180060cd8  mov     [rbp+BufferType], r12d
0x180060cdc  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180060ce3  mov     [rbp+cbData], r15d
0x180060ce7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060cee  mov     [rbp+Type], r12d
0x180060cf2  call    cs:__imp_RegOpenKeyExW
0x180060cf8  mov     edi, eax
0x180060cfa  test    eax, eax
0x180060cfc  jnz     loc_180061067
0x180060d02  mov     rcx, [rbp+NameBuffer]; hKey
0x180060d06  lea     rax, [rbp+cbData]
0x180060d0a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180060d0f  lea     r9, [rbp+Type]; lpType
0x180060d13  lea     rax, [rbp+BufferType]
0x180060d17  xor     r8d, r8d; lpReserved
0x180060d1a  lea     rdx, ValueName; "BackwardsCompatibleEncryptionFormat"
0x180060d21  mov     [rsp+50h+phkResult], rax; lpData
0x180060d26  call    cs:__imp_RegQueryValueExW
0x180060d2c  mov     edi, eax
0x180060d2e  cmp     eax, 2
0x180060d31  jnz     loc_18006135D
0x180060d37  mov     eax, r12d
0x180060d3a  mov     [rbp+BufferType], eax
0x180060d3d  cmp     [rbp+Type], r15d
0x180060d41  jz      short loc_180060D49
0x180060d43  mov     eax, r12d
0x180060d46  mov     [rbp+BufferType], eax
0x180060d49  test    eax, eax
0x180060d4b  jnz     loc_180061140
0x180060d51  mov     cl, 1
0x180060d53  mov     al, r12b
0x180060d56  mov     [rbx+2C44h], al
0x180060d5c  mov     [rbx+2C45h], al
0x180060d62  mov     [rbx+2C46h], al
0x180060d68  mov     [rbx+2C47h], al
0x180060d6e  mov     [rbx+2C48h], al
0x180060d74  mov     [rbx+2C49h], al
0x180060d7a  mov     [rbx+2C4Ah], cl
0x180060d80  mov     rcx, [rbp+NameBuffer]; hKey
0x180060d84  mov     [rbp+NameBuffer], r12
0x180060d88  test    rcx, rcx
0x180060d8b  jz      short loc_180060D93
0x180060d8d  call    cs:__imp_RegCloseKey
0x180060d93  mov     eax, 1
0x180060d98  xchg    eax, [rbx+2C50h]
0x180060d9e  xor     r8d, r8d; pcbe
0x180060da1  lea     rcx, ?_NotifyClientThread@WSManHttpSenderConnection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180060da8  mov     rdx, rbx; pv
0x180060dab  call    cs:__imp_CreateThreadpoolWork
0x180060db1  mov     [rbx+2C88h], rax
0x180060db8  test    rax, rax
0x180060dbb  jz      loc_1800613CE
0x180060dc1  xor     r8d, r8d; pcbe
0x180060dc4  lea     rcx, ?_ShutdownRequestHelper@WSManHttpSenderConnection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180060dcb  mov     rdx, rbx; pv
0x180060dce  call    cs:__imp_CreateThreadpoolWork
0x180060dd4  mov     [rbx+2C90h], rax
0x180060ddb  test    rax, rax
0x180060dde  jz      loc_180061417
0x180060de4  mov     eax, [rbx+2C80h]
0x180060dea  cmp     eax, 5
0x180060ded  jz      loc_180060F82
0x180060df3  mov     ecx, [rbx+2C84h]
0x180060df9  cmp     ecx, 5
0x180060dfc  jz      loc_180060F82
0x180060e02  cmp     ecx, r15d
0x180060e05  jnz     loc_1800610A9
0x180060e0b  mov     rax, [rbx+28h]
0x180060e0f  mov     rcx, [rax+80h]
0x180060e16  cmp     dword ptr [rcx+210h], 2
0x180060e1d  jnz     loc_180060F82
0x180060e23  mov     rax, [rbx+28h]
0x180060e27  mov     edx, r12d
0x180060e2a  mov     edi, 2
0x180060e2f  mov     dword ptr [rsp+50h+phkResult], 10000000h; dwFlags
0x180060e37  mov     rcx, [rax+80h]
0x180060e3e  cmp     [rcx+3D0h], edi
0x180060e44  lea     rcx, pszAgentW; "Microsoft WinRM Client"
0x180060e4b  setnz   dl; dwAccessType
0x180060e4e  xor     r9d, r9d; pszProxyBypassW
0x180060e51  xor     r8d, r8d; pszProxyW
0x180060e54  call    cs:__imp_WinHttpOpen
0x180060e5a  mov     [rbx+2058h], rax
0x180060e61  test    rax, rax
0x180060e64  jz      loc_18006143E
0x180060e6a  mov     r9d, r15d; dwBufferLength
0x180060e6d  mov     [rbp+Buffer], 1
0x180060e74  lea     r8, [rbp+Buffer]; lpBuffer
0x180060e78  mov     rcx, rax; hInternet
0x180060e7b  lea     edx, [rdi+47h]; dwOption
0x180060e7e  call    cs:__imp_WinHttpSetOption
0x180060e84  test    eax, eax
0x180060e86  jz      loc_18006146D
0x180060e8c  mov     rcx, [rbx+2058h]; hInternet
0x180060e93  lea     r8, [rbp+Buffer]; lpBuffer
0x180060e97  mov     r9d, r15d; dwBufferLength
0x180060e9a  mov     [rbp+Buffer], r12d
0x180060e9e  lea     edx, [rdi+56h]; dwOption
0x180060ea1  call    cs:__imp_WinHttpSetOption
0x180060ea7  test    eax, eax
0x180060ea9  jz      loc_180060FB2
0x180060eaf  mov     rax, [rbx+28h]
0x180060eb3  mov     rcx, [rax+80h]
0x180060eba  cmp     [rcx+3C0h], r12
0x180060ec1  jnz     loc_1800610DA
0x180060ec7  mov     rax, [rbx+28h]
0x180060ecb  xor     r9d, r9d; dwReserved
0x180060ece  mov     rcx, [rbx+2058h]; hSession
0x180060ed5  mov     rdx, [rax+80h]
0x180060edc  movzx   r8d, word ptr [rdx+214h]; nServerPort
0x180060ee4  mov     rdx, [rdx+218h]; pswzServerName
0x180060eeb  call    cs:__imp_WinHttpConnect
0x180060ef1  mov     [rbx+2060h], rax
0x180060ef8  test    rax, rax
0x180060efb  jz      loc_1800614E3
0x180060f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180060f08  cmp     rcx, r14
0x180060f0b  jz      short loc_180060F1A
0x180060f0d  test    dword ptr [rcx+1Ch], 400h
0x180060f14  jnz     loc_180061564
0x180060f1a  mov     rcx, [rbx+2060h]; hInternet
0x180060f21  lea     rdx, ?_StatusCallback@WSManHttpSenderConnection@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x180060f28  xor     r9d, r9d; dwReserved
0x180060f2b  mov     [rbp+var_10], rbx
0x180060f2f  mov     r8d, 97F0C30h; dwNotificationFlags
0x180060f35  call    cs:__imp_WinHttpSetStatusCallback
0x180060f3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180060f3f  jz      loc_180061586
0x180060f45  mov     rcx, [rbx+2060h]; hInternet
0x180060f4c  lea     r8, [rbp+var_10]; lpBuffer
0x180060f50  mov     r9d, 8; dwBufferLength
0x180060f56  lea     edx, [r9+25h]; dwOption
0x180060f5a  call    cs:__imp_WinHttpSetOption
0x180060f60  test    eax, eax
0x180060f62  jz      loc_180061586
0x180060f68  xor     eax, eax
0x180060f6a  mov     rbx, [rsp+50h+arg_0]
0x180060f72  add     rsp, 50h
0x180060f76  pop     r15
0x180060f78  pop     r14
0x180060f7a  pop     r13
0x180060f7c  pop     r12
0x180060f7e  pop     rdi
0x180060f7f  pop     rsi
0x180060f80  pop     rbp
0x180060f81  retn
0x180060f82  mov     rdx, r13; struct CClientConfigSettings *
0x180060f85  mov     rcx, rbx; this
0x180060f88  call    ?GetNegotiateCredentialsHandle@WSManHttpSenderConnection@@AEAAKPEAVCClientConfigSettings@@@Z; WSManHttpSenderConnection::GetNegotiateCredentialsHandle(CClientConfigSettings *)
0x180060f8d  mov     edi, eax
0x180060f8f  test    eax, eax
0x180060f91  jnz     short loc_180060FCA
0x180060f93  mov     rdx, r13; struct CClientConfigSettings *
0x180060f96  mov     rcx, rbx; this
0x180060f99  call    ?SetNegotiateSPN@WSManHttpSenderConnection@@AEAAKPEAVCClientConfigSettings@@@Z; WSManHttpSenderConnection::SetNegotiateSPN(CClientConfigSettings *)
0x180060f9e  mov     edi, eax
0x180060fa0  test    eax, eax
0x180060fa2  jz      loc_180060E23
0x180060fa8  jmp     short loc_180060FCA
0x180060faa  mov     eax, r12d
0x180060fad  jmp     loc_180060C9F
0x180060fb2  call    cs:__imp_GetLastError
0x180060fb8  mov     edi, eax
0x180060fba  mov     rcx, cs:WPP_GLOBAL_Control
0x180060fc1  cmp     rcx, r14
0x180060fc4  jnz     loc_18006149C
0x180060fca  mov     rax, [rsi]
0x180060fcd  mov     edx, edi
0x180060fcf  mov     rcx, rsi
0x180060fd2  mov     rax, [rax+48h]
0x180060fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fdb  mov     rcx, [rbx+2060h]; hInternet
0x180060fe2  test    rcx, rcx
0x180060fe5  jnz     loc_1800615DB
0x180060feb  mov     rcx, [rbx+2058h]; hInternet
0x180060ff2  test    rcx, rcx
0x180060ff5  jnz     loc_1800615ED
0x180060ffb  mov     eax, edi
0x180060ffd  jmp     loc_180060F6A
0x180061002  call    cs:__imp_SetLastError
0x180061008  mov     rax, [rsi]
0x18006100b  mov     rcx, rsi
0x18006100e  mov     rax, [rax+18h]
0x180061012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061017  mov     eax, 0Eh
0x18006101c  jmp     loc_180060F6A
0x180061021  mov     r14, [rdx+218h]
0x180061028  lea     r15, WPP_GLOBAL_Control
0x18006102f  cmp     rcx, r15
0x180061032  jz      short loc_180061041
0x180061034  test    dword ptr [rcx+1Ch], 200000h
  ... truncated ...
```
