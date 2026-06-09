# DoGetToken(AadContextFunctions *,void *,_SECURITY_LOGON_TYPE,_DECRYPTED_AUTH_DATA *,DiagnosticContext &,_AP_BLOB *,_AP_BLOB *,_APPLUGIN_USER_INFO * *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x18000f5cc`
- end: `0x180010b2f`
- name: `?DoGetToken@@YAJPEAVAadContextFunctions@@PEAXW4_SECURITY_LOGON_TYPE@@PEAU_DECRYPTED_AUTH_DATA@@AEAVDiagnosticContext@@PEAU_AP_BLOB@@5PEAPEAU_APPLUGIN_USER_INFO@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `5475`
- prototype: `__int64 __usercall@<rax>(struct AadContextFunctions *@<rcx>, struct _AadApPluginHandle *@<rdx>, enum _SECURITY_LOGON_TYPE@<r8d>, struct _DECRYPTED_AUTH_DATA *@<r9>, struct DiagnosticContext *, struct _AP_BLOB *, struct _AP_BLOB *, struct _APPLUGIN_USER_INFO **, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `63`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b580`

## callees

- `0x1800011b4`
- `0x180001280`
- `0x1800013b8`
- `0x1800014b8`
- `0x180001af4`
- `0x180001bb4`
- `0x180001cfc`
- `0x180001d28`
- `0x180003c20`
- `0x180003c44`
- `0x180004a24`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007bec`
- `0x1800090d0`
- `0x180009380`
- `0x180009f78`
- `0x18000f5cc`
- `0x18001a1a8`
- `0x18001a884`
- `0x18001a8fc`
- `0x18001ce38`
- `0x18001ceb4`
- `0x18001cf08`
- `0x18001d0ec`
- `0x18001d208`
- `0x18001dcf0`
- `0x18001f474`
- `0x180021cbc`
- `0x18002406c`
- `0x180027d18`
- `0x180028088`
- `0x180028418`
- `0x18002865c`
- `0x18002b430`
- `0x18002c144`
- `0x18002e624`
- `0x18002fde8`
- `0x18002fe50`
- `0x18002fec8`
- `0x180031a48`
- `0x180034590`
- `0x180036bf4`
- `0x180037e20`
- `0x180039414`
- `0x180039c10`
- `0x18003fd78`
- `0x180070678`
- `0x18007093c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fee4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fee4`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180010a40`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180010a40`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fc5e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000fc5e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800109b3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800109b3`
- `ntdll!RtlEqualSid` at `0x1800101b4`
- `ntdll!RtlEqualSid` at `0x1800101b4`

## string_xrefs

- `0x18000f6d8`: `DoGetToken`
- `0x18000f78f`: `DoGetToken`
- `0x18001081b`: `DoGetToken`
- `0x18000f925`: `Get token correlation ID`
- `0x18001006a`: `Token is expired`
- `0x180010399`: `Faild to get rbac vm type from registry, default back to Azure IMDS scenario`
- `0x18000fbbc`: `EnterpriseSTSTokenDisabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DoGetToken(
        struct AadContextFunctions *a1,
        struct _AadApPluginHandle *a2,
        unsigned int a3,
        struct _DECRYPTED_AUTH_DATA *a4,
        const WCHAR **a5,
        struct _AP_BLOB *a6,
        struct _AP_BLOB *a7,
        struct _APPLUGIN_USER_INFO **a8,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a9)
{
  char v13; // al
  GUID *v14; // rdx
  bool IsZero; // al
  GUID *p_ActivityId; // r9
  int LogonCredsFromAuthData; // ecx
  __int64 v18; // rdx
  DiagnosticContext *v19; // rsi
  struct _APPLUGIN_USER_INFO **v20; // rdi
  const WCHAR *v21; // rax
  __int64 v22; // r9
  const WCHAR *v23; // rcx
  unsigned int v24; // eax
  int v25; // esi
  struct _AadApPluginHandle *v26; // rdi
  int v27; // ecx
  AutoPasswordExpiryInfo *v28; // r13
  AutoPasswordExpiryInfo *v29; // rax
  int v30; // r13d
  int v31; // edi
  int v32; // r13d
  int v33; // eax
  __int64 v34; // rcx
  int v35; // esi
  __int64 v36; // r9
  struct _AadNetworkConfig **v37; // rdi
  struct _AadApPluginKeyInfo *v38; // rsi
  __int64 v39; // rcx
  int updated; // ecx
  bool v41; // al
  __int64 v42; // r8
  __int64 v43; // r9
  void *v44; // rcx
  struct _APPLUGIN_USER_INFO *v45; // rdx
  BOOLEAN v46; // al
  int v47; // edx
  unsigned __int64 v48; // rax
  __int64 v49; // rcx
  const wchar_t *v50; // r8
  char v51; // al
  __int64 v52; // r9
  const wchar_t *v53; // rax
  __int64 v54; // r9
  struct _APPLUGIN_USER_INFO *v55; // rcx
  AutoPasswordExpiryInfo *v56; // rdi
  __int64 v57; // rax
  int v58; // edi
  char DiagnosticMessage; // al
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v60; // rbx
  __int64 v61; // r9
  unsigned int v62; // ebx
  struct DiagnosticContext *v64; // [rsp+20h] [rbp-E0h]
  struct DiagnosticContext *v65; // [rsp+20h] [rbp-E0h]
  struct DiagnosticContext *v66; // [rsp+20h] [rbp-E0h]
  struct DiagnosticContext *v67; // [rsp+20h] [rbp-E0h]
  struct _AadApPluginKeyInfo *v68; // [rsp+28h] [rbp-D8h]
  struct _AAD_LOGON_CRED *v69; // [rsp+30h] [rbp-D0h]
  struct _AAD_LOGON_CRED *v70; // [rsp+30h] [rbp-D0h]
  struct _AAD_LOGON_CRED *v71; // [rsp+30h] [rbp-D0h]
  struct _AAD_LOGON_CRED *v72; // [rsp+30h] [rbp-D0h]
  unsigned int v73; // [rsp+50h] [rbp-B0h]
  int RbacVmType; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v75[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v76; // [rsp+78h] [rbp-88h] BYREF
  struct _APPLUGIN_USER_INFO **v77; // [rsp+80h] [rbp-80h]
  DiagnosticContext *v78; // [rsp+88h] [rbp-78h]
  struct _APPLUGIN_USER_INFO *v79; // [rsp+90h] [rbp-70h] BYREF
  bool v80[8]; // [rsp+98h] [rbp-68h] BYREF
  bool v81[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v82; // [rsp+A8h] [rbp-58h] BYREF
  __int64 DiagnosticMessageString; // [rsp+B0h] [rbp-50h] BYREF
  struct _AadApPluginHandle *v84; // [rsp+B8h] [rbp-48h]
  struct _APPLUGIN_USER_INFO *v85; // [rsp+C0h] [rbp-40h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v86; // [rsp+C8h] [rbp-38h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **v87; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v88; // [rsp+D8h] [rbp-28h] BYREF
  AutoPasswordExpiryInfo *v89; // [rsp+E0h] [rbp-20h]
  struct _AadApPluginHandle *v90; // [rsp+E8h] [rbp-18h] BYREF
  struct _DECRYPTED_AUTH_DATA *v91; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v92[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v93; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v94[3]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v95; // [rsp+168h] [rbp+68h]
  __int64 v96; // [rsp+178h] [rbp+78h]
  struct DiagnosticContext *v97; // [rsp+180h] [rbp+80h]
  _DWORD v98[24]; // [rsp+190h] [rbp+90h] BYREF
  const char *v99[6]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v100[112]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v101; // [rsp+290h] [rbp+190h]
  int v102; // [rsp+3D0h] [rbp+2D0h]
  int v103; // [rsp+3D8h] [rbp+2D8h]
  __int64 v104; // [rsp+3E0h] [rbp+2E0h]
  int v105; // [rsp+3E8h] [rbp+2E8h]
  int v106; // [rsp+3ECh] [rbp+2ECh]
  int v107; // [rsp+3F0h] [rbp+2F0h]
  _WORD *v108; // [rsp+3F8h] [rbp+2F8h]
  _BYTE v109[144]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v110[32]; // [rsp+520h] [rbp+420h] BYREF
  char v111; // [rsp+540h] [rbp+440h] BYREF
  __int64 v112; // [rsp+590h] [rbp+490h]
  __int64 v113; // [rsp+650h] [rbp+550h]
  int v114; // [rsp+658h] [rbp+558h]
  int v115; // [rsp+660h] [rbp+560h]
  int v116; // [rsp+670h] [rbp+570h]
  __int64 v117; // [rsp+674h] [rbp+574h]
  unsigned int v118; // [rsp+67Ch] [rbp+57Ch]
  __int128 v119; // [rsp+680h] [rbp+580h]
  int v120; // [rsp+700h] [rbp+600h] BYREF
  char v121; // [rsp+704h] [rbp+604h]
  _BYTE v122[16]; // [rsp+708h] [rbp+608h] BYREF
  GUID ActivityId; // [rsp+718h] [rbp+618h] BYREF
  struct _GUID v124; // [rsp+728h] [rbp+628h] BYREF
  struct _GUID v125; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v126[32]; // [rsp+750h] [rbp+650h] BYREF
  __int64 *v127; // [rsp+770h] [rbp+670h]
  __int64 v128; // [rsp+778h] [rbp+678h]
  _BYTE *v129; // [rsp+780h] [rbp+680h]
  __int64 v130; // [rsp+788h] [rbp+688h]

  v91 = a4;
  v84 = a2;
  v78 = (DiagnosticContext *)a5;
  DiagnosticMessageString = (__int64)a7;
  v77 = a8;
  v87 = a9;
  RbacVmType = 0;
  memset(v92, 0, sizeof(v92));
  memset_0(v100, 0, 0x268u);
  memset_0(v109, 0, 0x268u);
  v90 = a2;
  memset_0(v98, 0, sizeof(v98));
  v79 = 0;
  v85 = 0;
  v86 = 0;
  memset(v94, 0, sizeof(v94));
  v95 = 0;
  v96 = 0;
  v93 = 0;
  v124 = 0;
  v89 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v99,
    (int)"aadcloudap.cpp",
    (int)"DoGetToken",
    (int)&RbacVmType);
  v120 = 0;
  v121 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v120);
  if ( (unsigned int)dword_1800E5050 > 5 )
  {
    v13 = tlgKeywordOn(&dword_1800E5050, 0x400000000000LL);
    v14 = 0;
    if ( v13 )
    {
      *(_QWORD *)v81 = 0x1000000;
      if ( !v121 || (IsZero = _tlgGuidIsZero(&ActivityId), p_ActivityId = &ActivityId, IsZero) )
        p_ActivityId = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (__int64)&dword_1800E5050,
        (__int64)byte_1800D2B0D,
        (__int64)v122,
        (__int64)p_ActivityId,
        (__int64)v81);
    }
  }
  v97 = (struct DiagnosticContext *)a5;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
    a5 + 8,
    L"DoGetToken");
  if ( !a1 || !a2 || !v77 || !a7 )
  {
    LogonCredsFromAuthData = -1073741811;
    LODWORD(v69) = 1074;
    goto LABEL_164;
  }
  if ( !a4 )
  {
    LogonCredsFromAuthData = -2146893039;
    LODWORD(v69) = 1079;
LABEL_164:
    RbacVmType = LogonCredsFromAuthData;
    goto LABEL_165;
  }
  *v77 = 0;
  *(_QWORD *)a7 = 0;
  *((_QWORD *)a7 + 1) = 0;
  if ( v87 )
    *v87 = 0;
  if ( !PluginState::IsCloudDomainJoined((PluginState *)&v90) )
  {
    LODWORD(v64) = -2147187631;
    WPPTraceLogA(2, v18, "%x 0x%08x %s:%u : %s:%ws", 2, v64, "aadcloudap.cpp", 1092, "HRESULT", &base);
    RbacVmType = -1073445807;
    v19 = v78;
LABEL_17:
    v20 = v77;
LABEL_169:
    DiagnosticContext::LogDiagnosticEvent(v19, L"DoGetToken", RbacVmType, v92[1], (int)v92[2], 0, 0);
    goto LABEL_170;
  }
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(Microsoft_Windows_AAD_Context, Aad_CloudAPPlugin_GetToken_CorrelationID, a5[3]);
  v125 = *(struct _GUID *)(*(_QWORD *)a2 + 36LL);
  RegistryHelper::SetDWORDValue(a1, &v125, L"ForceNetworkLogon", 0, (bool)v64);
  WasTpmSucccessfullyResetSinceLastTime(a2, 1);
  LogonCredsFromAuthData = AuthBufferHelper::GetLogonCredsFromAuthData(a1, a4, (struct _AAD_LOGON_CRED *)v92, &v124);
  RbacVmType = LogonCredsFromAuthData;
  if ( LogonCredsFromAuthData < 0 )
  {
    LODWORD(v69) = 1105;
LABEL_165:
    LODWORD(v64) = LogonCredsFromAuthData;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v64, "aadcloudap.cpp", v69, "NTSTATUS", &base);
    goto LABEL_166;
  }
  v21 = &base;
  if ( a5[3] )
    v21 = a5[3];
  LODWORD(v64) = v92[2];
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, v64, "aadcloudap.cpp", 1107, "Get token correlation ID", v21);
  if ( v92[7] )
  {
    v64 = 0;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4);
    if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_CredBuffer_CorrelationID,
        v92[7],
        a5[3]);
  }
  if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v76 = a3;
    *(_DWORD *)v81 = v92[2];
    v23 = &base;
    if ( v92[7] )
      v23 = v92[7];
    v88 = (__int64)v23;
    v82 = (__int64)a5[3];
    *(_QWORD *)&v125.Data1 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800E5050,
      (__int64)word_1800D2A9A,
      (__int64)v122,
      v22,
      (__int64)&v125,
      (const WCHAR **)&v82,
      (const WCHAR **)&v88,
      (__int64)v81,
      (__int64)&v76);
  }
  if ( LODWORD(v92[2]) == 4 && a3 != 2 )
  {
    LogonCredsFromAuthData = -1073741790;
    LODWORD(v69) = 1140;
LABEL_35:
    RbacVmType = LogonCredsFromAuthData;
    goto LABEL_165;
  }
  LogonCredsFromAuthData = PluginState::CheckAuthorityUri((PluginState *)&v90, a1);
  RbacVmType = LogonCredsFromAuthData;
  if ( LogonCredsFromAuthData < 0 )
  {
    LODWORD(v69) = 1144;
    goto LABEL_165;
  }
  if ( (unsigned int)(LODWORD(v92[2]) - 6) <= 3 || LODWORD(v92[2]) == 4 )
  {
    v24 = 1;
    v98[0] = 1;
  }
  else
  {
    LogonCredsFromAuthData = GetUserRealm(
                               a1,
                               *(struct _AadNetworkConfig **)a2,
                               *((struct _AadApPluginJoinInfo **)a2 + 1),
                               *((_DWORD *)a2 + 10),
                               v78,
                               v92[1],
                               ((LODWORD(v92[2]) - 1) & 0xFFFFFFFD) == 0,
                               (struct _AadApPluginUserRealmInfo *)v98);
    RbacVmType = LogonCredsFromAuthData;
    if ( LogonCredsFromAuthData < 0 )
    {
      LODWORD(v69) = 1173;
      goto LABEL_165;
    }
    v24 = v98[0];
  }
  if ( v24 >= 2 )
  {
    LogonCredsFromAuthData = -1073741729;
    LODWORD(v69) = 1180;
    goto LABEL_35;
  }
  v25 = 64;
  if ( v24 )
  {
    v26 = v84;
  }
  else
  {
    v76 = 0;
    v26 = v84;
    v125 = *(struct _GUID *)(*(_QWORD *)v84 + 36LL);
    RegistryHelper::GetDWORDValue(a1, &v125, L"EnterpriseSTSTokenDisabled", &v76, (bool)v64);
    if ( v76 != 1 )
      v25 = 65;
  }
  if ( IsApBlobDefined(a6) )
  {
    v27 = TokenInfoSerializeHelper::DeserializeTokenInfo(a1, a6, &v85, (struct _AadApPluginTokenInfo *)v109);
    RbacVmType = v27;
    v28 = 0;
    if ( v27 < 0 )
    {
      LODWORD(v69) = 1203;
      LODWORD(v64) = v27;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v64, "aadcloudap.cpp", v69, "NTSTATUS", &base);
LABEL_166:
      v19 = v78;
      goto LABEL_167;
    }
    if ( v85 )
    {
      v29 = (AutoPasswordExpiryInfo *)malloc(0x20u);
      *(_QWORD *)&v125.Data1 = v29;
      if ( v29 )
        v28 = AutoPasswordExpiryInfo::AutoPasswordExpiryInfo(
                v29,
                a1,
                (struct _APPLUGIN_USER_INFO *)((char *)v85 + 96),
                v115 != 0);
      v89 = v28;
      if ( !v28 )
      {
        LogonCredsFromAuthData = -1073741801;
        LODWORD(v69) = 1210;
        goto LABEL_35;
      }
    }
    LODWORD(v94[0]) = v116;
    *(_QWORD *)((char *)v94 + 4) = v117;
    *(_QWORD *)((char *)&v94[1] + 4) = v118;
    v95 = v119;
    LODWORD(v96) = 0;
  }
  v30 = *((_DWORD *)v26 + 10);
  v31 = v25 | 0x20;
  v32 = v30 & 4;
  if ( v32 )
    v31 = v25;
  v33 = CheckCertificatePrivateKey(a1, 0);
  v35 = v33;
  if ( v33 < 0 )
  {
    if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v34, Aad_CloudAPPlugin_DeviceKeyTest_Error, (unsigned int)v33);
    LODWORD(v69) = 1233;
    LODWORD(v64) = v35;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v64, "aadcloudap.cpp", v69, "device key test error", &base);
    if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
    {
      *(_QWORD *)&v125.Data1 = "Certificate private key test failed";
      *(_DWORD *)v81 = v35;
      v82 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_1800E5050,
        (__int64)&byte_1800D2A5F,
        (__int64)v122,
        v36,
        (__int64)&v82,
        (__int64)v81,
        (const unsigned __int16 **)&v125);
    }
    if ( v32 )
    {
      LODWORD(v70) = 1239;
      LODWORD(v65) = v35;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v65, "aadcloudap.cpp", v70, "HRESULT", &base);
      RbacVmType = v35 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_166;
    }
    v37 = (struct _AadNetworkConfig **)v84;
    EnableAadRecoveryIfNecessary(v35, v84, L"Device certificate private key check");
    if ( !(unsigned __int8)CredTypeSupportsNoDeviceLogon(LODWORD(v92[2])) )
    {
      LODWORD(v70) = 1249;
      LODWORD(v65) = v35;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v65, "aadcloudap.cpp", v70, "HRESULT", &base);
      RbacVmType = v35 & 0xAFFFFFFF | 0x40000000;
      goto LABEL_166;
    }
    v19 = v78;
