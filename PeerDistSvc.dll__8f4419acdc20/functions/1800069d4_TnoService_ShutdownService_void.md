# TnoService::ShutdownService(void)

- ea: `0x1800069d4`
- end: `0x180007db1`
- name: `?ShutdownService@TnoService@@QEAAJXZ`
- size: `5085`
- prototype: `__int64 __fastcall(TnoService *__hidden this)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000594c`
- `0x180007fe0`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x18000573c`
- `0x1800069d4`
- `0x18000801c`
- `0x18000818c`
- `0x180008218`
- `0x180008290`
- `0x1800082d0`
- `0x180008360`
- `0x1800083bc`
- `0x180018efc`
- `0x18001911c`
- `0x180113d84`
- `0x180114308`
- `0x180114848`
- `0x18012df70`
- `0x180144882`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800077ca`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800077ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800078a0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006bb7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a29`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007d35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006a29`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007d35`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000780f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000780f`
- `ntdll!EtwEventUnregister` at `0x180007cb1`
- `ntdll!EtwEventUnregister` at `0x180007cb1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180007c0b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180007c0b`

## string_xrefs

- `0x1800075f5`: `Configuration Manager`
- `0x18000788a`: `Configuration Manager`
- `0x180007337`: `Cache Manager`
- `0x180006e94`: `Security Manager`
- `0x1800073f6`: `Hosted Cache Manager`
- `0x1800076a6`: `Network Configuration Monitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TnoService::ShutdownService(TnoService *this)
{
  TnoService *v1; // rbx
  unsigned int v2; // r15d
  DWORD v3; // r12d
  CHostedCacheMsgEncoding *v4; // rcx
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  struct ITnoCfgMgr *v20; // r13
  int v21; // eax
  unsigned int v22; // r13d
  CHostedCacheMsgEncoding *v23; // rcx
  int v24; // eax
  int v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  unsigned int v28; // r13d
  unsigned __int64 v29; // rcx
  __int64 v30; // rax
  DWORD v31; // eax
  char v32; // al
  unsigned int v33; // eax
  TnoService *v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // eax
  CHostedCacheMsgEncoding *v37; // rcx
  unsigned int v38; // eax
  unsigned int v39; // eax
  CHostedCacheMsgEncoding *v40; // rcx
  DWORD v42; // [rsp+30h] [rbp-D0h]
  const char *v43; // [rsp+30h] [rbp-D0h]
  TnoService *v44; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v45[4]; // [rsp+40h] [rbp-C0h] BYREF
  ULONGLONG TickCount64; // [rsp+80h] [rbp-80h]
  _BYTE v47[24]; // [rsp+88h] [rbp-78h] BYREF
  HANDLE Handles[16]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = this;
  v44 = this;
  memset_0(Handles, 0, 0x78u);
  memset(v45, 0, 60);
  TickCount64 = GetTickCount64();
  v2 = 1;
  InCritSec::InCritSec((InCritSec *)v47, v1, 1);
  if ( *((_DWORD *)v1 + 15) == 1 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 99, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
    }
    goto LABEL_334;
  }
  v42 = 0;
  v3 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 100, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v4 + 27) & 0x800) != 0 && *((_BYTE *)v4 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v4 + 12), 101, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v4 + 27) & 0x800) != 0
        && *((_BYTE *)v4 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v4 + 12), 102, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
        v4 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( *((_QWORD *)v1 + 48) && !*((_BYTE *)v1 + 137) )
  {
    if ( v4 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v4 + 27) & 0x800) != 0
      && *((_BYTE *)v4 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v4 + 12), 103, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 48) + 40LL))(*((_QWORD *)v1 + 48));
  }
  *((_DWORD *)v1 + 15) = 3;
  if ( !*((_QWORD *)v1 + 6) )
    goto LABEL_35;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 104, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
  }
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v1 + 6), (LPSERVICE_STATUS)v1 + 2) )
    goto LABEL_35;
  LastError = GetLastError();
  v42 = LastError;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 105, WPP_09eff81643953ecc218449769581d5a4_Traceguids, LastError);
LABEL_35:
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)v1 + 21);
  if ( v7 && *((_BYTE *)v1 + 665) )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v7 + 120LL))(*((_QWORD *)v1 + 21));
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)v1 + 42) && *((_BYTE *)v1 + 668) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 106, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Driver Layer Module");
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 42) + 8LL))(
           *((_QWORD *)v1 + 42),
           25000,
           *((_QWORD *)v1 + 44),
           0);
    if ( v8 >= 0 )
    {
      LODWORD(v45[0]) = 4;
      Handles[0] = *((HANDLE *)v1 + 44);
      v3 = 1;
      *((_BYTE *)v1 + 668) = 0;
LABEL_51:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_52;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        107,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v8);
      goto LABEL_51;
    }
  }
LABEL_52:
  if ( *((_QWORD *)v1 + 39) && *((_BYTE *)v1 + 672) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 108, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "RPC Server Module");
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 39) + 8LL))(
           *((_QWORD *)v1 + 39),
           25000,
           *((_QWORD *)v1 + 41),
           0);
    if ( v9 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 8;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 41);
      *((_BYTE *)v1 + 672) = 0;
LABEL_64:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_65;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        109,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v9);
      goto LABEL_64;
    }
  }
LABEL_65:
  if ( *((_QWORD *)v1 + 60) && *((_BYTE *)v1 + 678) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 110, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Network Cost Monitor");
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 60) + 8LL))(
            *((_QWORD *)v1 + 60),
            25000,
            *((_QWORD *)v1 + 62),
            0);
    if ( v10 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 14;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 62);
      *((_BYTE *)v1 + 678) = 0;
LABEL_77:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_78;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        111,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v10);
      goto LABEL_77;
    }
  }
LABEL_78:
  if ( *((_QWORD *)v1 + 27) && *((_BYTE *)v1 + 667) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 112, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Security Manager");
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 27) + 8LL))(
            *((_QWORD *)v1 + 27),
            25000,
            *((_QWORD *)v1 + 29),
            0);
    if ( v11 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 3;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 29);
      *((_BYTE *)v1 + 667) = 0;
LABEL_90:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_91;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        113,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v11);
      goto LABEL_90;
    }
  }
LABEL_91:
  if ( *((_QWORD *)v1 + 51) && *((_BYTE *)v1 + 675) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 114, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Roaming Monitor Module");
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 51) + 8LL))(
            *((_QWORD *)v1 + 51),
            25000,
            *((_QWORD *)v1 + 53),
            0);
    if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147023899 )
    {
      *((_DWORD *)v45 + v3) = 11;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 53);
      *((_BYTE *)v1 + 675) = 0;
      goto LABEL_104;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 115, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v12);
LABEL_104:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)v1 + 36) && *((_BYTE *)v1 + 671) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 116, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Retrieval Manager");
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 36) + 8LL))(
            *((_QWORD *)v1 + 36),
            25000,
            *((_QWORD *)v1 + 38),
            0);
    if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147023899 )
    {
      *((_DWORD *)v45 + v3) = 7;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 38);
      *((_BYTE *)v1 + 671) = 0;
      goto LABEL_118;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 117, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v13);
LABEL_118:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)v1 + 30) && *((_BYTE *)v1 + 669) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 118, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Publisher Module");
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 30) + 8LL))(
            *((_QWORD *)v1 + 30),
            25000,
            *((_QWORD *)v1 + 32),
            0);
    if ( v14 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 5;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 32);
      *((_BYTE *)v1 + 669) = 0;
LABEL_131:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_132;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        119,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v14);
      goto LABEL_131;
    }
  }
LABEL_132:
  if ( *((_QWORD *)v1 + 33) && *((_BYTE *)v1 + 670) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 120, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Download Manager");
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 33) + 8LL))(
            *((_QWORD *)v1 + 33),
            25000,
            *((_QWORD *)v1 + 35),
            0);
    if ( v15 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 6;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 35);
      *((_BYTE *)v1 + 670) = 0;
LABEL_144:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_145;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        121,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v15);
      goto LABEL_144;
    }
  }
LABEL_145:
  if ( *((_QWORD *)v1 + 24) && *((_BYTE *)v1 + 666) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 122, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Discovery Manager");
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 24) + 8LL))(
            *((_QWORD *)v1 + 24),
            25000,
            *((_QWORD *)v1 + 26),
            0);
    if ( (int)(v16 + 0x80000000) < 0 || v16 == -2147483638 )
    {
      *((_DWORD *)v45 + v3) = 2;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 26);
      *((_BYTE *)v1 + 666) = 0;
      goto LABEL_158;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 123, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v16);
LABEL_158:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)v1 + 21) && *((_BYTE *)v1 + 665) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 124, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Cache Manager");
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 21) + 8LL))(
            *((_QWORD *)v1 + 21),
            25000,
            *((_QWORD *)v1 + 23),
            0);
    if ( v17 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 1;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 23);
      *((_BYTE *)v1 + 665) = 0;
LABEL_171:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_172;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        125,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v17);
      goto LABEL_171;
    }
  }
LABEL_172:
  if ( *((_QWORD *)v1 + 45) && *((_BYTE *)v1 + 673) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 126, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Hosted Cache Manager");
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 45) + 8LL))(
            *((_QWORD *)v1 + 45),
            25000,
            *((_QWORD *)v1 + 47),
            0);
    if ( (int)(v18 + 0x80000000) < 0 || v18 == -2147023899 )
    {
      *((_DWORD *)v45 + v3) = 9;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 47);
      *((_BYTE *)v1 + 673) = 0;
      goto LABEL_185;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 127, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v18);
LABEL_185:
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( *((_QWORD *)v1 + 57) && *((_BYTE *)v1 + 677) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(*((_QWORD *)v6 + 12), 128, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "PeerDistAD Loader");
    }
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 57) + 8LL))(
            *((_QWORD *)v1 + 57),
            25000,
            *((_QWORD *)v1 + 59),
            0);
    if ( v19 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 13;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 59);
      *((_BYTE *)v1 + 677) = 0;
LABEL_198:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_199;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        129,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v19);
      goto LABEL_198;
    }
  }
LABEL_199:
  v20 = (struct ITnoCfgMgr *)*((_QWORD *)v1 + 18);
  if ( !v20 || !*((_BYTE *)v1 + 664) )
    goto LABEL_222;
  PeerDistSvcStopTimer();
  v21 = PeerDistSvcPersistStoredPerfCountersInternal(v20);
  v22 = v21;
  if ( v21 >= 0 )
    goto LABEL_210;
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_215;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      42,
      WPP_c106f1c2962a3571e634919788e67001_Traceguids,
      (unsigned int)v21);
    v23 = WPP_GLOBAL_Control;
  }
  if ( v23 == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    goto LABEL_215;
  if ( (*((_DWORD *)v23 + 27) & 0x800) != 0 && *((_BYTE *)v23 + 105) )
  {
    WPP_SF_d(*((_QWORD *)v23 + 12), 130, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v22);
LABEL_210:
    v23 = WPP_GLOBAL_Control;
  }
  if ( v23 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v23 + 27) & 0x800) != 0
    && *((_BYTE *)v23 + 105) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)v23 + 12), 131, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Configuration Manager");
  }
LABEL_215:
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 18) + 8LL))(
          *((_QWORD *)v1 + 18),
          25000,
          *((_QWORD *)v1 + 20),
          0);
  if ( v24 >= 0 )
  {
    *((_DWORD *)v45 + v3) = 0;
    Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 20);
    *((_BYTE *)v1 + 664) = 0;
LABEL_221:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_222;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      132,
      WPP_09eff81643953ecc218449769581d5a4_Traceguids,
      (unsigned int)v24);
    goto LABEL_221;
  }
LABEL_222:
  if ( *((_QWORD *)v1 + 54) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 3u )
    {
      WPP_SF_s(
        *((_QWORD *)v6 + 12),
        133,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        "Network Configuration Monitor");
    }
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 54) + 8LL))(
            *((_QWORD *)v1 + 54),
            25000,
            *((_QWORD *)v1 + 56),
            0);
    if ( v25 >= 0 )
    {
      *((_DWORD *)v45 + v3) = 12;
      Handles[v3++] = (HANDLE)*((_QWORD *)v1 + 56);
      *((_BYTE *)v1 + 676) = 0;
LABEL_233:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_234;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        134,
        WPP_09eff81643953ecc218449769581d5a4_Traceguids,
        (unsigned int)v25);
      goto LABEL_233;
    }
  }
LABEL_234:
  if ( *((_QWORD *)v1 + 48) && !*((_BYTE *)v1 + 137) )
  {
    if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v6 + 27) & 0x800) != 0
      && *((_BYTE *)v6 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v6 + 12), 135, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 48) + 48LL))(*((_QWORD *)v1 + 48));
    v6 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    while ( 1 )
    {
LABEL_242:
      if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v6 + 27) & 0x800) != 0
        && *((_BYTE *)v6 + 105) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)v6 + 12), 136, WPP_09eff81643953ecc218449769581d5a4_Traceguids, 5000);
      }
      v26 = WaitForMultipleObjectsEx(v3, Handles, 1, 0x1388u, 0);
      v42 = v26;
      if ( v26 != -1 )
        break;
      v27 = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 137, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v27);
      }
      Sleep(0x64u);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v26 == 258 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 138, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      }
      v28 = 0;
      while ( 1 )
      {
        v29 = v28 % 0xFuLL;
        if ( *((_DWORD *)v45 + v29) >= 0xFu )
          v30 = 15;
        else
          v30 = *((unsigned int *)v45 + v29);
        v43 = &TnoService::s_rgszComponentNames[48 * v30];
        v31 = WaitForSingleObject(Handles[v29], 0);
        if ( v31 == 258 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u )
          {
            goto LABEL_272;
          }
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 12), 139, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v43);
        }
        else if ( v31 == -1 )
        {
          v32 = GetLastError();
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_272;
          }
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            140,
            (unsigned int)WPP_09eff81643953ecc218449769581d5a4_Traceguids,
            (_DWORD)v43,
            v32);
        }
        v6 = WPP_GLOBAL_Control;
LABEL_272:
        if ( ++v28 >= v3 )
          goto LABEL_242;
      }
    }
    v6 = WPP_GLOBAL_Control;
    v1 = v44;
  }
  if ( !*((_QWORD *)v1 + 48) || !*((_BYTE *)v1 + 674) )
    goto LABEL_289;
  if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v6 + 27) & 0x800) != 0
    && *((_BYTE *)v6 + 105) >= 3u )
  {
    WPP_SF_s(*((_QWORD *)v6 + 12), 141, WPP_09eff81643953ecc218449769581d5a4_Traceguids, "Logging Manager");
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)v1 + 48) + 8LL))(
          *((_QWORD *)v1 + 48),
          25000,
          *((_QWORD *)v1 + 50),
          0);
  if ( (int)(v33 + 0x80000000) < 0 || v33 == -2147023899 )
  {
    ObjectHandle::Wait((TnoService *)((char *)v1 + 392), 0xFFFFFFFF);
    *((_BYTE *)v1 + 674) = 0;
    goto LABEL_288;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
LABEL_289:
      if ( v6 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v6 + 27) & 0x800) != 0
        && *((_BYTE *)v6 + 105) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)v6 + 12), 143, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v42);
      }
      goto LABEL_293;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 142, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v33);
LABEL_288:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_289;
  }
LABEL_293:
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 144, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 152));
  v34 = (TnoService *)*((_QWORD *)v1 + 21);
  *((_QWORD *)v1 + 21) = 0;
  v44 = v34;
  SmartPointer<CHostedCacheListManager>::Release(&v44);
  ObjectHandle::Close((TnoService *)((char *)v1 + 176));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 480, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 488));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 192, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 200));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 216, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 224));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 336, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 344));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 240, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 248));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 264, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 272));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 360, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 368));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 408, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 416));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 288, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 296));
  std::auto_ptr<IPeerDiscovery>::reset((char *)v1 + 312, 0);
  ObjectHandle::Close((TnoService *)((char *)v1 + 320));
  *((_QWORD *)v1 + 48) = 0;
  ObjectHandle::Close((TnoService *)((char *)v1 + 392));
  v35 = _InterlockedExchange64((volatile __int64 *)&IPeerDistADLoader::s_pSingletonInstance, 0);
  if ( v35 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 24LL))(v35, 1);
  *((_QWORD *)v1 + 57) = 0;
  ObjectHandle::Close((TnoService *)((char *)v1 + 464));
  ObjectHandle::Close((TnoService *)((char *)v1 + 112));
  if ( *((_BYTE *)v1 + 136) )
  {
    PeerDistSvcDeletePerfInstance();
    if ( byte_1801A77A8 )
    {
      if ( PeerDistSvc )
      {
        PerfStopProvider(PeerDistSvc);
        PeerDistSvc = 0;
      }
      byte_1801A77A8 = 0;
    }
    else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 144, WPP_09eff81643953ecc218449769581d5a4_Traceguids, 2147946454LL);
    }
  }
  v36 = McGenEventUnregister_EtwEventUnregister(MICROSOFT_PEERDIST_EVENTS_PROVIDER_Context);
  if ( v36 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 145, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v36);
    }
  }
  if ( (Microsoft_Windows_BranchCacheMonitoringEnableBits & 1) != 0 )
    McTemplateU0zq_EtwEventWriteTransfer(v37, ProviderDepartureEvent);
  v38 = McGenEventUnregister_EtwEventUnregister(&MICROSOFT_PEERDIST_MONITORING_PROVIDER_Context);
  if ( v38
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 146, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v38);
  }
  v39 = EtwEventUnregister(Microsoft_Windows_Networking_CorrelationHandle);
  Microsoft_Windows_Networking_CorrelationHandle = 0;
  if ( v39
    && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 147, WPP_09eff81643953ecc218449769581d5a4_Traceguids, v39);
  }
  PeerDistTelemetryShutdown();
  v40 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 148, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      v40 = WPP_GLOBAL_Control;
    }
    if ( v40 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v40 + 27) & 0x800) != 0 && *((_BYTE *)v40 + 105) >= 3u )
      {
        GetTickCount64();
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 149, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
        v40 = WPP_GLOBAL_Control;
      }
      if ( v40 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)v40 + 27) & 0x800) != 0
        && *((_BYTE *)v40 + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)v40 + 12), 150, WPP_09eff81643953ecc218449769581d5a4_Traceguids);
      }
    }
  }
  v2 = 0;
LABEL_334:
  InCritSec::~InCritSec((InCritSec *)v47);
  return v2;
}

```

