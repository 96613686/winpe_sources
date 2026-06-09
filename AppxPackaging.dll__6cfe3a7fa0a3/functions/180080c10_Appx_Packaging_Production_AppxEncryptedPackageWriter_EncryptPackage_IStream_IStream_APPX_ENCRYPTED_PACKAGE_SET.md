# Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage(IStream *,IStream *,APPX_ENCRYPTED_PACKAGE_SETTINGS2 const *,APPX_KEY_INFO const *,APPX_ENCRYPTED_EXEMPTIONS const *,bool,unsigned __int64,Appx::Packaging::AppxEncryptedPackageEditor * *)

- ea: `0x180080c10`
- end: `0x180081596`
- name: `?EncryptPackage@AppxEncryptedPackageWriter@Production@Packaging@Appx@@SAJPEAUIStream@@0PEBUAPPX_ENCRYPTED_PACKAGE_SETTINGS2@@PEBUAPPX_KEY_INFO@@PEBUAPPX_ENCRYPTED_EXEMPTIONS@@_N_KPEAPEAVAppxEncryptedPackageEditor@34@@Z`
- size: `2438`
- prototype: `__int64 __usercall@<rax>(struct IStream *@<rcx>, struct IStream *@<rdx>, const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *@<r8>, const struct APPX_KEY_INFO *@<r9>, const struct APPX_ENCRYPTED_EXEMPTIONS *, bool, unsigned __int64, struct Appx::Packaging::AppxEncryptedPackageEditor **)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c52d0`
- `0x1800c5320`
- `0x1800f1414`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180046f00`
- `0x180071f50`
- `0x180080c10`
- `0x18008159c`
- `0x1800816b8`
- `0x180081724`
- `0x180082690`
- `0x1800992c4`
- `0x1800992d0`
- `0x18009d3d0`
- `0x1800baeb0`
- `0x1800f0c2c`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800814dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008153f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800814dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008153f`

## string_xrefs