LABEL_122:
    if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(
        Microsoft_Windows_AAD_Context,
        Aad_CloudAPPlugin_LogonWithoutDeviceAuth_Error,
        *((_QWORD *)v19 + 3));
    updated = LogonIdentityNoDeviceAuth(
                a1,
                *v37,
                v37[1],
                v19,
                (struct _AAD_LOGON_CRED *)v92,
                v91,
                (struct _AadApPluginUserRealmInfo *)v98,
                &v79,
                (struct _AadApPluginTokenInfo *)v100,
                &v86);
    RbacVmType = updated;
    LODWORD(v42) = 0;
    if ( updated < 0 )
    {
      LODWORD(v71) = 1371;
      goto LABEL_95;
    }
    goto LABEL_126;
  }
  v38 = 0;
  if ( IsApBlobDefined((struct _AP_BLOB *)v110) )
  {
    v39 = *(_QWORD *)(*((_QWORD *)v84 + 1) + 72LL);
    if ( v39 )
    {
      if ( v112 && v114 == LODWORD(v92[2]) && !(unsigned int)_o__wcsicmp(v39, v112) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::GetImpl'::`2'::impl) )
        {
          if ( v113 && IsTimeOlderThan(v113, 2592000, 0) )
          {
            v31 |= 0x100u;
            if ( (Microsoft_Windows_AADEnableBits & 0x40) != 0 )
              McTemplateU0z_EventWriteTransfer(
                Microsoft_Windows_AAD_Context,
                Aad_CloudAPPlugin_DoGetToken_SessionKey_Needs_Roll,
                L"age");
            DiagnosticContext::AddDiagnosticMessage(v78, L"SkRolloverReason", L"age");
          }
          goto LABEL_84;
        }
        if ( !IsTimeOlderThan(v113, 2592000, 0) )
        {
LABEL_84:
          v38 = (struct _AadApPluginKeyInfo *)&v111;
          goto LABEL_88;
        }
        if ( v113 && (Microsoft_Windows_AADEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_DoGetToken_SessionKey_Needs_Roll,
            L"age");
      }
    }
  }
