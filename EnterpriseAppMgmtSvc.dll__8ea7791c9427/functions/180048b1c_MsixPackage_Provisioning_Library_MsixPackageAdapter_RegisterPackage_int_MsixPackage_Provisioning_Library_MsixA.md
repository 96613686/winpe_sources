# MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage(int,MsixPackage::Provisioning::Library::MsixAdapterCollection *,ushort const *)

- ea: `0x180048b1c`
- end: `0x180049613`
- name: `?RegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAVMsixAdapterCollection@234@PEBG@Z`
- size: `2807`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, struct MsixPackage::Provisioning::Library::MsixAdapterCollection *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800487bc`
- `0x18004961c`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180038d54`
- `0x180039124`
- `0x180039e9c`
- `0x180040400`
- `0x180040eb8`
- `0x180041e2c`
- `0x1800466d4`
- `0x180047338`
- `0x180048578`
- `0x180048b1c`
- `0x18004b55c`
- `0x18004bec0`
- `0x180066db2`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048ce2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048eb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048ce2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048eb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049506`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049506`
- `AppXAllUserStore!RemoveEndOfLifePackageMarkingForAllUsers` at `0x1800495a4`
- `AppXAllUserStore!RemoveEndOfLifePackageMarkingForAllUsers` at `0x1800495a4`
- `AppXAllUserStore!AddPackageToRegistryStore2` at `0x180048f8e`
- `AppXAllUserStore!AddPackageToRegistryStore2` at `0x180048f8e`
- `AppXAllUserStore!AddPackageToRegistryStore` at `0x180049326`
- `AppXAllUserStore!AddPackageToRegistryStore` at `0x180049326`
- `AppXAllUserStore!RemoveStatusOfMainPackageForAllUsers` at `0x18004939d`
- `AppXAllUserStore!RemoveStatusOfMainPackageForAllUsers` at `0x18004939d`
- `AppXAllUserStore!MarkPackageAsRequiringAllUserStoreRefresh` at `0x18004941d`
- `AppXAllUserStore!MarkPackageAsRequiringAllUserStoreRefresh` at `0x18004941d`
- `AppXAllUserStore!AddStagedPackageToRegistryStore` at `0x18004951b`
- `AppXAllUserStore!AddStagedPackageToRegistryStore` at `0x18004951b`

## string_xrefs

