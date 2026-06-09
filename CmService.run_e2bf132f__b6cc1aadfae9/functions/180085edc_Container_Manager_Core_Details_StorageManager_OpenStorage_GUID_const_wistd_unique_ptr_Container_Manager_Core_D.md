# Container::Manager::Core::Details::StorageManager::OpenStorage(_GUID const &,wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>> &)

- ea: `0x180085edc`
- end: `0x180086cec`
- name: `?OpenStorage@StorageManager@Details@Core@Manager@Container@@QEAAJAEBU_GUID@@AEAV?$unique_ptr@VContainerStorage@Details@Core@Manager@Container@@U?$default_delete@VContainerStorage@Details@Core@Manager@Container@@@wistd@@@wistd@@@Z`
- size: `3600`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006dce0`
- `0x180082490`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180005704`
- `0x180006cac`
- `0x18000da68`
- `0x18000da88`
- `0x18002c5b4`
- `0x18002f7e0`
- `0x180032978`
- `0x180033684`
- `0x180033730`
- `0x180033b18`
- `0x180033ed8`
- `0x180033f84`
- `0x1800343f0`
- `0x18003d400`
- `0x18003e190`
- `0x18003eb74`
- `0x1800506c4`
- `0x18007f784`
- `0x180080580`
- `0x180080a00`
- `0x18008423c`
- `0x18008431c`
- `0x180084648`
- `0x180085edc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800865bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008664a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008675b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008690b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086c15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800865bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008664a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008675b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008690b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180086c15`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008658a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008658a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085fce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008613e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800866ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086c99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085fce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008613e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800866ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086c99`

## string_xrefs

- `0x180086000`: `onecore\base\gendrv\silos\csl\lib\CslRegistry.h`
- `0x18008603f`: `onecore\base\gendrv\silos\csl\lib\CslRegistry.h`
- `0x1800860b2`: `onecore\base\gendrv\silos\csl\lib\CslRegistry.h`
- `0x18008617e`: `onecore\base\gendrv\silos\csl\lib\CslRegistry.h`
- `0x180086359`: `DebugConfiguration`
- `0x180086524`: `SecurityDescriptor`
- `0x18008625d`: `EncryptionKeyPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Container::Manager::Core::Details::StorageManager::OpenStorage(__int64 a1, _OWORD *a2, __int64 a3)
{
  int v5; // eax
  int GuidValue; // ebx
  void *v7; // rcx
  __int64 v8; // r13
  __int64 v9; // rcx
  __int64 v10; // rdx
  int DwordValue; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // zf
  int v16; // eax
  int v17; // r12d
  unsigned int v18; // r14d
  __int64 v19; // rdx
  bool v20; // zf
  int v21; // eax
  int StringValue; // eax
  __int64 v23; // rdx
  int v24; // eax
  int QwordValue; // eax
  __int128 v26; // xmm6
  int v27; // eax
  const char *v28; // r9
  Container::Manager::Core::Details::ContainerStorage *v29; // rax
  char *v30; // rsi
  __int64 v32; // rdx
  struct _GUID v33; // xmm1
  PSECURITY_DESCRIPTOR v34; // rbx
  struct _GUID v35; // xmm2
  __int64 v36; // rax
  __int64 v37; // r11
  int v38; // eax
  int v39; // eax
  PSECURITY_DESCRIPTOR v40; // r15
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // r11
  int v44; // eax
  Container::Manager::Core::Details::ContainerStorage *v45; // rbx
  int v46; // [rsp+28h] [rbp-E0h]
  int v47; // [rsp+28h] [rbp-E0h]
  int v48; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+88h] [rbp-80h] BYREF
  void *v50[2]; // [rsp+90h] [rbp-78h] BYREF
  _WORD v51[8]; // [rsp+A0h] [rbp-68h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-58h] BYREF
  void *v53[2]; // [rsp+B8h] [rbp-50h] BYREF
  _WORD v54[8]; // [rsp+C8h] [rbp-40h] BYREF
  void *v55[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v56; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v57; // [rsp+F8h] [rbp-10h]
  void *v58[2]; // [rsp+100h] [rbp-8h] BYREF
  _WORD v59[8]; // [rsp+110h] [rbp+8h] BYREF
  unsigned int v60; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v61; // [rsp+124h] [rbp+1Ch] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+128h] [rbp+20h] BYREF
  _WORD v63[8]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v64[2]; // [rsp+148h] [rbp+40h] BYREF
  int v65; // [rsp+158h] [rbp+50h]
  unsigned int v66; // [rsp+160h] [rbp+58h] BYREF
  Container::Manager::Core::Details::ContainerStorage *v67[2]; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v68; // [rsp+178h] [rbp+70h] BYREF
  void *v69[2]; // [rsp+180h] [rbp+78h] BYREF
  _WORD v70[8]; // [rsp+190h] [rbp+88h] BYREF
  void *v71[2]; // [rsp+1A0h] [rbp+98h] BYREF
  __int16 v72; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v73; // [rsp+1B2h] [rbp+AAh]
  int v74; // [rsp+1BAh] [rbp+B2h]
  __int16 v75; // [rsp+1BEh] [rbp+B6h]
  __int64 v76; // [rsp+1C0h] [rbp+B8h]
  __int64 v77[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _BYTE v78[216]; // [rsp+1D8h] [rbp+D0h] BYREF
  char v79; // [rsp+2B0h] [rbp+1A8h]
  __int64 v80[2]; // [rsp+2B8h] [rbp+1B0h] BYREF
  struct _GUID v81; // [rsp+2C8h] [rbp+1C0h]
  _BYTE v82[32]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v83[40]; // [rsp+2F8h] [rbp+1F0h] BYREF
  struct _GUID v84; // [rsp+320h] [rbp+218h] BYREF
  struct _GUID v85; // [rsp+330h] [rbp+228h] BYREF
  struct _GUID v86; // [rsp+340h] [rbp+238h] BYREF
  struct _GUID v87; // [rsp+350h] [rbp+248h] BYREF
  int v88; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v89[72]; // [rsp+370h] [rbp+268h] BYREF
  _BYTE v90[80]; // [rsp+3B8h] [rbp+2B0h] BYREF
  __int16 v91; // [rsp+408h] [rbp+300h]
  __int128 v92; // [rsp+40Ch] [rbp+304h]
  __int64 v93; // [rsp+420h] [rbp+318h]
  __m128i si128; // [rsp+428h] [rbp+320h]
  char v95; // [rsp+438h] [rbp+330h]
  char v96; // [rsp+440h] [rbp+338h]
  wil::details::in1diag3 *retaddr; // [rsp+4A0h] [rbp+398h]

  *(_QWORD *)&v85.Data1 = a2;
  v76 = a3;
  v50[0] = v51;
  v50[1] = v51;
  v51[0] = 0;
  v5 = Csl::GuidToString(a2, v50);
  GuidValue = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)v5,
      v46);
    goto LABEL_3;
  }
  v8 = a1 + 8;
  v9 = *(_QWORD *)(a1 + 8);
  hKey = 0;
  GuidValue = Csl::OpenRegistryKey(v9, v50[0], 131103, &hKey);
  if ( GuidValue < 0 )
  {
    v10 = 226;
    goto LABEL_7;
  }
  v61 = 0;
  DwordValue = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"ClientId", &v61);
  GuidValue = DwordValue;
  if ( DwordValue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslRegistry.h",
      (const char *)(unsigned int)DwordValue,
      v46);
    v10 = 231;
    goto LABEL_7;
  }
  v60 = 0;
  v12 = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"ParentType", &v60);
  GuidValue = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslRegistry.h",
      (const char *)(unsigned int)v12,
      v46);
    v10 = 236;
    goto LABEL_7;
  }
  v86 = 0;
  GuidValue = Csl::RegistryKey::GetGuidValue((Csl::RegistryKey *)&hKey, L"ParentId", &v86);
  if ( GuidValue < 0 )
  {
    v10 = 241;
    goto LABEL_7;
  }
  v66 = 0;
  v13 = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"State", &v66);
  GuidValue = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslRegistry.h",
      (const char *)(unsigned int)v13,
      v46);
    v10 = 246;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)GuidValue,
      v46);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_3:
    v7 = v50[0];
    if ( v50[0] != v51 )
      goto LABEL_168;
    return (unsigned int)GuidValue;
  }
  v54[0] = 0;
  v53[0] = v54;
  v53[1] = v54;
  GuidValue = Csl::RegistryKey::GetPathValue((Csl::RegistryKey *)&hKey, L"StorageFolder", (struct Path *)v53);
  if ( GuidValue < 0 )
  {
    v14 = 251;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)GuidValue,
      v46);
