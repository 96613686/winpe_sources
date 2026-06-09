# OAuthResponse::ParseIdTokenResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180057ac8`
- end: `0x1800583e0`
- name: `?ParseIdTokenResponse@OAuthResponse@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `2328`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800583e8`

## callees

- `0x180006380`
- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x180006e0c`
- `0x180007d7c`
- `0x1800090d0`
- `0x1800093e8`
- `0x18000a294`
- `0x18000a300`
- `0x18001cf08`
- `0x18001cfdc`
- `0x18003694c`
- `0x180036b3c`
- `0x1800377bc`
- `0x18003d390`
- `0x18004b1b4`
- `0x18004b8c0`
- `0x180057ac8`
- `0x180071e14`
- `0x180076758`
- `0x180076c3c`
- `0x180077b34`
- `0x180079fdc`
- `0x18007a070`
- `0x18007a0fc`
- `0x18007a4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180057ff6`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180057ff6`

## string_xrefs

- `0x180057e6d`: `group_sids`
- `0x180057ef4`: `xms_group_sids_map`
- `0x180057f7e`: `mdm_compliance_url`
- `0x180057af5`: `OAuthResponse::ParseIdTokenResponse`
- `0x1800582c8`: `mdm_compliance_url`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OAuthResponse::ParseIdTokenResponse(__int64 a1, __int64 a2)
{
  int v4; // r14d
  int v5; // ebx
  __int64 *v6; // rax
  struct AadContextFunctions *v7; // rax
  __int64 v8; // r9
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // edx
  char IsEnabled; // al
  struct CJsonObject *v14; // rdi
  struct CJsonObject **JsonDataAsArray; // rax
  __int64 v16; // rcx
  struct CJsonObject *v17; // rax
  _DWORD *v18; // rdx
  _QWORD *v19; // rcx
  const WCHAR **v20; // r12
  const WCHAR **v21; // r13
  int JsonDataAsNumber; // eax
  int v23; // eax
  const WCHAR *v24; // rdi
  unsigned int v25; // edx
  struct CJsonObject *v26; // rax
  struct CJsonObject *v27; // rbx
  const WCHAR *v28; // rcx
  const WCHAR *v29; // rcx
  const WCHAR *v30; // rcx
  const WCHAR *v31; // rax
  const WCHAR *v32; // rax
  const WCHAR *v33; // rax
  const WCHAR *v34; // rax
  unsigned int v35; // edx
  unsigned int v36; // ebx
  __int64 v38; // [rsp+30h] [rbp-89h]
  __int64 v39; // [rsp+30h] [rbp-89h]
  __int64 v40; // [rsp+30h] [rbp-89h]
  __int64 v41; // [rsp+30h] [rbp-89h]
  __int64 v42; // [rsp+30h] [rbp-89h]
  __int64 v43; // [rsp+30h] [rbp-89h]
  __int64 v44; // [rsp+30h] [rbp-89h]
  __int64 v45; // [rsp+30h] [rbp-89h]
  struct CJsonObject *v46; // [rsp+50h] [rbp-69h] BYREF
  char v47[8]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v48; // [rsp+60h] [rbp-59h] BYREF
  int cbMultiByte; // [rsp+68h] [rbp-51h] BYREF
  LPCCH lpMultiByteStr; // [rsp+70h] [rbp-49h]
  _BYTE v51[56]; // [rsp+78h] [rbp-41h] BYREF
  const char *v52[12]; // [rsp+B0h] [rbp-9h] BYREF
  int v53; // [rsp+130h] [rbp+77h] BYREF
  __int64 v54; // [rsp+138h] [rbp+7Fh] BYREF

  v53 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v52,
    (int)"oauthresponse.cpp",
    (int)"OAuthResponse::ParseIdTokenResponse",
    (int)&v53);
  v4 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
         a2,
         L".",
         0);
  v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
         a2,
         L".",
         (unsigned int)(v4 + 1));
  if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                       a2,
                       L".",
                       (unsigned int)(v5 + 1)) == -1
    && v4 > 0
    && v5 > 0 )
  {
    v6 = (__int64 *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                      a2,
                      &v54,
                      (unsigned int)(v4 + 1),
                      (unsigned int)(v5 - v4 - 1));
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v47,
      *v6);
    ATL::CStringData::Release((ATL::CStringData *)(v54 - 24));
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    lpMultiByteStr = 0;
    cbMultiByte = 0;
    v7 = PluginContextHelper::Context();
    LOBYTE(v8) = 1;
    v9 = StringUtility::Base64UrlDecode(v7, v47, &cbMultiByte, v8);
    v53 = v9;
    if ( v9 >= 0 )
    {
      v10 = StringUtility::DecodeBytes(lpMultiByteStr, cbMultiByte);
      v53 = v10;
      if ( v10 >= 0 )
      {
        CJsonValue::CJsonValue((CJsonValue *)v51);
        v46 = 0;
        v11 = WebResponseHelper::ParseJsonObject(&v54, v51, &v46);
        v53 = v11;
        if ( v11 >= 0 )
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::GetImpl'::`2'::impl);
          v14 = v46;
          if ( IsEnabled )
          {
            WebResponseHelper::GetJsonDataAsString(v46, L"iss", a1 + 512);
            WebResponseHelper::GetJsonDataAsString(v14, L"idp", a1 + 520);
          }
          WebResponseHelper::GetJsonDataAsString(v14, L"aud", a1 + 272);
          WebResponseHelper::GetJsonDataAsString(v14, L"oid", a1 + 280);
          WebResponseHelper::GetJsonDataAsString(v14, L"sub", a1 + 288);
          WebResponseHelper::GetJsonDataAsString(v14, L"tid", a1 + 296);
          WebResponseHelper::GetJsonDataAsString(v14, L"upn", a1 + 304);
          WebResponseHelper::GetJsonDataAsString(v14, L"name", a1 + 312);
          WebResponseHelper::GetJsonDataAsString(v14, L"unique_name", a1 + 320);
          WebResponseHelper::GetJsonDataAsString(v14, L"given_name", a1 + 328);
          WebResponseHelper::GetJsonDataAsString(v14, L"family_name", a1 + 336);
          WebResponseHelper::GetJsonDataAsString(v14, L"email", a1 + 344);
          WebResponseHelper::GetJsonDataAsString(v14, L"sid", a1 + 352);
          WebResponseHelper::GetJsonDataAsString(v14, L"fido_auth_data", a1 + 496);
          WebResponseHelper::GetJsonDataAsString(v14, L"xms_rid", a1 + 504);
          *(_DWORD *)(a1 + 480) = (int)WebResponseHelper::GetJsonDataAsNumber(v14, L"prt_refresh_timeout");
          JsonDataAsArray = (struct CJsonObject **)WebResponseHelper::GetJsonDataAsArray(v14, L"group_sids");
          if ( JsonDataAsArray )
          {
            v17 = *JsonDataAsArray;
            v46 = v17;
            while ( v17 )
            {
              v18 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                                  v16,
                                  v17);
              if ( v18 )
              {
                v19 = v18 + 2;
                if ( *v18 != 3 )
                  v19 = 0;
                if ( v19 && *(_DWORD *)(*v19 - 16LL) )
                  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
                    a1 + 360,
                    *v19);
              }
              ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v19, &v46);
              v17 = v46;
            }
            if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
              McTemplateU0d_EventWriteTransfer(v16, Aad_CloudAPPlugin_NumberOfGroups, *(unsigned int *)(a1 + 376));
          }
          WebResponseHelper::GetJsonDataAsString(v14, L"xms_group_sids_map", a1 + 408);
          WebResponseHelper::GetJsonDataAsString(v14, L"onprem_sam_account_name", a1 + 416);
          WebResponseHelper::GetJsonDataAsString(v14, L"domain_netbios_name", a1 + 424);
          WebResponseHelper::GetJsonDataAsString(v14, L"domain_dns_name", a1 + 432);
          v20 = (const WCHAR **)(a1 + 440);
          WebResponseHelper::GetJsonDataAsString(v14, L"mdm_enrollment_url", a1 + 440);
          v21 = (const WCHAR **)(a1 + 448);
          WebResponseHelper::GetJsonDataAsString(v14, L"mdm_terms_of_use_url", a1 + 448);
          WebResponseHelper::GetJsonDataAsString(v14, L"mdm_compliance_url", a1 + 456);
          WebResponseHelper::GetJsonDataAsString(v14, L"user_setting_sync_url", a1 + 464);
          WebResponseHelper::GetJsonDataAsString(v14, L"tenant_display_name", a1 + 472);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
          WebResponseHelper::GetJsonDataAsString(v14, L"pwd_exp", &v48);
          if ( *(_DWORD *)(v48 - 16) )
            JsonDataAsNumber = _o__wtol(v48);
          else
            JsonDataAsNumber = (int)WebResponseHelper::GetJsonDataAsNumber(v14, L"pwd_exp");
          *(_DWORD *)(a1 + 484) = JsonDataAsNumber;
          WebResponseHelper::GetJsonDataAsString(v14, L"pwd_url", a1 + 488);
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
          v23 = StringUtility::StringFormat(&v46, L"%d %s", *(unsigned int *)(a1 + 484), *(_QWORD *)(a1 + 488));
          v53 = v23;
          v24 = &base;
          if ( v23 >= 0 )
          {
            v26 = (struct CJsonObject *)&base;
            v27 = v46;
            if ( v46 )
              v26 = v46;
            WPPTraceLogA(
              4,
              0,
              "%x 0x%08x %s:%u : %s:%ws",
              4,
              0,
              "oauthresponse.cpp",
              412,
              "Password expiration claims",
              v26);
            if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
              McTemplateU0dz_EventWriteTransfer(
                Microsoft_Windows_AAD_Context,
                Aad_CloudAPPlugin_PasswordExpirationClaims,
                *(unsigned int *)(a1 + 484),
                *(_QWORD *)(a1 + 488));
            v28 = &base;
            if ( *(_QWORD *)(a1 + 304) )
              v28 = *(const WCHAR **)(a1 + 304);
            LODWORD(v38) = 415;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v38, "upn", v28);
            v29 = &base;
            if ( *(_QWORD *)(a1 + 352) )
              v29 = *(const WCHAR **)(a1 + 352);
            LODWORD(v39) = 416;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v39, "sid", v29);
            v30 = &base;
            if ( *(_QWORD *)(a1 + 504) )
              v30 = *(const WCHAR **)(a1 + 504);
            LODWORD(v40) = 417;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v40, "xms_rid", v30);
            v31 = &base;
            if ( *v20 )
              v31 = *v20;
            LODWORD(v41) = 418;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v41, "mdm_enrollment_url", v31);
            v32 = &base;
            if ( *v21 )
              v32 = *v21;
            LODWORD(v42) = 419;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v42, "mdm_terms_of_use_url", v32);
            v33 = &base;
            if ( *(_QWORD *)(a1 + 456) )
              v33 = *(const WCHAR **)(a1 + 456);
            LODWORD(v43) = 420;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v43, "mdm_compliance_url", v33);
            v34 = &base;
            if ( *(_QWORD *)(a1 + 464) )
              v34 = *(const WCHAR **)(a1 + 464);
            LODWORD(v44) = 421;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v44, "user_setting_sync_url", v34);
            if ( *(_QWORD *)(a1 + 472) )
              v24 = *(const WCHAR **)(a1 + 472);
            LODWORD(v45) = 422;
            WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v45, "tenant_display_name", v24);
            ATL::CStringData::Release((struct CJsonObject *)((char *)v27 - 24));
            CSecureString::~CSecureString((CSecureString *)&v48);
            CJsonValue::~CJsonValue((CJsonValue *)v51, v35);
            PluginLocalFreeApBlob((struct _AP_BLOB *)&cbMultiByte);
          }
          else
          {
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v23, "oauthresponse.cpp", 411, "HRESULT", &base);
            ATL::CStringData::Release((struct CJsonObject *)((char *)v46 - 24));
            CSecureString::~CSecureString((CSecureString *)&v48);
            CJsonValue::~CJsonValue((CJsonValue *)v51, v25);
            PluginLocalFreeApBlob((struct _AP_BLOB *)&cbMultiByte);
          }
        }
        else
        {
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v11, "oauthresponse.cpp", 331, "HRESULT", &base);
          CJsonValue::~CJsonValue((CJsonValue *)v51, v12);
          PluginLocalFreeApBlob((struct _AP_BLOB *)&cbMultiByte);
        }
      }
      else
      {
        WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v10, "oauthresponse.cpp", 322, "HRESULT", &base);
        PluginLocalFreeApBlob((struct _AP_BLOB *)&cbMultiByte);
      }
    }
    else
    {
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v9, "oauthresponse.cpp", 321, "HRESULT", &base);
      PluginLocalFreeApBlob((struct _AP_BLOB *)&cbMultiByte);
    }
    CSecureString::~CSecureString((CSecureString *)&v54);
    CSecureString::~CSecureString((CSecureString *)v47);
  }
  v36 = v53;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v52);
  return v36;
}