LABEL_88:
  v73 = v31;
  v68 = v38;
  v19 = v78;
  v37 = (struct _AadNetworkConfig **)v84;
  updated = LogonIdentity(
              a1,
              *(struct _AadNetworkConfig **)v84,
              *((struct _AadApPluginJoinInfo **)v84 + 1),
              v78,
              (struct _AP_BLOB *)v110,
              v68,
              (struct _AAD_LOGON_CRED *)v92,
              v91,
              (struct _AadApPluginUserRealmInfo *)v98,
              (struct _AadApPluginVsmBindingKeys *)v94,
              v73,
              &v79,
              (struct _AadApPluginTokenInfo *)v100,
              &v86);
  RbacVmType = updated;
  if ( updated < 0 )
  {
    if ( v32 )
    {
      LODWORD(v71) = 1349;
      goto LABEL_95;
    }
    EnableAadRecoveryIfNecessary(updated, (struct _AadApPluginHandle *)v37, L"Sign in (LogonIdentity)");
    v47 = RbacVmType;
    v48 = (unsigned int)(RbacVmType + 1073151997);
    if ( (unsigned int)v48 <= 0x2E && (v49 = 0x640000084001LL, _bittest64(&v49, v48))
      || RbacVmType == -1071053810
      || RbacVmType >= 0 )
    {
      if ( (unsigned __int8)CredTypeSupportsNoDeviceLogon(LODWORD(v92[2])) || v47 >= 0 )
        goto LABEL_122;
      LODWORD(v71) = 1342;
    }
    else
    {
      LODWORD(v71) = 1336;
    }
    LODWORD(v66) = v47;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v66, "aadcloudap.cpp", v71, "NTSTATUS", &base);
    goto LABEL_167;
  }
  v41 = IsTokenExpired((struct _AadApPluginTokenInfo *)v100);
  v42 = 0;
  if ( v41 )
  {
    RbacVmType = -1073740964;
    if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
    {
      *(_QWORD *)&v125.Data1 = "Token is expired";
      *(_DWORD *)v81 = RbacVmType;
      v82 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_1800E5050,
        (__int64)qword_1800D2A20,
        (__int64)v122,
        v43,
        (__int64)&v82,
        (__int64)v81,
        (const unsigned __int16 **)&v125);
      v42 = 0;
    }
    updated = RbacVmType;
    if ( RbacVmType < 0 )
    {
      LODWORD(v71) = 1318;
LABEL_95:
      LODWORD(v66) = updated;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v66, "aadcloudap.cpp", v71, "NTSTATUS", &base);
