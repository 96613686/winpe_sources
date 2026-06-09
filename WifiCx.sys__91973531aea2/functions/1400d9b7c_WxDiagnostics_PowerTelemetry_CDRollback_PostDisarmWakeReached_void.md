# WxDiagnostics::PowerTelemetry::CDRollback_PostDisarmWakeReached(void)

- ea: `0x1400d9b7c`
- end: `0x1400d9e90`
- name: `?CDRollback_PostDisarmWakeReached@PowerTelemetry@WxDiagnostics@@AEAAXXZ`
- size: `788`
- prototype: `void __fastcall(WxDiagnostics::PowerTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400d6f94`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140052d54`
- `0x140052ff4`
- `0x1400cd040`
- `0x1400d3e30`
- `0x1400d4098`
- `0x1400d579c`
- `0x1400d581c`
- `0x1400d6604`
- `0x1400d81cc`
- `0x1400d87c4`
- `0x1400d9b7c`
- `0x1400dfd00`
- `0x1400dfd40`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::CDRollback_PostDisarmWakeReached(WxDiagnostics::PowerTelemetry *this)
{
  __int64 v2; // rdx
  WxDevice *v3; // rax
  int DataPortsWakeReasonInWdfPostDisarmwakeCallback; // eax
  int v5; // edx
  int v6; // r9d
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // r8d
  int v11; // edx
  int v12; // edx
  int v13; // edx
  __int64 v14; // r9
  __int64 v15; // [rsp+28h] [rbp-38h]
  void *v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+50h] [rbp-10h]

  *((_DWORD *)this + 160) = 2;
  v16 = 0;
  v17 = (unsigned int)Feature_WificxSleepStudyReport__private_featureState;
  if ( (Feature_WificxSleepStudyReport__private_featureState & 0x10) == 0 )
  {
    LODWORD(v17) = Feature_WificxSleepStudyReport__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_WificxSleepStudyReport__private_descriptor, v17, 3, 1);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v17,
      3,
      Feature_WificxSleepStudyReport__private_descriptor);
  }
  if ( !*((_DWORD *)this + 166) )
  {
    v2 = *((_QWORD *)this + 75);
    v17 = 0;
    v18 = 0;
    v3 = (WxDevice *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
                       WdfDriverGlobals,
                       v2,
                       off_14010E308);
    DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDevice::GetDataPortsWakeReasonInWdfPostDisarmwakeCallback(
                                                       v3,
                                                       (struct DataPortNetWakeReason *)&v17);
    if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v6 = 16;
      goto LABEL_29;
    }
    if ( v18 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = WxDiagnostics::WxHelpers::MapNetWakeReason();
        v8 = MapWfcPortType(HIDWORD(v17), v7);
        WPP_RECORDER_SF_dSS(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          v10,
          17,
          (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids,
          v17,
          v8,
          v9);
      }
      WxDiagnostics::PowerTelemetry::SetPowerStateSessionWakeSource(this, 1);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          18,
          (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids);
      }
      DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayload(
                                                         this,
                                                         4,
                                                         v18,
                                                         &v16);
      if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v6 = 19;
        goto LABEL_29;
      }
    }
    else
    {
      WxDiagnostics::PowerTelemetry::SetPowerStateSessionWakeSource(this, 4);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 4;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          20,
          (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids);
      }
      DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayload(
                                                         this,
                                                         5,
                                                         *((_DWORD *)this + 172) != 0,
                                                         &v16);
      if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return;
        v6 = 21;
        goto LABEL_29;
      }
    }
    DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDiagnostics::PowerTelemetry::NotifyPowerTelemetryForStateChange(
                                                       this,
                                                       v16);
    if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return;
      v6 = 22;
      goto LABEL_29;
    }
  }
  v13 = *((_DWORD *)this + 166);
  v14 = *((unsigned int *)this + 160);
  v16 = 0;
  DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayloadForDevicePowerStateChange(
                                                     this,
                                                     *((_QWORD *)this + 82),
                                                     (unsigned int)_InterlockedCompareExchange(
                                                                     (volatile signed __int32 *)this + 180,
                                                                     0,
                                                                     0),
                                                     v14,
                                                     v13,
                                                     &v16);
  if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return;
    v6 = 23;
    goto LABEL_29;
  }
  DataPortsWakeReasonInWdfPostDisarmwakeCallback = WxDiagnostics::PowerTelemetry::NotifyPowerTelemetryForStateChange(
                                                     this,
                                                     v16);
  if ( DataPortsWakeReasonInWdfPostDisarmwakeCallback < 0
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v6 = 24;
LABEL_29:
    LODWORD(v15) = DataPortsWakeReasonInWdfPostDisarmwakeCallback;
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      v6,
      (__int64)WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids,
      v15);
  }
}

```