LABEL_20:
    if ( v53[0] != v54 )
      operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey )
      RegCloseKey(hKey);
    v7 = v50[0];
    v15 = v50[0] == v51;
    goto LABEL_167;
  }
  v68 = 0;
  v16 = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"BackingType", &v68);
  GuidValue = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslRegistry.h",
      (const char *)(unsigned int)v16,
      v46);
    v14 = 256;
    goto LABEL_19;
  }
  LODWORD(v67[0]) = 0;
  GuidValue = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"Flags", (unsigned int *)v67);
  if ( GuidValue < 0 )
  {
    v14 = 261;
    goto LABEL_19;
  }
  v17 = (int)v67[0];
  v18 = v66;
  v57 = 0;
  *(_OWORD *)v55 = 0;
  v56 = 0;
  if ( ((__int64)v67[0] & 1) != 0 && v66 == 2 )
  {
    v73 = 0;
    v71[0] = &v72;
    v74 = 0;
    v71[1] = &v72;
    v75 = 0;
    v72 = 0;
    utl::optional<Csl::Path>::operator=<Csl::Path,0>(v55, v71);
    if ( v71[0] != &v72 )
      operator delete(v71[0], (const struct std::nothrow_t *)&std::nothrow);
    GuidValue = Csl::RegistryKey::GetPathValue((Csl::RegistryKey *)&hKey, L"EncryptionKeyPath", (struct Path *)v55);
    if ( GuidValue < 0 )
    {
      v19 = 272;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)GuidValue,
        v46);
