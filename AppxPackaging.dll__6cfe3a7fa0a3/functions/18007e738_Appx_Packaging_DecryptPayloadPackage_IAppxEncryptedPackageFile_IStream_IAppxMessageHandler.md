# Appx::Packaging::DecryptPayloadPackage(IAppxEncryptedPackageFile *,IStream *,IAppxMessageHandler *)

- ea: `0x18007e738`
- end: `0x18007eef8`
- name: `?DecryptPayloadPackage@Packaging@Appx@@YAJPEAUIAppxEncryptedPackageFile@@PEAUIStream@@PEAUIAppxMessageHandler@@@Z`
- size: `1984`
- prototype: `int(Appx::Packaging *__hidden this, struct IAppxEncryptedPackageFile *, struct IStream *, struct IAppxMessageHandler *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ef00`
- `0x1800c3380`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18007e738`
- `0x18008ebd8`
- `0x18008ed60`
- `0x18008edcc`
- `0x18008fdb4`
- `0x18008fde0`
- `0x1800c3ddc`
- `0x1800c3e84`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007eba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ec1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007eba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ec1c`

## string_xrefs

- `0x18007ee27`: `onecore\printscan\appxpackaging\dll\lib\unpackhelper.cpp`
- `0x18007e78d`: `encryptedPackage->GetEncryptedPackageReader(&packageReader)`
- `0x18007e7f9`: `packageReader->GetFootprintFile(APPX_FOOTPRINT_FILE_TYPE_MANIFEST, &manifestFile)`
- `0x18007e864`: `manifestFile->GetStream(&manifestStream)`
- `0x18007e8cc`: `packageReader->GetPayloadFiles(&payloadFiles)`
- `0x18007e934`: `packageReader->GetBlockMap(&packageBlockMapReader)`
- `0x18007e99c`: `packageBlockMapReader->GetHashMethod(&hashMethod)`
- `0x18007ea06`: `Appx::Packaging::Production::AppxPackageWriter::Create( outputStream, &settings, &packageWriter)`
- `0x18007ebdf`: `packageWriter->AddPayloadFile(fileName, addSettings.GetContentType(), addSettings.GetCompressionOption(), packageFileStream.Get())`
- `0x18007ebce`: `payloadFiles->MoveNext(&hasCurrent)`
- `0x18007eda5`: `packageWriter.As(&packageWriter2)`
- `0x18007edfe`: `packageWriter2->Close(manifestStream.Get(), contentGroupMapStream.Get())`
- `0x18007ee63`: `packageWriter->Close(manifestStream.Get())`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::DecryptPayloadPackage(
        Appx::Packaging *this,
        struct IAppxEncryptedPackageFile *a2,
        struct IStream *a3,
        struct IAppxMessageHandler *a4)
{
  __int64 v4; // rax
  __int64 (__fastcall *v8)(Appx::Packaging *, __int64 *); // rbx
  struct IAppxMessageHandler *v9; // rdx
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  struct IAppxMessageHandler *v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  struct IAppxMessageHandler *v16; // rdx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  struct IAppxMessageHandler *v19; // rdx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  struct IAppxMessageHandler *v22; // rdx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, IUri **); // rbx
  struct IAppxMessageHandler *v25; // rdx
  struct IAppxMessageHandler *v26; // rdx
  struct IAppxMessageHandler *v27; // rdx
  const char *v28; // rax
  struct IAppxMessageHandler *v29; // rdx
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64 *); // rbx
  struct IAppxMessageHandler *v32; // rdx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64 *); // rbx
  struct IAppxMessageHandler *v35; // rdx
  struct IAppxMessageHandler *v36; // rdx
  const unsigned __int16 *FileExtension; // rax
  struct Appx::Packaging::AddFileSettings *v38; // rax
  struct IAppxMessageHandler *v39; // rdx
  struct IAppxMessageHandler *v40; // rdx
  const char *v41; // rax
  __int64 *v42; // rcx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64, __int64 *); // rbx
  int v45; // r14d
  __int64 v46; // rdx
  __int64 v47; // rbx
  __int64 (__fastcall *v48)(__int64, __int64 *); // rdi
  struct IAppxMessageHandler *v49; // rdx
  struct IAppxPackageWriter *v50; // rbx
  HRESULT (__stdcall *QueryInterface)(IAppxPackageWriter *, const IID *const, void **); // rdi
  struct IAppxMessageHandler *v52; // rdx
  const char *v53; // rax
  struct IAppxMessageHandler *v54; // rdx
  struct IAppxMessageHandler *v55; // rdx
  int v57; // [rsp+20h] [rbp-59h]
  __int64 v58; // [rsp+30h] [rbp-49h] BYREF
  __int64 v59; // [rsp+38h] [rbp-41h] BYREF
  struct IAppxPackageWriter *v60; // [rsp+40h] [rbp-39h] BYREF
  __int64 v61; // [rsp+48h] [rbp-31h] BYREF
  IUri *v62; // [rsp+50h] [rbp-29h] BYREF
  __int64 v63; // [rsp+58h] [rbp-21h] BYREF
  __int64 v64; // [rsp+60h] [rbp-19h] BYREF
  __int64 v65; // [rsp+68h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-9h] BYREF
  __int64 v67; // [rsp+78h] [rbp-1h] BYREF
  __int64 v68; // [rsp+80h] [rbp+7h] BYREF
  __int128 v69; // [rsp+88h] [rbp+Fh] BYREF
  int v70; // [rsp+98h] [rbp+1Fh]
  APPX_PACKAGE_SETTINGS v71; // [rsp+A0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v73; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v74; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = *(_QWORD *)this;
  v68 = 0;
  v8 = *(__int64 (__fastcall **)(Appx::Packaging *, __int64 *))(v4 + 72);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  v10 = v8(this, &v68);
  if ( v10 >= 0 )
  {
    v11 = v68;
    v59 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v68 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
    v10 = v12(v11, 0, &v59);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v13);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "packageReader->GetFootprintFile(APPX_FOOTPRINT_FILE_TYPE_MANIFEST, &manifestFile)",
        v10);