- `0x1800494d4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048b9c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048c58`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048c8f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048c49`: `Failed to get manifest path for package '%ws'`
- `0x180048b8d`: `Failed to create package adapter collection for adapter set.`
- `0x180049185`: `Failed to create newer version of dependency package '%ws'`
- `0x180048d96`: `Failed to obtain dependency package manifest path for package '%ws'; will retry if possible`
- `0x18004908b`: `Failed to obtain package manifest path for newer dependency package '%ws'`
- `0x180049490`: `(hr:0x%x) UpdateDependencies in the registry store failed`
- `0x1800493bc`: `Failed while removing package %ws from each user's registered packages registry store`
- `0x180048fb1`: `Failed while adding package %ws to the registered packages registry store`
- `0x180049345`: `Failed while adding package %ws to the registered packages registry store`
- `0x1800495b3`: `Failed to remove EndOfLife marking for package %ls`
- `0x18004953a`: `Failed while adding package %ws to the staged packages registry store`
- `0x1800494cd`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        int a2,
        struct MsixPackage::Provisioning::Library::MsixAdapterCollection *a3,
        const unsigned __int16 *a4)
{
  int TargetManifestPath; // ebx
  const char *v10; // rsi
  unsigned __int16 *v11; // rax
  bool v12; // zf
  _QWORD *v13; // rdx
  __int64 v14; // rbx
  unsigned int v15; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int v17; // r12d
  int v18; // edi
  const char *v19; // r14
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v20; // rdi
  unsigned int v21; // eax
  int v22; // r14d
  struct MsixPackage::Provisioning::Library::MsixProvisioningContext *v23; // rdx
  const char *v24; // r14
  char *v25; // rcx
  int v26; // r12d
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v27; // r14
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v28; // r12
  HANDLE v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  char IsEnabled; // al
  __int64 v37; // rcx
  const char *v38; // rax
  const char *v39; // rax
  char *v40; // rdx
  const char *v41; // rdi
  unsigned int v42; // eax
  int updated; // eax
  int v44; // eax
  void *v45; // rdi
  int v46; // eax
  char *v47; // rcx
  unsigned int v48; // eax
  char *v49; // [rsp+28h] [rbp-91h]
  unsigned __int16 **v50; // [rsp+40h] [rbp-79h] BYREF
  char v51; // [rsp+48h] [rbp-71h]
  unsigned int v52; // [rsp+50h] [rbp-69h]
  __int64 v53; // [rsp+58h] [rbp-61h] BYREF
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v54; // [rsp+60h] [rbp-59h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v55; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v56; // [rsp+70h] [rbp-49h] BYREF
  __int64 v57; // [rsp+78h] [rbp-41h]
  unsigned __int16 *v58[2]; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v59; // [rsp+90h] [rbp-29h]
  struct AppxAllUserStore::_PackageInfo **v60; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v61; // [rsp+A0h] [rbp-19h]
  int v62; // [rsp+A4h] [rbp-15h]
  int v63; // [rsp+B4h] [rbp-5h]
  int v64; // [rsp+DCh] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  LPVOID pv; // [rsp+120h] [rbp+67h] BYREF
  struct MsixPackage::Provisioning::Library::MsixAdapterCollection *v67; // [rsp+130h] [rbp+77h]

  v67 = a3;
  if ( *((_DWORD *)this + 6) == 3 )
    return 0;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  v63 = 0;
  memset_0(&v60, 0, 0x48u);
  v53 = 0;
  TargetManifestPath = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Make(&v53);
  if ( TargetManifestPath < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)TargetManifestPath,
      (int)"Failed to create package adapter collection for adapter set.",
      v49);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    return (unsigned int)TargetManifestPath;
  }
  v10 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v11 = (unsigned __int16 *)((char *)this + 48);
  else
    v11 = *(unsigned __int16 **)v10;
  v58[0] = v11;
  v61 = 0;
  v60 = 0;
  v59 = a4;
  v64 = *(_DWORD *)(*((_QWORD *)this + 2) + 672LL);
  v50 = v58;
  v51 = 1;
  if ( (*((_DWORD *)this + 9) & 0xFFFFFFFA) != 0 || (v12 = *((_DWORD *)this + 9) == 5, v62 = a2, v12) )
    v62 = 0;
  TargetManifestPath = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
                         this,
                         (const unsigned __int16 **)&v58[1]);
  if ( TargetManifestPath < 0 )
  {
    if ( *((_QWORD *)this + 9) >= 8u )
      v10 = *(const char **)v10;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)TargetManifestPath,
      (int)"Failed to get manifest path for package '%ws'",
      v10);
    wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    return (unsigned int)TargetManifestPath;
  }
  v14 = v53;
  if ( !a3 || (*((_DWORD *)this + 9) & 0xFFFFFFFA) != 0 || *((_DWORD *)this + 9) == 5 )
  {
LABEL_54:
    v32 = *((_DWORD *)this + 9);
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( !v34 || (v35 = v34 - 1) == 0 )
        {
LABEL_142:
          v18 = AddStagedPackageToRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v58);
          if ( v18 < 0 )
          {
            if ( *((_QWORD *)this + 9) >= 8u )
              v10 = *(const char **)v10;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x282,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v18,
              (int)"Failed while adding package %ws to the staged packages registry store",
              v10);
            wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            return (unsigned int)v18;
          }
          goto LABEL_148;
        }
        if ( v35 != 1 )
        {
LABEL_148:
          if ( *(_DWORD *)(*((_QWORD *)this + 2) + 600LL) && (*((_DWORD *)this + 9) & 0xFFFFFFFB) == 0 )
          {
            if ( *((_QWORD *)this + 9) < 8u )
            {
              v47 = (char *)this + 48;
            }
            else
            {
              v47 = *(char **)v10;
              v10 = *(const char **)v10;
            }
            v48 = RemoveEndOfLifePackageMarkingForAllUsers(v47, v13);
            wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x28E,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)v48,
              (int)"Failed to remove EndOfLife marking for package %ls",
              v10);
          }
          *((_DWORD *)this + 6) = 3;
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return 0;
        }
      }
    }
    if ( *((_DWORD *)this + 66) || !*(_DWORD *)(*((_QWORD *)this + 26) + 160LL) || *((_DWORD *)this + 9) == 1 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::GetImpl'::`2'::impl);
      v37 = *((_QWORD *)this + 2);
      if ( IsEnabled )
      {
        v18 = AddPackageToRegistryStore2(*(_QWORD *)(v37 + 584), v58, *(_QWORD *)(v37 + 680));
        if ( v18 < 0 )
        {
          if ( *((_QWORD *)this + 9) >= 8u )
            v10 = *(const char **)v10;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v18,
            (int)"Failed while adding package %ws to the registered packages registry store",
            v10);
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return (unsigned int)v18;
        }
      }
      else
      {
        v18 = AddPackageToRegistryStore(*(_QWORD *)(v37 + 584), v58);
        if ( v18 < 0 )
        {
          if ( *((_QWORD *)this + 9) >= 8u )
            v10 = *(const char **)v10;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x24A,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v18,
            (int)"Failed while adding package %ws to the registered packages registry store",
            v10);
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          return (unsigned int)v18;
        }
      }
      if ( *((_QWORD *)this + 9) < 8u )
        v40 = (char *)this + 48;
      else
        v40 = *(char **)v10;
      v18 = RemoveStatusOfMainPackageForAllUsers(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v40);
      if ( v18 < 0 )
      {
        if ( *((_QWORD *)this + 9) >= 8u )
          v10 = *(const char **)v10;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x253,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v18,
          (int)"Failed while removing package %ws from each user's registered packages registry store",
          v10);
        wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        return (unsigned int)v18;
      }
      if ( *((_QWORD *)this + 9) < 8u )
        v41 = (char *)this + 48;
      else
        v41 = *(const char **)v10;
      v42 = MarkPackageAsRequiringAllUserStoreRefresh(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL));
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)v42,
        (int)"Failed to mark package %ls as requiring all user store refresh",
        v41);
      if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 600LL) )
      {
        if ( v60 )
        {
          if ( v61 )
          {
            updated = MsixPackage::Provisioning::Library::MsixPackageAdapter::UpdateDependencies(this, v60, v61);
            if ( updated < 0 )
            {
              pv = 0;
              v44 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      (char *)&pv,
                      L"(hr:0x%x) UpdateDependencies in the registry store failed",
                      (unsigned int)updated);
              if ( v44 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x26D,
                  (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v44);
              v45 = pv;
              v46 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
                      pv,
                      L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                      L"MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage",
                      630);
              if ( v46 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x276,
                  (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v46);
              if ( v45 )
                CoTaskMemFree(v45);
            }
          }
        }
      }
    }
    goto LABEL_142;
  }
  v57 = (__int64)(*((_QWORD *)a3 + 3) - *((_QWORD *)a3 + 2)) >> 3;
  v15 = v57;
  ProcessHeap = GetProcessHeap();
  v60 = (struct AppxAllUserStore::_PackageInfo **)HeapAlloc(ProcessHeap, 8u, 8LL * v15);
  if ( !v60 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)0x8007000ELL,
      (int)"Failed to allocate memory for dependencyPackageInfo array",
      v49);
    wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
    if ( !v14 )
      return 2147942414LL;