LABEL_36:
      v20 = (_BYTE)v57 == 0;
LABEL_37:
      if ( !v20 && v55[0] != &v56 )
        operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_20;
    }
  }
  v65 = 0;
  *(_OWORD *)v64 = 0;
  v84 = 0;
  v21 = Csl::RegistryKey::GetGuidValue((Csl::RegistryKey *)&hKey, L"ServicingTransactionId", &v84);
  GuidValue = v21;
  if ( v21 != -2147024894 )
  {
    if ( v21 < 0 )
    {
      v19 = 290;
      goto LABEL_35;
    }
    LOBYTE(v64[0]) = v84.Data1;
    *(_DWORD *)((char *)&v64[1] + 1) = *(_DWORD *)&v84.Data4[1];
    *(_WORD *)((char *)&v64[1] + 5) = *(_WORD *)&v84.Data4[5];
    HIBYTE(v64[1]) = v84.Data4[7];
    *(__int64 *)((char *)v64 + 1) = *(_QWORD *)((char *)&v84.Data1 + 1);
    if ( !(_BYTE)v65 )
      LOBYTE(v65) = 1;
  }
  memset_0(v78, 0, 0xE0u);
  v59[0] = 0;
  v58[0] = v59;
  v58[1] = v59;
  StringValue = Csl::RegistryKey::GetStringValue(&hKey, L"DebugConfiguration", v58);
  GuidValue = StringValue;
  if ( StringValue != -2147024894 )
  {
    if ( StringValue < 0 )
    {
      v23 = 306;
LABEL_48:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)GuidValue,
        v46);
LABEL_49:
      if ( v58[0] != v59 )
        operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v79 )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
      goto LABEL_36;
    }
    v88 = 0;
    memset_0(v89, 0, sizeof(v89));
    v89[0] = 0;
    v89[64] = 0;
    memset_0(v90, 0, sizeof(v90));
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v90[0] = 0;
    v92 = 0;
    v90[72] = 0;
    v91 = 0;
    v93 = -1;
    v95 = 0;
    v24 = Csl::MarshalFromJson<Container::Manager::Core::Details::DebugConfiguration>(v58, &v88);
    GuidValue = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v24,
        v46);
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)&v88);
      goto LABEL_49;
    }
    if ( v79 )
    {
      Container::Manager::Core::Details::DebugConfiguration::operator=(v78, &v88);
    }
    else
    {
      Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(v78, &v88);
      v79 = 1;
    }
    Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)&v88);
  }
  v67[0] = 0;
  QwordValue = Csl::RegistryKey::GetQwordValue((Csl::RegistryKey *)&hKey, L"MaxSizeInBytes", (unsigned __int64 *)v67);
  GuidValue = QwordValue;
  if ( (v18 - 2 > 1 || QwordValue != -2147024894) && QwordValue < 0 )
  {
    v23 = 326;
    goto LABEL_48;
  }
  v26 = 0;
  if ( QwordValue != -2147024894 )
  {
    LOBYTE(v67[1]) = 1;
    v26 = *(_OWORD *)v67;
  }
  v63[0] = 0;
  StringSecurityDescriptor[0] = v63;
  StringSecurityDescriptor[1] = v63;
  v27 = Csl::RegistryKey::GetStringValue(&hKey, L"SecurityDescriptor", StringSecurityDescriptor);
  GuidValue = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)(unsigned int)v27,
      v46);