- `0x180080c4b`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080cb9`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080cfa`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080d46`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080d90`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080e15`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080e6f`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080ed1`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080f45`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180080f92`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x18008115b`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x1800811ac`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180081295`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x18008135d`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x1800813dd`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x18008152c`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180081551`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`
- `0x180081574`: `onecore\printscan\appxpackaging\production\src\appxencryptedpackagewriter.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage(
        struct IStream *a1,
        struct IStream *a2,
        const struct APPX_ENCRYPTED_PACKAGE_SETTINGS2 *a3,
        const struct APPX_KEY_INFO *a4,
        const struct APPX_ENCRYPTED_EXEMPTIONS *a5,
        bool a6,
        unsigned __int64 a7,
        struct Appx::Packaging::AppxEncryptedPackageEditor **a8)
{
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int valid; // eax
  int v15; // eax
  struct IAppxPackageReader *v16; // rdi
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, struct IStream **); // rbx
  int v21; // eax
  struct IAppxPackageReader *v22; // rdi
  HRESULT (__stdcall *v23)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rbx
  int v24; // eax
  struct IAppxPackageReader *v25; // rbx
  int v26; // r14d
  HRESULT (__stdcall *QueryInterface)(IAppxPackageReader *, const IID *const, void **); // rdi
  int v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r9
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, struct IStream **); // rbx
  int v36; // eax
  struct IAppxPackageReader *v37; // rdi
  HRESULT (__stdcall *GetPayloadFiles)(IAppxPackageReader *, IAppxFilesEnumerator **); // rbx
  int v39; // eax
  struct Appx::Packaging::AppxEncryptedPackageEditor **v40; // r13
  int v41; // eax
  __int64 v42; // rdx
  void (__fastcall *v43)(__int64, int *); // rax
  __int64 v44; // rbx
  unsigned __int64 v45; // rsi
  _QWORD *v46; // rax
  _DWORD *v47; // r14
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  int v50; // eax
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, _DWORD *); // rbx
  unsigned __int64 v53; // rsi
  __int64 v54; // rdx
  unsigned __int64 v55; // rax
  unsigned __int64 v56; // rdx
  _QWORD *v57; // r14
  unsigned __int64 i; // rcx
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 v61; // rdx
  _QWORD *v62; // rax
  __int64 v63; // rax
  Appx::Packaging::Production::AppxEncryptedPackageWriter *v64; // rbx
  __int64 (__fastcall *v65)(Appx::Packaging::Production::AppxEncryptedPackageWriter *, GUID *, __int64 *); // rdi
  int v66; // edi
  __int64 v67; // rdx
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // rdx
  unsigned __int64 v71; // rdx
  __int64 v72; // rsi
  __int64 (__fastcall *v73)(__int64, __int64 *); // rdi
  int v74; // eax
  __int64 v75; // rsi
  __int64 (__fastcall *v76)(__int64, __int64 *); // rdi
  int v77; // eax
  __int64 v78; // rdx
  int v79; // [rsp+20h] [rbp-C1h]
  int v80; // [rsp+20h] [rbp-C1h]
  __int64 v81; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v82; // [rsp+48h] [rbp-99h] BYREF
  __int64 v83; // [rsp+50h] [rbp-91h] BYREF
  __int64 v84; // [rsp+58h] [rbp-89h] BYREF
  struct IStream *v85; // [rsp+60h] [rbp-81h] BYREF
  Appx::Packaging::Production::AppxEncryptedPackageWriter *v86; // [rsp+68h] [rbp-79h] BYREF
  __int64 v87; // [rsp+70h] [rbp-71h] BYREF
  __int64 v88; // [rsp+78h] [rbp-69h] BYREF
  struct IAppxPackageReader *v89; // [rsp+80h] [rbp-61h] BYREF
  __int64 v90; // [rsp+88h] [rbp-59h] BYREF
  __int64 v91; // [rsp+90h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-49h] BYREF
  int v93; // [rsp+A0h] [rbp-41h] BYREF
  unsigned int v94; // [rsp+A4h] [rbp-3Dh] BYREF
  __int64 v95; // [rsp+A8h] [rbp-39h] BYREF
  struct IStream *v96; // [rsp+B0h] [rbp-31h] BYREF
  _QWORD v97[2]; // [rsp+B8h] [rbp-29h] BYREF
  unsigned __int64 v98; // [rsp+C8h] [rbp-19h]
  char v99; // [rsp+D0h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]
  int v101; // [rsp+130h] [rbp+4Fh] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v12 = 174;
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v12 = 175;
      goto LABEL_3;
    }
    if ( !a3->keyLength )
    {
      v13 = -2147024809;
      v12 = 176;
      goto LABEL_4;
    }
    if ( !a3->encryptionAlgorithm )
    {
      v12 = 177;
      goto LABEL_3;
    }
    if ( !a3->blockMapHashAlgorithm )
    {
      v12 = 178;
      goto LABEL_3;
    }
    if ( a4 )
    {
      valid = Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(a4);
      v13 = valid;
      if ( valid < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
          (const char *)(unsigned int)valid,
          v79);
        return v13;
      }
    }
    v89 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v89);
    v15 = Appx::Packaging::Consumption::AppxPackageReader::Create(a1, 1, 0, &v89);
    v13 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v15,
        v79);
LABEL_90:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v89);
      return v13;
    }
    v16 = v89;
    v95 = 0;
    GetFootprintFile = v89->lpVtbl->GetFootprintFile;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v95);
    v18 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, _QWORD, __int64 *))GetFootprintFile)(v16, 0, &v95);
    v13 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v18,
        v79);
LABEL_89:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v95);
      goto LABEL_90;
    }
    v19 = v95;
    v96 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v95 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v96);
    v21 = v20(v19, &v96);
    v13 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v21,
        v79);
LABEL_88:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v96);
      goto LABEL_89;
    }
    v22 = v89;
    v82 = 0;
    v23 = v89->lpVtbl->GetFootprintFile;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
    v24 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))v23)(v22, 4, &v82);
    v25 = v89;
    v26 = v24;
    v81 = 0;
    QueryInterface = v89->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v81);
    v28 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, GUID *, __int64 *))QueryInterface)(
            v25,
            &GUID_7b15dcbd_0419_4b53_8c9a_09d3edc73cf5,
            &v81);
    v13 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v28,
        v79);
