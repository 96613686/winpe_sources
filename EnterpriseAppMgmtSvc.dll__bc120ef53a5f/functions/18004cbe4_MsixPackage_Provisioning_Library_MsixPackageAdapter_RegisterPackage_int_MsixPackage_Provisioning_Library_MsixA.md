# MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage(int,MsixPackage::Provisioning::Library::MsixAdapterCollection *,ushort const *)

- ea: `0x18004cbe4`
- end: `0x18004d71e`
- name: `?RegisterPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJHPEAVMsixAdapterCollection@234@PEBG@Z`
- size: `2874`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, struct MsixPackage::Provisioning::Library::MsixAdapterCollection *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c884`
- `0x18004d724`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003c2c0`
- `0x18003c6d4`
- `0x18003d4ec`
- `0x180043fb4`
- `0x180044ae8`
- `0x180045b3c`
- `0x18004a6c4`
- `0x18004b384`
- `0x18004c62c`
- `0x18004cbe4`
- `0x18004f760`
- `0x18005011c`
- `0x18006c8d2`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cdb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cf91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cdb0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cf91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cd99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cf79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cd99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cf79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d5fe`
- `AppXAllUserStore!RemoveEndOfLifePackageMarkingForAllUsers` at `0x18004d6a8`
- `AppXAllUserStore!RemoveEndOfLifePackageMarkingForAllUsers` at `0x18004d6a8`
- `AppXAllUserStore!AddPackageToRegistryStore2` at `0x18004d06e`
- `AppXAllUserStore!AddPackageToRegistryStore2` at `0x18004d06e`
- `AppXAllUserStore!AddPackageToRegistryStore` at `0x18004d40c`
- `AppXAllUserStore!AddPackageToRegistryStore` at `0x18004d40c`
- `AppXAllUserStore!RemoveStatusOfMainPackageForAllUsers` at `0x18004d489`
- `AppXAllUserStore!RemoveStatusOfMainPackageForAllUsers` at `0x18004d489`
- `AppXAllUserStore!MarkPackageAsRequiringAllUserStoreRefresh` at `0x18004d50f`
- `AppXAllUserStore!MarkPackageAsRequiringAllUserStoreRefresh` at `0x18004d50f`
- `AppXAllUserStore!AddStagedPackageToRegistryStore` at `0x18004d619`
- `AppXAllUserStore!AddStagedPackageToRegistryStore` at `0x18004d619`

## string_xrefs

- `0x18004cc64`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004cd20`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004cd57`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004d5cc`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004cc55`: `Failed to create package adapter collection for adapter set.`
- `0x18004ce6a`: `Failed to obtain dependency package manifest path for package '%ws'; will retry if possible`
- `0x18004cd11`: `Failed to get manifest path for package '%ws'`
- `0x18004d171`: `Failed to obtain package manifest path for newer dependency package '%ws'`
- `0x18004d26b`: `Failed to create newer version of dependency package '%ws'`
- `0x18004d4ae`: `Failed while removing package %ws from each user's registered packages registry store`
- `0x18004d097`: `Failed while adding package %ws to the registered packages registry store`
- `0x18004d431`: `Failed while adding package %ws to the registered packages registry store`
- `0x18004d63e`: `Failed while adding package %ws to the staged packages registry store`
- `0x18004d5c5`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage`
- `0x18004d588`: `(hr:0x%x) UpdateDependencies in the registry store failed`
- `0x18004d6bd`: `Failed to remove EndOfLife marking for package %ls`

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
  __int64 v13; // rbx
  unsigned int v14; // r14d
  HANDLE ProcessHeap; // rax
  unsigned int v16; // r12d
  int v17; // edi
  const char *v18; // r14
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v19; // rdi
  unsigned int v20; // eax
  int v21; // r14d
  struct MsixPackage::Provisioning::Library::MsixProvisioningContext *v22; // rdx
  const char *v23; // r14
  char *v24; // rcx
  int v25; // r12d
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v26; // r14
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v27; // r12
  HANDLE v28; // rax
  struct AppxAllUserStore::_PackageInfo *v29; // rax
  _QWORD *v30; // rcx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  char IsEnabled; // al
  __int64 v36; // rcx
  const char *v37; // rax
  const char *v38; // rax
  char *v39; // rdx
  const char *v40; // rdi
  unsigned int v41; // eax
  int updated; // eax
  int v43; // eax
  void *v44; // rdi
  int v45; // eax
  unsigned int v46; // eax
  int v47; // [rsp+20h] [rbp-99h]
  char *v48; // [rsp+28h] [rbp-91h]
  unsigned __int16 **v49; // [rsp+40h] [rbp-79h] BYREF
  char v50; // [rsp+48h] [rbp-71h]
  unsigned int v51; // [rsp+50h] [rbp-69h]
  __int64 v52; // [rsp+58h] [rbp-61h] BYREF
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v53; // [rsp+60h] [rbp-59h] BYREF
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v54; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v55; // [rsp+70h] [rbp-49h] BYREF
  __int64 v56; // [rsp+78h] [rbp-41h]
  unsigned __int16 *v57[2]; // [rsp+80h] [rbp-39h] BYREF
  const unsigned __int16 *v58; // [rsp+90h] [rbp-29h]
  struct AppxAllUserStore::_PackageInfo **v59; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v60; // [rsp+A0h] [rbp-19h]
  int v61; // [rsp+A4h] [rbp-15h]
  int v62; // [rsp+B4h] [rbp-5h]
  int v63; // [rsp+DCh] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  LPVOID pv; // [rsp+120h] [rbp+67h] BYREF
  struct MsixPackage::Provisioning::Library::MsixAdapterCollection *v66; // [rsp+130h] [rbp+77h]

  v66 = a3;
  if ( *((_DWORD *)this + 6) == 3 )
    return 0;
  *(_OWORD *)v57 = 0;
  v58 = 0;
  v62 = 0;
  memset_0(&v59, 0, 0x48u);
  v52 = 0;
  TargetManifestPath = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Make(&v52);
  if ( TargetManifestPath < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)TargetManifestPath,
      (int)"Failed to create package adapter collection for adapter set.",
      v48);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    return (unsigned int)TargetManifestPath;
  }
  v10 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v11 = (unsigned __int16 *)((char *)this + 48);
  else
    v11 = *(unsigned __int16 **)v10;
  v57[0] = v11;
  v60 = 0;
  v59 = 0;
  v58 = a4;
  v63 = *(_DWORD *)(*((_QWORD *)this + 2) + 672LL);
  v49 = v57;
  v50 = 1;
  if ( (*((_DWORD *)this + 9) & 0xFFFFFFFA) != 0 || (v12 = *((_DWORD *)this + 9) == 5, v61 = a2, v12) )
    v61 = 0;
  TargetManifestPath = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
                         this,
                         (const unsigned __int16 **)&v57[1]);
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
    wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    return (unsigned int)TargetManifestPath;
  }
  v13 = v52;
  if ( !a3 || (*((_DWORD *)this + 9) & 0xFFFFFFFA) != 0 || *((_DWORD *)this + 9) == 5 )
  {
LABEL_54:
    v31 = *((_DWORD *)this + 9);
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( !v33 || (v34 = v33 - 1) == 0 )
        {
LABEL_142:
          v17 = AddStagedPackageToRegistryStore(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v57);
          if ( v17 < 0 )
          {
            if ( *((_QWORD *)this + 9) >= 8u )
              v10 = *(const char **)v10;
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x282,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)(unsigned int)v17,
              (int)"Failed while adding package %ws to the staged packages registry store",
              v10);
            wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
            if ( v13 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
            return (unsigned int)v17;
          }
          goto LABEL_148;
        }
        if ( v34 != 1 )
        {
LABEL_148:
          if ( *(_DWORD *)(*((_QWORD *)this + 2) + 600LL) && (*((_DWORD *)this + 9) & 0xFFFFFFFB) == 0 )
          {
            if ( *((_QWORD *)this + 9) >= 8u )
              v10 = *(const char **)v10;
            v46 = RemoveEndOfLifePackageMarkingForAllUsers();
            wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x28E,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              (const char *)v46,
              (int)"Failed to remove EndOfLife marking for package %ls",
              v10);
          }
          *((_DWORD *)this + 6) = 3;
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          return 0;
        }
      }
    }
    if ( *((_DWORD *)this + 66) || !*(_DWORD *)(*((_QWORD *)this + 26) + 160LL) || *((_DWORD *)this + 9) == 1 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::GetImpl'::`2'::impl);
      v36 = *((_QWORD *)this + 2);
      if ( IsEnabled )
      {
        v17 = AddPackageToRegistryStore2(*(_QWORD *)(v36 + 584), v57, *(_QWORD *)(v36 + 680));
        if ( v17 < 0 )
        {
          if ( *((_QWORD *)this + 9) >= 8u )
            v10 = *(const char **)v10;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x240,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v17,
            (int)"Failed while adding package %ws to the registered packages registry store",
            v10);
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          return (unsigned int)v17;
        }
      }
      else
      {
        v17 = AddPackageToRegistryStore(*(_QWORD *)(v36 + 584), v57);
        if ( v17 < 0 )
        {
          if ( *((_QWORD *)this + 9) >= 8u )
            v10 = *(const char **)v10;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x24A,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v17,
            (int)"Failed while adding package %ws to the registered packages registry store",
            v10);
          wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          return (unsigned int)v17;
        }
      }
      if ( *((_QWORD *)this + 9) < 8u )
        v39 = (char *)this + 48;
      else
        v39 = *(char **)v10;
      v17 = RemoveStatusOfMainPackageForAllUsers(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL), v39);
      if ( v17 < 0 )
      {
        if ( *((_QWORD *)this + 9) >= 8u )
          v10 = *(const char **)v10;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x253,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed while removing package %ws from each user's registered packages registry store",
          v10);
        wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        return (unsigned int)v17;
      }
      if ( *((_QWORD *)this + 9) < 8u )
        v40 = (char *)this + 48;
      else
        v40 = *(const char **)v10;
      v41 = MarkPackageAsRequiringAllUserStoreRefresh(*(_QWORD *)(*((_QWORD *)this + 2) + 584LL));
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)v41,
        (int)"Failed to mark package %ls as requiring all user store refresh",
        v40);
      if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 600LL) )
      {
        if ( v59 )
        {
          if ( v60 )
          {
            updated = MsixPackage::Provisioning::Library::MsixPackageAdapter::UpdateDependencies(this, v59, v60);
            if ( updated < 0 )
            {
              pv = 0;
              v43 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &pv,
                      L"(hr:0x%x) UpdateDependencies in the registry store failed",
                      (unsigned int)updated);
              if ( v43 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x26D,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v43,
                  v47);
              v44 = pv;
              v45 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
                      pv,
                      L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                      L"MsixPackage::Provisioning::Library::MsixPackageAdapter::RegisterPackage",
                      630);
              if ( v45 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x276,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                  (const char *)(unsigned int)v45,
                  1);
              if ( v44 )
                CoTaskMemFree(v44);
            }
          }
        }
      }
    }
    goto LABEL_142;
  }
  v56 = (__int64)(*((_QWORD *)a3 + 3) - *((_QWORD *)a3 + 2)) >> 3;
  v14 = v56;
  ProcessHeap = GetProcessHeap();
  v59 = (struct AppxAllUserStore::_PackageInfo **)HeapAlloc(ProcessHeap, 8u, 8LL * v14);
  if ( !v59 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)0x8007000ELL,
      (int)"Failed to allocate memory for dependencyPackageInfo array",
      v48);
    wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
    if ( !v13 )
      return 2147942414LL;
