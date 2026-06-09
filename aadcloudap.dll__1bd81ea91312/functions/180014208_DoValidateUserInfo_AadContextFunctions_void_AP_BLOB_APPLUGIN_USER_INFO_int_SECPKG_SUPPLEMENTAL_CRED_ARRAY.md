# DoValidateUserInfo(AadContextFunctions *,void *,_AP_BLOB *,_APPLUGIN_USER_INFO * *,int *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)

- ea: `0x180014208`
- end: `0x180014c0c`
- name: `?DoValidateUserInfo@@YAJPEAVAadContextFunctions@@PEAXPEAU_AP_BLOB@@PEAPEAU_APPLUGIN_USER_INFO@@PEAHPEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z`
- size: `2564`
- prototype: `int(struct AadContextFunctions *, void *, struct _AP_BLOB *, struct _APPLUGIN_USER_INFO **, int *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x1800011b4`
- `0x180001a34`
- `0x180001af4`
- `0x180001cfc`
- `0x180003c20`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180009f78`
- `0x180014208`
- `0x18001a1a8`
- `0x18001a8fc`
- `0x18001ce38`
- `0x18001cf08`
- `0x18001d0ec`
- `0x18001f458`
- `0x18001f474`
- `0x180023308`
- `0x180028088`
- `0x18002865c`
- `0x180034590`
- `0x180071e14`
- `0x1800727f8`
- `0x180078b18`
- `0x180078b98`
- `0x180078bfc`
- `0x1800790ac`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014564`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800145d3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014450`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014564`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800145d3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014b1e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014b1e`

## string_xrefs

- `0x180014716`: `Token is expired`
- `0x180014694`: `Token is restricted`
- `0x1800146be`: `Token is restricted`
- `0x1800146ec`: `Token is expired`
- `0x180014753`: `Enterprise token is expired`
- `0x18001477d`: `Enterprise token is expired`
- `0x1800147c9`: `Network config timeout`
- `0x1800147f3`: `Network config timeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DoValidateUserInfo(
        struct AadContextFunctions *a1,
        _QWORD *a2,
        struct _AP_BLOB *a3,
        const WCHAR *a4,
        unsigned int *a5,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a6)
{
  const wchar_t *v10; // rdi
  GUID *p_ActivityId; // r9
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // rcx
  bool v20; // al
  _QWORD *v21; // r12
  int v22; // eax
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v23; // r14
  struct _APPLUGIN_USER_INFO *v24; // rcx
  struct AadContextFunctions *v25; // rsi
  __int64 v26; // rax
  __int64 v27; // r9
  const WCHAR *v28; // rax
  unsigned int v29; // eax
  unsigned int v30; // ebx
  bool v32[8]; // [rsp+20h] [rbp-E0h]
  bool v33[8]; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h]
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v36; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  bool v38[8]; // [rsp+68h] [rbp-98h] BYREF
  struct _APPLUGIN_USER_INFO *v39; // [rsp+70h] [rbp-90h] BYREF
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v40; // [rsp+78h] [rbp-88h] BYREF
  struct AadContextFunctions *v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v43; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v44; // [rsp+98h] [rbp-68h] BYREF
  const char *v45; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v46; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  __int128 v49; // [rsp+D8h] [rbp-28h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  const char *v51[6]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v52[36]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v53[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v54; // [rsp+1C0h] [rbp+C0h]
  __int64 v55; // [rsp+1F8h] [rbp+F8h]
  __int64 v56; // [rsp+218h] [rbp+118h]
  __int64 v57; // [rsp+220h] [rbp+120h]
  int v58; // [rsp+258h] [rbp+158h]
  __int64 v59; // [rsp+260h] [rbp+160h]
  __int64 v60; // [rsp+280h] [rbp+180h]
  int v61; // [rsp+2D4h] [rbp+1D4h]
  int v62; // [rsp+2E8h] [rbp+1E8h]
  __int128 v63; // [rsp+300h] [rbp+200h]
  __int128 v64; // [rsp+310h] [rbp+210h]
  int v65; // [rsp+390h] [rbp+290h] BYREF
  char v66; // [rsp+394h] [rbp+294h]
  _BYTE v67[16]; // [rsp+398h] [rbp+298h] BYREF
  GUID ActivityId; // [rsp+3A8h] [rbp+2A8h] BYREF

  v43 = (WCHAR *)a4;
  v41 = a1;
  v42 = (__int64)a6;
  v10 = 0;
  v35 = 0;
  v44 = a2;
  memset_0(v52, 0, 0x268u);
  v39 = 0;
  v36 = 0;
  v40 = 0;
  v37 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v51,
    (int)"aadcloudap.cpp",
    (int)"DoValidateUserInfo",
    (int)&v35);
  v65 = 0;
  v66 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v65);
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    *(_QWORD *)v38 = 0x1000000;
    if ( !v66 || _tlgGuidIsZero(&ActivityId) )
      p_ActivityId = 0;
    else
      p_ActivityId = &ActivityId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_1800E5050,
      (__int64)&word_1800D2526,
      (__int64)v67,
      (__int64)p_ActivityId,
      (__int64)v38);
  }
  if ( !a1 || !a2 || !a4 || !a3 || !a5 )
  {
    v12 = -1073741811;
    v35 = -1073741811;
    LODWORD(v34) = 2072;
    goto LABEL_91;
  }
  *(_QWORD *)a4 = 0;
  *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !PluginState::IsCloudDomainJoined((PluginState *)&v44) )
  {
    *(_DWORD *)v32 = -2147187631;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v32, "aadcloudap.cpp", 2085, "HRESULT", &base);
    v35 = -1073445807;