```

## disassembly

```asm
0x180057ac8  mov     [rsp-8+arg_0], rbx
0x180057acd  push    rbp
0x180057ace  push    rsi
0x180057acf  push    rdi
0x180057ad0  push    r12
0x180057ad2  push    r13
0x180057ad4  push    r14
0x180057ad6  push    r15
0x180057ad8  lea     rbp, [rsp-27h]
0x180057add  sub     rsp, 0E0h
0x180057ae4  mov     rdi, rdx
0x180057ae7  mov     rsi, rcx
0x180057aea  xor     r13d, r13d
0x180057aed  mov     [rbp+57h+arg_10], r13d
0x180057af1  lea     r9, [rbp+57h+arg_10]
0x180057af5  lea     r8, aOauthresponseP_0; "OAuthResponse::ParseIdTokenResponse"
0x180057afc  lea     rdx, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180057b03  lea     rcx, [rbp+57h+var_60]
0x180057b07  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180057b0c  nop
0x180057b0d  xor     r8d, r8d
0x180057b10  lea     r12, asc_1800B5778; "."
0x180057b17  mov     rdx, r12
0x180057b1a  mov     rcx, rdi
0x180057b1d  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180057b22  mov     r14d, eax
0x180057b25  lea     r8d, [rax+1]
0x180057b29  mov     rdx, r12
0x180057b2c  mov     rcx, rdi
0x180057b2f  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180057b34  mov     ebx, eax
0x180057b36  lea     r8d, [rax+1]
0x180057b3a  mov     rdx, r12
0x180057b3d  mov     rcx, rdi
0x180057b40  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180057b45  cmp     eax, 0FFFFFFFFh
0x180057b48  jnz     loc_1800583B7
0x180057b4e  test    r14d, r14d
0x180057b51  jle     loc_1800583B7
0x180057b57  test    ebx, ebx
0x180057b59  jle     loc_1800583B7
0x180057b5f  sub     ebx, r14d
0x180057b62  lea     r9d, [rbx-1]
0x180057b66  lea     r8d, [r14+1]
0x180057b6a  lea     rdx, [rbp+57h+arg_18]
0x180057b6e  mov     rcx, rdi
0x180057b71  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180057b76  nop
0x180057b77  mov     rdx, [rax]
0x180057b7a  lea     rcx, [rbp+57h+var_B8]
0x180057b7e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180057b83  nop
0x180057b84  mov     rcx, [rbp+57h+arg_18]
0x180057b88  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180057b8c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057b91  lea     rcx, [rbp+57h+arg_18]; void *
0x180057b95  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057b9a  nop
0x180057b9b  mov     [rbp+57h+lpMultiByteStr], r13
0x180057b9f  mov     [rbp+57h+cbMultiByte], r13d
0x180057ba3  call    ?Context@PluginContextHelper@@SAPEAVAadContextFunctions@@XZ; PluginContextHelper::Context(void)
0x180057ba8  mov     rcx, rax
0x180057bab  mov     r9b, 1
0x180057bae  lea     r8, [rbp+57h+cbMultiByte]
0x180057bb2  lea     rdx, [rbp+57h+var_B8]
0x180057bb6  call    ?Base64UrlDecode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64UrlDecode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x180057bbb  mov     [rbp+57h+arg_10], eax
0x180057bbe  test    eax, eax
0x180057bc0  jns     short loc_180057C17
0x180057bc2  lea     rdi, base
0x180057bc9  mov     [rsp+110h+var_D0], rdi
0x180057bce  lea     rcx, aHresult; "HRESULT"
0x180057bd5  mov     [rsp+110h+var_D8], rcx
0x180057bda  mov     dword ptr [rsp+110h+var_E0], 141h
0x180057be2  lea     rcx, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180057be9  mov     [rsp+110h+var_E8], rcx
0x180057bee  mov     dword ptr [rsp+110h+var_F0], eax
0x180057bf2  lea     ecx, [r13+2]
0x180057bf6  mov     r9d, ecx
0x180057bf9  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180057c00  xor     edx, edx
0x180057c02  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180057c07  nop
0x180057c08  lea     rcx, [rbp+57h+cbMultiByte]; struct _AP_BLOB *
0x180057c0c  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x180057c11  nop
0x180057c12  jmp     loc_1800583A4
0x180057c17  mov     r9d, 0FDE9h
0x180057c1d  lea     r8, [rbp+57h+arg_18]
0x180057c21  mov     edx, [rbp+57h+cbMultiByte]; cbMultiByte
0x180057c24  mov     rcx, [rbp+57h+lpMultiByteStr]; lpMultiByteStr
0x180057c28  call    ?DecodeBytes@StringUtility@@SAJPEBDHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; StringUtility::DecodeBytes(char const *,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,uint)
0x180057c2d  mov     [rbp+57h+arg_10], eax
0x180057c30  test    eax, eax
0x180057c32  jns     short loc_180057C8A
0x180057c34  lea     rdi, base
0x180057c3b  mov     [rsp+110h+var_D0], rdi
0x180057c40  lea     rcx, aHresult; "HRESULT"
0x180057c47  mov     [rsp+110h+var_D8], rcx
0x180057c4c  mov     dword ptr [rsp+110h+var_E0], 142h
0x180057c54  lea     rcx, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180057c5b  mov     [rsp+110h+var_E8], rcx
0x180057c60  mov     dword ptr [rsp+110h+var_F0], eax
0x180057c64  mov     ecx, 2
0x180057c69  mov     r9d, ecx
0x180057c6c  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180057c73  xor     edx, edx
0x180057c75  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180057c7a  nop
0x180057c7b  lea     rcx, [rbp+57h+cbMultiByte]; struct _AP_BLOB *
0x180057c7f  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x180057c84  nop
0x180057c85  jmp     loc_1800583A4
0x180057c8a  lea     rcx, [rbp+57h+var_98]; this
0x180057c8e  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x180057c93  nop
0x180057c94  mov     [rbp+57h+var_C0], r13
0x180057c98  lea     r8, [rbp+57h+var_C0]
0x180057c9c  lea     rdx, [rbp+57h+var_98]
0x180057ca0  lea     rcx, [rbp+57h+arg_18]
0x180057ca4  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x180057ca9  mov     [rbp+57h+arg_10], eax
0x180057cac  test    eax, eax
0x180057cae  jns     short loc_180057D10
0x180057cb0  lea     rdi, base
0x180057cb7  mov     [rsp+110h+var_D0], rdi
0x180057cbc  lea     rcx, aHresult; "HRESULT"
0x180057cc3  mov     [rsp+110h+var_D8], rcx
0x180057cc8  mov     dword ptr [rsp+110h+var_E0], 14Bh
0x180057cd0  lea     rcx, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180057cd7  mov     [rsp+110h+var_E8], rcx
0x180057cdc  mov     dword ptr [rsp+110h+var_F0], eax
0x180057ce0  mov     ecx, 2
0x180057ce5  mov     r9d, ecx
0x180057ce8  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180057cef  xor     edx, edx
0x180057cf1  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180057cf6  nop
0x180057cf7  lea     rcx, [rbp+57h+var_98]; this
0x180057cfb  call    ??1CJsonValue@@QEAA@XZ; CJsonValue::~CJsonValue(void)
0x180057d00  nop
0x180057d01  lea     rcx, [rbp+57h+cbMultiByte]; struct _AP_BLOB *
0x180057d05  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x180057d0a  nop
0x180057d0b  jmp     loc_1800583A4
0x180057d10  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD> `wil::Feature<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::GetImpl(void)'::`2'::impl
0x180057d17  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GuestUserRDPToAVD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GuestUserRDPToAVD>::__private_IsEnabled(void)
0x180057d1c  mov     rdi, [rbp+57h+var_C0]
0x180057d20  test    al, al
0x180057d22  jz      short loc_180057D50
0x180057d24  lea     r8, [rsi+200h]
0x180057d2b  lea     rdx, aIss; "iss"
0x180057d32  mov     rcx, rdi
0x180057d35  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057d3a  lea     r8, [rsi+208h]
0x180057d41  lea     rdx, aIdp; "idp"
0x180057d48  mov     rcx, rdi
0x180057d4b  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057d50  lea     rbx, [rsi+110h]
0x180057d57  mov     r8, rbx
0x180057d5a  lea     rdx, aAud; "aud"
0x180057d61  mov     rcx, rdi
0x180057d64  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057d69  lea     r8, [rbx+8]
0x180057d6d  lea     rdx, aOid; "oid"
0x180057d74  mov     rcx, rdi
0x180057d77  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057d7c  lea     r8, [rbx+10h]
0x180057d80  lea     rdx, aSub; "sub"
0x180057d87  mov     rcx, rdi
0x180057d8a  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057d8f  lea     r8, [rbx+18h]
0x180057d93  lea     rdx, aTid; "tid"
0x180057d9a  mov     rcx, rdi
0x180057d9d  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057da2  lea     r8, [rbx+20h]
0x180057da6  lea     rdx, aUpn; "upn"
0x180057dad  mov     rcx, rdi
0x180057db0  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057db5  lea     r8, [rbx+28h]
0x180057db9  lea     rdx, aName_1; "name"
0x180057dc0  mov     rcx, rdi
0x180057dc3  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057dc8  lea     r8, [rbx+30h]
0x180057dcc  lea     rdx, aUniqueName; "unique_name"
0x180057dd3  mov     rcx, rdi
0x180057dd6  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057ddb  lea     r8, [rbx+38h]
0x180057ddf  lea     rdx, aGivenName; "given_name"
0x180057de6  mov     rcx, rdi
0x180057de9  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057dee  lea     r8, [rbx+40h]
0x180057df2  lea     rdx, aFamilyName; "family_name"
0x180057df9  mov     rcx, rdi
0x180057dfc  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057e01  lea     r8, [rbx+48h]
0x180057e05  lea     rdx, aEmail; "email"
0x180057e0c  mov     rcx, rdi
0x180057e0f  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057e14  lea     r8, [rbx+50h]
0x180057e18  lea     rdx, aSid_1; "sid"
0x180057e1f  mov     rcx, rdi
0x180057e22  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057e27  lea     r8, [rbx+0E0h]
0x180057e2e  lea     rdx, aFidoAuthData; "fido_auth_data"
0x180057e35  mov     rcx, rdi
0x180057e38  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057e3d  lea     r8, [rbx+0E8h]
0x180057e44  lea     rdx, aXmsRid; "xms_rid"
0x180057e4b  mov     rcx, rdi
0x180057e4e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057e53  lea     rdx, aPrtRefreshTime; "prt_refresh_timeout"
0x180057e5a  mov     rcx, rdi; struct CJsonObject *
0x180057e5d  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180057e62  cvttsd2si rax, xmm0
0x180057e67  mov     [rsi+1E0h], eax
0x180057e6d  lea     rdx, aGroupSids; "group_sids"
0x180057e74  mov     rcx, rdi; struct CJsonObject *
0x180057e77  call    ?GetJsonDataAsArray@WebResponseHelper@@SAPEAVCJsonArray@@PEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsArray(CJsonObject *,ushort const *)
0x180057e7c  test    rax, rax
0x180057e7f  jz      short loc_180057EED
0x180057e81  mov     rax, [rax]
0x180057e84  mov     [rbp+57h+var_C0], rax
0x180057e88  jmp     short loc_180057ECC
0x180057e8a  mov     rdx, rax
0x180057e8d  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x180057e92  mov     rdx, [rax]
0x180057e95  test    rdx, rdx
0x180057e98  jz      short loc_180057EBF
0x180057e9a  lea     rcx, [rdx+8]
0x180057e9e  cmp     dword ptr [rdx], 3
0x180057ea1  cmovnz  rcx, r13
0x180057ea5  test    rcx, rcx
0x180057ea8  jz      short loc_180057EBF
0x180057eaa  mov     rdx, [rcx]
0x180057ead  cmp     [rdx-10h], r13d
0x180057eb1  jz      short loc_180057EBF
0x180057eb3  lea     rcx, [rsi+168h]
0x180057eba  call    ?AddTail@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddTail(ushort const *)
0x180057ebf  lea     rdx, [rbp+57h+var_C0]
0x180057ec3  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x180057ec8  mov     rax, [rbp+57h+var_C0]
0x180057ecc  test    rax, rax
0x180057ecf  jnz     short loc_180057E8A
0x180057ed1  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x180057ed8  jz      short loc_180057EED
0x180057eda  mov     r8d, [rsi+178h]
0x180057ee1  lea     rdx, Aad_CloudAPPlugin_NumberOfGroups
0x180057ee8  call    McTemplateU0d_EventWriteTransfer
0x180057eed  lea     r8, [rsi+198h]
0x180057ef4  lea     rdx, aXmsGroupSidsMa; "xms_group_sids_map"
0x180057efb  mov     rcx, rdi
0x180057efe  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f03  lea     r8, [rsi+1A0h]
0x180057f0a  lea     rdx, aOnpremSamAccou; "onprem_sam_account_name"
0x180057f11  mov     rcx, rdi
0x180057f14  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f19  lea     r8, [rsi+1A8h]
0x180057f20  lea     rdx, aDomainNetbiosN; "domain_netbios_name"
0x180057f27  mov     rcx, rdi
0x180057f2a  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f2f  lea     r8, [rsi+1B0h]
0x180057f36  lea     rdx, aDomainDnsName; "domain_dns_name"
0x180057f3d  mov     rcx, rdi
0x180057f40  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f45  lea     r12, [rsi+1B8h]
0x180057f4c  mov     r8, r12
0x180057f4f  lea     rdx, aMdmEnrollmentU_0; "mdm_enrollment_url"
0x180057f56  mov     rcx, rdi
0x180057f59  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f5e  lea     r13, [rsi+1C0h]
0x180057f65  mov     r8, r13
0x180057f68  lea     rdx, aMdmTermsOfUseU_0; "mdm_terms_of_use_url"
0x180057f6f  mov     rcx, rdi
0x180057f72  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f77  lea     r8, [rsi+1C8h]
0x180057f7e  lea     rdx, aMdmComplianceU; "mdm_compliance_url"
0x180057f85  mov     rcx, rdi
0x180057f88  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057f8d  lea     r8, [rsi+1D0h]
0x180057f94  lea     rdx, aUserSettingSyn; "user_setting_sync_url"
0x180057f9b  mov     rcx, rdi
0x180057f9e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057fa3  lea     r8, [rsi+1D8h]
0x180057faa  lea     rdx, aTenantDisplayN_0; "tenant_display_name"
0x180057fb1  mov     rcx, rdi
0x180057fb4  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057fb9  lea     rcx, [rbp+57h+var_B0]; void *
0x180057fbd  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180057fc2  nop
0x180057fc3  lea     r8, [rbp+57h+var_B0]
0x180057fc7  lea     rdx, aPwdExp; "pwd_exp"
0x180057fce  mov     rcx, rdi
0x180057fd1  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180057fd6  mov     rcx, [rbp+57h+var_B0]
0x180057fda  cmp     dword ptr [rcx-10h], 0
0x180057fde  jnz     short loc_180057FF6
0x180057fe0  lea     rdx, aPwdExp; "pwd_exp"
0x180057fe7  mov     rcx, rdi; struct CJsonObject *
0x180057fea  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
  ... truncated ...
```
