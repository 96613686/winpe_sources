# SendProtocolResultToRasman

- ea: `0x180045f64`
- end: `0x180046eb8`
- name: `SendProtocolResultToRasman`
- size: `3924`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002a010`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800070c4`
- `0x18000bfb0`
- `0x18000c00c`
- `0x180018d9c`
- `0x18003204c`
- `0x18003209c`
- `0x180038aa0`
- `0x18003b8fc`
- `0x18003ca44`
- `0x18003e480`
- `0x18003e9e8`
- `0x18003ee98`
- `0x18004033c`
- `0x1800421ac`
- `0x18004238c`
- `0x180043c34`
- `0x180045f64`
- `0x1800477c0`
- `0x180047934`
- `0x1800482dc`
- `0x180048464`
- `0x180049548`
- `0x180049ebc`
- `0x180065484`
- `0x180099770`
- `0x1800e71ee`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800469ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800469ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800464d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800469a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004648e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004648e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046439`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180046439`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800464ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800464ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800464c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004699a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800464c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004699a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046db4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046b0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046db4`

## string_xrefs

- `0x180046252`: `RasUpdateVpnLuidStatus: Setting %I64X to %s`
- `0x180046344`: `RasUpdateVpnLuidStatus: Setting %I64X to %s`

## pseudocode

```c
__int64 __fastcall SendProtocolResultToRasman(_QWORD *Src)
{
  __int64 PortByHandle; // r14
  struct _LIST_ENTRY *v3; // rcx
  unsigned int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // r9
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  _QWORD *i; // rbx
  _BYTE *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // edx
  _DWORD *v16; // rax
  _DWORD *v17; // r15
  DWORD LastError; // eax
  __int64 v19; // rdx
  struct _LIST_ENTRY *v20; // rsi
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r13
  __int64 v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // r9
  void *v27; // r8
  const CHAR *v28; // rdx
  const CHAR *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rsi
  _BYTE *v32; // rdi
  DWORD CurrentProcessId; // eax
  unsigned int PasswordA; // eax
  HLOCAL *v35; // rbx
  __int64 v36; // rcx
  _BYTE *v37; // rax
  _BYTE *v38; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned int v40; // eax
  struct _LIST_ENTRY *v41; // rcx
  _DWORD *v42; // rcx
  struct _LIST_ENTRY *v43; // rcx
  __int64 v44; // r9
  __int64 v45; // rcx
  _QWORD *v46; // rax
  HLOCAL hMem; // [rsp+60h] [rbp-58h] BYREF
  int v49; // [rsp+68h] [rbp-50h]
  __int128 v50; // [rsp+6Ch] [rbp-4Ch]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 269, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
  }
  PortByHandle = GetPortByHandle(Src[2]);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control[1].Flink,
      270,
      WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
      *((unsigned int *)Src + 3),
      Src[2]);
    v3 = WPP_GLOBAL_Control;
  }
  if ( PortByHandle )
  {
    v4 = 0;
    if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v3[1].Blink) & 0x2000) != 0
      && BYTE1(v3[1].Blink) >= 5u )
    {
      WPP_SF_Ds(
        v3[1].Flink,
        272,
        (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
        *(_DWORD *)(PortByHandle + 28),
        PortByHandle + 8);
      v3 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(PortByHandle + 28) != 2 )
    {
      if ( *(_DWORD *)(PortByHandle + 28) == 1 )
      {
        v7 = *((unsigned int *)Src + 3);
        if ( (_DWORD)v7 != 1 )
        {
          if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v4;
          if ( (HIDWORD(v3[1].Blink) & 0x2000) == 0 || BYTE1(v3[1].Blink) < 5u )
            goto LABEL_262;
          WPP_SF_dq(v3[1].Flink, 275, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v7, *(_QWORD *)PortByHandle);
          goto LABEL_261;
        }
      }
      if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v3[1].Blink) & 0x2000) != 0
        && BYTE1(v3[1].Blink) >= 5u )
      {
        WPP_SF_(v3[1].Flink, 273, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
      *(_DWORD *)(PortByHandle + 1316) = 0;
      v8 = DwProcessProtocolFailureMessage(PortByHandle);
      v4 = v8;
      if ( !v8 )
      {
LABEL_261:
        v3 = WPP_GLOBAL_Control;
        goto LABEL_262;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_262;
      v5 = 274;
      goto LABEL_36;
    }
    if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v3[1].Blink) & 0x2000) != 0
      && BYTE1(v3[1].Blink) >= 5u )
    {
      WPP_SF_d(v3[1].Flink, 276, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, *((unsigned int *)Src + 3));
      v3 = WPP_GLOBAL_Control;
    }
    v9 = *((_DWORD *)Src + 3);
    switch ( v9 )
    {
      case 14:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 277, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
        v10 = SignalNotifierAndNetman(PortByHandle, 512, 16);
        v4 = v10;
        if ( v10 )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_52:
            for ( i = g_RasVpnLuids; i; i = (_QWORD *)i[2] )
            {
              if ( *i == (*(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 160LL) & 0xFFFFFF | 0x17000000LL) << 24 )
              {
                TraceMsg("RasUpdateVpnLuidStatus: Setting %I64X to %s");
                *((_BYTE *)i + 8) = 1;
                goto LABEL_261;
              }
            }
            goto LABEL_262;
          }
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 278, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v10);
        }
        v3 = WPP_GLOBAL_Control;
        goto LABEL_52;
      case 16:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 279, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
        v8 = SignalNotifierAndNetman(PortByHandle, 1024, 0);
        v4 = v8;
        if ( !v8 )
          goto LABEL_261;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_262;
        v5 = 280;
        goto LABEL_36;
      case 15:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 281, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
        v12 = g_RasVpnLuids;
        v13 = (*(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 160LL) & 0xFFFFFF | 0x17000000LL) << 24;
        while ( v12 )
        {
          if ( *(_QWORD *)v12 == v13 )
          {
            TraceMsg("RasUpdateVpnLuidStatus: Setting %I64X to %s");
            v12[8] = 0;
            break;
          }
          v12 = (_BYTE *)*((_QWORD *)v12 + 2);
        }
        LogUpdateConnectionSuccessEvent(PortByHandle, v13);
        v8 = SignalNotifierAndNetman(PortByHandle, 2048, 32);
        v4 = v8;
        if ( !v8 )
          goto LABEL_261;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_262;
        v5 = 282;