LABEL_92:
    v23 = v36;
    goto LABEL_93;
  }
  v12 = TokenInfoSerializeHelper::DeserializeTokenInfo(a1, a3, &v39, (struct _AadApPluginTokenInfo *)v52);
  v35 = v12;
  if ( v12 < 0 )
  {
    LODWORD(v34) = 2093;
LABEL_91:
    *(_DWORD *)v32 = v12;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v32, "aadcloudap.cpp", v34, "NTSTATUS", &base);
    goto LABEL_92;
  }
  v13 = *(_QWORD *)(a2[1] + 24LL);
  if ( v13 && (!v55 || (unsigned int)_o__wcsicmp(v13, v55)) )
  {
    v35 = -1073741715;
    if ( (unsigned int)dword_1800E5050 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
    {
      v45 = "Tenant ID's don't match";
      *(_DWORD *)v38 = v35;
      *(_QWORD *)&v46.Data1 = 2048;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)&dword_1800E5050,
        (__int64)&byte_1800D24DF,
        (__int64)v67,
        v14,
        (__int64)&v46,
        (__int64)v38,
        (const unsigned __int16 **)&v45);
    }
    v12 = v35;
    if ( v35 < 0 )
    {
      LODWORD(v34) = 2101;
      goto LABEL_91;
    }
  }
  if ( v52[0] >= 3u )
  {
    v15 = *(_QWORD *)(a2[1] + 40LL);
    if ( v15 && (!v56 || (unsigned int)_o__wcsicmp(v15, v56)) )
    {
      *a5 = 1;
      v10 = L"Device ID's don't match";
      if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
          L"Device ID's don't match");
      LODWORD(v34) = 2121;
      WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Device ID's don't match", &base);
    }
    else
    {
      v16 = *(_QWORD *)(a2[1] + 72LL);
      if ( v16 && (!v57 || (unsigned int)_o__wcsicmp(v16, v57)) )
      {
        *a5 = 1;
        v10 = L"Device certificates don't match";
        if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
            L"Device certificates don't match");
        LODWORD(v34) = 2131;
        WPPTraceLogA(
          4,
          0,
          "%x 0x%08x %s:%u : %s:%ws",
          4,
          0,
          "aadcloudap.cpp",
          v34,
          "Device certificates don't match",
          &base);
      }
      else if ( IsApBlobDefined((struct _AP_BLOB *)v53) )
      {
        if ( v61 )
        {
          *a5 = 1;
          v10 = L"Token is restricted";
          if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
              L"Token is restricted");
          LODWORD(v34) = 2147;
          WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Token is restricted", &base);
        }
        else if ( IsTokenExpired((struct _AadApPluginTokenInfo *)v52) )
        {
          *a5 = 1;
          v10 = L"Token is expired";
          if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
              L"Token is expired");
          LODWORD(v34) = 2155;
          WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Token is expired", &base);
        }
        else if ( v58 && IsTimeOlderThan(v60, 3, 1) )
        {
          *a5 = 1;
          v10 = L"Enterprise token is expired";
          if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
              L"Enterprise token is expired");
          LODWORD(v34) = 2163;
          WPPTraceLogA(
            4,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            4,
            0,
            "aadcloudap.cpp",
            v34,
            "Enterprise token is expired",
            &base);
        }
        else if ( *(_DWORD *)(*a2 + 32LL) )
        {
          v17 = v59;
          if ( *((_DWORD *)a2 + 11) == 1 )
            v17 = v54;
          *a5 = IsTimeOlderThan(v17, 3600 * *(_DWORD *)(*a2 + 32LL), 1);
          v10 = L"Network config timeout";
          if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
              L"Network config timeout");
          LODWORD(v34) = 2174;
          WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Network config timeout", &base);
        }
        else if ( WasTpmSucccessfullyResetSinceLastTime((struct _AadApPluginHandle *)a2, 0) )
        {
          *a5 = 1;
          v10 = L"Successful TPM reset detected";
          if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
              L"Successful TPM reset detected");
          LODWORD(v34) = 2182;
          WPPTraceLogA(
            4,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            4,
            0,
            "aadcloudap.cpp",
            v34,
            "Successful TPM reset detected",
            &base);
        }
        else
        {
          v46 = *(struct _GUID *)(*a2 + 36LL);
          if ( (int)RegistryHelper::GetDWORDValue(v41, &v46, L"ForceNetworkLogon", &v37, v32[0]) >= 0 && v37 == 1 )
          {
            *a5 = 1;
            v10 = L"Force network logon";
            if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(
                Microsoft_Windows_AAD_Context,
                Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
                L"Force network logon");
            LODWORD(v34) = 2190;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Force network logon", &base);
          }
          else
          {
            v18 = 14400;
            if ( v62 == 8 )
              v18 = 3600;
            v19 = v59;
            if ( *((_DWORD *)a2 + 11) == 1 )
              v19 = v54;
            v20 = IsTimeOlderThan(v19, v18, 1);
            *a5 = v20;
            if ( v20 )
            {
              v10 = L"Timeout";
              if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
                McTemplateU0z_EventWriteTransfer(
                  Microsoft_Windows_AAD_Context,
                  Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
                  L"Timeout");
              LODWORD(v34) = 2203;
              WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Timeout", &base);
            }
          }
        }
      }
      else
      {
        *a5 = 1;
        v10 = L"PRT is missing";
        if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason,
            L"PRT is missing");
        LODWORD(v34) = 2139;
        WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "PRT is missing", &base);
      }
    }
  }
  else
  {
    *a5 = 1;
    v10 = L"Data version is old";
    LODWORD(v34) = 2111;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "aadcloudap.cpp", v34, "Data version is old", &base);
  }
  v21 = (_QWORD *)v42;
  if ( v42 && PluginState::IsAadJoined((PluginState *)&v44) )
  {
    v47 = v63;
    v48 = 0;
    v49 = v64;
    v50 = 0;
    v22 = BuildSupplementalCredentialsCollection(
            v41,
            (struct _AadApPluginTokenInfo *)v52,
            (struct _AadApPluginVsmBindingKeys *)&v47,
            &v40);
    v35 = v22;
    if ( v22 < 0 )
    {
      LODWORD(v34) = 2222;
      *(_DWORD *)v33 = v22;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)v33, "aadcloudap.cpp", v34, "NTSTATUS", &base);
      v23 = v40;
      goto LABEL_93;
    }
    *v21 = v40;
    v23 = 0;
  }
  else
  {
    v23 = v36;
  }
  v24 = v39;
  *(_QWORD *)v43 = v39;
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
  {
    McTemplateU0d_EventWriteTransfer(v24, Aad_CloudAPPlugin_Validation_Needed, *a5);
    v24 = v39;
  }
  DumpGroupSids(v24);