LABEL_67:
    if ( StringSecurityDescriptor[0] != v63 )
      operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_49;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, &SecurityDescriptor, 0) )
  {
    GuidValue = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x15B,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
                  v28);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_67;
  }
  v29 = (Container::Manager::Core::Details::ContainerStorage *)operator new(
                                                                 0x1A0u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
  if ( !v29
    || (v67[0] = (Container::Manager::Core::Details::ContainerStorage *)Container::Manager::Core::Details::ContainerStorage::ContainerStorage(v29),
        (v30 = (char *)v67[0]) == 0) )
  {
    GuidValue = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x160,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
      (const char *)0x8007000ELL,
      v46);
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    if ( StringSecurityDescriptor[0] != v63 )
      operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v58[0] != v59 )
      operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v79 )
      Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
    if ( (_BYTE)v57 && v55[0] != &v56 )
      operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v53[0] != v54 )
      operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( hKey )
      RegCloseKey(hKey);
    v7 = v50[0];
    v15 = v50[0] == v51;
LABEL_167:
    if ( !v15 )
LABEL_168:
      operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)GuidValue;
  }
  if ( v68 == 1 )
  {
    v69[0] = v70;
    v69[1] = v70;
    v70[0] = 0;
    v39 = Container::Manager::Core::Details::ContainerStorage::Vhd::Initialize(
            (Container::Manager::Core::Details::ContainerStorage::Vhd *)v69,
            (const struct Path *)v53);
    GuidValue = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v39,
        v46);
      if ( v69[0] != v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_97;
    }
    v40 = SecurityDescriptor;
    LOBYTE(v88) = 0;
    v96 = 0;
    if ( v79 )
    {
      Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(&v88, v78);
      v96 = 1;
    }
    v41 = Container::Manager::Core::Details::ContainerStorage::Vhd::Vhd(v82, v69);
    utl::optional<Csl::Path>::optional<Csl::Path>(v83, v55);
    v42 = Container::Manager::Core::Details::ContainerStorage::Vhd::Vhd(v80, v53);
    *(_OWORD *)v77 = v26;
    v44 = Container::Manager::Core::Details::ContainerStorage::InitializeAsVhd(
            v30,
            *(_OWORD **)&v85.Data1,
            v61,
            v60,
            &v86,
            v18,
            v42,
            v17,
            v43,
            (__int64)v64,
            v41,
            v8,
            (Container::Manager::Core::Details::DebugConfiguration *)&v88,
            (__int128 *)v77,
            v40);
    GuidValue = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x178,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v44,
        v48);
      if ( v69[0] != v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_112;
    }
    if ( v69[0] != v70 )
      operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  else
  {
    if ( v68 != 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)0x8000FFFFLL,
        v46);
      Container::Manager::Core::Details::ContainerStorage::~ContainerStorage((Container::Manager::Core::Details::ContainerStorage *)v30);
      operator delete(v30, (const struct std::nothrow_t *)0x1A0);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      if ( StringSecurityDescriptor[0] != v63 )
        operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v58[0] != v59 )
        operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v79 )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
      if ( (_BYTE)v57 && v55[0] != &v56 )
        operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v50[0] != v51 )
        operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
      return 2147549183LL;
    }
    v85 = 0;
    GuidValue = Csl::RegistryKey::GetGuidValue((Csl::RegistryKey *)&hKey, L"PoolId", &v85);
    if ( GuidValue < 0 )
    {
      v32 = 387;
LABEL_96:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)GuidValue,
        v46);
LABEL_97:
      Container::Manager::Core::Details::ContainerStorage::~ContainerStorage((Container::Manager::Core::Details::ContainerStorage *)v30);
      operator delete(v30, (const struct std::nothrow_t *)0x1A0);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      if ( StringSecurityDescriptor[0] != v63 )
        operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v58[0] != v59 )
        operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v79 )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
      v20 = (_BYTE)v57 == 0;
      goto LABEL_37;
    }
    v87 = 0;
    GuidValue = Csl::RegistryKey::GetGuidValue((Csl::RegistryKey *)&hKey, L"SpaceId", &v87);
    if ( GuidValue < 0 )
    {
      v32 = 392;
      goto LABEL_96;
    }
    v33 = v85;
    v34 = SecurityDescriptor;
    v35 = v87;
    LOBYTE(v88) = 0;
    v96 = 0;
    if ( v79 )
    {
      Container::Manager::Core::Details::DebugConfiguration::DebugConfiguration(&v88, v78);
      v96 = 1;
    }
    *(struct _GUID *)v80 = v33;
    v81 = v35;
    utl::optional<Csl::Path>::optional<Csl::Path>(v83, v55);
    v36 = Container::Manager::Core::Details::ContainerStorage::Vhd::Vhd(v82, v53);
    *(_OWORD *)v77 = v26;
    v38 = Container::Manager::Core::Details::ContainerStorage::InitializeAsStorageSpace(
            v30,
            a2,
            v61,
            v60,
            &v86,
            v18,
            v36,
            v17,
            v37,
            (__int64)v64,
            v80,
            v8,
            (Container::Manager::Core::Details::DebugConfiguration *)&v88,
            (__int128 *)v77,
            v34);
    GuidValue = v38;
    if ( v38 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\storage.cpp",
        (const char *)(unsigned int)v38,
        v47);