LABEL_36:
        v6 = v8;
        goto LABEL_15;
      case 17:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 283, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
          v3 = WPP_GLOBAL_Control;
        }
        v14 = *(_QWORD *)(PortByHandle + 1304);
        if ( v14 )
        {
          v15 = *((_DWORD *)Src + 16);
          *(_DWORD *)v14 = v15;
          if ( v15 )
          {
            LogUpdateConnectionFailureEvent(PortByHandle);
            SignalNotifierAndNetman(PortByHandle, 512, 0);
          }
          SetEvent(*(HANDLE *)(v14 + 8));
          goto LABEL_261;
        }
        v4 = 6;
        if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(v3[1].Blink) & 0x2000) == 0 || BYTE1(v3[1].Blink) < 2u )
          goto LABEL_262;
        v5 = 284;
        goto LABEL_14;
      case 18:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 285, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
        SignalNotifiers(*(_QWORD *)(*(_QWORD *)(PortByHandle + 1064) + 48LL), 64, 0);
        EnterCriticalSection(&g_csConnectionNotifierList);
        SignalNotifiers(pConnectionNotifierList, 64, 0);
        LeaveCriticalSection(&g_csConnectionNotifierList);
        goto LABEL_261;
    }
    v16 = LocalAlloc(0x40u, 0x6D8u);
    v17 = v16;
    if ( !v16 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( !LastError )
        goto LABEL_261;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_262;
      v19 = 286;
      goto LABEL_109;
    }
    memcpy_0(v16, Src, 0x6D8u);
    if ( v17[3] == 11 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
      {
LABEL_116:
        if ( v17[3] == 1 && v17[16] )
        {
          if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v20[1].Blink) & 0x2000) != 0
            && BYTE1(v20[1].Blink) >= 5u )
          {
            WPP_SF_sd(
              v20[1].Flink,
              288,
              (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
              PortByHandle + 8,
              v17[16]);
          }
          *(_DWORD *)(PortByHandle + 264) = v17[16];
          v20 = WPP_GLOBAL_Control;
        }
        if ( v17[3] == 12 )
        {
          if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v20[1].Blink) & 0x2000) != 0
            && BYTE1(v20[1].Blink) >= 5u )
          {
            WPP_SF_(v20[1].Flink, 289, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
            v20 = WPP_GLOBAL_Control;
          }
          v21 = (unsigned int)v17[18];
          if ( (_DWORD)v21 )
          {
            v22 = *((_QWORD *)v17 + 8);
            if ( v22 )
            {
              SetUserData(PortByHandle + 1080, 6, v22, v21);
              v20 = WPP_GLOBAL_Control;
            }
          }
        }
        if ( v17[3] == 13 )
        {
          if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v20[1].Blink) & 0x2000) != 0
            && BYTE1(v20[1].Blink) >= 5u )
          {
            WPP_SF_(v20[1].Flink, 290, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
          }
          SetUserData(PortByHandle + 1080, 15, v17 + 16, 8);
          v20 = WPP_GLOBAL_Control;
        }
        v23 = -1;
        if ( v17[3] != 4 )
        {
LABEL_173:
          if ( v17[3] == 7 )
          {
            if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v20[1].Blink) & 0x2000) != 0
              && BYTE1(v20[1].Blink) >= 5u )
            {
              WPP_SF_(v20[1].Flink, 296, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
            }
            v31 = 257;
            v32 = LocalAlloc(0x40u, 0x101u);
            if ( !v32 )
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( !LastError )
                goto LABEL_261;
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                return v4;
              if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                goto LABEL_262;
              v19 = 297;
              goto LABEL_109;
            }
            CurrentProcessId = GetCurrentProcessId();
            PasswordA = DwGetPasswordA(PortByHandle, v32, CurrentProcessId);
            if ( PasswordA
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 298, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, PasswordA);
            }
            if ( !v4 )
            {
              hMem = 0;
              do
                ++v23;
              while ( v32[v23] );
              v4 = EncodeData(v32, (unsigned int)(v23 + 1), &hMem);
              if ( v4 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 299, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v4);
                }
              }
              else
              {
                v35 = (HLOCAL *)hMem;
                if ( hMem )
                {
                  SetUserData(PortByHandle + 1080, 10, *((_QWORD *)hMem + 1), *(unsigned int *)hMem);
                  v36 = *(unsigned int *)v35;
                  v37 = v35[1];
                  if ( *(_DWORD *)v35 )
                  {
                    do
                    {
                      *v37++ = 0;
                      --v36;
                    }
                    while ( v36 );
                  }
                  LocalFree(v35[1]);
                  LocalFree(v35);
                }
              }
              v38 = v32;
              do
              {
                *v38++ = 0;
                --v31;
              }
              while ( v31 );
              LocalFree(v32);
            }
          }
          if ( (Feature_VPN_2026_Bundle_1_Disconnect_Port_After_Plugin_Failure__private_featureState & 0x10) != 0 )
            IsEnabledDeviceUsageNoInline = Feature_VPN_2026_Bundle_1_Disconnect_Port_After_Plugin_Failure__private_featureState
                                         & 1;
          else
            IsEnabledDeviceUsageNoInline = Feature_VPN_2026_Bundle_1_Disconnect_Port_After_Plugin_Failure__private_IsEnabledDeviceUsageNoInline();
          if ( IsEnabledDeviceUsageNoInline && v17[3] == 1 && *(_DWORD *)(PortByHandle + 28) == 2 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control[1].Flink,
                300,
                (unsigned int)WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
                PortByHandle + 8,
                v17[16]);
            }
            *(_DWORD *)(PortByHandle + 264) = v17[16];
            *(_DWORD *)(PortByHandle + 1316) = 0;
            LastError = DwProcessProtocolFailureMessage(PortByHandle);
            v4 = LastError;
            if ( !LastError )
              goto LABEL_261;
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              return v4;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              goto LABEL_262;
            v19 = 301;
