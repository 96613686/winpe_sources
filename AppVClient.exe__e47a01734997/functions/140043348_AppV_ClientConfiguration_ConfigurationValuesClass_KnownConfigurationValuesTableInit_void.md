# AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationValuesTableInit(void)

- ea: `0x140043348`
- end: `0x140044d76`
- name: `?KnownConfigurationValuesTableInit@ConfigurationValuesClass@ClientConfiguration@AppV@@AEAAXXZ`
- size: `6702`
- prototype: `void __fastcall(AppV::ClientConfiguration::ConfigurationValuesClass *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140042d28`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x1400067f0`
- `0x140014440`
- `0x1400165b4`
- `0x14003c9d8`
- `0x14003ce4c`
- `0x140042094`
- `0x140042330`
- `0x140043348`
- `0x1400455e8`
- `0x1400457d0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@I@Z` at `0x140044514`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@I@Z` at `0x140044514`

## string_xrefs

- `0x1400433f8`: `Client\Streaming\PackageInstallationRoot`
- `0x14004348b`: `Client\Streaming\PackageInstallationRoot`
- `0x1400438f4`: `Client\Streaming\SupportBranchCache`
- `0x140043bb0`: `Client\Integration\RoamingRegistryExclusions`
- `0x140043e71`: `Client\Integration\VirtualizableExtensions`
- `0x140044248`: `Client\Reporting\ReportingDataCacheLimit`
- `0x140044bcf`: `Client\Virtualization\ProcessesUsingVirtualComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AppV::ClientConfiguration::ConfigurationValuesClass::KnownConfigurationValuesTableInit(
        AppV::ClientConfiguration::ConfigurationValuesClass *this)
{
  __int64 *v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdi
  __int64 v8; // rdi
  __int64 v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 v14; // rdi
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rdi
  __int64 v19; // rdi
  __int64 v20; // rdi
  __int64 v21; // rdi
  __int64 v22; // rdi
  __int64 v23; // rdi
  __int64 v24; // rdi
  __int64 v25; // rdi
  __int64 v26; // rdi
  __int64 v27; // rdi
  __int64 v28; // rdi
  __int64 v29; // rdi
  __int64 v30; // rdi
  __int64 v31; // rdi
  __int64 v32; // rdi
  __int64 v33; // rdi
  unsigned int i; // edi
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v48[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v49[232]; // [rsp+38h] [rbp-C8h] BYREF
  char *v50[4]; // [rsp+120h] [rbp+20h] BYREF
  int v51; // [rsp+140h] [rbp+40h]
  __int16 v52; // [rsp+144h] [rbp+44h]
  __int128 v53; // [rsp+148h] [rbp+48h] BYREF
  __int128 v54; // [rsp+158h] [rbp+58h]
  char *v55[4]; // [rsp+168h] [rbp+68h] BYREF
  int v56; // [rsp+188h] [rbp+88h]
  __int16 v57; // [rsp+18Ch] [rbp+8Ch]
  char *v58[4]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v59[2]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset(v59, 0, sizeof(v59));
  std::wstring::_Construct<1,wchar_t const *>((char **)v59, L"\\*\\", 3u);
  v2 = (__int64 *)((char *)this + 24);
  v47 = 85;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((v2[2] - *v2) >> 3) < 0x55 )
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Reallocate<0>(v2, &v47);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\PackageInstallationRoot", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v3 = v2[1];
  if ( v3 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v3 + 32) = v51;
    *(_WORD *)(v3 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\PackageInstallationRoot", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v4 = v2[1];
  if ( v4 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v4 + 32) = v51;
    *(_WORD *)(v4 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\PackageSourceRoot", 0x22u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v5 = v2[1];
  if ( v5 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v5 + 32) = v51;
    *(_WORD *)(v5 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\LocationProvider", 0x21u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v6 = v2[1];
  if ( v6 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v6 + 32) = v51;
    *(_WORD *)(v6 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\AutoLoad", 0x19u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v7 = v2[1];
  if ( v7 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v7 + 32) = v51;
    *(_WORD *)(v7 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Scripting\\EnablePackageScripts", 0x25u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v8 = v2[1];
  if ( v8 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v8 + 32) = v51;
    *(_WORD *)(v8 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\ReestablishmentInterval", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v9 = v2[1];
  if ( v9 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v9 + 32) = v51;
    *(_WORD *)(v9 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\ReestablishmentRetries", 0x27u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v10 = v2[1];
  if ( v10 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v10 + 32) = v51;
    *(_WORD *)(v10 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\CertFilterForClientSsl", 0x27u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v11 = v2[1];
  if ( v11 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v11 + 32) = v51;
    *(_WORD *)(v11 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\SupportBranchCache", 0x23u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v12 = v2[1];
  if ( v12 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v12 + 32) = v51;
    *(_WORD *)(v12 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v53,
    L"Client\\Streaming\\VerifyCertificateRevocationList",
    0x30u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v13 = v2[1];
  if ( v13 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v13 + 32) = v51;
    *(_WORD *)(v13 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\SharedContentStoreMode", 0x27u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v14 = v2[1];
  if ( v14 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v14 + 32) = v51;
    *(_WORD *)(v14 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Coexistence\\MigrationMode", 0x20u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v15 = v2[1];
  if ( v15 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v15 + 32) = v51;
    *(_WORD *)(v15 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Integration\\RoamingFileExclusions", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v16 = v2[1];
  if ( v16 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v16 + 32) = v51;
    *(_WORD *)(v16 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Integration\\RoamingRegistryExclusions", 0x2Cu);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v17 = v2[1];
  if ( v17 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v17 + 32) = v51;
    *(_WORD *)(v17 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\AllowHighCostLaunch", 0x24u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v18 = v2[1];
  if ( v18 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v18 + 32) = v51;
    *(_WORD *)(v18 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\RequirePublishAsAdmin", 0x26u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v19 = v2[1];
  if ( v19 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v19 + 32) = v51;
    *(_WORD *)(v19 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Integration\\IntegrationRootUser", 0x26u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v20 = v2[1];
  if ( v20 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v20 + 32) = v51;
    *(_WORD *)(v20 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Integration\\IntegrationRootGlobal", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v21 = v2[1];
  if ( v21 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v21 + 32) = v51;
    *(_WORD *)(v21 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Integration\\VirtualizableExtensions", 0x2Au);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v22 = v2[1];
  if ( v22 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v22 + 32) = v51;
    *(_WORD *)(v22 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Streaming\\IgnoreLocationProvider", 0x27u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v23 = v2[1];
  if ( v23 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v23 + 32) = v51;
    *(_WORD *)(v23 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingEnabled", 0x21u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v24 = v2[1];
  if ( v24 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v24 + 32) = v51;
    *(_WORD *)(v24 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingStartTime", 0x23u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v25 = v2[1];
  if ( v25 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v25 + 32) = v51;
    *(_WORD *)(v25 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingRandomDelay", 0x25u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v26 = v2[1];
  if ( v26 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v26 + 32) = v51;
    *(_WORD *)(v26 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingInterval", 0x22u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v27 = v2[1];
  if ( v27 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v27 + 32) = v51;
    *(_WORD *)(v27 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingServerURL", 0x23u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 2;
  v52 = 256;
  v28 = v2[1];
  if ( v28 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v28 + 32) = v51;
    *(_WORD *)(v28 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingDataCacheLimit", 0x28u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v29 = v2[1];
  if ( v29 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v29 + 32) = v51;
    *(_WORD *)(v29 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Reporting\\ReportingDataBlockSize", 0x27u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v30 = v2[1];
  if ( v30 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v30 + 32) = v51;
    *(_WORD *)(v30 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"CEIP\\CEIPEnable", 0xFu);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v31 = v2[1];
  if ( v31 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v31 + 32) = v51;
    *(_WORD *)(v31 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Publishing\\EnablePublishingRefreshUI", 0x2Bu);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v32 = v2[1];
  if ( v32 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v32 + 32) = v51;
    *(_WORD *)(v32 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v53,
    L"Client\\Publishing\\MaxConcurrentPublishingRefresh",
    0x30u);
  std::wstring::wstring((__int64)v50, (__int64)&v53);
  v51 = 1;
  v52 = 256;
  v33 = v2[1];
  if ( v33 == v2[2] )
  {
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(
      v2,
      v2[1],
      (__int64)v50);
  }
  else
  {
    std::wstring::wstring(v2[1], (__int64)v50);
    *(_DWORD *)(v33 + 32) = v51;
    *(_WORD *)(v33 + 36) = v52;
    v2[1] += 40;
  }
  std::wstring::~wstring(v50);
  std::wstring::~wstring((char **)&v53);
  for ( i = 1; i <= 5; ++i )
  {
    std::wostringstream::wostringstream(v48);
    v35 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v48, L"\\");
    v36 = std::wostream::operator<<(v35, i);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v36, L"\\");
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Publishing\\Servers\\*\\Name", 0x20u);
    v37 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v37);
    v56 = 2;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Publishing\\Servers\\*\\URL", 0x1Fu);
    v38 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v38);
    v56 = 2;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Publishing\\Servers\\*\\GlobalEnabled", 0x29u);
    v39 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v39);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\GlobalLogonRefresh",
      0x2Eu);
    v40 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v40);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\GlobalPeriodicRefreshInterval",
      0x39u);
    v41 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v41);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\GlobalPeriodicRefreshIntervalUnit",
      0x3Du);
    v42 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v42);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\Publishing\\Servers\\*\\UserEnabled", 0x27u);
    v43 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v43);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\UserLogonRefresh",
      0x2Cu);
    v44 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v44);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\UserPeriodicRefreshInterval",
      0x37u);
    v45 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v45);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wstringbuf::str(v49, v58);
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v53,
      L"Client\\Publishing\\Servers\\*\\UserPeriodicRefreshIntervalUnit",
      0x3Bu);
    v46 = appv::string::replace_all_copy(v50, &v53, v59, v58, v47);
    std::wstring::wstring((__int64)v55, v46);
    v56 = 1;
    v57 = 256;
    std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
    std::wstring::~wstring(v55);
    std::wstring::~wstring(v50);
    std::wstring::~wstring((char **)&v53);
    std::wstring::~wstring(v58);
    std::wostringstream::`vbase destructor'(v48);
  }
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v53,
    L"Client\\Virtualization\\ProcessesUsingVirtualComponents",
    0x35u);
  std::wstring::wstring((__int64)v55, (__int64)&v53);
  v56 = 3;
  v57 = 256;
  std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
  std::wstring::~wstring(v55);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v53,
    L"Client\\Virtualization\\EnableDynamicVirtualization",
    0x31u);
  std::wstring::wstring((__int64)v55, (__int64)&v53);
  v56 = 1;
  v57 = 256;
  std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
  std::wstring::~wstring(v55);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\PackageManagement\\AutoCleanupEnabled", 0x2Bu);
  std::wstring::wstring((__int64)v55, (__int64)&v53);
  v56 = 1;
  v57 = 256;
  std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
  std::wstring::~wstring(v55);
  std::wstring::~wstring((char **)&v53);
  v53 = 0;
  v54 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client\\PowerManagement\\SyncOnBatteriesEnabled", 0x2Du);
  std::wstring::wstring((__int64)v55, (__int64)&v53);
  v56 = 1;
  v57 = 256;
  std::vector<AppV::ClientConfiguration::ConfigurationValue>::push_back(v2, v55);
  std::wstring::~wstring(v55);
  std::wstring::~wstring((char **)&v53);
  std::wstring::~wstring((char **)v59);
}

