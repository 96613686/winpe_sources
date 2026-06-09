# MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,IAppxPackageReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x180053324`
- end: `0x180054460`
- name: `?CreateForPackageReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@HPEAUIAppxPackageReader@@PEAPEAV1234@@Z`
- size: `4412`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, int, struct IAppxPackageReader *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800441c8`
- `0x180056d60`

## callees

- `0x18001bf0c`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180032ad0`
- `0x180039e9c`
- `0x180040400`
- `0x180047338`
- `0x180053324`
- `0x180054b84`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18005381a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005381a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005345e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800536dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005345e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800536dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054092`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054276`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800536d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800536d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800536e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800536e4`

## string_xrefs

- `0x18005339b`: `Failed to create payload adapter for package.`
- `0x1800534f6`: `Failed to get manifest reader for package.`
- `0x180053946`: `Failed to insert manifest file into payload adapter for package %ws.`
- `0x180053fd4`: `Failed to insert manifest file into payload adapter for package %ws.`
- `0x180053869`: `Failed to get manifest footprint file for package %ws.`
- `0x180053e57`: `MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a1,
        int a2,
        struct IAppxPackageReader *a3,
        struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **a4)
{
  int v8; // ebx
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v10; // rbx
  __int64 v11; // rdi
  HRESULT (__stdcall *GetManifest)(IAppxPackageReader *, IAppxManifestReader **); // rdi
  __int64 v13; // rcx
  int v14; // edi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // r14
  __int64 v17; // rcx
  __int64 v18; // r15
  __int64 (__fastcall *v19)(__int64, LPVOID *); // r12
  DWORD LastError; // edi
  unsigned __int64 v21; // r8
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  __int64 v23; // rcx
  HRESULT (__stdcall *v24)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  __int64 v25; // rcx
  HRESULT (__stdcall *v26)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  __int64 v27; // rcx
  HRESULT (__stdcall *v28)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rdi
  __int64 v29; // rcx
  int v30; // eax
  void *v31; // rdi
  int v32; // eax
  HRESULT (__stdcall *GetPayloadFiles)(IAppxPackageReader *, IAppxFilesEnumerator **); // r14
  __int64 **v34; // rdi
  __int64 v35; // rcx
  int v36; // esi
  int v37; // r14d
  __int64 *v38; // rcx
  __int64 v39; // rax
  char *v40; // [rsp+28h] [rbp-61h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  __int64 v42; // [rsp+38h] [rbp-51h] BYREF
  __int64 v43; // [rsp+40h] [rbp-49h] BYREF
  __int64 v44; // [rsp+48h] [rbp-41h] BYREF
  __int64 v45; // [rsp+50h] [rbp-39h] BYREF
  __int64 v46; // [rsp+58h] [rbp-31h] BYREF
  __int64 v47; // [rsp+60h] [rbp-29h] BYREF
  int v48; // [rsp+68h] [rbp-21h] BYREF
  LPVOID v49; // [rsp+70h] [rbp-19h] BYREF
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v50; // [rsp+78h] [rbp-11h] BYREF
  void *Src[3]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v52; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  pv = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v48 = 0;
  *a4 = 0;
  v50 = 0;
  v8 = MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(&v50);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v8,
      (int)"Failed to create payload adapter for package.",
      v40);
    if ( v50 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v8;
  }
  v10 = v50;
  *((_QWORD *)v50 + 6) = a1;
  *((_DWORD *)v10 + 30) = 1;
  v11 = *((_QWORD *)v10 + 17);
  *((_QWORD *)v10 + 17) = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IAppxPackageReader *))a3->lpVtbl->AddRef)(a3);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  *((_DWORD *)v10 + 40) = a2;
  GetManifest = a3->lpVtbl->GetManifest;
  v13 = v47;
  v47 = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetManifest)(a3, &v47);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get manifest reader for package.",
      v40);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
