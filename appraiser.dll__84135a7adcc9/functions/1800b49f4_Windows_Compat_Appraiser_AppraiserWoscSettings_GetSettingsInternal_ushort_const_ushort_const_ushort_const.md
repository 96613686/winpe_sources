# Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal(ushort const *,ushort const *,ushort const *)

- ea: `0x1800b49f4`
- end: `0x1800b53c6`
- name: `?GetSettingsInternal@AppraiserWoscSettings@Appraiser@Compat@Windows@@CAJPEBG00@Z`
- size: `2514`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b48f0`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x18001a2f4`
- `0x1800291c8`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18006da84`
- `0x18008b878`
- `0x18008fadc`
- `0x1800b4040`
- `0x1800b4144`
- `0x1800b429c`
- `0x1800b43c8`
- `0x1800b4510`
- `0x1800b49f4`
- `0x1800b53cc`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `OLE32!CoGetClassObject` at `0x1800b4d9d`
- `OLE32!CoGetClassObject` at `0x1800b4d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4ee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4c70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4ee3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4caa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4f20`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4caa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4f20`

## string_xrefs

- `0x1800b4c41`: `COMPATRESTOREAPPRAISER`
- `0x1800b4af7`: `onecore\base\appcompat\appraiser\helpers\appraiserwoscsettings.cpp`
- `0x1800b4b2a`: `onecore\base\appcompat\appraiser\helpers\appraiserwoscsettings.cpp`
- `0x1800b4af0`: `Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal`
- `0x1800b4b23`: `Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal`
- `0x1800b4da9`: `Error initializing WOSC Broker Factory for %ls: [0x%x].`
- `0x1800b4dcf`: `Error initializing WOSC Broker Factory for %ls: [0x%x].`
- `0x1800b4c04`: `Error reading old WOSC ETag value for %ls: [0x%x].`
- `0x1800b4c2a`: `Error reading old WOSC ETag value for %ls: [0x%x].`
- `0x1800b4b83`: `Error reading old WOSC app version value for %ls: [0x%x].`
- `0x1800b4bbf`: `Error reading old WOSC app version value for %ls: [0x%x].`
- `0x1800b4e8e`: `Error refreshing WOSC through WOSC broker for %ls: [0x%x].`
- `0x1800b4eb4`: `Error refreshing WOSC through WOSC broker for %ls: [0x%x].`
- `0x1800b4e34`: `Error getting WOSC broker for %ls: [0x%x].`
- `0x1800b4e5a`: `Error getting WOSC broker for %ls: [0x%x].`
- `0x1800b5210`: `Failed to check if cache was used for WOSC payload: [0x%x].`
- `0x1800b5231`: `Failed to check if cache was used for WOSC payload: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal(
        const wchar_t *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  int v5; // eax
  int ClassObject; // ebx
  char v7; // dl
  const char *v8; // r9
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  __int64 v12; // r12
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, const wchar_t **); // r13
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, _QWORD, const wchar_t **); // r12
  __int64 v22; // rax
  __int64 v23; // rcx
  const char *v24; // r9
  char v25; // dl
  const wchar_t *v26; // rcx
  unsigned __int16 *v27; // rax
  signed __int64 v28; // r13
  int v29; // ecx
  int v30; // edx
  bool v31; // r15
  const wchar_t *v32; // r13
  const wchar_t *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  LPVOID v36; // rcx
  __int64 v37; // rcx
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  LPVOID *ppva; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+28h] [rbp-E0h]
  const char *v42; // [rsp+30h] [rbp-D8h]
  char *v43; // [rsp+38h] [rbp-D0h]
  char *v44; // [rsp+38h] [rbp-D0h]
  int v45; // [rsp+40h] [rbp-C8h]
  bool v46[8]; // [rsp+58h] [rbp-B0h] BYREF
  const wchar_t *v47; // [rsp+60h] [rbp-A8h] BYREF
  const wchar_t *v48; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+70h] [rbp-98h] BYREF
  __int64 v50; // [rsp+78h] [rbp-90h] BYREF
  LPVOID v51; // [rsp+80h] [rbp-88h] BYREF
  __int64 v52; // [rsp+88h] [rbp-80h] BYREF
  const unsigned __int16 *v53; // [rsp+90h] [rbp-78h]
  const wchar_t *v54; // [rsp+98h] [rbp-70h]
  _QWORD v55[3]; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-48h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v58[40]; // [rsp+E0h] [rbp-28h] BYREF
  unsigned __int16 v59[264]; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 v60[264]; // [rsp+318h] [rbp+210h] BYREF
  unsigned __int16 v61[264]; // [rsp+528h] [rbp+420h] BYREF
  unsigned __int16 v62[264]; // [rsp+738h] [rbp+630h] BYREF

  v55[2] = -2;
  v54 = a3;
  v3 = a2;
  v53 = a2;
  v48 = a1;
  v55[0] = a2;
  v52 = 0;
  v51 = 0;
  v50 = 0;
  v49 = 0;
  v47 = 0;
  memset_0(v59, 0, 0x208u);
  memset_0(v60, 0, 0x208u);
  memset_0(v62, 0, 0x208u);
  memset_0(v61, 0, 0x208u);
  v46[0] = 0;
  v46[1] = 0;
  v46[2] = 0;
  v5 = StringCchPrintfW(
         v59,
         0x104u,
         L"%ls\\%ls",
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState",
         a1);
  ClassObject = v5;
  if ( v5 < 0 )
  {
    v45 = v5;
    v44 = (char *)a1;
    v42 = "Error getting WOSC App ID reg key for %ls: [0x%x]";
    v7 = -23;
LABEL_3:
    LODWORD(ppv) = ClassObject;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v7,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      (const char *)ppv,
      (int)v42,
      v44,
      v45);
    goto LABEL_78;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1E9u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      "Error getting WOSC App ID reg key for %ls: [0x%x]",
      a1,
      v5);
  ClassObject = Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
                  v62,
                  0x104u,
                  (unsigned __int16 *)&szValueBuf,
                  v59,
                  L"Version");
  if ( ClassObject < 0 )
  {
    v8 = "Error reading old WOSC app version value for %ls: [0x%x].";
    v7 = -13;
LABEL_8:
    v45 = ClassObject;
    v44 = (char *)a1;
    LODWORD(v42) = (_DWORD)v8;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1F3u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      "Error reading old WOSC app version value for %ls: [0x%x].",
      a1,
      ClassObject);
  ClassObject = Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(
                  v61,
                  0x104u,
                  (unsigned __int16 *)&szValueBuf,
                  v59,
                  L"ETag");
  if ( ClassObject < 0 )
  {
    v8 = "Error reading old WOSC ETag value for %ls: [0x%x].";
    v7 = -3;
    goto LABEL_8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x1FDu,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      "Error reading old WOSC ETag value for %ls: [0x%x].",
      a1,
      ClassObject);
  if ( !wcscmp_0(a1, L"COMPATRESTOREAPPRAISER") )
  {
    ClassObject = CoGetClassObject(&CLSID_OneSettingsBroker, 4u, 0, &GUID_00000001_0000_0000_c000_000000000046, &v51);
    if ( ClassObject < 0 )
    {
      v8 = "Error initializing WOSC Broker Factory for %ls: [0x%x].";
      v7 = 18;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x212u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Error initializing WOSC Broker Factory for %ls: [0x%x].",
        a1,
        ClassObject);
    ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)v51 + 24LL))(
                    v51,
                    0,
                    &GUID_6b8773dc_2e64_467a_9771_2e07caeae514,
                    &v50);
    if ( ClassObject < 0 )
    {
      v8 = "Error getting WOSC broker for %ls: [0x%x].";
      v7 = 21;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x215u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Error getting WOSC broker for %ls: [0x%x].",
        a1,
        ClassObject);
    ClassObject = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v50 + 32LL))(
                    v50,
                    a1,
                    v3);
    if ( ClassObject < 0 )
    {
      v8 = "Error refreshing WOSC through WOSC broker for %ls: [0x%x].";
      v7 = 24;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x218u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Error refreshing WOSC through WOSC broker for %ls: [0x%x].",
        a1,
        ClassObject);
    string = 0;
    v17 = WindowsCreateStringReference(
            L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
            0x39u,
            &hstringHeader,
            &string);
    if ( v17 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
      __debugbreak();
    }
    ClassObject = RoGetActivationFactory(string, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v49);
    if ( ClassObject < 0 )
    {
      v8 = "Error getting WOSC payload statics for %ls: [0x%x].";
      v7 = 27;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x21Bu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Error getting WOSC payload statics for %ls: [0x%x].",
        a1,
        ClassObject);
    v20 = v49;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t **))(*(_QWORD *)v49 + 48LL);
    v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v58, &v48);
    ClassObject = v21(v20, *(_QWORD *)(v22 + 24), &v47);
  }
  else
  {
    string = 0;
    v9 = WindowsCreateStringReference(
           L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
           0x39u,
           &hstringHeader,
           &string);
    if ( v9 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
      JUMPOUT(0x1800B53C5LL);
    }
    ClassObject = RoGetActivationFactory(string, &GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017, &v52);
    if ( ClassObject < 0 )
    {
      v8 = "Error getting WOSC manager for %ls: [0x%x].";
      v7 = 5;
      goto LABEL_8;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x205u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Error getting WOSC manager for %ls: [0x%x].",
        a1,
        ClassObject);
    v12 = v52;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, const wchar_t **))(*(_QWORD *)v52 + 56LL);
    v14 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v55) + 24);
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v58, &v48);
    ClassObject = v13(v12, *(_QWORD *)(v15 + 24), v14, &v47);
    v3 = v53;
  }
  if ( ClassObject < 0 )
  {
    v32 = v54;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      551,
      "Failed to refresh WOSC App ID %ls for OneSettings data: [0x%x] :: (%ls)",
      a1,
      ClassObject,
      v54);
    LODWORD(ppvb) = ClassObject;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      43,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      (const char *)ppvb,
      (int)"Failed to refresh WOSC App ID %ls for OneSettings data: [0x%x] :: (%ls)",
      (const char *)a1,
      ClassObject,
      v32);
  }
  else
  {
    Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v60, v16);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
      546,
      "%ls - Querying WOSC OneSettings for Appraiser succeeded.",
      v60);
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x22Bu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to refresh WOSC App ID %ls for OneSettings data: [0x%x] :: (%ls)",
        a1,
        ClassObject,
        v54);
    if ( !v47 )
    {
      ClassObject = -2147024882;
      goto LABEL_78;
    }
    v48 = v47;
    (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
    ClassObject = Windows::Compat::Appraiser::ParseWoscPayload(v23, &v48);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to parse WOSC payload: [0x%x].";
      v25 = 47;
LABEL_47:
      LODWORD(v43) = ClassObject;
      LODWORD(ppva) = ClassObject;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v25,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        (const char *)ppva,
        (int)v24,
        v43);
      goto LABEL_78;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x22Fu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to parse WOSC payload: [0x%x].",
        ClassObject);
    v26 = v47;
    v48 = v47;
    if ( v47 )
      (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
    ClassObject = Windows::Compat::Appraiser::DetermineSettingsFreshnessTimestamp(v26, &v48);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to determine WOSC settings freshness timestamp: [0x%x].";
      v25 = 50;
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x232u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to determine WOSC settings freshness timestamp: [0x%x].",
        ClassObject);
    v48 = v47;
    if ( v47 )
      (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
    ClassObject = Windows::Compat::Appraiser::CheckETagChanged(&v46[2], v61, &v48);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to check if WOSC ETag changed: [0x%x].";
      v25 = 53;
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x235u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to check if WOSC ETag changed: [0x%x].",
        ClassObject);
    v27 = v62;
    v28 = (char *)v3 - (char *)v62;
    do
    {
      v29 = *(unsigned __int16 *)((char *)v27 + v28);
      v30 = *v27 - v29;
      if ( v30 )
        break;
      ++v27;
    }
    while ( v29 );
    v31 = v30 != 0;
    ClassObject = Windows::Compat::Appraiser::AppraiserWoscSettings::CheckRefreshTimeExpiry(&v46[1], v59);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to check if WOSC data is expired: [0x%x].";
      v25 = 58;
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x23Au,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to check if WOSC data is expired: [0x%x].",
        ClassObject);
    ClassObject = Windows::Compat::Appraiser::AppraiserWoscSettings::CheckCacheUsed(v46, v59);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to check if cache was used for WOSC payload: [0x%x].";
      v25 = 61;
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x23Du,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to check if cache was used for WOSC payload: [0x%x].",
        ClassObject);
    ClassObject = Windows::Compat::Appraiser::AppraiserWoscSettings::DetermineSettingsFresh(
                    v59,
                    v46[2],
                    v31,
                    v46[1],
                    v46[0]);
    if ( ClassObject < 0 )
    {
      v24 = "Failed to check if settings are fresh: [0x%x].";
      v25 = 64;
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x240u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\appraiserwoscsettings.cpp",
        "Windows::Compat::Appraiser::AppraiserWoscSettings::GetSettingsInternal",
        "Failed to check if settings are fresh: [0x%x].",
        ClassObject);
  }
LABEL_78:
  v33 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1800b49f4  mov     rax, rsp
0x1800b49f7  push    rbp
0x1800b49f8  push    rsi
0x1800b49f9  push    rdi
0x1800b49fa  push    r12
0x1800b49fc  push    r13
0x1800b49fe  push    r14
0x1800b4a00  push    r15
0x1800b4a02  lea     rbp, [rax-888h]
0x1800b4a09  sub     rsp, 950h
0x1800b4a10  mov     [rbp+880h+var_8D0], 0FFFFFFFFFFFFFFFEh
0x1800b4a18  mov     [rax+20h], rbx
0x1800b4a1c  mov     rax, cs:__security_cookie
0x1800b4a23  xor     rax, rsp
0x1800b4a26  mov     [rbp+880h+var_40], rax
0x1800b4a2d  mov     [rbp+880h+var_8F0], r8
0x1800b4a31  mov     r13, rdx
0x1800b4a34  mov     [rbp+880h+var_8F8], rdx
0x1800b4a38  mov     r15, rcx
0x1800b4a3b  mov     [rsp+980h+var_920], rcx
0x1800b4a40  mov     [rbp+880h+var_8E0], rdx
0x1800b4a44  xor     r12d, r12d
0x1800b4a47  mov     [rbp+880h+var_900], r12
0x1800b4a4b  mov     [rsp+980h+var_908], r12
0x1800b4a50  mov     [rsp+980h+var_910], r12
0x1800b4a55  mov     [rsp+980h+var_918], r12
0x1800b4a5a  mov     [rsp+980h+var_928], r12
0x1800b4a5f  mov     ebx, 208h
0x1800b4a64  mov     r8d, ebx; Size
0x1800b4a67  xor     edx, edx; Val
0x1800b4a69  lea     rcx, [rbp+880h+var_880]; void *
0x1800b4a6d  call    memset_0
0x1800b4a72  mov     r8d, ebx; Size
0x1800b4a75  xor     edx, edx; Val
0x1800b4a77  lea     rcx, [rbp+880h+var_670]; void *
0x1800b4a7e  call    memset_0
0x1800b4a83  mov     r8d, ebx; Size
0x1800b4a86  xor     edx, edx; Val
0x1800b4a88  lea     rcx, [rbp+880h+var_250]; void *
0x1800b4a8f  call    memset_0
0x1800b4a94  mov     r8d, ebx; Size
0x1800b4a97  xor     edx, edx; Val
0x1800b4a99  lea     rcx, [rbp+880h+var_460]; void *
0x1800b4aa0  call    memset_0
0x1800b4aa5  mov     [rsp+980h+var_930], r12b
0x1800b4aaa  mov     [rsp+980h+var_930+1], r12b
0x1800b4aaf  mov     [rsp+980h+var_930+2], r12b
0x1800b4ab4  mov     [rsp+980h+ppv], r15
0x1800b4ab9  lea     r9, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800b4ac0  lea     r8, aLsLs_0; "%ls\\%ls"
0x1800b4ac7  mov     edx, 104h; unsigned __int64
0x1800b4acc  lea     rcx, [rbp+880h+var_880]; unsigned __int16 *
0x1800b4ad0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b4ad5  mov     ebx, eax
0x1800b4ad7  test    eax, eax
0x1800b4ad9  jns     short loc_1800B4B16
0x1800b4adb  mov     [rsp+980h+var_948], eax
0x1800b4adf  mov     [rsp+980h+var_950], r15; char *
0x1800b4ae4  lea     r9, aErrorGettingWo; "Error getting WOSC App ID reg key for %"...
0x1800b4aeb  mov     qword ptr [rsp+980h+var_958], r9; int
0x1800b4af0  lea     r9, aWindowsCompatA_663; "Windows::Compat::Appraiser::AppraiserWo"...
0x1800b4af7  lea     r8, aOnecoreBaseApp_95; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b4afe  mov     edx, 1E9h; bool
0x1800b4b03  lea     ecx, [r12+1]; this
0x1800b4b08  mov     dword ptr [rsp+980h+ppv], ebx; char *
0x1800b4b0c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800b4b11  jmp     loc_1800B5300
0x1800b4b16  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4b1c  mov     edi, 1
0x1800b4b21  and     eax, edi
0x1800b4b23  lea     rsi, aWindowsCompatA_663; "Windows::Compat::Appraiser::AppraiserWo"...
0x1800b4b2a  lea     r14, aOnecoreBaseApp_95; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800b4b31  test    al, al
0x1800b4b33  jz      short loc_1800B4B55
0x1800b4b35  mov     [rsp+980h+var_958], ebx
0x1800b4b39  mov     [rsp+980h+ppv], r15
0x1800b4b3e  lea     r9, aErrorGettingWo; "Error getting WOSC App ID reg key for %"...
0x1800b4b45  mov     r8, rsi; char *
0x1800b4b48  mov     rdx, r14; char *
0x1800b4b4b  mov     ecx, 1E9h; unsigned int
0x1800b4b50  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4b55  lea     rax, aVersion; "Version"
0x1800b4b5c  mov     [rsp+980h+ppv], rax; unsigned __int16 *
0x1800b4b61  lea     r9, [rbp+880h+var_880]; unsigned __int16 *
0x1800b4b65  lea     r8, szValueBuf; unsigned __int16 *
0x1800b4b6c  mov     edx, 104h; unsigned __int64
0x1800b4b71  lea     rcx, [rbp+880h+var_250]; unsigned __int16 *
0x1800b4b78  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x1800b4b7d  mov     ebx, eax
0x1800b4b7f  test    eax, eax
0x1800b4b81  jns     short loc_1800B4BAA
0x1800b4b83  lea     r9, aErrorReadingOl_1; "Error reading old WOSC app version valu"...
0x1800b4b8a  mov     edx, 1F3h
0x1800b4b8f  mov     [rsp+980h+var_948], ebx
0x1800b4b93  mov     [rsp+980h+var_950], r15
0x1800b4b98  mov     qword ptr [rsp+980h+var_958], r9
0x1800b4b9d  mov     r9, rsi
0x1800b4ba0  mov     r8, r14
0x1800b4ba3  mov     ecx, edi
0x1800b4ba5  jmp     loc_1800B4B08
0x1800b4baa  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4bb0  and     eax, edi
0x1800b4bb2  test    al, al
0x1800b4bb4  jz      short loc_1800B4BD6
0x1800b4bb6  mov     [rsp+980h+var_958], ebx
0x1800b4bba  mov     [rsp+980h+ppv], r15
0x1800b4bbf  lea     r9, aErrorReadingOl_1; "Error reading old WOSC app version valu"...
0x1800b4bc6  mov     r8, rsi; char *
0x1800b4bc9  mov     rdx, r14; char *
0x1800b4bcc  mov     ecx, 1F3h; unsigned int
0x1800b4bd1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4bd6  lea     rax, aEtag; "ETag"
0x1800b4bdd  mov     [rsp+980h+ppv], rax; unsigned __int16 *
0x1800b4be2  lea     r9, [rbp+880h+var_880]; unsigned __int16 *
0x1800b4be6  lea     r8, szValueBuf; unsigned __int16 *
0x1800b4bed  mov     edx, 104h; unsigned __int64
0x1800b4bf2  lea     rcx, [rbp+880h+var_460]; unsigned __int16 *
0x1800b4bf9  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x1800b4bfe  mov     ebx, eax
0x1800b4c00  test    eax, eax
0x1800b4c02  jns     short loc_1800B4C15
0x1800b4c04  lea     r9, aErrorReadingOl; "Error reading old WOSC ETag value for %"...
0x1800b4c0b  mov     edx, 1FDh
0x1800b4c10  jmp     loc_1800B4B8F
0x1800b4c15  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4c1b  and     eax, edi
0x1800b4c1d  test    al, al
0x1800b4c1f  jz      short loc_1800B4C41
0x1800b4c21  mov     [rsp+980h+var_958], ebx
0x1800b4c25  mov     [rsp+980h+ppv], r15
0x1800b4c2a  lea     r9, aErrorReadingOl; "Error reading old WOSC ETag value for %"...
0x1800b4c31  mov     r8, rsi; char *
0x1800b4c34  mov     rdx, r14; char *
0x1800b4c37  mov     ecx, 1FDh; unsigned int
0x1800b4c3c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4c41  lea     rdx, aCompatrestorea; "COMPATRESTOREAPPRAISER"
0x1800b4c48  mov     rcx, r15; String1
0x1800b4c4b  call    wcscmp_0
0x1800b4c50  test    eax, eax
0x1800b4c52  jz      loc_1800B4D62
0x1800b4c58  mov     [rbp+880h+string], r12
0x1800b4c5c  lea     r9, [rbp+880h+string]; string
0x1800b4c60  lea     r8, [rbp+880h+hstringHeader]; hstringHeader
0x1800b4c64  mov     edx, 39h ; '9'; length
0x1800b4c69  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800b4c70  call    cs:__imp_WindowsCreateStringReference
0x1800b4c76  test    eax, eax
0x1800b4c78  js      loc_1800B53BE
0x1800b4c7e  mov     rbx, [rbp+880h+string]
0x1800b4c82  mov     rcx, [rbp+880h+var_900]
0x1800b4c86  test    rcx, rcx
0x1800b4c89  jz      short loc_1800B4C9C
0x1800b4c8b  mov     [rbp+880h+var_900], r12
0x1800b4c8f  mov     rax, [rcx]
0x1800b4c92  mov     rax, [rax+10h]
0x1800b4c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c9b  nop
0x1800b4c9c  lea     r8, [rbp+880h+var_900]
0x1800b4ca0  lea     rdx, _GUID_6ebfc469_e65b_45eb_9863_b3f57e2a5017
0x1800b4ca7  mov     rcx, rbx
0x1800b4caa  call    cs:__imp_RoGetActivationFactory
0x1800b4cb0  mov     ebx, eax
0x1800b4cb2  test    eax, eax
0x1800b4cb4  jns     short loc_1800B4CC7
0x1800b4cb6  lea     r9, aErrorGettingWo_0; "Error getting WOSC manager for %ls: [0x"...
0x1800b4cbd  mov     edx, 205h
0x1800b4cc2  jmp     loc_1800B4B8F
0x1800b4cc7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4ccd  and     eax, edi
0x1800b4ccf  test    al, al
0x1800b4cd1  jz      short loc_1800B4CF3
0x1800b4cd3  mov     [rsp+980h+var_958], ebx
0x1800b4cd7  mov     [rsp+980h+ppv], r15
0x1800b4cdc  lea     r9, aErrorGettingWo_0; "Error getting WOSC manager for %ls: [0x"...
0x1800b4ce3  mov     r8, rsi; char *
0x1800b4ce6  mov     rdx, r14; char *
0x1800b4ce9  mov     ecx, 205h; unsigned int
0x1800b4cee  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4cf3  mov     r12, [rbp+880h+var_900]
0x1800b4cf7  mov     rax, [r12]
0x1800b4cfb  mov     r13, [rax+38h]
0x1800b4cff  mov     rcx, [rsp+980h+var_928]
0x1800b4d04  test    rcx, rcx
0x1800b4d07  jz      short loc_1800B4D1F
0x1800b4d09  mov     [rsp+980h+var_928], 0
0x1800b4d12  mov     rax, [rcx]
0x1800b4d15  mov     rax, [rax+10h]
0x1800b4d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d1e  nop
0x1800b4d1f  lea     rdx, [rbp+880h+var_8E0]
0x1800b4d23  lea     rcx, [rbp+880h+hstringHeader]
0x1800b4d27  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b4d2c  nop
0x1800b4d2d  mov     rbx, [rax+18h]
0x1800b4d31  lea     rdx, [rsp+980h+var_920]
0x1800b4d36  lea     rcx, [rbp+880h+var_8A8]
0x1800b4d3a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b4d3f  nop
0x1800b4d40  lea     r9, [rsp+980h+var_928]
0x1800b4d45  mov     r8, rbx
0x1800b4d48  mov     rdx, [rax+18h]
0x1800b4d4c  mov     rcx, r12
0x1800b4d4f  mov     rax, r13
0x1800b4d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d57  mov     ebx, eax
0x1800b4d59  mov     r13, [rbp+880h+var_8F8]
0x1800b4d5d  jmp     loc_1800B4FBA
0x1800b4d62  mov     rcx, [rsp+980h+var_908]
0x1800b4d67  test    rcx, rcx
0x1800b4d6a  jz      short loc_1800B4D7E
0x1800b4d6c  mov     [rsp+980h+var_908], r12
0x1800b4d71  mov     rax, [rcx]
0x1800b4d74  mov     rax, [rax+10h]
0x1800b4d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d7d  nop
0x1800b4d7e  lea     rax, [rsp+980h+var_908]
0x1800b4d83  mov     [rsp+980h+ppv], rax; ppv
0x1800b4d88  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1800b4d8f  xor     r8d, r8d; pvReserved
0x1800b4d92  lea     edx, [r8+4]; dwClsContext
0x1800b4d96  lea     rcx, CLSID_OneSettingsBroker; rclsid
0x1800b4d9d  call    cs:__imp_CoGetClassObject
0x1800b4da3  mov     ebx, eax
0x1800b4da5  test    eax, eax
0x1800b4da7  jns     short loc_1800B4DBA
0x1800b4da9  lea     r9, aErrorInitializ_22; "Error initializing WOSC Broker Factory "...
0x1800b4db0  mov     edx, 212h
0x1800b4db5  jmp     loc_1800B4B8F
0x1800b4dba  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4dc0  and     eax, edi
0x1800b4dc2  test    al, al
0x1800b4dc4  jz      short loc_1800B4DE6
0x1800b4dc6  mov     [rsp+980h+var_958], ebx
0x1800b4dca  mov     [rsp+980h+ppv], r15
0x1800b4dcf  lea     r9, aErrorInitializ_22; "Error initializing WOSC Broker Factory "...
0x1800b4dd6  mov     r8, rsi; char *
0x1800b4dd9  mov     rdx, r14; char *
0x1800b4ddc  mov     ecx, 212h; unsigned int
0x1800b4de1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4de6  mov     rbx, [rsp+980h+var_908]
0x1800b4deb  mov     rax, [rbx]
0x1800b4dee  mov     r12, [rax+18h]
0x1800b4df2  mov     rcx, [rsp+980h+var_910]
0x1800b4df7  test    rcx, rcx
0x1800b4dfa  jz      short loc_1800B4E12
0x1800b4dfc  mov     [rsp+980h+var_910], 0
0x1800b4e05  mov     rdx, [rcx]
0x1800b4e08  mov     rax, [rdx+10h]
0x1800b4e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e11  nop
0x1800b4e12  lea     r9, [rsp+980h+var_910]
0x1800b4e17  lea     r8, _GUID_6b8773dc_2e64_467a_9771_2e07caeae514
0x1800b4e1e  xor     edx, edx
0x1800b4e20  mov     rcx, rbx
0x1800b4e23  mov     rax, r12
0x1800b4e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e2b  mov     ebx, eax
0x1800b4e2d  xor     r12d, r12d
0x1800b4e30  test    eax, eax
0x1800b4e32  jns     short loc_1800B4E45
0x1800b4e34  lea     r9, aErrorGettingWo_2; "Error getting WOSC broker for %ls: [0x%"...
0x1800b4e3b  mov     edx, 215h
0x1800b4e40  jmp     loc_1800B4B8F
0x1800b4e45  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4e4b  and     eax, edi
0x1800b4e4d  test    al, al
0x1800b4e4f  jz      short loc_1800B4E71
0x1800b4e51  mov     [rsp+980h+var_958], ebx
0x1800b4e55  mov     [rsp+980h+ppv], r15
0x1800b4e5a  lea     r9, aErrorGettingWo_2; "Error getting WOSC broker for %ls: [0x%"...
0x1800b4e61  mov     r8, rsi; char *
0x1800b4e64  mov     rdx, r14; char *
0x1800b4e67  mov     ecx, 215h; unsigned int
0x1800b4e6c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4e71  mov     rcx, [rsp+980h+var_910]
0x1800b4e76  mov     rax, [rcx]
0x1800b4e79  mov     r8, r13
0x1800b4e7c  mov     rdx, r15
0x1800b4e7f  mov     rax, [rax+20h]
0x1800b4e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e88  mov     ebx, eax
0x1800b4e8a  test    eax, eax
0x1800b4e8c  jns     short loc_1800B4E9F
0x1800b4e8e  lea     r9, aErrorRefreshin; "Error refreshing WOSC through WOSC brok"...
0x1800b4e95  mov     edx, 218h
0x1800b4e9a  jmp     loc_1800B4B8F
0x1800b4e9f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800b4ea5  and     eax, edi
0x1800b4ea7  test    al, al
0x1800b4ea9  jz      short loc_1800B4ECB
0x1800b4eab  mov     [rsp+980h+var_958], ebx
0x1800b4eaf  mov     [rsp+980h+ppv], r15
0x1800b4eb4  lea     r9, aErrorRefreshin; "Error refreshing WOSC through WOSC brok"...
0x1800b4ebb  mov     r8, rsi; char *
0x1800b4ebe  mov     rdx, r14; char *
0x1800b4ec1  mov     ecx, 218h; unsigned int
0x1800b4ec6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800b4ecb  mov     [rbp+880h+string], r12
0x1800b4ecf  lea     r9, [rbp+880h+string]; string
0x1800b4ed3  lea     r8, [rbp+880h+hstringHeader]; hstringHeader
  ... truncated ...
```