LABEL_112:
      Container::Manager::Core::Details::ContainerStorage::~ContainerStorage((Container::Manager::Core::Details::ContainerStorage *)v30);
      operator delete(v30, (const struct std::nothrow_t *)0x1A0);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      if ( StringSecurityDescriptor[0] != v63 )
        operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v58[0] != v59 )
        operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v79 )
        Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
      v20 = (_BYTE)v57 == 0;
      goto LABEL_37;
    }
  }
  wistd::unique_ptr<Container::Manager::Core::Details::ContainerStorage,wistd::default_delete<Container::Manager::Core::Details::ContainerStorage>>::operator=(
    v76,
    v67);
  v45 = v67[0];
  if ( v67[0] )
  {
    Container::Manager::Core::Details::ContainerStorage::~ContainerStorage(v67[0]);
    operator delete(v45, (const struct std::nothrow_t *)0x1A0);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( StringSecurityDescriptor[0] != v63 )
    operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v58[0] != v59 )
    operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v79 )
    Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration((Container::Manager::Core::Details::DebugConfiguration *)v78);
  if ( (_BYTE)v57 && v55[0] != &v56 )
    operator delete(v55[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v53[0] != v54 )
    operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v50[0] != v51 )
    operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x180085edc  mov     rax, rsp
