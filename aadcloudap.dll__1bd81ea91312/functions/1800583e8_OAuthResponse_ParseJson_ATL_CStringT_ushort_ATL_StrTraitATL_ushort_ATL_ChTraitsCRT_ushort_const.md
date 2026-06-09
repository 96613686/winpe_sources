# OAuthResponse::ParseJson(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800583e8`
- end: `0x180058ab0`
- name: `?ParseJson@OAuthResponse@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1736`
- prototype: `__int64 __fastcall(WebResponseBase *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057720`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x1800093e8`
- `0x18000a294`
- `0x18000a300`
- `0x18001a884`
- `0x18001d0ec`
- `0x180033180`
- `0x18004aad0`
- `0x180057a10`
- `0x180057ac8`
- `0x1800583e8`
- `0x180058ab8`
- `0x1800591ac`
- `0x18005970c`
- `0x18006a40c`
- `0x18006a4f4`
- `0x180071e14`
- `0x180078a58`
- `0x18007a070`
- `0x18007a0fc`
- `0x18007a4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180058611`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18005864c`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180058611`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18005864c`

## string_xrefs

- `0x1800585cf`: `refresh_token`
- `0x1800585b9`: `access_token`
- `0x1800585e2`: `refresh_token_expires_in`
- `0x1800585fb`: `refresh_token_expires_in`
- `0x180058662`: `id_token`
- `0x1800587a8`: `cert_token_use`
- `0x180058423`: `OAuthResponse::ParseJson`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OAuthResponse::ParseJson(WebResponseBase *this, __int64 a2)
{
  _QWORD *v4; // r15
  int UnixEpochTime; // eax
  const unsigned __int16 **v6; // rbx
  struct CJsonObject *v7; // rsi
  const unsigned __int16 **v8; // r14
  __int64 v9; // rdx
  int JsonDataAsNumber; // eax
  int v11; // eax
  int v12; // eax
  OAuthResponse *v13; // rcx
  const WCHAR *v14; // r14
  const WCHAR *v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  const WCHAR *v18; // rax
  __int64 v19; // r9
  int v20; // ecx
  unsigned int v21; // ebx
  unsigned int v22; // edx
  __int64 v24; // [rsp+20h] [rbp-99h]
  int v25; // [rsp+20h] [rbp-99h]
  __int64 v26; // [rsp+30h] [rbp-89h]
  int v27; // [rsp+30h] [rbp-89h]
  int v28; // [rsp+30h] [rbp-89h]
  __int64 v29; // [rsp+50h] [rbp-69h] BYREF
  __int64 v30; // [rsp+58h] [rbp-61h] BYREF
  __int64 v31; // [rsp+60h] [rbp-59h] BYREF
  __int64 v32; // [rsp+68h] [rbp-51h] BYREF
  __int64 v33; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v34[56]; // [rsp+78h] [rbp-41h] BYREF
  const char *v35[12]; // [rsp+B0h] [rbp-9h] BYREF
  int v36; // [rsp+120h] [rbp+67h] BYREF
  struct CJsonObject *v37; // [rsp+130h] [rbp+77h] BYREF
  __int64 v38; // [rsp+138h] [rbp+7Fh] BYREF

  v36 = 0;
  CJsonValue::CJsonValue((CJsonValue *)v34);
  v37 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v35,
    (int)"oauthresponse.cpp",
    (int)"OAuthResponse::ParseJson",
    (int)&v36);
  v4 = (_QWORD *)((char *)this + 16);
  UnixEpochTime = GetUnixEpochTime((__int64 *)this + 2);
  v36 = UnixEpochTime;
  if ( UnixEpochTime < 0 )
  {
    v27 = 151;
LABEL_3:
    v25 = UnixEpochTime;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v25, "oauthresponse.cpp", v27, "HRESULT", &base);
    goto LABEL_57;
  }
  UnixEpochTime = WebResponseHelper::ParseJsonObject(a2, v34, &v37);
  v36 = UnixEpochTime;
  if ( UnixEpochTime < 0 )
  {
    v27 = 154;
    goto LABEL_3;
  }
  v6 = (const unsigned __int16 **)((char *)this + 32);
  v7 = v37;
  WebResponseHelper::GetJsonDataAsString(v37, L"error", (char *)this + 32);
  WebResponseHelper::GetJsonDataAsString(v7, L"suberror", (char *)this + 40);
  v8 = (const unsigned __int16 **)((char *)this + 48);
  WebResponseHelper::GetJsonDataAsString(v7, L"error_description", (char *)this + 48);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl'::`2'::impl,
                          v9) )
  {
    WebResponseHelper::GetJsonDataAsString(v7, L"sso_nonce", (char *)this + 744);
    *((_DWORD *)this + 188) = (int)WebResponseHelper::GetJsonDataAsNumber(v7, L"sso_nonce_expires_in");
  }
  if ( !*((_DWORD *)*v6 - 4) && !*((_DWORD *)*v8 - 4) )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v33);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v31);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v30);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v29);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v37);
    WebResponseHelper::GetJsonDataAsString(v7, L"access_token", (char *)this + 248);
    WebResponseHelper::GetJsonDataAsString(v7, L"refresh_token", (char *)this + 256);
    WebResponseHelper::GetJsonDataAsString(v7, L"refresh_token_expires_in", &v33);
    if ( *(_DWORD *)(v33 - 16) )
      JsonDataAsNumber = _o__wtol(v33);
    else
      JsonDataAsNumber = (int)WebResponseHelper::GetJsonDataAsNumber(v7, L"refresh_token_expires_in");
    if ( !JsonDataAsNumber )
      JsonDataAsNumber = 1209600;
    *((_QWORD *)this + 3) = *v4 + JsonDataAsNumber;
    WebResponseHelper::GetJsonDataAsString(v7, L"expires_in", &v32);
    if ( *(_DWORD *)(v32 - 16) )
      v11 = _o__wtol(v32);
    else
      v11 = 0;
    *((_QWORD *)this + 74) = *v4 + v11;
    WebResponseHelper::GetJsonDataAsString(v7, L"id_token", &v30);
    if ( *(_DWORD *)(v30 - 16) )
      OAuthResponse::ParseIdTokenResponse(this, &v30);
    WebResponseHelper::GetJsonDataAsString(v7, L"device_info", &v29);
    if ( *(_DWORD *)(v29 - 16) )
      OAuthResponse::ParseDeviceInfo(this, &v29);
    if ( !*((_QWORD *)this + 17)
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::GetImpl'::`2'::impl)
      && (*((_DWORD *)this + 45) & 0x100) != 0 )
    {
      WebResponseHelper::GetJsonDataAsString(v7, L"session_key_jwe", &v31);
      if ( *(_DWORD *)(v31 - 16) )
      {
        v12 = OAuthResponse::ParseSessionTokenResponse(this, &v31);
        v36 = v12;
        if ( v12 < 0 )
        {
          LODWORD(v26) = 232;
LABEL_28:
          LODWORD(v24) = v12;
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "oauthresponse.cpp", v26, "HRESULT", &base);
LABEL_29:
          CSecureString::~CSecureString((CSecureString *)&v37);
          CSecureString::~CSecureString((CSecureString *)&v38);
          CSecureString::~CSecureString((CSecureString *)&v29);
          CSecureString::~CSecureString((CSecureString *)&v30);
          CSecureString::~CSecureString((CSecureString *)&v31);
          CSecureString::~CSecureString((CSecureString *)&v32);
          CSecureString::~CSecureString((CSecureString *)&v33);
          goto LABEL_57;
        }
      }
    }
    WebResponseHelper::GetJsonDataAsString(v7, L"cert_token_use", (char *)this + 544);
    WebResponseHelper::GetJsonDataAsString(v7, L"x5c", (char *)this + 552);
    WebResponseHelper::GetJsonDataAsString(v7, L"x5c_ca", (char *)this + 560);
    WebResponseHelper::GetJsonDataAsString(v7, L"tgt_ad", &v38);
    WebResponseHelper::GetJsonDataAsString(v7, L"tgt_cloud", &v37);
    v14 = &base;
    if ( *(_DWORD *)(v38 - 16) )
    {
      v12 = OAuthResponse::ParseTgtToken(
              v13,
              (const struct CSecureString *)&v38,
              (WebResponseBase *)((char *)this + 600));
      v36 = v12;
      if ( v12 < 0 )
      {
        LODWORD(v26) = 249;
        goto LABEL_28;
      }
      v13 = (OAuthResponse *)*((_QWORD *)this + 81);
      if ( !*((_DWORD *)v13 - 4) )
      {
        v16 = 1;
LABEL_40:
        if ( *((_DWORD *)v37 - 4) )
        {
          v12 = OAuthResponse::ParseTgtToken(
                  v13,
                  (const struct CSecureString *)&v37,
                  (WebResponseBase *)((char *)this + 664));
          v36 = v12;
          if ( v12 < 0 )
          {
            LODWORD(v26) = 264;
            goto LABEL_28;
          }
          v17 = *((_QWORD *)this + 89);
          if ( !*(_DWORD *)(v17 - 16) )
          {
            v19 = 1;
            goto LABEL_50;
          }
          v18 = &base;
          if ( v17 )
            v18 = (const WCHAR *)*((_QWORD *)this + 89);
          LODWORD(v26) = 268;
          WPPTraceLogA(3, 0, "%x 0x%08x %s:%u : %s:%ws", 3, 0, "oauthresponse.cpp", v26, "cloud tgt error", v18);
          if ( (Microsoft_Windows_AADEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_CloudTgtError,
              *((_QWORD *)this + 89));
        }
        v19 = 0;
LABEL_50:
        if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
          McTemplateU0qq_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_TgtReceivedStatus,
            v16,
            v19);
        WebResponseHelper::GetJsonDataAsString(v7, L"kerberos_top_level_names", (char *)this + 728);
        if ( *((_QWORD *)this + 91) )
          v14 = (const WCHAR *)*((_QWORD *)this + 91);
        LODWORD(v26) = 281;
        WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "oauthresponse.cpp", v26, "kerberos top level names", v14);
        WebResponseHelper::GetJsonDataAsString(v7, L"client_info", (char *)this + 736);
        goto LABEL_29;
      }
      v15 = &base;
      if ( v13 )
        v15 = (const WCHAR *)*((_QWORD *)this + 81);
      v28 = 253;
      WPPTraceLogA(3, 0, "%x 0x%08x %s:%u : %s:%ws", 3, 0, "oauthresponse.cpp", v28, "on-prem tgt error", v15);
      if ( (Microsoft_Windows_AADEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_OnpremTgtError,
          *((_QWORD *)this + 81));
    }
    v16 = 0;
    goto LABEL_40;
  }
  WebResponseBase::ParseErrorCodes(this, v7);
  WebResponseBase::AddDiagnosticMessage(this, L"serverErrorCode", *v6);
  WebResponseBase::AddDiagnosticMessage(this, L"serverErrorDescription", *v8);
  if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      v20,
      (unsigned int)Aad_CloudAPPlugin_OAuthResponse_Error,
      (unsigned int)*v6,
      (unsigned int)*v8,
      *((_QWORD *)this + 13));