LABEL_93:
  v25 = v41;
  ReleaseTokenInfo(v41, (struct _AadApPluginTokenInfo *)v52);
  if ( v23 )
    FreeSupplementalCredentials(v25, v23);
  if ( v35 < 0 && v25 && v39 )
  {
    v26 = (*(__int64 (__fastcall **)(struct AadContextFunctions *))(*(_QWORD *)v25 + 48LL))(v25);
    (*(void (__fastcall **)(struct _APPLUGIN_USER_INFO *))(v26 + 56))(v39);
  }
  if ( v66 )
    EventActivityIdControl(4u, &ActivityId);
  v65 = 2;
  if ( (unsigned int)dword_1800E5050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v28 = L"N/A";
    if ( v10 )
      v28 = v10;
    v43 = (WCHAR *)v28;
    if ( a5 )
      v29 = *a5;
    else
      v29 = 0;
    *(_DWORD *)v38 = v29;
    LODWORD(v36) = v35;
    v42 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800E5050,
      (__int64)&byte_1800D247F,
      (__int64)v67,
      v27,
      (__int64)&v42,
      (__int64)&v36,
      (__int64)v38,
      (const WCHAR **)&v43);
  }
  v30 = v35;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v65);
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v51);
  return v30;
}

```

## disassembly

```asm
0x180014208  mov     [rsp-8+arg_8], rbx
0x18001420d  push    rbp
0x18001420e  push    rsi
0x18001420f  push    rdi
0x180014210  push    r12
0x180014212  push    r13
0x180014214  push    r14
0x180014216  push    r15
0x180014218  lea     rbp, [rsp-2C0h]
0x180014220  sub     rsp, 3C0h
0x180014227  mov     rax, cs:__security_cookie
0x18001422e  xor     rax, rsp
0x180014231  mov     [rbp+2F0h+var_38], rax
0x180014238  mov     r13, r9
0x18001423b  mov     [rbp+2F0h+var_360], r9
0x18001423f  mov     rbx, r8
0x180014242  mov     r12, rdx
0x180014245  mov     rsi, rcx
0x180014248  mov     [rbp+2F0h+var_370], rcx
0x18001424c  mov     r15, [rbp+2F0h+arg_20]
0x180014253  mov     r14, [rbp+2F0h+arg_28]
0x18001425a  mov     [rbp+2F0h+var_368], r14
0x18001425e  xor     edi, edi
0x180014260  mov     [rsp+3F0h+var_3A0], edi
0x180014264  mov     [rbp+2F0h+var_358], rdx
0x180014268  xor     edx, edx; Val
0x18001426a  mov     r8d, 268h; Size
0x180014270  lea     rcx, [rbp+2F0h+var_2D0]; void *
0x180014274  call    memset_0
0x180014279  mov     [rsp+3F0h+var_380], rdi
0x18001427e  mov     eax, edi
0x180014280  mov     [rsp+3F0h+var_398], rax
0x180014285  mov     [rsp+3F0h+var_378], rax
0x18001428a  mov     [rsp+3F0h+var_390], edi
0x18001428e  lea     r9, [rsp+3F0h+var_3A0]
0x180014293  lea     r8, aDovalidateuser; "DoValidateUserInfo"
0x18001429a  lea     rdx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x1800142a1  lea     rcx, [rbp+2F0h+var_300]
0x1800142a5  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x1800142aa  nop
0x1800142ab  mov     [rbp+2F0h+var_60], edi
0x1800142b1  mov     [rbp+2F0h+var_5C], dil
0x1800142b8  lea     rcx, [rbp+2F0h+var_60]
0x1800142bf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_traceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_traceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800142c4  mov     eax, cs:dword_1800E5050
0x1800142ca  cmp     eax, 5
0x1800142cd  jbe     short loc_18001433B
0x1800142cf  mov     rdx, 400000000000h
0x1800142d9  lea     rcx, dword_1800E5050
0x1800142e0  call    _tlgKeywordOn
0x1800142e5  test    al, al
0x1800142e7  jz      short loc_18001433B
0x1800142e9  mov     qword ptr [rsp+3F0h+var_388], 1000000h
0x1800142f2  cmp     [rbp+2F0h+var_5C], dil
0x1800142f9  jz      short loc_180014314
0x1800142fb  lea     rcx, [rbp+2F0h+ActivityId]; struct _GUID *
0x180014302  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180014307  test    al, al
0x180014309  jnz     short loc_180014314
0x18001430b  lea     r9, [rbp+2F0h+ActivityId]
0x180014312  jmp     short loc_180014317
0x180014314  xor     r9d, r9d
0x180014317  lea     rax, [rsp+3F0h+var_388]
0x18001431c  mov     qword ptr [rsp+3F0h+var_3D0], rax; bool
0x180014321  lea     r8, [rbp+2F0h+var_58]
0x180014328  lea     rdx, word_1800D2526
0x18001432f  lea     rcx, dword_1800E5050
0x180014336  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18001433b  test    rsi, rsi
0x18001433e  jz      loc_180014A60
0x180014344  test    r12, r12
0x180014347  jz      loc_180014A60
0x18001434d  test    r13, r13
0x180014350  jz      loc_180014A60
0x180014356  test    rbx, rbx
0x180014359  jz      loc_180014A60
0x18001435f  test    r15, r15
0x180014362  jz      loc_180014A60
0x180014368  mov     qword ptr [r13+0], 0
0x180014370  mov     dword ptr [r15], 0
0x180014377  test    r14, r14
0x18001437a  jz      short loc_180014383
0x18001437c  mov     qword ptr [r14], 0
0x180014383  lea     rcx, [rbp+2F0h+var_358]; this
0x180014387  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x18001438c  test    al, al
0x18001438e  jnz     short loc_1800143EB
0x180014390  lea     r14, base
0x180014397  mov     [rsp+3F0h+var_3B0], r14
0x18001439c  lea     rax, aHresult; "HRESULT"
0x1800143a3  mov     [rsp+3F0h+var_3B8], rax
0x1800143a8  mov     dword ptr [rsp+3F0h+var_3C0], 825h
0x1800143b0  lea     rcx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x1800143b7  mov     [rsp+3F0h+var_3C8], rcx
0x1800143bc  mov     dword ptr [rsp+3F0h+var_3D0], 80048451h
0x1800143c4  mov     r13d, 2
0x1800143ca  mov     r9d, r13d
0x1800143cd  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800143d4  xor     edx, edx
0x1800143d6  mov     ecx, r13d
0x1800143d9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800143de  mov     [rsp+3F0h+var_3A0], 0C0048451h
0x1800143e6  jmp     loc_180014AB3
0x1800143eb  lea     r9, [rbp+2F0h+var_2D0]; struct _AadApPluginTokenInfo *
0x1800143ef  lea     r8, [rsp+3F0h+var_380]; struct _APPLUGIN_USER_INFO **
0x1800143f4  mov     rdx, rbx; struct _AP_BLOB *
0x1800143f7  mov     rcx, rsi; struct AadContextFunctions *
0x1800143fa  call    ?DeserializeTokenInfo@TokenInfoSerializeHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@PEAPEAU_APPLUGIN_USER_INFO@@PEAU_AadApPluginTokenInfo@@@Z; TokenInfoSerializeHelper::DeserializeTokenInfo(AadContextFunctions *,_AP_BLOB *,_APPLUGIN_USER_INFO * *,_AadApPluginTokenInfo *)
0x1800143ff  mov     [rsp+3F0h+var_3A0], eax
0x180014403  mov     r13d, 2
0x180014409  test    eax, eax
0x18001440b  jns     short loc_180014432
0x18001440d  lea     r14, base
0x180014414  mov     [rsp+3F0h+var_3B0], r14
0x180014419  lea     rcx, aNtstatus; "NTSTATUS"
0x180014420  mov     [rsp+3F0h+var_3B8], rcx
0x180014425  mov     dword ptr [rsp+3F0h+var_3C0], 82Dh
0x18001442d  jmp     loc_180014A8F
0x180014432  mov     rax, [r12+8]
0x180014437  mov     rcx, [rax+18h]
0x18001443b  test    rcx, rcx
0x18001443e  jz      loc_180014509
0x180014444  mov     rdx, [rbp+2F0h+var_1F8]
0x18001444b  test    rdx, rdx
0x18001444e  jz      short loc_18001445E
0x180014450  call    cs:__imp__o__wcsicmp
0x180014456  test    eax, eax
0x180014458  jz      loc_180014509
0x18001445e  mov     [rsp+3F0h+var_3A0], 0C000006Dh
0x180014466  mov     eax, cs:dword_1800E5050
0x18001446c  cmp     eax, r13d
0x18001446f  jbe     short loc_1800144DC
0x180014471  mov     rdx, 400000000000h
0x18001447b  lea     rcx, dword_1800E5050
0x180014482  call    _tlgKeywordOn
0x180014487  test    al, al
0x180014489  jz      short loc_1800144DC
0x18001448b  lea     rax, aTenantIdSDonTM; "Tenant ID's don't match"
0x180014492  mov     [rbp+2F0h+var_350], rax
0x180014496  mov     eax, [rsp+3F0h+var_3A0]
0x18001449a  mov     dword ptr [rsp+3F0h+var_388], eax
0x18001449e  mov     qword ptr [rbp+2F0h+var_340.Data1], 800h
0x1800144a6  lea     rax, [rbp+2F0h+var_350]
0x1800144aa  mov     [rsp+3F0h+var_3C0], rax
0x1800144af  lea     rax, [rsp+3F0h+var_388]
0x1800144b4  mov     [rsp+3F0h+var_3C8], rax
0x1800144b9  lea     rax, [rbp+2F0h+var_340]
0x1800144bd  mov     qword ptr [rsp+3F0h+var_3D0], rax
0x1800144c2  lea     r8, [rbp+2F0h+var_58]
0x1800144c9  lea     rdx, byte_1800D24DF
0x1800144d0  lea     rcx, dword_1800E5050
0x1800144d7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800144dc  mov     eax, [rsp+3F0h+var_3A0]
0x1800144e0  test    eax, eax
0x1800144e2  jns     short loc_180014509
0x1800144e4  lea     r14, base
0x1800144eb  mov     [rsp+3F0h+var_3B0], r14
0x1800144f0  lea     rcx, aNtstatus; "NTSTATUS"
0x1800144f7  mov     [rsp+3F0h+var_3B8], rcx
0x1800144fc  mov     dword ptr [rsp+3F0h+var_3C0], 835h
0x180014504  jmp     loc_180014A8F
0x180014509  lea     r14, base
0x180014510  lea     rsi, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180014517  cmp     [rbp+2F0h+var_2D0], 3
0x18001451b  jnb     short loc_18001454A
0x18001451d  mov     ebx, 1
0x180014522  mov     [r15], ebx
0x180014525  lea     rdi, aDataVersionIsO_0; "Data version is old"
0x18001452c  mov     [rsp+3F0h+var_3B0], r14
0x180014531  lea     rax, aDataVersionIsO; "Data version is old"
0x180014538  mov     [rsp+3F0h+var_3B8], rax
0x18001453d  mov     dword ptr [rsp+3F0h+var_3C0], 83Fh
0x180014545  jmp     loc_18001494B
0x18001454a  mov     rax, [r12+8]
0x18001454f  mov     rcx, [rax+28h]
0x180014553  test    rcx, rcx
0x180014556  jz      short loc_1800145B9
0x180014558  mov     rdx, [rbp+2F0h+var_1D8]
0x18001455f  test    rdx, rdx
0x180014562  jz      short loc_18001456E
0x180014564  call    cs:__imp__o__wcsicmp
0x18001456a  test    eax, eax
0x18001456c  jz      short loc_1800145B9
0x18001456e  mov     ebx, 1
0x180014573  mov     [r15], ebx
0x180014576  lea     rdi, aDeviceIdSDonTM; "Device ID's don't match"
0x18001457d  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x180014583  jz      short loc_18001459B
0x180014585  mov     r8, rdi
0x180014588  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x18001458f  lea     rcx, Microsoft_Windows_AAD_Context
0x180014596  call    McTemplateU0z_EventWriteTransfer
0x18001459b  mov     [rsp+3F0h+var_3B0], r14
0x1800145a0  lea     rax, aDeviceIdSDonTM_0; "Device ID's don't match"
0x1800145a7  mov     [rsp+3F0h+var_3B8], rax
0x1800145ac  mov     dword ptr [rsp+3F0h+var_3C0], 849h
0x1800145b4  jmp     loc_18001494B
0x1800145b9  mov     rax, [r12+8]
0x1800145be  mov     rcx, [rax+48h]
0x1800145c2  test    rcx, rcx
0x1800145c5  jz      short loc_180014628
0x1800145c7  mov     rdx, [rbp+2F0h+var_1D0]
0x1800145ce  test    rdx, rdx
0x1800145d1  jz      short loc_1800145DD
0x1800145d3  call    cs:__imp__o__wcsicmp
0x1800145d9  test    eax, eax
0x1800145db  jz      short loc_180014628
0x1800145dd  mov     ebx, 1
0x1800145e2  mov     [r15], ebx
0x1800145e5  lea     rdi, aDeviceCertific_0; "Device certificates don't match"
0x1800145ec  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x1800145f2  jz      short loc_18001460A
0x1800145f4  mov     r8, rdi
0x1800145f7  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x1800145fe  lea     rcx, Microsoft_Windows_AAD_Context
0x180014605  call    McTemplateU0z_EventWriteTransfer
0x18001460a  mov     [rsp+3F0h+var_3B0], r14
0x18001460f  lea     rax, aDeviceCertific_1; "Device certificates don't match"
0x180014616  mov     [rsp+3F0h+var_3B8], rax
0x18001461b  mov     dword ptr [rsp+3F0h+var_3C0], 853h
0x180014623  jmp     loc_18001494B
0x180014628  lea     rcx, [rbp+2F0h+var_240]; struct _AP_BLOB *
0x18001462f  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x180014634  test    al, al
0x180014636  jnz     short loc_180014683
0x180014638  mov     ebx, 1
0x18001463d  mov     [r15], ebx
0x180014640  lea     rdi, aPrtIsMissing; "PRT is missing"
0x180014647  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x18001464d  jz      short loc_180014665
0x18001464f  mov     r8, rdi
0x180014652  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x180014659  lea     rcx, Microsoft_Windows_AAD_Context
0x180014660  call    McTemplateU0z_EventWriteTransfer
0x180014665  mov     [rsp+3F0h+var_3B0], r14
0x18001466a  lea     rax, aPrtIsMissing_0; "PRT is missing"
0x180014671  mov     [rsp+3F0h+var_3B8], rax
0x180014676  mov     dword ptr [rsp+3F0h+var_3C0], 85Bh
0x18001467e  jmp     loc_18001494B
0x180014683  cmp     [rbp+2F0h+var_11C], 0
0x18001468a  jz      short loc_1800146D7
0x18001468c  mov     ebx, 1
0x180014691  mov     [r15], ebx
0x180014694  lea     rdi, aTokenIsRestric_0; "Token is restricted"
0x18001469b  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x1800146a1  jz      short loc_1800146B9
0x1800146a3  mov     r8, rdi
0x1800146a6  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x1800146ad  lea     rcx, Microsoft_Windows_AAD_Context
0x1800146b4  call    McTemplateU0z_EventWriteTransfer
0x1800146b9  mov     [rsp+3F0h+var_3B0], r14
0x1800146be  lea     rax, aTokenIsRestric; "Token is restricted"
0x1800146c5  mov     [rsp+3F0h+var_3B8], rax
0x1800146ca  mov     dword ptr [rsp+3F0h+var_3C0], 863h
0x1800146d2  jmp     loc_18001494B
0x1800146d7  lea     rcx, [rbp+2F0h+var_2D0]; struct _AadApPluginTokenInfo *
0x1800146db  call    ?IsTokenExpired@@YA_NPEAU_AadApPluginTokenInfo@@@Z; IsTokenExpired(_AadApPluginTokenInfo *)
0x1800146e0  mov     ebx, 1
0x1800146e5  test    al, al
0x1800146e7  jz      short loc_18001472F
0x1800146e9  mov     [r15], ebx
0x1800146ec  lea     rdi, aTokenIsExpired_0; "Token is expired"
0x1800146f3  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x1800146f9  jz      short loc_180014711
0x1800146fb  mov     r8, rdi
0x1800146fe  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x180014705  lea     rcx, Microsoft_Windows_AAD_Context
0x18001470c  call    McTemplateU0z_EventWriteTransfer
0x180014711  mov     [rsp+3F0h+var_3B0], r14
0x180014716  lea     rax, aTokenIsExpired; "Token is expired"
0x18001471d  mov     [rsp+3F0h+var_3B8], rax
0x180014722  mov     dword ptr [rsp+3F0h+var_3C0], 86Bh
0x18001472a  jmp     loc_18001494B
0x18001472f  cmp     [rbp+2F0h+var_198], 0
0x180014736  jz      short loc_180014796
0x180014738  mov     r8b, bl; bool
0x18001473b  mov     edx, 3; int
0x180014740  mov     rcx, [rbp+2F0h+var_170]; __int64
0x180014747  call    ?IsTimeOlderThan@@YA_N_JH_N@Z; IsTimeOlderThan(__int64,int,bool)
0x18001474c  test    al, al
0x18001474e  jz      short loc_180014796
0x180014750  mov     [r15], ebx
0x180014753  lea     rdi, aEnterpriseToke_0; "Enterprise token is expired"
0x18001475a  test    byte ptr cs:Microsoft_Windows_AADEnableBits, bl
0x180014760  jz      short loc_180014778
0x180014762  mov     r8, rdi
0x180014765  lea     rdx, Aad_CloudAPPlugin_OpaqueBlobNeedsRefresh_Reason
0x18001476c  lea     rcx, Microsoft_Windows_AAD_Context
0x180014773  call    McTemplateU0z_EventWriteTransfer
0x180014778  mov     [rsp+3F0h+var_3B0], r14
0x18001477d  lea     rax, aEnterpriseToke; "Enterprise token is expired"
0x180014784  mov     [rsp+3F0h+var_3B8], rax
0x180014789  mov     dword ptr [rsp+3F0h+var_3C0], 873h
0x180014791  jmp     loc_18001494B
0x180014796  mov     rax, [r12]
0x18001479a  cmp     dword ptr [rax+20h], 0
0x18001479e  jbe     short loc_18001480C
0x1800147a0  mov     rcx, [rbp+2F0h+var_190]
0x1800147a7  cmp     [r12+2Ch], ebx
0x1800147ac  cmovz   rcx, [rbp+2F0h+var_230]; __int64
  ... truncated ...
```
