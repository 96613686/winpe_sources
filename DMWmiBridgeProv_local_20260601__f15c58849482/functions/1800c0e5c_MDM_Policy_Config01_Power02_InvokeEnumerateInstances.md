# MDM_Policy_Config01_Power02_InvokeEnumerateInstances

- ea: `0x1800c0e5c`
- end: `0x1800c181a`
- name: `MDM_Policy_Config01_Power02_InvokeEnumerateInstances`
- size: `2494`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c0230`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050b8`
- `0x1800050f0`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x180005278`
- `0x180005358`
- `0x1800053c8`
- `0x180005438`
- `0x1800054a8`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800c0e5c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800c116e`
- `msvcrt!_wtoi` at `0x1800c1299`
- `msvcrt!_wtoi` at `0x1800c12e0`
- `msvcrt!_wtoi` at `0x1800c140b`
- `msvcrt!_wtoi` at `0x1800c1452`
- `msvcrt!_wtoi` at `0x1800c1499`
- `msvcrt!_wtoi` at `0x1800c14e0`
- `msvcrt!_wtoi` at `0x1800c1527`
- `msvcrt!_wtoi` at `0x1800c156e`
- `msvcrt!_wtoi` at `0x1800c1627`
- `msvcrt!_wtoi` at `0x1800c166e`
- `msvcrt!_wtoi` at `0x1800c16b5`
- `msvcrt!_wtoi` at `0x1800c16fc`
- `msvcrt!_wtoi` at `0x1800c116e`
- `msvcrt!_wtoi` at `0x1800c1299`
- `msvcrt!_wtoi` at `0x1800c12e0`
- `msvcrt!_wtoi` at `0x1800c140b`
- `msvcrt!_wtoi` at `0x1800c1452`
- `msvcrt!_wtoi` at `0x1800c1499`
- `msvcrt!_wtoi` at `0x1800c14e0`
- `msvcrt!_wtoi` at `0x1800c1527`
- `msvcrt!_wtoi` at `0x1800c156e`
- `msvcrt!_wtoi` at `0x1800c1627`
- `msvcrt!_wtoi` at `0x1800c166e`
- `msvcrt!_wtoi` at `0x1800c16b5`
- `msvcrt!_wtoi` at `0x1800c16fc`

## string_xrefs

