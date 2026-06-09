# MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,IAppxPackageReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x180057830`
- end: `0x1800589a9`
- name: `?CreateForPackageReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@HPEAUIAppxPackageReader@@PEAPEAV1234@@Z`
- size: `4473`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, int, struct IAppxPackageReader *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004804c`
- `0x18005b444`

## callees

- `0x18001d160`
- `0x18001d65c`
- `0x180034d7c`
- `0x180035a84`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18004b384`
- `0x180057830`
- `0x180059118`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180057d44`
- `msvcrt!??3@YAXPEAX@Z` at `0x180057d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005796a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800583c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005796a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800583c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800585ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800587b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057be9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057be9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057c08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180057c08`

## string_xrefs

- `0x180057a08`: `Failed to get manifest reader for package.`
- `0x1800578a7`: `Failed to create payload adapter for package.`
- `0x180057e76`: `Failed to insert manifest file into payload adapter for package %ws.`
- `0x180058510`: `Failed to insert manifest file into payload adapter for package %ws.`
- `0x180057d99`: `Failed to get manifest footprint file for package %ws.`
- `0x180058387`: `MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
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
  __int64 v21; // r8
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
  int v40; // [rsp+20h] [rbp-69h]
  char *v41; // [rsp+28h] [rbp-61h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  __int64 v43; // [rsp+38h] [rbp-51h] BYREF
  __int64 v44; // [rsp+40h] [rbp-49h] BYREF
  __int64 v45; // [rsp+48h] [rbp-41h] BYREF
  __int64 v46; // [rsp+50h] [rbp-39h] BYREF
  __int64 v47; // [rsp+58h] [rbp-31h] BYREF
  __int64 v48; // [rsp+60h] [rbp-29h] BYREF
  int v49; // [rsp+68h] [rbp-21h] BYREF
  LPVOID v50; // [rsp+70h] [rbp-19h] BYREF
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v51; // [rsp+78h] [rbp-11h] BYREF
  void *Src[3]; // [rsp+80h] [rbp-9h] BYREF
  unsigned __int64 v53; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  pv = 0;
  v48 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v49 = 0;
  *a4 = 0;
  v51 = 0;
  v8 = MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(&v51);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v8,
      (int)"Failed to create payload adapter for package.",
      v41);
    if ( v51 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v51 + 16LL))(v51);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v8;
  }
  v10 = v51;
  *((_QWORD *)v51 + 6) = a1;
  *((_DWORD *)v10 + 30) = 1;
  v11 = *((_QWORD *)v10 + 17);
  *((_QWORD *)v10 + 17) = a3;
  if ( a3 )
    ((void (__fastcall *)(struct IAppxPackageReader *))a3->lpVtbl->AddRef)(a3);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  *((_DWORD *)v10 + 40) = a2;
  GetManifest = a3->lpVtbl->GetManifest;
  v13 = v48;
  v48 = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetManifest)(a3, &v48);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get manifest reader for package.",
      v41);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