LABEL_87:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
      goto LABEL_88;
    }
    v29 = v81;
    v84 = 0;
    v93 = 0;
    v30 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v84);
    v31 = v30(v29, &v84);
    v13 = v31;
    if ( v31 < 0 )
    {
      v32 = 199;
LABEL_28:
      v33 = (unsigned int)v31;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)v33,
        v79);
LABEL_86:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v84);
      goto LABEL_87;
    }
    v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v84 + 32LL))(v84, &v93);
    v13 = v31;
    if ( v31 < 0 )
    {
      v32 = 200;
      goto LABEL_28;
    }
    if ( v93 )
    {
      v13 = -2147024846;
      v32 = 201;
      v33 = 2147942450LL;
      goto LABEL_29;
    }
    if ( (int)(v26 + 0x80000000) >= 0 && v26 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v26,
        v79);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v84);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
      v13 = v26;
      goto LABEL_88;
    }
    v85 = 0;
    if ( v26 >= 0 )
    {
      v34 = v82;
      v35 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v82 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v85);
      v36 = v35(v34, &v85);
      v13 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
          (const char *)(unsigned int)v36,
          v79);
LABEL_85:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v85);
        goto LABEL_86;
      }
    }
    v37 = v89;
    v83 = 0;
    GetPayloadFiles = v89->lpVtbl->GetPayloadFiles;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v83);
    v39 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64 *))GetPayloadFiles)(v37, &v83);
    v13 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v39,
        v79);
LABEL_84:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v83);
      goto LABEL_85;
    }
    v86 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v86);
    v40 = a8;
    v41 = Appx::Packaging::Production::AppxEncryptedPackageWriter::Create(a8 == 0, a2, v96, v85, a3, a4, a5, &v86);
    v13 = v41;
    if ( v41 < 0 )
    {
      v42 = 227;
      goto LABEL_82;
    }
    v101 = 0;
    v43 = *(void (__fastcall **)(__int64, int *))(*(_QWORD *)v83 + 32LL);
    if ( !a6 )
    {
      v43(v83, &v101);
      v64 = v86;
      while ( 1 )
      {
        if ( v101 != 1 )
          goto LABEL_80;
        v72 = v83;
        v88 = 0;
        v73 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 24LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v88);
        v74 = v73(v72, &v88);
        v66 = v74;
        if ( v74 < 0 )
          break;
        v75 = v88;
        v90 = 0;
        v76 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 56LL);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v90);
        v77 = v76(v75, &v90);
        v66 = v77;
        if ( v77 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x124,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
            (const char *)(unsigned int)v77,
            v80);
          goto LABEL_106;
        }
        pv = 0;
        v66 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v88 + 40LL))(v88, &pv);
        if ( v66 < 0 )
        {
          v78 = 294;
LABEL_104:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v78,
            (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
            (const char *)(unsigned int)v66,
            v80);
          CoTaskMemFree(pv);
LABEL_106:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v90);
LABEL_108:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v88);
          goto LABEL_76;
        }
        v94 = 0;
        v66 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v88 + 24LL))(v88, &v94);
        if ( v66 < 0 )
        {
          v78 = 297;
          goto LABEL_104;
        }
        v66 = (*(__int64 (__fastcall **)(Appx::Packaging::Production::AppxEncryptedPackageWriter *, LPVOID, _QWORD, __int64))(*(_QWORD *)v64 + 24LL))(
                v64,
                pv,
                v94,
                v90);
        if ( v66 < 0 )
        {
          v78 = 302;
          goto LABEL_104;
        }
        CoTaskMemFree(pv);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v90);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v88);
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v83 + 40LL))(v83, &v101);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)(unsigned int)v74,
        v80);
      goto LABEL_108;
    }
    v44 = 0;
    v97[1] = 0;
    v97[0] = 0;
    v99 = 1;
    v45 = 0;
    v98 = 0;
    v43(v83, &v101);
    while ( v101 == 1 )
    {
      v46 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v47 = v46;
      if ( !v46 )
      {
        v13 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
          (const char *)0x8007000ELL,
          v80);
        goto LABEL_56;
      }
      v46[2] = 0;
      *v46 = 0;
      v46[1] = 0;
      v48 = v83;
      v87 = 0;
      v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 24LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v87);
      v50 = v49(v48, &v87);
      v13 = v50;
      if ( v50 < 0 )
      {
        v54 = 251;
LABEL_55:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v54,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
          (const char *)(unsigned int)v50,
          v80);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v87);
        Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData::_scalar_deleting_destructor_(v47);