LABEL_100:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    return 2147942414LL;
  }
  v17 = 0;
  v52 = 0;
  if ( !v15 )
  {
LABEL_53:
    v61 = v17;
    goto LABEL_54;
  }
  while ( 1 )
  {
    v56 = 0;
    v55 = 0;
    v18 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
            v67,
            v17,
            &v55);
    if ( v18 < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v10 = *(const char **)v10;
      LODWORD(v49) = v17;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v18,
        (int)"Failed to obtain dependency package %d for package '%ws'",
        v49,
        v10);
      if ( v55 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v55 + 16LL))(v55);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)v18;
    }
    if ( *((_QWORD *)this + 9) < 8u )
      v19 = (char *)this + 48;
    else
      v19 = *(const char **)v10;
    v20 = v55;
    v21 = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
            v55,
            (const unsigned __int16 **)&v56);
    v22 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x1F5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)v21,
            (int)"Failed to obtain dependency package manifest path for package '%ws'; will retry if possible",
            v19);
    if ( v22 != -2147023728 )
    {
      if ( v22 < 0 )
        break;
      goto LABEL_47;
    }
    v23 = (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)*((_QWORD *)this + 2);
    if ( !*((_DWORD *)v23 + 150) || *((_DWORD *)v20 + 6) != 3 )
      break;
    LOBYTE(pv) = 0;
    v54 = 0;
    v24 = (char *)v20 + 48;
    if ( *((_QWORD *)v20 + 9) < 8u )
      v25 = (char *)v20 + 48;
    else
      v25 = *(char **)v24;
    v26 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(
            v25,
            v23,
            (bool *)&pv,
            &v54);
    if ( v26 < 0 )
    {
      if ( *((_QWORD *)v20 + 9) >= 8u )
        v24 = *(const char **)v24;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v26,
        (int)"Failed to create newer version of dependency package '%ws'",
        v24);
      if ( v54 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v54 + 16LL))(v54);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)v26;
    }
    if ( !(_BYTE)pv )
    {
      if ( *((_QWORD *)v20 + 9) >= 8u )
        v24 = *(const char **)v24;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x20A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Failed to find expected higher version of dependency '%ws' on retry",
        v24);
      if ( v54 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v54 + 16LL))(v54);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return 2147549183LL;
    }
    v27 = v54;
    v26 = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
            v54,
            (const unsigned __int16 **)&v56);
    if ( v26 < 0 )
    {
      v39 = (char *)v27 + 48;
      if ( *((_QWORD *)v27 + 9) >= 8u )
        v39 = *(const char **)v39;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v26,
        (int)"Failed to obtain package manifest path for newer dependency package '%ws'",
        v39);
      if ( v27 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)v26;
    }
    v28 = v20;
    v20 = v27;
    v55 = v27;
    if ( v27 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 8LL))(v27);
    if ( v28 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v28 + 16LL))(v28);
    v26 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
            v14,
            v27);
    if ( v26 < 0 )
    {
      v38 = (char *)v27 + 48;
      if ( *((_QWORD *)v27 + 9) >= 8u )
        v38 = *(const char **)v38;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x218,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v26,
        (int)"Failed to add newer dependency package '%ws' to collection of new dependencies",
        v38);
      if ( v27 )
      {
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)v26;
    }
    if ( v27 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
    v17 = v52;
LABEL_47:
    v29 = GetProcessHeap();
    v30 = HeapAlloc(v29, 8u, 0x18u);
    v13 = v30;
    if ( !v30 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)0x8007000ELL,
        (int)"Failed to allocate memory for packageInfo object",
        v49);
      if ( v20 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
      if ( !v14 )
        return 2147942414LL;
      goto LABEL_100;
    }
    v31 = (_QWORD *)((char *)v20 + 48);
    if ( *((_QWORD *)v20 + 9) >= 8u )
      v31 = (_QWORD *)*v31;
    *v30 = v31;
    v30[1] = v56;
    v60[v17] = (struct AppxAllUserStore::_PackageInfo *)v30;
    if ( v20 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
    v52 = ++v17;
    if ( v17 >= (unsigned int)v57 )
      goto LABEL_53;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x21C,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v22,
    (int)"Retrying was not applicable",
    v49);
  if ( v20 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v20 + 16LL))(v20);
  wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v50);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180048b1c  mov     [rsp-8+arg_8], rbx