## disassembly

```asm
0x1400d9b7c  mov     [rsp-18h+arg_8], rbx
0x1400d9b81  mov     [rsp-18h+arg_10], rsi
0x1400d9b86  push    rbp
0x1400d9b87  push    rdi
0x1400d9b88  push    r15
0x1400d9b8a  mov     rbp, rsp
0x1400d9b8d  sub     rsp, 60h
0x1400d9b91  mov     rax, cs:__security_cookie
0x1400d9b98  xor     rax, rsp
0x1400d9b9b  mov     [rbp+var_8], rax
0x1400d9b9f  mov     rdi, rcx
0x1400d9ba2  mov     dword ptr [rcx+280h], 2
0x1400d9bac  mov     [rbp+var_20], 0
0x1400d9bb4  mov     ecx, cs:Feature_WificxSleepStudyReport__private_featureState
0x1400d9bba  mov     r15d, 1
0x1400d9bc0  mov     [rbp+var_18], 0
0x1400d9bc8  mov     dword ptr [rbp+var_18], ecx
0x1400d9bcb  test    cl, 10h
0x1400d9bce  jnz     short loc_1400D9C0A
0x1400d9bd0  mov     rax, [rbp+var_18]
0x1400d9bd4  lea     ebx, [r15+2]
0x1400d9bd8  or      ecx, r15d
0x1400d9bdb  mov     [rbp+var_18], rax
0x1400d9bdf  mov     dword ptr [rbp+var_18], ecx
0x1400d9be2  mov     r9d, r15d
0x1400d9be5  mov     rdx, [rbp+var_18]
0x1400d9be9  lea     rcx, Feature_WificxSleepStudyReport__private_descriptor
0x1400d9bf0  mov     r8d, ebx
0x1400d9bf3  call    wil_details_FeatureReporting_ReportUsageToService
0x1400d9bf8  mov     rcx, [rbp+var_18]
0x1400d9bfc  lea     r8, Feature_WificxSleepStudyReport__private_descriptor
0x1400d9c03  mov     edx, ebx
0x1400d9c05  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1400d9c0a  cmp     dword ptr [rdi+298h], 0
0x1400d9c11  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400d9c18  lea     rsi, WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids
0x1400d9c1f  jnz     loc_1400D9DDC
0x1400d9c25  mov     r8, cs:off_14010E308
0x1400d9c2c  xor     eax, eax
0x1400d9c2e  mov     rdx, [rdi+258h]
0x1400d9c35  mov     rcx, cs:WdfDriverGlobals
0x1400d9c3c  mov     [rbp+var_18], rax
0x1400d9c40  mov     [rbp+var_10], eax
0x1400d9c43  mov     rax, cs:WdfFunctions_01031
0x1400d9c4a  mov     rax, [rax+650h]
0x1400d9c51  call    _guard_dispatch_icall
0x1400d9c56  lea     rdx, [rbp+var_18]; struct DataPortNetWakeReason *
0x1400d9c5a  mov     rcx, rax; this
0x1400d9c5d  call    ?GetDataPortsWakeReasonInWdfPostDisarmwakeCallback@WxDevice@@QEAAJPEAUDataPortNetWakeReason@@@Z; WxDevice::GetDataPortsWakeReasonInWdfPostDisarmwakeCallback(DataPortNetWakeReason *)
0x1400d9c62  test    eax, eax
0x1400d9c64  jns     short loc_1400D9C8C
0x1400d9c66  lea     rbx, WPP_RECORDER_INITIALIZED
0x1400d9c6d  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9c74  jz      loc_1400D9E6E
0x1400d9c7a  mov     r9d, 10h
0x1400d9c80  lea     rsi, WPP_5f801e5f1820335c6525eb5df2870ab2_Traceguids
0x1400d9c87  jmp     loc_1400D9E50
0x1400d9c8c  mov     ecx, [rbp+var_10]
0x1400d9c8f  test    ecx, ecx
0x1400d9c91  jz      loc_1400D9D46
0x1400d9c97  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9c9e  jz      short loc_1400D9CDD
0x1400d9ca0  call    ?MapNetWakeReason@WxHelpers@WxDiagnostics@@YAPEBGW4_NET_WAKE_REASON_TYPE@@@Z; WxDiagnostics::WxHelpers::MapNetWakeReason(_NET_WAKE_REASON_TYPE)
0x1400d9ca5  mov     ecx, dword ptr [rbp+var_18+4]
0x1400d9ca8  mov     rdx, rax
0x1400d9cab  call    ?MapWfcPortType@@YAPEBGW4_WFC_PORT_TYPE@@@Z; MapWfcPortType(_WFC_PORT_TYPE)
0x1400d9cb0  movzx   ecx, word ptr [rbp+var_18]
0x1400d9cb4  mov     r9d, 11h
0x1400d9cba  mov     [rsp+60h+var_28], rdx
0x1400d9cbf  mov     [rsp+60h+var_30], rax
0x1400d9cc4  mov     dword ptr [rsp+60h+var_38], ecx
0x1400d9cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9ccf  mov     [rsp+60h+var_40], rsi
0x1400d9cd4  mov     rcx, [rcx+40h]
0x1400d9cd8  call    WPP_RECORDER_SF_dSS
0x1400d9cdd  mov     edx, r15d
0x1400d9ce0  mov     rcx, rdi
0x1400d9ce3  call    ?SetPowerStateSessionWakeSource@PowerTelemetry@WxDiagnostics@@AEAAXW4PowerStateSessionWakeSource@12@@Z; WxDiagnostics::PowerTelemetry::SetPowerStateSessionWakeSource(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource)
0x1400d9ce8  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9cef  jz      short loc_1400D9D11
0x1400d9cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9cf8  mov     r9d, 12h
0x1400d9cfe  mov     r8d, r15d
0x1400d9d01  mov     [rsp+60h+var_40], rsi
0x1400d9d06  mov     dl, 4
0x1400d9d08  mov     rcx, [rcx+40h]
0x1400d9d0c  call    WPP_RECORDER_SF_
0x1400d9d11  mov     r8d, [rbp+var_10]
0x1400d9d15  lea     r9, [rbp+var_20]
0x1400d9d19  mov     edx, 4
0x1400d9d1e  mov     rcx, rdi
0x1400d9d21  call    ?CreatePowerTelemetryStateChangePayload@PowerTelemetry@WxDiagnostics@@AEAAJW4WIFICX_POWER_TELEMETRY_NOTIFICATION_CONTEXT_TYPE@2@JPEAPEAX@Z; WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayload(WxDiagnostics::WIFICX_POWER_TELEMETRY_NOTIFICATION_CONTEXT_TYPE,long,void * *)
0x1400d9d26  test    eax, eax
0x1400d9d28  jns     loc_1400D9DB7
0x1400d9d2e  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9d35  jz      loc_1400D9E6E
0x1400d9d3b  mov     r9d, 13h
0x1400d9d41  jmp     loc_1400D9E50
0x1400d9d46  mov     edx, 4
0x1400d9d4b  mov     rcx, rdi
0x1400d9d4e  call    ?SetPowerStateSessionWakeSource@PowerTelemetry@WxDiagnostics@@AEAAXW4PowerStateSessionWakeSource@12@@Z; WxDiagnostics::PowerTelemetry::SetPowerStateSessionWakeSource(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource)
0x1400d9d53  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9d5a  jz      short loc_1400D9D7C
0x1400d9d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9d63  mov     r9d, 14h
0x1400d9d69  mov     r8d, r15d
0x1400d9d6c  mov     [rsp+60h+var_40], rsi
0x1400d9d71  mov     dl, 4
0x1400d9d73  mov     rcx, [rcx+40h]
0x1400d9d77  call    WPP_RECORDER_SF_
0x1400d9d7c  xor     r8d, r8d
0x1400d9d7f  lea     r9, [rbp+var_20]
0x1400d9d83  cmp     [rdi+2B0h], r8d
0x1400d9d8a  mov     edx, 5
0x1400d9d8f  mov     rcx, rdi
0x1400d9d92  setnz   r8b
0x1400d9d96  call    ?CreatePowerTelemetryStateChangePayload@PowerTelemetry@WxDiagnostics@@AEAAJW4WIFICX_POWER_TELEMETRY_NOTIFICATION_CONTEXT_TYPE@2@JPEAPEAX@Z; WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayload(WxDiagnostics::WIFICX_POWER_TELEMETRY_NOTIFICATION_CONTEXT_TYPE,long,void * *)
0x1400d9d9b  test    eax, eax
0x1400d9d9d  jns     short loc_1400D9DB7
0x1400d9d9f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9da6  jz      loc_1400D9E6E
0x1400d9dac  mov     r9d, 15h
0x1400d9db2  jmp     loc_1400D9E50
0x1400d9db7  mov     rdx, [rbp+var_20]; void *
0x1400d9dbb  mov     rcx, rdi; this
0x1400d9dbe  call    ?NotifyPowerTelemetryForStateChange@PowerTelemetry@WxDiagnostics@@AEAAJPEAX@Z; WxDiagnostics::PowerTelemetry::NotifyPowerTelemetryForStateChange(void *)
0x1400d9dc3  test    eax, eax
0x1400d9dc5  jns     short loc_1400D9DDC
0x1400d9dc7  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9dce  jz      loc_1400D9E6E
0x1400d9dd4  mov     r9d, 16h
0x1400d9dda  jmp     short loc_1400D9E50
0x1400d9ddc  mov     edx, [rdi+298h]
0x1400d9de2  xor     ecx, ecx
0x1400d9de4  mov     r9d, [rdi+280h]
0x1400d9deb  xor     eax, eax
0x1400d9ded  mov     [rbp+var_20], 0
0x1400d9df5  lock cmpxchg [rdi+2D0h], ecx
0x1400d9dfd  lea     rcx, [rbp+var_20]
0x1400d9e01  mov     r8d, eax
0x1400d9e04  mov     [rsp+60h+var_38], rcx
0x1400d9e09  mov     rcx, rdi
0x1400d9e0c  mov     dword ptr [rsp+60h+var_40], edx
0x1400d9e10  mov     rdx, [rdi+290h]
0x1400d9e17  call    ?CreatePowerTelemetryStateChangePayloadForDevicePowerStateChange@PowerTelemetry@WxDiagnostics@@AEAAJ_KJW4PowerState@12@W4PowerStateSessionWakeSource@12@PEAPEAX@Z; WxDiagnostics::PowerTelemetry::CreatePowerTelemetryStateChangePayloadForDevicePowerStateChange(unsigned __int64,long,WxDiagnostics::PowerTelemetry::PowerState,WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource,void * *)
0x1400d9e1c  test    eax, eax
0x1400d9e1e  jns     short loc_1400D9E31
0x1400d9e20  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9e27  jz      short loc_1400D9E6E
0x1400d9e29  mov     r9d, 17h
0x1400d9e2f  jmp     short loc_1400D9E50
0x1400d9e31  mov     rdx, [rbp+var_20]; void *
0x1400d9e35  mov     rcx, rdi; this
0x1400d9e38  call    ?NotifyPowerTelemetryForStateChange@PowerTelemetry@WxDiagnostics@@AEAAJPEAX@Z; WxDiagnostics::PowerTelemetry::NotifyPowerTelemetryForStateChange(void *)
0x1400d9e3d  test    eax, eax
0x1400d9e3f  jns     short loc_1400D9E6E
0x1400d9e41  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400d9e48  jz      short loc_1400D9E6E
0x1400d9e4a  mov     r9d, 18h
0x1400d9e50  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d9e57  mov     r8d, r15d
0x1400d9e5a  mov     dword ptr [rsp+60h+var_38], eax
0x1400d9e5e  mov     dl, 2
0x1400d9e60  mov     [rsp+60h+var_40], rsi
0x1400d9e65  mov     rcx, [rcx+40h]
0x1400d9e69  call    WPP_RECORDER_SF_d
0x1400d9e6e  mov     rcx, [rbp+var_8]
0x1400d9e72  xor     rcx, rsp; StackCookie
0x1400d9e75  call    __security_check_cookie
0x1400d9e7a  lea     r11, [rsp+60h+var_s0]
0x1400d9e7f  mov     rbx, [r11+28h]
0x1400d9e83  mov     rsi, [r11+30h]
0x1400d9e87  mov     rsp, r11
0x1400d9e8a  pop     r15
0x1400d9e8c  pop     rdi
0x1400d9e8d  pop     rbp
0x1400d9e8e  retn
```