LABEL_38:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v14;
  }
  v15 = v47;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 24LL);
  v17 = v46;
  v46 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v14 = v16(v15, &v46);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get package id for package.",
      v40);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v18 = v46;
  v19 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v46 + 72LL);
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(pv);
    SetLastError(LastError);
  }
  pv = 0;
  v14 = v19(v18, &pv);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get package full name for package.",
      v40);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v52 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)pv )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pv + v21) );
  }
  else
  {
    v21 = 0;
  }
  std::wstring::assign(Src, (char *)pv, v21);
  std::wstring::assign((char *)v10 + 56, Src);
  if ( v52 >= 8 )
    operator delete(Src[0]);
  GetFootprintFile = a3->lpVtbl->GetFootprintFile;
  v23 = v45;
  v45 = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, _QWORD, __int64 *))GetFootprintFile)(a3, 0, &v45);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get manifest footprint file for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v45);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to insert manifest file into payload adapter for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v24 = a3->lpVtbl->GetFootprintFile;
  v25 = v44;
  v44 = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v24)(a3, 1, &v44);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get blockmap footprint file for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v44);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to insert blockmap file into payload adapter for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v26 = a3->lpVtbl->GetFootprintFile;
  v27 = v43;
  v43 = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v26)(a3, 2, &v43);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get signature footprint file for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v43);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to insert signature file into payload adapter for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    goto LABEL_38;
  }
  v28 = a3->lpVtbl->GetFootprintFile;
  v29 = v42;
  v42 = 0;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v28)(a3, 3, &v42);
  if ( v14 == -2147024894 )
  {
    v49 = 0;
    v30 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&v49,
            L"Code integrity footprint file not found for package %ws",
            pv);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x52,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v30);
    v31 = v49;
    v32 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            v49,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
            L"MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader",
            91);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v32);
    if ( v31 )
      CoTaskMemFree(v31);
  }
  else
  {
    v37 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
            v10,
            v42);
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x64,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v37,
        (int)"Failed to insert manifest file into payload adapter for package %ws.",
        (const char *)pv);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)v37;
    }
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v14,
        (int)"Failed to get code integrity footprint file for package %ws.",
        (const char *)pv);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v46 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      goto LABEL_38;
    }
  }
  GetPayloadFiles = a3->lpVtbl->GetPayloadFiles;
  v34 = (__int64 **)((char *)v10 + 144);
  v35 = *((_QWORD *)v10 + 18);
  *((_QWORD *)v10 + 18) = 0;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v36 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, char *))GetPayloadFiles)(a3, (char *)v10 + 144);
  if ( v36 >= 0 )
  {
    (*(void (__fastcall **)(__int64 *, int *))(**v34 + 32))(*v34, &v48);
    while ( 1 )
    {
      if ( !v48 )
      {
        *a4 = v10;
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        if ( v46 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
      v49 = 0;
      v38 = *v34;
      v39 = **v34;
      v49 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v39 + 24))(v38, &v49);
      if ( v36 < 0 )
        break;
      v36 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
              v10,
              v49);
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v36,
          (int)"Failed to insert payload file into unpack list for package %ws.",
          (const char *)pv);
        if ( v49 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        if ( v46 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
        if ( v47 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        goto LABEL_193;
      }
      if ( v49 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
      (*(void (__fastcall **)(__int64 *, int *))(**v34 + 40))(*v34, &v48);
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v36,
      (int)"Failed to get payload file for package %ws.",
      (const char *)pv);
    if ( v49 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v49 + 16LL))(v49);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v36,
      (int)"Failed to get payload files for package %ws.",
      (const char *)pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( v44 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
LABEL_193:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x180053324  mov     [rsp-8+arg_0], rbx
0x180053329  push    rbp
0x18005332a  push    rsi
0x18005332b  push    rdi
0x18005332c  push    r12
0x18005332e  push    r13
0x180053330  push    r14
0x180053332  push    r15
0x180053334  lea     rbp, [rsp-27h]
0x180053339  sub     rsp, 0B0h
0x180053340  mov     rax, cs:__security_cookie
0x180053347  xor     rax, rsp
0x18005334a  mov     [rbp+57h+var_40], rax
0x18005334e  mov     r13, r9
0x180053351  mov     rsi, r8
0x180053354  mov     r14d, edx
0x180053357  mov     rdi, rcx
0x18005335a  xor     r15d, r15d
0x18005335d  mov     [rbp+57h+pv], r15
0x180053361  mov     [rbp+57h+var_80], r15
0x180053365  mov     [rbp+57h+var_88], r15
0x180053369  mov     [rbp+57h+var_90], r15
0x18005336d  mov     [rbp+57h+var_98], r15
0x180053371  mov     [rbp+57h+var_A0], r15
0x180053375  mov     [rbp+57h+var_A8], r15
0x180053379  mov     [rbp+57h+var_78], r15d
0x18005337d  mov     [r9], r15
0x180053380  mov     [rbp+57h+var_68], r15
0x180053384  lea     rcx, [rbp+57h+var_68]
0x180053388  call    ?Make@?$CContainer@UIAppxFile@@VPackageMonikerToPayload@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@SAJPEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x18005338d  mov     ebx, eax
0x18005338f  test    eax, eax
0x180053391  jns     loc_18005346B
0x180053397  mov     rcx, [rbp+5Fh]; this
0x18005339b  lea     rax, aFailedToCreate_16; "Failed to create payload adapter for pa"...
0x1800533a2  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800533a7  mov     r9d, ebx; char *
0x1800533aa  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800533b1  lea     edx, [r15+1Fh]; void *
0x1800533b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800533ba  nop
0x1800533bb  mov     rcx, [rbp+57h+var_68]
0x1800533bf  test    rcx, rcx
0x1800533c2  jz      short loc_1800533D1
0x1800533c4  mov     rax, [rcx]
0x1800533c7  mov     rax, [rax+10h]
0x1800533cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533d0  nop
0x1800533d1  mov     rcx, [rbp+57h+var_A8]
0x1800533d5  test    rcx, rcx
0x1800533d8  jz      short loc_1800533E7
0x1800533da  mov     rax, [rcx]
0x1800533dd  mov     rax, [rax+10h]
0x1800533e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533e6  nop
0x1800533e7  mov     rcx, [rbp+57h+var_A0]
0x1800533eb  test    rcx, rcx
0x1800533ee  jz      short loc_1800533FD
0x1800533f0  mov     rax, [rcx]
0x1800533f3  mov     rax, [rax+10h]
0x1800533f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533fc  nop
0x1800533fd  mov     rcx, [rbp+57h+var_98]
0x180053401  test    rcx, rcx
0x180053404  jz      short loc_180053413
0x180053406  mov     rax, [rcx]
0x180053409  mov     rax, [rax+10h]
0x18005340d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053412  nop
0x180053413  mov     rcx, [rbp+57h+var_90]
0x180053417  test    rcx, rcx
0x18005341a  jz      short loc_180053429
0x18005341c  mov     rax, [rcx]
0x18005341f  mov     rax, [rax+10h]
0x180053423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053428  nop
0x180053429  mov     rcx, [rbp+57h+var_88]
0x18005342d  test    rcx, rcx
0x180053430  jz      short loc_18005343F
0x180053432  mov     rax, [rcx]
0x180053435  mov     rax, [rax+10h]
0x180053439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005343e  nop
0x18005343f  mov     rcx, [rbp+57h+var_80]
0x180053443  test    rcx, rcx
0x180053446  jz      short loc_180053455
0x180053448  mov     rax, [rcx]
0x18005344b  mov     rax, [rax+10h]
0x18005344f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053454  nop
0x180053455  mov     rcx, [rbp+57h+pv]; pv
0x180053459  test    rcx, rcx
0x18005345c  jz      short loc_180053464
0x18005345e  call    cs:__imp_CoTaskMemFree
0x180053464  mov     eax, ebx
0x180053466  jmp     loc_18005427E
0x18005346b  mov     rbx, [rbp+57h+var_68]
0x18005346f  mov     [rbx+30h], rdi
0x180053473  mov     dword ptr [rbx+78h], 1
0x18005347a  mov     rdi, [rbx+88h]
0x180053481  mov     [rbx+88h], rsi
0x180053488  test    rsi, rsi
0x18005348b  jz      short loc_18005349C
0x18005348d  mov     rax, [rsi]
0x180053490  mov     rcx, rsi
0x180053493  mov     rax, [rax+8]
0x180053497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005349c  test    rdi, rdi
0x18005349f  jz      short loc_1800534B1
0x1800534a1  mov     rax, [rdi]
0x1800534a4  mov     rcx, rdi
0x1800534a7  mov     rax, [rax+10h]
0x1800534ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534b0  nop
0x1800534b1  mov     [rbx+0A0h], r14d
0x1800534b8  mov     rax, [rsi]
0x1800534bb  mov     rdi, [rax+38h]
0x1800534bf  mov     rcx, [rbp+57h+var_80]
0x1800534c3  mov     [rbp+57h+var_80], r15
0x1800534c7  test    rcx, rcx
0x1800534ca  jz      short loc_1800534D9
0x1800534cc  mov     rdx, [rcx]
0x1800534cf  mov     rax, [rdx+10h]
0x1800534d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534d8  nop
0x1800534d9  lea     rdx, [rbp+57h+var_80]
0x1800534dd  mov     rcx, rsi
0x1800534e0  mov     rax, rdi
0x1800534e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800534e8  mov     edi, eax
0x1800534ea  test    eax, eax
0x1800534ec  jns     loc_1800535C1
0x1800534f2  mov     rcx, [rbp+5Fh]; this
0x1800534f6  lea     rax, aFailedToGetMan_1; "Failed to get manifest reader for packa"...
0x1800534fd  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180053502  mov     r9d, edi; char *
0x180053505  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005350c  mov     edx, 27h ; '''; void *
0x180053511  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053516  nop
0x180053517  mov     rax, [rbx]
0x18005351a  mov     rcx, rbx
0x18005351d  mov     rax, [rax+10h]
0x180053521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053526  nop
0x180053527  mov     rcx, [rbp+57h+var_A8]
0x18005352b  test    rcx, rcx
0x18005352e  jz      short loc_18005353D
0x180053530  mov     rax, [rcx]
0x180053533  mov     rax, [rax+10h]
0x180053537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005353c  nop
0x18005353d  mov     rcx, [rbp+57h+var_A0]
0x180053541  test    rcx, rcx
0x180053544  jz      short loc_180053553
0x180053546  mov     rax, [rcx]
0x180053549  mov     rax, [rax+10h]
0x18005354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053552  nop
0x180053553  mov     rcx, [rbp+57h+var_98]
0x180053557  test    rcx, rcx
0x18005355a  jz      short loc_180053569
0x18005355c  mov     rax, [rcx]
0x18005355f  mov     rax, [rax+10h]
0x180053563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053568  nop
0x180053569  mov     rcx, [rbp+57h+var_90]
0x18005356d  test    rcx, rcx
0x180053570  jz      short loc_18005357F
0x180053572  mov     rax, [rcx]
0x180053575  mov     rax, [rax+10h]
0x180053579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005357e  nop
0x18005357f  mov     rcx, [rbp+57h+var_88]
0x180053583  test    rcx, rcx
0x180053586  jz      short loc_180053595
0x180053588  mov     rax, [rcx]
0x18005358b  mov     rax, [rax+10h]
0x18005358f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053594  nop
0x180053595  mov     rcx, [rbp+57h+var_80]
0x180053599  test    rcx, rcx
0x18005359c  jz      short loc_1800535AB
0x18005359e  mov     rax, [rcx]
0x1800535a1  mov     rax, [rax+10h]
0x1800535a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535aa  nop
0x1800535ab  mov     rcx, [rbp+57h+pv]; pv
0x1800535af  test    rcx, rcx
0x1800535b2  jz      short loc_1800535BA
0x1800535b4  call    cs:__imp_CoTaskMemFree
0x1800535ba  mov     eax, edi
0x1800535bc  jmp     loc_18005427E
0x1800535c1  mov     rdi, [rbp+57h+var_80]
0x1800535c5  mov     rax, [rdi]
0x1800535c8  mov     r14, [rax+18h]
0x1800535cc  mov     rcx, [rbp+57h+var_88]
0x1800535d0  mov     [rbp+57h+var_88], r15
0x1800535d4  test    rcx, rcx
0x1800535d7  jz      short loc_1800535E6
0x1800535d9  mov     rdx, [rcx]
0x1800535dc  mov     rax, [rdx+10h]
0x1800535e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535e5  nop
0x1800535e6  lea     rdx, [rbp+57h+var_88]
0x1800535ea  mov     rcx, rdi
0x1800535ed  mov     rax, r14
0x1800535f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535f5  mov     edi, eax
0x1800535f7  test    eax, eax
0x1800535f9  jns     loc_1800536BD
0x1800535ff  mov     rcx, [rbp+5Fh]; this
0x180053603  lea     rax, aFailedToGetPac_3; "Failed to get package id for package."
0x18005360a  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18005360f  mov     r9d, edi; char *
0x180053612  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053619  mov     edx, 28h ; '('; void *
0x18005361e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053623  nop
0x180053624  mov     rax, [rbx]
0x180053627  mov     rcx, rbx
0x18005362a  mov     rax, [rax+10h]
0x18005362e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053633  nop
0x180053634  mov     rcx, [rbp+57h+var_A8]
0x180053638  test    rcx, rcx
0x18005363b  jz      short loc_18005364A
0x18005363d  mov     rax, [rcx]
0x180053640  mov     rax, [rax+10h]
0x180053644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053649  nop
0x18005364a  mov     rcx, [rbp+57h+var_A0]
0x18005364e  test    rcx, rcx
0x180053651  jz      short loc_180053660
0x180053653  mov     rax, [rcx]
0x180053656  mov     rax, [rax+10h]
0x18005365a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005365f  nop
0x180053660  mov     rcx, [rbp+57h+var_98]
0x180053664  test    rcx, rcx
0x180053667  jz      short loc_180053676
0x180053669  mov     rax, [rcx]
0x18005366c  mov     rax, [rax+10h]
0x180053670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053675  nop
0x180053676  mov     rcx, [rbp+57h+var_90]
0x18005367a  test    rcx, rcx
0x18005367d  jz      short loc_18005368C
0x18005367f  mov     rax, [rcx]
0x180053682  mov     rax, [rax+10h]
0x180053686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005368b  nop
0x18005368c  mov     rcx, [rbp+57h+var_88]
0x180053690  test    rcx, rcx
0x180053693  jz      short loc_1800536A2
0x180053695  mov     rax, [rcx]
0x180053698  mov     rax, [rax+10h]
0x18005369c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536a1  nop
0x1800536a2  mov     rcx, [rbp+57h+var_80]
0x1800536a6  test    rcx, rcx
0x1800536a9  jz      short loc_1800536B8
0x1800536ab  mov     rax, [rcx]
0x1800536ae  mov     rax, [rax+10h]
0x1800536b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536b7  nop
0x1800536b8  jmp     loc_1800535AB
0x1800536bd  mov     r15, [rbp+57h+var_88]
0x1800536c1  mov     rax, [r15]
0x1800536c4  mov     r12, [rax+48h]
0x1800536c8  mov     r14, [rbp+57h+pv]
0x1800536cc  test    r14, r14
0x1800536cf  jz      short loc_1800536EA
0x1800536d1  call    cs:__imp_GetLastError
0x1800536d7  mov     edi, eax
0x1800536d9  mov     rcx, r14; pv
0x1800536dc  call    cs:__imp_CoTaskMemFree
0x1800536e2  mov     ecx, edi; dwErrCode
0x1800536e4  call    cs:__imp_SetLastError
0x1800536ea  mov     [rbp+57h+pv], 0
0x1800536f2  lea     rdx, [rbp+57h+pv]
0x1800536f6  mov     rcx, r15
0x1800536f9  mov     rax, r12
0x1800536fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053701  mov     edi, eax
0x180053703  xor     r15d, r15d
0x180053706  test    eax, eax
0x180053708  jns     loc_1800537CB
0x18005370e  mov     rcx, [rbp+5Fh]; this
0x180053712  lea     rax, aFailedToGetPac_1; "Failed to get package full name for pac"...
0x180053719  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18005371e  mov     r9d, edi; char *
0x180053721  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180053728  lea     edx, [r15+29h]; void *
0x18005372c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180053731  nop
0x180053732  mov     rax, [rbx]
0x180053735  mov     rcx, rbx
0x180053738  mov     rax, [rax+10h]
0x18005373c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