LABEL_5:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
      goto LABEL_63;
    }
    v14 = v59;
    v58 = 0;
    v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
    v10 = v15(v14, &v58);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v16);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "manifestFile->GetStream(&manifestStream)",
        v10);
LABEL_8:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
      goto LABEL_5;
    }
    v17 = v68;
    v74 = 0;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 48LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    v10 = v18(v17, &v74);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v19);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "packageReader->GetPayloadFiles(&payloadFiles)",
        v10);
LABEL_11:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
      goto LABEL_8;
    }
    v20 = v68;
    v61 = 0;
    v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v68 + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    v10 = v21(v20, &v61);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v22);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "packageReader->GetBlockMap(&packageBlockMapReader)",
        v10);
LABEL_14:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
      goto LABEL_11;
    }
    v23 = v61;
    v62 = 0;
    v24 = *(__int64 (__fastcall **)(__int64, IUri **))(*(_QWORD *)v61 + 40LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
    v10 = v24(v23, &v62);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v25);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "packageBlockMapReader->GetHashMethod(&hashMethod)",
        v10);
LABEL_17:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      goto LABEL_14;
    }
    v71.hashMethod = v62;
    *(_QWORD *)&v71.forceZip32 = 0;
    v60 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
    v10 = Appx::Packaging::Production::AppxPackageWriter::Create(a2, &v71, &v60);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v26);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "Appx::Packaging::Production::AppxPackageWriter::Create( outputStream, &settings, &packageWriter)",
        v10);