0x180048b21  mov     [rsp-8+arg_10], r8
0x180048b26  push    rbp
0x180048b27  push    rsi
0x180048b28  push    rdi
0x180048b29  push    r12
0x180048b2b  push    r13
0x180048b2d  push    r14
0x180048b2f  push    r15
0x180048b31  lea     rbp, [rsp-27h]
0x180048b36  sub     rsp, 0E0h
0x180048b3d  mov     r14, r9
0x180048b40  mov     r12, r8
0x180048b43  mov     edi, edx
0x180048b45  mov     r13, rcx
0x180048b48  cmp     dword ptr [rcx+18h], 3
0x180048b4c  jz      loc_1800495F6
0x180048b52  xorps   xmm0, xmm0
0x180048b55  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x180048b5a  xor     r15d, r15d
0x180048b5d  mov     [rbp+57h+var_80], r15
0x180048b61  xor     eax, eax
0x180048b63  mov     [rbp+57h+var_5C], eax
0x180048b66  xor     edx, edx; Val
0x180048b68  lea     r8d, [r15+48h]; Size
0x180048b6c  lea     rcx, [rbp+57h+var_78]; void *
0x180048b70  call    memset_0
0x180048b75  nop
0x180048b76  mov     [rbp+57h+var_B8], r15
0x180048b7a  lea     rcx, [rbp+57h+var_B8]
0x180048b7e  call    ?Make@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@SAJPEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Make(MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x180048b83  mov     ebx, eax
0x180048b85  test    eax, eax
0x180048b87  jns     short loc_180048BCB
0x180048b89  mov     rcx, [rbp+5Fh]; this
0x180048b8d  lea     rax, aFailedToCreate_17; "Failed to create package adapter collec"...
0x180048b94  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180048b99  mov     r9d, ebx; char *
0x180048b9c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048ba3  mov     edx, 1B7h; void *
0x180048ba8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048bad  nop
0x180048bae  mov     rcx, [rbp+57h+var_B8]
0x180048bb2  test    rcx, rcx
0x180048bb5  jz      short loc_180048BC4
0x180048bb7  mov     rax, [rcx]
0x180048bba  mov     rax, [rax+10h]
0x180048bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bc3  nop
0x180048bc4  mov     eax, ebx
0x180048bc6  jmp     loc_1800495F8
0x180048bcb  lea     rsi, [r13+30h]
0x180048bcf  cmp     qword ptr [rsi+18h], 8
0x180048bd4  jb      short loc_180048BDB
0x180048bd6  mov     rax, [rsi]
0x180048bd9  jmp     short loc_180048BDE
0x180048bdb  mov     rax, rsi
0x180048bde  mov     [rbp+57h+var_90], rax
0x180048be2  mov     [rbp+57h+var_70], r15d
0x180048be6  mov     [rbp+57h+var_78], r15
0x180048bea  mov     [rbp+57h+var_80], r14
0x180048bee  mov     rax, [r13+10h]
0x180048bf2  mov     ecx, [rax+2A0h]
0x180048bf8  mov     [rbp+57h+var_34], ecx
0x180048bfb  lea     rax, [rbp+57h+var_90]
0x180048bff  mov     [rbp+57h+var_D0], rax
0x180048c03  mov     [rbp+57h+var_C8], 1
0x180048c07  mov     r14d, 0FFFFFFFAh
0x180048c0d  test    [r13+24h], r14d
0x180048c11  jnz     short loc_180048C1D
0x180048c13  cmp     dword ptr [r13+24h], 5
0x180048c18  mov     [rbp+57h+var_6C], edi
0x180048c1b  jnz     short loc_180048C24
0x180048c1d  mov     [rbp+57h+var_6C], 0
0x180048c24  lea     rdx, [rbp+57h+var_90+8]; unsigned __int16 **
0x180048c28  mov     rcx, r13; this
0x180048c2b  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x180048c30  mov     ebx, eax
0x180048c32  test    eax, eax
0x180048c34  jns     short loc_180048C8F
0x180048c36  cmp     qword ptr [rsi+18h], 8
0x180048c3b  jb      short loc_180048C40
0x180048c3d  mov     rsi, [rsi]
0x180048c40  mov     rcx, [rbp+5Fh]; this
0x180048c44  mov     [rsp+110h+var_E8], rsi; char *
0x180048c49  lea     rax, aFailedToGetMan_0; "Failed to get manifest path for package"...
0x180048c50  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180048c55  mov     r9d, ebx; char *
0x180048c58  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048c5f  mov     edx, 1D5h; void *
0x180048c64  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048c69  nop
0x180048c6a  lea     rcx, [rbp+57h+var_D0]
0x180048c6e  call    wil__details__ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f______ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___
0x180048c73  nop
0x180048c74  mov     rcx, [rbp+57h+var_B8]
0x180048c78  test    rcx, rcx
0x180048c7b  jz      short loc_180048C8A
0x180048c7d  mov     rax, [rcx]
0x180048c80  mov     rax, [rax+10h]
0x180048c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c89  nop
0x180048c8a  jmp     loc_180048BC4
0x180048c8f  lea     r15, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048c96  mov     rbx, [rbp+57h+var_B8]
0x180048c9a  test    r12, r12
0x180048c9d  jz      loc_180048F17
0x180048ca3  test    [r13+24h], r14d
0x180048ca7  jnz     loc_180048F17
0x180048cad  cmp     dword ptr [r13+24h], 5
0x180048cb2  jz      loc_180048F17
0x180048cb8  mov     r14, [r12+18h]
0x180048cbd  sub     r14, [r12+10h]
0x180048cc2  sar     r14, 3
0x180048cc6  mov     [rbp+57h+var_98], r14
0x180048cca  mov     edi, r14d
0x180048ccd  shl     rdi, 3
0x180048cd1  call    cs:__imp_GetProcessHeap
0x180048cd7  mov     rcx, rax; hHeap
0x180048cda  mov     r8, rdi; dwBytes
0x180048cdd  mov     edx, 8; dwFlags
0x180048ce2  call    cs:__imp_HeapAlloc
0x180048ce8  mov     [rbp+57h+var_78], rax
0x180048cec  test    rax, rax
0x180048cef  jnz     short loc_180048D34
0x180048cf1  mov     rcx, [rbp+5Fh]; this
0x180048cf5  lea     rax, aFailedToAlloca; "Failed to allocate memory for dependenc"...
0x180048cfc  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180048d01  mov     r9d, 8007000Eh; char *
0x180048d07  mov     r8, r15; unsigned int
0x180048d0a  mov     edx, 1E6h; void *
0x180048d0f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048d14  nop
0x180048d15  lea     rcx, [rbp+57h+var_D0]
0x180048d19  call    wil__details__ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f______ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___
0x180048d1e  nop
0x180048d1f  test    rbx, rbx
0x180048d22  jz      loc_180049247
0x180048d28  mov     rax, [rbx]
0x180048d2b  mov     rax, [rax+10h]
0x180048d2f  jmp     loc_18004923E
0x180048d34  xor     r12d, r12d
0x180048d37  mov     [rbp+57h+var_C0], r12d
0x180048d3b  test    r14d, r14d
0x180048d3e  jz      loc_180048F13
0x180048d44  mov     [rbp+57h+var_A0], 0
0x180048d4c  mov     [rbp+57h+var_A8], 0
0x180048d54  lea     r8, [rbp+57h+var_A8]
0x180048d58  mov     edx, r12d
0x180048d5b  mov     rcx, [rbp+57h+arg_10]
0x180048d5f  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180048d64  mov     edi, eax
0x180048d66  test    eax, eax
0x180048d68  js      loc_1800492AE
0x180048d6e  cmp     qword ptr [rsi+18h], 8
0x180048d73  jb      short loc_180048D7A
0x180048d75  mov     r14, [rsi]
0x180048d78  jmp     short loc_180048D7D
0x180048d7a  mov     r14, rsi
0x180048d7d  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x180048d81  mov     rdi, [rbp+57h+var_A8]
0x180048d85  mov     rcx, rdi; this
0x180048d88  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x180048d8d  mov     rcx, [rbp+5Fh]; this
0x180048d91  mov     [rsp+110h+var_E8], r14; char *
0x180048d96  lea     rdx, aFailedToObtain_1; "Failed to obtain dependency package man"...
0x180048d9d  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x180048da2  mov     r9d, eax; char *
0x180048da5  mov     r8, r15; unsigned int
0x180048da8  mov     edx, 1F5h; void *
0x180048dad  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048db2  mov     r14d, eax
0x180048db5  cmp     eax, 80070490h
0x180048dba  jnz     loc_180048E9C
0x180048dc0  mov     rdx, [r13+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x180048dc4  cmp     dword ptr [rdx+258h], 0
0x180048dcb  jz      loc_180049251
0x180048dd1  cmp     dword ptr [rdi+18h], 3
0x180048dd5  jnz     loc_180049251
0x180048ddb  mov     byte ptr [rbp+57h+pv], 0
0x180048ddf  mov     [rbp+57h+var_B0], 0
0x180048de7  lea     r14, [rdi+30h]
0x180048deb  cmp     qword ptr [r14+18h], 8
0x180048df0  jb      short loc_180048DF7
0x180048df2  mov     rcx, [r14]
0x180048df5  jmp     short loc_180048DFA
0x180048df7  mov     rcx, r14; char *
0x180048dfa  lea     r9, [rbp+57h+var_B0]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x180048dfe  lea     r8, [rbp+57h+pv]; bool *
0x180048e02  call    ?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180048e07  mov     r12d, eax
0x180048e0a  test    eax, eax
0x180048e0c  js      loc_180049172
0x180048e12  cmp     byte ptr [rbp+57h+pv], 0
0x180048e16  jz      loc_1800490F1
0x180048e1c  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x180048e20  mov     r14, [rbp+57h+var_B0]
0x180048e24  mov     rcx, r14; this
0x180048e27  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x180048e2c  mov     r12d, eax
0x180048e2f  test    eax, eax
0x180048e31  js      loc_180049074
0x180048e37  mov     r12, rdi
0x180048e3a  mov     rdi, r14
0x180048e3d  mov     [rbp+57h+var_A8], r14
0x180048e41  test    r14, r14
0x180048e44  jz      short loc_180048E55
0x180048e46  mov     rax, [r14]
0x180048e49  mov     rcx, r14
0x180048e4c  mov     rax, [rax+8]
0x180048e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e55  test    r12, r12
0x180048e58  jz      short loc_180048E6B
0x180048e5a  mov     rax, [r12]
0x180048e5e  mov     rcx, r12
0x180048e61  mov     rax, [rax+10h]
0x180048e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e6a  nop
0x180048e6b  mov     rdx, r14
0x180048e6e  mov     rcx, rbx
0x180048e71  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x180048e76  mov     r12d, eax
0x180048e79  test    eax, eax
0x180048e7b  js      loc_180048FF2
0x180048e81  test    r14, r14
0x180048e84  jz      short loc_180048E96
0x180048e86  mov     rax, [r14]
0x180048e89  mov     rcx, r14
0x180048e8c  mov     rax, [rax+10h]
0x180048e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e95  nop
0x180048e96  mov     r12d, [rbp+57h+var_C0]
0x180048e9a  jmp     short loc_180048EA5
0x180048e9c  test    r14d, r14d
0x180048e9f  js      loc_180049251
0x180048ea5  call    cs:__imp_GetProcessHeap
0x180048eab  mov     rcx, rax; hHeap
0x180048eae  mov     edx, 8; dwFlags
0x180048eb3  lea     r8d, [rdx+10h]; dwBytes
0x180048eb7  call    cs:__imp_HeapAlloc
0x180048ebd  mov     rdx, rax
0x180048ec0  test    rax, rax
0x180048ec3  jz      loc_1800491EF
0x180048ec9  lea     rcx, [rdi+30h]
0x180048ecd  cmp     qword ptr [rcx+18h], 8
0x180048ed2  jb      short loc_180048ED7
0x180048ed4  mov     rcx, [rcx]
0x180048ed7  mov     [rax], rcx
0x180048eda  mov     rax, [rbp+57h+var_A0]
0x180048ede  mov     [rdx+8], rax
0x180048ee2  mov     ecx, r12d
0x180048ee5  mov     rax, [rbp+57h+var_78]
0x180048ee9  mov     [rax+rcx*8], rdx
0x180048eed  test    rdi, rdi
0x180048ef0  jz      short loc_180048F02
0x180048ef2  mov     rax, [rdi]
0x180048ef5  mov     rcx, rdi
0x180048ef8  mov     rax, [rax+10h]
0x180048efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f01  nop
0x180048f02  inc     r12d
0x180048f05  mov     [rbp+57h+var_C0], r12d
0x180048f09  cmp     r12d, dword ptr [rbp+57h+var_98]
0x180048f0d  jb      loc_180048D44
0x180048f13  mov     [rbp+57h+var_70], r12d
0x180048f17  mov     ecx, [r13+24h]
0x180048f1b  test    ecx, ecx
0x180048f1d  jz      short loc_180048F3F
0x180048f1f  sub     ecx, 1
0x180048f22  jz      short loc_180048F3F
0x180048f24  sub     ecx, 1
0x180048f27  jz      loc_18004950C
0x180048f2d  sub     ecx, 1
0x180048f30  jz      loc_18004950C
0x180048f36  cmp     ecx, 1
0x180048f39  jnz     loc_18004957B
0x180048f3f  cmp     dword ptr [r13+108h], 0
0x180048f47  jnz     short loc_180048F64
0x180048f49  mov     rax, [r13+0D0h]
0x180048f50  cmp     dword ptr [rax+0A0h], 0
0x180048f57  jz      short loc_180048F64
0x180048f59  cmp     dword ptr [r13+24h], 1
0x180048f5e  jnz     loc_18004950C
0x180048f64  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore> `wil::Feature<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::GetImpl(void)'::`2'::impl
0x180048f6b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::__private_IsEnabled(void)
0x180048f70  mov     rcx, [r13+10h]
0x180048f74  lea     rdx, [rbp+57h+var_90]
0x180048f78  test    al, al
0x180048f7a  jz      loc_18004931F
0x180048f80  mov     r8, [rcx+2A8h]
0x180048f87  mov     rcx, [rcx+248h]
0x180048f8e  call    cs:__imp_AddPackageToRegistryStore2
0x180048f94  mov     edi, eax
0x180048f96  test    eax, eax
0x180048f98  jns     loc_180049383
0x180048f9e  cmp     qword ptr [rsi+18h], 8
0x180048fa3  jb      short loc_180048FA8
0x180048fa5  mov     rsi, [rsi]
0x180048fa8  mov     rcx, [rbp+5Fh]; this
0x180048fac  mov     [rsp+110h+var_E8], rsi; char *
  ... truncated ...
```