LABEL_56:
        Common::Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___::_Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___(v97);
        goto LABEL_83;
      }
      v51 = v87;
      v52 = *(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v87 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v47);
      v50 = v52(v51, v47);
      v13 = v50;
      if ( v50 < 0 )
      {
        v54 = 253;
        goto LABEL_55;
      }
      v50 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v87 + 40LL))(v87, v47 + 2);
      v13 = v50;
      if ( v50 < 0 )
      {
        v54 = 254;
        goto LABEL_55;
      }
      v47[4] = 0;
      v50 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 24LL))(v87);
      v13 = v50;
      if ( v50 < 0 )
      {
        v54 = 257;
        goto LABEL_55;
      }
      v50 = Common::Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___::EnsureCapacity(
              v97,
              v45 + 1);
      v13 = v50;
      if ( v50 < 0 )
      {
        v54 = 259;
        goto LABEL_55;
      }
      v53 = v98;
      v44 = v97[0];
      *(_QWORD *)(v97[0] + 8 * v98) = v47;
      v45 = v53 + 1;
      v98 = v45;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v87);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v83 + 40LL))(v83, &v101);
    }
    v55 = 32 * v45;
    if ( !is_mul_ok(v45, 0x20u) )
      v55 = -1;
    v57 = operator new[](v55, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v57 )
    {
      v13 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
        (const char *)0x8007000ELL,
        v80);
      operator delete(0, v71);
      goto LABEL_56;
    }
    operator delete(0, v56);
    for ( i = 0; i < v45; v57[v61 + 2] = 0 )
    {
      v59 = 8 * i;
      v60 = 0;
      if ( i < v45 )
        v60 = *(_QWORD *)(v44 + 8 * i);
      v61 = 4 * i;
      v57[4 * i + 1] = *(_QWORD *)(v60 + 8);
      v62 = 0;
      if ( i < v45 )
        v62 = *(_QWORD **)(v59 + v44);
      v57[v61] = *v62;
      v63 = 0;
      if ( i < v45 )
        v63 = *(_QWORD *)(v59 + v44);
      ++i;
      LODWORD(v57[v61 + 3]) = *(_DWORD *)(v63 + 16);
    }
    v64 = v86;
    v91 = 0;
    v65 = **(__int64 (__fastcall ***)(Appx::Packaging::Production::AppxEncryptedPackageWriter *, GUID *, __int64 *))v86;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v91);
    v66 = v65(v64, &GUID_3e475447_3a25_40b5_8ad2_f953ae50c92d, &v91);
    if ( v66 >= 0 )
    {
      v66 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, unsigned __int64))(*(_QWORD *)v91 + 24LL))(
              v91,
              (unsigned int)v45,
              v57,
              a7);
      if ( v66 >= 0 )
      {
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v91);
        operator delete(v57, v69);
        Common::Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___::_Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___(v97);
LABEL_80:
        v41 = Appx::Packaging::Production::AppxEncryptedPackageWriter::Close(v64, v40);
        v13 = v41;
        if ( v41 >= 0 )
          goto LABEL_83;
        v42 = 307;
LABEL_82:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v42,
          (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
          (const char *)(unsigned int)v41,
          v80);
LABEL_83:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v86);
        goto LABEL_84;
      }
      v67 = 283;
    }
    else
    {
      v67 = 278;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v67,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
      (const char *)(unsigned int)v66,
      v80);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v91);
    operator delete(v57, v68);
    Common::Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___::_Array__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::ContainerOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage::I__::I_::FileData__Common::NoKey_Common::ContainerOperations_Common::NoKey__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData__Common::ArrayOperations__Appx::Packaging::Production::AppxEncryptedPackageWriter::EncryptPackage__::I_::FileData_Common::NoKey___(v97);
