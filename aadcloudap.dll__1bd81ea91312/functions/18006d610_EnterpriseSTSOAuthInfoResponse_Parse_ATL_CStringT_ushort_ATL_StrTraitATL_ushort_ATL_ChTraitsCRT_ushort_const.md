# EnterpriseSTSOAuthInfoResponse::Parse(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18006d610`
- end: `0x18006db7e`
- name: `?Parse@EnterpriseSTSOAuthInfoResponse@@UEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1390`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067f4`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x1800093e8`
- `0x18000a294`
- `0x18003345c`
- `0x18003694c`
- `0x180036b3c`
- `0x18006d610`
- `0x180071e14`
- `0x180079fdc`
- `0x18007a0fc`
- `0x18007a4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d7cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d886`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d93d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006da0b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006daac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d7cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d886`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006d93d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006da0b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006daac`

## string_xrefs

- `0x18006d75a`: `token_endpoint`
- `0x18006d770`: `access_token_issuer`
- `0x18006d7fe`: `winhello_cert protocol is supported by enterprise STS`
- `0x18006d8b5`: `winhello_cert_kr protocol is supported by enterprise STS`
- `0x18006d7f7`: `winhello_cert protocol is NOT supported by enterprise STS`
- `0x18006d8ae`: `winhello_cert_kr protocol is NOT supported by enterprise STS`
- `0x18006dad8`: `PRT protocol is NOT supported by enterprise STS`
- `0x18006db64`: `PRT protocol is supported by enterprise STS`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnterpriseSTSOAuthInfoResponse::Parse(_DWORD *a1, _QWORD *a2)
{
  __int64 v4; // rcx
  unsigned int *v5; // rbx
  int v6; // eax
  struct CJsonObject *v7; // rdi
  struct CJsonObject **JsonDataAsArray; // rax
  struct CJsonObject **v9; // rbx
  struct CJsonObject *v10; // rcx
  _DWORD *v11; // rdx
  _QWORD *v12; // rcx
  unsigned __int8 v13; // dl
  const char *v14; // rcx
  __int64 v15; // rcx
  struct CJsonObject *v16; // rax
  _DWORD *v17; // rdx
  _QWORD *v18; // rcx
  unsigned __int8 v19; // dl
  const char *v20; // rcx
  __int64 v21; // rcx
  struct CJsonObject *v22; // rax
  _DWORD *v23; // rdx
  _QWORD *v24; // rcx
  unsigned __int8 v25; // dl
  const char *v26; // rcx
  struct CJsonObject **v27; // rax
  __int64 v28; // rcx
  struct CJsonObject *v29; // rax
  _DWORD *v30; // rdx
  _QWORD *v31; // rcx
  struct CJsonObject **v32; // rax
  __int64 v33; // rcx
  struct CJsonObject *v34; // rax
  _DWORD *v35; // rdx
  _QWORD *v36; // rcx
  unsigned int v37; // ebx
  unsigned int v38; // edx
  __int64 v40; // [rsp+20h] [rbp-79h]
  __int64 v41; // [rsp+30h] [rbp-69h]
  __int64 v42; // [rsp+30h] [rbp-69h]
  __int64 v43; // [rsp+30h] [rbp-69h]
  __int64 v44; // [rsp+30h] [rbp-69h]
  __int64 v45; // [rsp+30h] [rbp-69h]
  const char *v46; // [rsp+38h] [rbp-61h]
  __int64 v47; // [rsp+50h] [rbp-49h] BYREF
  const char *v48[6]; // [rsp+58h] [rbp-41h] BYREF
  _BYTE v49[104]; // [rsp+88h] [rbp-11h] BYREF
  int v50; // [rsp+100h] [rbp+67h] BYREF
  struct CJsonObject *v51; // [rsp+110h] [rbp+77h] BYREF
  __int64 v52; // [rsp+118h] [rbp+7Fh] BYREF

  v50 = 0;
  CJsonValue::CJsonValue((CJsonValue *)v49);
  v51 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v48,
    (int)"enterprisestsoauthinforesponse.cpp",
    (int)"EnterpriseSTSOAuthInfoResponse::Parse",
    (int)&v50);
  v5 = a1 + 2;
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0zd_EventWriteTransfer(v4, Aad_CloudAPPlugin_EnterpriseSTS_OAuthInfoResponse, *a2, *v5);
  WPPTraceLogA(
    4,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    4,
    *v5,
    "enterprisestsoauthinforesponse.cpp",
    20,
    "enterpriseSTSOAuthInfoResponse",
    &base);
  if ( *v5 == 200 )
  {
    v6 = WebResponseHelper::ParseJsonObject(a2, v49, &v51);
    v50 = v6;
    if ( v6 >= 0 )
    {
      v7 = v51;
      WebResponseHelper::GetJsonDataAsString(v51, L"authorization_endpoint", a1 + 62);
      WebResponseHelper::GetJsonDataAsString(v7, L"token_endpoint", a1 + 64);
      WebResponseHelper::GetJsonDataAsString(v7, L"access_token_issuer", a1 + 66);
      JsonDataAsArray = (struct CJsonObject **)WebResponseHelper::GetJsonDataAsArray(v7, L"capabilities");
      v9 = JsonDataAsArray;
      if ( JsonDataAsArray )
      {
        v10 = *JsonDataAsArray;
        v51 = *JsonDataAsArray;
        while ( v10 )
        {
          v11 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                              v10,
                              v10);
          if ( v11 )
          {
            v12 = v11 + 2;
            if ( *v11 != 3 )
              v12 = 0;
            if ( v12 )
            {
              v12 = (_QWORD *)*v12;
              if ( *((_DWORD *)v12 - 4) )
              {
                if ( !(unsigned int)_o__wcsicmp(v12, L"winhello_cert") )
                {
                  v13 = 1;
                  goto LABEL_17;
                }
              }
            }
          }
          ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v12, &v51);
          v10 = v51;
        }
      }
      v13 = 0;