LABEL_20:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
      goto LABEL_17;
    }
    v70 = 0;
    v69 = 0;
    v10 = Appx::Packaging::AddFileSettingsListContainer::Initialize((Appx::Packaging::AddFileSettingsListContainer *)&v69);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v27);
      v28 = "addFileSettingsListContainer.Initialize()";
      goto LABEL_23;
    }
    v73 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v74 + 32LL))(v74, &v73);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo(a3, v29);
      v28 = "payloadFiles->GetHasCurrent(&hasCurrent)";
LABEL_23:
      Appx::Packaging::LogMessage(a3, 2, 1, L"Failure at %1!hs! - 0x%2!x!\n", v28, v10);
LABEL_24:
      Appx::Packaging::AddFileSettingsListContainer::~AddFileSettingsListContainer((Appx::Packaging::AddFileSettingsListContainer *)&v69);
      goto LABEL_20;
    }
    while ( v73 )
    {
      v30 = v74;
      v63 = 0;
      v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v74 + 24LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
      v10 = v31(v30, &v63);
      if ( v10 < 0 )
      {
        Appx::Packaging::LogErrorInfo(a3, v32);
        Appx::Packaging::LogMessage(
          a3,
          2,
          1,
          L"Failure at %1!hs! - 0x%2!x!\n",
          "payloadFiles->GetCurrent(&currentFile)",
          v10);
        goto LABEL_41;
      }
      v33 = v63;
      v65 = 0;
      v34 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      v10 = v34(v33, &v65);
      if ( v10 < 0 )
      {
        Appx::Packaging::LogErrorInfo(a3, v35);
        Appx::Packaging::LogMessage(
          a3,
          2,
          1,
          L"Failure at %1!hs! - 0x%2!x!\n",
          "currentFile->GetStream(&packageFileStream)",
          v10);
        goto LABEL_39;
      }
      pv = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v63 + 40LL))(v63, &pv);
      if ( v10 < 0 )
      {
        Appx::Packaging::LogErrorInfo(a3, v36);
        v41 = "currentFile->GetName(&fileName)";
LABEL_37:
        Appx::Packaging::LogMessage(a3, 2, 1, L"Failure at %1!hs! - 0x%2!x!\n", v41, v10);
        CoTaskMemFree(pv);
LABEL_39:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
LABEL_41:
        v42 = &v63;
LABEL_42:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v42);
        goto LABEL_24;
      }
      FileExtension = Appx::Packaging::FileExtensionHelper::GetFileExtension((wchar_t *)pv);
      v38 = Appx::Packaging::AddFileSettingsListContainer::Find(
              (Appx::Packaging::AddFileSettingsListContainer *)&v69,
              FileExtension);
      v57 = v65;
      v10 = ((__int64 (__fastcall *)(struct IAppxPackageWriter *, LPVOID, _QWORD, _QWORD))v60->lpVtbl->AddPayloadFile)(
              v60,
              pv,
              *(_QWORD *)v38,
              *((unsigned int *)v38 + 2));
      if ( v10 < 0 )
      {
        Appx::Packaging::LogErrorInfo(a3, v39);
        v41 = "packageWriter->AddPayloadFile(fileName, addSettings.GetContentType(), addSettings.GetCompressionOption(), "
              "packageFileStream.Get())";
        goto LABEL_37;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v74 + 40LL))(v74, &v73);
      if ( v10 < 0 )
      {
        Appx::Packaging::LogErrorInfo(a3, v40);
        v41 = "payloadFiles->MoveNext(&hasCurrent)";
        goto LABEL_37;
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
    }
    v43 = v68;
    v64 = 0;
    v44 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v68 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
    v45 = v44(v43, 4, &v64);
    if ( (int)(v45 + 0x80000000) >= 0 && v45 != -2147024894 )
    {
      v46 = 299;
      goto LABEL_58;
    }
    v47 = v64;
    if ( v64 )
    {
      v67 = 0;
      v48 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 56LL);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      v10 = v48(v47, &v67);
      if ( v10 >= 0 )
      {
        v50 = v60;
        *(_QWORD *)&v71.forceZip32 = 0;
        QueryInterface = v60->lpVtbl->QueryInterface;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
        v10 = ((__int64 (__fastcall *)(struct IAppxPackageWriter *, GUID *, APPX_PACKAGE_SETTINGS *))QueryInterface)(
                v50,
                &GUID_2cf5c4fd_e54c_4ea5_ba4e_f8c4b105a8c8,
                &v71);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)&v71.forceZip32 + 24LL))(
                  *(_QWORD *)&v71.forceZip32,
                  v58,
                  v67);
          if ( v10 >= 0 )
          {
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
            if ( v45 >= 0 )
            {
LABEL_62:
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
              Appx::Packaging::AddFileSettingsListContainer::~AddFileSettingsListContainer((Appx::Packaging::AddFileSettingsListContainer *)&v69);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v60);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v59);
              v10 = v45;
              goto LABEL_63;
            }
            v46 = 319;