LABEL_167:
      v20 = v77;
      goto LABEL_168;
    }
  }
  if ( v104 == v42 && v113 > 0 )
    v104 = v113;
  if ( v32 )
  {
    if ( v108 && *v108 != (_WORD)v42 )
    {
      if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_Surrogate_SkipRbacLogon,
          v42,
          1,
          &v125);
        LODWORD(v42) = 0;
      }
      *((_DWORD *)v79 + 32) &= ~1u;
    }
    goto LABEL_105;
  }
LABEL_126:
  if ( !v108 || *v108 == (_WORD)v42 )
  {
    if ( (*((_BYTE *)v37[1] + 112) & 1) != 0 )
    {
      LODWORD(v71) = 1410;
      LODWORD(v66) = -2147187211;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        v66,
        "aadcloudap.cpp",
        v71,
        "RBAC resource ID is expected",
        &base);
      LODWORD(v72) = 1411;
      LODWORD(v67) = -2147187211;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v67, "aadcloudap.cpp", v72, "HRESULT", &base);
      RbacVmType = -1073445387;
      goto LABEL_17;
    }
    goto LABEL_105;
  }
  v76 = v42;
  RbacVmType = RegistryHelper::GetRbacVmType(&v76);
  if ( RbacVmType )
  {
    v76 = 0;
    LODWORD(v71) = 1386;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      4,
      0,
      "aadcloudap.cpp",
      v71,
      "Faild to get rbac vm type from registry, default back to Azure IMDS scenario",
      &base);
  }
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
  {
    v50 = L"Arc VM";
    if ( v76 != 1 )
      v50 = L"Azure VM";
    McTemplateU0z_EventWriteTransfer(Microsoft_Windows_AAD_Context, Aad_CloudAPPlugin_RbacLogon, v50);
  }
  updated = RBACHelper::UpdateUserGroupsCollection(a1, v79, (struct _AadApPluginTokenInfo *)v100);
  RbacVmType = updated;
  if ( updated < 0 )
  {
    LODWORD(v71) = 1393;
    goto LABEL_95;
  }
  RbacVmType = RBACHelper::CheckRoleBasedAccess(
                 a1,
                 (struct _AadApPluginHandle *)v37,
                 v19,
                 v79,
                 (struct _AadApPluginTokenInfo *)v100,
                 v76);
  if ( (unsigned int)dword_1800E5050 > 4 )
  {
    v51 = tlgKeywordOn(&dword_1800E5050, 0x400000000000LL);
    LODWORD(v42) = 0;
    if ( !v51 )
      goto LABEL_142;
    *(_DWORD *)v81 = RbacVmType;
    v53 = L"Arc Vm";
    if ( v76 != 1 )
      v53 = L"Azure Vm";
    *(_QWORD *)&v125.Data1 = v53;
    v82 = *((_QWORD *)v19 + 3);
    v88 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D29C9,
      (__int64)v122,
      v52,
      (__int64)&v88,
      (const WCHAR **)&v82,
      (const WCHAR **)&v125,
      (__int64)v81);
  }
  LODWORD(v42) = 0;