LABEL_109:
            WPP_SF_d(v3[1].Flink, v19, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
            v3 = WPP_GLOBAL_Control;
            goto LABEL_262;
          }
          if ( v17[3] != 10 )
          {
            if ( !v17[3] )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 307, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
              }
              v45 = *(_QWORD *)(PortByHandle + 1064);
              *(_DWORD *)(PortByHandle + 1320) = 1;
              if ( v45 && (*(_BYTE *)(v45 + 112) & 0x10) != 0 )
                CheckAndInitiateProtocolRenegotiation(v45, 0);
            }
            v46 = *(_QWORD **)(PortByHandle + 1120);
            if ( v46 )
              *v46 = v17;
            else
              *(_QWORD *)(PortByHandle + 1112) = v17;
            *(_QWORD *)(PortByHandle + 1120) = v17;
            *(_QWORD *)v17 = 0;
            SetProtocolResultAvailableEvent(PortByHandle);
            goto LABEL_261;
          }
          if ( *(_DWORD *)(PortByHandle + 1360) != 3 )
          {
LABEL_233:
            v43 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                304,
                WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
                (unsigned int)v17[2]);
              v43 = WPP_GLOBAL_Control;
            }
            v44 = (unsigned int)v17[2];
            if ( (_DWORD)v44 )
            {
              if ( v43 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v43[1].Blink) & 0x2000) != 0
                && BYTE1(v43[1].Blink) >= 5u )
              {
                WPP_SF_d(v43[1].Flink, 305, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v44);
              }
              *(_DWORD *)(PortByHandle + 264) = v17[2];
            }
            *(_DWORD *)(PortByHandle + 1316) = v17[16] & 1;
            v4 = DwProcessProtocolFailureMessage(PortByHandle);
            if ( v4
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 306, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v4);
            }
            LocalFree(v17);
            goto LABEL_261;
          }
          *(_DWORD *)g_RasEvent = 128;
          v40 = DwSendNotificationInternal(*(_QWORD *)(PortByHandle + 1064), g_RasEvent);
          if ( v40 )
          {
            v41 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
LABEL_231:
              *(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 120LL) = *(_DWORD *)(PortByHandle + 1072);
              v42 = *(_DWORD **)(PortByHandle + 1064);
              if ( !v42[41] )
              {
                FreeConnection(v42);
                *(_QWORD *)(PortByHandle + 1064) = 0;
              }
              goto LABEL_233;
            }
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_227:
              if ( v41 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v41[1].Blink) & 0x2000) != 0
                && BYTE1(v41[1].Blink) >= 5u )
              {
                WPP_SF_qqd(
                  v41[1].Flink,
                  303,
                  WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids,
                  *(_QWORD *)(*(_QWORD *)(PortByHandle + 1064) + 16LL),
                  *(_QWORD *)(PortByHandle + 1064),
                  *(_DWORD *)(PortByHandle + 1072));
              }
              goto LABEL_231;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 302, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v40);
          }
          v41 = WPP_GLOBAL_Control;
          goto LABEL_227;
        }
        if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v20[1].Blink) & 0x2000) != 0
          && BYTE1(v20[1].Blink) >= 5u )
        {
          WPP_SF_(v20[1].Flink, 291, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
          v20 = WPP_GLOBAL_Control;
        }
        v24 = *(_QWORD *)(PortByHandle + 1064);
        if ( v24 )
        {
          v25 = *((_QWORD *)v17 + 35);
          if ( v25 )
          {
            if ( !GetUserData(v24 + 32, 4) )
            {
              v26 = -1;
              do
                ++v26;
              while ( *(_BYTE *)(v25 + v26) );
              SetUserData(*(_QWORD *)(PortByHandle + 1064) + 32LL, 4, v25, (unsigned int)(v26 + 1));
            }
            v20 = WPP_GLOBAL_Control;
          }
        }
        if ( !v17[31] && (*(_BYTE *)(PortByHandle + 40) & 4) == 0 )
        {
          v27 = *(void **)(PortByHandle + 1240);
          v28 = *(const CHAR **)(PortByHandle + 1208);
          v29 = *(const CHAR **)(PortByHandle + 1200);
          *(_QWORD *)((char *)&v50 + 1) = 0;
          *(_QWORD *)&v50 = *((_QWORD *)v17 + 16);
          *((_QWORD *)&v50 + 1) = *((_QWORD *)v17 + 18);
          v49 = 3;
          v30 = WriteSharedPbkOptions(v29, v28, v27);
          v4 = v30;
          if ( !v30 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_165;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_DDDDDDDD(
                WPP_GLOBAL_Control[1].Flink,
                293,
                *((unsigned __int8 *)v17 + 133),
                *((unsigned __int8 *)v17 + 128),
                *((unsigned __int8 *)v17 + 129),
                *((unsigned __int8 *)v17 + 130),
                *((unsigned __int8 *)v17 + 131),
                *((unsigned __int8 *)v17 + 132),
                *((unsigned __int8 *)v17 + 133),
                *((unsigned __int8 *)v17 + 134),
                *((unsigned __int8 *)v17 + 135));
              v20 = WPP_GLOBAL_Control;
            }
            if ( v20 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(v20[1].Blink) & 0x2000) == 0
              || BYTE1(v20[1].Blink) < 5u )
            {
              goto LABEL_165;
            }
            WPP_SF_DDDDDDDD(
              v20[1].Flink,
              294,
              *((unsigned __int8 *)v17 + 149),
              *((unsigned __int8 *)v17 + 144),
              *((unsigned __int8 *)v17 + 145),
              *((unsigned __int8 *)v17 + 146),
              *((unsigned __int8 *)v17 + 147),
              *((unsigned __int8 *)v17 + 148),
              *((unsigned __int8 *)v17 + 149),
              *((unsigned __int8 *)v17 + 150),
              *((unsigned __int8 *)v17 + 151));
            goto LABEL_164;
          }
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 292, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v30);
LABEL_164:
            v20 = WPP_GLOBAL_Control;
          }
        }
