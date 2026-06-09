# TnoService::InitializeService(void)

- ea: `0x180004b74`
- end: `0x1800055e5`
- name: `?InitializeService@TnoService@@QEAAJXZ`
- size: `2673`
- prototype: `__int64 __fastcall(TnoService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000594c`

## callees

- `0x180004374`
- `0x180004b74`
- `0x180007db8`
- `0x180008290`
- `0x1800082d0`
- `0x180008360`
- `0x1800190f0`
- `0x1800191b8`
- `0x180159010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004c72`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180004c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b88`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000557d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b88`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000557d`

## string_xrefs

- `0x180005077`: `PeerDist-Common-KMDriver-Enabled`
- `0x180004de2`: `Configuration Manager`
- `0x180004f02`: `Cache Manager`
- `0x180005012`: `Security Manager`
- `0x1800051be`: `Hosted Cache Manager`

## pseudocode

```c
__int64 __fastcall TnoService::InitializeService(struct _SERVICE_STATUS *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  SERVICE_STATUS_HANDLE v3; // rcx
  DWORD LastError; // eax
  int v5; // ebx
  Event *v6; // rbp
  int v7; // edi
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax
  __int64 v11; // rdx
  int v12; // eax
  CHostedCacheMsgEncoding *v13; // rcx

  GetTickCount64();
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 58, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v2 + 27) & 0x800) != 0 && *((_BYTE *)v2 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v2 + 12), 59, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v2 + 27) & 0x800) != 0
        && *((_BYTE *)v2 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v2 + 12), 60, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      }
    }
  }
  this[5].dwServiceType = 1;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
  }
  v3 = *(SERVICE_STATUS_HANDLE *)&this[1].dwCheckPoint;
  ++this[2].dwCheckPoint;
  this[2].dwCurrentState = 2;
  this[2].dwWaitHint = 60000;
  if ( SetServiceStatus(v3, this + 2) )
  {
    *(_QWORD *)&this[23].dwCheckPoint = 0;
    this[24].dwServiceType = 0;
    LOWORD(this[24].dwCurrentState) = 0;
    BYTE2(this[24].dwCurrentState) = 0;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        63,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Logging Manager");
    }
    v6 = (Event *)&this[4];
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[13].dwCheckPoint)(
           *(_QWORD *)&this[13].dwCheckPoint,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 64;
      goto LABEL_33;
    }
    BYTE2(this[24].dwServiceType) = 1;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&this[15].dwWin32ExitCode + 32LL))(*(_QWORD *)&this[15].dwWin32ExitCode);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 65;
      goto LABEL_33;
    }
    LOBYTE(v11) = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&this[5].dwCurrentState + 32LL))(
      *(_QWORD *)&this[5].dwCurrentState,
      v11);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        66,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Configuration Manager");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[5].dwCurrentState)(
           *(_QWORD *)&this[5].dwCurrentState,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 67;
      goto LABEL_33;
    }
    LOBYTE(this[23].dwCheckPoint) = 1;
    result = TnoService::StartupConfigurationCheck((TnoService *)this);
    if ( (int)result < 0 )
      return result;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        68,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "PeerDistAD Loader");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[16].dwControlsAccepted)(
           *(_QWORD *)&this[16].dwControlsAccepted,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 69;
      goto LABEL_33;
    }
    BYTE1(this[24].dwCurrentState) = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        70,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Cache Manager");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[6].dwServiceType)(
           *(_QWORD *)&this[6].dwServiceType,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 71;
      goto LABEL_33;
    }
    BYTE1(this[23].dwCheckPoint) = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        72,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Discovery Manager");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[6].dwWaitHint)(
           *(_QWORD *)&this[6].dwWaitHint,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 73;
      goto LABEL_33;
    }
    BYTE2(this[23].dwCheckPoint) = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        74,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Security Manager");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[7].dwCheckPoint)(
           *(_QWORD *)&this[7].dwCheckPoint,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 75;
      goto LABEL_33;
    }
    HIBYTE(this[23].dwCheckPoint) = 1;
    if ( IsLicenseEnabled(L"PeerDist-Common-KMDriver-Enabled") )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          76,
          WPP_09eff81643953ecc218449769581d5a4_Traceguids,
          "Driver Layer Module");
      }
      v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[12].dwServiceType)(
             *(_QWORD *)&this[12].dwServiceType,
             (char *)&this[18],
             *(_QWORD *)&this[4].dwControlsAccepted);
      if ( v7 < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          return (unsigned int)v7;
        }
        v9 = 77;
        goto LABEL_33;
      }
      LOBYTE(this[23].dwWaitHint) = 1;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        78,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Publisher Module");
    }
    v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[8].dwServiceSpecificExitCode)(
           *(_QWORD *)&this[8].dwServiceSpecificExitCode,
           (char *)&this[18],
           *(_QWORD *)&this[4].dwControlsAccepted);
    if ( v7 >= 0 )
    {
      BYTE1(this[23].dwWaitHint) = 1;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          80,
          WPP_09eff81643953ecc218449769581d5a4_Traceguids,
          "Hosted Cache Manager");
      }
      v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[12].dwWaitHint)(
             *(_QWORD *)&this[12].dwWaitHint,
             (char *)&this[18],
             *(_QWORD *)&this[4].dwControlsAccepted);
      if ( v7 >= 0 )
      {
        BYTE1(this[24].dwServiceType) = 1;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            82,
            WPP_09eff81643953ecc218449769581d5a4_Traceguids,
            "Download Manager");
        }
        v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[9].dwWin32ExitCode)(
               *(_QWORD *)&this[9].dwWin32ExitCode,
               (char *)&this[18],
               *(_QWORD *)&this[4].dwControlsAccepted);
        if ( v7 >= 0 )
        {
          BYTE2(this[23].dwWaitHint) = 1;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              84,
              WPP_09eff81643953ecc218449769581d5a4_Traceguids,
              "Retrieval Manager");
          }
          v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[10].dwControlsAccepted)(
                 *(_QWORD *)&this[10].dwControlsAccepted,
                 (char *)&this[18],
                 *(_QWORD *)&this[4].dwControlsAccepted);
          if ( v7 >= 0 )
          {
            HIBYTE(this[23].dwWaitHint) = 1;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                86,
                WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                "Roaming Monitor Module");
            }
            v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[14].dwServiceSpecificExitCode)(
                   *(_QWORD *)&this[14].dwServiceSpecificExitCode,
                   (char *)&this[18],
                   *(_QWORD *)&this[4].dwControlsAccepted);
            if ( v7 >= 0 )
            {
              HIBYTE(this[24].dwServiceType) = 1;
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  88,
                  WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                  "Network Cost Monitor");
              }
              v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[17].dwCurrentState)(
                     *(_QWORD *)&this[17].dwCurrentState,
                     (char *)&this[18],
                     *(_QWORD *)&this[4].dwControlsAccepted);
              if ( v7 >= 0 )
              {
                BYTE2(this[24].dwCurrentState) = 1;
                if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 12),
                    90,
                    WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                    "RPC Server Module");
                }
                v7 = (***(__int64 (__fastcall ****)(_QWORD, char *, _QWORD))&this[11].dwCurrentState)(
                       *(_QWORD *)&this[11].dwCurrentState,
                       (char *)&this[18],
                       *(_QWORD *)&this[4].dwControlsAccepted);
                if ( v7 >= 0 )
                {
                  LOBYTE(this[24].dwServiceType) = 1;
                  v12 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&this[6].dwServiceType + 24LL))(*(_QWORD *)&this[6].dwServiceType);
                  v5 = v12;
                  if ( v12 >= 0 )
                  {
                    Event::Set(v6);
                    v13 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                    {
                      if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 12),
                          93,
                          WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                        v13 = WPP_GLOBAL_Control;
                      }
                      if ( v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
                      {
                        if ( (*((_DWORD *)v13 + 27) & 0x800) != 0 && *((_BYTE *)v13 + 105) >= 3u )
                        {
                          GetTickCount64();
                          WPP_SF_q(
                            *((_QWORD *)WPP_GLOBAL_Control + 12),
                            94,
                            WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                          v13 = WPP_GLOBAL_Control;
                        }
                        if ( v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                          && (*((_DWORD *)v13 + 27) & 0x800) != 0
                          && *((_BYTE *)v13 + 105) >= 3u )
                        {
                          WPP_SF_(*((_QWORD *)v13 + 12), 95, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
                        }
                      }
                    }
                  }
                  else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                         && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
                         && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 12),
                      92,
                      WPP_09eff81643953ecc218449769581d5a4_Traceguids,
                      (unsigned int)v12);
                  }
                  return (unsigned int)v5;
                }
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  return (unsigned int)v7;
                }
                v9 = 91;
              }
              else
              {
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                  || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
                {
                  return (unsigned int)v7;
                }
                v9 = 89;
              }
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
                || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                return (unsigned int)v7;
              }
              v9 = 87;
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              return (unsigned int)v7;
            }
            v9 = 85;
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            return (unsigned int)v7;
          }
          v9 = 83;
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          return (unsigned int)v7;
        }
        v9 = 81;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return (unsigned int)v7;
      }
      v9 = 79;
    }