LABEL_142:
  updated = RbacVmType;
  if ( RbacVmType < 0 )
  {
    LODWORD(v71) = 1404;
    goto LABEL_95;
  }
LABEL_105:
  if ( !v85 || (v44 = (void *)*((_QWORD *)v85 + 2)) == 0 )
  {
LABEL_146:
    v45 = v79;
    goto LABEL_147;
  }
  v45 = v79;
  if ( v79 && *((_QWORD *)v79 + 2) )
  {
    v46 = RtlEqualSid(v44, *((PSID *)v79 + 2));
    LODWORD(v42) = 0;
    if ( !v46 )
    {
      LODWORD(v71) = 1426;
      LODWORD(v66) = -2147187621;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v66, "aadcloudap.cpp", v71, "HRESULT", &base);
      RbacVmType = -1073445797;
      goto LABEL_17;
    }
    goto LABEL_146;
  }
LABEL_147:
  v102 = v42;
  v105 = (int)v92[2];
  v106 = v98[0];
  if ( v89 && v107 != (_DWORD)v42 && *((_BYTE *)v89 + 24) == (_BYTE)v42 )
    AutoPasswordExpiryInfo::ApplyPasswordChangeUri(v89, v45, (struct _AadApPluginTokenInfo *)v100);
  updated = SetVsmBindingKeys(a1, (struct _AadApPluginVsmBindingKeys *)v94, (struct _AadApPluginTokenInfo *)v100);
  RbacVmType = updated;
  if ( updated < 0 )
  {
    LODWORD(v71) = 1442;
    goto LABEL_95;
  }
  updated = TokenInfoSerializeHelper::SerializeTokenInfo(a1, v100, &v93, 3);
  RbacVmType = updated;
  if ( updated < 0 )
  {
    LODWORD(v71) = 1445;
    goto LABEL_95;
  }
  if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v80[0] = v107 != 0;
    v75[0] = v103 != 0;
    *(_QWORD *)&v125.Data1 = v101;
    v82 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D296D,
      (__int64)v122,
      v54,
      (__int64)&v82,
      (__int64)&v125,
      (__int64)v75,
      (__int64)v80);
  }
  if ( LODWORD(v92[2]) == 8 )
    *((_DWORD *)v79 + 32) |= 4u;
  v55 = v79;
  v20 = v77;
  *v77 = v79;
  *(_OWORD *)DiagnosticMessageString = v93;
  DumpGroupSids(v55);
  v79 = 0;
  v93 = 0;
  if ( v87 )
  {
    *v87 = v86;
    v86 = 0;
  }
LABEL_168:
  if ( RbacVmType < 0 )
    goto LABEL_169;
LABEL_170:
  if ( RbacVmType == -1073741711 && v79 )
  {
    if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
    {
      v75[0] = *((_QWORD *)v79 + 12) != 0;
      DiagnosticMessageString = 2048;
      v129 = v75;
      v130 = 1;
      v127 = &DiagnosticMessageString;
      v128 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800E5050, byte_1800D2925, v122, 0, 4, v126);
    }
    *v20 = v79;
    v79 = 0;
  }
  v56 = v89;
  if ( v89 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)v89 + 1) - 24LL));
    operator delete(v56, (const struct std::nothrow_t *)0x20);
  }
  if ( a1 )
  {
    ReleaseUserInfoData(a1, &v85, (struct _AadApPluginTokenInfo *)v109);
    AuthBufferHelper::FreeLogonCredsContent(a1, (struct _AAD_LOGON_CRED *)v92);
    ReleaseTokenInfo(a1, (struct _AadApPluginTokenInfo *)v100);
    ReleaseUserRealmData(a1, (struct _AadApPluginUserRealmInfo *)v98);
    if ( v79 )
    {
      v57 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)a1 + 48LL))(a1);
      (*(void (__fastcall **)(struct _APPLUGIN_USER_INFO *))(v57 + 56))(v79);
    }
    AadContextFunctions::LsaFreeApBlob(a1, (struct _AP_BLOB *)&v93);
    if ( v86 )
      FreeSupplementalCredentials(a1, v86);
    ReleaseVsmBindingKeys(a1, (struct _AadApPluginVsmBindingKeys *)v94);
  }
  if ( v121 )
    EventActivityIdControl(4u, &ActivityId);
  v120 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    DiagnosticMessageString = (__int64)DiagnosticContext::GetDiagnosticMessageString(v19, L"SkRolloverSigningDeviceKey");
    *(_QWORD *)&v125.Data1 = DiagnosticContext::GetDiagnosticMessageString(v19, L"SkRolloverSigningSessionKey");
    v58 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
    DiagnosticMessage = DiagnosticContext::TryGetDiagnosticMessage(v19, L"deviceAuthFallbackCausedByError", &v87);
    v60 = v87;
    if ( DiagnosticMessage )
      v58 = _o__wtol(v87);
    ATL::CStringData::Release((ATL::CStringData *)(v60 - 3));
    *(_DWORD *)v81 = v58;
    v82 = (__int64)DiagnosticContext::GetDiagnosticMessageString(v19, L"SkRolloverReason");
    v76 = RbacVmType;
    v88 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5050,
      (__int64)byte_1800D2889,
      (__int64)v122,
      v61,
      (__int64)&v88,
      (__int64)&v76,
      (const WCHAR **)&v82,
      (__int64)v81,
      (const WCHAR **)&v125,
      (const WCHAR **)&DiagnosticMessageString);
  }
  v62 = RbacVmType;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveHead(
    (char *)v19 + 64,
    &DiagnosticMessageString);
  ATL::CStringData::Release((ATL::CStringData *)(DiagnosticMessageString - 24));
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v120);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v99);
  return v62;
}