LABEL_17:
      a1[69] = v13;
      v14 = "winhello_cert protocol is supported by enterprise STS";
      if ( !v13 )
        v14 = "winhello_cert protocol is NOT supported by enterprise STS";
      LODWORD(v41) = v13 != 0 ? 41 : 46;
      WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "enterprisestsoauthinforesponse.cpp", v41, v14, &base);
      if ( v9 )
      {
        v16 = *v9;
        v51 = *v9;
        while ( v16 )
        {
          v17 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                              v15,
                              v16);
          if ( v17 )
          {
            v18 = v17 + 2;
            if ( *v17 != 3 )
              v18 = 0;
            if ( v18 )
            {
              v18 = (_QWORD *)*v18;
              if ( *((_DWORD *)v18 - 4) )
              {
                if ( !(unsigned int)_o__wcsicmp(v18, L"winhello_cert_kr") )
                {
                  v19 = 1;
                  goto LABEL_31;
                }
              }
            }
          }
          ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v18, &v51);
          v16 = v51;
        }
      }
      v19 = 0;
LABEL_31:
      a1[70] = v19;
      v20 = "winhello_cert_kr protocol is supported by enterprise STS";
      if ( !v19 )
        v20 = "winhello_cert_kr protocol is NOT supported by enterprise STS";
      LODWORD(v42) = v19 != 0 ? 52 : 57;
      WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "enterprisestsoauthinforesponse.cpp", v42, v20, &base);
      if ( v9 )
      {
        v22 = *v9;
        v51 = *v9;
        while ( v22 )
        {
          v23 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                              v21,
                              v22);
          if ( v23 )
          {
            v24 = v23 + 2;
            if ( *v23 != 3 )
              v24 = 0;
            if ( v24 )
            {
              v24 = (_QWORD *)*v24;
              if ( *((_DWORD *)v24 - 4) )
              {
                if ( !(unsigned int)_o__wcsicmp(v24, L"kdf_ver2") )
                {
                  v25 = 1;
                  goto LABEL_45;
                }
              }
            }
          }
          ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v24, &v51);
          v22 = v51;
        }
      }
      v25 = 0;