LABEL_58:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v46,
              (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\unpackhelper.cpp",
              (const char *)(unsigned int)v45,
              v57);
            goto LABEL_62;
          }
          Appx::Packaging::LogErrorInfo(a3, v54);
          v53 = "packageWriter2->Close(manifestStream.Get(), contentGroupMapStream.Get())";
        }
        else
        {
          Appx::Packaging::LogErrorInfo(a3, v52);
          v53 = "packageWriter.As(&packageWriter2)";
        }
        Appx::Packaging::LogMessage(a3, 2, 1, L"Failure at %1!hs! - 0x%2!x!\n", v53, v10);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
      }
      else
      {
        Appx::Packaging::LogErrorInfo(a3, v49);
        Appx::Packaging::LogMessage(
          a3,
          2,
          1,
          L"Failure at %1!hs! - 0x%2!x!\n",
          "optionalContentGroupMapFile->GetStream(&contentGroupMapStream)",
          v10);
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    }
    else
    {
      v10 = ((__int64 (__fastcall *)(struct IAppxPackageWriter *, __int64))v60->lpVtbl->Close)(v60, v58);
      if ( v10 >= 0 )
      {
        v45 = 0;
        goto LABEL_62;
      }
      Appx::Packaging::LogErrorInfo(a3, v55);
      Appx::Packaging::LogMessage(
        a3,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "packageWriter->Close(manifestStream.Get())",
        v10);
    }
    v42 = &v64;
    goto LABEL_42;
  }
  Appx::Packaging::LogErrorInfo(a3, v9);
  Appx::Packaging::LogMessage(
    a3,
    2,
    1,
    L"Failure at %1!hs! - 0x%2!x!\n",
    "encryptedPackage->GetEncryptedPackageReader(&packageReader)",
    v10);