- `0x1800c1375`: `RequirePasswordWhenComputerWakesOnBattery`
- `0x1800c13ae`: `RequirePasswordWhenComputerWakesPluggedIn`
- `0x1800c10b0`: `./Vendor/MSFT/Policy/Config`
- `0x1800c0ed7`: `MDM_Policy_Config01_Power02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Power02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-218h] BYREF
  char v14; // [rsp+48h] [rbp-210h]
  _QWORD *v15; // [rsp+50h] [rbp-208h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-200h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1E8h] BYREF
  char v18; // [rsp+80h] [rbp-1D8h]
  int v19; // [rsp+88h] [rbp-1D0h] BYREF
  char v20; // [rsp+8Ch] [rbp-1CCh]
  _BYTE v21[16]; // [rsp+90h] [rbp-1C8h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-1B8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-1A8h] BYREF
  int v24; // [rsp+110h] [rbp-148h]
  char v25; // [rsp+114h] [rbp-144h]
  int v26; // [rsp+158h] [rbp-100h]
  char v27; // [rsp+15Ch] [rbp-FCh]
  int v28; // [rsp+160h] [rbp-F8h]
  char v29; // [rsp+164h] [rbp-F4h]
  int v30; // [rsp+1A8h] [rbp-B0h]
  char v31; // [rsp+1ACh] [rbp-ACh]
  int v32; // [rsp+1B0h] [rbp-A8h]
  char v33; // [rsp+1B4h] [rbp-A4h]
  int v34; // [rsp+1B8h] [rbp-A0h]
  char v35; // [rsp+1BCh] [rbp-9Ch]
  int v36; // [rsp+1C0h] [rbp-98h]
  char v37; // [rsp+1C4h] [rbp-94h]
  int v38; // [rsp+1C8h] [rbp-90h]
  char v39; // [rsp+1CCh] [rbp-8Ch]
  int v40; // [rsp+1D0h] [rbp-88h]
  char v41; // [rsp+1D4h] [rbp-84h]
  int v42; // [rsp+1F8h] [rbp-60h]
  char v43; // [rsp+1FCh] [rbp-5Ch]
  int v44; // [rsp+200h] [rbp-58h]
  char v45; // [rsp+204h] [rbp-54h]
  int v46; // [rsp+208h] [rbp-50h]
  char v47; // [rsp+20Ch] [rbp-4Ch]
  int v48; // [rsp+210h] [rbp-48h]
  char v49; // [rsp+214h] [rbp-44h]

  memset_0(&instance, 0, 0x168u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_Policy_Config01_Power02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_18034105E,
      v21,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v16, v4);
  try
  {
    v15 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Power02_NodeList, 25, 2, &v15);
    if ( v7 == MI_RESULT_OK )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = (wil *)v15;
          if ( v15 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v15;
            if ( v15 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Power02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_118;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"Power",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowHibernate",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStandbyStatesWhenSleepingOnBattery",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStandbyWhenSleepingPluggedIn",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisplayOffTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisplayOffTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnergySaverBatteryThresholdOnBattery",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnergySaverBatteryThresholdPluggedIn",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HibernateTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HibernateTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePasswordWhenComputerWakesOnBattery",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePasswordWhenComputerWakesPluggedIn",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectLidCloseActionOnBattery",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectLidCloseActionPluggedIn",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectPowerButtonActionOnBattery",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectPowerButtonActionPluggedIn",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectSleepButtonActionOnBattery",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SelectSleepButtonActionPluggedIn",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"StandbyTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"StandbyTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffHybridSleepOnBattery",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffHybridSleepPluggedIn",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"UnattendedSleepTimeoutOnBattery",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"UnattendedSleepTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  v48 = _wtoi(String);
                  v49 = 1;
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
              v14 = 0;
            }
            v6 = (wil *)v15;
            if ( v15 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v17 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v17[0] + 8LL))(v17[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v16, v11);
    LODWORD(v15) = 1;
    goto LABEL_109;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_109:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (int)v15;
  }
LABEL_118:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803575A5,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c0e5c  mov     [rsp+arg_8], rbx
0x1800c0e61  mov     [rsp+arg_10], rsi
0x1800c0e66  push    rdi
0x1800c0e67  push    r12
0x1800c0e69  push    r13
0x1800c0e6b  push    r14
0x1800c0e6d  push    r15
0x1800c0e6f  sub     rsp, 230h
0x1800c0e76  mov     rax, cs:__security_cookie
0x1800c0e7d  xor     rax, rsp
0x1800c0e80  mov     [rsp+258h+var_38], rax
0x1800c0e88  mov     r13b, dl
0x1800c0e8b  mov     r12, rcx
0x1800c0e8e  xor     edx, edx; Val
0x1800c0e90  mov     r8d, 168h; Size
0x1800c0e96  lea     rcx, [rsp+258h+instance]; void *
0x1800c0e9e  call    memset_0
0x1800c0ea3  xor     edi, edi
0x1800c0ea5  mov     [rsp+258h+var_210], dil
0x1800c0eaa  mov     [rsp+258h+String], rdi
0x1800c0eaf  mov     [rsp+258h+var_1D0], edi
0x1800c0eb6  mov     [rsp+258h+var_1CC], dil
0x1800c0ebe  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800c0ec5  mov     [rsp+258h+var_200], rax
0x1800c0eca  lea     rax, [rsp+258h+var_1D0]
0x1800c0ed2  mov     [rsp+258h+var_1F8], rax
0x1800c0ed7  lea     rax, aMdmPolicyConfi_10; "MDM_Policy_Config01_Power02"
0x1800c0ede  mov     [rsp+258h+var_1F0], rax
0x1800c0ee3  lea     rcx, [rsp+258h+var_1D0]
0x1800c0eeb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800c0ef0  mov     eax, cs:dword_180380B68
0x1800c0ef6  cmp     eax, 5
0x1800c0ef9  jbe     short loc_1800C0F6B
0x1800c0efb  mov     rdx, 200000000000h
0x1800c0f05  lea     rcx, dword_180380B68
0x1800c0f0c  call    _tlgKeywordOn
0x1800c0f11  test    al, al
0x1800c0f13  jz      short loc_1800C0F6B
0x1800c0f15  cmp     [rsp+258h+var_1CC], dil
0x1800c0f1d  jz      short loc_1800C0F4D
0x1800c0f1f  cmp     [rsp+258h+var_1B8], edi
0x1800c0f26  jnz     short loc_1800C0F43
0x1800c0f28  cmp     [rsp+258h+var_1B4], edi
0x1800c0f2f  jnz     short loc_1800C0F43
0x1800c0f31  cmp     [rsp+258h+var_1B0], edi
0x1800c0f38  jnz     short loc_1800C0F43
0x1800c0f3a  cmp     [rsp+258h+var_1AC], edi
0x1800c0f41  jz      short loc_1800C0F4D
0x1800c0f43  lea     r9, [rsp+258h+var_1B8]
0x1800c0f4b  jmp     short loc_1800C0F50
0x1800c0f4d  mov     r9, rdi
0x1800c0f50  lea     r8, [rsp+258h+var_1C8]
0x1800c0f58  lea     rdx, word_18034105E
0x1800c0f5f  lea     rcx, dword_180380B68
0x1800c0f66  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800c0f6b  lea     rcx, [rsp+258h+var_200]; this
0x1800c0f70  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800c0f75  nop
0x1800c0f76  mov     [rsp+258h+var_208], rdi
0x1800c0f7b  lea     rax, [rsp+258h+var_208]
0x1800c0f80  mov     [rsp+258h+var_228], rax
0x1800c0f85  mov     [rsp+258h+var_230], 2
0x1800c0f8d  mov     [rsp+258h+var_238], 19h
0x1800c0f95  lea     r9, ?MDM_Policy_Config01_Power02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Power02_NodeList
0x1800c0f9c  xor     r8d, r8d
0x1800c0f9f  xor     edx, edx
0x1800c0fa1  mov     rcx, r12
0x1800c0fa4  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800c0fa9  mov     r15d, eax
0x1800c0fac  test    eax, eax
0x1800c0fae  jz      short loc_1800C0FB5
0x1800c0fb0  jmp     loc_1800C1779
0x1800c0fb5  lea     rbx, [rsp+258h+var_208]
0x1800c0fba  mov     [rsp+258h+var_1E0], rbx
0x1800c0fbf  mov     r14d, 1
0x1800c0fc5  mov     [rsp+258h+var_1D8], r14b
0x1800c0fcd  mov     rsi, [rsp+258h+var_208]
0x1800c0fd2  test    rsi, rsi
0x1800c0fd5  jnz     short loc_1800C0FDF
0x1800c0fd7  mov     r15d, r14d
0x1800c0fda  jmp     loc_1800C1779
0x1800c0fdf  mov     rax, [rsi]
0x1800c0fe2  mov     rcx, rsi
0x1800c0fe5  mov     rax, [rax+10h]
0x1800c0fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0fee  mov     r15d, eax
0x1800c0ff1  test    eax, eax
0x1800c0ff3  jz      short loc_1800C1013
0x1800c0ff5  mov     rcx, [rsp+258h+var_208]
0x1800c0ffa  test    rcx, rcx
0x1800c0ffd  jz      short loc_1800C100E
0x1800c0fff  mov     rax, [rcx]
0x1800c1002  mov     edx, r14d
0x1800c1005  mov     rax, [rax]
0x1800c1008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c100d  nop
0x1800c100e  jmp     loc_1800C1779
0x1800c1013  mov     rax, [rsi]
0x1800c1016  mov     rcx, rsi
0x1800c1019  mov     rax, [rax+8]
0x1800c101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1022  mov     r15d, eax
0x1800c1025  test    eax, eax
0x1800c1027  jz      short loc_1800C1047
0x1800c1029  mov     rcx, [rsp+258h+var_208]
0x1800c102e  test    rcx, rcx
0x1800c1031  jz      short loc_1800C1042
0x1800c1033  mov     rax, [rcx]
0x1800c1036  mov     edx, r14d
0x1800c1039  mov     rax, [rax]
0x1800c103c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1041  nop
0x1800c1042  jmp     loc_1800C1779
0x1800c1047  mov     r14d, edi
0x1800c104a  mov     rax, [rsi+108h]
0x1800c1051  sub     rax, [rsi+100h]
0x1800c1058  sar     rax, 4
0x1800c105c  cmp     r14d, eax
0x1800c105f  jnb     loc_1800C1741
0x1800c1065  lea     r8, [rsp+258h+instance]; instance
0x1800c106d  lea     rdx, MDM_Policy_Config01_Power02_rtti; classDecl
0x1800c1074  mov     rcx, r12; context
0x1800c1077  call    MI_Context_ConstructInstance
0x1800c107c  mov     r15d, eax
0x1800c107f  test    eax, eax
0x1800c1081  jz      short loc_1800C10A3
0x1800c1083  mov     rcx, [rbx]
0x1800c1086  test    rcx, rcx
0x1800c1089  jz      short loc_1800C109E
0x1800c108b  mov     rax, [rcx]
0x1800c108e  mov     edx, 1
0x1800c1093  mov     rax, [rax]
0x1800c1096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c109b  mov     [rbx], rdi
0x1800c109e  jmp     loc_1800C1779
0x1800c10a3  mov     [rsp+258h+var_210], 1
0x1800c10a8  mov     rax, [rsi]
0x1800c10ab  lea     r9, [rsp+258h+String]
0x1800c10b0  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800c10b7  mov     edx, r14d
0x1800c10ba  mov     rcx, rsi
0x1800c10bd  mov     rax, [rax+18h]
0x1800c10c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10c6  test    eax, eax
0x1800c10c8  jnz     short loc_1800C10E1
0x1800c10ca  mov     rdx, [rsp+258h+String]
0x1800c10cf  test    rdx, rdx
0x1800c10d2  jz      short loc_1800C10E1
0x1800c10d4  lea     rcx, [rsp+258h+instance]
0x1800c10dc  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800c10e1  mov     rax, [rsi]
0x1800c10e4  lea     r9, [rsp+258h+String]
0x1800c10e9  lea     r8, aPower; "Power"
0x1800c10f0  mov     edx, r14d
0x1800c10f3  mov     rcx, rsi
0x1800c10f6  mov     rax, [rax+18h]
0x1800c10fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10ff  test    eax, eax
0x1800c1101  jnz     short loc_1800C111A
0x1800c1103  mov     rdx, [rsp+258h+String]
0x1800c1108  test    rdx, rdx
0x1800c110b  jz      short loc_1800C111A
0x1800c110d  lea     rcx, [rsp+258h+instance]
0x1800c1115  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800c111a  cmp     r13b, 1
0x1800c111e  jnz     short loc_1800C1142
0x1800c1120  lea     rdx, [rsp+258h+instance]
0x1800c1128  mov     rcx, r12; self
0x1800c112b  call    MI_Instance_Destruct
0x1800c1130  lea     rcx, [rsp+258h+instance]; self
0x1800c1138  call    MI_Instance_Destruct
0x1800c113d  jmp     loc_1800C1734
0x1800c1142  mov     rax, [rsi]
0x1800c1145  lea     r9, [rsp+258h+String]
0x1800c114a  lea     r8, aAllowhibernate; "AllowHibernate"
0x1800c1151  mov     edx, r14d
0x1800c1154  mov     rcx, rsi
0x1800c1157  mov     rax, [rax+18h]
0x1800c115b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1160  test    eax, eax
0x1800c1162  jnz     short loc_1800C1189
0x1800c1164  mov     rcx, [rsp+258h+String]; String
0x1800c1169  test    rcx, rcx
0x1800c116c  jz      short loc_1800C1189
0x1800c116e  call    cs:__imp__wtoi
0x1800c1175  nop     dword ptr [rax+rax+00h]
0x1800c117a  mov     [rsp+258h+var_148], eax
0x1800c1181  mov     [rsp+258h+var_144], 1
0x1800c1189  mov     rax, [rsi]
0x1800c118c  lea     r9, [rsp+258h+String]
0x1800c1191  lea     r8, aAllowstandbyst; "AllowStandbyStatesWhenSleepingOnBattery"
0x1800c1198  mov     edx, r14d
0x1800c119b  mov     rcx, rsi
0x1800c119e  mov     rax, [rax+18h]
0x1800c11a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c11a7  test    eax, eax
0x1800c11a9  jnz     short loc_1800C11C2
0x1800c11ab  mov     rdx, [rsp+258h+String]
0x1800c11b0  test    rdx, rdx
0x1800c11b3  jz      short loc_1800C11C2
0x1800c11b5  lea     rcx, [rsp+258h+instance]
0x1800c11bd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800c11c2  mov     rax, [rsi]
0x1800c11c5  lea     r9, [rsp+258h+String]
0x1800c11ca  lea     r8, aAllowstandbywh; "AllowStandbyWhenSleepingPluggedIn"
0x1800c11d1  mov     edx, r14d
0x1800c11d4  mov     rcx, rsi
0x1800c11d7  mov     rax, [rax+18h]
0x1800c11db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c11e0  test    eax, eax
0x1800c11e2  jnz     short loc_1800C11FB
0x1800c11e4  mov     rdx, [rsp+258h+String]
0x1800c11e9  test    rdx, rdx
0x1800c11ec  jz      short loc_1800C11FB
0x1800c11ee  lea     rcx, [rsp+258h+instance]
0x1800c11f6  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800c11fb  mov     rax, [rsi]
0x1800c11fe  lea     r9, [rsp+258h+String]
0x1800c1203  lea     r8, aDisplayofftime_0; "DisplayOffTimeoutOnBattery"
0x1800c120a  mov     edx, r14d
0x1800c120d  mov     rcx, rsi
0x1800c1210  mov     rax, [rax+18h]
0x1800c1214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1219  test    eax, eax
0x1800c121b  jnz     short loc_1800C1234
0x1800c121d  mov     rdx, [rsp+258h+String]
0x1800c1222  test    rdx, rdx
0x1800c1225  jz      short loc_1800C1234
0x1800c1227  lea     rcx, [rsp+258h+instance]
0x1800c122f  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800c1234  mov     rax, [rsi]
0x1800c1237  lea     r9, [rsp+258h+String]
0x1800c123c  lea     r8, aDisplayofftime; "DisplayOffTimeoutPluggedIn"
0x1800c1243  mov     edx, r14d
0x1800c1246  mov     rcx, rsi
0x1800c1249  mov     rax, [rax+18h]
0x1800c124d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1252  test    eax, eax
0x1800c1254  jnz     short loc_1800C126D
0x1800c1256  mov     rdx, [rsp+258h+String]
0x1800c125b  test    rdx, rdx
0x1800c125e  jz      short loc_1800C126D
0x1800c1260  lea     rcx, [rsp+258h+instance]
0x1800c1268  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800c126d  mov     rax, [rsi]
0x1800c1270  lea     r9, [rsp+258h+String]
0x1800c1275  lea     r8, aEnergysaverbat; "EnergySaverBatteryThresholdOnBattery"
0x1800c127c  mov     edx, r14d
0x1800c127f  mov     rcx, rsi
0x1800c1282  mov     rax, [rax+18h]
0x1800c1286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c128b  test    eax, eax
0x1800c128d  jnz     short loc_1800C12B4
0x1800c128f  mov     rcx, [rsp+258h+String]; String
0x1800c1294  test    rcx, rcx
0x1800c1297  jz      short loc_1800C12B4
0x1800c1299  call    cs:__imp__wtoi
0x1800c12a0  nop     dword ptr [rax+rax+00h]
0x1800c12a5  mov     [rsp+258h+var_100], eax
0x1800c12ac  mov     [rsp+258h+var_FC], 1
0x1800c12b4  mov     rax, [rsi]
0x1800c12b7  lea     r9, [rsp+258h+String]
0x1800c12bc  lea     r8, aEnergysaverbat_0; "EnergySaverBatteryThresholdPluggedIn"
0x1800c12c3  mov     edx, r14d
0x1800c12c6  mov     rcx, rsi
0x1800c12c9  mov     rax, [rax+18h]
0x1800c12cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c12d2  test    eax, eax
0x1800c12d4  jnz     short loc_1800C12FB
0x1800c12d6  mov     rcx, [rsp+258h+String]; String
0x1800c12db  test    rcx, rcx
0x1800c12de  jz      short loc_1800C12FB
0x1800c12e0  call    cs:__imp__wtoi
0x1800c12e7  nop     dword ptr [rax+rax+00h]
0x1800c12ec  mov     [rsp+258h+var_F8], eax
0x1800c12f3  mov     [rsp+258h+var_F4], 1
0x1800c12fb  mov     rax, [rsi]
0x1800c12fe  lea     r9, [rsp+258h+String]
0x1800c1303  lea     r8, aHibernatetimeo; "HibernateTimeoutOnBattery"
0x1800c130a  mov     edx, r14d
0x1800c130d  mov     rcx, rsi
0x1800c1310  mov     rax, [rax+18h]
0x1800c1314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1319  test    eax, eax
0x1800c131b  jnz     short loc_1800C1334
0x1800c131d  mov     rdx, [rsp+258h+String]
0x1800c1322  test    rdx, rdx
0x1800c1325  jz      short loc_1800C1334
0x1800c1327  lea     rcx, [rsp+258h+instance]
0x1800c132f  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800c1334  mov     rax, [rsi]
0x1800c1337  lea     r9, [rsp+258h+String]
0x1800c133c  lea     r8, aHibernatetimeo_0; "HibernateTimeoutPluggedIn"
0x1800c1343  mov     edx, r14d
0x1800c1346  mov     rcx, rsi
0x1800c1349  mov     rax, [rax+18h]
0x1800c134d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1352  test    eax, eax
0x1800c1354  jnz     short loc_1800C136D
0x1800c1356  mov     rdx, [rsp+258h+String]
  ... truncated ...
```