```

## disassembly

```asm
0x140043348  push    rbp
0x14004334a  push    rbx
0x14004334b  push    rsi
0x14004334c  push    rdi
0x14004334d  push    r12
0x14004334f  push    r13
0x140043351  push    r14
0x140043353  push    r15
0x140043355  lea     rbp, [rsp-0E8h]
0x14004335d  sub     rsp, 1E8h
0x140043364  mov     rax, cs:__security_cookie
0x14004336b  xor     rax, rsp
0x14004336e  mov     [rbp+120h+var_50], rax
0x140043375  mov     rbx, rcx
0x140043378  xorps   xmm0, xmm0
0x14004337b  movups  [rbp+120h+var_70], xmm0
0x140043382  xorps   xmm1, xmm1
0x140043385  movdqu  [rbp+120h+var_60], xmm1
0x14004338d  mov     r8d, 3
0x140043393  lea     rdx, asc_14008B3A8; "\\*\\"
0x14004339a  lea     rcx, [rbp+120h+var_70]
0x1400433a1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400433a6  nop
0x1400433a7  add     rbx, 18h
0x1400433ab  mov     [rsp+220h+var_200], 55h ; 'U'
0x1400433b4  mov     rax, [rbx+10h]
0x1400433b8  sub     rax, [rbx]
0x1400433bb  sar     rax, 3
0x1400433bf  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1400433c9  imul    rax, rcx
0x1400433cd  cmp     rax, 55h ; 'U'
0x1400433d1  jnb     short loc_1400433E0
0x1400433d3  lea     rdx, [rsp+220h+var_200]
0x1400433d8  mov     rcx, rbx
0x1400433db  call    ??$_Reallocate@$0A@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAXAEA_K@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Reallocate<0>(unsigned __int64 &)
0x1400433e0  xorps   xmm0, xmm0
0x1400433e3  movups  [rbp+120h+var_D8], xmm0
0x1400433e7  xorps   xmm1, xmm1
0x1400433ea  movdqu  [rbp+120h+var_C8], xmm1
0x1400433ef  mov     r14d, 28h ; '('
0x1400433f5  mov     r8d, r14d
0x1400433f8  lea     rdx, aClientStreamin_4; "Client\\Streaming\\PackageInstallationR"...
0x1400433ff  lea     rcx, [rbp+120h+var_D8]
0x140043403  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140043408  nop
0x140043409  lea     rdx, [rbp+120h+var_D8]
0x14004340d  lea     rcx, [rbp+120h+var_100]
0x140043411  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043416  lea     r12d, [r14-26h]
0x14004341a  mov     [rbp+120h+var_E0], r12d
0x14004341e  mov     [rbp+120h+var_DC], 100h
0x140043424  lea     esi, [r14-27h]
0x140043428  mov     rdi, [rbx+8]
0x14004342c  cmp     rdi, [rbx+10h]
0x140043430  jz      short loc_140043456
0x140043432  lea     rdx, [rbp+120h+var_100]
0x140043436  mov     rcx, rdi
0x140043439  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004343e  mov     eax, [rbp+120h+var_E0]
0x140043441  mov     [rdi+20h], eax
0x140043444  mov     al, byte ptr [rbp+120h+var_DC]
0x140043447  mov     [rdi+24h], al
0x14004344a  mov     al, byte ptr [rbp+120h+var_DC+1]
0x14004344d  mov     [rdi+25h], al
0x140043450  add     [rbx+8], r14
0x140043454  jmp     short loc_140043466
0x140043456  lea     r8, [rbp+120h+var_100]
0x14004345a  mov     rdx, rdi
0x14004345d  mov     rcx, rbx
0x140043460  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x140043465  nop
0x140043466  lea     rcx, [rbp+120h+var_100]
0x14004346a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004346f  nop
0x140043470  lea     rcx, [rbp+120h+var_D8]
0x140043474  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043479  xorps   xmm0, xmm0
0x14004347c  movups  [rbp+120h+var_D8], xmm0
0x140043480  xorps   xmm1, xmm1
0x140043483  movdqu  [rbp+120h+var_C8], xmm1
0x140043488  mov     r8, r14
0x14004348b  lea     rdx, aClientStreamin_4; "Client\\Streaming\\PackageInstallationR"...
0x140043492  lea     rcx, [rbp+120h+var_D8]
0x140043496  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004349b  nop
0x14004349c  lea     rdx, [rbp+120h+var_D8]
0x1400434a0  lea     rcx, [rbp+120h+var_100]
0x1400434a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400434a9  mov     [rbp+120h+var_E0], r12d
0x1400434ad  mov     [rbp+120h+var_DC], 100h
0x1400434b3  mov     rdi, [rbx+8]
0x1400434b7  cmp     rdi, [rbx+10h]
0x1400434bb  jz      short loc_1400434E1
0x1400434bd  lea     rdx, [rbp+120h+var_100]
0x1400434c1  mov     rcx, rdi
0x1400434c4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400434c9  mov     eax, [rbp+120h+var_E0]
0x1400434cc  mov     [rdi+20h], eax
0x1400434cf  mov     al, byte ptr [rbp+120h+var_DC]
0x1400434d2  mov     [rdi+24h], al
0x1400434d5  mov     al, byte ptr [rbp+120h+var_DC+1]
0x1400434d8  mov     [rdi+25h], al
0x1400434db  add     [rbx+8], r14
0x1400434df  jmp     short loc_1400434F1
0x1400434e1  lea     r8, [rbp+120h+var_100]
0x1400434e5  mov     rdx, rdi
0x1400434e8  mov     rcx, rbx
0x1400434eb  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x1400434f0  nop
0x1400434f1  lea     rcx, [rbp+120h+var_100]
0x1400434f5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400434fa  nop
0x1400434fb  lea     rcx, [rbp+120h+var_D8]
0x1400434ff  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043504  xorps   xmm0, xmm0
0x140043507  movups  [rbp+120h+var_D8], xmm0
0x14004350b  xorps   xmm1, xmm1
0x14004350e  movdqu  [rbp+120h+var_C8], xmm1
0x140043513  mov     r8d, 22h ; '"'
0x140043519  lea     rdx, aClientStreamin; "Client\\Streaming\\PackageSourceRoot"
0x140043520  lea     rcx, [rbp+120h+var_D8]
0x140043524  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140043529  nop
0x14004352a  lea     rdx, [rbp+120h+var_D8]
0x14004352e  lea     rcx, [rbp+120h+var_100]
0x140043532  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043537  mov     [rbp+120h+var_E0], r12d
0x14004353b  mov     [rbp+120h+var_DC], 100h
0x140043541  mov     rdi, [rbx+8]
0x140043545  cmp     rdi, [rbx+10h]
0x140043549  jz      short loc_14004356F
0x14004354b  lea     rdx, [rbp+120h+var_100]
0x14004354f  mov     rcx, rdi
0x140043552  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043557  mov     eax, [rbp+120h+var_E0]
0x14004355a  mov     [rdi+20h], eax
0x14004355d  mov     al, byte ptr [rbp+120h+var_DC]
0x140043560  mov     [rdi+24h], al
0x140043563  mov     al, byte ptr [rbp+120h+var_DC+1]
0x140043566  mov     [rdi+25h], al
0x140043569  add     [rbx+8], r14
0x14004356d  jmp     short loc_14004357F
0x14004356f  lea     r8, [rbp+120h+var_100]
0x140043573  mov     rdx, rdi
0x140043576  mov     rcx, rbx
0x140043579  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x14004357e  nop
0x14004357f  lea     rcx, [rbp+120h+var_100]
0x140043583  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043588  nop
0x140043589  lea     rcx, [rbp+120h+var_D8]
0x14004358d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043592  xorps   xmm0, xmm0
0x140043595  movups  [rbp+120h+var_D8], xmm0
0x140043599  xorps   xmm1, xmm1
0x14004359c  movdqu  [rbp+120h+var_C8], xmm1
0x1400435a1  mov     r8d, 21h ; '!'
0x1400435a7  lea     rdx, aClientStreamin_12; "Client\\Streaming\\LocationProvider"
0x1400435ae  lea     rcx, [rbp+120h+var_D8]
0x1400435b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400435b7  nop
0x1400435b8  lea     rdx, [rbp+120h+var_D8]
0x1400435bc  lea     rcx, [rbp+120h+var_100]
0x1400435c0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400435c5  mov     [rbp+120h+var_E0], r12d
0x1400435c9  mov     [rbp+120h+var_DC], 100h
0x1400435cf  mov     rdi, [rbx+8]
0x1400435d3  cmp     rdi, [rbx+10h]
0x1400435d7  jz      short loc_1400435FD
0x1400435d9  lea     rdx, [rbp+120h+var_100]
0x1400435dd  mov     rcx, rdi
0x1400435e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400435e5  mov     eax, [rbp+120h+var_E0]
0x1400435e8  mov     [rdi+20h], eax
0x1400435eb  mov     al, byte ptr [rbp+120h+var_DC]
0x1400435ee  mov     [rdi+24h], al
0x1400435f1  mov     al, byte ptr [rbp+120h+var_DC+1]
0x1400435f4  mov     [rdi+25h], al
0x1400435f7  add     [rbx+8], r14
0x1400435fb  jmp     short loc_14004360D
0x1400435fd  lea     r8, [rbp+120h+var_100]
0x140043601  mov     rdx, rdi
0x140043604  mov     rcx, rbx
0x140043607  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x14004360c  nop
0x14004360d  lea     rcx, [rbp+120h+var_100]
0x140043611  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043616  nop
0x140043617  lea     rcx, [rbp+120h+var_D8]
0x14004361b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043620  xorps   xmm0, xmm0
0x140043623  movups  [rbp+120h+var_D8], xmm0
0x140043627  xorps   xmm1, xmm1
0x14004362a  movdqu  [rbp+120h+var_C8], xmm1
0x14004362f  mov     r8d, 19h
0x140043635  lea     rdx, aClientStreamin_1; "Client\\Streaming\\AutoLoad"
0x14004363c  lea     rcx, [rbp+120h+var_D8]
0x140043640  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140043645  nop
0x140043646  lea     rdx, [rbp+120h+var_D8]
0x14004364a  lea     rcx, [rbp+120h+var_100]
0x14004364e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043653  mov     [rbp+120h+var_E0], esi
0x140043656  mov     [rbp+120h+var_DC], 100h
0x14004365c  mov     rdi, [rbx+8]
0x140043660  cmp     rdi, [rbx+10h]
0x140043664  jz      short loc_14004368A
0x140043666  lea     rdx, [rbp+120h+var_100]
0x14004366a  mov     rcx, rdi
0x14004366d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043672  mov     eax, [rbp+120h+var_E0]
0x140043675  mov     [rdi+20h], eax
0x140043678  mov     al, byte ptr [rbp+120h+var_DC]
0x14004367b  mov     [rdi+24h], al
0x14004367e  mov     al, byte ptr [rbp+120h+var_DC+1]
0x140043681  mov     [rdi+25h], al
0x140043684  add     [rbx+8], r14
0x140043688  jmp     short loc_14004369A
0x14004368a  lea     r8, [rbp+120h+var_100]
0x14004368e  mov     rdx, rdi
0x140043691  mov     rcx, rbx
0x140043694  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x140043699  nop
0x14004369a  lea     rcx, [rbp+120h+var_100]
0x14004369e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400436a3  nop
0x1400436a4  lea     rcx, [rbp+120h+var_D8]
0x1400436a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400436ad  xorps   xmm0, xmm0
0x1400436b0  movups  [rbp+120h+var_D8], xmm0
0x1400436b4  xorps   xmm1, xmm1
0x1400436b7  movdqu  [rbp+120h+var_C8], xmm1
0x1400436bc  mov     r8d, 25h ; '%'
0x1400436c2  lea     rdx, aClientScriptin; "Client\\Scripting\\EnablePackageScripts"
0x1400436c9  lea     rcx, [rbp+120h+var_D8]
0x1400436cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400436d2  nop
0x1400436d3  lea     rdx, [rbp+120h+var_D8]
0x1400436d7  lea     rcx, [rbp+120h+var_100]
0x1400436db  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400436e0  mov     [rbp+120h+var_E0], esi
0x1400436e3  mov     [rbp+120h+var_DC], 100h
0x1400436e9  mov     rdi, [rbx+8]
0x1400436ed  cmp     rdi, [rbx+10h]
0x1400436f1  jz      short loc_140043717
0x1400436f3  lea     rdx, [rbp+120h+var_100]
0x1400436f7  mov     rcx, rdi
0x1400436fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400436ff  mov     eax, [rbp+120h+var_E0]
0x140043702  mov     [rdi+20h], eax
0x140043705  mov     al, byte ptr [rbp+120h+var_DC]
0x140043708  mov     [rdi+24h], al
0x14004370b  mov     al, byte ptr [rbp+120h+var_DC+1]
0x14004370e  mov     [rdi+25h], al
0x140043711  add     [rbx+8], r14
0x140043715  jmp     short loc_140043727
0x140043717  lea     r8, [rbp+120h+var_100]
0x14004371b  mov     rdx, rdi
0x14004371e  mov     rcx, rbx
0x140043721  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x140043726  nop
0x140043727  lea     rcx, [rbp+120h+var_100]
0x14004372b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140043730  nop
0x140043731  lea     rcx, [rbp+120h+var_D8]
0x140043735  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004373a  xorps   xmm0, xmm0
0x14004373d  movups  [rbp+120h+var_D8], xmm0
0x140043741  xorps   xmm1, xmm1
0x140043744  movdqu  [rbp+120h+var_C8], xmm1
0x140043749  mov     r8, r14
0x14004374c  lea     rdx, aClientStreamin_2; "Client\\Streaming\\ReestablishmentInter"...
0x140043753  lea     rcx, [rbp+120h+var_D8]
0x140043757  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004375c  nop
0x14004375d  lea     rdx, [rbp+120h+var_D8]
0x140043761  lea     rcx, [rbp+120h+var_100]
0x140043765  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004376a  mov     [rbp+120h+var_E0], esi
0x14004376d  mov     [rbp+120h+var_DC], 100h
0x140043773  mov     rdi, [rbx+8]
0x140043777  cmp     rdi, [rbx+10h]
0x14004377b  jz      short loc_1400437A1
0x14004377d  lea     rdx, [rbp+120h+var_100]
0x140043781  mov     rcx, rdi
0x140043784  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140043789  mov     eax, [rbp+120h+var_E0]
0x14004378c  mov     [rdi+20h], eax
0x14004378f  mov     al, byte ptr [rbp+120h+var_DC]
0x140043792  mov     [rdi+24h], al
0x140043795  mov     al, byte ptr [rbp+120h+var_DC+1]
0x140043798  mov     [rdi+25h], al
0x14004379b  add     [rbx+8], r14
0x14004379f  jmp     short loc_1400437B1
0x1400437a1  lea     r8, [rbp+120h+var_100]
0x1400437a5  mov     rdx, rdi
0x1400437a8  mov     rcx, rbx
0x1400437ab  call    ??$_Emplace_reallocate@UConfigurationValue@ClientConfiguration@AppV@@@?$vector@UConfigurationValue@ClientConfiguration@AppV@@V?$allocator@UConfigurationValue@ClientConfiguration@AppV@@@std@@@std@@AEAAPEAUConfigurationValue@ClientConfiguration@AppV@@QEAU234@$$QEAU234@@Z; std::vector<AppV::ClientConfiguration::ConfigurationValue>::_Emplace_reallocate<AppV::ClientConfiguration::ConfigurationValue>(AppV::ClientConfiguration::ConfigurationValue * const,AppV::ClientConfiguration::ConfigurationValue &&)
0x1400437b0  nop
0x1400437b1  lea     rcx, [rbp+120h+var_100]
  ... truncated ...
```
