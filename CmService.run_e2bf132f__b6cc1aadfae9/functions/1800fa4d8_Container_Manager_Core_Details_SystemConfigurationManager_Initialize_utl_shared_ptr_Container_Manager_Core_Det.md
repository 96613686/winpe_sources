# Container::Manager::Core::Details::SystemConfigurationManager::Initialize(utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &)

- ea: `0x1800fa4d8`
- end: `0x1800fb01d`
- name: `?Initialize@SystemConfigurationManager@Details@Core@Manager@Container@@QEAAJAEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@@Z`
- size: `2885`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::SystemConfigurationManager *this)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180075454`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x180016658`
- `0x180023b68`
- `0x1800262e4`
- `0x18002c6f8`
- `0x18002dc0c`
- `0x180033684`
- `0x1800343f0`
- `0x1800471dc`
- `0x18004dea8`
- `0x180096700`
- `0x1800e7fc0`
- `0x1800f9f9c`
- `0x1800fa4d8`
- `0x1800fb5b0`
- `0x1800fc060`
- `0x1800fc19c`

## import_xrefs

- `ntdll!NtQuerySystemInformationEx` at `0x1800fa9ba`
- `ntdll!NtQuerySystemInformationEx` at `0x1800fa9ba`
- `ntdll!RtlQueryAllInternalFeatureConfigurations` at `0x1800fa7f0`
- `ntdll!RtlQueryAllInternalFeatureConfigurations` at `0x1800fa86f`
- `ntdll!RtlQueryAllInternalFeatureConfigurations` at `0x1800fa7f0`
- `ntdll!RtlQueryAllInternalFeatureConfigurations` at `0x1800fa86f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fab1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800fab1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800faba1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fac43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800facb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fade2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800faba1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fac43`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800facb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800fade2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fadcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fae0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fadcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fae0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fac51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fadf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fae36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fac51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fadf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800fae36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fab8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fac94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fae20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fab8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fac94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fae20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fa7c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fa9ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800faa50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fa7c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fa9ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800faa50`

## string_xrefs

- `0x1800fa54b`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fa6a1`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fa707`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fa766`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fab6f`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`
- `0x1800fae6b`: `onecore\base\gendrv\silos\clem\core\lib\systemconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::SystemConfigurationManager::Initialize(
        Container::Manager::Core::Details::SystemConfigurationManager *this)
{
  __int64 v2; // rdi
  HKEY v3; // r12
  int FeatureConfigurationTables; // eax
  unsigned int v5; // ebx
  const struct std::nothrow_t *v6; // rdx
  PUCHAR v7; // rcx
  bool v8; // zf
  PUCHAR v10; // r15
  unsigned __int64 v11; // rdi
  UCHAR *v12; // rbx
  __int64 v13; // r8
  size_t v14; // rsi
  UCHAR *v15; // rax
  UCHAR *v16; // rdx
  PUCHAR i; // rcx
  UCHAR *v18; // rdx
  char *v19; // r9
  HKEY v20; // rcx
  int v21; // eax
  const struct std::nothrow_t *v22; // rdx
  unsigned int v23; // edi
  const struct std::nothrow_t *v24; // rdx
  const struct std::nothrow_t *v25; // rdx
  HKEY v26; // rcx
  bool v27; // zf
  __int64 v28; // rdi
  int DwordValue; // eax
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rcx
  PUCHAR v33; // rax
  int v34; // eax
  int v35; // eax
  HKEY v36; // rcx
  int HotPatchFolderMapping; // eax
  PTP_WORK *v38; // rsi
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v40; // r9
  int v41; // eax
  unsigned int v42; // esi
  unsigned int v43; // r8d
  const char *v44; // r9
  const struct std::nothrow_t *v45; // rdx
  DWORD v46; // esi
  unsigned int v47; // r8d
  const char *v48; // r9
  char v49; // bl
  PTP_WORK v50; // rax
  unsigned int v51; // ecx
  __int64 v52; // rcx
  void *v53; // rsi
  DWORD LastError; // ebx
  void *v55; // rbx
  DWORD v56; // edi
  unsigned int v57; // r8d
  const char *v58; // r9
  _WORD *v59; // rcx
  __int64 v60; // rcx
  void *v61; // rbx
  Container::Manager::Core::Details::PolicyManager *v62; // rcx
  utl::_RefCountBase *v63; // rax
  utl::_RefCountBase *v64; // rcx
  void *v65; // rcx
  const struct std::nothrow_t *v66; // rdx
  void *v67; // rcx
  int v68; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v70[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v71; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+48h] [rbp-B8h] BYREF
  PTP_WORK pwk; // [rsp+50h] [rbp-B0h] BYREF
  void *v74[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v75[8]; // [rsp+68h] [rbp-98h] BYREF
  PUCHAR v76; // [rsp+78h] [rbp-88h] BYREF
  void *v77; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v78; // [rsp+88h] [rbp-78h]
  _WORD v79[8]; // [rsp+90h] [rbp-70h] BYREF
  void *v80[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v81[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v82[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v83[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v84; // [rsp+F0h] [rbp-10h]
  char v85; // [rsp+F8h] [rbp-8h] BYREF
  PUCHAR pbInput[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v87; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(__m128i *)pbInput = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v2 = -1;
  v72 = -1;
  v87 = -1;
  v74[0] = v75;
  v74[1] = v75;
  v75[0] = 0;
  v3 = 0;
  hKey = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VelocityProxyContainerSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VelocityProxyContainerSupport>::GetImpl'::`2'::impl) )
  {
    v76 = 0;
    hKey = 0;
    v31 = RtlQueryAllInternalFeatureConfigurations(0, &v76, 0, &hKey);
    *(__m128i *)v82 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v32 = -1;
    *(_QWORD *)&v83[0] = -1;
    if ( v31 == -2147483643 )
    {
      if ( !(unsigned __int8)utl::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,utl::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>::resize(
                               v82,
                               hKey) )
      {
        v5 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
          (const char *)0x8007000ELL,
          v68);
        if ( v82[0] != (void *)-1LL )
          operator delete(v82[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_54:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
          (const char *)v5,
          v68);
        v7 = (PUCHAR)v74[0];
        v8 = v74[0] == v75;
        goto LABEL_8;
      }
      v10 = (PUCHAR)v82[0];
      v31 = RtlQueryAllInternalFeatureConfigurations(0, &v76, v82[0], &hKey);
      v32 = *(_QWORD *)&v83[0];
    }
    else
    {
      v10 = (PUCHAR)v82[0];
    }
    if ( v31 >= 0 )
    {
      v33 = (PUCHAR)v82[1];
      v72 = v32;
      v2 = (__int64)v10;
    }
    else
    {
      v5 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x63,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
             (const char *)(unsigned int)v31,
             v68);
      if ( v10 != (PUCHAR)-1LL )
        operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
      if ( (v5 & 0x80000000) != 0 )
        goto LABEL_54;
      v33 = pbInput[1];
      v10 = pbInput[0];
    }
    v76 = v33;
    v34 = Csl::HashBytes(v10, ((_DWORD)v33 - v2) & 0xFFFFFFF0);
    v5 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
        (const char *)(unsigned int)v34,
        v68);
      if ( v74[0] != v75 )
        operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
      v27 = v2 == -1;
      goto LABEL_35;
    }
    goto LABEL_40;
  }
  v72 = 0;
  utl::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,utl::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>::resize(
    pbInput,
    0);
  FeatureConfigurationTables = Container::Manager::Core::Details::_anonymous_namespace_::GetFeatureConfigurationTables(
                                 &hKey,
                                 &v72,
                                 pbInput);
  v5 = FeatureConfigurationTables;
  if ( FeatureConfigurationTables < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)(unsigned int)FeatureConfigurationTables,
      v68);
    if ( hKey )
      operator delete(hKey, v6);
    if ( v74[0] != v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    v7 = pbInput[0];
    v8 = pbInput[0] == (PUCHAR)-1LL;
LABEL_8:
    if ( v8 )
      return v5;
LABEL_9:
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return v5;
  }
  v76 = pbInput[1];
  v10 = pbInput[0];
  v11 = (pbInput[1] - pbInput[0]) & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = 0;
  v13 = v72;
  v14 = v11 + v72;
  if ( v11 + v72 )
  {
    v15 = (UCHAR *)operator new[](v11 + v72, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v15;
    if ( !v15 )
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
        (const char *)0x8007000ELL,
        v68);
      v26 = hKey;
      if ( !hKey )
      {
LABEL_32:
        if ( v74[0] != v75 )
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        v27 = v10 + 1 == 0;
LABEL_35:
        if ( v27 )
          return v5;
        v7 = v10;
        goto LABEL_9;
      }
LABEL_31:
      operator delete(v26, v25);
      goto LABEL_32;
    }
    memset_0(v15, 0, v14);
    v13 = v72;
  }
  if ( v11 )
  {
    v16 = v12;
    for ( i = v10; i != &v10[v11]; ++i )
      *v16++ = *i;
  }
  v3 = hKey;
  if ( v13 )
  {
    v18 = &v12[v11];
    v19 = (char *)hKey + v13;
    v20 = hKey;
    if ( hKey != (HKEY)((char *)hKey + v13) )
    {
      do
      {
        *v18++ = *(_BYTE *)v20;
        v20 = (HKEY)((char *)v20 + 1);
      }
      while ( v20 != (HKEY)v19 );
    }
  }
  v21 = Csl::HashBytes(v12, (int)v11 + (int)v13);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)(unsigned int)v21,
      v68);
    if ( v12 )
      operator delete(v12, v24);
