# MDM_Policy_Config01_Power02_InvokeEnumerateInstances

- ea: `0x1800c1894`
- end: `0x1800c2203`
- name: `MDM_Policy_Config01_Power02_InvokeEnumerateInstances`
- size: `2415`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c0c50`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004ee4`
- `0x180004f1c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x1800050a4`
- `0x180005184`
- `0x1800051f4`
- `0x180005264`
- `0x1800052d4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800c1894`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800c1ba6`
- `msvcrt!_wtoi` at `0x1800c1ccb`
- `msvcrt!_wtoi` at `0x1800c1d0c`
- `msvcrt!_wtoi` at `0x1800c1e31`
- `msvcrt!_wtoi` at `0x1800c1e72`
- `msvcrt!_wtoi` at `0x1800c1eb3`
- `msvcrt!_wtoi` at `0x1800c1ef4`
- `msvcrt!_wtoi` at `0x1800c1f35`
- `msvcrt!_wtoi` at `0x1800c1f76`
- `msvcrt!_wtoi` at `0x1800c2029`
- `msvcrt!_wtoi` at `0x1800c206a`
- `msvcrt!_wtoi` at `0x1800c20ab`
- `msvcrt!_wtoi` at `0x1800c20ec`
- `msvcrt!_wtoi` at `0x1800c1ba6`
- `msvcrt!_wtoi` at `0x1800c1ccb`
- `msvcrt!_wtoi` at `0x1800c1d0c`
- `msvcrt!_wtoi` at `0x1800c1e31`
- `msvcrt!_wtoi` at `0x1800c1e72`
- `msvcrt!_wtoi` at `0x1800c1eb3`
- `msvcrt!_wtoi` at `0x1800c1ef4`
- `msvcrt!_wtoi` at `0x1800c1f35`
- `msvcrt!_wtoi` at `0x1800c1f76`
- `msvcrt!_wtoi` at `0x1800c2029`
- `msvcrt!_wtoi` at `0x1800c206a`
- `msvcrt!_wtoi` at `0x1800c20ab`
- `msvcrt!_wtoi` at `0x1800c20ec`

## string_xrefs

- `0x1800c1d9b`: `RequirePasswordWhenComputerWakesOnBattery`
- `0x1800c1dd4`: `RequirePasswordWhenComputerWakesPluggedIn`
- `0x1800c1ae8`: `./Vendor/MSFT/Policy/Config`
- `0x1800c190f`: `MDM_Policy_Config01_Power02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Power02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-218h] BYREF
  char v14; // [rsp+48h] [rbp-210h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-208h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Power02_NodeList,
           0x19u,
           2,
           &v15);
    if ( !v7 )
    {
      v17[1] = (const exception *)&v15;
      v18 = 1;
      v8 = v15;
      if ( v15 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v15 + 16LL))(v15);
        if ( v7 )
        {
          v6 = v15;
          if ( v15 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v15;
            if ( v15 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Power02_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_118;
              }
              v14 = 1;
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowHibernate",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStandbyStatesWhenSleepingOnBattery",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowStandbyWhenSleepingPluggedIn",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisplayOffTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisplayOffTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnergySaverBatteryThresholdOnBattery",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnergySaverBatteryThresholdPluggedIn",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HibernateTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HibernateTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePasswordWhenComputerWakesOnBattery",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePasswordWhenComputerWakesPluggedIn",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectLidCloseActionOnBattery",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectLidCloseActionPluggedIn",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectPowerButtonActionOnBattery",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectPowerButtonActionPluggedIn",
                        &String)
                  && String )
                {
                  v36 = _wtoi(String);
                  v37 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectSleepButtonActionOnBattery",
                        &String)
                  && String )
                {
                  v38 = _wtoi(String);
                  v39 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SelectSleepButtonActionPluggedIn",
                        &String)
                  && String )
                {
                  v40 = _wtoi(String);
                  v41 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"StandbyTimeoutOnBattery",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"StandbyTimeoutPluggedIn",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownRestrictedSitesZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffHybridSleepOnBattery",
                        &String)
                  && String )
                {
                  v42 = _wtoi(String);
                  v43 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TurnOffHybridSleepPluggedIn",
                        &String)
                  && String )
                {
                  v44 = _wtoi(String);
                  v45 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"UnattendedSleepTimeoutOnBattery",
                        &String)
                  && String )
                {
                  v46 = _wtoi(String);
                  v47 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
            v6 = v15;
            if ( v15 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
              v15 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
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
    v7 = (unsigned int)v15;
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
  return v7;
}

```

## disassembly

```asm
0x1800c1894  mov     [rsp+arg_8], rbx
0x1800c1899  mov     [rsp+arg_10], rsi
0x1800c189e  push    rdi
0x1800c189f  push    r12
0x1800c18a1  push    r13
0x1800c18a3  push    r14
0x1800c18a5  push    r15
0x1800c18a7  sub     rsp, 230h
0x1800c18ae  mov     rax, cs:__security_cookie
0x1800c18b5  xor     rax, rsp
0x1800c18b8  mov     [rsp+258h+var_38], rax
0x1800c18c0  mov     r13b, dl
0x1800c18c3  mov     r12, rcx
0x1800c18c6  xor     edx, edx; Val
0x1800c18c8  mov     r8d, 168h; Size
0x1800c18ce  lea     rcx, [rsp+258h+instance]; void *
0x1800c18d6  call    memset_0
0x1800c18db  xor     edi, edi
0x1800c18dd  mov     [rsp+258h+var_210], dil
0x1800c18e2  mov     [rsp+258h+String], rdi
0x1800c18e7  mov     [rsp+258h+var_1D0], edi
0x1800c18ee  mov     [rsp+258h+var_1CC], dil
0x1800c18f6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800c18fd  mov     [rsp+258h+var_200], rax
0x1800c1902  lea     rax, [rsp+258h+var_1D0]
0x1800c190a  mov     [rsp+258h+var_1F8], rax
0x1800c190f  lea     rax, aMdmPolicyConfi_10; "MDM_Policy_Config01_Power02"
0x1800c1916  mov     [rsp+258h+var_1F0], rax
0x1800c191b  lea     rcx, [rsp+258h+var_1D0]
0x1800c1923  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800c1928  mov     eax, cs:dword_180380B68
0x1800c192e  cmp     eax, 5
0x1800c1931  jbe     short loc_1800C19A3
0x1800c1933  mov     rdx, 200000000000h
0x1800c193d  lea     rcx, dword_180380B68
0x1800c1944  call    _tlgKeywordOn
0x1800c1949  test    al, al
0x1800c194b  jz      short loc_1800C19A3
0x1800c194d  cmp     [rsp+258h+var_1CC], dil
0x1800c1955  jz      short loc_1800C1985
0x1800c1957  cmp     [rsp+258h+var_1B8], edi
0x1800c195e  jnz     short loc_1800C197B
0x1800c1960  cmp     [rsp+258h+var_1B4], edi
0x1800c1967  jnz     short loc_1800C197B
0x1800c1969  cmp     [rsp+258h+var_1B0], edi
0x1800c1970  jnz     short loc_1800C197B
0x1800c1972  cmp     [rsp+258h+var_1AC], edi
0x1800c1979  jz      short loc_1800C1985
0x1800c197b  lea     r9, [rsp+258h+var_1B8]
0x1800c1983  jmp     short loc_1800C1988
0x1800c1985  mov     r9, rdi
0x1800c1988  lea     r8, [rsp+258h+var_1C8]
0x1800c1990  lea     rdx, word_18034105E
0x1800c1997  lea     rcx, dword_180380B68
0x1800c199e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800c19a3  lea     rcx, [rsp+258h+var_200]; this
0x1800c19a8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800c19ad  nop
0x1800c19ae  mov     [rsp+258h+var_208], rdi
0x1800c19b3  lea     rax, [rsp+258h+var_208]
0x1800c19b8  mov     [rsp+258h+var_228], rax
0x1800c19bd  mov     [rsp+258h+var_230], 2
0x1800c19c5  mov     [rsp+258h+var_238], 19h
0x1800c19cd  lea     r9, ?MDM_Policy_Config01_Power02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Power02_NodeList
0x1800c19d4  xor     r8d, r8d
0x1800c19d7  xor     edx, edx
0x1800c19d9  mov     rcx, r12
0x1800c19dc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800c19e1  mov     r15d, eax
0x1800c19e4  test    eax, eax
0x1800c19e6  jz      short loc_1800C19ED
0x1800c19e8  jmp     loc_1800C2163
0x1800c19ed  lea     rbx, [rsp+258h+var_208]
0x1800c19f2  mov     [rsp+258h+var_1E0], rbx
0x1800c19f7  mov     r14d, 1
0x1800c19fd  mov     [rsp+258h+var_1D8], r14b
0x1800c1a05  mov     rsi, [rsp+258h+var_208]
0x1800c1a0a  test    rsi, rsi
0x1800c1a0d  jnz     short loc_1800C1A17
0x1800c1a0f  mov     r15d, r14d
0x1800c1a12  jmp     loc_1800C2163
0x1800c1a17  mov     rax, [rsi]
0x1800c1a1a  mov     rcx, rsi
0x1800c1a1d  mov     rax, [rax+10h]
0x1800c1a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a26  mov     r15d, eax
0x1800c1a29  test    eax, eax
0x1800c1a2b  jz      short loc_1800C1A4B
0x1800c1a2d  mov     rcx, [rsp+258h+var_208]
0x1800c1a32  test    rcx, rcx
0x1800c1a35  jz      short loc_1800C1A46
0x1800c1a37  mov     rax, [rcx]
0x1800c1a3a  mov     edx, r14d
0x1800c1a3d  mov     rax, [rax]
0x1800c1a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a45  nop
0x1800c1a46  jmp     loc_1800C2163
0x1800c1a4b  mov     rax, [rsi]
0x1800c1a4e  mov     rcx, rsi
0x1800c1a51  mov     rax, [rax+8]
0x1800c1a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a5a  mov     r15d, eax
0x1800c1a5d  test    eax, eax
0x1800c1a5f  jz      short loc_1800C1A7F
0x1800c1a61  mov     rcx, [rsp+258h+var_208]
0x1800c1a66  test    rcx, rcx
0x1800c1a69  jz      short loc_1800C1A7A
0x1800c1a6b  mov     rax, [rcx]
0x1800c1a6e  mov     edx, r14d
0x1800c1a71  mov     rax, [rax]
0x1800c1a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a79  nop
0x1800c1a7a  jmp     loc_1800C2163
0x1800c1a7f  mov     r14d, edi
0x1800c1a82  mov     rax, [rsi+108h]
0x1800c1a89  sub     rax, [rsi+100h]
0x1800c1a90  sar     rax, 4
0x1800c1a94  cmp     r14d, eax
0x1800c1a97  jnb     loc_1800C212B
0x1800c1a9d  lea     r8, [rsp+258h+instance]; instance
0x1800c1aa5  lea     rdx, MDM_Policy_Config01_Power02_rtti; classDecl
0x1800c1aac  mov     rcx, r12; context
0x1800c1aaf  call    MI_Context_ConstructInstance
0x1800c1ab4  mov     r15d, eax
0x1800c1ab7  test    eax, eax
0x1800c1ab9  jz      short loc_1800C1ADB
0x1800c1abb  mov     rcx, [rbx]
0x1800c1abe  test    rcx, rcx
0x1800c1ac1  jz      short loc_1800C1AD6
0x1800c1ac3  mov     rax, [rcx]
0x1800c1ac6  mov     edx, 1
0x1800c1acb  mov     rax, [rax]
0x1800c1ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1ad3  mov     [rbx], rdi
0x1800c1ad6  jmp     loc_1800C2163
0x1800c1adb  mov     [rsp+258h+var_210], 1
0x1800c1ae0  mov     rax, [rsi]
0x1800c1ae3  lea     r9, [rsp+258h+String]
0x1800c1ae8  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800c1aef  mov     edx, r14d
0x1800c1af2  mov     rcx, rsi
0x1800c1af5  mov     rax, [rax+18h]
0x1800c1af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1afe  test    eax, eax
0x1800c1b00  jnz     short loc_1800C1B19
0x1800c1b02  mov     rdx, [rsp+258h+String]
0x1800c1b07  test    rdx, rdx
0x1800c1b0a  jz      short loc_1800C1B19
0x1800c1b0c  lea     rcx, [rsp+258h+instance]
0x1800c1b14  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800c1b19  mov     rax, [rsi]
0x1800c1b1c  lea     r9, [rsp+258h+String]
0x1800c1b21  lea     r8, aPower; "Power"
0x1800c1b28  mov     edx, r14d
0x1800c1b2b  mov     rcx, rsi
0x1800c1b2e  mov     rax, [rax+18h]
0x1800c1b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b37  test    eax, eax
0x1800c1b39  jnz     short loc_1800C1B52
0x1800c1b3b  mov     rdx, [rsp+258h+String]
0x1800c1b40  test    rdx, rdx
0x1800c1b43  jz      short loc_1800C1B52
0x1800c1b45  lea     rcx, [rsp+258h+instance]
0x1800c1b4d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800c1b52  cmp     r13b, 1
0x1800c1b56  jnz     short loc_1800C1B7A
0x1800c1b58  lea     rdx, [rsp+258h+instance]
0x1800c1b60  mov     rcx, r12; self
0x1800c1b63  call    MI_Instance_Destruct
0x1800c1b68  lea     rcx, [rsp+258h+instance]; self
0x1800c1b70  call    MI_Instance_Destruct
0x1800c1b75  jmp     loc_1800C211E
0x1800c1b7a  mov     rax, [rsi]
0x1800c1b7d  lea     r9, [rsp+258h+String]
0x1800c1b82  lea     r8, aAllowhibernate; "AllowHibernate"
0x1800c1b89  mov     edx, r14d
0x1800c1b8c  mov     rcx, rsi
0x1800c1b8f  mov     rax, [rax+18h]
0x1800c1b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b98  test    eax, eax
0x1800c1b9a  jnz     short loc_1800C1BBB
0x1800c1b9c  mov     rcx, [rsp+258h+String]; String
0x1800c1ba1  test    rcx, rcx
0x1800c1ba4  jz      short loc_1800C1BBB
0x1800c1ba6  call    cs:__imp__wtoi
0x1800c1bac  mov     [rsp+258h+var_148], eax
0x1800c1bb3  mov     [rsp+258h+var_144], 1
0x1800c1bbb  mov     rax, [rsi]
0x1800c1bbe  lea     r9, [rsp+258h+String]
0x1800c1bc3  lea     r8, aAllowstandbyst; "AllowStandbyStatesWhenSleepingOnBattery"
0x1800c1bca  mov     edx, r14d
0x1800c1bcd  mov     rcx, rsi
0x1800c1bd0  mov     rax, [rax+18h]
0x1800c1bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1bd9  test    eax, eax
0x1800c1bdb  jnz     short loc_1800C1BF4
0x1800c1bdd  mov     rdx, [rsp+258h+String]
0x1800c1be2  test    rdx, rdx
0x1800c1be5  jz      short loc_1800C1BF4
0x1800c1be7  lea     rcx, [rsp+258h+instance]
0x1800c1bef  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800c1bf4  mov     rax, [rsi]
0x1800c1bf7  lea     r9, [rsp+258h+String]
0x1800c1bfc  lea     r8, aAllowstandbywh; "AllowStandbyWhenSleepingPluggedIn"
0x1800c1c03  mov     edx, r14d
0x1800c1c06  mov     rcx, rsi
0x1800c1c09  mov     rax, [rax+18h]
0x1800c1c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c12  test    eax, eax
0x1800c1c14  jnz     short loc_1800C1C2D
0x1800c1c16  mov     rdx, [rsp+258h+String]
0x1800c1c1b  test    rdx, rdx
0x1800c1c1e  jz      short loc_1800C1C2D
0x1800c1c20  lea     rcx, [rsp+258h+instance]
0x1800c1c28  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x1800c1c2d  mov     rax, [rsi]
0x1800c1c30  lea     r9, [rsp+258h+String]
0x1800c1c35  lea     r8, aDisplayofftime_0; "DisplayOffTimeoutOnBattery"
0x1800c1c3c  mov     edx, r14d
0x1800c1c3f  mov     rcx, rsi
0x1800c1c42  mov     rax, [rax+18h]
0x1800c1c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c4b  test    eax, eax
0x1800c1c4d  jnz     short loc_1800C1C66
0x1800c1c4f  mov     rdx, [rsp+258h+String]
0x1800c1c54  test    rdx, rdx
0x1800c1c57  jz      short loc_1800C1C66
0x1800c1c59  lea     rcx, [rsp+258h+instance]
0x1800c1c61  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1800c1c66  mov     rax, [rsi]
0x1800c1c69  lea     r9, [rsp+258h+String]
0x1800c1c6e  lea     r8, aDisplayofftime; "DisplayOffTimeoutPluggedIn"
0x1800c1c75  mov     edx, r14d
0x1800c1c78  mov     rcx, rsi
0x1800c1c7b  mov     rax, [rax+18h]
0x1800c1c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1c84  test    eax, eax
0x1800c1c86  jnz     short loc_1800C1C9F
0x1800c1c88  mov     rdx, [rsp+258h+String]
0x1800c1c8d  test    rdx, rdx
0x1800c1c90  jz      short loc_1800C1C9F
0x1800c1c92  lea     rcx, [rsp+258h+instance]
0x1800c1c9a  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800c1c9f  mov     rax, [rsi]
0x1800c1ca2  lea     r9, [rsp+258h+String]
0x1800c1ca7  lea     r8, aEnergysaverbat; "EnergySaverBatteryThresholdOnBattery"
0x1800c1cae  mov     edx, r14d
0x1800c1cb1  mov     rcx, rsi
0x1800c1cb4  mov     rax, [rax+18h]
0x1800c1cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1cbd  test    eax, eax
0x1800c1cbf  jnz     short loc_1800C1CE0
0x1800c1cc1  mov     rcx, [rsp+258h+String]; String
0x1800c1cc6  test    rcx, rcx
0x1800c1cc9  jz      short loc_1800C1CE0
0x1800c1ccb  call    cs:__imp__wtoi
0x1800c1cd1  mov     [rsp+258h+var_100], eax
0x1800c1cd8  mov     [rsp+258h+var_FC], 1
0x1800c1ce0  mov     rax, [rsi]
0x1800c1ce3  lea     r9, [rsp+258h+String]
0x1800c1ce8  lea     r8, aEnergysaverbat_0; "EnergySaverBatteryThresholdPluggedIn"
0x1800c1cef  mov     edx, r14d
0x1800c1cf2  mov     rcx, rsi
0x1800c1cf5  mov     rax, [rax+18h]
0x1800c1cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1cfe  test    eax, eax
0x1800c1d00  jnz     short loc_1800C1D21
0x1800c1d02  mov     rcx, [rsp+258h+String]; String
0x1800c1d07  test    rcx, rcx
0x1800c1d0a  jz      short loc_1800C1D21
0x1800c1d0c  call    cs:__imp__wtoi
0x1800c1d12  mov     [rsp+258h+var_F8], eax
0x1800c1d19  mov     [rsp+258h+var_F4], 1
0x1800c1d21  mov     rax, [rsi]
0x1800c1d24  lea     r9, [rsp+258h+String]
0x1800c1d29  lea     r8, aHibernatetimeo; "HibernateTimeoutOnBattery"
0x1800c1d30  mov     edx, r14d
0x1800c1d33  mov     rcx, rsi
0x1800c1d36  mov     rax, [rax+18h]
0x1800c1d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d3f  test    eax, eax
0x1800c1d41  jnz     short loc_1800C1D5A
0x1800c1d43  mov     rdx, [rsp+258h+String]
0x1800c1d48  test    rdx, rdx
0x1800c1d4b  jz      short loc_1800C1D5A
0x1800c1d4d  lea     rcx, [rsp+258h+instance]
0x1800c1d55  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800c1d5a  mov     rax, [rsi]
0x1800c1d5d  lea     r9, [rsp+258h+String]
0x1800c1d62  lea     r8, aHibernatetimeo_0; "HibernateTimeoutPluggedIn"
0x1800c1d69  mov     edx, r14d
0x1800c1d6c  mov     rcx, rsi
0x1800c1d6f  mov     rax, [rax+18h]
0x1800c1d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d78  test    eax, eax
0x1800c1d7a  jnz     short loc_1800C1D93
0x1800c1d7c  mov     rdx, [rsp+258h+String]
0x1800c1d81  test    rdx, rdx
0x1800c1d84  jz      short loc_1800C1D93
0x1800c1d86  lea     rcx, [rsp+258h+instance]
  ... truncated ...
```