LABEL_100:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    return 2147942414LL;
  }
  v16 = 0;
  v51 = 0;
  if ( !v14 )
  {
LABEL_53:
    v60 = v16;
    goto LABEL_54;
  }
  while ( 1 )
  {
    v55 = 0;
    v54 = 0;
    v17 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(
            v66,
            v16,
            &v54);
    if ( v17 < 0 )
    {
      if ( *((_QWORD *)this + 9) >= 8u )
        v10 = *(const char **)v10;
      LODWORD(v48) = v16;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v17,
        (int)"Failed to obtain dependency package %d for package '%ws'",
        v48,
        v10);
      if ( v54 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v54 + 16LL))(v54);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return (unsigned int)v17;
    }
    if ( *((_QWORD *)this + 9) < 8u )
      v18 = (char *)this + 48;
    else
      v18 = *(const char **)v10;
    v19 = v54;
    v20 = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
            v54,
            (const unsigned __int16 **)&v55);
    v21 = wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x1F5,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)v20,
            (int)"Failed to obtain dependency package manifest path for package '%ws'; will retry if possible",
            v18);
    if ( v21 != -2147023728 )
    {
      if ( v21 < 0 )
        break;
      goto LABEL_47;
    }
    v22 = (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)*((_QWORD *)this + 2);
    if ( !*((_DWORD *)v22 + 150) || *((_DWORD *)v19 + 6) != 3 )
      break;
    LOBYTE(pv) = 0;
    v53 = 0;
    v23 = (char *)v19 + 48;
    if ( *((_QWORD *)v19 + 9) < 8u )
      v24 = (char *)v19 + 48;
    else
      v24 = *(char **)v23;
    v25 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(
            v24,
            v22,
            (bool *)&pv,
            &v53);
    if ( v25 < 0 )
    {
      if ( *((_QWORD *)v19 + 9) >= 8u )
        v23 = *(const char **)v23;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v25,
        (int)"Failed to create newer version of dependency package '%ws'",
        v23);
      if ( v53 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v53 + 16LL))(v53);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return (unsigned int)v25;
    }
    if ( !(_BYTE)pv )
    {
      if ( *((_QWORD *)v19 + 9) >= 8u )
        v23 = *(const char **)v23;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x20A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Failed to find expected higher version of dependency '%ws' on retry",
        v23);
      if ( v53 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v53 + 16LL))(v53);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return 2147549183LL;
    }
    v26 = v53;
    v25 = MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(
            v53,
            (const unsigned __int16 **)&v55);
    if ( v25 < 0 )
    {
      v38 = (char *)v26 + 48;
      if ( *((_QWORD *)v26 + 9) >= 8u )
        v38 = *(const char **)v38;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v25,
        (int)"Failed to obtain package manifest path for newer dependency package '%ws'",
        v38);
      if ( v26 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return (unsigned int)v25;
    }
    v27 = v19;
    v19 = v26;
    v54 = v26;
    if ( v26 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 8LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v27 + 16LL))(v27);
    v25 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
            v13,
            v26);
    if ( v25 < 0 )
    {
      v37 = (char *)v26 + 48;
      if ( *((_QWORD *)v26 + 9) >= 8u )
        v37 = *(const char **)v37;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x218,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v25,
        (int)"Failed to add newer dependency package '%ws' to collection of new dependencies",
        v37);
      if ( v26 )
      {
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      return (unsigned int)v25;
    }
    if ( v26 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v26 + 16LL))(v26);
    v16 = v51;