LABEL_23:
    if ( v3 )
      operator delete(v3, v24);
    if ( v74[0] != v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 != (PUCHAR)-1LL )
      operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
    return v23;
  }
  if ( v12 )
    operator delete(v12, v22);
  v72 = v87;
LABEL_40:
  v28 = 0;
  v84 = 0;
  hKey = 0;
  DwordValue = Csl::OpenRegistryKey(
                 -2147483646,
                 L"SYSTEM\\CurrentControlSet\\Control\\Session Manager\\Memory Management",
                 131097,
                 &hKey);
  v5 = DwordValue;
  if ( DwordValue < 0 )
  {
    v30 = 1531;
    goto LABEL_42;
  }
  v70[0] = 0;
  DwordValue = Csl::RegistryKey::GetDwordValue((Csl::RegistryKey *)&hKey, L"HotPatchTableSize", v70);
  v5 = DwordValue;
  if ( DwordValue == -2147024894 )
  {
    v36 = hKey;
LABEL_74:
    if ( v36 )
      RegCloseKey(v36);
    goto LABEL_76;
  }
  if ( DwordValue < 0 )
  {
    v30 = 1539;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
      (const char *)(unsigned int)DwordValue,
      v68);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)v5,
      v68);
LABEL_69:
    if ( !v3 )
      goto LABEL_32;
    v26 = v3;
    goto LABEL_31;
  }
  *(_OWORD *)pbInput = 0;
  v71 = 0;
  pwk = 0;
  v68 = 16;
  v35 = NtQuerySystemInformationEx(165, &pwk, 8, pbInput);
  if ( v35 >= 0 )
  {
    v36 = hKey;
    if ( ((__int64)pbInput[0] & 1) != 0 )
    {
      LOBYTE(v70[1]) = 1;
      v28 = *(_QWORD *)v70;
      v84 = *(_QWORD *)v70;
    }
    goto LABEL_74;
  }
  v5 = wil::details::in1diag3::Return_NtStatus(
         retaddr,
         (void *)0x616,
         (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslutils.cpp",
         (const char *)(unsigned int)v35,
         16);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_68;
LABEL_76:
  LOWORD(v70[0]) = 0;
  if ( !BYTE4(v84) )
  {
LABEL_133:
    v62 = Container::Manager::Core::g_policyManager;
    v63 = qword_18021F478;
    if ( qword_18021F478 )
      _InterlockedIncrement((volatile signed __int32 *)qword_18021F478 + 2);
    *((_QWORD *)this + 2) = v62;
    v64 = (utl::_RefCountBase *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v63;
    if ( v64 )
      utl::_RefCountBase::_DecStrong(v64);
    v65 = (void *)*((_QWORD *)this + 4);
    if ( v65 != (void *)-1LL )
    {
      *((_QWORD *)this + 5) = v65;
      operator delete(v65, (const struct std::nothrow_t *)&std::nothrow);
    }
    *((_QWORD *)this + 4) = v10;
    *((_QWORD *)this + 5) = v76;
    *((_QWORD *)this + 6) = v72;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (char *)this + 56,
      v74);
    *((_WORD *)this + 76) = v70[0];
    *(_QWORD *)((char *)this + 156) = v28;
    v67 = (void *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v3;
    if ( v67 )
      operator delete(v67, v66);
    if ( v74[0] != v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  v77 = v79;
  v78 = v79;
  v79[0] = 0;
  v80[0] = v81;
  v80[1] = v81;
  v81[0] = 0;
  HotPatchFolderMapping = Container::Manager::Core::Details::PolicyManager::GetHotPatchFolderMapping(
                            Container::Manager::Core::g_policyManager,
                            (struct Path *)&v77,
                            (struct Path *)v80);
  v5 = HotPatchFolderMapping;
  if ( HotPatchFolderMapping < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
      (const char *)(unsigned int)HotPatchFolderMapping,
      v68);
LABEL_79:
    if ( v80[0] != v81 )
      operator delete(v80[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v77 != v79 )
      operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_69;
  }
  if ( v78 == v77 )
  {
    v38 = (PTP_WORK *)((char *)this + 232);
LABEL_109:
    if ( !*v38 && (*((_DWORD *)Container::Manager::Core::g_policyManager + 24) & 0x8000) != 0 )
    {
      v49 = 0;
    }
    else
    {
      v49 = 1;
      v71 = 0;
      v82[0] = (void *)-1LL;
      v82[1] = (void *)-1LL;
      v83[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v83[1] = v83[0];
      LODWORD(hKey) = Container::Manager::Core::Details::SystemConfigurationManager::RetrieveHotPatchInformation(
                        this,
                        &v71,
                        (struct Container::Manager::Common::HotPatches *)v82);
      v50 = *v38;
      pwk = *v38;
      if ( (int)hKey < 0 )
      {
        if ( v50 )
        {
          LastError = GetLastError();
          CloseThreadpoolWork(pwk);
          SetLastError(LastError);
        }
        *v38 = 0;
        v55 = (void *)*((_QWORD *)this + 30);
        if ( v55 )
        {
          v56 = GetLastError();
          if ( !CloseHandle(v55) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v57, v58);
          SetLastError(v56);
        }
        *((_QWORD *)this + 30) = 0;
        v59 = (_WORD *)*((_QWORD *)this + 31);
        *((_QWORD *)this + 32) = v59;
        *v59 = 0;
        v23 = (unsigned int)hKey;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
          (const char *)(unsigned int)hKey,
          v68);
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit((char *)v83 + 8);
        v61 = v82[0];
        if ( v82[0] != (void *)-1LL )
        {
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Common::HotPatch>>(
            v60,
            v82[0],
            ((char *)v82[1] - (char *)v82[0]) / 112);
          operator delete(v61, (const struct std::nothrow_t *)&std::nothrow);
        }
        if ( v80[0] != v81 )
          operator delete(v80[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v77 != v79 )
          operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_23;
      }
      if ( v50 )
        v51 = v82[0] != v82[1];
      else
        v51 = v71;
      *((_DWORD *)this + 41) = v51;
      *((_BYTE *)this + 168) = 1;
      *(_WORD *)((char *)this + 169) = *(_WORD *)((char *)&pwk + 5);
      *((_BYTE *)this + 171) = HIBYTE(pwk);
      utl::_OptionalData2<Container::Manager::Common::HotPatches>::_AssignVal<Container::Manager::Common::HotPatches>(
        (char *)this + 176,
        v82);
      utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit((char *)v83 + 8);
      v53 = v82[0];
      if ( v82[0] != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Container::Manager::Common::HotPatch>>(
          v52,
          v82[0],
          ((char *)v82[1] - (char *)v82[0]) / 112);
        operator delete(v53, (const struct std::nothrow_t *)&std::nothrow);
      }
    }
    LOBYTE(v70[0]) = v49;
    BYTE1(v70[0]) = 1;
    if ( v80[0] != v81 )
      operator delete(v80[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v77 != v79 )
      operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_133;
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     Container::Manager::Core::Details::SystemConfigurationManager::HotPatchesKeyListenerWork,
                     this,
                     0);
  if ( !ThreadpoolWork )
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x154,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
           v40);
    goto LABEL_79;
  }
  hKey = 0;
  v41 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &hKey,
          0);
  v42 = v41;
  if ( v41 >= 0 )
  {
    v38 = (PTP_WORK *)((char *)this + 232);
    if ( (char *)this + 232 != &v85 )
    {
      pwk = *v38;
      if ( pwk )
      {
        v46 = GetLastError();
        CloseThreadpoolWork(pwk);
        SetLastError(v46);
        v38 = (PTP_WORK *)((char *)this + 232);
      }
      *v38 = ThreadpoolWork;
      ThreadpoolWork = 0;
    }
    __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
      (char *)this + 240,
      &hKey);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (char *)this + 248,
      v80);
    if ( hKey && !CloseHandle(hKey) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v47, v48);
    if ( ThreadpoolWork )
      CloseThreadpoolWork(ThreadpoolWork);
    goto LABEL_109;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x157,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\systemconfigurationmanager.cpp",
    (const char *)(unsigned int)v41,
    v68);
  if ( hKey && !CloseHandle(hKey) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
  CloseThreadpoolWork(ThreadpoolWork);
  if ( v80[0] != v81 )
    operator delete(v80[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v77 != v79 )
    operator delete(v77, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
    operator delete(v3, v45);
  if ( v74[0] != v75 )
    operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 != (PUCHAR)-1LL )
    operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
  return v42;
}

```

## disassembly

```asm
0x1800fa4d8  push    rbp
0x1800fa4da  push    rbx
0x1800fa4db  push    rsi
0x1800fa4dc  push    rdi
0x1800fa4dd  push    r12
0x1800fa4df  push    r13
0x1800fa4e1  push    r14
0x1800fa4e3  push    r15
0x1800fa4e5  lea     rbp, [rsp-28h]
0x1800fa4ea  sub     rsp, 128h
0x1800fa4f1  mov     rax, cs:__security_cookie
0x1800fa4f8  xor     rax, rsp
0x1800fa4fb  mov     [rbp+60h+var_48], rax
0x1800fa4ff  mov     r13, rcx
0x1800fa502  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800fa50a  movdqu  xmmword ptr [rbp+60h+pbInput], xmm0
0x1800fa50f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fa513  mov     [rsp+160h+var_118], rdi
0x1800fa518  mov     [rbp+60h+var_50], rdi
0x1800fa51c  lea     rax, [rsp+160h+var_F8]
0x1800fa521  mov     [rsp+160h+var_108], rax
0x1800fa526  lea     rax, [rsp+160h+var_F8]
0x1800fa52b  mov     [rsp+160h+var_100], rax
0x1800fa530  xor     eax, eax
0x1800fa532  mov     [rsp+160h+var_F8], ax
0x1800fa537  xor     r12d, r12d
0x1800fa53a  mov     [rsp+160h+hKey], r12
0x1800fa53f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VelocityProxyContainerSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VelocityProxyContainerSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VelocityProxyContainerSupport> `wil::Feature<__WilFeatureTraits_Feature_VelocityProxyContainerSupport>::GetImpl(void)'::`2'::impl
0x1800fa546  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VelocityProxyContainerSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VelocityProxyContainerSupport>::__private_IsEnabled(void)
0x1800fa54b  lea     rsi, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fa552  test    al, al
0x1800fa554  jz      loc_1800FA7D7
0x1800fa55a  mov     [rsp+160h+var_118], r12
0x1800fa55f  xor     edx, edx
0x1800fa561  lea     rcx, [rbp+60h+pbInput]
0x1800fa565  call    ?resize@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,utl::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>::resize(unsigned __int64)
0x1800fa56a  lea     r8, [rbp+60h+pbInput]
0x1800fa56e  lea     rdx, [rsp+160h+var_118]
0x1800fa573  lea     rcx, [rsp+160h+hKey]
0x1800fa578  call    Container__Manager__Core__Details___anonymous_namespace___GetFeatureConfigurationTables
0x1800fa57d  mov     ebx, eax
0x1800fa57f  test    eax, eax
0x1800fa581  jns     short loc_1800FA5DC
0x1800fa583  mov     rcx, [rbp+68h]; this
0x1800fa587  mov     r9d, eax; char *
0x1800fa58a  mov     r8, rsi; unsigned int
0x1800fa58d  mov     edx, 0FFh; void *
0x1800fa592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa597  mov     rcx, [rsp+160h+hKey]; void *
0x1800fa59c  test    rcx, rcx
0x1800fa59f  jz      short loc_1800FA5A6
0x1800fa5a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa5a6  lea     rax, [rsp+160h+var_F8]
0x1800fa5ab  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800fa5b2  mov     rcx, [rsp+160h+var_108]; void *
0x1800fa5b7  cmp     rcx, rax
0x1800fa5ba  jz      short loc_1800FA5C4
0x1800fa5bc  mov     rdx, r14; struct std::nothrow_t *
0x1800fa5bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa5c4  mov     rcx, [rbp+60h+pbInput]; void *
0x1800fa5c8  cmp     rcx, rdi
0x1800fa5cb  jz      short loc_1800FA5D5
0x1800fa5cd  mov     rdx, r14; struct std::nothrow_t *
0x1800fa5d0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa5d5  mov     eax, ebx
0x1800fa5d7  jmp     loc_1800FAFD3
0x1800fa5dc  mov     rax, [rbp+60h+pbInput+8]
0x1800fa5e0  mov     [rsp+160h+var_E8], rax
0x1800fa5e5  mov     rdi, rax
0x1800fa5e8  mov     r15, [rbp+60h+pbInput]
0x1800fa5ec  sub     rdi, r15
0x1800fa5ef  and     rdi, 0FFFFFFFFFFFFFFF0h
0x1800fa5f3  xor     ebx, ebx
0x1800fa5f5  mov     r8, [rsp+160h+var_118]
0x1800fa5fa  lea     rsi, [rdi+r8]
0x1800fa5fe  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800fa605  test    rsi, rsi
0x1800fa608  jz      short loc_1800FA633
0x1800fa60a  mov     rdx, r14; struct std::nothrow_t *
0x1800fa60d  mov     rcx, rsi; unsigned __int64
0x1800fa610  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800fa615  mov     rbx, rax
0x1800fa618  test    rax, rax
0x1800fa61b  jz      loc_1800FA6FB
0x1800fa621  mov     r8, rsi; Size
0x1800fa624  xor     edx, edx; Val
0x1800fa626  mov     rcx, rax; void *
0x1800fa629  call    memset_0
0x1800fa62e  mov     r8, [rsp+160h+var_118]
0x1800fa633  test    rdi, rdi
0x1800fa636  jz      short loc_1800FA656
0x1800fa638  mov     rdx, rbx
0x1800fa63b  lea     r9, [r15+rdi]
0x1800fa63f  mov     rcx, r15
0x1800fa642  cmp     r15, r9
0x1800fa645  jz      short loc_1800FA656
0x1800fa647  mov     al, [rcx]
0x1800fa649  mov     [rdx], al
0x1800fa64b  inc     rdx
0x1800fa64e  inc     rcx
0x1800fa651  cmp     rcx, r9
0x1800fa654  jnz     short loc_1800FA647
0x1800fa656  mov     r12, [rsp+160h+hKey]
0x1800fa65b  test    r8, r8
0x1800fa65e  jz      short loc_1800FA67F
0x1800fa660  lea     rdx, [rbx+rdi]
0x1800fa664  lea     r9, [r8+r12]
0x1800fa668  mov     rcx, r12
0x1800fa66b  cmp     r12, r9
0x1800fa66e  jz      short loc_1800FA67F
0x1800fa670  mov     al, [rcx]
0x1800fa672  mov     [rdx], al
0x1800fa674  inc     rdx
0x1800fa677  inc     rcx
0x1800fa67a  cmp     rcx, r9
0x1800fa67d  jnz     short loc_1800FA670
0x1800fa67f  lea     edx, [rdi+r8]; cbInput
0x1800fa683  lea     r8, [rsp+160h+var_108]
0x1800fa688  mov     rcx, rbx; pbInput
0x1800fa68b  call    ?HashBytes@Csl@@YAJPEAEKAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4HashAlgorithm@1@@Z; Csl::HashBytes(uchar *,ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,Csl::HashAlgorithm)
0x1800fa690  mov     edi, eax
0x1800fa692  test    eax, eax
0x1800fa694  jns     loc_1800FA750
0x1800fa69a  mov     rcx, [rbp+68h]; this
0x1800fa69e  mov     r9d, eax; char *
0x1800fa6a1  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fa6a8  mov     edx, 126h; void *
0x1800fa6ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa6b2  test    rbx, rbx
0x1800fa6b5  jz      short loc_1800FA6BF
0x1800fa6b7  mov     rcx, rbx; void *
0x1800fa6ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa6bf  test    r12, r12
0x1800fa6c2  jz      short loc_1800FA6CC
0x1800fa6c4  mov     rcx, r12; void *
0x1800fa6c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa6cc  lea     rax, [rsp+160h+var_F8]
0x1800fa6d1  mov     rcx, [rsp+160h+var_108]; void *
0x1800fa6d6  cmp     rcx, rax
0x1800fa6d9  jz      short loc_1800FA6E3
0x1800fa6db  mov     rdx, r14; struct std::nothrow_t *
0x1800fa6de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa6e3  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800fa6e7  jz      short loc_1800FA6F4
0x1800fa6e9  mov     rdx, r14; struct std::nothrow_t *
0x1800fa6ec  mov     rcx, r15; void *
0x1800fa6ef  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa6f4  mov     eax, edi
0x1800fa6f6  jmp     loc_1800FAFD3
0x1800fa6fb  mov     rcx, [rbp+68h]; this
0x1800fa6ff  mov     ebx, 8007000Eh
0x1800fa704  mov     r9d, ebx; char *
0x1800fa707  lea     r8, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fa70e  mov     edx, 110h; void *
0x1800fa713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa718  mov     rcx, [rsp+160h+hKey]; void *
0x1800fa71d  test    rcx, rcx
0x1800fa720  jz      short loc_1800FA727
0x1800fa722  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa727  lea     rax, [rsp+160h+var_F8]
0x1800fa72c  mov     rcx, [rsp+160h+var_108]; void *
0x1800fa731  cmp     rcx, rax
0x1800fa734  jz      short loc_1800FA73E
0x1800fa736  mov     rdx, r14; struct std::nothrow_t *
0x1800fa739  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa73e  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800fa742  jz      loc_1800FA5D5
0x1800fa748  mov     rcx, r15
0x1800fa74b  jmp     loc_1800FA5CD
0x1800fa750  test    rbx, rbx
0x1800fa753  jz      short loc_1800FA75D
0x1800fa755  mov     rcx, rbx; void *
0x1800fa758  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa75d  mov     rsi, [rbp+60h+var_50]
0x1800fa761  mov     [rsp+160h+var_118], rsi
0x1800fa766  lea     rsi, aOnecoreBaseGen_59; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800fa76d  xor     edi, edi
0x1800fa76f  mov     [rbp+60h+var_70], rdi
0x1800fa773  mov     [rsp+160h+hKey], rdi
0x1800fa778  lea     r9, [rsp+160h+hKey]
0x1800fa77d  mov     r8d, 20019h
0x1800fa783  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x1800fa78a  mov     rcx, 0FFFFFFFF80000002h
0x1800fa791  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800fa796  mov     ebx, eax
0x1800fa798  test    eax, eax
0x1800fa79a  jns     loc_1800FA94F
0x1800fa7a0  mov     edx, 5FBh; void *
0x1800fa7a5  lea     r8, aOnecoreBaseGen_80; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800fa7ac  mov     r9d, eax; char *
0x1800fa7af  mov     rcx, [rbp+68h]; this
0x1800fa7b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa7b8  mov     rcx, [rsp+160h+hKey]; hKey
0x1800fa7bd  test    rcx, rcx
0x1800fa7c0  jz      loc_1800FA9FE
0x1800fa7c6  call    cs:__imp_RegCloseKey
0x1800fa7cd  nop     dword ptr [rax+rax+00h]
0x1800fa7d2  jmp     loc_1800FA9FE
0x1800fa7d7  mov     [rsp+160h+var_E8], r12
0x1800fa7dc  mov     [rsp+160h+hKey], r12
0x1800fa7e1  lea     r9, [rsp+160h+hKey]
0x1800fa7e6  xor     r8d, r8d
0x1800fa7e9  lea     rdx, [rsp+160h+var_E8]
0x1800fa7ee  xor     ecx, ecx
0x1800fa7f0  call    cs:__imp_RtlQueryAllInternalFeatureConfigurations
0x1800fa7f7  nop     dword ptr [rax+rax+00h]
0x1800fa7fc  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800fa804  movdqu  xmmword ptr [rbp+60h+var_A0], xmm0
0x1800fa809  mov     rcx, rdi
0x1800fa80c  mov     qword ptr [rbp+60h+var_90], rcx
0x1800fa810  cmp     eax, 80000005h
0x1800fa815  jnz     short loc_1800FA881
0x1800fa817  mov     rdx, [rsp+160h+hKey]
0x1800fa81c  lea     rcx, [rbp+60h+var_A0]
0x1800fa820  call    ?resize@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,utl::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>::resize(unsigned __int64)
0x1800fa825  test    al, al
0x1800fa827  jnz     short loc_1800FA85C
0x1800fa829  mov     rcx, [rbp+68h]; this
0x1800fa82d  mov     ebx, 8007000Eh
0x1800fa832  mov     r9d, ebx; char *
0x1800fa835  mov     r8, rsi; unsigned int
0x1800fa838  mov     edx, 5Bh ; '['; void *
0x1800fa83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa842  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800fa849  mov     rcx, [rbp+60h+var_A0]; void *
0x1800fa84d  cmp     rcx, rdi
0x1800fa850  jz      short loc_1800FA8BA
0x1800fa852  mov     rdx, r14; struct std::nothrow_t *
0x1800fa855  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa85a  jmp     short loc_1800FA8BA
0x1800fa85c  lea     r9, [rsp+160h+hKey]
0x1800fa861  mov     r15, [rbp+60h+var_A0]
0x1800fa865  mov     r8, r15
0x1800fa868  lea     rdx, [rsp+160h+var_E8]
0x1800fa86d  xor     ecx, ecx
0x1800fa86f  call    cs:__imp_RtlQueryAllInternalFeatureConfigurations
0x1800fa876  nop     dword ptr [rax+rax+00h]
0x1800fa87b  mov     rcx, qword ptr [rbp+60h+var_90]
0x1800fa87f  jmp     short loc_1800FA885
0x1800fa881  mov     r15, [rbp+60h+var_A0]
0x1800fa885  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800fa88c  test    eax, eax
0x1800fa88e  jns     short loc_1800FA8EA
0x1800fa890  mov     rcx, [rbp+68h]; this
0x1800fa894  mov     r9d, eax; char *
0x1800fa897  mov     r8, rsi; unsigned int
0x1800fa89a  mov     edx, 63h ; 'c'; void *
0x1800fa89f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800fa8a4  mov     ebx, eax
0x1800fa8a6  cmp     r15, rdi
0x1800fa8a9  jz      short loc_1800FA8B6
0x1800fa8ab  mov     rdx, r14; struct std::nothrow_t *
0x1800fa8ae  mov     rcx, r15; void *
0x1800fa8b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa8b6  test    ebx, ebx
0x1800fa8b8  jns     short loc_1800FA8E0
0x1800fa8ba  mov     rcx, [rbp+68h]; this
0x1800fa8be  mov     r9d, ebx; char *
0x1800fa8c1  mov     r8, rsi; unsigned int
0x1800fa8c4  mov     edx, 12Bh; void *
0x1800fa8c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa8ce  lea     rax, [rsp+160h+var_F8]
0x1800fa8d3  mov     rcx, [rsp+160h+var_108]
0x1800fa8d8  cmp     rcx, rax
0x1800fa8db  jmp     loc_1800FA5CB
0x1800fa8e0  mov     rax, [rbp+60h+pbInput+8]
0x1800fa8e4  mov     r15, [rbp+60h+pbInput]
0x1800fa8e8  jmp     short loc_1800FA8F6
0x1800fa8ea  mov     rax, [rbp+60h+var_A0+8]
0x1800fa8ee  mov     [rsp+160h+var_118], rcx
0x1800fa8f3  mov     rdi, r15
0x1800fa8f6  mov     [rsp+160h+var_E8], rax
0x1800fa8fb  mov     rdx, rax
0x1800fa8fe  sub     rdx, rdi
0x1800fa901  and     edx, 0FFFFFFF0h; cbInput
0x1800fa904  lea     r8, [rsp+160h+var_108]
0x1800fa909  mov     rcx, r15; pbInput
0x1800fa90c  call    ?HashBytes@Csl@@YAJPEAEKAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@W4HashAlgorithm@1@@Z; Csl::HashBytes(uchar *,ulong,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,Csl::HashAlgorithm)
0x1800fa911  mov     ebx, eax
0x1800fa913  test    eax, eax
0x1800fa915  jns     loc_1800FA76D
0x1800fa91b  mov     rcx, [rbp+68h]; this
0x1800fa91f  mov     r9d, eax; char *
0x1800fa922  mov     r8, rsi; unsigned int
0x1800fa925  mov     edx, 135h; void *
0x1800fa92a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa92f  lea     rax, [rsp+160h+var_F8]
0x1800fa934  mov     rcx, [rsp+160h+var_108]; void *
0x1800fa939  cmp     rcx, rax
0x1800fa93c  jz      short loc_1800FA946
0x1800fa93e  mov     rdx, r14; struct std::nothrow_t *
0x1800fa941  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800fa946  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800fa94a  jmp     loc_1800FA742
0x1800fa94f  mov     [rsp+160h+var_128], edi
0x1800fa953  lea     r8, [rsp+160h+var_128]; unsigned int *
0x1800fa958  lea     rdx, aHotpatchtables; "HotPatchTableSize"
0x1800fa95f  lea     rcx, [rsp+160h+hKey]; this
0x1800fa964  call    ?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z; Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)
0x1800fa969  mov     ebx, eax
  ... truncated ...
```
