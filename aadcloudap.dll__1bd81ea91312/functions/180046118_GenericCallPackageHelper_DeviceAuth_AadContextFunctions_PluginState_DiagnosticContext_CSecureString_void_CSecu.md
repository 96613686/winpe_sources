# GenericCallPackageHelper::DeviceAuth(AadContextFunctions *,PluginState &,DiagnosticContext &,CSecureString &,void *,CSecureString &,CSecureString &)

- ea: `0x180046118`
- end: `0x180046c7a`
- name: `?DeviceAuth@GenericCallPackageHelper@@SAJPEAVAadContextFunctions@@AEAVPluginState@@AEAVDiagnosticContext@@AEAVCSecureString@@PEAX33@Z`
- size: `2914`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, struct PluginState *, struct DiagnosticContext *, struct CSecureString *, HANDLE TokenHandle, struct CSecureString *, struct CSecureString *)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800477bc`

## callees

- `0x180001cfc`
- `0x180001f7c`
- `0x1800063f4`
- `0x1800065e8`
- `0x1800067f4`
- `0x18000685c`
- `0x1800069c0`
- `0x180006ac4`
- `0x1800090d0`
- `0x1800093e8`
- `0x18000a294`
- `0x18000a300`
- `0x18000c7ac`
- `0x18001d0ec`
- `0x18001f474`
- `0x180030040`
- `0x180030300`
- `0x180036b3c`
- `0x18003f010`
- `0x18003f30c`
- `0x18003fa88`
- `0x180046118`
- `0x180047320`
- `0x18004861c`
- `0x18004aad0`
- `0x180051cf4`
- `0x180071e14`
- `0x180077ab4`
- `0x180077b34`
- `0x180079658`
- `0x18007a0bc`
- `0x18007a0fc`
- `0x18007a4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046595`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046612`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046627`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046649`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004666e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046595`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800465e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046612`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046627`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180046649`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004666e`

## string_xrefs

- `0x18004658b`: `token_type`
- `0x1800464b3`: `ms-appx-web://Microsoft.AAD.BrokerPlugin`
- `0x18004650a`: `ms-appx-web://Microsoft.AAD.BrokerPlugin`
- `0x180046963`: `binding claims loaded from cache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GenericCallPackageHelper::DeviceAuth(
        struct AadContextFunctions *a1,
        struct PluginState *a2,
        struct DiagnosticContext *a3,
        struct CSecureString *a4,
        HANDLE TokenHandle,
        struct CSecureString *a6,
        struct CSecureString *a7)
{
  unsigned int v10; // r15d
  int v11; // eax
  int appended; // ebx
  struct CJsonObject *v13; // rbx
  struct CJsonObject *JsonDataAsObject; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int16 *v17; // rsi
  unsigned __int16 *v18; // rdi
  unsigned __int16 *v19; // r14
  int v20; // r9d
  bool v21; // si
  char v22; // di
  char v23; // r14
  _QWORD *Next; // rax
  _QWORD *v25; // rbx
  const wchar_t *v26; // rdx
  bool v27; // zf
  int DefaultTokenBindingKeyType; // eax
  const wchar_t *v29; // rdx
  const WCHAR *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // r15
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r15
  unsigned int v37; // ebx
  unsigned __int16 *v39; // [rsp+28h] [rbp-E0h]
  unsigned __int16 *v40; // [rsp+38h] [rbp-D0h]
  unsigned __int16 *v41; // [rsp+38h] [rbp-D0h]
  char v42; // [rsp+88h] [rbp-80h]
  unsigned int v43[3]; // [rsp+8Ch] [rbp-7Ch] BYREF
  __int64 v44; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v45; // [rsp+A0h] [rbp-68h] BYREF
  struct CJsonObject *v46; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v48; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v51; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v52; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v53; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v55; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v56; // [rsp+F8h] [rbp-10h] BYREF
  ATL::CStringData *v57; // [rsp+100h] [rbp-8h] BYREF
  __int64 v58; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 *v59; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int16 *v60; // [rsp+118h] [rbp+10h] BYREF
  __int128 v61; // [rsp+120h] [rbp+18h] BYREF
  __int64 v62; // [rsp+130h] [rbp+28h]
  __int128 v63; // [rsp+138h] [rbp+30h]
  int v64; // [rsp+148h] [rbp+40h]
  __int64 v65[2]; // [rsp+150h] [rbp+48h] BYREF
  __int64 v66; // [rsp+160h] [rbp+58h]
  __int128 v67; // [rsp+168h] [rbp+60h]
  int v68; // [rsp+178h] [rbp+70h]
  _BYTE v69[56]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v70[96]; // [rsp+1B8h] [rbp+B0h] BYREF

  v43[0] = 0;
  CJsonValue::CJsonValue((CJsonValue *)v69);
  v46 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v56);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v53);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v49);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v48);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  *(_OWORD *)v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 10;
  v58 = 0;
  v10 = 0;
  v45 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v70,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::DeviceAuth",
    v43);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a7);
  v11 = SecurityGroupsHelper::CheckUserIsSystem(TokenHandle);
  v43[0] = v11;
  if ( v11 < 0 )
  {
    LODWORD(v40) = 614;
LABEL_3:
    LODWORD(v39) = v11;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v39, "genericcallpackagehelper.cpp", v40, "NTSTATUS", &base);
    goto LABEL_85;
  }
  if ( !PluginState::IsCloudDomainJoined(a2) )
  {
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      -2147187631,
      "genericcallpackagehelper.cpp",
      618,
      "HRESULT",
      &base);
    v43[0] = -1073445807;
    goto LABEL_85;
  }
  if ( !*(_DWORD *)(*(_QWORD *)a4 - 16LL) )
  {
    WPPTraceLogA(
      2,
      0,
      "%x 0x%08x %s:%u : %s:%ws",
      2,
      -2147187439,
      "genericcallpackagehelper.cpp",
      623,
      "HRESULT",
      &base);
    v43[0] = -1073445615;
    goto LABEL_85;
  }
  appended = WebResponseHelper::ParseJsonObject(a4, v69, &v46);
  if ( appended < 0 )
  {
    LODWORD(v40) = 627;
    goto LABEL_84;
  }
  v13 = v46;
  WebResponseHelper::GetJsonDataAsString(v46, L"resource", &v53);
  WebResponseHelper::GetJsonDataAsString(v13, L"clientid", &v52);
  WebResponseHelper::GetJsonDataAsString(v13, L"scope", &v51);
  JsonDataAsObject = WebResponseHelper::GetJsonDataAsObject(v13, L"extraparams");
  if ( JsonDataAsObject )
  {
    appended = WebResponseHelper::ConvertJsonObjectToKeyValueList(JsonDataAsObject, 0, v16, v65);
    if ( appended < 0 )
    {
      LODWORD(v40) = 636;
      goto LABEL_84;
    }
  }
  v17 = v53;
  v18 = v52;
  v19 = v51;
  if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      v15,
      (unsigned int)Aad_CloudAPPlugin_GetDeviceToken,
      (_DWORD)v53,
      (_DWORD)v52,
      (__int64)v51);
  if ( (unsigned int)dword_1800E5050 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E5050, 0x400000000000LL) )
  {
    v46 = (struct CJsonObject *)v19;
    v59 = v17;
    v60 = v18;
    v57 = (ATL::CStringData *)2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v15,
      (unsigned int)&word_1800D2FD6,
      *((_QWORD *)a3 + 7),
      v20,
      (__int64)&v57,
      (__int64)&v60,
      (__int64)&v59,
      (__int64)&v46);
  }
  if ( *(_DWORD *)(*(_QWORD *)a6 - 16LL) )
  {
    appended = StringUtility::StringFormat(&v50, L"%s/%s", L"ms-appx-web://Microsoft.AAD.BrokerPlugin");
    if ( appended < 0 )
    {
      LODWORD(v40) = 649;
      goto LABEL_84;
    }
  }
  else if ( *((_DWORD *)v18 - 4) )
  {
    appended = StringUtility::StringFormat(&v50, L"%s/%s", L"ms-appx-web://Microsoft.AAD.BrokerPlugin", v18);
    if ( appended < 0 )
    {
      LODWORD(v40) = 653;
      goto LABEL_84;
    }
  }
  if ( !v66 )
    goto LABEL_79;
  v46 = (struct CJsonObject *)v65[0];
  if ( !v65[0] )
    goto LABEL_79;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  while ( 1 )
  {
    Next = (_QWORD *)ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(
                       v15,
                       &v46);
    v25 = Next;
    if ( !v23 && !(unsigned int)_o__wcsicmp(*Next, L"token_type") )
    {
      v21 = !(unsigned int)_o__wcsicmp(v25[1], L"pop") || !(unsigned int)_o__wcsicmp(v25[1], L"shr");
      v23 = 1;
      goto LABEL_47;
    }
    if ( v22 || (unsigned int)_o__wcsicmp(*v25, L"req_cnf") )
      break;
    v22 = 1;
LABEL_47:
    if ( !v46 )
      goto LABEL_48;
  }
  if ( !*(_DWORD *)(v44 - 16) && !(unsigned int)_o__wcsicmp(*v25, L"enclave") )
  {
    if ( (unsigned int)_o__wcsicmp(v25[1], L"hw") )
    {
      if ( !(unsigned int)_o__wcsicmp(v25[1], L"kg") )
      {
        v10 = 2;
        v45 = 2;
        v26 = L"kg";
LABEL_46:
        CSecureString::operator=(&v44, v26);
        goto LABEL_47;
      }
      if ( (unsigned int)_o__wcsicmp(v25[1], L"sw") )
        goto LABEL_47;
      v10 = 0;
      v26 = L"sw";
    }
    else
    {
      v10 = 1;
      v26 = L"hw";
    }
    v45 = v10;
    goto LABEL_46;
  }
LABEL_48:
  v42 = v22;
  v27 = !v21;
  v18 = v52;
  v17 = v53;
  v19 = v51;
  if ( v27 || v42 )
  {
LABEL_79:
    v31 = v47;
    goto LABEL_80;
  }
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 10;
  if ( !*(_DWORD *)(v44 - 16) )
  {
    DefaultTokenBindingKeyType = GenericCallPackageHelper::GetDefaultTokenBindingKeyType(a1, &v45);
    v43[0] = DefaultTokenBindingKeyType;
    if ( DefaultTokenBindingKeyType < 0 )
    {
      LODWORD(v40) = 705;
      goto LABEL_53;
    }
    v10 = v45;
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%u",
      4,
      0,
      "genericcallpackagehelper.cpp",
      706,
      "Using default key type",
      v45);
    switch ( v10 )
    {
      case 1u:
        v29 = L"hw";
        goto LABEL_60;
      case 2u:
        v29 = L"kg";
        goto LABEL_60;
      case 0u:
        v29 = L"sw";
LABEL_60:
        CSecureString::operator=(&v44, v29);
        break;
    }
  }
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%u", 4, 0, "genericcallpackagehelper.cpp", 725, "binding key type", v10);
  v30 = &base;
  if ( v44 )
    v30 = (const WCHAR *)v44;
  LODWORD(v41) = 726;
  WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "genericcallpackagehelper.cpp", v41, "binding key enclave", v30);
  DefaultTokenBindingKeyType = GenericCallPackageHelper::GenerateTokenBindingKeyContainerName(
                                 a1,
                                 TokenHandle,
                                 0,
                                 0,
                                 v18,
                                 v17,
                                 v19,
                                 v10,
                                 (struct CSecureString *)&v47,
                                 (struct CSecureString *)&v54);
  v43[0] = DefaultTokenBindingKeyType;
  if ( DefaultTokenBindingKeyType < 0 )
  {
    LODWORD(v40) = 738;
    goto LABEL_53;
  }
  DefaultTokenBindingKeyType = TokenBindingHelper::LoadBindingKeyFromCache(
                                 a2,
                                 (const struct CSecureString *)&v47,
                                 0,
                                 (struct CSecureString *)&v49);
  v43[0] = DefaultTokenBindingKeyType;
  if ( DefaultTokenBindingKeyType < 0 )
  {
    LODWORD(v40) = 740;
    goto LABEL_53;
  }
  v31 = v47;
  if ( !*(_DWORD *)(v49 - 16) )
  {
LABEL_78:
    ATL::CAtlList<CSecureString,ATL::CElementTraits<CSecureString>>::RemoveAll(&v61);
LABEL_80:
    v11 = RequestDeviceToken(
            a1,
            (__int64)v19,
            (__int64)v17,
            (__int64)v18,
            v50,
            (__int64)v65,
            (__int64)&v49,
            (__int64)&v48,
            (__int64)&v44,
            (__int64)&v56,
            (__int64)&v55,
            (__int64)&v58);
    v43[0] = v11;
    if ( v11 < 0 )
    {
      LODWORD(v40) = 777;
      goto LABEL_3;
    }
    appended = StringUtility::StringAppendFormat(
                 a7,
                 L"\"%s\" : %d, \"%s\" : \"%s\", \"%s\" : \"%s\", \"%s\" : \"%s\", \"%s\" : \"%lld\", \"%s\" : \"%s\", \"%s\" : \"%s\"",
                 L"call",
                 5,
                 L"assertion",
                 v56,
                 L"deviceinfo",
                 v55,
                 L"authority",
                 *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 8LL),
                 L"expireson",
                 v58,
                 L"BindingKeyId",
                 v31,
                 L"BindingKeyEnclave",
                 v44);
    if ( appended >= 0 )
      goto LABEL_85;
    LODWORD(v40) = 786;
LABEL_84:
    LODWORD(v39) = appended;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v39, "genericcallpackagehelper.cpp", v40, "HRESULT", &base);
    v43[0] = appended & 0xAFFFFFFF | 0x40000000;
    goto LABEL_85;
  }
  DefaultTokenBindingKeyType = TokenBindingHelper::LoadBindingClaims(
                                 (_DWORD)a2,
                                 v47,
                                 v54,
                                 *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a2 + 8LL) + 24LL),
                                 (__int64)&v61);
  v43[0] = DefaultTokenBindingKeyType;
  if ( DefaultTokenBindingKeyType >= 0 )
  {
    WPPTraceLogA(
      4,
      0,
      "%x 0x%08x %s:%u : %s:%u",
      4,
      0,
      "genericcallpackagehelper.cpp",
      751,
      "binding claims loaded from cache",
      v62);
    v32 = v61;
    if ( (_QWORD)v61 )
    {
      if ( (Microsoft_Windows_AADEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          Microsoft_Windows_AAD_Context,
          Aad_CloudAPPlugin_Token_Binding_Including_Claim,
          *((_QWORD *)a3 + 3));
      v33 = *(_QWORD *)(v32 + 16);
      v34 = (_QWORD *)(v33 - 24);
      v35 = v48 - 24;
      v57 = (ATL::CStringData *)(v48 - 24);
      if ( v33 - 24 != v48 - 24 )
      {
        if ( *(int *)(v35 + 16) >= 0 && *v34 == *(_QWORD *)v35 )
        {
          v36 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v34);
          ATL::CStringData::Release(v57);
          v48 = v36 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v48, v33, *(unsigned int *)(v33 - 16));
        }
      }
    }
    goto LABEL_78;
  }
  LODWORD(v40) = 749;
LABEL_53:
  LODWORD(v39) = DefaultTokenBindingKeyType;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v39, "genericcallpackagehelper.cpp", v40, "NTSTATUS", &base);
  ATL::CAtlList<CSecureString,ATL::CElementTraits<CSecureString>>::RemoveAll(&v61);
LABEL_85:
  v37 = v43[0];
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v70);
  CSecureString::~CSecureString((CSecureString *)&v54);
  ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::RemoveAll(v65);
  CSecureString::~CSecureString((CSecureString *)&v44);
  CSecureString::~CSecureString((CSecureString *)&v47);
  CSecureString::~CSecureString((CSecureString *)&v48);
  CSecureString::~CSecureString((CSecureString *)&v49);
  CSecureString::~CSecureString((CSecureString *)&v50);
  CSecureString::~CSecureString((CSecureString *)&v51);
  CSecureString::~CSecureString((CSecureString *)&v52);
  CSecureString::~CSecureString((CSecureString *)&v53);
  CSecureString::~CSecureString((CSecureString *)&v55);
  CSecureString::~CSecureString((CSecureString *)&v56);
  CJsonValue::~CJsonValue((CJsonValue *)v69);
  return v37;
}

```