LABEL_33:
    WPP_SF_d(*((_QWORD *)v8 + 12), v9, WPP_09eff81643953ecc218449769581d5a4_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 62, WPP_09eff81643953ecc218449769581d5a4_Traceguids, LastError);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004b74  push    rbx
0x180004b76  push    rbp
0x180004b77  push    rsi
0x180004b78  push    rdi
0x180004b79  push    r12
0x180004b7b  push    r13
0x180004b7d  push    r14
0x180004b7f  push    r15
0x180004b81  sub     rsp, 28h
0x180004b85  mov     rbx, rcx
0x180004b88  call    cs:__imp_GetTickCount64
0x180004b8e  mov     r14, rax
0x180004b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b98  lea     r12, WPP_GLOBAL_Control
0x180004b9f  lea     rdi, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004ba6  mov     r15d, 800h
0x180004bac  mov     sil, 3
0x180004baf  cmp     rcx, r12
0x180004bb2  jz      short loc_180004C23
0x180004bb4  test    [rcx+6Ch], r15d
0x180004bb8  jz      short loc_180004BD8
0x180004bba  cmp     [rcx+69h], sil
0x180004bbe  jb      short loc_180004BD8
0x180004bc0  mov     rcx, [rcx+60h]
0x180004bc4  mov     edx, 3Ah ; ':'
0x180004bc9  mov     r8, rdi
0x180004bcc  call    WPP_SF_
0x180004bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bd8  cmp     rcx, r12
0x180004bdb  jz      short loc_180004C23
0x180004bdd  test    [rcx+6Ch], r15d
0x180004be1  jz      short loc_180004C01
0x180004be3  cmp     [rcx+69h], sil
0x180004be7  jb      short loc_180004C01
0x180004be9  mov     rcx, [rcx+60h]
0x180004bed  mov     edx, 3Bh ; ';'
0x180004bf2  mov     r8, rdi
0x180004bf5  call    WPP_SF_
0x180004bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c01  cmp     rcx, r12
0x180004c04  jz      short loc_180004C23
0x180004c06  test    [rcx+6Ch], r15d
0x180004c0a  jz      short loc_180004C23
0x180004c0c  cmp     [rcx+69h], sil
0x180004c10  jb      short loc_180004C23
0x180004c12  mov     rcx, [rcx+60h]
0x180004c16  mov     edx, 3Ch ; '<'
0x180004c1b  mov     r8, rdi
0x180004c1e  call    WPP_SF_
0x180004c23  mov     r13d, 1
0x180004c29  mov     [rbx+8Ch], r13d
0x180004c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c37  cmp     rcx, r12
0x180004c3a  jz      short loc_180004C58
0x180004c3c  test    [rcx+6Ch], r15d
0x180004c40  jz      short loc_180004C58
0x180004c42  cmp     [rcx+69h], sil
0x180004c46  jb      short loc_180004C58
0x180004c48  mov     rcx, [rcx+60h]
0x180004c4c  lea     edx, [r13+3Ch]
0x180004c50  mov     r8, rdi
0x180004c53  call    WPP_SF_
0x180004c58  mov     rcx, [rbx+30h]; hServiceStatus
0x180004c5c  lea     rdx, [rbx+38h]; lpServiceStatus
0x180004c60  add     [rbx+4Ch], r13d
0x180004c64  mov     dword ptr [rdx+4], 2
0x180004c6b  mov     dword ptr [rbx+50h], 0EA60h
0x180004c72  call    cs:__imp_SetServiceStatus
0x180004c78  test    eax, eax
0x180004c7a  jnz     short loc_180004CC6
0x180004c7c  call    cs:__imp_GetLastError
0x180004c82  mov     ebx, eax
0x180004c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c8b  cmp     rcx, r12
0x180004c8e  jz      short loc_180004CB0
0x180004c90  test    [rcx+6Ch], r15d
0x180004c94  jz      short loc_180004CB0
0x180004c96  cmp     [rcx+69h], r13b
0x180004c9a  jb      short loc_180004CB0
0x180004c9c  mov     rcx, [rcx+60h]
0x180004ca0  mov     edx, 3Eh ; '>'
0x180004ca5  mov     r9d, eax
0x180004ca8  mov     r8, rdi
0x180004cab  call    WPP_SF_d
0x180004cb0  test    ebx, ebx
0x180004cb2  jle     loc_1800055D2
0x180004cb8  movzx   ebx, bx
0x180004cbb  or      ebx, 80070000h
0x180004cc1  jmp     loc_1800055D2
0x180004cc6  xor     eax, eax
0x180004cc8  mov     [rbx+298h], rax
0x180004ccf  mov     [rbx+2A0h], eax
0x180004cd5  mov     [rbx+2A4h], ax
0x180004cdc  mov     [rbx+2A6h], al
0x180004ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ce9  cmp     rcx, r12
0x180004cec  jz      short loc_180004D10
0x180004cee  test    [rcx+6Ch], r15d
0x180004cf2  jz      short loc_180004D10
0x180004cf4  cmp     [rcx+69h], sil
0x180004cf8  jb      short loc_180004D10
0x180004cfa  mov     rcx, [rcx+60h]
0x180004cfe  lea     edx, [rax+3Fh]
0x180004d01  lea     r9, aLoggingManager; "Logging Manager"
0x180004d08  mov     r8, rdi
0x180004d0b  call    WPP_SF_s
0x180004d10  mov     rcx, [rbx+180h]
0x180004d17  lea     rbp, [rbx+70h]
0x180004d1b  mov     r8, [rbp+8]
0x180004d1f  lea     rsi, [rbx+1F8h]
0x180004d26  mov     rdx, rsi
0x180004d29  mov     rax, [rcx]
0x180004d2c  mov     rax, [rax]
0x180004d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d34  mov     edi, eax
0x180004d36  test    eax, eax
0x180004d38  jns     short loc_180004D71
0x180004d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d41  cmp     rcx, r12
0x180004d44  jz      short loc_180004D6A
0x180004d46  test    [rcx+6Ch], r15d
0x180004d4a  jz      short loc_180004D6A
0x180004d4c  cmp     [rcx+69h], r13b
0x180004d50  jb      short loc_180004D6A
0x180004d52  mov     edx, 40h ; '@'
0x180004d57  mov     rcx, [rcx+60h]
0x180004d5b  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004d62  mov     r9d, edi
0x180004d65  call    WPP_SF_d
0x180004d6a  mov     eax, edi
0x180004d6c  jmp     loc_1800055D4
0x180004d71  mov     [rbx+2A2h], r13b
0x180004d78  mov     rcx, [rbx+1B0h]
0x180004d7f  mov     rax, [rcx]
0x180004d82  mov     rax, [rax+20h]
0x180004d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8b  mov     edi, eax
0x180004d8d  test    eax, eax
0x180004d8f  jns     short loc_180004DB0
0x180004d91  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d98  cmp     rcx, r12
0x180004d9b  jz      short loc_180004D6A
0x180004d9d  test    [rcx+6Ch], r15d
0x180004da1  jz      short loc_180004D6A
0x180004da3  cmp     [rcx+69h], r13b
0x180004da7  jb      short loc_180004D6A
0x180004da9  mov     edx, 41h ; 'A'
0x180004dae  jmp     short loc_180004D57
0x180004db0  mov     rcx, [rbx+90h]
0x180004db7  mov     dl, r13b
0x180004dba  mov     rax, [rcx]
0x180004dbd  mov     rax, [rax+20h]
0x180004dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dcd  cmp     rcx, r12
0x180004dd0  jz      short loc_180004DFA
0x180004dd2  test    [rcx+6Ch], r15d
0x180004dd6  jz      short loc_180004DFA
0x180004dd8  cmp     byte ptr [rcx+69h], 3
0x180004ddc  jb      short loc_180004DFA
0x180004dde  mov     rcx, [rcx+60h]
0x180004de2  lea     r9, ?s_rgszComponentNames@TnoService@@0QAY0DA@$$CBDA; "Configuration Manager"
0x180004de9  mov     edx, 42h ; 'B'
0x180004dee  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004df5  call    WPP_SF_s
0x180004dfa  mov     rcx, [rbx+90h]
0x180004e01  mov     rdx, rsi
0x180004e04  mov     r8, [rbx+78h]
0x180004e08  mov     rax, [rcx]
0x180004e0b  mov     rax, [rax]
0x180004e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e13  mov     edi, eax
0x180004e15  test    eax, eax
0x180004e17  jns     short loc_180004E47
0x180004e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e20  cmp     rcx, r12
0x180004e23  jz      loc_180004D6A
0x180004e29  test    [rcx+6Ch], r15d
0x180004e2d  jz      loc_180004D6A
0x180004e33  cmp     [rcx+69h], r13b
0x180004e37  jb      loc_180004D6A
0x180004e3d  mov     edx, 43h ; 'C'
0x180004e42  jmp     loc_180004D57
0x180004e47  mov     rcx, rbx; this
0x180004e4a  mov     [rbx+298h], r13b
0x180004e51  call    ?StartupConfigurationCheck@TnoService@@AEAAJXZ; TnoService::StartupConfigurationCheck(void)
0x180004e56  test    eax, eax
0x180004e58  js      loc_1800055D4
0x180004e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e65  cmp     rcx, r12
0x180004e68  jz      short loc_180004E92
0x180004e6a  test    [rcx+6Ch], r15d
0x180004e6e  jz      short loc_180004E92
0x180004e70  cmp     byte ptr [rcx+69h], 3
0x180004e74  jb      short loc_180004E92
0x180004e76  mov     rcx, [rcx+60h]
0x180004e7a  lea     r9, aPeerdistadLoad; "PeerDistAD Loader"
0x180004e81  mov     edx, 44h ; 'D'
0x180004e86  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004e8d  call    WPP_SF_s
0x180004e92  mov     rcx, [rbx+1C8h]
0x180004e99  mov     rdx, rsi
0x180004e9c  mov     r8, [rbx+78h]
0x180004ea0  mov     rax, [rcx]
0x180004ea3  mov     rax, [rax]
0x180004ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eab  mov     edi, eax
0x180004ead  test    eax, eax
0x180004eaf  jns     short loc_180004EDF
0x180004eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eb8  cmp     rcx, r12
0x180004ebb  jz      loc_180004D6A
0x180004ec1  test    [rcx+6Ch], r15d
0x180004ec5  jz      loc_180004D6A
0x180004ecb  cmp     [rcx+69h], r13b
0x180004ecf  jb      loc_180004D6A
0x180004ed5  mov     edx, 45h ; 'E'
0x180004eda  jmp     loc_180004D57
0x180004edf  mov     [rbx+2A5h], r13b
0x180004ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eed  cmp     rcx, r12
0x180004ef0  jz      short loc_180004F1A
0x180004ef2  test    [rcx+6Ch], r15d
0x180004ef6  jz      short loc_180004F1A
0x180004ef8  cmp     byte ptr [rcx+69h], 3
0x180004efc  jb      short loc_180004F1A
0x180004efe  mov     rcx, [rcx+60h]
0x180004f02  lea     r9, aCacheManager; "Cache Manager"
0x180004f09  mov     edx, 46h ; 'F'
0x180004f0e  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004f15  call    WPP_SF_s
0x180004f1a  mov     rcx, [rbx+0A8h]
0x180004f21  mov     rdx, rsi
0x180004f24  mov     r8, [rbx+78h]
0x180004f28  mov     rax, [rcx]
0x180004f2b  mov     rax, [rax]
0x180004f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f33  mov     edi, eax
0x180004f35  test    eax, eax
0x180004f37  jns     short loc_180004F67
0x180004f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f40  cmp     rcx, r12
0x180004f43  jz      loc_180004D6A
0x180004f49  test    [rcx+6Ch], r15d
0x180004f4d  jz      loc_180004D6A
0x180004f53  cmp     [rcx+69h], r13b
0x180004f57  jb      loc_180004D6A
0x180004f5d  mov     edx, 47h ; 'G'
0x180004f62  jmp     loc_180004D57
0x180004f67  mov     [rbx+299h], r13b
0x180004f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f75  cmp     rcx, r12
0x180004f78  jz      short loc_180004FA2
0x180004f7a  test    [rcx+6Ch], r15d
0x180004f7e  jz      short loc_180004FA2
0x180004f80  cmp     byte ptr [rcx+69h], 3
0x180004f84  jb      short loc_180004FA2
0x180004f86  mov     rcx, [rcx+60h]
0x180004f8a  lea     r9, aDiscoveryManag; "Discovery Manager"
0x180004f91  mov     edx, 48h ; 'H'
0x180004f96  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180004f9d  call    WPP_SF_s
0x180004fa2  mov     rcx, [rbx+0C0h]
0x180004fa9  mov     rdx, rsi
0x180004fac  mov     r8, [rbx+78h]
0x180004fb0  mov     rax, [rcx]
0x180004fb3  mov     rax, [rax]
0x180004fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fbb  mov     edi, eax
0x180004fbd  test    eax, eax
0x180004fbf  jns     short loc_180004FEF
0x180004fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fc8  cmp     rcx, r12
0x180004fcb  jz      loc_180004D6A
0x180004fd1  test    [rcx+6Ch], r15d
0x180004fd5  jz      loc_180004D6A
0x180004fdb  cmp     [rcx+69h], r13b
0x180004fdf  jb      loc_180004D6A
0x180004fe5  mov     edx, 49h ; 'I'
0x180004fea  jmp     loc_180004D57
0x180004fef  mov     [rbx+29Ah], r13b
0x180004ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ffd  cmp     rcx, r12
0x180005000  jz      short loc_18000502A
0x180005002  test    [rcx+6Ch], r15d
0x180005006  jz      short loc_18000502A
0x180005008  cmp     byte ptr [rcx+69h], 3
0x18000500c  jb      short loc_18000502A
0x18000500e  mov     rcx, [rcx+60h]
0x180005012  lea     r9, aSecurityManage; "Security Manager"
0x180005019  mov     edx, 4Ah ; 'J'
0x18000501e  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180005025  call    WPP_SF_s
0x18000502a  mov     rcx, [rbx+0D8h]
0x180005031  mov     rdx, rsi
0x180005034  mov     r8, [rbx+78h]
0x180005038  mov     rax, [rcx]
0x18000503b  mov     rax, [rax]
0x18000503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005043  mov     edi, eax
  ... truncated ...
```