```

## disassembly

```asm
0x18000f5cc  mov     [rsp-8+arg_8], rbx
0x18000f5d1  push    rbp
0x18000f5d2  push    rsi
0x18000f5d3  push    rdi
0x18000f5d4  push    r12
0x18000f5d6  push    r13
0x18000f5d8  push    r14
0x18000f5da  push    r15
0x18000f5dc  lea     rbp, [rsp-6A0h]
0x18000f5e4  sub     rsp, 7A0h
0x18000f5eb  mov     rax, cs:__security_cookie
0x18000f5f2  xor     rax, rsp
0x18000f5f5  mov     [rbp+6D0h+var_40], rax
0x18000f5fc  mov     r14, r9
0x18000f5ff  mov     [rbp+6D0h+var_6E0], r9
0x18000f603  mov     edi, r8d
0x18000f606  mov     rsi, rdx
0x18000f609  mov     [rbp+6D0h+var_718], rdx
0x18000f60d  mov     r12, rcx
0x18000f610  mov     rbx, [rbp+6D0h+arg_20]
0x18000f617  mov     [rbp+6D0h+var_748], rbx
0x18000f61b  mov     r13, [rbp+6D0h+arg_28]
0x18000f622  mov     r15, [rbp+6D0h+arg_30]
0x18000f629  mov     [rbp+6D0h+var_720], r15
0x18000f62d  mov     rax, [rbp+6D0h+arg_38]
0x18000f634  mov     [rbp+6D0h+var_750], rax
0x18000f638  mov     rcx, [rbp+6D0h+arg_40]
0x18000f63f  mov     [rbp+6D0h+var_700], rcx
0x18000f643  xor     eax, eax
0x18000f645  mov     [rsp+7D0h+var_760], eax
0x18000f649  mov     [rbp+6D0h+var_6D0], ax
0x18000f64d  xorps   xmm0, xmm0
0x18000f650  movups  xmmword ptr [rbp+6D0h+var_6CE], xmm0
0x18000f654  movups  [rbp+6D0h+var_6BE], xmm0
0x18000f658  movups  [rbp+6D0h+var_6AE], xmm0
0x18000f65c  movups  [rbp+6D0h+var_6AE+0Eh], xmm0
0x18000f660  xor     edx, edx; Val
0x18000f662  mov     r8d, 268h; Size
0x18000f668  lea     rcx, [rbp+6D0h+var_5B0]; void *
0x18000f66f  call    memset_0
0x18000f674  xor     edx, edx; Val
0x18000f676  mov     r8d, 268h; Size
0x18000f67c  lea     rcx, [rbp+6D0h+var_340]; void *
0x18000f683  call    memset_0
0x18000f688  mov     [rbp+6D0h+var_6E8], rsi
0x18000f68c  xor     edx, edx; Val
0x18000f68e  lea     r8d, [rdx+60h]; Size
0x18000f692  lea     rcx, [rbp+6D0h+var_640]; void *
0x18000f699  call    memset_0
0x18000f69e  xor     ecx, ecx
0x18000f6a0  mov     [rbp+6D0h+var_740], rcx
0x18000f6a4  mov     [rbp+6D0h+var_710], rcx
0x18000f6a8  mov     [rbp+6D0h+var_708], rcx
0x18000f6ac  mov     [rbp+6D0h+var_680], rcx
0x18000f6b0  xorps   xmm0, xmm0
0x18000f6b3  xor     eax, eax
0x18000f6b5  movups  [rbp+6D0h+var_678], xmm0
0x18000f6b9  movups  [rbp+6D0h+var_668], xmm0
0x18000f6bd  mov     [rbp+6D0h+var_658], rax
0x18000f6c1  movups  [rbp+6D0h+var_690], xmm0
0x18000f6c5  xorps   xmm1, xmm1
0x18000f6c8  movups  xmmword ptr [rbp+6D0h+var_A8.Data1], xmm1
0x18000f6cf  mov     [rbp+6D0h+var_6F0], rcx
0x18000f6d3  lea     r9, [rsp+7D0h+var_760]
0x18000f6d8  lea     r8, aDogettoken_0; "DoGetToken"
0x18000f6df  lea     rdx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000f6e6  lea     rcx, [rbp+6D0h+var_5E0]
0x18000f6ed  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18000f6f2  nop
0x18000f6f3  mov     [rbp+6D0h+var_D0], 0
0x18000f6fd  mov     [rbp+6D0h+var_CC], 0
0x18000f704  lea     rcx, [rbp+6D0h+var_D0]
0x18000f70b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x18000f710  mov     eax, cs:dword_1800E5050
0x18000f716  cmp     eax, 5
0x18000f719  jbe     short loc_18000F784
0x18000f71b  mov     rdx, 400000000000h
0x18000f725  lea     rcx, dword_1800E5050
0x18000f72c  call    _tlgKeywordOn
0x18000f731  xor     edx, edx
0x18000f733  test    al, al
0x18000f735  jz      short loc_18000F784
0x18000f737  mov     qword ptr [rbp+6D0h+var_730], 1000000h
0x18000f73f  cmp     [rbp+6D0h+var_CC], dl
0x18000f745  jz      short loc_18000F75E
0x18000f747  lea     rcx, [rbp+6D0h+ActivityId]; struct _GUID *
0x18000f74e  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18000f753  test    al, al
0x18000f755  lea     r9, [rbp+6D0h+ActivityId]
0x18000f75c  jz      short loc_18000F761
0x18000f75e  mov     r9, rdx
0x18000f761  lea     rax, [rbp+6D0h+var_730]
0x18000f765  mov     [rsp+7D0h+var_7B0], rax; bool
0x18000f76a  lea     r8, [rbp+6D0h+var_C8]
0x18000f771  lea     rdx, byte_1800D2B0D
0x18000f778  lea     rcx, dword_1800E5050
0x18000f77f  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18000f784  mov     [rbp+6D0h+var_650], rbx
0x18000f78b  lea     rcx, [rbx+40h]
0x18000f78f  lea     rdx, aDogettoken; "DoGetToken"
0x18000f796  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x18000f79b  nop
0x18000f79c  xor     edx, edx
0x18000f79e  test    r12, r12
0x18000f7a1  jz      loc_1800107A0
0x18000f7a7  test    rsi, rsi
0x18000f7aa  jz      loc_1800107A0
0x18000f7b0  mov     rax, [rbp+6D0h+var_750]
0x18000f7b4  test    rax, rax
0x18000f7b7  jz      loc_1800107A0
0x18000f7bd  test    r15, r15
0x18000f7c0  jz      loc_1800107A0
0x18000f7c6  test    r14, r14
0x18000f7c9  jnz     short loc_18000F7F5
0x18000f7cb  mov     ecx, 80090311h
0x18000f7d0  lea     r15, base
0x18000f7d7  mov     [rsp+7D0h+var_790], r15
0x18000f7dc  lea     rax, aNtstatus; "NTSTATUS"
0x18000f7e3  mov     [rsp+7D0h+var_798], rax
0x18000f7e8  mov     dword ptr [rsp+7D0h+var_7A0], 437h
0x18000f7f0  jmp     loc_1800107C5
0x18000f7f5  mov     [rax], rdx
0x18000f7f8  mov     [r15], rdx
0x18000f7fb  mov     [r15+8], rdx
0x18000f7ff  mov     rax, [rbp+6D0h+var_700]
0x18000f803  test    rax, rax
0x18000f806  jz      short loc_18000F80B
0x18000f808  mov     [rax], rdx
0x18000f80b  lea     rcx, [rbp+6D0h+var_6E8]; this
0x18000f80f  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x18000f814  test    al, al
0x18000f816  jnz     short loc_18000F87A
0x18000f818  lea     r15, base
0x18000f81f  mov     [rsp+7D0h+var_790], r15
0x18000f824  lea     rax, aHresult; "HRESULT"
0x18000f82b  mov     [rsp+7D0h+var_798], rax
0x18000f830  mov     dword ptr [rsp+7D0h+var_7A0], 444h
0x18000f838  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000f83f  mov     [rsp+7D0h+var_7A8], rax
0x18000f844  mov     dword ptr [rsp+7D0h+var_7B0], 80048451h
0x18000f84c  mov     ebx, 2
0x18000f851  mov     r9d, ebx
0x18000f854  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000f85b  mov     ecx, ebx
0x18000f85d  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000f862  mov     [rsp+7D0h+var_760], 0C0048451h
0x18000f86a  mov     rsi, [rbp+6D0h+var_748]
0x18000f86e  mov     rdi, [rbp+6D0h+var_750]
0x18000f872  xor     r13d, r13d
0x18000f875  jmp     loc_180010801
0x18000f87a  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18000f881  jz      short loc_18000F89A
0x18000f883  mov     r8, [rbx+18h]
0x18000f887  lea     rdx, Aad_CloudAPPlugin_GetToken_CorrelationID
0x18000f88e  lea     rcx, Microsoft_Windows_AAD_Context
0x18000f895  call    McTemplateU0z_EventWriteTransfer
0x18000f89a  mov     rax, [rsi]
0x18000f89d  movups  xmm0, xmmword ptr [rax+24h]
0x18000f8a1  movdqu  xmmword ptr [rbp+6D0h+var_90.Data1], xmm0
0x18000f8a9  xor     r9d, r9d; unsigned int
0x18000f8ac  lea     r8, aForcenetworklo; "ForceNetworkLogon"
0x18000f8b3  lea     rdx, [rbp+6D0h+var_90]; struct _GUID
0x18000f8ba  mov     rcx, r12; struct AadContextFunctions *
0x18000f8bd  call    ?SetDWORDValue@RegistryHelper@@CAJPEAVAadContextFunctions@@U_GUID@@PEBGK_N@Z; RegistryHelper::SetDWORDValue(AadContextFunctions *,_GUID,ushort const *,ulong,bool)
0x18000f8c2  mov     dl, 1; bool
0x18000f8c4  mov     rcx, rsi; struct _AadApPluginHandle *
0x18000f8c7  call    ?WasTpmSucccessfullyResetSinceLastTime@@YA_NPEAU_AadApPluginHandle@@_N@Z; WasTpmSucccessfullyResetSinceLastTime(_AadApPluginHandle *,bool)
0x18000f8cc  lea     r9, [rbp+6D0h+var_A8]; struct _GUID *
0x18000f8d3  lea     r8, [rbp+6D0h+var_6D0]; struct _AAD_LOGON_CRED *
0x18000f8d7  mov     rdx, r14; struct _DECRYPTED_AUTH_DATA *
0x18000f8da  mov     rcx, r12; this
0x18000f8dd  call    ?GetLogonCredsFromAuthData@AuthBufferHelper@@SAJPEAVAadContextFunctions@@PEAU_DECRYPTED_AUTH_DATA@@PEAU_AAD_LOGON_CRED@@PEAU_GUID@@@Z; AuthBufferHelper::GetLogonCredsFromAuthData(AadContextFunctions *,_DECRYPTED_AUTH_DATA *,_AAD_LOGON_CRED *,_GUID *)
0x18000f8e2  mov     ecx, eax
0x18000f8e4  mov     [rsp+7D0h+var_760], eax
0x18000f8e8  lea     r15, base
0x18000f8ef  test    eax, eax
0x18000f8f1  jns     short loc_18000F913
0x18000f8f3  mov     [rsp+7D0h+var_790], r15
0x18000f8f8  lea     rax, aNtstatus; "NTSTATUS"
0x18000f8ff  mov     [rsp+7D0h+var_798], rax
0x18000f904  mov     dword ptr [rsp+7D0h+var_7A0], 451h
0x18000f90c  xor     edx, edx
0x18000f90e  jmp     loc_1800107C9
0x18000f913  mov     rax, r15
0x18000f916  cmp     qword ptr [rbx+18h], 0
0x18000f91b  cmovnz  rax, [rbx+18h]
0x18000f920  mov     [rsp+7D0h+var_790], rax
0x18000f925  lea     rax, aGetTokenCorrel; "Get token correlation ID"
0x18000f92c  mov     [rsp+7D0h+var_798], rax
0x18000f931  mov     dword ptr [rsp+7D0h+var_7A0], 453h
0x18000f939  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000f940  mov     [rsp+7D0h+var_7A8], rax
0x18000f945  mov     eax, dword ptr [rbp+6D0h+var_6CE+0Eh]
0x18000f948  mov     dword ptr [rsp+7D0h+var_7B0], eax
0x18000f94c  mov     eax, 4
0x18000f951  mov     r9d, eax
0x18000f954  lea     r14, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000f95b  mov     r8, r14
0x18000f95e  xor     edx, edx
0x18000f960  mov     ecx, eax
0x18000f962  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000f967  mov     rax, [rbp+6D0h+var_698]
0x18000f96b  xor     r8d, r8d
0x18000f96e  test    rax, rax
0x18000f971  jz      short loc_18000F9D4
0x18000f973  mov     [rsp+7D0h+var_790], rax
0x18000f978  lea     rax, aCredbufferCorr; "Credbuffer correlation ID"
0x18000f97f  mov     [rsp+7D0h+var_798], rax
0x18000f984  mov     dword ptr [rsp+7D0h+var_7A0], 457h
0x18000f98c  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000f993  mov     [rsp+7D0h+var_7A8], rax
0x18000f998  mov     [rsp+7D0h+var_7B0], r8
0x18000f99d  lea     eax, [r8+4]
0x18000f9a1  mov     r9d, eax
0x18000f9a4  mov     r8, r14
0x18000f9a7  xor     edx, edx
0x18000f9a9  mov     ecx, eax
0x18000f9ab  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000f9b0  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18000f9b7  jz      short loc_18000F9D4
0x18000f9b9  mov     r9, [rbx+18h]
0x18000f9bd  mov     r8, [rbp+6D0h+var_698]
0x18000f9c1  lea     rdx, Aad_CloudAPPlugin_CredBuffer_CorrelationID
0x18000f9c8  lea     rcx, Microsoft_Windows_AAD_Context
0x18000f9cf  call    McTemplateU0zz_EventWriteTransfer
0x18000f9d4  mov     eax, cs:dword_1800E5050
0x18000f9da  cmp     eax, 4
0x18000f9dd  jbe     loc_18000FA77
0x18000f9e3  mov     rdx, 400000000000h
0x18000f9ed  lea     rcx, dword_1800E5050
0x18000f9f4  call    _tlgKeywordOn
0x18000f9f9  test    al, al
0x18000f9fb  jz      short loc_18000FA77
0x18000f9fd  mov     [rsp+7D0h+var_758], edi
0x18000fa01  mov     eax, dword ptr [rbp+6D0h+var_6CE+0Eh]
0x18000fa04  mov     dword ptr [rbp+6D0h+var_730], eax
0x18000fa07  mov     rcx, r15
0x18000fa0a  mov     rax, [rbp+6D0h+var_698]
0x18000fa0e  test    rax, rax
0x18000fa11  cmovnz  rcx, rax
0x18000fa15  mov     [rbp+6D0h+var_6F8], rcx
0x18000fa19  mov     rax, [rbx+18h]
0x18000fa1d  mov     [rbp+6D0h+var_728], rax
0x18000fa21  mov     qword ptr [rbp+6D0h+var_90.Data1], 800h
0x18000fa2c  lea     rax, [rsp+7D0h+var_758]
0x18000fa31  mov     [rsp+7D0h+var_790], rax
0x18000fa36  lea     rax, [rbp+6D0h+var_730]
0x18000fa3a  mov     [rsp+7D0h+var_798], rax
0x18000fa3f  lea     rax, [rbp+6D0h+var_6F8]
0x18000fa43  mov     [rsp+7D0h+var_7A0], rax
0x18000fa48  lea     rax, [rbp+6D0h+var_728]
0x18000fa4c  mov     [rsp+7D0h+var_7A8], rax
0x18000fa51  lea     rax, [rbp+6D0h+var_90]
0x18000fa58  mov     [rsp+7D0h+var_7B0], rax; bool
0x18000fa5d  lea     r8, [rbp+6D0h+var_C8]
0x18000fa64  lea     rdx, word_1800D2A9A
0x18000fa6b  lea     rcx, dword_1800E5050
0x18000fa72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000fa77  mov     ebx, 2
0x18000fa7c  cmp     dword ptr [rbp+6D0h+var_6CE+0Eh], 4
0x18000fa80  jnz     short loc_18000FAB2
0x18000fa82  cmp     edi, ebx
0x18000fa84  jz      short loc_18000FAB2
0x18000fa86  mov     ecx, 0C0000022h
0x18000fa8b  mov     [rsp+7D0h+var_790], r15
0x18000fa90  lea     rax, aNtstatus; "NTSTATUS"
0x18000fa97  mov     [rsp+7D0h+var_798], rax
0x18000fa9c  mov     dword ptr [rsp+7D0h+var_7A0], 474h
0x18000faa4  mov     [rsp+7D0h+var_760], ecx
0x18000faa8  mov     r8, r14
0x18000faab  xor     edx, edx
0x18000faad  jmp     loc_1800107D5
0x18000fab2  mov     rdx, r12; struct AadContextFunctions *
0x18000fab5  lea     rcx, [rbp+6D0h+var_6E8]; this
0x18000fab9  call    ?CheckAuthorityUri@PluginState@@QEAAJPEAVAadContextFunctions@@@Z; PluginState::CheckAuthorityUri(AadContextFunctions *)
0x18000fabe  mov     ecx, eax
0x18000fac0  mov     [rsp+7D0h+var_760], eax
0x18000fac4  xor     edi, edi
0x18000fac6  test    eax, eax
0x18000fac8  jns     short loc_18000FAE5
0x18000faca  mov     [rsp+7D0h+var_790], r15
0x18000facf  lea     rax, aNtstatus; "NTSTATUS"
0x18000fad6  mov     [rsp+7D0h+var_798], rax
0x18000fadb  mov     dword ptr [rsp+7D0h+var_7A0], 478h
0x18000fae3  jmp     short loc_18000FAA8
0x18000fae5  mov     ecx, dword ptr [rbp+6D0h+var_6CE+0Eh]
0x18000fae8  lea     eax, [rcx-6]
0x18000faeb  cmp     eax, 3
0x18000faee  jbe     short loc_18000FB65
0x18000faf0  cmp     ecx, 4
0x18000faf3  jz      short loc_18000FB65
0x18000faf5  lea     eax, [rcx-1]
0x18000faf8  test    eax, 0FFFFFFFDh
0x18000fafd  setz    al
0x18000fb00  lea     rcx, [rbp+6D0h+var_640]
0x18000fb07  mov     [rsp+7D0h+var_798], rcx; struct _AadApPluginUserRealmInfo *
0x18000fb0c  mov     byte ptr [rsp+7D0h+var_7A0], al; bool
0x18000fb10  mov     rax, [rbp+6D0h+var_6CE+6]
0x18000fb14  mov     [rsp+7D0h+var_7A8], rax; unsigned __int16 *
0x18000fb19  mov     rax, [rbp+6D0h+var_748]
  ... truncated ...
```