## disassembly

```asm
0x180046118  mov     rax, rsp
0x18004611b  mov     [rax+20h], rbx
0x18004611f  mov     [rax+18h], r8
0x180046123  mov     [rax+10h], rdx
0x180046127  mov     [rax+8], rcx
0x18004612b  push    rbp
0x18004612c  push    rsi
0x18004612d  push    rdi
0x18004612e  push    r12
0x180046130  push    r13
0x180046132  push    r14
0x180046134  push    r15
0x180046136  lea     rbp, [rax-118h]
0x18004613d  sub     rsp, 1E0h
0x180046144  mov     rbx, r9
0x180046147  mov     r13, r8
0x18004614a  mov     rdi, rdx
0x18004614d  xor     r12d, r12d
0x180046150  mov     [rbp+110h+var_18C], r12d
0x180046154  lea     rcx, [rbp+110h+var_98]; this
0x180046158  call    ??0CJsonValue@@QEAA@XZ; CJsonValue::CJsonValue(void)
0x18004615d  nop
0x18004615e  mov     [rbp+110h+var_170], r12
0x180046162  lea     rcx, [rbp+110h+var_120]; void *
0x180046166  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004616b  nop
0x18004616c  lea     rcx, [rbp+110h+var_128]; void *
0x180046170  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180046175  nop
0x180046176  lea     rcx, [rbp+110h+var_138]; void *
0x18004617a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004617f  nop
0x180046180  lea     rcx, [rbp+110h+var_140]; void *
0x180046184  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180046189  nop
0x18004618a  lea     rcx, [rbp+110h+var_148]; void *
0x18004618e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180046193  nop
0x180046194  lea     rcx, [rbp+110h+var_150]; void *
0x180046198  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18004619d  nop
0x18004619e  lea     rcx, [rbp+110h+var_158]; void *
0x1800461a2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800461a7  nop
0x1800461a8  lea     rcx, [rbp+110h+var_160]; void *
0x1800461ac  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800461b1  nop
0x1800461b2  lea     rcx, [rbp+110h+var_168]; void *
0x1800461b6  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800461bb  nop
0x1800461bc  lea     rcx, [rbp+110h+var_180]; void *
0x1800461c0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800461c5  nop
0x1800461c6  xorps   xmm0, xmm0
0x1800461c9  movdqu  xmmword ptr [rbp+110h+var_C8], xmm0
0x1800461ce  mov     [rbp+110h+var_B8], r12
0x1800461d2  xorps   xmm1, xmm1
0x1800461d5  movdqu  [rbp+110h+var_B0], xmm1
0x1800461da  mov     [rbp+110h+var_A0], 0Ah
0x1800461e1  mov     [rbp+110h+var_110], r12
0x1800461e5  mov     r15d, r12d
0x1800461e8  mov     [rbp+110h+var_178], r12d
0x1800461ec  lea     rcx, [rbp+110h+var_130]; void *
0x1800461f0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800461f5  nop
0x1800461f6  lea     r9, [rbp+110h+var_18C]
0x1800461fa  lea     r8, aGenericcallpac_22; "GenericCallPackageHelper::DeviceAuth"
0x180046201  lea     rsi, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x180046208  mov     rdx, rsi
0x18004620b  lea     rcx, [rbp+110h+var_60]
0x180046212  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180046217  nop
0x180046218  mov     rcx, [rbp+110h+arg_30]
0x18004621f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180046224  mov     rcx, [rbp+110h+TokenHandle]; TokenHandle
0x18004622b  call    ?CheckUserIsSystem@SecurityGroupsHelper@@SAJPEAX@Z; SecurityGroupsHelper::CheckUserIsSystem(void *)
0x180046230  mov     [rbp+110h+var_18C], eax
0x180046233  test    eax, eax
0x180046235  jns     short loc_18004627F
0x180046237  lea     r13, base
0x18004623e  mov     [rsp+210h+var_1D0], r13
0x180046243  lea     rcx, aNtstatus; "NTSTATUS"
0x18004624a  mov     qword ptr [rsp+210h+var_1D8], rcx
0x18004624f  mov     dword ptr [rsp+210h+var_1E0], 266h
0x180046257  mov     [rsp+210h+var_1E8], rsi
0x18004625c  mov     r12d, 2
0x180046262  mov     dword ptr [rsp+210h+var_1F0], eax
0x180046266  mov     r9d, r12d
0x180046269  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180046270  xor     edx, edx
0x180046272  mov     ecx, r12d
0x180046275  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004627a  jmp     loc_180046BCC
0x18004627f  mov     rcx, rdi; this
0x180046282  call    ?IsCloudDomainJoined@PluginState@@QEAA_NXZ; PluginState::IsCloudDomainJoined(void)
0x180046287  test    al, al
0x180046289  jnz     short loc_1800462DE
0x18004628b  lea     r13, base
0x180046292  mov     [rsp+210h+var_1D0], r13
0x180046297  lea     rax, aHresult; "HRESULT"
0x18004629e  mov     qword ptr [rsp+210h+var_1D8], rax
0x1800462a3  mov     dword ptr [rsp+210h+var_1E0], 26Ah
0x1800462ab  mov     [rsp+210h+var_1E8], rsi
0x1800462b0  mov     dword ptr [rsp+210h+var_1F0], 80048451h
0x1800462b8  mov     r12d, 2
0x1800462be  mov     r9d, r12d
0x1800462c1  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800462c8  xor     edx, edx
0x1800462ca  mov     ecx, r12d
0x1800462cd  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800462d2  mov     [rbp+110h+var_18C], 0C0048451h
0x1800462d9  jmp     loc_180046BCC
0x1800462de  mov     rax, [rbx]
0x1800462e1  cmp     [rax-10h], r12d
0x1800462e5  jnz     short loc_18004633A
0x1800462e7  lea     r13, base
0x1800462ee  mov     [rsp+210h+var_1D0], r13
0x1800462f3  lea     rax, aHresult; "HRESULT"
0x1800462fa  mov     qword ptr [rsp+210h+var_1D8], rax
0x1800462ff  mov     dword ptr [rsp+210h+var_1E0], 26Fh
0x180046307  mov     [rsp+210h+var_1E8], rsi
0x18004630c  mov     dword ptr [rsp+210h+var_1F0], 80048511h
0x180046314  mov     r12d, 2
0x18004631a  mov     r9d, r12d
0x18004631d  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180046324  xor     edx, edx
0x180046326  mov     ecx, r12d
0x180046329  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004632e  mov     [rbp+110h+var_18C], 0C0048511h
0x180046335  jmp     loc_180046BCC
0x18004633a  lea     r8, [rbp+110h+var_170]
0x18004633e  lea     rdx, [rbp+110h+var_98]
0x180046342  mov     rcx, rbx
0x180046345  call    ?ParseJsonObject@WebResponseHelper@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCJsonValue@@PEAPEAVCJsonObject@@@Z; WebResponseHelper::ParseJsonObject(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CJsonValue *,CJsonObject * *)
0x18004634a  mov     ebx, eax
0x18004634c  test    eax, eax
0x18004634e  jns     short loc_180046380
0x180046350  lea     r13, base
0x180046357  mov     [rsp+210h+var_1D0], r13
0x18004635c  lea     rax, aHresult; "HRESULT"
0x180046363  mov     qword ptr [rsp+210h+var_1D8], rax
0x180046368  mov     dword ptr [rsp+210h+var_1E0], 273h
0x180046370  mov     [rsp+210h+var_1E8], rsi
0x180046375  mov     r12d, 2
0x18004637b  jmp     loc_180046BA9
0x180046380  lea     r8, [rbp+110h+var_138]
0x180046384  lea     rdx, aResource_0; "resource"
0x18004638b  mov     rbx, [rbp+110h+var_170]
0x18004638f  mov     rcx, rbx
0x180046392  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180046397  lea     r8, [rbp+110h+var_140]
0x18004639b  lea     rdx, aClientid; "clientid"
0x1800463a2  mov     rcx, rbx
0x1800463a5  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800463aa  lea     r8, [rbp+110h+var_148]
0x1800463ae  lea     rdx, aScope_0; "scope"
0x1800463b5  mov     rcx, rbx
0x1800463b8  call    ?GetJsonDataAsString@WebResponseHelper@@SAXPEAVCJsonObject@@PEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebResponseHelper::GetJsonDataAsString(CJsonObject *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800463bd  lea     rdx, aExtraparams; "extraparams"
0x1800463c4  mov     rcx, rbx; struct CJsonObject *
0x1800463c7  call    ?GetJsonDataAsObject@WebResponseHelper@@SAPEAVCJsonObject@@PEAV2@PEBG@Z; WebResponseHelper::GetJsonDataAsObject(CJsonObject *,ushort const *)
0x1800463cc  test    rax, rax
0x1800463cf  jz      short loc_18004640A
0x1800463d1  lea     r9, [rbp+110h+var_C8]
0x1800463d5  xor     edx, edx
0x1800463d7  mov     rcx, rax
0x1800463da  call    ?ConvertJsonObjectToKeyValueList@WebResponseHelper@@SAJPEAVCJsonObject@@PEBG_NAEAV?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@@Z; WebResponseHelper::ConvertJsonObjectToKeyValueList(CJsonObject *,ushort const *,bool,ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>> &)
0x1800463df  mov     ebx, eax
0x1800463e1  test    eax, eax
0x1800463e3  jns     short loc_18004640A
0x1800463e5  lea     r13, base
0x1800463ec  mov     [rsp+210h+var_1D0], r13
0x1800463f1  lea     rax, aHresult; "HRESULT"
0x1800463f8  mov     qword ptr [rsp+210h+var_1D8], rax
0x1800463fd  mov     dword ptr [rsp+210h+var_1E0], 27Ch
0x180046405  jmp     loc_180046370
0x18004640a  mov     rsi, [rbp+110h+var_138]
0x18004640e  mov     rdi, [rbp+110h+var_140]
0x180046412  mov     r14, [rbp+110h+var_148]
0x180046416  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 1
0x18004641d  jz      short loc_180046436
0x18004641f  mov     [rsp+210h+var_1F0], r14
0x180046424  mov     r9, rdi
0x180046427  mov     r8, rsi
0x18004642a  lea     rdx, Aad_CloudAPPlugin_GetDeviceToken
0x180046431  call    McTemplateU0zzz_EventWriteTransfer
0x180046436  mov     eax, cs:dword_1800E5050
0x18004643c  cmp     eax, 4
0x18004643f  jbe     short loc_1800464A3
0x180046441  mov     rdx, 400000000000h
0x18004644b  lea     rcx, dword_1800E5050
0x180046452  call    _tlgKeywordOn
0x180046457  test    al, al
0x180046459  jz      short loc_1800464A3
0x18004645b  mov     [rbp+110h+var_170], r14
0x18004645f  mov     [rbp+110h+var_108], rsi
0x180046463  mov     [rbp+110h+var_100], rdi
0x180046467  mov     [rbp+110h+var_118], 800h
0x18004646f  lea     rax, [rbp+110h+var_170]
0x180046473  mov     qword ptr [rsp+210h+var_1D8], rax
0x180046478  lea     rax, [rbp+110h+var_108]
0x18004647c  mov     [rsp+210h+var_1E0], rax
0x180046481  lea     rax, [rbp+110h+var_100]
0x180046485  mov     [rsp+210h+var_1E8], rax
0x18004648a  lea     rax, [rbp+110h+var_118]
0x18004648e  mov     [rsp+210h+var_1F0], rax
0x180046493  mov     r8, [r13+38h]
0x180046497  lea     rdx, word_1800D2FD6
0x18004649e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800464a3  mov     rax, [rbp+110h+arg_28]
0x1800464aa  mov     r9, [rax]
0x1800464ad  cmp     [r9-10h], r12d
0x1800464b1  jz      short loc_180046501
0x1800464b3  lea     r8, aMsAppxWebMicro; "ms-appx-web://Microsoft.AAD.BrokerPlugi"...
0x1800464ba  lea     rdx, aSS_9; "%s/%s"
0x1800464c1  lea     rcx, [rbp+110h+var_150]
0x1800464c5  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x1800464ca  mov     ebx, eax
0x1800464cc  test    eax, eax
0x1800464ce  jns     short loc_180046549
0x1800464d0  lea     r13, base
0x1800464d7  mov     [rsp+210h+var_1D0], r13
0x1800464dc  lea     rax, aHresult; "HRESULT"
0x1800464e3  mov     qword ptr [rsp+210h+var_1D8], rax
0x1800464e8  mov     dword ptr [rsp+210h+var_1E0], 289h
0x1800464f0  lea     rcx, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x1800464f7  mov     [rsp+210h+var_1E8], rcx
0x1800464fc  jmp     loc_180046375
0x180046501  cmp     [rdi-10h], r12d
0x180046505  jz      short loc_180046549
0x180046507  mov     r9, rdi
0x18004650a  lea     r8, aMsAppxWebMicro; "ms-appx-web://Microsoft.AAD.BrokerPlugi"...
0x180046511  lea     rdx, aSS_9; "%s/%s"
0x180046518  lea     rcx, [rbp+110h+var_150]
0x18004651c  call    ?StringFormat@StringUtility@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGZZ; StringUtility::StringFormat(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,...)
0x180046521  mov     ebx, eax
0x180046523  test    eax, eax
0x180046525  jns     short loc_180046549
0x180046527  lea     r13, base
0x18004652e  mov     [rsp+210h+var_1D0], r13
0x180046533  lea     rax, aHresult; "HRESULT"
0x18004653a  mov     qword ptr [rsp+210h+var_1D8], rax
0x18004653f  mov     dword ptr [rsp+210h+var_1E0], 28Dh
0x180046547  jmp     short loc_1800464F0
0x180046549  lea     r13, base
0x180046550  xor     ebx, ebx
0x180046552  lea     r12d, [rbx+2]
0x180046556  cmp     [rbp+110h+var_B8], rbx
0x18004655a  jz      loc_180046A2D
0x180046560  mov     rax, [rbp+110h+var_C8]
0x180046564  mov     [rbp+110h+var_170], rax
0x180046568  test    rax, rax
0x18004656b  jz      loc_180046A2D
0x180046571  mov     sil, bl
0x180046574  mov     dil, bl
0x180046577  mov     r14b, bl
0x18004657a  lea     rdx, [rbp+110h+var_170]
0x18004657e  call    ?GetNext@?$CAtlList@UJsonKeyStringValueItem@@V?$CElementTraits@UJsonKeyStringValueItem@@@ATL@@@ATL@@QEAAAEAUJsonKeyStringValueItem@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<JsonKeyStringValueItem,ATL::CElementTraits<JsonKeyStringValueItem>>::GetNext(__POSITION * &)
0x180046583  mov     rbx, rax
0x180046586  test    r14b, r14b
0x180046589  jnz     short loc_1800465D9
0x18004658b  lea     rdx, aTokenType; "token_type"
0x180046592  mov     rcx, [rax]
0x180046595  call    cs:__imp__o__wcsicmp
0x18004659b  test    eax, eax
0x18004659d  jnz     short loc_1800465D9
0x18004659f  lea     rdx, aPop; "pop"
0x1800465a6  mov     rcx, [rbx+8]
0x1800465aa  call    cs:__imp__o__wcsicmp
0x1800465b0  test    eax, eax
0x1800465b2  jz      short loc_1800465CE
0x1800465b4  lea     rdx, aShr; "shr"
0x1800465bb  mov     rcx, [rbx+8]
0x1800465bf  call    cs:__imp__o__wcsicmp
0x1800465c5  test    eax, eax
0x1800465c7  jz      short loc_1800465CE
0x1800465c9  xor     sil, sil
0x1800465cc  jmp     short loc_1800465D1
0x1800465ce  mov     sil, 1
0x1800465d1  mov     r14b, 1
0x1800465d4  jmp     loc_18004668F
0x1800465d9  test    dil, dil
0x1800465dc  jnz     short loc_1800465FA
0x1800465de  lea     rdx, aReqCnf; "req_cnf"
0x1800465e5  mov     rcx, [rbx]
0x1800465e8  call    cs:__imp__o__wcsicmp
0x1800465ee  test    eax, eax
0x1800465f0  jnz     short loc_1800465FA
0x1800465f2  mov     dil, 1
0x1800465f5  jmp     loc_18004668F
0x1800465fa  mov     rax, [rbp+110h+var_180]
0x1800465fe  cmp     dword ptr [rax-10h], 0
0x180046602  jnz     loc_18004669A
0x180046608  lea     rdx, aEnclave; "enclave"
0x18004660f  mov     rcx, [rbx]
0x180046612  call    cs:__imp__o__wcsicmp
0x180046618  test    eax, eax
0x18004661a  jnz     short loc_18004669A
0x18004661c  lea     rdx, aHw; "hw"
0x180046623  mov     rcx, [rbx+8]
  ... truncated ...
```