0x180085edf  mov     [rax+20h], rbx
0x180085ee3  push    rbp
0x180085ee4  push    rsi
0x180085ee5  push    rdi
0x180085ee6  push    r12
0x180085ee8  push    r13
0x180085eea  push    r14
0x180085eec  push    r15
0x180085eee  lea     rbp, [rax-398h]
0x180085ef5  sub     rsp, 460h
0x180085efc  movaps  xmmword ptr [rax-48h], xmm6
0x180085f00  mov     rax, cs:__security_cookie
0x180085f07  xor     rax, rsp
0x180085f0a  mov     [rbp+390h+var_50], rax
0x180085f11  mov     r15, rdx
0x180085f14  mov     qword ptr [rbp+390h+var_168.Data1], rdx
0x180085f1b  lea     rax, [rbp+390h+var_3F8]
0x180085f1f  mov     [rbp+390h+var_2D8], r8
0x180085f26  mov     [rbp+390h+var_408], rax
0x180085f2a  lea     rdx, [rbp+390h+var_408]
0x180085f2e  lea     rax, [rbp+390h+var_3F8]
0x180085f32  mov     rdi, rcx
0x180085f35  xor     esi, esi
0x180085f37  mov     [rbp+390h+var_400], rax
0x180085f3b  mov     rcx, r15
0x180085f3e  mov     [rbp+390h+var_3F8], si
0x180085f42  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180085f47  mov     ebx, eax
0x180085f49  test    eax, eax
0x180085f4b  jns     short loc_180085F85
0x180085f4d  mov     rcx, [rbp+398h]; this
0x180085f54  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180085f5b  mov     r9d, eax; char *
0x180085f5e  mov     edx, 0DBh; void *
0x180085f63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085f68  mov     rcx, [rbp+390h+var_408]
0x180085f6c  lea     rax, [rbp+390h+var_3F8]
0x180085f70  cmp     rcx, rax
0x180085f73  jz      loc_180086CBA
0x180085f79  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180085f80  jmp     loc_180086CB5
0x180085f85  mov     rdx, [rbp+390h+var_408]
0x180085f89  lea     r13, [rdi+8]
0x180085f8d  mov     rcx, [r13+0]
0x180085f91  lea     r9, [rbp+390h+hKey]
0x180085f95  mov     r8d, 2001Fh
0x180085f9b  mov     [rbp+390h+hKey], rsi
0x180085f9f  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180085fa4  mov     ebx, eax
0x180085fa6  test    eax, eax
0x180085fa8  jns     short loc_180085FDC
0x180085faa  mov     edx, 0E2h; void *
0x180085faf  mov     rcx, [rbp+398h]; this
0x180085fb6  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180085fbd  mov     r9d, ebx; char *
0x180085fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085fc5  mov     rcx, [rbp+390h+hKey]; hKey
0x180085fc9  test    rcx, rcx
0x180085fcc  jz      short loc_180085F68
0x180085fce  call    cs:__imp_RegCloseKey
0x180085fd5  nop     dword ptr [rax+rax+00h]
0x180085fda  jmp     short loc_180085F68
0x180085fdc  lea     r8, [rbp+390h+var_374]; unsigned int *
0x180085fe0  mov     [rbp+390h+var_374], esi
0x180085fe3  lea     rdx, aClientid; "ClientId"
0x180085fea  lea     rcx, [rbp+390h+hKey]; this
0x180085fee  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x180085ff3  mov     ebx, eax
0x180085ff5  test    eax, eax
0x180085ff7  jns     short loc_18008601B
0x180085ff9  mov     rcx, [rbp+398h]; this
0x180086000  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180086007  mov     r9d, eax; char *
0x18008600a  mov     edx, 69Ch; void *
0x18008600f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086014  mov     edx, 0E7h
0x180086019  jmp     short loc_180085FAF
0x18008601b  lea     r8, [rbp+390h+var_378]; unsigned int *
0x18008601f  mov     [rbp+390h+var_378], esi
0x180086022  lea     rdx, aParenttype; "ParentType"
0x180086029  lea     rcx, [rbp+390h+hKey]; this
0x18008602d  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x180086032  mov     ebx, eax
0x180086034  test    eax, eax
0x180086036  jns     short loc_18008605D
0x180086038  mov     rcx, [rbp+398h]; this
0x18008603f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180086046  mov     r9d, eax; char *
0x180086049  mov     edx, 69Ch; void *
0x18008604e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086053  mov     edx, 0ECh
0x180086058  jmp     loc_180085FAF
0x18008605d  xorps   xmm0, xmm0
0x180086060  lea     r8, [rbp+390h+var_158]; struct _GUID *
0x180086067  lea     rdx, aParentid; "ParentId"
0x18008606e  lea     rcx, [rbp+390h+hKey]; this
0x180086072  movups  xmmword ptr [rbp+390h+var_158.Data1], xmm0
0x180086079  call    ?GetGuidValue@RegistryKey@Csl@@QEBAJPEBGAEAU_GUID@@@Z; Csl::RegistryKey::GetGuidValue(ushort const *,_GUID &)
0x18008607e  mov     ebx, eax
0x180086080  test    eax, eax
0x180086082  jns     short loc_18008608E
0x180086084  mov     edx, 0F1h
0x180086089  jmp     loc_180085FAF
0x18008608e  lea     r8, [rbp+390h+var_338]; unsigned int *
0x180086092  mov     [rbp+390h+var_338], esi
0x180086095  lea     rdx, aState; "State"
0x18008609c  lea     rcx, [rbp+390h+hKey]; this
0x1800860a0  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x1800860a5  mov     ebx, eax
0x1800860a7  test    eax, eax
0x1800860a9  jns     short loc_1800860D0
0x1800860ab  mov     rcx, [rbp+398h]; this
0x1800860b2  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800860b9  mov     r9d, eax; char *
0x1800860bc  mov     edx, 69Ch; void *
0x1800860c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800860c6  mov     edx, 0F6h
0x1800860cb  jmp     loc_180085FAF
0x1800860d0  lea     rax, [rbp+390h+var_3D0]
0x1800860d4  mov     [rbp+390h+var_3D0], si
0x1800860d8  mov     [rbp+390h+var_3E0], rax
0x1800860dc  lea     r8, [rbp+390h+var_3E0]; struct Path *
0x1800860e0  lea     rax, [rbp+390h+var_3D0]
0x1800860e4  lea     rdx, aStoragefolder; "StorageFolder"
0x1800860eb  mov     [rbp+390h+var_3D8], rax
0x1800860ef  lea     rcx, [rbp+390h+hKey]; this
0x1800860f3  call    ?GetPathValue@RegistryKey@Csl@@QEBAJPEBGAEAVPath@2@@Z; Csl::RegistryKey::GetPathValue(ushort const *,Csl::Path &)
0x1800860f8  mov     ebx, eax
0x1800860fa  test    eax, eax
0x1800860fc  jns     short loc_18008615A
0x1800860fe  mov     edx, 0FBh; void *
0x180086103  mov     rcx, [rbp+398h]; this
0x18008610a  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180086111  mov     r9d, ebx; char *
0x180086114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086119  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180086120  mov     rcx, [rbp+390h+var_3E0]; void *
0x180086124  lea     rax, [rbp+390h+var_3D0]
0x180086128  cmp     rcx, rax
0x18008612b  jz      short loc_180086135
0x18008612d  mov     rdx, rdi; struct std::nothrow_t *
0x180086130  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086135  mov     rcx, [rbp+390h+hKey]; hKey
0x180086139  test    rcx, rcx
0x18008613c  jz      short loc_18008614A
0x18008613e  call    cs:__imp_RegCloseKey
0x180086145  nop     dword ptr [rax+rax+00h]
0x18008614a  mov     rcx, [rbp+390h+var_408]
0x18008614e  lea     rax, [rbp+390h+var_3F8]
0x180086152  cmp     rcx, rax
0x180086155  jmp     loc_180086CB0
0x18008615a  lea     r8, [rbp+390h+var_320]; unsigned int *
0x18008615e  mov     [rbp+390h+var_320], esi
0x180086161  lea     rdx, aBackingtype; "BackingType"
0x180086168  lea     rcx, [rbp+390h+hKey]; this
0x18008616c  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x180086171  mov     ebx, eax
0x180086173  test    eax, eax
0x180086175  jns     short loc_18008619C
0x180086177  mov     rcx, [rbp+398h]; this
0x18008617e  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180086185  mov     r9d, eax; char *
0x180086188  mov     edx, 69Ch; void *
0x18008618d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086192  mov     edx, 100h
0x180086197  jmp     loc_180086103
0x18008619c  lea     r8, [rbp+390h+var_330]; unsigned int *
0x1800861a0  mov     dword ptr [rbp+390h+var_330], esi
0x1800861a3  lea     rdx, aFlags; "Flags"
0x1800861aa  lea     rcx, [rbp+390h+hKey]; this
0x1800861ae  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x1800861b3  mov     ebx, eax
0x1800861b5  test    eax, eax
0x1800861b7  jns     short loc_1800861C3
0x1800861b9  mov     edx, 105h
0x1800861be  jmp     loc_180086103
0x1800861c3  mov     r12d, dword ptr [rbp+390h+var_330]
0x1800861c7  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800861ce  mov     r14d, [rbp+390h+var_338]
0x1800861d2  xor     eax, eax
0x1800861d4  mov     [rbp+390h+var_3A0], rax
0x1800861d8  xorps   xmm0, xmm0
0x1800861db  movups  xmmword ptr [rbp+390h+var_3C0], xmm0
0x1800861df  movups  [rbp+390h+var_3B0], xmm0
0x1800861e3  test    r12b, 1
0x1800861e7  jz      loc_1800862B6
0x1800861ed  cmp     r14d, 2
0x1800861f1  jnz     loc_1800862B6
0x1800861f7  lea     rax, [rbp+390h+var_2E8]
0x1800861fe  mov     [rbp+390h+var_2E6], rsi
0x180086205  mov     [rbp+390h+var_2F8], rax
0x18008620c  lea     rdx, [rbp+390h+var_2F8]
0x180086213  lea     rax, [rbp+390h+var_2E8]
0x18008621a  mov     [rbp+390h+var_2DE], esi
0x180086220  lea     rcx, [rbp+390h+var_3C0]
0x180086224  mov     [rbp+390h+var_2F0], rax
0x18008622b  mov     [rbp+390h+var_2DA], si
0x180086232  mov     [rbp+390h+var_2E8], si
0x180086239  call    ??$?4VPath@Csl@@$0A@@?$optional@VPath@Csl@@@utl@@QEAAAEAV01@$$QEAVPath@Csl@@@Z; utl::optional<Csl::Path>::operator=<Csl::Path,0>(Csl::Path &&)
0x18008623e  mov     rcx, [rbp+390h+var_2F8]; void *
0x180086245  lea     rax, [rbp+390h+var_2E8]
0x18008624c  cmp     rcx, rax
0x18008624f  jz      short loc_180086259
0x180086251  mov     rdx, rdi; struct std::nothrow_t *
0x180086254  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180086259  lea     r8, [rbp+390h+var_3C0]; struct Path *
0x18008625d  lea     rdx, aEncryptionkeyp; "EncryptionKeyPath"
0x180086264  lea     rcx, [rbp+390h+hKey]; this
0x180086268  call    ?GetPathValue@RegistryKey@Csl@@QEBAJPEBGAEAVPath@2@@Z; Csl::RegistryKey::GetPathValue(ushort const *,Csl::Path &)
0x18008626d  mov     ebx, eax
0x18008626f  test    eax, eax
0x180086271  jns     short loc_1800862B6
0x180086273  mov     edx, 110h; void *
0x180086278  mov     rcx, [rbp+398h]; this
0x18008627f  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180086286  mov     r9d, ebx; char *
0x180086289  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008628e  cmp     byte ptr [rbp+390h+var_3A0], sil
0x180086292  jz      loc_180086120
0x180086298  mov     rcx, [rbp+390h+var_3C0]; void *
0x18008629c  lea     rax, [rbp+390h+var_3B0]
0x1800862a0  cmp     rcx, rax
0x1800862a3  jz      loc_180086120
0x1800862a9  mov     rdx, rdi; struct std::nothrow_t *
0x1800862ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800862b1  jmp     loc_180086120
0x1800862b6  xorps   xmm0, xmm0
0x1800862b9  lea     r8, [rbp+390h+var_178]; struct _GUID *
0x1800862c0  xor     eax, eax
0x1800862c2  lea     rdx, aServicingtrans_1; "ServicingTransactionId"
0x1800862c9  lea     rcx, [rbp+390h+hKey]; this
0x1800862cd  mov     [rbp+390h+var_340], eax
0x1800862d0  movups  xmmword ptr [rbp+390h+var_350], xmm0
0x1800862d4  movups  xmmword ptr [rbp+390h+var_178.Data1], xmm0
0x1800862db  call    ?GetGuidValue@RegistryKey@Csl@@QEBAJPEBGAEAU_GUID@@@Z; Csl::RegistryKey::GetGuidValue(ushort const *,_GUID &)
0x1800862e0  mov     ebx, eax
0x1800862e2  cmp     eax, 80070002h
0x1800862e7  jz      short loc_180086331
0x1800862e9  test    eax, eax
0x1800862eb  jns     short loc_1800862F4
0x1800862ed  mov     edx, 122h
0x1800862f2  jmp     short loc_180086278
0x1800862f4  mov     al, byte ptr [rbp+390h+var_178.Data1]
0x1800862fa  movsd   xmm0, qword ptr [rbp+390h+var_178.Data1+1]
0x180086302  mov     byte ptr [rbp+390h+var_350], al
0x180086305  mov     eax, dword ptr [rbp+390h+var_178.Data4+1]
0x18008630b  mov     dword ptr [rbp+390h+var_350+9], eax
0x18008630e  movzx   eax, word ptr [rbp+390h+var_178.Data4+5]
0x180086315  mov     word ptr [rbp+390h+var_350+0Dh], ax
0x180086319  mov     al, [rbp+390h+var_178.Data4+7]
0x18008631f  mov     byte ptr [rbp+390h+var_350+0Fh], al
0x180086322  movsd   [rbp+390h+var_350+1], xmm0
0x180086327  cmp     byte ptr [rbp+390h+var_340], sil
0x18008632b  jnz     short loc_180086331
0x18008632d  mov     byte ptr [rbp+390h+var_340], 1
0x180086331  xor     edx, edx; Val
0x180086333  lea     rcx, [rbp+390h+var_2C0]; void *
0x18008633a  mov     r8d, 0E0h; Size
0x180086340  call    memset_0
0x180086345  lea     rax, [rbp+390h+var_388]
0x180086349  mov     [rbp+390h+var_388], si
0x18008634d  mov     [rbp+390h+var_398], rax
0x180086351  lea     r8, [rbp+390h+var_398]
0x180086355  lea     rax, [rbp+390h+var_388]
0x180086359  lea     rdx, aDebugconfigura; "DebugConfiguration"
0x180086360  mov     [rbp+390h+var_390], rax
0x180086364  lea     rcx, [rbp+390h+hKey]
0x180086368  call    ?GetStringValue@RegistryKey@Csl@@QEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::RegistryKey::GetStringValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18008636d  mov     ebx, eax
0x18008636f  cmp     eax, 80070002h
0x180086374  jz      loc_1800864BD
0x18008637a  test    eax, eax
0x18008637c  jns     short loc_1800863CC
0x18008637e  mov     edx, 132h; void *
0x180086383  mov     rcx, [rbp+398h]; this
0x18008638a  lea     r8, aOnecoreBaseGen_54; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180086391  mov     r9d, ebx; char *
0x180086394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180086399  mov     rcx, [rbp+390h+var_398]; void *
0x18008639d  lea     rax, [rbp+390h+var_388]
0x1800863a1  cmp     rcx, rax
0x1800863a4  jz      short loc_1800863AE
0x1800863a6  mov     rdx, rdi; struct std::nothrow_t *
0x1800863a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800863ae  cmp     [rbp+390h+var_1E8], sil
0x1800863b5  jz      loc_18008628E
0x1800863bb  lea     rcx, [rbp+390h+var_2C0]; this
0x1800863c2  call    ??1DebugConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfiguration::~DebugConfiguration(void)
0x1800863c7  jmp     loc_18008628E
0x1800863cc  xor     edx, edx; Val
0x1800863ce  mov     [rbp+390h+var_130], esi
0x1800863d4  lea     rcx, [rbp+390h+var_128]; void *
0x1800863db  lea     r8d, [rdx+48h]; Size
0x1800863df  call    memset_0
0x1800863e4  xor     edx, edx; Val
0x1800863e6  mov     [rbp+390h+var_128], sil
0x1800863ed  lea     rcx, [rbp+390h+var_E0]; void *
0x1800863f4  mov     [rbp+390h+var_E8], sil
0x1800863fb  lea     r8d, [rdx+50h]; Size
  ... truncated ...
```
