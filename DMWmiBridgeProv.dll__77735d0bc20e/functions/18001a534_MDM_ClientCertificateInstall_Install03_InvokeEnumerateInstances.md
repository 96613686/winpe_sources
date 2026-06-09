# MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances

- ea: `0x18001a534`
- end: `0x18001ad4e`
- name: `MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances`
- size: `2074`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800196d0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004f1c`
- `0x180004f54`
- `0x180004f8c`
- `0x180004fc4`
- `0x1800050a4`
- `0x1800050dc`
- `0x180005114`
- `0x18000514c`
- `0x180005184`
- `0x1800051bc`
- `0x1800051f4`
- `0x18000522c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18001a534`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18001a8f1`
- `msvcrt!_wtoi` at `0x18001a96b`
- `msvcrt!_wtoi` at `0x18001a9ac`
- `msvcrt!_wtoi` at `0x18001a9ed`
- `msvcrt!_wtoi` at `0x18001aa67`
- `msvcrt!_wtoi` at `0x18001ab8c`
- `msvcrt!_wtoi` at `0x18001a8f1`
- `msvcrt!_wtoi` at `0x18001a96b`
- `msvcrt!_wtoi` at `0x18001a9ac`
- `msvcrt!_wtoi` at `0x18001a9ed`
- `msvcrt!_wtoi` at `0x18001aa67`
- `msvcrt!_wtoi` at `0x18001ab8c`

## string_xrefs

- `0x18001aa0a`: `TemplateName`
- `0x18001a788`: `./Vendor/MSFT/ClientCertificateInstall/SCEP/%s`
- `0x18001a7c1`: `./Vendor/MSFT/ClientCertificateInstall/SCEP/%s/Install`
- `0x18001a5af`: `MDM_ClientCertificateInstall_Install03`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1F8h] BYREF
  char v14; // [rsp+48h] [rbp-1F0h]
  WmiRequestHandlerAdd *v15; // [rsp+50h] [rbp-1E8h] BYREF
  _QWORD v16[3]; // [rsp+58h] [rbp-1E0h] BYREF
  const exception *v17[2]; // [rsp+70h] [rbp-1C8h] BYREF
  char v18; // [rsp+80h] [rbp-1B8h]
  int v19; // [rsp+88h] [rbp-1B0h] BYREF
  char v20; // [rsp+8Ch] [rbp-1ACh]
  _BYTE v21[16]; // [rsp+90h] [rbp-1A8h] BYREF
  _DWORD v22[4]; // [rsp+A0h] [rbp-198h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-188h] BYREF
  int v24; // [rsp+140h] [rbp-F8h]
  char v25; // [rsp+144h] [rbp-F4h]
  int v26; // [rsp+158h] [rbp-E0h]
  char v27; // [rsp+15Ch] [rbp-DCh]
  int v28; // [rsp+160h] [rbp-D8h]
  char v29; // [rsp+164h] [rbp-D4h]
  int v30; // [rsp+168h] [rbp-D0h]
  char v31; // [rsp+16Ch] [rbp-CCh]
  int v32; // [rsp+180h] [rbp-B8h]
  char v33; // [rsp+184h] [rbp-B4h]
  int v34; // [rsp+1C8h] [rbp-70h]
  char v35; // [rsp+1CCh] [rbp-6Ch]

  memset_0(&instance, 0, 0x150u);
  v14 = 0;
  String = 0;
  v19 = 0;
  v20 = 0;
  v16[0] = &TelemetryEventWriter::`vftable';
  v16[1] = &v19;
  v16[2] = "MDM_ClientCertificateInstall_Install03";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v19);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v20 && (v22[0] || v22[1] || v22[2] || v22[3]) )
      v5 = v22;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803423E3,
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
           (struct WmiNodeInfo *)&MDM_ClientCertificateInstall_Install03_NodeList,
           0x15u,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_ClientCertificateInstall_Install03_rtti, &instance);
              if ( v7 )
              {
                v6 = v15;
                if ( v15 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_103;
              }
              v14 = 1;
              if ( !(*(unsigned int (**)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, ...))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/ClientCertificateInstall/SCEP/%s",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (**)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, ...))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/ClientCertificateInstall/SCEP/%s/Install",
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
                        L"ServerURL",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"Challenge",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EKUMapping",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"KeyUsage",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SubjectName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"KeyProtection",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RetryDelay",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RetryCount",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"TemplateName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"KeyLength",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HashAlgorithm",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CAThumbprint",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"SubjectAlternativeNames",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ValidPeriod",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ValidPeriodUnits",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ContainerName",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"CustomTextToShowInPrompt",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DataEncryption(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AADKeyIdentifierList",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownLocalMachineZoneTemplate(&instance);
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
    goto LABEL_94;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v16, v12);
    LODWORD(v15) = 1;
LABEL_94:
    if ( v14 )
      MI_Instance_Destruct(&instance);
    v7 = (unsigned int)v15;
  }
LABEL_103:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v16, "EnumerateInstancesEnd", v7);
  v19 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18036A29C,
      v21,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v19);
  return v7;
}

```

