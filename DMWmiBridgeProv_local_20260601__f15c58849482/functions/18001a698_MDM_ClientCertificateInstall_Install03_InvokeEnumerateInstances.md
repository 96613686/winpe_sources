# MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances

- ea: `0x18001a698`
- end: `0x18001aed7`
- name: `MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances`
- size: `2111`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050f0`
- `0x180005128`
- `0x180005160`
- `0x180005198`
- `0x180005278`
- `0x1800052b0`
- `0x1800052e8`
- `0x180005320`
- `0x180005358`
- `0x180005390`
- `0x1800053c8`
- `0x180005400`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18001a698`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18001aa55`
- `msvcrt!_wtoi` at `0x18001aad5`
- `msvcrt!_wtoi` at `0x18001ab1c`
- `msvcrt!_wtoi` at `0x18001ab63`
- `msvcrt!_wtoi` at `0x18001abe3`
- `msvcrt!_wtoi` at `0x18001ad0e`
- `msvcrt!_wtoi` at `0x18001aa55`
- `msvcrt!_wtoi` at `0x18001aad5`
- `msvcrt!_wtoi` at `0x18001ab1c`
- `msvcrt!_wtoi` at `0x18001ab63`
- `msvcrt!_wtoi` at `0x18001abe3`
- `msvcrt!_wtoi` at `0x18001ad0e`

## string_xrefs

- `0x18001ab86`: `TemplateName`
- `0x18001a8ec`: `./Vendor/MSFT/ClientCertificateInstall/SCEP/%s`
- `0x18001a925`: `./Vendor/MSFT/ClientCertificateInstall/SCEP/%s/Install`
- `0x18001a713`: `MDM_ClientCertificateInstall_Install03`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_ClientCertificateInstall_Install03_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+40h] [rbp-1F8h] BYREF
  char v14; // [rsp+48h] [rbp-1F0h]
  _QWORD *v15; // [rsp+50h] [rbp-1E8h] BYREF
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
    v7 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         0,
                         0,
                         &MDM_ClientCertificateInstall_Install03_NodeList,
                         21,
                         2,
                         &v15);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_ClientCertificateInstall_Install03_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v15;
                if ( v15 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v15)(v15, 1);
                  v15 = 0;
                }
                goto LABEL_103;
              }
              v14 = 1;
              if ( !(*(unsigned int (**)(_QWORD *, _QWORD, const wchar_t *, ...))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/ClientCertificateInstall/SCEP/%s",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (**)(_QWORD *, _QWORD, const wchar_t *, ...))(*v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ServerURL",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"Challenge",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EKUMapping",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"KeyUsage",
                        &String)
                  && String )
                {
                  v24 = _wtoi(String);
                  v25 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SubjectName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"KeyProtection",
                        &String)
                  && String )
                {
                  v26 = _wtoi(String);
                  v27 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RetryDelay",
                        &String)
                  && String )
                {
                  v28 = _wtoi(String);
                  v29 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RetryCount",
                        &String)
                  && String )
                {
                  v30 = _wtoi(String);
                  v31 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"TemplateName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"KeyLength",
                        &String)
                  && String )
                {
                  v32 = _wtoi(String);
                  v33 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HashAlgorithm",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CAThumbprint",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_ProfileXML(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"SubjectAlternativeNames",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ValidPeriod",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowIntranetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ValidPeriodUnits",
                        &String)
                  && String )
                {
                  v34 = _wtoi(String);
                  v35 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ContainerName",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLockedDownInternetZoneTemplate(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"CustomTextToShowInPrompt",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DataEncryption(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
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
    v7 = (int)v15;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a698  mov     [rsp+arg_8], rbx
0x18001a69d  mov     [rsp+arg_10], rsi
0x18001a6a2  push    rdi
0x18001a6a3  push    r12
0x18001a6a5  push    r13
0x18001a6a7  push    r14
0x18001a6a9  push    r15
0x18001a6ab  sub     rsp, 210h
0x18001a6b2  mov     rax, cs:__security_cookie
0x18001a6b9  xor     rax, rsp
0x18001a6bc  mov     [rsp+238h+var_38], rax
0x18001a6c4  mov     r13b, dl
0x18001a6c7  mov     r12, rcx
0x18001a6ca  xor     edx, edx; Val
0x18001a6cc  mov     r8d, 150h; Size
0x18001a6d2  lea     rcx, [rsp+238h+instance]; void *
0x18001a6da  call    memset_0
0x18001a6df  xor     edi, edi
0x18001a6e1  mov     [rsp+238h+var_1F0], dil
0x18001a6e6  mov     [rsp+238h+String], rdi
0x18001a6eb  mov     [rsp+238h+var_1B0], edi
0x18001a6f2  mov     [rsp+238h+var_1AC], dil
0x18001a6fa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18001a701  mov     [rsp+238h+var_1E0], rax
0x18001a706  lea     rax, [rsp+238h+var_1B0]
0x18001a70e  mov     [rsp+238h+var_1D8], rax
0x18001a713  lea     rax, aMdmClientcerti_4; "MDM_ClientCertificateInstall_Install03"
0x18001a71a  mov     [rsp+238h+var_1D0], rax
0x18001a71f  lea     rcx, [rsp+238h+var_1B0]
0x18001a727  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18001a72c  mov     eax, cs:dword_180380B68
0x18001a732  cmp     eax, 5
0x18001a735  jbe     short loc_18001A7A7
0x18001a737  mov     rdx, 200000000000h
0x18001a741  lea     rcx, dword_180380B68
0x18001a748  call    _tlgKeywordOn
0x18001a74d  test    al, al
0x18001a74f  jz      short loc_18001A7A7
0x18001a751  cmp     [rsp+238h+var_1AC], dil
0x18001a759  jz      short loc_18001A789
0x18001a75b  cmp     [rsp+238h+var_198], edi
0x18001a762  jnz     short loc_18001A77F
0x18001a764  cmp     [rsp+238h+var_194], edi
0x18001a76b  jnz     short loc_18001A77F
0x18001a76d  cmp     [rsp+238h+var_190], edi
0x18001a774  jnz     short loc_18001A77F
0x18001a776  cmp     [rsp+238h+var_18C], edi
0x18001a77d  jz      short loc_18001A789
0x18001a77f  lea     r9, [rsp+238h+var_198]
0x18001a787  jmp     short loc_18001A78C
0x18001a789  mov     r9, rdi
0x18001a78c  lea     r8, [rsp+238h+var_1A8]
0x18001a794  lea     rdx, byte_1803423E3
0x18001a79b  lea     rcx, dword_180380B68
0x18001a7a2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a7a7  lea     rcx, [rsp+238h+var_1E0]; this
0x18001a7ac  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18001a7b1  nop
0x18001a7b2  mov     [rsp+238h+var_1E8], rdi
0x18001a7b7  lea     rax, [rsp+238h+var_1E8]
0x18001a7bc  mov     [rsp+238h+var_208], rax
0x18001a7c1  mov     [rsp+238h+var_210], 2
0x18001a7c9  mov     [rsp+238h+var_218], 15h
0x18001a7d1  lea     r9, ?MDM_ClientCertificateInstall_Install03_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_ClientCertificateInstall_Install03_NodeList
0x18001a7d8  xor     r8d, r8d
0x18001a7db  xor     edx, edx
0x18001a7dd  mov     rcx, r12
0x18001a7e0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18001a7e5  mov     r15d, eax
0x18001a7e8  test    eax, eax
0x18001a7ea  jz      short loc_18001A7F1
0x18001a7ec  jmp     loc_18001AE36
0x18001a7f1  lea     rbx, [rsp+238h+var_1E8]
0x18001a7f6  mov     [rsp+238h+var_1C0], rbx
0x18001a7fb  mov     r14d, 1
0x18001a801  mov     [rsp+238h+var_1B8], r14b
0x18001a809  mov     rsi, [rsp+238h+var_1E8]
0x18001a80e  test    rsi, rsi
0x18001a811  jnz     short loc_18001A81B
0x18001a813  mov     r15d, r14d
0x18001a816  jmp     loc_18001AE36
0x18001a81b  mov     rax, [rsi]
0x18001a81e  mov     rcx, rsi
0x18001a821  mov     rax, [rax+10h]
0x18001a825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a82a  mov     r15d, eax
0x18001a82d  test    eax, eax
0x18001a82f  jz      short loc_18001A84F
0x18001a831  mov     rcx, [rsp+238h+var_1E8]
0x18001a836  test    rcx, rcx
0x18001a839  jz      short loc_18001A84A
0x18001a83b  mov     rax, [rcx]
0x18001a83e  mov     edx, r14d
0x18001a841  mov     rax, [rax]
0x18001a844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a849  nop
0x18001a84a  jmp     loc_18001AE36
0x18001a84f  mov     rax, [rsi]
0x18001a852  mov     rcx, rsi
0x18001a855  mov     rax, [rax+8]
0x18001a859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a85e  mov     r15d, eax
0x18001a861  test    eax, eax
0x18001a863  jz      short loc_18001A883
0x18001a865  mov     rcx, [rsp+238h+var_1E8]
0x18001a86a  test    rcx, rcx
0x18001a86d  jz      short loc_18001A87E
0x18001a86f  mov     rax, [rcx]
0x18001a872  mov     edx, r14d
0x18001a875  mov     rax, [rax]
0x18001a878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a87d  nop
0x18001a87e  jmp     loc_18001AE36
0x18001a883  mov     r14d, edi
0x18001a886  mov     rax, [rsi+108h]
0x18001a88d  sub     rax, [rsi+100h]
0x18001a894  sar     rax, 4
0x18001a898  cmp     r14d, eax
0x18001a89b  jnb     loc_18001ADFE
0x18001a8a1  lea     r8, [rsp+238h+instance]; instance
0x18001a8a9  lea     rdx, MDM_ClientCertificateInstall_Install03_rtti; classDecl
0x18001a8b0  mov     rcx, r12; context
0x18001a8b3  call    MI_Context_ConstructInstance
0x18001a8b8  mov     r15d, eax
0x18001a8bb  test    eax, eax
0x18001a8bd  jz      short loc_18001A8DF
0x18001a8bf  mov     rcx, [rbx]
0x18001a8c2  test    rcx, rcx
0x18001a8c5  jz      short loc_18001A8DA
0x18001a8c7  mov     rax, [rcx]
0x18001a8ca  mov     edx, 1
0x18001a8cf  mov     rax, [rax]
0x18001a8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8d7  mov     [rbx], rdi
0x18001a8da  jmp     loc_18001AE36
0x18001a8df  mov     [rsp+238h+var_1F0], 1
0x18001a8e4  mov     rax, [rsi]
0x18001a8e7  lea     r9, [rsp+238h+String]
0x18001a8ec  lea     r8, aVendorMsftClie_2; "./Vendor/MSFT/ClientCertificateInstall/"...
0x18001a8f3  mov     edx, r14d
0x18001a8f6  mov     rcx, rsi
0x18001a8f9  mov     rax, [rax+18h]
0x18001a8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a902  test    eax, eax
0x18001a904  jnz     short loc_18001A91D
0x18001a906  mov     rdx, [rsp+238h+String]
0x18001a90b  test    rdx, rdx
0x18001a90e  jz      short loc_18001A91D
0x18001a910  lea     rcx, [rsp+238h+instance]
0x18001a918  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18001a91d  mov     rax, [rsi]
0x18001a920  lea     r9, [rsp+238h+String]
0x18001a925  lea     r8, aVendorMsftClie; "./Vendor/MSFT/ClientCertificateInstall/"...
0x18001a92c  mov     edx, r14d
0x18001a92f  mov     rcx, rsi
0x18001a932  mov     rax, [rax+18h]
0x18001a936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a93b  test    eax, eax
0x18001a93d  jnz     short loc_18001A956
0x18001a93f  mov     rdx, [rsp+238h+String]
0x18001a944  test    rdx, rdx
0x18001a947  jz      short loc_18001A956
0x18001a949  lea     rcx, [rsp+238h+instance]
0x18001a951  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18001a956  cmp     r13b, 1
0x18001a95a  jnz     short loc_18001A97E
0x18001a95c  lea     rdx, [rsp+238h+instance]
0x18001a964  mov     rcx, r12; self
0x18001a967  call    MI_Instance_Destruct
0x18001a96c  lea     rcx, [rsp+238h+instance]; self
0x18001a974  call    MI_Instance_Destruct
0x18001a979  jmp     loc_18001ADF1
0x18001a97e  mov     rax, [rsi]
0x18001a981  lea     r9, [rsp+238h+String]
0x18001a986  lea     r8, aServerurl; "ServerURL"
0x18001a98d  mov     edx, r14d
0x18001a990  mov     rcx, rsi
0x18001a993  mov     rax, [rax+18h]
0x18001a997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99c  test    eax, eax
0x18001a99e  jnz     short loc_18001A9B7
0x18001a9a0  mov     rdx, [rsp+238h+String]
0x18001a9a5  test    rdx, rdx
0x18001a9a8  jz      short loc_18001A9B7
0x18001a9aa  lea     rcx, [rsp+238h+instance]
0x18001a9b2  call    MDM_VPNv2_User_01_Set_EdpModeId
0x18001a9b7  mov     rax, [rsi]
0x18001a9ba  lea     r9, [rsp+238h+String]
0x18001a9bf  lea     r8, aChallenge; "Challenge"
0x18001a9c6  mov     edx, r14d
0x18001a9c9  mov     rcx, rsi
0x18001a9cc  mov     rax, [rax+18h]
0x18001a9d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9d5  test    eax, eax
0x18001a9d7  jnz     short loc_18001A9F0
0x18001a9d9  mov     rdx, [rsp+238h+String]
0x18001a9de  test    rdx, rdx
0x18001a9e1  jz      short loc_18001A9F0
0x18001a9e3  lea     rcx, [rsp+238h+instance]
0x18001a9eb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x18001a9f0  mov     rax, [rsi]
0x18001a9f3  lea     r9, [rsp+238h+String]
0x18001a9f8  lea     r8, aEkumapping; "EKUMapping"
0x18001a9ff  mov     edx, r14d
0x18001aa02  mov     rcx, rsi
0x18001aa05  mov     rax, [rax+18h]
0x18001aa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa0e  test    eax, eax
0x18001aa10  jnz     short loc_18001AA29
0x18001aa12  mov     rdx, [rsp+238h+String]
0x18001aa17  test    rdx, rdx
0x18001aa1a  jz      short loc_18001AA29
0x18001aa1c  lea     rcx, [rsp+238h+instance]
0x18001aa24  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18001aa29  mov     rax, [rsi]
0x18001aa2c  lea     r9, [rsp+238h+String]
0x18001aa31  lea     r8, aKeyusage; "KeyUsage"
0x18001aa38  mov     edx, r14d
0x18001aa3b  mov     rcx, rsi
0x18001aa3e  mov     rax, [rax+18h]
0x18001aa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa47  test    eax, eax
0x18001aa49  jnz     short loc_18001AA70
0x18001aa4b  mov     rcx, [rsp+238h+String]; String
0x18001aa50  test    rcx, rcx
0x18001aa53  jz      short loc_18001AA70
0x18001aa55  call    cs:__imp__wtoi
0x18001aa5c  nop     dword ptr [rax+rax+00h]
0x18001aa61  mov     [rsp+238h+var_F8], eax
0x18001aa68  mov     [rsp+238h+var_F4], 1
0x18001aa70  mov     rax, [rsi]
0x18001aa73  lea     r9, [rsp+238h+String]
0x18001aa78  lea     r8, aSubjectname; "SubjectName"
0x18001aa7f  mov     edx, r14d
0x18001aa82  mov     rcx, rsi
0x18001aa85  mov     rax, [rax+18h]
0x18001aa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa8e  test    eax, eax
0x18001aa90  jnz     short loc_18001AAA9
0x18001aa92  mov     rdx, [rsp+238h+String]
0x18001aa97  test    rdx, rdx
0x18001aa9a  jz      short loc_18001AAA9
0x18001aa9c  lea     rcx, [rsp+238h+instance]
0x18001aaa4  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18001aaa9  mov     rax, [rsi]
0x18001aaac  lea     r9, [rsp+238h+String]
0x18001aab1  lea     r8, aKeyprotection; "KeyProtection"
0x18001aab8  mov     edx, r14d
0x18001aabb  mov     rcx, rsi
0x18001aabe  mov     rax, [rax+18h]
0x18001aac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aac7  test    eax, eax
0x18001aac9  jnz     short loc_18001AAF0
0x18001aacb  mov     rcx, [rsp+238h+String]; String
0x18001aad0  test    rcx, rcx
0x18001aad3  jz      short loc_18001AAF0
0x18001aad5  call    cs:__imp__wtoi
0x18001aadc  nop     dword ptr [rax+rax+00h]
0x18001aae1  mov     [rsp+238h+var_E0], eax
0x18001aae8  mov     [rsp+238h+var_DC], 1
0x18001aaf0  mov     rax, [rsi]
0x18001aaf3  lea     r9, [rsp+238h+String]
0x18001aaf8  lea     r8, aRetrydelay; "RetryDelay"
0x18001aaff  mov     edx, r14d
0x18001ab02  mov     rcx, rsi
0x18001ab05  mov     rax, [rax+18h]
0x18001ab09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab0e  test    eax, eax
0x18001ab10  jnz     short loc_18001AB37
0x18001ab12  mov     rcx, [rsp+238h+String]; String
0x18001ab17  test    rcx, rcx
0x18001ab1a  jz      short loc_18001AB37
0x18001ab1c  call    cs:__imp__wtoi
0x18001ab23  nop     dword ptr [rax+rax+00h]
0x18001ab28  mov     [rsp+238h+var_D8], eax
0x18001ab2f  mov     [rsp+238h+var_D4], 1
0x18001ab37  mov     rax, [rsi]
0x18001ab3a  lea     r9, [rsp+238h+String]
0x18001ab3f  lea     r8, aRetrycount; "RetryCount"
0x18001ab46  mov     edx, r14d
0x18001ab49  mov     rcx, rsi
0x18001ab4c  mov     rax, [rax+18h]
0x18001ab50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab55  test    eax, eax
0x18001ab57  jnz     short loc_18001AB7E
0x18001ab59  mov     rcx, [rsp+238h+String]; String
0x18001ab5e  test    rcx, rcx
0x18001ab61  jz      short loc_18001AB7E
0x18001ab63  call    cs:__imp__wtoi
0x18001ab6a  nop     dword ptr [rax+rax+00h]
0x18001ab6f  mov     [rsp+238h+var_D0], eax
0x18001ab76  mov     [rsp+238h+var_CC], 1
0x18001ab7e  mov     rax, [rsi]
0x18001ab81  lea     r9, [rsp+238h+String]
0x18001ab86  lea     r8, aTemplatename; "TemplateName"
0x18001ab8d  mov     edx, r14d
0x18001ab90  mov     rcx, rsi
0x18001ab93  mov     rax, [rax+18h]
0x18001ab97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab9c  test    eax, eax
  ... truncated ...
```