## disassembly

```asm
0x1800069d4  push    rbp
0x1800069d6  push    rbx
0x1800069d7  push    rsi
0x1800069d8  push    rdi
0x1800069d9  push    r12
0x1800069db  push    r13
0x1800069dd  push    r14
0x1800069df  push    r15
0x1800069e1  lea     rbp, [rsp-38h]
0x1800069e6  sub     rsp, 138h
0x1800069ed  mov     rax, cs:__security_cookie
0x1800069f4  xor     rax, rsp
0x1800069f7  mov     [rbp+70h+var_50], rax
0x1800069fb  mov     rbx, rcx
0x1800069fe  mov     [rsp+170h+var_138], rcx
0x180006a03  xor     edx, edx; Val
0x180006a05  lea     r8d, [rdx+78h]; Size
0x180006a09  lea     rcx, [rbp+70h+Handles]; void *
0x180006a0d  call    memset_0
0x180006a12  xorps   xmm0, xmm0
0x180006a15  movups  [rsp+170h+var_130], xmm0
0x180006a1a  movups  [rsp+170h+var_120], xmm0
0x180006a1f  movups  xmmword ptr [rsp+170h+var_110], xmm0
0x180006a24  movups  xmmword ptr [rsp+170h+var_110+0Ch], xmm0
0x180006a29  call    cs:__imp_GetTickCount64
0x180006a2f  mov     [rbp+70h+var_F0], rax
0x180006a33  mov     r15d, 1
0x180006a39  mov     r8b, r15b; bool
0x180006a3c  mov     rdx, rbx; struct CritSec *
0x180006a3f  lea     rcx, [rbp+70h+var_E8]; this
0x180006a43  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x180006a48  nop
0x180006a49  cmp     [rbx+3Ch], r15d
0x180006a4d  jnz     short loc_180006A97
0x180006a4f  lea     rsi, WPP_GLOBAL_Control
0x180006a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a5d  cmp     rcx, rsi
0x180006a60  jz      loc_180007D85
0x180006a66  mov     edi, 800h
0x180006a6b  test    [rcx+6Ch], edi
0x180006a6e  jz      loc_180007D85
0x180006a74  cmp     [rcx+69h], r15b
0x180006a78  jb      loc_180007D85
0x180006a7e  lea     edx, [r15+62h]
0x180006a82  lea     r8, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180006a89  mov     rcx, [rcx+60h]
0x180006a8d  call    WPP_SF_
0x180006a92  jmp     loc_180007D85
0x180006a97  mov     dword ptr [rsp+170h+var_140], 0
0x180006a9f  xor     r12d, r12d
0x180006aa2  lea     rsi, WPP_GLOBAL_Control
0x180006aa9  mov     edi, 800h
0x180006aae  lea     r14, WPP_09eff81643953ecc218449769581d5a4_Traceguids
0x180006ab5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006abc  cmp     rcx, rsi
0x180006abf  jz      short loc_180006B34
0x180006ac1  test    [rcx+6Ch], edi
0x180006ac4  jz      short loc_180006AE4
0x180006ac6  cmp     byte ptr [rcx+69h], 3
0x180006aca  jb      short loc_180006AE4
0x180006acc  lea     edx, [r12+64h]
0x180006ad1  mov     r8, r14
0x180006ad4  mov     rcx, [rcx+60h]
0x180006ad8  call    WPP_SF_
0x180006add  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ae4  cmp     rcx, rsi
0x180006ae7  jz      short loc_180006B34
0x180006ae9  test    [rcx+6Ch], edi
0x180006aec  jz      short loc_180006B0C
0x180006aee  cmp     byte ptr [rcx+69h], 3
0x180006af2  jb      short loc_180006B0C
0x180006af4  mov     edx, 65h ; 'e'
0x180006af9  mov     r8, r14
0x180006afc  mov     rcx, [rcx+60h]
0x180006b00  call    WPP_SF_
0x180006b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b0c  cmp     rcx, rsi
0x180006b0f  jz      short loc_180006B34
0x180006b11  test    [rcx+6Ch], edi
0x180006b14  jz      short loc_180006B34
0x180006b16  cmp     byte ptr [rcx+69h], 3
0x180006b1a  jb      short loc_180006B34
0x180006b1c  mov     edx, 66h ; 'f'
0x180006b21  mov     r8, r14
0x180006b24  mov     rcx, [rcx+60h]
0x180006b28  call    WPP_SF_
0x180006b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b34  cmp     [rbx+180h], r12
0x180006b3b  jz      short loc_180006B7A
0x180006b3d  cmp     [rbx+89h], r12b
0x180006b44  jnz     short loc_180006B7A
0x180006b46  cmp     rcx, rsi
0x180006b49  jz      short loc_180006B67
0x180006b4b  test    [rcx+6Ch], edi
0x180006b4e  jz      short loc_180006B67
0x180006b50  cmp     byte ptr [rcx+69h], 4
0x180006b54  jb      short loc_180006B67
0x180006b56  mov     edx, 67h ; 'g'
0x180006b5b  mov     r8, r14
0x180006b5e  mov     rcx, [rcx+60h]
0x180006b62  call    WPP_SF_
0x180006b67  mov     rcx, [rbx+180h]
0x180006b6e  mov     rax, [rcx]
0x180006b71  mov     rax, [rax+28h]
0x180006b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7a  mov     dword ptr [rbx+3Ch], 3
0x180006b81  cmp     [rbx+30h], r12
0x180006b85  jz      short loc_180006BF6
0x180006b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b8e  cmp     rcx, rsi
0x180006b91  jz      short loc_180006BAF
0x180006b93  test    [rcx+6Ch], edi
0x180006b96  jz      short loc_180006BAF
0x180006b98  cmp     byte ptr [rcx+69h], 4
0x180006b9c  jb      short loc_180006BAF
0x180006b9e  mov     edx, 68h ; 'h'
0x180006ba3  mov     r8, r14
0x180006ba6  mov     rcx, [rcx+60h]
0x180006baa  call    WPP_SF_
0x180006baf  lea     rdx, [rbx+38h]; lpServiceStatus
0x180006bb3  mov     rcx, [rbx+30h]; hServiceStatus
0x180006bb7  call    cs:__imp_SetServiceStatus
0x180006bbd  test    eax, eax
0x180006bbf  jnz     short loc_180006BF6
0x180006bc1  call    cs:__imp_GetLastError
0x180006bc7  mov     dword ptr [rsp+170h+var_140], eax
0x180006bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bd2  cmp     rcx, rsi
0x180006bd5  jz      short loc_180006BFD
0x180006bd7  test    [rcx+6Ch], edi
0x180006bda  jz      short loc_180006BFD
0x180006bdc  cmp     [rcx+69h], r15b
0x180006be0  jb      short loc_180006BFD
0x180006be2  mov     edx, 69h ; 'i'
0x180006be7  mov     r9d, eax
0x180006bea  mov     r8, r14
0x180006bed  mov     rcx, [rcx+60h]
0x180006bf1  call    WPP_SF_d
0x180006bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bfd  mov     rdx, [rbx+0A8h]
0x180006c04  test    rdx, rdx
0x180006c07  jz      short loc_180006C28
0x180006c09  cmp     [rbx+299h], r12b
0x180006c10  jz      short loc_180006C28
0x180006c12  mov     rax, [rdx]
0x180006c15  mov     rcx, rdx
0x180006c18  mov     rax, [rax+78h]
0x180006c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c28  lea     r13, [rbx+150h]
0x180006c2f  cmp     [r13+0], r12
0x180006c33  jz      loc_180006CE2
0x180006c39  cmp     [rbx+29Ch], r12b
0x180006c40  jz      loc_180006CE2
0x180006c46  cmp     rcx, rsi
0x180006c49  jz      short loc_180006C6E
0x180006c4b  test    [rcx+6Ch], edi
0x180006c4e  jz      short loc_180006C6E
0x180006c50  cmp     byte ptr [rcx+69h], 3
0x180006c54  jb      short loc_180006C6E
0x180006c56  mov     edx, 6Ah ; 'j'
0x180006c5b  lea     r9, aDriverLayerMod; "Driver Layer Module"
0x180006c62  mov     r8, r14
0x180006c65  mov     rcx, [rcx+60h]
0x180006c69  call    WPP_SF_s
0x180006c6e  mov     rcx, [r13+0]
0x180006c72  mov     rax, [rcx]
0x180006c75  xor     r9d, r9d
0x180006c78  mov     r8, [rbx+160h]
0x180006c7f  mov     edx, 61A8h
0x180006c84  mov     rax, [rax+8]
0x180006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8d  test    eax, eax
0x180006c8f  js      short loc_180006CB0
0x180006c91  mov     dword ptr [rsp+170h+var_130], 4
0x180006c99  mov     rax, [rbx+160h]
0x180006ca0  mov     [rbp+70h+Handles], rax
0x180006ca4  mov     r12d, r15d
0x180006ca7  mov     byte ptr [rbx+29Ch], 0
0x180006cae  jmp     short loc_180006CDB
0x180006cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cb7  cmp     rcx, rsi
0x180006cba  jz      short loc_180006CE2
0x180006cbc  test    [rcx+6Ch], edi
0x180006cbf  jz      short loc_180006CE2
0x180006cc1  cmp     [rcx+69h], r15b
0x180006cc5  jb      short loc_180006CE2
0x180006cc7  mov     edx, 6Bh ; 'k'
0x180006ccc  mov     r9d, eax
0x180006ccf  mov     r8, r14
0x180006cd2  mov     rcx, [rcx+60h]
0x180006cd6  call    WPP_SF_d
0x180006cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ce2  lea     r13, [rbx+138h]
0x180006ce9  cmp     qword ptr [r13+0], 0
0x180006cee  jz      loc_180006DA1
0x180006cf4  cmp     byte ptr [rbx+2A0h], 0
0x180006cfb  jz      loc_180006DA1
0x180006d01  cmp     rcx, rsi
0x180006d04  jz      short loc_180006D29
0x180006d06  test    [rcx+6Ch], edi
0x180006d09  jz      short loc_180006D29
0x180006d0b  cmp     byte ptr [rcx+69h], 3
0x180006d0f  jb      short loc_180006D29
0x180006d11  mov     edx, 6Ch ; 'l'
0x180006d16  lea     r9, aRpcServerModul; "RPC Server Module"
0x180006d1d  mov     r8, r14
0x180006d20  mov     rcx, [rcx+60h]
0x180006d24  call    WPP_SF_s
0x180006d29  mov     rcx, [r13+0]
0x180006d2d  mov     rax, [rcx]
0x180006d30  xor     r9d, r9d
0x180006d33  mov     r8, [rbx+148h]
0x180006d3a  mov     edx, 61A8h
0x180006d3f  mov     rax, [rax+8]
0x180006d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d48  test    eax, eax
0x180006d4a  js      short loc_180006D6F
0x180006d4c  mov     ecx, r12d
0x180006d4f  mov     dword ptr [rsp+rcx*4+170h+var_130], 8
0x180006d57  mov     rax, [rbx+148h]
0x180006d5e  mov     [rbp+rcx*8+70h+Handles], rax
0x180006d63  add     r12d, r15d
0x180006d66  mov     byte ptr [rbx+2A0h], 0
0x180006d6d  jmp     short loc_180006D9A
0x180006d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d76  cmp     rcx, rsi
0x180006d79  jz      short loc_180006DA1
0x180006d7b  test    [rcx+6Ch], edi
0x180006d7e  jz      short loc_180006DA1
0x180006d80  cmp     [rcx+69h], r15b
0x180006d84  jb      short loc_180006DA1
0x180006d86  mov     edx, 6Dh ; 'm'
0x180006d8b  mov     r9d, eax
0x180006d8e  mov     r8, r14
0x180006d91  mov     rcx, [rcx+60h]
0x180006d95  call    WPP_SF_d
0x180006d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006da1  lea     r13, [rbx+1E0h]
0x180006da8  cmp     qword ptr [r13+0], 0
0x180006dad  jz      loc_180006E60
0x180006db3  cmp     byte ptr [rbx+2A6h], 0
0x180006dba  jz      loc_180006E60
0x180006dc0  cmp     rcx, rsi
0x180006dc3  jz      short loc_180006DE8
0x180006dc5  test    [rcx+6Ch], edi
0x180006dc8  jz      short loc_180006DE8
0x180006dca  cmp     byte ptr [rcx+69h], 3
0x180006dce  jb      short loc_180006DE8
0x180006dd0  mov     edx, 6Eh ; 'n'
0x180006dd5  lea     r9, aNetworkCostMon; "Network Cost Monitor"
0x180006ddc  mov     r8, r14
0x180006ddf  mov     rcx, [rcx+60h]
0x180006de3  call    WPP_SF_s
0x180006de8  mov     rcx, [r13+0]
0x180006dec  mov     rax, [rcx]
0x180006def  xor     r9d, r9d
0x180006df2  mov     r8, [rbx+1F0h]
0x180006df9  mov     edx, 61A8h
0x180006dfe  mov     rax, [rax+8]
0x180006e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e07  test    eax, eax
0x180006e09  js      short loc_180006E2E
0x180006e0b  mov     ecx, r12d
0x180006e0e  mov     dword ptr [rsp+rcx*4+170h+var_130], 0Eh
0x180006e16  mov     rax, [rbx+1F0h]
0x180006e1d  mov     [rbp+rcx*8+70h+Handles], rax
0x180006e22  add     r12d, r15d
0x180006e25  mov     byte ptr [rbx+2A6h], 0
0x180006e2c  jmp     short loc_180006E59
0x180006e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e35  cmp     rcx, rsi
0x180006e38  jz      short loc_180006E60
0x180006e3a  test    [rcx+6Ch], edi
0x180006e3d  jz      short loc_180006E60
0x180006e3f  cmp     [rcx+69h], r15b
0x180006e43  jb      short loc_180006E60
0x180006e45  mov     edx, 6Fh ; 'o'
0x180006e4a  mov     r9d, eax
0x180006e4d  mov     r8, r14
0x180006e50  mov     rcx, [rcx+60h]
0x180006e54  call    WPP_SF_d
0x180006e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e60  lea     r13, [rbx+0D8h]
0x180006e67  cmp     qword ptr [r13+0], 0
0x180006e6c  jz      loc_180006F1F
0x180006e72  cmp     byte ptr [rbx+29Bh], 0
0x180006e79  jz      loc_180006F1F
0x180006e7f  cmp     rcx, rsi
0x180006e82  jz      short loc_180006EA7
0x180006e84  test    [rcx+6Ch], edi
0x180006e87  jz      short loc_180006EA7
0x180006e89  cmp     byte ptr [rcx+69h], 3
0x180006e8d  jb      short loc_180006EA7
0x180006e8f  mov     edx, 70h ; 'p'
0x180006e94  lea     r9, aSecurityManage; "Security Manager"
0x180006e9b  mov     r8, r14
0x180006e9e  mov     rcx, [rcx+60h]
0x180006ea2  call    WPP_SF_s
0x180006ea7  mov     rcx, [r13+0]
  ... truncated ...
```