LABEL_38:
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v14;
  }
  v15 = v48;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 24LL);
  v17 = v47;
  v47 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v14 = v16(v15, &v47);
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v14,
      (int)"Failed to get package id for package.",
      v41);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v18 = v47;
  v19 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v47 + 72LL);
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
      v41);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v53 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)pv )
  {
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pv + v21) );
  }
  std::wstring::assign(Src, pv);
  std::wstring::assign((char *)v10 + 56, Src);
  if ( v53 >= 8 )
    operator delete(Src[0]);
  GetFootprintFile = a3->lpVtbl->GetFootprintFile;
  v23 = v46;
  v46 = 0;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, _QWORD, __int64 *))GetFootprintFile)(a3, 0, &v46);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v46);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v24 = a3->lpVtbl->GetFootprintFile;
  v25 = v45;
  v45 = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v24)(a3, 1, &v45);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v45);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v26 = a3->lpVtbl->GetFootprintFile;
  v27 = v44;
  v44 = 0;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v26)(a3, 2, &v44);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v14 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
          v10,
          v44);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_38;
  }
  v28 = a3->lpVtbl->GetFootprintFile;
  v29 = v43;
  v43 = 0;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v14 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v28)(a3, 3, &v43);
  if ( v14 == -2147024894 )
  {
    v50 = 0;
    v30 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v50,
            L"Code integrity footprint file not found for package %ws",
            pv);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v30,
        v40);
    v31 = v50;
    v32 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            v50,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
            L"MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForPackageReader",
            91);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v32,
        2);
    if ( v31 )
      CoTaskMemFree(v31);
  }
  else
  {
    v37 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
            v10,
            v43);
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
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
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
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
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
    (*(void (__fastcall **)(__int64 *, int *))(**v34 + 32))(*v34, &v49);
    while ( 1 )
    {
      if ( !v49 )
      {
        *a4 = v10;
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
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
      v50 = 0;
      v38 = *v34;
      v39 = **v34;
      v50 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v39 + 24))(v38, &v50);
      if ( v36 < 0 )
        break;
      v36 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
              v10,
              v50);
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v36,
          (int)"Failed to insert payload file into unpack list for package %ws.",
          (const char *)pv);
        if ( v50 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
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
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        goto LABEL_192;
      }
      if ( v50 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
      (*(void (__fastcall **)(__int64 *, int *))(**v34 + 40))(*v34, &v49);
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v36,
      (int)"Failed to get payload file for package %ws.",
      (const char *)pv);
    if ( v50 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v50 + 16LL))(v50);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v10 + 16LL))(v10);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
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
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  }
LABEL_192:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x180057830  mov     [rsp-8+arg_0], rbx
0x180057835  push    rbp
0x180057836  push    rsi
0x180057837  push    rdi
0x180057838  push    r12
0x18005783a  push    r13
0x18005783c  push    r14
0x18005783e  push    r15
0x180057840  lea     rbp, [rsp-27h]
0x180057845  sub     rsp, 0B0h
0x18005784c  mov     rax, cs:__security_cookie
0x180057853  xor     rax, rsp
0x180057856  mov     [rbp+57h+var_40], rax
0x18005785a  mov     r13, r9
0x18005785d  mov     rsi, r8
0x180057860  mov     r14d, edx
0x180057863  mov     rdi, rcx
0x180057866  xor     r15d, r15d
0x180057869  mov     [rbp+57h+pv], r15
0x18005786d  mov     [rbp+57h+var_80], r15
0x180057871  mov     [rbp+57h+var_88], r15
0x180057875  mov     [rbp+57h+var_90], r15
0x180057879  mov     [rbp+57h+var_98], r15
0x18005787d  mov     [rbp+57h+var_A0], r15
0x180057881  mov     [rbp+57h+var_A8], r15
0x180057885  mov     [rbp+57h+var_78], r15d
0x180057889  mov     [r9], r15
0x18005788c  mov     [rbp+57h+var_68], r15
0x180057890  lea     rcx, [rbp+57h+var_68]
0x180057894  call    ?Make@?$CContainer@UIAppxFile@@VPackageMonikerToPayload@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@SAJPEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x180057899  mov     ebx, eax
0x18005789b  test    eax, eax
0x18005789d  jns     loc_18005797D
0x1800578a3  mov     rcx, [rbp+5Fh]; this
0x1800578a7  lea     rax, aFailedToCreate_16; "Failed to create payload adapter for pa"...
0x1800578ae  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800578b3  mov     r9d, ebx; char *
0x1800578b6  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800578bd  lea     edx, [r15+1Fh]; void *
0x1800578c1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800578c6  nop
0x1800578c7  mov     rcx, [rbp+57h+var_68]
0x1800578cb  test    rcx, rcx
0x1800578ce  jz      short loc_1800578DD
0x1800578d0  mov     rax, [rcx]
0x1800578d3  mov     rax, [rax+10h]
0x1800578d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578dc  nop
0x1800578dd  mov     rcx, [rbp+57h+var_A8]
0x1800578e1  test    rcx, rcx
0x1800578e4  jz      short loc_1800578F3
0x1800578e6  mov     rax, [rcx]
0x1800578e9  mov     rax, [rax+10h]
0x1800578ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578f2  nop
0x1800578f3  mov     rcx, [rbp+57h+var_A0]
0x1800578f7  test    rcx, rcx
0x1800578fa  jz      short loc_180057909
0x1800578fc  mov     rax, [rcx]
0x1800578ff  mov     rax, [rax+10h]
0x180057903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057908  nop
0x180057909  mov     rcx, [rbp+57h+var_98]
0x18005790d  test    rcx, rcx
0x180057910  jz      short loc_18005791F
0x180057912  mov     rax, [rcx]
0x180057915  mov     rax, [rax+10h]
0x180057919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005791e  nop
0x18005791f  mov     rcx, [rbp+57h+var_90]
0x180057923  test    rcx, rcx
0x180057926  jz      short loc_180057935
0x180057928  mov     rax, [rcx]
0x18005792b  mov     rax, [rax+10h]
0x18005792f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057934  nop
0x180057935  mov     rcx, [rbp+57h+var_88]
0x180057939  test    rcx, rcx
0x18005793c  jz      short loc_18005794B
0x18005793e  mov     rax, [rcx]
0x180057941  mov     rax, [rax+10h]
0x180057945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005794a  nop
0x18005794b  mov     rcx, [rbp+57h+var_80]
0x18005794f  test    rcx, rcx
0x180057952  jz      short loc_180057961
0x180057954  mov     rax, [rcx]
0x180057957  mov     rax, [rax+10h]
0x18005795b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057960  nop
0x180057961  mov     rcx, [rbp+57h+pv]; pv
0x180057965  test    rcx, rcx
0x180057968  jz      short loc_180057976
0x18005796a  call    cs:__imp_CoTaskMemFree
0x180057971  nop     dword ptr [rax+rax+00h]
0x180057976  mov     eax, ebx
0x180057978  jmp     loc_1800587C6
0x18005797d  mov     rbx, [rbp+57h+var_68]
0x180057981  mov     [rbx+30h], rdi
0x180057985  mov     dword ptr [rbx+78h], 1
0x18005798c  mov     rdi, [rbx+88h]
0x180057993  mov     [rbx+88h], rsi
0x18005799a  test    rsi, rsi
0x18005799d  jz      short loc_1800579AE
0x18005799f  mov     rax, [rsi]
0x1800579a2  mov     rcx, rsi
0x1800579a5  mov     rax, [rax+8]
0x1800579a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579ae  test    rdi, rdi
0x1800579b1  jz      short loc_1800579C3
0x1800579b3  mov     rax, [rdi]
0x1800579b6  mov     rcx, rdi
0x1800579b9  mov     rax, [rax+10h]
0x1800579bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579c2  nop
0x1800579c3  mov     [rbx+0A0h], r14d
0x1800579ca  mov     rax, [rsi]
0x1800579cd  mov     rdi, [rax+38h]
0x1800579d1  mov     rcx, [rbp+57h+var_80]
0x1800579d5  mov     [rbp+57h+var_80], r15
0x1800579d9  test    rcx, rcx
0x1800579dc  jz      short loc_1800579EB
0x1800579de  mov     rdx, [rcx]
0x1800579e1  mov     rax, [rdx+10h]
0x1800579e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579ea  nop
0x1800579eb  lea     rdx, [rbp+57h+var_80]
0x1800579ef  mov     rcx, rsi
0x1800579f2  mov     rax, rdi
0x1800579f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579fa  mov     edi, eax
0x1800579fc  test    eax, eax
0x1800579fe  jns     loc_180057AD9
0x180057a04  mov     rcx, [rbp+5Fh]; this
0x180057a08  lea     rax, aFailedToGetMan_1; "Failed to get manifest reader for packa"...
0x180057a0f  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180057a14  mov     r9d, edi; char *
0x180057a17  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180057a1e  mov     edx, 27h ; '''; void *
0x180057a23  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180057a28  nop
0x180057a29  mov     rax, [rbx]
0x180057a2c  mov     rcx, rbx
0x180057a2f  mov     rax, [rax+10h]
0x180057a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a38  nop
0x180057a39  mov     rcx, [rbp+57h+var_A8]
0x180057a3d  test    rcx, rcx
0x180057a40  jz      short loc_180057A4F
0x180057a42  mov     rax, [rcx]
0x180057a45  mov     rax, [rax+10h]
0x180057a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a4e  nop
0x180057a4f  mov     rcx, [rbp+57h+var_A0]
0x180057a53  test    rcx, rcx
0x180057a56  jz      short loc_180057A65
0x180057a58  mov     rax, [rcx]
0x180057a5b  mov     rax, [rax+10h]
0x180057a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a64  nop
0x180057a65  mov     rcx, [rbp+57h+var_98]
0x180057a69  test    rcx, rcx
0x180057a6c  jz      short loc_180057A7B
0x180057a6e  mov     rax, [rcx]
0x180057a71  mov     rax, [rax+10h]
0x180057a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a7a  nop
0x180057a7b  mov     rcx, [rbp+57h+var_90]
0x180057a7f  test    rcx, rcx
0x180057a82  jz      short loc_180057A91
0x180057a84  mov     rax, [rcx]
0x180057a87  mov     rax, [rax+10h]
0x180057a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a90  nop
0x180057a91  mov     rcx, [rbp+57h+var_88]
0x180057a95  test    rcx, rcx
0x180057a98  jz      short loc_180057AA7
0x180057a9a  mov     rax, [rcx]
0x180057a9d  mov     rax, [rax+10h]
0x180057aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aa6  nop
0x180057aa7  mov     rcx, [rbp+57h+var_80]
0x180057aab  test    rcx, rcx
0x180057aae  jz      short loc_180057ABD
0x180057ab0  mov     rax, [rcx]
0x180057ab3  mov     rax, [rax+10h]
0x180057ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057abc  nop
0x180057abd  mov     rcx, [rbp+57h+pv]; pv
0x180057ac1  test    rcx, rcx
0x180057ac4  jz      short loc_180057AD2
0x180057ac6  call    cs:__imp_CoTaskMemFree
0x180057acd  nop     dword ptr [rax+rax+00h]
0x180057ad2  mov     eax, edi
0x180057ad4  jmp     loc_1800587C6
0x180057ad9  mov     rdi, [rbp+57h+var_80]
0x180057add  mov     rax, [rdi]
0x180057ae0  mov     r14, [rax+18h]
0x180057ae4  mov     rcx, [rbp+57h+var_88]
0x180057ae8  mov     [rbp+57h+var_88], r15
0x180057aec  test    rcx, rcx
0x180057aef  jz      short loc_180057AFE
0x180057af1  mov     rdx, [rcx]
0x180057af4  mov     rax, [rdx+10h]
0x180057af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057afd  nop
0x180057afe  lea     rdx, [rbp+57h+var_88]
0x180057b02  mov     rcx, rdi
0x180057b05  mov     rax, r14
0x180057b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b0d  mov     edi, eax
0x180057b0f  test    eax, eax
0x180057b11  jns     loc_180057BD5
0x180057b17  mov     rcx, [rbp+5Fh]; this
0x180057b1b  lea     rax, aFailedToGetPac_3; "Failed to get package id for package."
0x180057b22  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180057b27  mov     r9d, edi; char *
0x180057b2a  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180057b31  mov     edx, 28h ; '('; void *
0x180057b36  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180057b3b  nop
0x180057b3c  mov     rax, [rbx]
0x180057b3f  mov     rcx, rbx
0x180057b42  mov     rax, [rax+10h]
0x180057b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b4b  nop
0x180057b4c  mov     rcx, [rbp+57h+var_A8]
0x180057b50  test    rcx, rcx
0x180057b53  jz      short loc_180057B62
0x180057b55  mov     rax, [rcx]
0x180057b58  mov     rax, [rax+10h]
0x180057b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b61  nop
0x180057b62  mov     rcx, [rbp+57h+var_A0]
0x180057b66  test    rcx, rcx
0x180057b69  jz      short loc_180057B78
0x180057b6b  mov     rax, [rcx]
0x180057b6e  mov     rax, [rax+10h]
0x180057b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b77  nop
0x180057b78  mov     rcx, [rbp+57h+var_98]
0x180057b7c  test    rcx, rcx
0x180057b7f  jz      short loc_180057B8E
0x180057b81  mov     rax, [rcx]
0x180057b84  mov     rax, [rax+10h]
0x180057b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b8d  nop
0x180057b8e  mov     rcx, [rbp+57h+var_90]
0x180057b92  test    rcx, rcx
0x180057b95  jz      short loc_180057BA4
0x180057b97  mov     rax, [rcx]
0x180057b9a  mov     rax, [rax+10h]
0x180057b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ba3  nop
0x180057ba4  mov     rcx, [rbp+57h+var_88]
0x180057ba8  test    rcx, rcx
0x180057bab  jz      short loc_180057BBA
0x180057bad  mov     rax, [rcx]
0x180057bb0  mov     rax, [rax+10h]
0x180057bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bb9  nop
0x180057bba  mov     rcx, [rbp+57h+var_80]
0x180057bbe  test    rcx, rcx
0x180057bc1  jz      short loc_180057BD0
0x180057bc3  mov     rax, [rcx]
0x180057bc6  mov     rax, [rax+10h]
0x180057bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bcf  nop
0x180057bd0  jmp     loc_180057ABD
0x180057bd5  mov     r15, [rbp+57h+var_88]
0x180057bd9  mov     rax, [r15]
0x180057bdc  mov     r12, [rax+48h]
0x180057be0  mov     r14, [rbp+57h+pv]
0x180057be4  test    r14, r14
0x180057be7  jz      short loc_180057C14
0x180057be9  call    cs:__imp_GetLastError
0x180057bf0  nop     dword ptr [rax+rax+00h]
0x180057bf5  mov     edi, eax
0x180057bf7  mov     rcx, r14; pv
0x180057bfa  call    cs:__imp_CoTaskMemFree
0x180057c01  nop     dword ptr [rax+rax+00h]
0x180057c06  mov     ecx, edi; dwErrCode
0x180057c08  call    cs:__imp_SetLastError
0x180057c0f  nop     dword ptr [rax+rax+00h]
0x180057c14  mov     [rbp+57h+pv], 0
0x180057c1c  lea     rdx, [rbp+57h+pv]
0x180057c20  mov     rcx, r15
0x180057c23  mov     rax, r12
0x180057c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c2b  mov     edi, eax
0x180057c2d  xor     r15d, r15d
0x180057c30  test    eax, eax
0x180057c32  jns     loc_180057CF5
0x180057c38  mov     rcx, [rbp+5Fh]; this
0x180057c3c  lea     rax, aFailedToGetPac_1; "Failed to get package full name for pac"...
0x180057c43  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180057c48  mov     r9d, edi; char *
0x180057c4b  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180057c52  lea     edx, [r15+29h]; void *
0x180057c56  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
  ... truncated ...
```