LABEL_45:
      a1[71] = v25;
      v26 = "KdfVerV2 is supported by enterprise STS";
      if ( !v25 )
        v26 = "KdfVerV2 is NOT supported by enterprise STS";
      LODWORD(v43) = v25 != 0 ? 63 : 68;
      WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "enterprisestsoauthinforesponse.cpp", v43, v26, &base);
      v27 = (struct CJsonObject **)WebResponseHelper::GetJsonDataAsArray(v7, L"scopes_supported");
      if ( v27 )
      {
        v29 = *v27;
        v51 = v29;
        while ( v29 )
        {
          v30 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                              v28,
                              v29);
          if ( v30 )
          {
            v31 = v30 + 2;
            if ( *v30 != 3 )
              v31 = 0;
            if ( v31 )
            {
              v31 = (_QWORD *)*v31;
              if ( *((_DWORD *)v31 - 4) )
              {
                if ( !(unsigned int)_o__wcsicmp(v31, L"aza") )
                {
                  LODWORD(v44) = 75;
                  WPPTraceLogA(
                    4,
                    0,
                    "%x 0x%08x %s:%u : %s:%ws",
                    4,
                    0,
                    "enterprisestsoauthinforesponse.cpp",
                    v44,
                    "Found aza scope in enterprise STS OAuthInfo Response",
                    &base);
                  v32 = (struct CJsonObject **)WebResponseHelper::GetJsonDataAsArray(v7, L"grant_types_supported");
                  if ( v32 )
                  {
                    v34 = *v32;
                    v51 = v34;
                    while ( v34 )
                    {
                      v35 = *(_DWORD **)ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(
                                          v33,
                                          v34);
                      if ( v35 )
                      {
                        v36 = v35 + 2;
                        if ( *v35 != 3 )
                          v36 = 0;
                        if ( v36 )
                        {
                          v36 = (_QWORD *)*v36;
                          if ( *((_DWORD *)v36 - 4) )
                          {
                            if ( !(unsigned int)_o__wcsicmp(v36, L"urn:ietf:params:oauth:grant-type:jwt-bearer") )
                            {
                              a1[68] = 1;
                              v46 = "PRT protocol is supported by enterprise STS";
                              LODWORD(v45) = 81;
                              goto LABEL_70;
                            }
                          }
                        }
                      }
                      ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(
                        v36,
                        &v51);
                      v34 = v51;
                    }
                  }
                  a1[68] = 0;
                  v46 = "PRT protocol is NOT supported by enterprise STS";
                  LODWORD(v45) = 86;
LABEL_70:
                  WPPTraceLogA(
                    4,
                    0,
                    "%x 0x%08x %s:%u : %s:%ws",
                    4,
                    0,
                    "enterprisestsoauthinforesponse.cpp",
                    v45,
                    v46,
                    &base);
                  break;
                }
              }
            }
          }
          ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(v31, &v51);
          v29 = v51;
        }
      }
    }
    else
    {
      LODWORD(v41) = 29;
      LODWORD(v40) = v6;
      WPPTraceLogA(
        2,
        0,
        "%x 0x%08x %s:%u : %s:%ws",
        2,
        v40,
        "enterprisestsoauthinforesponse.cpp",
        v41,
        "HRESULT",
        &base);
    }
  }
  v37 = v50;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v48);
  ATL::CStringData::Release((ATL::CStringData *)(v52 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v47 - 24));
  CJsonValue::~CJsonValue((CJsonValue *)v49, v38);
  return v37;
}