LABEL_57:
  v21 = v36;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v35);
  CJsonValue::~CJsonValue((CJsonValue *)v34, v22);
  return v21;
}

```

## disassembly

```asm
0x1800583e8  mov     [rsp-8+arg_8], rbx
0x1800583ed  push    rbp
0x1800583ee  push    rsi
0x1800583ef  push    rdi
0x1800583f0  push    r12
0x1800583f2  push    r13
0x1800583f4  push    r14
0x1800583f6  push    r15
0x1800583f8  lea     rbp, [rsp-27h]
0x1800583fd  sub     rsp, 0E0h
0x180058404  mov     rbx, rdx
0x180058407  mov     rdi, rcx
0x18005840a  xor     r12d, r12d
0x18005840d  mov     [rbp+57h+arg_0], r12d
0x180058411  lea     rcx, [rbp+57h+var_98]; this
0x180058415  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x18005841a  nop
0x18005841b  mov     [rbp+57h+arg_10], r12
0x18005841f  lea     r9, [rbp+57h+arg_0]
0x180058423  lea     r8, aOauthresponseP_2; "OAuthResponse::ParseJson"
0x18005842a  lea     r13, aOnecoreuapDsEx_66+21h; "oauthresponse.cpp"
0x180058431  mov     rdx, r13
0x180058434  lea     rcx, [rbp+57h+var_60]
0x180058438  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18005843d  nop
0x18005843e  lea     r15, [rdi+10h]
0x180058442  mov     rcx, r15; __int64 *
0x180058445  call    ?GetUnixEpochTime@@YAJAEA_J@Z; GetUnixEpochTime(__int64 &)
0x18005844a  mov     [rbp+57h+arg_0], eax
0x18005844d  test    eax, eax
0x18005844f  jns     short loc_180058497
0x180058451  lea     r14, base
0x180058458  mov     [rsp+110h+var_D0], r14
0x18005845d  lea     rcx, aHresult; "HRESULT"
0x180058464  mov     [rsp+110h+var_D8], rcx
0x180058469  mov     dword ptr [rsp+110h+var_E0], 97h
0x180058471  mov     [rsp+110h+var_E8], r13
0x180058476  mov     dword ptr [rsp+110h+var_F0], eax
0x18005847a  mov     eax, 2
0x18005847f  mov     r9d, eax
0x180058482  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180058489  xor     edx, edx
0x18005848b  mov     ecx, eax
0x18005848d  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180058492  jmp     loc_180058A7D
0x180058497  lea     r8, [rbp+57h+arg_10]
0x18005849b  lea     rdx, [rbp+57h+var_98]
0x18005849f  mov     rcx, rbx
0x1800584a2  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x1800584a7  mov     [rbp+57h+arg_0], eax
0x1800584aa  test    eax, eax
0x1800584ac  jns     short loc_1800584D0
0x1800584ae  lea     r14, base
0x1800584b5  mov     [rsp+110h+var_D0], r14
0x1800584ba  lea     rcx, aHresult; "HRESULT"
0x1800584c1  mov     [rsp+110h+var_D8], rcx
0x1800584c6  mov     dword ptr [rsp+110h+var_E0], 9Ah
0x1800584ce  jmp     short loc_180058471
0x1800584d0  lea     rbx, [rdi+20h]
0x1800584d4  mov     r8, rbx
0x1800584d7  lea     rdx, aError; "error"
0x1800584de  mov     rsi, [rbp+57h+arg_10]
0x1800584e2  mov     rcx, rsi
0x1800584e5  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800584ea  lea     r8, [rdi+28h]
0x1800584ee  lea     rdx, aSuberror; "suberror"
0x1800584f5  mov     rcx, rsi
0x1800584f8  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800584fd  lea     r14, [rdi+30h]
0x180058501  mov     r8, r14
0x180058504  lea     rdx, aErrorDescripti; "error_description"
0x18005850b  mov     rcx, rsi
0x18005850e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180058513  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching> `wil::Feature<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::GetImpl(void)'::`2'::impl
0x18005851a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BrowserSSONonceCaching@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BrowserSSONonceCaching>::__private_IsEnabled(void)
0x18005851f  test    al, al
0x180058521  jz      short loc_180058552
0x180058523  lea     r8, [rdi+2E8h]
0x18005852a  lea     rdx, aSsoNonce_0; "sso_nonce"
0x180058531  mov     rcx, rsi
0x180058534  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180058539  lea     rdx, aSsoNonceExpire_0; "sso_nonce_expires_in"
0x180058540  mov     rcx, rsi; struct CJsonObject *
0x180058543  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x180058548  cvttsd2si eax, xmm0
0x18005854c  mov     [rdi+2F0h], eax
0x180058552  mov     rax, [rbx]
0x180058555  cmp     [rax-10h], r12d
0x180058559  jnz     loc_180058A26
0x18005855f  mov     rax, [r14]
0x180058562  cmp     [rax-10h], r12d
0x180058566  jnz     loc_180058A26
0x18005856c  lea     rcx, [rbp+57h+var_A0]; void *
0x180058570  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180058575  nop
0x180058576  lea     rcx, [rbp+57h+var_A8]; void *
0x18005857a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005857f  nop
0x180058580  lea     rcx, [rbp+57h+var_B0]; void *
0x180058584  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180058589  nop
0x18005858a  lea     rcx, [rbp+57h+var_B8]; void *
0x18005858e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180058593  nop
0x180058594  lea     rcx, [rbp+57h+var_C0]; void *
0x180058598  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005859d  nop
0x18005859e  lea     rcx, [rbp+57h+arg_18]; void *
0x1800585a2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800585a7  nop
0x1800585a8  lea     rcx, [rbp+57h+arg_10]; void *
0x1800585ac  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800585b1  nop
0x1800585b2  lea     r8, [rdi+0F8h]
0x1800585b9  lea     rdx, aAccessToken; "access_token"
0x1800585c0  mov     rcx, rsi
0x1800585c3  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800585c8  lea     r8, [rdi+100h]
0x1800585cf  lea     rdx, aRefreshToken; "refresh_token"
0x1800585d6  mov     rcx, rsi
0x1800585d9  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800585de  lea     r8, [rbp+57h+var_A0]
0x1800585e2  lea     rdx, aRefreshTokenEx; "refresh_token_expires_in"
0x1800585e9  mov     rcx, rsi
0x1800585ec  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800585f1  mov     rcx, [rbp+57h+var_A0]
0x1800585f5  cmp     [rcx-10h], r12d
0x1800585f9  jnz     short loc_180058611
0x1800585fb  lea     rdx, aRefreshTokenEx; "refresh_token_expires_in"
0x180058602  mov     rcx, rsi; struct CJsonObject *
0x180058605  call    ?GetJsonDataAsNumber@WebResponseHelper@@SANPEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsNumber(CJsonObject *,ushort const *)
0x18005860a  cvttsd2si rax, xmm0
0x18005860f  jmp     short loc_180058617
0x180058611  call    cs:__imp__o__wtol
0x180058617  mov     ecx, 127500h
0x18005861c  test    eax, eax
0x18005861e  cmovz   eax, ecx
0x180058621  cdqe
0x180058623  add     rax, [r15]
0x180058626  mov     [rdi+18h], rax
0x18005862a  lea     r8, [rbp+57h+var_A8]
0x18005862e  lea     rdx, aExpiresIn; "expires_in"
0x180058635  mov     rcx, rsi
0x180058638  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18005863d  mov     rcx, [rbp+57h+var_A8]
0x180058641  cmp     [rcx-10h], r12d
0x180058645  jnz     short loc_18005864C
0x180058647  mov     eax, r12d
0x18005864a  jmp     short loc_180058652
0x18005864c  call    cs:__imp__o__wtol
0x180058652  cdqe
0x180058654  add     rax, [r15]
0x180058657  mov     [rdi+250h], rax
0x18005865e  lea     r8, [rbp+57h+var_B8]
0x180058662  lea     rdx, aIdToken; "id_token"
0x180058669  mov     rcx, rsi
0x18005866c  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180058671  mov     rax, [rbp+57h+var_B8]
0x180058675  cmp     [rax-10h], r12d
0x180058679  jz      short loc_180058687
0x18005867b  lea     rdx, [rbp+57h+var_B8]
0x18005867f  mov     rcx, rdi
0x180058682  call    ?ParseIdTokenResponse@OAuthResponse@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthResponse::ParseIdTokenResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180058687  lea     r8, [rbp+57h+var_C0]
0x18005868b  lea     rdx, aDeviceInfo; "device_info"
0x180058692  mov     rcx, rsi
0x180058695  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18005869a  mov     rax, [rbp+57h+var_C0]
0x18005869e  cmp     [rax-10h], r12d
0x1800586a2  jz      short loc_1800586B0
0x1800586a4  lea     rdx, [rbp+57h+var_C0]
0x1800586a8  mov     rcx, rdi
0x1800586ab  call    ?ParseDeviceInfo@OAuthResponse@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthResponse::ParseDeviceInfo(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800586b0  cmp     [rdi+88h], r12
0x1800586b7  jz      short loc_1800586DD
0x1800586b9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2> `wil::Feature<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::GetImpl(void)'::`2'::impl
0x1800586c0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADClientSessionKeyRolloverV2>::__private_IsEnabled(void)
0x1800586c5  test    al, al
0x1800586c7  jz      loc_1800587A1
0x1800586cd  test    dword ptr [rdi+0B4h], 100h
0x1800586d7  jz      loc_1800587A1
0x1800586dd  lea     r8, [rbp+57h+var_B0]
0x1800586e1  lea     rdx, aSessionKeyJwe; "session_key_jwe"
0x1800586e8  mov     rcx, rsi
0x1800586eb  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800586f0  mov     rax, [rbp+57h+var_B0]
0x1800586f4  cmp     [rax-10h], r12d
0x1800586f8  jz      loc_1800587A1
0x1800586fe  lea     rdx, [rbp+57h+var_B0]
0x180058702  mov     rcx, rdi
0x180058705  call    ?ParseSessionTokenResponse@OAuthResponse@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; OAuthResponse::ParseSessionTokenResponse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18005870a  mov     [rbp+57h+arg_0], eax
0x18005870d  test    eax, eax
0x18005870f  jns     loc_1800587A1
0x180058715  lea     r14, base
0x18005871c  mov     [rsp+110h+var_D0], r14
0x180058721  lea     rcx, aHresult; "HRESULT"
0x180058728  mov     [rsp+110h+var_D8], rcx
0x18005872d  mov     dword ptr [rsp+110h+var_E0], 0E8h
0x180058735  mov     [rsp+110h+var_E8], r13
0x18005873a  mov     dword ptr [rsp+110h+var_F0], eax
0x18005873e  mov     eax, 2
0x180058743  mov     r9d, eax
0x180058746  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18005874d  xor     edx, edx
0x18005874f  mov     ecx, eax
0x180058751  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180058756  nop
0x180058757  lea     rcx, [rbp+57h+arg_10]; this
0x18005875b  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180058760  nop
0x180058761  lea     rcx, [rbp+57h+arg_18]; this
0x180058765  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x18005876a  nop
0x18005876b  lea     rcx, [rbp+57h+var_C0]; this
0x18005876f  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180058774  nop
0x180058775  lea     rcx, [rbp+57h+var_B8]; this
0x180058779  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x18005877e  nop
0x18005877f  lea     rcx, [rbp+57h+var_B0]; this
0x180058783  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180058788  nop
0x180058789  lea     rcx, [rbp+57h+var_A8]; this
0x18005878d  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x180058792  nop
0x180058793  lea     rcx, [rbp+57h+var_A0]; this
0x180058797  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x18005879c  jmp     loc_180058A7D
0x1800587a1  lea     r8, [rdi+220h]
0x1800587a8  lea     rdx, aCertTokenUse; "cert_token_use"
0x1800587af  mov     rcx, rsi
0x1800587b2  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800587b7  lea     r8, [rdi+228h]
0x1800587be  lea     rdx, aX5c; "x5c"
0x1800587c5  mov     rcx, rsi
0x1800587c8  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800587cd  lea     r8, [rdi+230h]
0x1800587d4  lea     rdx, aX5cCa; "x5c_ca"
0x1800587db  mov     rcx, rsi
0x1800587de  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800587e3  lea     r8, [rbp+57h+arg_18]
0x1800587e7  lea     rdx, aTgtAd; "tgt_ad"
0x1800587ee  mov     rcx, rsi
0x1800587f1  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800587f6  lea     r8, [rbp+57h+arg_10]
0x1800587fa  lea     rdx, aTgtCloud; "tgt_cloud"
0x180058801  mov     rcx, rsi
0x180058804  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180058809  mov     r15d, 1
0x18005880f  lea     r14, base
0x180058816  lea     ebx, [r15+2]
0x18005881a  mov     rax, [rbp+57h+arg_18]
0x18005881e  cmp     [rax-10h], r12d
0x180058822  jz      loc_1800588CD
0x180058828  lea     r8, [rdi+258h]; struct OAuthResponse::TgtToken *
0x18005882f  lea     rdx, [rbp+57h+arg_18]; struct CSecureString *
0x180058833  call    ?ParseTgtToken@OAuthResponse@@AEAAJAEBVCSecureString@@AEAUTgtToken@1@@Z; OAuthResponse::ParseTgtToken(CSecureString const &,OAuthResponse::TgtToken &)
0x180058838  mov     [rbp+57h+arg_0], eax
0x18005883b  test    eax, eax
0x18005883d  jns     short loc_18005885D
0x18005883f  mov     [rsp+110h+var_D0], r14
0x180058844  lea     rcx, aHresult; "HRESULT"
0x18005884b  mov     [rsp+110h+var_D8], rcx
0x180058850  mov     dword ptr [rsp+110h+var_E0], 0F9h
0x180058858  jmp     loc_180058735
0x18005885d  mov     rcx, [rdi+288h]; this
0x180058864  cmp     [rcx-10h], r12d
0x180058868  jz      short loc_1800588D2
0x18005886a  mov     rax, r14
0x18005886d  test    rcx, rcx
0x180058870  cmovnz  rax, rcx
0x180058874  mov     [rsp+110h+var_D0], rax
0x180058879  lea     rax, aOnPremTgtError; "on-prem tgt error"
0x180058880  mov     [rsp+110h+var_D8], rax
0x180058885  mov     dword ptr [rsp+110h+var_E0], 0FDh
0x18005888d  mov     [rsp+110h+var_E8], r13
0x180058892  mov     [rsp+110h+var_F0], r12
0x180058897  mov     r9d, ebx
0x18005889a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800588a1  xor     edx, edx
0x1800588a3  mov     ecx, ebx
0x1800588a5  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800588aa  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 40h
0x1800588b1  jz      short loc_1800588CD
0x1800588b3  mov     r8, [rdi+288h]
0x1800588ba  lea     rdx, Aad_CloudAPPlugin_OnpremTgtError
0x1800588c1  lea     rcx, Microsoft_Windows_AAD_Context
0x1800588c8  call    McTemplateU0z_EventWriteTransfer
0x1800588cd  mov     ebx, r12d
0x1800588d0  jmp     short loc_1800588D5
0x1800588d2  mov     ebx, r15d
0x1800588d5  mov     rax, [rbp+57h+arg_10]
0x1800588d9  cmp     [rax-10h], r12d
0x1800588dd  jz      loc_18005898B
0x1800588e3  lea     r8, [rdi+298h]; struct OAuthResponse::TgtToken *
0x1800588ea  lea     rdx, [rbp+57h+arg_10]; struct CSecureString *
0x1800588ee  call    ?ParseTgtToken@OAuthResponse@@AEAAJAEBVCSecureString@@AEAUTgtToken@1@@Z; OAuthResponse::ParseTgtToken(CSecureString const &,OAuthResponse::TgtToken &)
0x1800588f3  mov     [rbp+57h+arg_0], eax
0x1800588f6  test    eax, eax
  ... truncated ...
```