## disassembly

```asm
0x18001a534  mov     [rsp+arg_8], rbx
0x18001a539  mov     [rsp+arg_10], rsi
0x18001a53e  push    rdi
0x18001a53f  push    r12
0x18001a541  push    r13
0x18001a543  push    r14
0x18001a545  push    r15
0x18001a547  sub     rsp, 210h
0x18001a54e  mov     rax, cs:__security_cookie
0x18001a555  xor     rax, rsp
0x18001a558  mov     [rsp+238h+var_38], rax
0x18001a560  mov     r13b, dl
0x18001a563  mov     r12, rcx
0x18001a566  xor     edx, edx; Val
0x18001a568  mov     r8d, 150h; Size
0x18001a56e  lea     rcx, [rsp+238h+instance]; void *
0x18001a576  call    memset_0
0x18001a57b  xor     edi, edi
0x18001a57d  mov     [rsp+238h+var_1F0], dil
0x18001a582  mov     [rsp+238h+String], rdi
0x18001a587  mov     [rsp+238h+var_1B0], edi
0x18001a58e  mov     [rsp+238h+var_1AC], dil
0x18001a596  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18001a59d  mov     [rsp+238h+var_1E0], rax
0x18001a5a2  lea     rax, [rsp+238h+var_1B0]
0x18001a5aa  mov     [rsp+238h+var_1D8], rax
0x18001a5af  lea     rax, aMdmClientcerti_4; "MDM_ClientCertificateInstall_Install03"
0x18001a5b6  mov     [rsp+238h+var_1D0], rax
0x18001a5bb  lea     rcx, [rsp+238h+var_1B0]
0x18001a5c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18001a5c8  mov     eax, cs:dword_180380B68
0x18001a5ce  cmp     eax, 5
0x18001a5d1  jbe     short loc_18001A643
0x18001a5d3  mov     rdx, 200000000000h
0x18001a5dd  lea     rcx, dword_180380B68
0x18001a5e4  call    _tlgKeywordOn
0x18001a5e9  test    al, al
0x18001a5eb  jz      short loc_18001A643
0x18001a5ed  cmp     [rsp+238h+var_1AC], dil
0x18001a5f5  jz      short loc_18001A625
0x18001a5f7  cmp     [rsp+238h+var_198], edi
0x18001a5fe  jnz     short loc_18001A61B
0x18001a600  cmp     [rsp+238h+var_194], edi
0x18001a607  jnz     short loc_18001A61B
0x18001a609  cmp     [rsp+238h+var_190], edi
0x18001a610  jnz     short loc_18001A61B
0x18001a612  cmp     [rsp+238h+var_18C], edi
0x18001a619  jz      short loc_18001A625
0x18001a61b  lea     r9, [rsp+238h+var_198]
0x18001a623  jmp     short loc_18001A628
0x18001a625  mov     r9, rdi
0x18001a628  lea     r8, [rsp+238h+var_1A8]
0x18001a630  lea     rdx, byte_1803423E3
0x18001a637  lea     rcx, dword_180380B68
0x18001a63e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a643  lea     rcx, [rsp+238h+var_1E0]; this
0x18001a648  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18001a64d  nop
0x18001a64e  mov     [rsp+238h+var_1E8], rdi
0x18001a653  lea     rax, [rsp+238h+var_1E8]
0x18001a658  mov     [rsp+238h+var_208], rax
0x18001a65d  mov     [rsp+238h+var_210], 2
0x18001a665  mov     [rsp+238h+var_218], 15h
0x18001a66d  lea     r9, ?MDM_ClientCertificateInstall_Install03_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_ClientCertificateInstall_Install03_NodeList
0x18001a674  xor     r8d, r8d
0x18001a677  xor     edx, edx
0x18001a679  mov     rcx, r12
0x18001a67c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18001a681  mov     r15d, eax
0x18001a684  test    eax, eax
0x18001a686  jz      short loc_18001A68D
0x18001a688  jmp     loc_18001ACAE
0x18001a68d  lea     rbx, [rsp+238h+var_1E8]
0x18001a692  mov     [rsp+238h+var_1C0], rbx
0x18001a697  mov     r14d, 1
0x18001a69d  mov     [rsp+238h+var_1B8], r14b
0x18001a6a5  mov     rsi, [rsp+238h+var_1E8]
0x18001a6aa  test    rsi, rsi
0x18001a6ad  jnz     short loc_18001A6B7
0x18001a6af  mov     r15d, r14d
0x18001a6b2  jmp     loc_18001ACAE
0x18001a6b7  mov     rax, [rsi]
0x18001a6ba  mov     rcx, rsi
0x18001a6bd  mov     rax, [rax+10h]
0x18001a6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6c6  mov     r15d, eax
0x18001a6c9  test    eax, eax
0x18001a6cb  jz      short loc_18001A6EB
0x18001a6cd  mov     rcx, [rsp+238h+var_1E8]
0x18001a6d2  test    rcx, rcx
0x18001a6d5  jz      short loc_18001A6E6
0x18001a6d7  mov     rax, [rcx]
0x18001a6da  mov     edx, r14d
0x18001a6dd  mov     rax, [rax]
0x18001a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6e5  nop
0x18001a6e6  jmp     loc_18001ACAE
0x18001a6eb  mov     rax, [rsi]
0x18001a6ee  mov     rcx, rsi
0x18001a6f1  mov     rax, [rax+8]
0x18001a6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6fa  mov     r15d, eax
0x18001a6fd  test    eax, eax
0x18001a6ff  jz      short loc_18001A71F
0x18001a701  mov     rcx, [rsp+238h+var_1E8]
0x18001a706  test    rcx, rcx
0x18001a709  jz      short loc_18001A71A
0x18001a70b  mov     rax, [rcx]
0x18001a70e  mov     edx, r14d
0x18001a711  mov     rax, [rax]
0x18001a714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a719  nop
0x18001a71a  jmp     loc_18001ACAE
0x18001a71f  mov     r14d, edi
0x18001a722  mov     rax, [rsi+108h]
0x18001a729  sub     rax, [rsi+100h]
0x18001a730  sar     rax, 4
0x18001a734  cmp     r14d, eax
0x18001a737  jnb     loc_18001AC76
0x18001a73d  lea     r8, [rsp+238h+instance]; instance
0x18001a745  lea     rdx, MDM_ClientCertificateInstall_Install03_rtti; classDecl
0x18001a74c  mov     rcx, r12; context
0x18001a74f  call    MI_Context_ConstructInstance
0x18001a754  mov     r15d, eax
0x18001a757  test    eax, eax
0x18001a759  jz      short loc_18001A77B
0x18001a75b  mov     rcx, [rbx]
0x18001a75e  test    rcx, rcx
0x18001a761  jz      short loc_18001A776
0x18001a763  mov     rax, [rcx]
0x18001a766  mov     edx, 1
0x18001a76b  mov     rax, [rax]
0x18001a76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a773  mov     [rbx], rdi
0x18001a776  jmp     loc_18001ACAE
0x18001a77b  mov     [rsp+238h+var_1F0], 1
0x18001a780  mov     rax, [rsi]
0x18001a783  lea     r9, [rsp+238h+String]
0x18001a788  lea     r8, aVendorMsftClie_2; "./Vendor/MSFT/ClientCertificateInstall/"...
0x18001a78f  mov     edx, r14d
0x18001a792  mov     rcx, rsi
0x18001a795  mov     rax, [rax+18h]
0x18001a799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a79e  test    eax, eax
0x18001a7a0  jnz     short loc_18001A7B9
0x18001a7a2  mov     rdx, [rsp+238h+String]
0x18001a7a7  test    rdx, rdx
0x18001a7aa  jz      short loc_18001A7B9
0x18001a7ac  lea     rcx, [rsp+238h+instance]
0x18001a7b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18001a7b9  mov     rax, [rsi]
0x18001a7bc  lea     r9, [rsp+238h+String]
0x18001a7c1  lea     r8, aVendorMsftClie; "./Vendor/MSFT/ClientCertificateInstall/"...
0x18001a7c8  mov     edx, r14d
0x18001a7cb  mov     rcx, rsi
0x18001a7ce  mov     rax, [rax+18h]
0x18001a7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7d7  test    eax, eax
0x18001a7d9  jnz     short loc_18001A7F2
0x18001a7db  mov     rdx, [rsp+238h+String]
0x18001a7e0  test    rdx, rdx
0x18001a7e3  jz      short loc_18001A7F2
0x18001a7e5  lea     rcx, [rsp+238h+instance]
0x18001a7ed  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18001a7f2  cmp     r13b, 1
0x18001a7f6  jnz     short loc_18001A81A
0x18001a7f8  lea     rdx, [rsp+238h+instance]
0x18001a800  mov     rcx, r12; self
0x18001a803  call    MI_Instance_Destruct
0x18001a808  lea     rcx, [rsp+238h+instance]; self
0x18001a810  call    MI_Instance_Destruct
0x18001a815  jmp     loc_18001AC69
0x18001a81a  mov     rax, [rsi]
0x18001a81d  lea     r9, [rsp+238h+String]
0x18001a822  lea     r8, aServerurl; "ServerURL"
0x18001a829  mov     edx, r14d
0x18001a82c  mov     rcx, rsi
0x18001a82f  mov     rax, [rax+18h]
0x18001a833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a838  test    eax, eax
0x18001a83a  jnz     short loc_18001A853
0x18001a83c  mov     rdx, [rsp+238h+String]
0x18001a841  test    rdx, rdx
0x18001a844  jz      short loc_18001A853
0x18001a846  lea     rcx, [rsp+238h+instance]
0x18001a84e  call    MDM_VPNv2_User_01_Set_EdpModeId
0x18001a853  mov     rax, [rsi]
0x18001a856  lea     r9, [rsp+238h+String]
0x18001a85b  lea     r8, aChallenge; "Challenge"
0x18001a862  mov     edx, r14d
0x18001a865  mov     rcx, rsi
0x18001a868  mov     rax, [rax+18h]
0x18001a86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a871  test    eax, eax
0x18001a873  jnz     short loc_18001A88C
0x18001a875  mov     rdx, [rsp+238h+String]
0x18001a87a  test    rdx, rdx
0x18001a87d  jz      short loc_18001A88C
0x18001a87f  lea     rcx, [rsp+238h+instance]
0x18001a887  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x18001a88c  mov     rax, [rsi]
0x18001a88f  lea     r9, [rsp+238h+String]
0x18001a894  lea     r8, aEkumapping; "EKUMapping"
0x18001a89b  mov     edx, r14d
0x18001a89e  mov     rcx, rsi
0x18001a8a1  mov     rax, [rax+18h]
0x18001a8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8aa  test    eax, eax
0x18001a8ac  jnz     short loc_18001A8C5
0x18001a8ae  mov     rdx, [rsp+238h+String]
0x18001a8b3  test    rdx, rdx
0x18001a8b6  jz      short loc_18001A8C5
0x18001a8b8  lea     rcx, [rsp+238h+instance]
0x18001a8c0  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18001a8c5  mov     rax, [rsi]
0x18001a8c8  lea     r9, [rsp+238h+String]
0x18001a8cd  lea     r8, aKeyusage; "KeyUsage"
0x18001a8d4  mov     edx, r14d
0x18001a8d7  mov     rcx, rsi
0x18001a8da  mov     rax, [rax+18h]
0x18001a8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8e3  test    eax, eax
0x18001a8e5  jnz     short loc_18001A906
0x18001a8e7  mov     rcx, [rsp+238h+String]; String
0x18001a8ec  test    rcx, rcx
0x18001a8ef  jz      short loc_18001A906
0x18001a8f1  call    cs:__imp__wtoi
0x18001a8f7  mov     [rsp+238h+var_F8], eax
0x18001a8fe  mov     [rsp+238h+var_F4], 1
0x18001a906  mov     rax, [rsi]
0x18001a909  lea     r9, [rsp+238h+String]
0x18001a90e  lea     r8, aSubjectname; "SubjectName"
0x18001a915  mov     edx, r14d
0x18001a918  mov     rcx, rsi
0x18001a91b  mov     rax, [rax+18h]
0x18001a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a924  test    eax, eax
0x18001a926  jnz     short loc_18001A93F
0x18001a928  mov     rdx, [rsp+238h+String]
0x18001a92d  test    rdx, rdx
0x18001a930  jz      short loc_18001A93F
0x18001a932  lea     rcx, [rsp+238h+instance]
0x18001a93a  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18001a93f  mov     rax, [rsi]
0x18001a942  lea     r9, [rsp+238h+String]
0x18001a947  lea     r8, aKeyprotection; "KeyProtection"
0x18001a94e  mov     edx, r14d
0x18001a951  mov     rcx, rsi
0x18001a954  mov     rax, [rax+18h]
0x18001a958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a95d  test    eax, eax
0x18001a95f  jnz     short loc_18001A980
0x18001a961  mov     rcx, [rsp+238h+String]; String
0x18001a966  test    rcx, rcx
0x18001a969  jz      short loc_18001A980
0x18001a96b  call    cs:__imp__wtoi
0x18001a971  mov     [rsp+238h+var_E0], eax
0x18001a978  mov     [rsp+238h+var_DC], 1
0x18001a980  mov     rax, [rsi]
0x18001a983  lea     r9, [rsp+238h+String]
0x18001a988  lea     r8, aRetrydelay; "RetryDelay"
0x18001a98f  mov     edx, r14d
0x18001a992  mov     rcx, rsi
0x18001a995  mov     rax, [rax+18h]
0x18001a999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99e  test    eax, eax
0x18001a9a0  jnz     short loc_18001A9C1
0x18001a9a2  mov     rcx, [rsp+238h+String]; String
0x18001a9a7  test    rcx, rcx
0x18001a9aa  jz      short loc_18001A9C1
0x18001a9ac  call    cs:__imp__wtoi
0x18001a9b2  mov     [rsp+238h+var_D8], eax
0x18001a9b9  mov     [rsp+238h+var_D4], 1
0x18001a9c1  mov     rax, [rsi]
0x18001a9c4  lea     r9, [rsp+238h+String]
0x18001a9c9  lea     r8, aRetrycount; "RetryCount"
0x18001a9d0  mov     edx, r14d
0x18001a9d3  mov     rcx, rsi
0x18001a9d6  mov     rax, [rax+18h]
0x18001a9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9df  test    eax, eax
0x18001a9e1  jnz     short loc_18001AA02
0x18001a9e3  mov     rcx, [rsp+238h+String]; String
0x18001a9e8  test    rcx, rcx
0x18001a9eb  jz      short loc_18001AA02
0x18001a9ed  call    cs:__imp__wtoi
0x18001a9f3  mov     [rsp+238h+var_D0], eax
0x18001a9fa  mov     [rsp+238h+var_CC], 1
0x18001aa02  mov     rax, [rsi]
0x18001aa05  lea     r9, [rsp+238h+String]
0x18001aa0a  lea     r8, aTemplatename; "TemplateName"
0x18001aa11  mov     edx, r14d
0x18001aa14  mov     rcx, rsi
0x18001aa17  mov     rax, [rax+18h]
0x18001aa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa20  test    eax, eax
0x18001aa22  jnz     short loc_18001AA3B
0x18001aa24  mov     rdx, [rsp+238h+String]
0x18001aa29  test    rdx, rdx
0x18001aa2c  jz      short loc_18001AA3B
  ... truncated ...
```