```

## disassembly

```asm
0x18006d610  mov     [rsp-8+arg_8], rbx
0x18006d615  push    rbp
0x18006d616  push    rsi
0x18006d617  push    rdi
0x18006d618  push    r12
0x18006d61a  push    r13
0x18006d61c  push    r14
0x18006d61e  push    r15
0x18006d620  lea     rbp, [rsp-27h]
0x18006d625  sub     rsp, 0C0h
0x18006d62c  mov     rdi, rdx
0x18006d62f  mov     rsi, rcx
0x18006d632  xor     r14d, r14d
0x18006d635  mov     [rbp+57h+arg_0], r14d
0x18006d639  lea     rcx, [rbp+57h+var_68]; this
0x18006d63d  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x18006d642  nop
0x18006d643  mov     [rbp+57h+arg_10], r14
0x18006d647  lea     rcx, [rbp+57h+var_A0]; void *
0x18006d64b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006d650  nop
0x18006d651  lea     rcx, [rbp+57h+arg_18]; void *
0x18006d655  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18006d65a  nop
0x18006d65b  lea     r9, [rbp+57h+arg_0]
0x18006d65f  lea     r8, aEnterprisestso; "EnterpriseSTSOAuthInfoResponse::Parse"
0x18006d666  lea     r12, aOnecoreuapDsEx_67+21h; "enterprisestsoauthinforesponse.cpp"
0x18006d66d  mov     rdx, r12
0x18006d670  lea     rcx, [rbp+57h+var_98]
0x18006d674  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18006d679  nop
0x18006d67a  lea     rbx, [rsi+8]
0x18006d67e  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18006d685  jz      short loc_18006D699
0x18006d687  mov     r9d, [rbx]
0x18006d68a  mov     r8, [rdi]
0x18006d68d  lea     rdx, Aad_CloudAPPlugin_EnterpriseSTS_OAuthInfoResponse
0x18006d694  call    McTemplateU0zd_EventWriteTransfer
0x18006d699  lea     rax, base
0x18006d6a0  mov     [rsp+0F0h+var_B0], rax
0x18006d6a5  lea     rax, aEnterprisestso_0; "enterpriseSTSOAuthInfoResponse"
0x18006d6ac  mov     [rsp+0F0h+var_B8], rax
0x18006d6b1  mov     dword ptr [rsp+0F0h+var_C0], 14h
0x18006d6b9  mov     [rsp+0F0h+var_C8], r12
0x18006d6be  mov     eax, [rbx]
0x18006d6c0  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18006d6c4  mov     r15d, 4
0x18006d6ca  mov     r9d, r15d
0x18006d6cd  lea     r13, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18006d6d4  mov     r8, r13
0x18006d6d7  xor     edx, edx
0x18006d6d9  mov     ecx, r15d
0x18006d6dc  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006d6e1  cmp     dword ptr [rbx], 0C8h
0x18006d6e7  jnz     loc_18006DB06
0x18006d6ed  lea     r8, [rbp+57h+arg_10]
0x18006d6f1  lea     rdx, [rbp+57h+var_68]
0x18006d6f5  mov     rcx, rdi
0x18006d6f8  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x18006d6fd  mov     [rbp+57h+arg_0], eax
0x18006d700  test    eax, eax
0x18006d702  jns     short loc_18006D739
0x18006d704  lea     rcx, base
0x18006d70b  mov     [rsp+0F0h+var_B0], rcx
0x18006d710  lea     rcx, aHresult; "HRESULT"
0x18006d717  mov     [rsp+0F0h+var_B8], rcx
0x18006d71c  mov     dword ptr [rsp+0F0h+var_C0], 1Dh
0x18006d724  mov     [rsp+0F0h+var_C8], r12
0x18006d729  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18006d72d  lea     ecx, [r15-2]
0x18006d731  mov     r9d, ecx
0x18006d734  jmp     loc_18006DAFC
0x18006d739  lea     r8, [rsi+0F8h]
0x18006d740  lea     rdx, aAuthorizationE; "authorization_endpoint"
0x18006d747  mov     rdi, [rbp+57h+arg_10]
0x18006d74b  mov     rcx, rdi
0x18006d74e  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18006d753  lea     r8, [rsi+100h]
0x18006d75a  lea     rdx, aTokenEndpoint; "token_endpoint"
0x18006d761  mov     rcx, rdi
0x18006d764  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18006d769  lea     r8, [rsi+108h]
0x18006d770  lea     rdx, aAccessTokenIss; "access_token_issuer"
0x18006d777  mov     rcx, rdi
0x18006d77a  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18006d77f  lea     rdx, aCapabilities; "capabilities"
0x18006d786  mov     rcx, rdi; struct CJsonObject *
0x18006d789  call    ?GetJsonDataAsArray@WebResponseHelper@@SAPEAVCJsonArray@@PEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsArray(CJsonObject *,ushort const *)
0x18006d78e  mov     rbx, rax
0x18006d791  test    rax, rax
0x18006d794  jz      short loc_18006D7EB
0x18006d796  mov     rcx, [rax]
0x18006d799  mov     [rbp+57h+arg_10], rcx
0x18006d79d  jmp     short loc_18006D7E6
0x18006d79f  mov     rdx, rcx
0x18006d7a2  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x18006d7a7  mov     rdx, [rax]
0x18006d7aa  test    rdx, rdx
0x18006d7ad  jz      short loc_18006D7D9
0x18006d7af  lea     rcx, [rdx+8]
0x18006d7b3  cmp     dword ptr [rdx], 3
0x18006d7b6  cmovnz  rcx, r14
0x18006d7ba  test    rcx, rcx
0x18006d7bd  jz      short loc_18006D7D9
0x18006d7bf  mov     rcx, [rcx]
0x18006d7c2  cmp     [rcx-10h], r14d
0x18006d7c6  jz      short loc_18006D7D9
0x18006d7c8  lea     rdx, aWinhelloCert; "winhello_cert"
0x18006d7cf  call    cs:__imp__o__wcsicmp
0x18006d7d5  test    eax, eax
0x18006d7d7  jz      short loc_18006D852
0x18006d7d9  lea     rdx, [rbp+57h+arg_10]
0x18006d7dd  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x18006d7e2  mov     rcx, [rbp+57h+arg_10]
0x18006d7e6  test    rcx, rcx
0x18006d7e9  jnz     short loc_18006D79F
0x18006d7eb  mov     dl, r14b
0x18006d7ee  movzx   eax, dl
0x18006d7f1  mov     [rsi+114h], eax
0x18006d7f7  lea     rax, aWinhelloCertPr; "winhello_cert protocol is NOT supported"...
0x18006d7fe  lea     rcx, aWinhelloCertPr_0; "winhello_cert protocol is supported by "...
0x18006d805  test    dl, dl
0x18006d807  cmovz   rcx, rax
0x18006d80b  neg     dl
0x18006d80d  sbb     eax, eax
0x18006d80f  and     eax, 0FFFFFFFBh
0x18006d812  add     eax, 2Eh ; '.'
0x18006d815  lea     rdx, base
0x18006d81c  mov     [rsp+0F0h+var_B0], rdx
0x18006d821  mov     [rsp+0F0h+var_B8], rcx
0x18006d826  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18006d82a  mov     [rsp+0F0h+var_C8], r12
0x18006d82f  mov     [rsp+0F0h+var_D0], r14
0x18006d834  mov     r9d, r15d
0x18006d837  mov     r8, r13
0x18006d83a  xor     edx, edx
0x18006d83c  mov     ecx, r15d
0x18006d83f  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006d844  test    rbx, rbx
0x18006d847  jz      short loc_18006D8A2
0x18006d849  mov     rax, [rbx]
0x18006d84c  mov     [rbp+57h+arg_10], rax
0x18006d850  jmp     short loc_18006D89D
0x18006d852  mov     dl, 1
0x18006d854  jmp     short loc_18006D7EE
0x18006d856  mov     rdx, rax
0x18006d859  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x18006d85e  mov     rdx, [rax]
0x18006d861  test    rdx, rdx
0x18006d864  jz      short loc_18006D890
0x18006d866  lea     rcx, [rdx+8]
0x18006d86a  cmp     dword ptr [rdx], 3
0x18006d86d  cmovnz  rcx, r14
0x18006d871  test    rcx, rcx
0x18006d874  jz      short loc_18006D890
0x18006d876  mov     rcx, [rcx]
0x18006d879  cmp     [rcx-10h], r14d
0x18006d87d  jz      short loc_18006D890
0x18006d87f  lea     rdx, aWinhelloCertKr; "winhello_cert_kr"
0x18006d886  call    cs:__imp__o__wcsicmp
0x18006d88c  test    eax, eax
0x18006d88e  jz      short loc_18006D909
0x18006d890  lea     rdx, [rbp+57h+arg_10]
0x18006d894  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x18006d899  mov     rax, [rbp+57h+arg_10]
0x18006d89d  test    rax, rax
0x18006d8a0  jnz     short loc_18006D856
0x18006d8a2  mov     dl, r14b
0x18006d8a5  movzx   eax, dl
0x18006d8a8  mov     [rsi+118h], eax
0x18006d8ae  lea     rax, aWinhelloCertKr_1; "winhello_cert_kr protocol is NOT suppor"...
0x18006d8b5  lea     rcx, aWinhelloCertKr_0; "winhello_cert_kr protocol is supported "...
0x18006d8bc  test    dl, dl
0x18006d8be  cmovz   rcx, rax
0x18006d8c2  neg     dl
0x18006d8c4  sbb     eax, eax
0x18006d8c6  and     eax, 0FFFFFFFBh
0x18006d8c9  add     eax, 39h ; '9'
0x18006d8cc  lea     rdx, base
0x18006d8d3  mov     [rsp+0F0h+var_B0], rdx
0x18006d8d8  mov     [rsp+0F0h+var_B8], rcx
0x18006d8dd  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18006d8e1  mov     [rsp+0F0h+var_C8], r12
0x18006d8e6  mov     [rsp+0F0h+var_D0], r14
0x18006d8eb  mov     r9d, r15d
0x18006d8ee  mov     r8, r13
0x18006d8f1  xor     edx, edx
0x18006d8f3  mov     ecx, r15d
0x18006d8f6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006d8fb  test    rbx, rbx
0x18006d8fe  jz      short loc_18006D95D
0x18006d900  mov     rax, [rbx]
0x18006d903  mov     [rbp+57h+arg_10], rax
0x18006d907  jmp     short loc_18006D958
0x18006d909  mov     dl, 1
0x18006d90b  jmp     short loc_18006D8A5
0x18006d90d  mov     rdx, rax
0x18006d910  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x18006d915  mov     rdx, [rax]
0x18006d918  test    rdx, rdx
0x18006d91b  jz      short loc_18006D94B
0x18006d91d  lea     rcx, [rdx+8]
0x18006d921  cmp     dword ptr [rdx], 3
0x18006d924  cmovnz  rcx, r14
0x18006d928  test    rcx, rcx
0x18006d92b  jz      short loc_18006D94B
0x18006d92d  mov     rcx, [rcx]
0x18006d930  cmp     [rcx-10h], r14d
0x18006d934  jz      short loc_18006D94B
0x18006d936  lea     rdx, aKdfVer2; "kdf_ver2"
0x18006d93d  call    cs:__imp__o__wcsicmp
0x18006d943  test    eax, eax
0x18006d945  jz      loc_18006D9D7
0x18006d94b  lea     rdx, [rbp+57h+arg_10]
0x18006d94f  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x18006d954  mov     rax, [rbp+57h+arg_10]
0x18006d958  test    rax, rax
0x18006d95b  jnz     short loc_18006D90D
0x18006d95d  mov     dl, r14b
0x18006d960  movzx   eax, dl
0x18006d963  mov     [rsi+11Ch], eax
0x18006d969  lea     rax, aKdfverv2IsNotS; "KdfVerV2 is NOT supported by enterprise"...
0x18006d970  lea     rcx, aKdfverv2IsSupp; "KdfVerV2 is supported by enterprise STS"
0x18006d977  test    dl, dl
0x18006d979  cmovz   rcx, rax
0x18006d97d  neg     dl
0x18006d97f  sbb     eax, eax
0x18006d981  and     eax, 0FFFFFFFBh
0x18006d984  add     eax, 44h ; 'D'
0x18006d987  lea     rbx, base
0x18006d98e  mov     [rsp+0F0h+var_B0], rbx
0x18006d993  mov     [rsp+0F0h+var_B8], rcx
0x18006d998  mov     dword ptr [rsp+0F0h+var_C0], eax
0x18006d99c  mov     [rsp+0F0h+var_C8], r12
0x18006d9a1  mov     [rsp+0F0h+var_D0], r14
0x18006d9a6  mov     r9d, r15d
0x18006d9a9  mov     r8, r13
0x18006d9ac  xor     edx, edx
0x18006d9ae  mov     ecx, r15d
0x18006d9b1  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006d9b6  lea     rdx, aScopesSupporte; "scopes_supported"
0x18006d9bd  mov     rcx, rdi; struct CJsonObject *
0x18006d9c0  call    ?GetJsonDataAsArray@WebResponseHelper@@SAPEAVCJsonArray@@PEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsArray(CJsonObject *,ushort const *)
0x18006d9c5  test    rax, rax
0x18006d9c8  jz      loc_18006DB06
0x18006d9ce  mov     rax, [rax]
0x18006d9d1  mov     [rbp+57h+arg_10], rax
0x18006d9d5  jmp     short loc_18006DA22
0x18006d9d7  mov     dl, 1
0x18006d9d9  jmp     short loc_18006D960
0x18006d9db  mov     rdx, rax
0x18006d9de  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x18006d9e3  mov     rdx, [rax]
0x18006d9e6  test    rdx, rdx
0x18006d9e9  jz      short loc_18006DA15
0x18006d9eb  lea     rcx, [rdx+8]
0x18006d9ef  cmp     dword ptr [rdx], 3
0x18006d9f2  cmovnz  rcx, r14
0x18006d9f6  test    rcx, rcx
0x18006d9f9  jz      short loc_18006DA15
0x18006d9fb  mov     rcx, [rcx]
0x18006d9fe  cmp     [rcx-10h], r14d
0x18006da02  jz      short loc_18006DA15
0x18006da04  lea     rdx, aAza; "aza"
0x18006da0b  call    cs:__imp__o__wcsicmp
0x18006da11  test    eax, eax
0x18006da13  jz      short loc_18006DA2C
0x18006da15  lea     rdx, [rbp+57h+arg_10]
0x18006da19  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x18006da1e  mov     rax, [rbp+57h+arg_10]
0x18006da22  test    rax, rax
0x18006da25  jnz     short loc_18006D9DB
0x18006da27  jmp     loc_18006DB06
0x18006da2c  mov     [rsp+0F0h+var_B0], rbx
0x18006da31  lea     rax, aFoundAzaScopeI; "Found aza scope in enterprise STS OAuth"...
0x18006da38  mov     [rsp+0F0h+var_B8], rax
0x18006da3d  mov     dword ptr [rsp+0F0h+var_C0], 4Bh ; 'K'
0x18006da45  mov     [rsp+0F0h+var_C8], r12
0x18006da4a  mov     [rsp+0F0h+var_D0], r14
0x18006da4f  mov     r9d, r15d
0x18006da52  mov     r8, r13
0x18006da55  xor     edx, edx
0x18006da57  mov     ecx, r15d
0x18006da5a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18006da5f  lea     rdx, aGrantTypesSupp; "grant_types_supported"
0x18006da66  mov     rcx, rdi; struct CJsonObject *
0x18006da69  call    ?GetJsonDataAsArray@WebResponseHelper@@SAPEAVCJsonArray@@PEAVCJsonObject@@PEBG@Z; WebResponseHelper::GetJsonDataAsArray(CJsonObject *,ushort const *)
0x18006da6e  test    rax, rax
0x18006da71  jz      short loc_18006DACC
0x18006da73  mov     rax, [rax]
0x18006da76  mov     [rbp+57h+arg_10], rax
0x18006da7a  jmp     short loc_18006DAC7
0x18006da7c  mov     rdx, rax
0x18006da7f  call    ?GetAt@?$CAtlList@V?$CAutoPtr@VCJsonValue@@@ATL@@V?$CAutoPtrElementTraits@VCJsonValue@@@2@@ATL@@QEBAAEBV?$CAutoPtr@VCJsonValue@@@2@PEAU__POSITION@@@Z; ATL::CAtlList<ATL::CAutoPtr<CJsonValue>,ATL::CAutoPtrElementTraits<CJsonValue>>::GetAt(__POSITION *)
0x18006da84  mov     rdx, [rax]
0x18006da87  test    rdx, rdx
0x18006da8a  jz      short loc_18006DABA
0x18006da8c  lea     rcx, [rdx+8]
0x18006da90  cmp     dword ptr [rdx], 3
0x18006da93  cmovnz  rcx, r14
  ... truncated ...
```