LABEL_165:
        if ( v17[16] == 1 )
        {
          v4 = PopulateTsRoutes(*(_QWORD *)(PortByHandle + 1064), v17 + 62);
          if ( v4 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 295, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v4);
              v20 = WPP_GLOBAL_Control;
            }
            v4 = 0;
          }
          else
          {
            v20 = WPP_GLOBAL_Control;
          }
        }
        goto LABEL_173;
      }
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 287, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, PortByHandle + 8);
    }
    v20 = WPP_GLOBAL_Control;
    goto LABEL_116;
  }
  v4 = 6;
  if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(v3[1].Blink) & 0x2000) != 0 && BYTE1(v3[1].Blink) >= 2u )
  {
    v5 = 271;
LABEL_14:
    v6 = 6;
LABEL_15:
    WPP_SF_d(v3[1].Flink, v5, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v6);
    goto LABEL_261;
  }
LABEL_262:
  if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v3[1].Blink) & 0x2000) != 0
    && BYTE1(v3[1].Blink) >= 6u )
  {
    WPP_SF_d(v3[1].Flink, 308, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180045f64  mov     [rsp+arg_8], rbx
0x180045f69  mov     [rsp+arg_10], rbp
0x180045f6e  push    rsi
0x180045f6f  push    rdi
0x180045f70  push    r13
0x180045f72  push    r14
0x180045f74  push    r15
0x180045f76  sub     rsp, 90h
0x180045f7d  mov     rax, cs:__security_cookie
0x180045f84  xor     rax, rsp
0x180045f87  mov     [rsp+0B8h+var_38], rax
0x180045f8f  mov     rbx, rcx
0x180045f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180045f99  lea     r15, WPP_GLOBAL_Control
0x180045fa0  mov     esi, 6
0x180045fa5  mov     edi, 2000h
0x180045faa  cmp     rcx, r15
0x180045fad  jz      short loc_180045FCF
0x180045faf  test    [rcx+1Ch], edi
0x180045fb2  jz      short loc_180045FCF
0x180045fb4  cmp     [rcx+19h], sil
0x180045fb8  jb      short loc_180045FCF
0x180045fba  mov     rcx, [rcx+10h]
0x180045fbe  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180045fc5  mov     edx, 10Dh
0x180045fca  call    WPP_SF_
0x180045fcf  mov     rcx, [rbx+10h]
0x180045fd3  call    GetPortByHandle
0x180045fd8  mov     r14, rax
0x180045fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045fe2  mov     r13b, 5
0x180045fe5  cmp     rcx, r15
0x180045fe8  jz      short loc_18004601E
0x180045fea  test    [rcx+1Ch], edi
0x180045fed  jz      short loc_18004601E
0x180045fef  cmp     [rcx+19h], r13b
0x180045ff3  jb      short loc_18004601E
0x180045ff5  mov     rax, [rbx+10h]
0x180045ff9  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180046000  mov     r9d, [rbx+0Ch]
0x180046004  mov     edx, 10Eh
0x180046009  mov     rcx, [rcx+10h]
0x18004600d  mov     [rsp+0B8h+var_98], rax
0x180046012  call    WPP_SF_dq
0x180046017  mov     rcx, cs:WPP_GLOBAL_Control
0x18004601e  test    r14, r14
0x180046021  jnz     short loc_18004605E
0x180046023  mov     ebp, esi
0x180046025  cmp     rcx, r15
0x180046028  jz      loc_180046E8A
0x18004602e  test    [rcx+1Ch], edi
0x180046031  jz      loc_180046E5B
0x180046037  cmp     byte ptr [rcx+19h], 2
0x18004603b  jb      loc_180046E5B
0x180046041  mov     edx, 10Fh
0x180046046  mov     r9d, esi
0x180046049  mov     rcx, [rcx+10h]
0x18004604d  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180046054  call    WPP_SF_d
0x180046059  jmp     loc_180046E54
0x18004605e  xor     ebp, ebp
0x180046060  cmp     rcx, r15
0x180046063  jz      short loc_180046099
0x180046065  test    [rcx+1Ch], edi
0x180046068  jz      short loc_180046099
0x18004606a  cmp     [rcx+19h], r13b
0x18004606e  jb      short loc_180046099
0x180046070  mov     r9d, [r14+1Ch]
0x180046074  lea     rax, [r14+8]
0x180046078  mov     rcx, [rcx+10h]
0x18004607c  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180046083  mov     edx, 110h
0x180046088  mov     [rsp+0B8h+var_98], rax
0x18004608d  call    WPP_SF_Ds
0x180046092  mov     rcx, cs:WPP_GLOBAL_Control
0x180046099  cmp     dword ptr [r14+1Ch], 2
0x18004609e  jz      loc_180046161
0x1800460a4  cmp     dword ptr [r14+1Ch], 1
0x1800460a9  jnz     short loc_1800460F3
0x1800460ab  mov     r9d, [rbx+0Ch]
0x1800460af  cmp     r9d, 1
0x1800460b3  jz      short loc_1800460F3
0x1800460b5  cmp     rcx, r15
0x1800460b8  jz      loc_180046E8A
0x1800460be  test    [rcx+1Ch], edi
0x1800460c1  jz      loc_180046E5B
0x1800460c7  cmp     [rcx+19h], r13b
0x1800460cb  jb      loc_180046E5B
0x1800460d1  mov     rax, [r14]
0x1800460d4  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800460db  mov     rcx, [rcx+10h]
0x1800460df  mov     edx, 113h
0x1800460e4  mov     [rsp+0B8h+var_98], rax
0x1800460e9  call    WPP_SF_dq
0x1800460ee  jmp     loc_180046E54
0x1800460f3  cmp     rcx, r15
0x1800460f6  jz      short loc_180046118
0x1800460f8  test    [rcx+1Ch], edi
0x1800460fb  jz      short loc_180046118
0x1800460fd  cmp     [rcx+19h], r13b
0x180046101  jb      short loc_180046118
0x180046103  mov     rcx, [rcx+10h]
0x180046107  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18004610e  mov     edx, 111h
0x180046113  call    WPP_SF_
0x180046118  mov     rcx, r14
0x18004611b  mov     [r14+524h], ebp
0x180046122  call    DwProcessProtocolFailureMessage
0x180046127  mov     ebp, eax
0x180046129  test    eax, eax
0x18004612b  jz      loc_180046E54
0x180046131  mov     rcx, cs:WPP_GLOBAL_Control
0x180046138  cmp     rcx, r15
0x18004613b  jz      loc_180046E8A
0x180046141  test    [rcx+1Ch], edi
0x180046144  jz      loc_180046E5B
0x18004614a  cmp     byte ptr [rcx+19h], 2
0x18004614e  jb      loc_180046E5B
0x180046154  mov     edx, 112h
0x180046159  mov     r9d, eax
0x18004615c  jmp     loc_180046049
0x180046161  cmp     rcx, r15
0x180046164  jz      short loc_180046191
0x180046166  test    [rcx+1Ch], edi
0x180046169  jz      short loc_180046191
0x18004616b  cmp     [rcx+19h], r13b
0x18004616f  jb      short loc_180046191
0x180046171  mov     r9d, [rbx+0Ch]
0x180046175  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18004617c  mov     rcx, [rcx+10h]
0x180046180  mov     edx, 114h
0x180046185  call    WPP_SF_d
0x18004618a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046191  mov     eax, [rbx+0Ch]
0x180046194  cmp     eax, 0Eh
0x180046197  jnz     loc_180046267
0x18004619d  cmp     rcx, r15
0x1800461a0  jz      short loc_1800461C2
0x1800461a2  test    [rcx+1Ch], edi
0x1800461a5  jz      short loc_1800461C2
0x1800461a7  cmp     [rcx+19h], r13b
0x1800461ab  jb      short loc_1800461C2
0x1800461ad  mov     rcx, [rcx+10h]
0x1800461b1  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800461b8  mov     edx, 115h
0x1800461bd  call    WPP_SF_
0x1800461c2  mov     edx, 200h
0x1800461c7  mov     r8d, 10h
0x1800461cd  mov     rcx, r14
0x1800461d0  call    SignalNotifierAndNetman
0x1800461d5  mov     ebp, eax
0x1800461d7  test    eax, eax
0x1800461d9  jz      short loc_18004620A
0x1800461db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461e2  cmp     rcx, r15
0x1800461e5  jz      short loc_180046211
0x1800461e7  test    [rcx+1Ch], edi
0x1800461ea  jz      short loc_180046211
0x1800461ec  cmp     byte ptr [rcx+19h], 2
0x1800461f0  jb      short loc_180046211
0x1800461f2  mov     rcx, [rcx+10h]
0x1800461f6  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800461fd  mov     edx, 116h
0x180046202  mov     r9d, eax
0x180046205  call    WPP_SF_d
0x18004620a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046211  mov     rdx, [r14+428h]
0x180046218  mov     rbx, cs:g_RasVpnLuids
0x18004621f  mov     edx, [rdx+0A0h]
0x180046225  and     edx, 0FFFFFFh
0x18004622b  or      rdx, 17000000h
0x180046232  shl     rdx, 18h
0x180046236  jmp     short loc_180046241
0x180046238  cmp     [rbx], rdx
0x18004623b  jz      short loc_18004624B
0x18004623d  mov     rbx, [rbx+10h]
0x180046241  test    rbx, rbx
0x180046244  jnz     short loc_180046238
0x180046246  jmp     loc_180046E5B
0x18004624b  lea     r8, aDormant; "Dormant"
0x180046252  lea     rcx, szFormat; "RasUpdateVpnLuidStatus: Setting %I64X t"...
0x180046259  call    TraceMsg
0x18004625e  mov     byte ptr [rbx+8], 1
0x180046262  jmp     loc_180046E54
0x180046267  cmp     eax, 10h
0x18004626a  jnz     short loc_1800462D8
0x18004626c  cmp     rcx, r15
0x18004626f  jz      short loc_180046291
0x180046271  test    [rcx+1Ch], edi
0x180046274  jz      short loc_180046291
0x180046276  cmp     [rcx+19h], r13b
0x18004627a  jb      short loc_180046291
0x18004627c  mov     rcx, [rcx+10h]
0x180046280  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180046287  mov     edx, 117h
0x18004628c  call    WPP_SF_
0x180046291  xor     r8d, r8d
0x180046294  mov     edx, 400h
0x180046299  mov     rcx, r14
0x18004629c  call    SignalNotifierAndNetman
0x1800462a1  mov     ebp, eax
0x1800462a3  test    eax, eax
0x1800462a5  jz      loc_180046E54
0x1800462ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462b2  cmp     rcx, r15
0x1800462b5  jz      loc_180046E8A
0x1800462bb  test    [rcx+1Ch], edi
0x1800462be  jz      loc_180046E5B
0x1800462c4  cmp     byte ptr [rcx+19h], 2
0x1800462c8  jb      loc_180046E5B
0x1800462ce  mov     edx, 118h
0x1800462d3  jmp     loc_180046159
0x1800462d8  cmp     eax, 0Fh
0x1800462db  jnz     loc_1800463A6
0x1800462e1  cmp     rcx, r15
0x1800462e4  jz      short loc_180046306
0x1800462e6  test    [rcx+1Ch], edi
0x1800462e9  jz      short loc_180046306
0x1800462eb  cmp     [rcx+19h], r13b
0x1800462ef  jb      short loc_180046306
0x1800462f1  mov     rcx, [rcx+10h]
0x1800462f5  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800462fc  mov     edx, 119h
0x180046301  call    WPP_SF_
0x180046306  mov     rdx, [r14+428h]
0x18004630d  mov     rbx, cs:g_RasVpnLuids
0x180046314  mov     edx, [rdx+0A0h]
0x18004631a  and     edx, 0FFFFFFh
0x180046320  or      rdx, 17000000h
0x180046327  shl     rdx, 18h
0x18004632b  jmp     short loc_180046336
0x18004632d  cmp     [rbx], rdx
0x180046330  jz      short loc_18004633D
0x180046332  mov     rbx, [rbx+10h]
0x180046336  test    rbx, rbx
0x180046339  jnz     short loc_18004632D
0x18004633b  jmp     short loc_180046354
0x18004633d  lea     r8, aActive; "Active"
0x180046344  lea     rcx, szFormat; "RasUpdateVpnLuidStatus: Setting %I64X t"...
0x18004634b  call    TraceMsg
0x180046350  mov     [rbx+8], bpl
0x180046354  mov     rcx, r14
0x180046357  call    LogUpdateConnectionSuccessEvent
0x18004635c  mov     edx, 800h
0x180046361  mov     r8d, 20h ; ' '
0x180046367  mov     rcx, r14
0x18004636a  call    SignalNotifierAndNetman
0x18004636f  mov     ebp, eax
0x180046371  test    eax, eax
0x180046373  jz      loc_180046E54
0x180046379  mov     rcx, cs:WPP_GLOBAL_Control
0x180046380  cmp     rcx, r15
0x180046383  jz      loc_180046E8A
0x180046389  test    [rcx+1Ch], edi
0x18004638c  jz      loc_180046E5B
0x180046392  cmp     byte ptr [rcx+19h], 2
0x180046396  jb      loc_180046E5B
0x18004639c  mov     edx, 11Ah
0x1800463a1  jmp     loc_180046159
0x1800463a6  cmp     eax, 11h
0x1800463a9  jnz     loc_180046444
0x1800463af  cmp     rcx, r15
0x1800463b2  jz      short loc_1800463DB
0x1800463b4  test    [rcx+1Ch], edi
0x1800463b7  jz      short loc_1800463DB
0x1800463b9  cmp     [rcx+19h], r13b
0x1800463bd  jb      short loc_1800463DB
0x1800463bf  mov     rcx, [rcx+10h]
0x1800463c3  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800463ca  mov     edx, 11Bh
0x1800463cf  call    WPP_SF_
0x1800463d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463db  mov     rdi, [r14+518h]
0x1800463e2  test    rdi, rdi
0x1800463e5  jnz     short loc_180046414
0x1800463e7  mov     ebp, esi
0x1800463e9  cmp     rcx, r15
0x1800463ec  jz      loc_180046E8A
0x1800463f2  mov     edi, 2000h
0x1800463f7  test    [rcx+1Ch], edi
0x1800463fa  jz      loc_180046E5B
0x180046400  cmp     byte ptr [rcx+19h], 2
0x180046404  jb      loc_180046E5B
0x18004640a  mov     edx, 11Ch
0x18004640f  jmp     loc_180046046
0x180046414  mov     edx, [rbx+40h]
0x180046417  mov     [rdi], edx
0x180046419  test    edx, edx
0x18004641b  jz      short loc_180046435
0x18004641d  mov     rcx, r14
0x180046420  call    LogUpdateConnectionFailureEvent
0x180046425  xor     r8d, r8d
0x180046428  mov     edx, 200h
0x18004642d  mov     rcx, r14
0x180046430  call    SignalNotifierAndNetman
0x180046435  mov     rcx, [rdi+8]; hEvent
0x180046439  call    cs:__imp_SetEvent
0x18004643f  jmp     loc_180046E4F
0x180046444  cmp     eax, 12h
0x180046447  jnz     short loc_1800464B7
  ... truncated ...
```