LABEL_76:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v86);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v83);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v85);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v84);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v81);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v82);
    v13 = v66;
    goto LABEL_88;
  }
  v12 = 173;
LABEL_3:
  v13 = -2147467261;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxencryptedpackagewriter.cpp",
    (const char *)v13,
    v79);
  return v13;
}

```

## disassembly

```asm
0x180080c10  push    rbp
0x180080c12  push    rbx
0x180080c13  push    rsi
0x180080c14  push    rdi
0x180080c15  push    r12
0x180080c17  push    r13
0x180080c19  push    r14
0x180080c1b  push    r15
0x180080c1d  lea     rbp, [rsp-7]
0x180080c22  sub     rsp, 0E8h
0x180080c29  xor     r13d, r13d
0x180080c2c  mov     r15, r9
0x180080c2f  mov     rsi, r8
0x180080c32  mov     r12, rdx
0x180080c35  mov     rdi, rcx
0x180080c38  test    rcx, rcx
0x180080c3b  jnz     short loc_180080C5F
0x180080c3d  mov     edx, 0ADh; void *
0x180080c42  mov     ebx, 80004003h
0x180080c47  mov     rcx, [rbp+47h]; this
0x180080c4b  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080c52  mov     r9d, ebx; char *
0x180080c55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080c5a  jmp     loc_1800813C2
0x180080c5f  test    r12, r12
0x180080c62  jnz     short loc_180080C6B
0x180080c64  mov     edx, 0AEh
0x180080c69  jmp     short loc_180080C42
0x180080c6b  test    rsi, rsi
0x180080c6e  jnz     short loc_180080C77
0x180080c70  mov     edx, 0AFh
0x180080c75  jmp     short loc_180080C42
0x180080c77  cmp     [r8], r13d
0x180080c7a  jnz     short loc_180080C88
0x180080c7c  mov     ebx, 80070057h
0x180080c81  mov     edx, 0B0h
0x180080c86  jmp     short loc_180080C47
0x180080c88  cmp     [r8+8], r13
0x180080c8c  jnz     short loc_180080C95
0x180080c8e  mov     edx, 0B1h
0x180080c93  jmp     short loc_180080C42
0x180080c95  cmp     [r8+10h], r13
0x180080c99  jnz     short loc_180080CA2
0x180080c9b  mov     edx, 0B2h
0x180080ca0  jmp     short loc_180080C42
0x180080ca2  test    r15, r15
0x180080ca5  jz      short loc_180080CD2
0x180080ca7  mov     rcx, r15; struct APPX_KEY_INFO *
0x180080caa  call    ?ValidAppxKeyInfo@EncryptionHelper@Packaging@Appx@@SAJAEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(APPX_KEY_INFO const &)
0x180080caf  mov     ebx, eax
0x180080cb1  test    eax, eax
0x180080cb3  jns     short loc_180080CD2
0x180080cb5  mov     rcx, [rbp+47h]; this
0x180080cb9  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080cc0  mov     r9d, eax; char *
0x180080cc3  mov     edx, 0B4h; void *
0x180080cc8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080ccd  jmp     loc_1800813C2
0x180080cd2  lea     rcx, [rbp+3Fh+var_A0]
0x180080cd6  mov     [rbp+3Fh+var_A0], r13
0x180080cda  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080cdf  lea     r9, [rbp+3Fh+var_A0]; struct IAppxPackageReader **
0x180080ce3  xor     r8d, r8d; unsigned __int16 *
0x180080ce6  mov     dl, 1; bool
0x180080ce8  mov     rcx, rdi; struct IStream *
0x180080ceb  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,IAppxPackageReader * *)
0x180080cf0  mov     ebx, eax
0x180080cf2  test    eax, eax
0x180080cf4  jns     short loc_180080D13
0x180080cf6  mov     rcx, [rbp+47h]; this
0x180080cfa  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080d01  mov     r9d, eax; char *
0x180080d04  mov     edx, 0B8h; void *
0x180080d09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080d0e  jmp     loc_1800813B9
0x180080d13  mov     rdi, [rbp+3Fh+var_A0]
0x180080d17  lea     rcx, [rbp+3Fh+var_78]
0x180080d1b  mov     [rbp+3Fh+var_78], r13
0x180080d1f  mov     rax, [rdi]
0x180080d22  mov     rbx, [rax+20h]
0x180080d26  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080d2b  lea     r8, [rbp+3Fh+var_78]
0x180080d2f  xor     edx, edx
0x180080d31  mov     rcx, rdi
0x180080d34  mov     rax, rbx
0x180080d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080d3c  mov     ebx, eax
0x180080d3e  test    eax, eax
0x180080d40  jns     short loc_180080D5F
0x180080d42  mov     rcx, [rbp+47h]; this
0x180080d46  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080d4d  mov     r9d, eax; char *
0x180080d50  mov     edx, 0BAh; void *
0x180080d55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080d5a  jmp     loc_1800813B0
0x180080d5f  mov     rdi, [rbp+3Fh+var_78]
0x180080d63  lea     rcx, [rbp+3Fh+var_70]
0x180080d67  mov     [rbp+3Fh+var_70], r13
0x180080d6b  mov     rax, [rdi]
0x180080d6e  mov     rbx, [rax+38h]
0x180080d72  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080d77  lea     rdx, [rbp+3Fh+var_70]
0x180080d7b  mov     rcx, rdi
0x180080d7e  mov     rax, rbx
0x180080d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080d86  mov     ebx, eax
0x180080d88  test    eax, eax
0x180080d8a  jns     short loc_180080DA9
0x180080d8c  mov     rcx, [rbp+47h]; this
0x180080d90  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080d97  mov     r9d, eax; char *
0x180080d9a  mov     edx, 0BCh; void *
0x180080d9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080da4  jmp     loc_1800813A7
0x180080da9  mov     rdi, [rbp+3Fh+var_A0]
0x180080dad  lea     rcx, [rsp+120h+var_D8]
0x180080db2  mov     [rsp+120h+var_D8], r13
0x180080db7  mov     rax, [rdi]
0x180080dba  mov     rbx, [rax+20h]
0x180080dbe  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080dc3  lea     r8, [rsp+120h+var_D8]
0x180080dc8  mov     edx, 4
0x180080dcd  mov     rcx, rdi
0x180080dd0  mov     rax, rbx
0x180080dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080dd8  mov     rbx, [rbp+3Fh+var_A0]
0x180080ddc  mov     r14d, eax
0x180080ddf  mov     [rsp+120h+var_E0], r13
0x180080de4  mov     rcx, [rbx]
0x180080de7  mov     rdi, [rcx]
0x180080dea  lea     rcx, [rsp+120h+var_E0]
0x180080def  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080df4  lea     r8, [rsp+120h+var_E0]
0x180080df9  mov     rcx, rbx
0x180080dfc  lea     rdx, _GUID_7b15dcbd_0419_4b53_8c9a_09d3edc73cf5
0x180080e03  mov     rax, rdi
0x180080e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e0b  mov     ebx, eax
0x180080e0d  test    eax, eax
0x180080e0f  jns     short loc_180080E2E
0x180080e11  mov     rcx, [rbp+47h]; this
0x180080e15  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080e1c  mov     r9d, eax; char *
0x180080e1f  mov     edx, 0C4h; void *
0x180080e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080e29  jmp     loc_180081393
0x180080e2e  mov     rdi, [rsp+120h+var_E0]
0x180080e33  lea     rcx, [rsp+120h+var_C8]
0x180080e38  mov     [rsp+120h+var_C8], r13
0x180080e3d  mov     [rbp+3Fh+var_80], r13d
0x180080e41  mov     rax, [rdi]
0x180080e44  mov     rbx, [rax+20h]
0x180080e48  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080e4d  lea     rdx, [rsp+120h+var_C8]
0x180080e52  mov     rcx, rdi
0x180080e55  mov     rax, rbx
0x180080e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e5d  mov     ebx, eax
0x180080e5f  test    eax, eax
0x180080e61  jns     short loc_180080E80
0x180080e63  mov     edx, 0C7h; void *
0x180080e68  mov     r9d, eax; char *
0x180080e6b  mov     rcx, [rbp+47h]; this
0x180080e6f  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080e76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080e7b  jmp     loc_180081389
0x180080e80  mov     rcx, [rsp+120h+var_C8]
0x180080e85  lea     rdx, [rbp+3Fh+var_80]
0x180080e89  mov     rax, [rcx]
0x180080e8c  mov     rax, [rax+20h]
0x180080e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e95  mov     ebx, eax
0x180080e97  test    eax, eax
0x180080e99  jns     short loc_180080EA2
0x180080e9b  mov     edx, 0C8h
0x180080ea0  jmp     short loc_180080E68
0x180080ea2  cmp     [rbp+3Fh+var_80], r13d
0x180080ea6  jz      short loc_180080EB7
0x180080ea8  mov     ebx, 80070032h
0x180080ead  mov     edx, 0C9h
0x180080eb2  mov     r9d, ebx
0x180080eb5  jmp     short loc_180080E6B
0x180080eb7  mov     ecx, 80000000h
0x180080ebc  lea     eax, [r14+rcx]
0x180080ec0  test    ecx, eax
0x180080ec2  jnz     short loc_180080F0B
0x180080ec4  cmp     r14d, 80070002h
0x180080ecb  jz      short loc_180080F0B
0x180080ecd  mov     rcx, [rbp+47h]; this
0x180080ed1  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080ed8  mov     r9d, r14d; char *
0x180080edb  mov     edx, 0CDh; void *
0x180080ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080ee5  lea     rcx, [rsp+120h+var_C8]
0x180080eea  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080eef  lea     rcx, [rsp+120h+var_E0]
0x180080ef4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080ef9  lea     rcx, [rsp+120h+var_D8]
0x180080efe  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080f03  mov     ebx, r14d
0x180080f06  jmp     loc_1800813A7
0x180080f0b  mov     [rsp+120h+var_C0], r13
0x180080f10  test    r14d, r14d
0x180080f13  js      short loc_180080F5E
0x180080f15  mov     rdi, [rsp+120h+var_D8]
0x180080f1a  lea     rcx, [rsp+120h+var_C0]
0x180080f1f  mov     rax, [rdi]
0x180080f22  mov     rbx, [rax+38h]
0x180080f26  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080f2b  lea     rdx, [rsp+120h+var_C0]
0x180080f30  mov     rcx, rdi
0x180080f33  mov     rax, rbx
0x180080f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f3b  mov     ebx, eax
0x180080f3d  test    eax, eax
0x180080f3f  jns     short loc_180080F5E
0x180080f41  mov     rcx, [rbp+47h]; this
0x180080f45  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080f4c  mov     r9d, eax; char *
0x180080f4f  mov     edx, 0D3h; void *
0x180080f54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080f59  jmp     loc_18008137F
0x180080f5e  mov     rdi, [rbp+3Fh+var_A0]
0x180080f62  lea     rcx, [rsp+120h+var_D0]
0x180080f67  mov     [rsp+120h+var_D0], r13
0x180080f6c  mov     rax, [rdi]
0x180080f6f  mov     rbx, [rax+30h]
0x180080f73  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080f78  lea     rdx, [rsp+120h+var_D0]
0x180080f7d  mov     rcx, rdi
0x180080f80  mov     rax, rbx
0x180080f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080f88  mov     ebx, eax
0x180080f8a  test    eax, eax
0x180080f8c  jns     short loc_180080FAB
0x180080f8e  mov     rcx, [rbp+47h]; this
0x180080f92  lea     r8, aOnecorePrintsc_136; "onecore\\printscan\\appxpackaging\\prod"...
0x180080f99  mov     r9d, eax; char *
0x180080f9c  mov     edx, 0D7h; void *
0x180080fa1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080fa6  jmp     loc_180081375
0x180080fab  lea     rcx, [rbp+3Fh+var_B8]
0x180080faf  mov     [rbp+3Fh+var_B8], r13
0x180080fb3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080fb8  mov     r13, [rbp+3Fh+arg_38]
0x180080fbf  lea     rax, [rbp+3Fh+var_B8]
0x180080fc3  mov     r9, [rsp+120h+var_C0]; struct IStream *
0x180080fc8  test    r13, r13
0x180080fcb  mov     r8, [rbp+3Fh+var_70]; struct IStream *
0x180080fcf  mov     rdx, r12; struct IStream *
0x180080fd2  mov     [rsp+120h+var_E8], rax; struct Appx::Packaging::Production::AppxEncryptedPackageWriter **
0x180080fd7  setz    cl; bool
0x180080fda  mov     rax, [rbp+3Fh+arg_20]
0x180080fde  mov     [rsp+120h+var_F0], rax; struct APPX_ENCRYPTED_EXEMPTIONS *
0x180080fe3  mov     [rsp+120h+var_F8], r15; struct APPX_KEY_INFO *
0x180080fe8  mov     [rsp+120h+var_100], rsi; int
0x180080fed  call    ?Create@AppxEncryptedPackageWriter@Production@Packaging@Appx@@CAJ_NPEAUIStream@@11PEBUAPPX_ENCRYPTED_PACKAGE_SETTINGS2@@PEBUAPPX_KEY_INFO@@PEBUAPPX_ENCRYPTED_EXEMPTIONS@@PEAPEAV1234@@Z; Appx::Packaging::Production::AppxEncryptedPackageWriter::Create(bool,IStream *,IStream *,IStream *,APPX_ENCRYPTED_PACKAGE_SETTINGS2 const *,APPX_KEY_INFO const *,APPX_ENCRYPTED_EXEMPTIONS const *,Appx::Packaging::Production::AppxEncryptedPackageWriter * *)
0x180080ff2  xor     r15d, r15d
0x180080ff5  mov     ebx, eax
0x180080ff7  test    eax, eax
0x180080ff9  jns     short loc_180081005
0x180080ffb  mov     edx, 0E3h
0x180081000  jmp     loc_180081359
0x180081005  lea     rdx, [rbp+3Fh+arg_0]
0x180081009  mov     rcx, [rsp+120h+var_D0]
0x18008100e  mov     [rbp+3Fh+arg_0], r15d
0x180081012  mov     rax, [rcx]
0x180081015  mov     rax, [rax+20h]
0x180081019  cmp     [rbp+3Fh+arg_28], r15b
0x18008101d  jz      loc_180081402
0x180081023  mov     rbx, r15
0x180081026  mov     [rbp+3Fh+var_60], r15
0x18008102a  mov     r12d, 1
0x180081030  mov     [rbp+3Fh+var_68], rbx
0x180081034  mov     [rbp+3Fh+var_50], r12b
0x180081038  mov     rsi, r15
0x18008103b  mov     [rbp+3Fh+var_58], r15
0x18008103f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081044  cmp     [rbp+3Fh+arg_0], r12d
0x180081048  jnz     loc_1800811C7
0x18008104e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180081055  mov     ecx, 18h; unsigned __int64
0x18008105a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008105f  mov     r14, rax
0x180081062  test    rax, rax
0x180081065  jz      loc_1800811A8
0x18008106b  mov     [rax+10h], r15
0x18008106f  lea     rcx, [rbp+3Fh+var_B0]
0x180081073  mov     [rax], r15
0x180081076  mov     [rax+8], r15
0x18008107a  mov     rdi, [rsp+120h+var_D0]
0x18008107f  mov     [rbp+3Fh+var_B0], r15
0x180081083  mov     rdx, [rdi]
0x180081086  mov     rbx, [rdx+18h]
0x18008108a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008108f  lea     rdx, [rbp+3Fh+var_B0]
0x180081093  mov     rcx, rdi
0x180081096  mov     rax, rbx
0x180081099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008109e  mov     ebx, eax
  ... truncated ...
```