LABEL_63:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18007e738  mov     [rsp-8+arg_8], rbx
0x18007e73d  push    rbp
0x18007e73e  push    rsi
0x18007e73f  push    rdi
0x18007e740  push    r14
0x18007e742  push    r15
0x18007e744  lea     rbp, [rsp-37h]
0x18007e749  sub     rsp, 0B0h
0x18007e750  mov     rax, [rcx]
0x18007e753  mov     rdi, rcx
0x18007e756  xor     r15d, r15d
0x18007e759  lea     rcx, [rbp+57h+var_50]
0x18007e75d  mov     rsi, r8
0x18007e760  mov     [rbp+57h+var_50], r15
0x18007e764  mov     r14, rdx
0x18007e767  mov     rbx, [rax+48h]
0x18007e76b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e770  lea     rdx, [rbp+57h+var_50]
0x18007e774  mov     rcx, rdi
0x18007e777  mov     rax, rbx
0x18007e77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e77f  mov     ebx, eax
0x18007e781  test    eax, eax
0x18007e783  jns     short loc_18007E7B9
0x18007e785  mov     rcx, rsi; this
0x18007e788  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e78d  lea     rax, aEncryptedpacka; "encryptedPackage->GetEncryptedPackageRe"...
0x18007e794  mov     [rsp+0D0h+var_A8], ebx
0x18007e798  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e79f  mov     [rsp+0D0h+var_B0], rax
0x18007e7a4  lea     edx, [r15+2]
0x18007e7a8  mov     rcx, rsi
0x18007e7ab  lea     r8d, [r15+1]
0x18007e7af  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e7b4  jmp     loc_18007EED5
0x18007e7b9  mov     rdi, [rbp+57h+var_50]
0x18007e7bd  lea     rcx, [rbp+57h+var_98]
0x18007e7c1  mov     [rbp+57h+var_98], r15
0x18007e7c5  mov     rax, [rdi]
0x18007e7c8  mov     rbx, [rax+20h]
0x18007e7cc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e7d1  lea     r8, [rbp+57h+var_98]
0x18007e7d5  xor     edx, edx
0x18007e7d7  mov     rcx, rdi
0x18007e7da  mov     rax, rbx
0x18007e7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7e2  mov     ebx, eax
0x18007e7e4  test    eax, eax
0x18007e7e6  jns     short loc_18007E826
0x18007e7e8  mov     rcx, rsi; this
0x18007e7eb  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e7f0  mov     edx, 2
0x18007e7f5  mov     [rsp+0D0h+var_A8], ebx
0x18007e7f9  lea     rax, aPackagereaderG; "packageReader->GetFootprintFile(APPX_FO"...
0x18007e800  mov     rcx, rsi
0x18007e803  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e80a  mov     [rsp+0D0h+var_B0], rax
0x18007e80f  lea     r8d, [rdx-1]
0x18007e813  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e818  lea     rcx, [rbp+57h+var_98]
0x18007e81c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e821  jmp     loc_18007EED5
0x18007e826  mov     rdi, [rbp+57h+var_98]
0x18007e82a  lea     rcx, [rbp+57h+var_A0]
0x18007e82e  mov     [rbp+57h+var_A0], r15
0x18007e832  mov     rax, [rdi]
0x18007e835  mov     rbx, [rax+38h]
0x18007e839  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e83e  lea     rdx, [rbp+57h+var_A0]
0x18007e842  mov     rcx, rdi
0x18007e845  mov     rax, rbx
0x18007e848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e84d  mov     ebx, eax
0x18007e84f  test    eax, eax
0x18007e851  jns     short loc_18007E88E
0x18007e853  mov     rcx, rsi; this
0x18007e856  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e85b  mov     edx, 2
0x18007e860  mov     [rsp+0D0h+var_A8], ebx
0x18007e864  lea     rax, aManifestfileGe_0; "manifestFile->GetStream(&manifestStream"...
0x18007e86b  mov     rcx, rsi
0x18007e86e  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e875  mov     [rsp+0D0h+var_B0], rax
0x18007e87a  lea     r8d, [rdx-1]
0x18007e87e  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e883  lea     rcx, [rbp+57h+var_A0]
0x18007e887  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e88c  jmp     short loc_18007E818
0x18007e88e  mov     rdi, [rbp+57h+var_50]
0x18007e892  lea     rcx, [rbp+57h+arg_18]
0x18007e896  mov     [rbp+57h+arg_18], r15
0x18007e89a  mov     rax, [rdi]
0x18007e89d  mov     rbx, [rax+30h]
0x18007e8a1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e8a6  lea     rdx, [rbp+57h+arg_18]
0x18007e8aa  mov     rcx, rdi
0x18007e8ad  mov     rax, rbx
0x18007e8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8b5  mov     ebx, eax
0x18007e8b7  test    eax, eax
0x18007e8b9  jns     short loc_18007E8F6
0x18007e8bb  mov     rcx, rsi; this
0x18007e8be  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e8c3  mov     edx, 2
0x18007e8c8  mov     [rsp+0D0h+var_A8], ebx
0x18007e8cc  lea     rax, aPackagereaderG_2; "packageReader->GetPayloadFiles(&payload"...
0x18007e8d3  mov     rcx, rsi
0x18007e8d6  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e8dd  mov     [rsp+0D0h+var_B0], rax
0x18007e8e2  lea     r8d, [rdx-1]
0x18007e8e6  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e8eb  lea     rcx, [rbp+57h+arg_18]
0x18007e8ef  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e8f4  jmp     short loc_18007E883
0x18007e8f6  mov     rdi, [rbp+57h+var_50]
0x18007e8fa  lea     rcx, [rbp+57h+var_88]
0x18007e8fe  mov     [rbp+57h+var_88], r15
0x18007e902  mov     rax, [rdi]
0x18007e905  mov     rbx, [rax+18h]
0x18007e909  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e90e  lea     rdx, [rbp+57h+var_88]
0x18007e912  mov     rcx, rdi
0x18007e915  mov     rax, rbx
0x18007e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e91d  mov     ebx, eax
0x18007e91f  test    eax, eax
0x18007e921  jns     short loc_18007E95E
0x18007e923  mov     rcx, rsi; this
0x18007e926  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e92b  mov     edx, 2
0x18007e930  mov     [rsp+0D0h+var_A8], ebx
0x18007e934  lea     rax, aPackagereaderG_1; "packageReader->GetBlockMap(&packageBloc"...
0x18007e93b  mov     rcx, rsi
0x18007e93e  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e945  mov     [rsp+0D0h+var_B0], rax
0x18007e94a  lea     r8d, [rdx-1]
0x18007e94e  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e953  lea     rcx, [rbp+57h+var_88]
0x18007e957  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e95c  jmp     short loc_18007E8EB
0x18007e95e  mov     rdi, [rbp+57h+var_88]
0x18007e962  lea     rcx, [rbp+57h+var_80]
0x18007e966  mov     [rbp+57h+var_80], r15
0x18007e96a  mov     rax, [rdi]
0x18007e96d  mov     rbx, [rax+28h]
0x18007e971  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e976  lea     rdx, [rbp+57h+var_80]
0x18007e97a  mov     rcx, rdi
0x18007e97d  mov     rax, rbx
0x18007e980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e985  mov     ebx, eax
0x18007e987  test    eax, eax
0x18007e989  jns     short loc_18007E9C6
0x18007e98b  mov     rcx, rsi; this
0x18007e98e  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e993  mov     edx, 2
0x18007e998  mov     [rsp+0D0h+var_A8], ebx
0x18007e99c  lea     rax, aPackageblockma; "packageBlockMapReader->GetHashMethod(&h"...
0x18007e9a3  mov     rcx, rsi
0x18007e9a6  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007e9ad  mov     [rsp+0D0h+var_B0], rax
0x18007e9b2  lea     r8d, [rdx-1]
0x18007e9b6  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007e9bb  lea     rcx, [rbp+57h+var_80]
0x18007e9bf  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e9c4  jmp     short loc_18007E953
0x18007e9c6  mov     rax, [rbp+57h+var_80]
0x18007e9ca  lea     rcx, [rbp+57h+var_90]
0x18007e9ce  mov     [rbp+57h+var_30.hashMethod], rax
0x18007e9d2  mov     qword ptr [rbp+57h+var_30.forceZip32], r15
0x18007e9d6  mov     [rbp+57h+var_90], r15
0x18007e9da  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007e9df  lea     r8, [rbp+57h+var_90]; struct IAppxPackageWriter **
0x18007e9e3  mov     rcx, r14; struct IStream *
0x18007e9e6  lea     rdx, [rbp+57h+var_30]; struct APPX_PACKAGE_SETTINGS *
0x18007e9ea  call    ?Create@AppxPackageWriter@Production@Packaging@Appx@@SAJPEAUIStream@@PEAUAPPX_PACKAGE_SETTINGS@@PEAPEAUIAppxPackageWriter@@@Z; Appx::Packaging::Production::AppxPackageWriter::Create(IStream *,APPX_PACKAGE_SETTINGS *,IAppxPackageWriter * *)
0x18007e9ef  mov     ebx, eax
0x18007e9f1  test    eax, eax
0x18007e9f3  jns     short loc_18007EA30
0x18007e9f5  mov     rcx, rsi; this
0x18007e9f8  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007e9fd  mov     edx, 2
0x18007ea02  mov     [rsp+0D0h+var_A8], ebx
0x18007ea06  lea     rax, aAppxPackagingP; "Appx::Packaging::Production::AppxPackag"...
0x18007ea0d  mov     rcx, rsi
0x18007ea10  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007ea17  mov     [rsp+0D0h+var_B0], rax
0x18007ea1c  lea     r8d, [rdx-1]
0x18007ea20  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007ea25  lea     rcx, [rbp+57h+var_90]
0x18007ea29  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ea2e  jmp     short loc_18007E9BB
0x18007ea30  xorps   xmm0, xmm0
0x18007ea33  mov     [rbp+57h+var_38], r15d
0x18007ea37  lea     rcx, [rbp+57h+var_48]; this
0x18007ea3b  movdqu  [rbp+57h+var_48], xmm0
0x18007ea40  call    ?Initialize@AddFileSettingsListContainer@Packaging@Appx@@QEAAJXZ; Appx::Packaging::AddFileSettingsListContainer::Initialize(void)
0x18007ea45  mov     ebx, eax
0x18007ea47  test    eax, eax
0x18007ea49  jns     short loc_18007EA86
0x18007ea4b  mov     rcx, rsi; this
0x18007ea4e  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007ea53  lea     rax, aAddfilesetting; "addFileSettingsListContainer.Initialize"...
0x18007ea5a  mov     edx, 2
0x18007ea5f  mov     [rsp+0D0h+var_A8], ebx
0x18007ea63  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x18007ea6a  mov     [rsp+0D0h+var_B0], rax
0x18007ea6f  mov     rcx, rsi
0x18007ea72  lea     r8d, [rdx-1]
0x18007ea76  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18007ea7b  lea     rcx, [rbp+57h+var_48]; this
0x18007ea7f  call    ??1AddFileSettingsListContainer@Packaging@Appx@@QEAA@XZ; Appx::Packaging::AddFileSettingsListContainer::~AddFileSettingsListContainer(void)
0x18007ea84  jmp     short loc_18007EA25
0x18007ea86  mov     rcx, [rbp+57h+arg_18]
0x18007ea8a  lea     rdx, [rbp+57h+arg_0]
0x18007ea8e  mov     [rbp+57h+arg_0], r15d
0x18007ea92  mov     rax, [rcx]
0x18007ea95  mov     rax, [rax+20h]
0x18007ea99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea9e  mov     ebx, eax
0x18007eaa0  test    eax, eax
0x18007eaa2  jns     short loc_18007EAB5
0x18007eaa4  mov     rcx, rsi; this
0x18007eaa7  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007eaac  lea     rax, aPayloadfilesGe; "payloadFiles->GetHasCurrent(&hasCurrent"...
0x18007eab3  jmp     short loc_18007EA5A
0x18007eab5  cmp     [rbp+57h+arg_0], r15d
0x18007eab9  jz      loc_18007ECA3
0x18007eabf  mov     rdi, [rbp+57h+arg_18]
0x18007eac3  lea     rcx, [rbp+57h+var_78]
0x18007eac7  mov     [rbp+57h+var_78], r15
0x18007eacb  mov     rax, [rdi]
0x18007eace  mov     rbx, [rax+18h]
0x18007ead2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ead7  lea     rdx, [rbp+57h+var_78]
0x18007eadb  mov     rcx, rdi
0x18007eade  mov     rax, rbx
0x18007eae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eae6  mov     ebx, eax
0x18007eae8  test    eax, eax
0x18007eaea  js      loc_18007EC65
0x18007eaf0  mov     rdi, [rbp+57h+var_78]
0x18007eaf4  lea     rcx, [rbp+57h+var_68]
0x18007eaf8  mov     [rbp+57h+var_68], r15
0x18007eafc  mov     rax, [rdi]
0x18007eaff  mov     rbx, [rax+38h]
0x18007eb03  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007eb08  lea     rdx, [rbp+57h+var_68]
0x18007eb0c  mov     rcx, rdi
0x18007eb0f  mov     rax, rbx
0x18007eb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb17  mov     ebx, eax
0x18007eb19  test    eax, eax
0x18007eb1b  js      loc_18007EC2A
0x18007eb21  mov     rcx, [rbp+57h+var_78]
0x18007eb25  lea     rdx, [rbp+57h+pv]
0x18007eb29  mov     [rbp+57h+pv], r15
0x18007eb2d  mov     rax, [rcx]
0x18007eb30  mov     rax, [rax+28h]
0x18007eb34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb39  mov     ebx, eax
0x18007eb3b  test    eax, eax
0x18007eb3d  js      loc_18007EBE8
0x18007eb43  mov     rcx, [rbp+57h+pv]; Str
0x18007eb47  call    ?GetFileExtension@FileExtensionHelper@Packaging@Appx@@SAPEBGPEBG@Z; Appx::Packaging::FileExtensionHelper::GetFileExtension(ushort const *)
0x18007eb4c  mov     rdx, rax; unsigned __int16 *
0x18007eb4f  lea     rcx, [rbp+57h+var_48]; this
0x18007eb53  call    ?Find@AddFileSettingsListContainer@Packaging@Appx@@QEAAAEAVAddFileSettings@23@PEBG@Z; Appx::Packaging::AddFileSettingsListContainer::Find(ushort const *)
0x18007eb58  mov     r9, [rbp+57h+var_68]
0x18007eb5c  mov     rdx, rax
0x18007eb5f  mov     rcx, [rbp+57h+var_90]
0x18007eb63  mov     [rsp+0D0h+var_B0], r9
0x18007eb68  mov     r9d, [rdx+8]
0x18007eb6c  mov     r8, [rcx]
0x18007eb6f  mov     rax, [r8+18h]
0x18007eb73  mov     r8, [rdx]
0x18007eb76  mov     rdx, [rbp+57h+pv]
0x18007eb7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb7f  mov     ebx, eax
0x18007eb81  test    eax, eax
0x18007eb83  js      short loc_18007EBD7
0x18007eb85  mov     rcx, [rbp+57h+arg_18]
0x18007eb89  lea     rdx, [rbp+57h+arg_0]
0x18007eb8d  mov     rax, [rcx]
0x18007eb90  mov     rax, [rax+28h]
0x18007eb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb99  mov     ebx, eax
0x18007eb9b  test    eax, eax
0x18007eb9d  js      short loc_18007EBC6
0x18007eb9f  mov     rcx, [rbp+57h+pv]; pv
0x18007eba3  call    cs:__imp_CoTaskMemFree
0x18007ebaa  nop     dword ptr [rax+rax+00h]
0x18007ebaf  lea     rcx, [rbp+57h+var_68]
0x18007ebb3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ebb8  lea     rcx, [rbp+57h+var_78]
0x18007ebbc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ebc1  jmp     loc_18007EAB5
0x18007ebc6  mov     rcx, rsi; this
0x18007ebc9  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18007ebce  lea     rax, aPayloadfilesMo; "payloadFiles->MoveNext(&hasCurrent)"
  ... truncated ...
```