LABEL_47:
    v28 = GetProcessHeap();
    v29 = (struct AppxAllUserStore::_PackageInfo *)HeapAlloc(v28, 8u, 0x18u);
    if ( !v29 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x226,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)0x8007000ELL,
        (int)"Failed to allocate memory for packageInfo object",
        v48);
      if ( v19 )
        (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
      wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
      if ( !v13 )
        return 2147942414LL;
      goto LABEL_100;
    }
    v30 = (_QWORD *)((char *)v19 + 48);
    if ( *((_QWORD *)v19 + 9) >= 8u )
      v30 = (_QWORD *)*v30;
    *(_QWORD *)v29 = v30;
    *((_QWORD *)v29 + 1) = v55;
    v59[v16] = v29;
    if ( v19 )
      (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
    v51 = ++v16;
    if ( v16 >= (unsigned int)v56 )
      goto LABEL_53;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x21C,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v21,
    (int)"Retrying was not applicable",
    v48);
  if ( v19 )
    (*(void (__fastcall **)(MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v19 + 16LL))(v19);
  wil::details::ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___::_ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___(&v49);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18004cbe4  mov     [rsp-8+arg_8], rbx
0x18004cbe9  mov     [rsp-8+arg_10], r8
0x18004cbee  push    rbp
0x18004cbef  push    rsi
0x18004cbf0  push    rdi
0x18004cbf1  push    r12
0x18004cbf3  push    r13
0x18004cbf5  push    r14
0x18004cbf7  push    r15
0x18004cbf9  lea     rbp, [rsp-27h]
0x18004cbfe  sub     rsp, 0E0h
0x18004cc05  mov     r14, r9
0x18004cc08  mov     r12, r8
0x18004cc0b  mov     edi, edx
0x18004cc0d  mov     r13, rcx
0x18004cc10  cmp     dword ptr [rcx+18h], 3
0x18004cc14  jz      loc_18004D700
0x18004cc1a  xorps   xmm0, xmm0
0x18004cc1d  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x18004cc22  xor     r15d, r15d
0x18004cc25  mov     [rbp+57h+var_80], r15
0x18004cc29  xor     eax, eax
0x18004cc2b  mov     [rbp+57h+var_5C], eax
0x18004cc2e  xor     edx, edx; Val
0x18004cc30  lea     r8d, [r15+48h]; Size
0x18004cc34  lea     rcx, [rbp+57h+var_78]; void *
0x18004cc38  call    memset_0
0x18004cc3d  nop
0x18004cc3e  mov     [rbp+57h+var_B8], r15
0x18004cc42  lea     rcx, [rbp+57h+var_B8]
0x18004cc46  call    ?Make@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@SAJPEAPEAVMsixAdapterCollection@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Make(MsixPackage::Provisioning::Library::MsixAdapterCollection * *)
0x18004cc4b  mov     ebx, eax
0x18004cc4d  test    eax, eax
0x18004cc4f  jns     short loc_18004CC93
0x18004cc51  mov     rcx, [rbp+5Fh]; this
0x18004cc55  lea     rax, aFailedToCreate_17; "Failed to create package adapter collec"...
0x18004cc5c  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18004cc61  mov     r9d, ebx; char *
0x18004cc64  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004cc6b  mov     edx, 1B7h; void *
0x18004cc70  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cc75  nop
0x18004cc76  mov     rcx, [rbp+57h+var_B8]
0x18004cc7a  test    rcx, rcx
0x18004cc7d  jz      short loc_18004CC8C
0x18004cc7f  mov     rax, [rcx]
0x18004cc82  mov     rax, [rax+10h]
0x18004cc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc8b  nop
0x18004cc8c  mov     eax, ebx
0x18004cc8e  jmp     loc_18004D702
0x18004cc93  lea     rsi, [r13+30h]
0x18004cc97  cmp     qword ptr [rsi+18h], 8
0x18004cc9c  jb      short loc_18004CCA3
0x18004cc9e  mov     rax, [rsi]
0x18004cca1  jmp     short loc_18004CCA6
0x18004cca3  mov     rax, rsi
0x18004cca6  mov     [rbp+57h+var_90], rax
0x18004ccaa  mov     [rbp+57h+var_70], r15d
0x18004ccae  mov     [rbp+57h+var_78], r15
0x18004ccb2  mov     [rbp+57h+var_80], r14
0x18004ccb6  mov     rax, [r13+10h]
0x18004ccba  mov     ecx, [rax+2A0h]
0x18004ccc0  mov     [rbp+57h+var_34], ecx
0x18004ccc3  lea     rax, [rbp+57h+var_90]
0x18004ccc7  mov     [rbp+57h+var_D0], rax
0x18004cccb  mov     [rbp+57h+var_C8], 1
0x18004cccf  mov     r14d, 0FFFFFFFAh
0x18004ccd5  test    [r13+24h], r14d
0x18004ccd9  jnz     short loc_18004CCE5
0x18004ccdb  cmp     dword ptr [r13+24h], 5
0x18004cce0  mov     [rbp+57h+var_6C], edi
0x18004cce3  jnz     short loc_18004CCEC
0x18004cce5  mov     [rbp+57h+var_6C], 0
0x18004ccec  lea     rdx, [rbp+57h+var_90+8]; unsigned __int16 **
0x18004ccf0  mov     rcx, r13; this
0x18004ccf3  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x18004ccf8  mov     ebx, eax
0x18004ccfa  test    eax, eax
0x18004ccfc  jns     short loc_18004CD57
0x18004ccfe  cmp     qword ptr [rsi+18h], 8
0x18004cd03  jb      short loc_18004CD08
0x18004cd05  mov     rsi, [rsi]
0x18004cd08  mov     rcx, [rbp+5Fh]; this
0x18004cd0c  mov     [rsp+110h+var_E8], rsi; char *
0x18004cd11  lea     rax, aFailedToGetMan_0; "Failed to get manifest path for package"...
0x18004cd18  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18004cd1d  mov     r9d, ebx; char *
0x18004cd20  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004cd27  mov     edx, 1D5h; void *
0x18004cd2c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cd31  nop
0x18004cd32  lea     rcx, [rbp+57h+var_D0]
0x18004cd36  call    wil__details__ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f______ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___
0x18004cd3b  nop
0x18004cd3c  mov     rcx, [rbp+57h+var_B8]
0x18004cd40  test    rcx, rcx
0x18004cd43  jz      short loc_18004CD52
0x18004cd45  mov     rax, [rcx]
0x18004cd48  mov     rax, [rax+10h]
0x18004cd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd51  nop
0x18004cd52  jmp     loc_18004CC8C
0x18004cd57  lea     r15, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004cd5e  mov     rbx, [rbp+57h+var_B8]
0x18004cd62  test    r12, r12
0x18004cd65  jz      loc_18004CFF7
0x18004cd6b  test    [r13+24h], r14d
0x18004cd6f  jnz     loc_18004CFF7
0x18004cd75  cmp     dword ptr [r13+24h], 5
0x18004cd7a  jz      loc_18004CFF7
0x18004cd80  mov     r14, [r12+18h]
0x18004cd85  sub     r14, [r12+10h]
0x18004cd8a  sar     r14, 3
0x18004cd8e  mov     [rbp+57h+var_98], r14
0x18004cd92  mov     edi, r14d
0x18004cd95  shl     rdi, 3
0x18004cd99  call    cs:__imp_GetProcessHeap
0x18004cda0  nop     dword ptr [rax+rax+00h]
0x18004cda5  mov     rcx, rax; hHeap
0x18004cda8  mov     r8, rdi; dwBytes
0x18004cdab  mov     edx, 8; dwFlags
0x18004cdb0  call    cs:__imp_HeapAlloc
0x18004cdb7  nop     dword ptr [rax+rax+00h]
0x18004cdbc  mov     [rbp+57h+var_78], rax
0x18004cdc0  test    rax, rax
0x18004cdc3  jnz     short loc_18004CE08
0x18004cdc5  mov     rcx, [rbp+5Fh]; this
0x18004cdc9  lea     rax, aFailedToAlloca; "Failed to allocate memory for dependenc"...
0x18004cdd0  mov     qword ptr [rsp+110h+var_F0], rax; int
0x18004cdd5  mov     r9d, 8007000Eh; char *
0x18004cddb  mov     r8, r15; unsigned int
0x18004cdde  mov     edx, 1E6h; void *
0x18004cde3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cde8  nop
0x18004cde9  lea     rcx, [rbp+57h+var_D0]
0x18004cded  call    wil__details__ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f______ScopeExitFn__lambda_781979bece8efe9ccb6deacd5578a61f___
0x18004cdf2  nop
0x18004cdf3  test    rbx, rbx
0x18004cdf6  jz      loc_18004D32D
0x18004cdfc  mov     rax, [rbx]
0x18004cdff  mov     rax, [rax+10h]
0x18004ce03  jmp     loc_18004D324
0x18004ce08  xor     r12d, r12d
0x18004ce0b  mov     [rbp+57h+var_C0], r12d
0x18004ce0f  test    r14d, r14d
0x18004ce12  jz      loc_18004CFF3
0x18004ce18  mov     [rbp+57h+var_A0], 0
0x18004ce20  mov     [rbp+57h+var_A8], 0
0x18004ce28  lea     r8, [rbp+57h+var_A8]
0x18004ce2c  mov     edx, r12d
0x18004ce2f  mov     rcx, [rbp+57h+arg_10]
0x18004ce33  call    ?Item@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJKPEAPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Item(ulong,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004ce38  mov     edi, eax
0x18004ce3a  test    eax, eax
0x18004ce3c  js      loc_18004D394
0x18004ce42  cmp     qword ptr [rsi+18h], 8
0x18004ce47  jb      short loc_18004CE4E
0x18004ce49  mov     r14, [rsi]
0x18004ce4c  jmp     short loc_18004CE51
0x18004ce4e  mov     r14, rsi
0x18004ce51  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18004ce55  mov     rdi, [rbp+57h+var_A8]
0x18004ce59  mov     rcx, rdi; this
0x18004ce5c  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x18004ce61  mov     rcx, [rbp+5Fh]; this
0x18004ce65  mov     [rsp+110h+var_E8], r14; char *
0x18004ce6a  lea     rdx, aFailedToObtain_1; "Failed to obtain dependency package man"...
0x18004ce71  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18004ce76  mov     r9d, eax; char *
0x18004ce79  mov     r8, r15; unsigned int
0x18004ce7c  mov     edx, 1F5h; void *
0x18004ce81  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004ce86  mov     r14d, eax
0x18004ce89  cmp     eax, 80070490h
0x18004ce8e  jnz     loc_18004CF70
0x18004ce94  mov     rdx, [r13+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18004ce98  cmp     dword ptr [rdx+258h], 0
0x18004ce9f  jz      loc_18004D337
0x18004cea5  cmp     dword ptr [rdi+18h], 3
0x18004cea9  jnz     loc_18004D337
0x18004ceaf  mov     byte ptr [rbp+57h+pv], 0
0x18004ceb3  mov     [rbp+57h+var_B0], 0
0x18004cebb  lea     r14, [rdi+30h]
0x18004cebf  cmp     qword ptr [r14+18h], 8
0x18004cec4  jb      short loc_18004CECB
0x18004cec6  mov     rcx, [r14]
0x18004cec9  jmp     short loc_18004CECE
0x18004cecb  mov     rcx, r14; char *
0x18004cece  lea     r9, [rbp+57h+var_B0]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18004ced2  lea     r8, [rbp+57h+pv]; bool *
0x18004ced6  call    ?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004cedb  mov     r12d, eax
0x18004cede  test    eax, eax
0x18004cee0  js      loc_18004D258
0x18004cee6  cmp     byte ptr [rbp+57h+pv], 0
0x18004ceea  jz      loc_18004D1D7
0x18004cef0  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x18004cef4  mov     r14, [rbp+57h+var_B0]
0x18004cef8  mov     rcx, r14; this
0x18004cefb  call    ?GetTargetManifestPath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEAPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::GetTargetManifestPath(ushort const * *)
0x18004cf00  mov     r12d, eax
0x18004cf03  test    eax, eax
0x18004cf05  js      loc_18004D15A
0x18004cf0b  mov     r12, rdi
0x18004cf0e  mov     rdi, r14
0x18004cf11  mov     [rbp+57h+var_A8], r14
0x18004cf15  test    r14, r14
0x18004cf18  jz      short loc_18004CF29
0x18004cf1a  mov     rax, [r14]
0x18004cf1d  mov     rcx, r14
0x18004cf20  mov     rax, [rax+8]
0x18004cf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf29  test    r12, r12
0x18004cf2c  jz      short loc_18004CF3F
0x18004cf2e  mov     rax, [r12]
0x18004cf32  mov     rcx, r12
0x18004cf35  mov     rax, [rax+10h]
0x18004cf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf3e  nop
0x18004cf3f  mov     rdx, r14
0x18004cf42  mov     rcx, rbx
0x18004cf45  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x18004cf4a  mov     r12d, eax
0x18004cf4d  test    eax, eax
0x18004cf4f  js      loc_18004D0D8
0x18004cf55  test    r14, r14
0x18004cf58  jz      short loc_18004CF6A
0x18004cf5a  mov     rax, [r14]
0x18004cf5d  mov     rcx, r14
0x18004cf60  mov     rax, [rax+10h]
0x18004cf64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf69  nop
0x18004cf6a  mov     r12d, [rbp+57h+var_C0]
0x18004cf6e  jmp     short loc_18004CF79
0x18004cf70  test    r14d, r14d
0x18004cf73  js      loc_18004D337
0x18004cf79  call    cs:__imp_GetProcessHeap
0x18004cf80  nop     dword ptr [rax+rax+00h]
0x18004cf85  mov     rcx, rax; hHeap
0x18004cf88  mov     edx, 8; dwFlags
0x18004cf8d  lea     r8d, [rdx+10h]; dwBytes
0x18004cf91  call    cs:__imp_HeapAlloc
0x18004cf98  nop     dword ptr [rax+rax+00h]
0x18004cf9d  mov     rdx, rax
0x18004cfa0  test    rax, rax
0x18004cfa3  jz      loc_18004D2D5
0x18004cfa9  lea     rcx, [rdi+30h]
0x18004cfad  cmp     qword ptr [rcx+18h], 8
0x18004cfb2  jb      short loc_18004CFB7
0x18004cfb4  mov     rcx, [rcx]
0x18004cfb7  mov     [rax], rcx
0x18004cfba  mov     rax, [rbp+57h+var_A0]
0x18004cfbe  mov     [rdx+8], rax
0x18004cfc2  mov     ecx, r12d
0x18004cfc5  mov     rax, [rbp+57h+var_78]
0x18004cfc9  mov     [rax+rcx*8], rdx
0x18004cfcd  test    rdi, rdi
0x18004cfd0  jz      short loc_18004CFE2
0x18004cfd2  mov     rax, [rdi]
0x18004cfd5  mov     rcx, rdi
0x18004cfd8  mov     rax, [rax+10h]
0x18004cfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfe1  nop
0x18004cfe2  inc     r12d
0x18004cfe5  mov     [rbp+57h+var_C0], r12d
0x18004cfe9  cmp     r12d, dword ptr [rbp+57h+var_98]
0x18004cfed  jb      loc_18004CE18
0x18004cff3  mov     [rbp+57h+var_70], r12d
0x18004cff7  mov     ecx, [r13+24h]
0x18004cffb  test    ecx, ecx
0x18004cffd  jz      short loc_18004D01F
0x18004cfff  sub     ecx, 1
0x18004d002  jz      short loc_18004D01F
0x18004d004  sub     ecx, 1
0x18004d007  jz      loc_18004D60A
0x18004d00d  sub     ecx, 1
0x18004d010  jz      loc_18004D60A
0x18004d016  cmp     ecx, 1
0x18004d019  jnz     loc_18004D67F
0x18004d01f  cmp     dword ptr [r13+108h], 0
0x18004d027  jnz     short loc_18004D044
0x18004d029  mov     rax, [r13+0D0h]
0x18004d030  cmp     dword ptr [rax+0A0h], 0
0x18004d037  jz      short loc_18004D044
0x18004d039  cmp     dword ptr [r13+24h], 1
0x18004d03e  jnz     loc_18004D60A
0x18004d044  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore> `wil::Feature<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::GetImpl(void)'::`2'::impl
0x18004d04b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ProvisionedExternalLocationInAllUserStore>::__private_IsEnabled(void)
0x18004d050  mov     rcx, [r13+10h]
0x18004d054  lea     rdx, [rbp+57h+var_90]
0x18004d058  test    al, al
0x18004d05a  jz      loc_18004D405
0x18004d060  mov     r8, [rcx+2A8h]
0x18004d067  mov     rcx, [rcx+248h]
0x18004d06e  call    cs:__imp_AddPackageToRegistryStore2
0x18004d075  nop     dword ptr [rax+rax+00h]
0x18004d07a  mov     edi, eax
0x18004d07c  test    eax, eax
0x18004d07e  jns     loc_18004D46F
  ... truncated ...
```
