# Appx::Packaging::Consumption::EncryptedBundleStreamingReader::Create(IAppxStreamingDataSource *,APPX_PACKAGE_READER_OPTIONS,Appx::Packaging::Consumption::EncryptedAppxHeaderReceiver *,unsigned __int64,uint,uchar const *,IAppxFootprintFileDownloadProgressHandler *,ushort const *,IAppxBundleStreamingReader * *)

- ea: `0x18006d578`
- end: `0x18006e153`
- name: `?Create@EncryptedBundleStreamingReader@Consumption@Packaging@Appx@@SAJPEAUIAppxStreamingDataSource@@W4APPX_PACKAGE_READER_OPTIONS@@PEAVEncryptedAppxHeaderReceiver@234@_KIPEBEPEAUIAppxFootprintFileDownloadProgressHandler@@PEBGPEAPEAUIAppxBundleStreamingReader@@@Z`
- size: `3035`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006cf50`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x18000849c`
- `0x1800133fc`
- `0x180017b48`
- `0x180024974`
- `0x180046da4`
- `0x180046e28`
- `0x18005dbd8`
- `0x18006c8e0`
- `0x18006ca18`
- `0x18006cbc4`
- `0x18006cd10`
- `0x18006ce48`
- `0x18006d578`
- `0x18006f1f8`
- `0x18006f310`
- `0x18006f358`
- `0x180071f50`
- `0x1800728bc`
- `0x180084398`
- `0x180084e24`
- `0x1800850b0`
- `0x1800850dc`
- `0x180086460`
- `0x180086918`
- `0x180086a74`
- `0x1800871d4`
- `0x1800872ac`
- `0x180096a00`
- `0x1800992a0`
- `0x1800c9aac`
- `0x1800cfdc0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18006ddd0`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18006ddd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dfe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006dfe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e0b7`

## string_xrefs

- `0x18006de16`: `AppxMetadata\AppxBundleManifest.xml`
- `0x18006d5e1`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d69f`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d725`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d7c8`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d86c`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d8b0`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d8d5`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d924`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006d9d6`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006da1f`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006da73`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dacd`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006db6a`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dbff`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dc88`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dd51`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dd9b`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006de3a`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006de7a`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006df44`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006dfcf`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`
- `0x18006e022`: `onecore\printscan\appxpackaging\consumption\src\encryptedbundlestreamingreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::EncryptedBundleStreamingReader::Create(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        Appx::Packaging::Consumption::AppxEncryptedFile *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned __int16 *a7,
        Appx::Packaging *a8,
        __int64 a9)
{
  __int64 v12; // rdx
  int TempFolderPathCached; // ebx
  Appx::Packaging::Consumption::AppxEncryptedBundleReader *v15; // r14
  __int64 v16; // rdx
  Appx::Packaging::FileNameHelper *v17; // rcx
  __int64 v18; // rax
  __int64 (__fastcall *v19)(__int64 *, Appx::Packaging **); // rbx
  __int64 v20; // rdx
  __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // rcx
  struct IStream *v26; // rbx
  int FootersStream; // edi
  __int64 v28; // rdx
  unsigned __int64 v29; // rdx
  Appx::Packaging::Consumption::AppxEncryptedFile *v30; // rsi
  int v31; // edi
  __int64 v32; // rdx
  Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *v33; // rsi
  __int64 v34; // rdx
  int v35; // eax
  struct Appx::Packaging::AppxEncryptionSettings *v36; // rdi
  Appx::Packaging::Consumption::AppxEncryptedBundleReader *v37; // rsi
  int BlockMapEncryptedFile; // esi
  __int64 v39; // rdx
  Appx::Packaging::Consumption::AppxEncryptedFile *v40; // rsi
  unsigned __int64 v41; // r12
  int v42; // r12d
  __int64 v43; // rdx
  char *v44; // r12
  int BlockMap; // eax
  Appx::Packaging *v46; // r13
  const unsigned __int16 *v47; // r8
  __int64 v48; // rdx
  ULONG v49; // eax
  unsigned int v50; // r13d
  int v51; // r9d
  int matched; // eax
  Appx::Packaging::Consumption::AppxEncryptedFile *v53; // rsi
  unsigned __int64 v54; // r12
  __int64 v55; // rdx
  const unsigned __int16 *v56; // r12
  int BundleManifest; // eax
  int AppxFilesWithManifestData; // eax
  __int64 v59; // rcx
  __int64 v60; // r8
  int lpString1; // [rsp+20h] [rbp-B9h]
  int lpString1a; // [rsp+20h] [rbp-B9h]
  int lpString1b; // [rsp+20h] [rbp-B9h]
  int lpString1c; // [rsp+20h] [rbp-B9h]
  int lpString1d; // [rsp+20h] [rbp-B9h]
  int lpString1e; // [rsp+20h] [rbp-B9h]
  int lpString1f; // [rsp+20h] [rbp-B9h]
  int lpString1g; // [rsp+20h] [rbp-B9h]
  struct IStream **v69; // [rsp+30h] [rbp-A9h]
  struct IStream **v70; // [rsp+30h] [rbp-A9h]
  Appx::Packaging *v71; // [rsp+50h] [rbp-89h] BYREF
  Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *v72; // [rsp+58h] [rbp-81h] BYREF
  struct IStream *v73; // [rsp+60h] [rbp-79h] BYREF
  struct IStream *v74; // [rsp+68h] [rbp-71h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedFile *v75; // [rsp+70h] [rbp-69h] BYREF
  struct Appx::Packaging::AppxEncryptionSettings *v76; // [rsp+78h] [rbp-61h] BYREF
  struct IStream *v77; // [rsp+80h] [rbp-59h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedFile *v78; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v79; // [rsp+90h] [rbp-49h]
  unsigned __int16 *v80; // [rsp+98h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-39h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedBundleReader *v82; // [rsp+A8h] [rbp-31h] BYREF
  Appx::Packaging *v83; // [rsp+B0h] [rbp-29h]
  __int64 v84; // [rsp+B8h] [rbp-21h]
  unsigned __int16 *v85; // [rsp+C0h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  v83 = a8;
  v84 = a9;
  v78 = a4;
  v79 = a2;
  v85 = a7;
  if ( !a1 )
  {
    v12 = 42;
LABEL_3:
    TempFolderPathCached = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)TempFolderPathCached,
      lpString1);
    return (unsigned int)TempFolderPathCached;
  }
  if ( !a3 )
  {
    v12 = 43;
    goto LABEL_3;
  }
  if ( a5 )
  {
    if ( !a6 )
    {
LABEL_10:
      TempFolderPathCached = -2147024809;
      v12 = 44;
      goto LABEL_4;
    }
  }
  else if ( a6 )
  {
    goto LABEL_10;
  }
  if ( !a9 )
  {
    v12 = 45;
    goto LABEL_3;
  }
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(a1, EVENT_STREAMING_READER_CREATE_START, a2);
  Microsoft::WRL::Details::Make<Appx::Packaging::Consumption::EncryptedBundleStreamingReader,>((__int64 *)&v82);
  v15 = v82;
  if ( !v82 )
  {
    TempFolderPathCached = -2147024882;
    v12 = 51;
    goto LABEL_4;
  }
  Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=((char *)v82 + 288, a1);
  *((_DWORD *)v15 + 70) = a2;
  Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=((char *)v15 + 312, a7);
  TempFolderPathCached = Appx::Packaging::FileNameHelper::Create((struct Appx::Packaging::FileNameHelper **)v15 + 38);
  if ( TempFolderPathCached < 0 )
  {
    v16 = 56;
    goto LABEL_20;
  }
  v17 = (Appx::Packaging::FileNameHelper *)*((_QWORD *)v15 + 38);
  v80 = 0;
  TempFolderPathCached = Appx::Packaging::FileNameHelper::GetTempFolderPathCached(v17, (const unsigned __int16 **)&v80);
  if ( TempFolderPathCached < 0 )
  {
    v16 = 58;
LABEL_20:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)TempFolderPathCached,
      lpString1);
    if ( !v15 )
      return (unsigned int)TempFolderPathCached;
LABEL_21:
    (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)TempFolderPathCached;
  }
  v18 = *a1;
  v71 = 0;
  v19 = *(__int64 (__fastcall **)(__int64 *, Appx::Packaging **))(v18 + 32);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
  TempFolderPathCached = v19(a1, &v71);
  if ( TempFolderPathCached < 0 )
  {
    v20 = 61;
LABEL_26:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)TempFolderPathCached,
      lpString1);
    goto LABEL_27;
  }
  if ( a7 )
  {
    TempFolderPathCached = (*(__int64 (__fastcall **)(unsigned __int16 *, Appx::Packaging *))(*(_QWORD *)a7 + 32LL))(
                             a7,
                             v71);
    if ( TempFolderPathCached < 0 )
    {
      v20 = 67;
      goto LABEL_26;
    }
  }
  v21 = *(_QWORD *)(a3 + 24);
  if ( *(_DWORD *)(v21 + 48) )
  {
    v73 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
    TempFolderPathCached = Appx::Packaging::DownloadToTempFileStream(
                             v71,
                             *(struct IAppxRangeRequestJob **)(v21 + 32),
                             *(unsigned int *)(v21 + 48),
                             (unsigned int)v80,
                             a7,
                             (struct IAppxFootprintFileDownloadProgressHandler *)&v73,
                             v69);
    if ( TempFolderPathCached < 0 )
    {
      v22 = 82;
LABEL_35:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)TempFolderPathCached,
        lpString1);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      goto LABEL_27;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v15 + 56);
    TempFolderPathCached = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadSignatureFile(
                             v73,
                             (enum APPX_COMPRESSION_OPTION)*(_DWORD *)(v21 + 40),
                             v80,
                             (struct IAppxFile **)v15 + 7);
    if ( TempFolderPathCached < 0 )
    {
      v22 = 84;
      goto LABEL_35;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
  }
  v23 = *((_QWORD *)v15 + 7);
  v73 = 0;
  v24 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(v79, v23, &v73);
  TempFolderPathCached = v24;
  if ( v24 < 0 )
  {
    if ( v24 == -2146762496 )
    {
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v25, &EVENT_BUNDLE_UNSIGNED, 2148204800LL);
      AppxPackagingLog(&EVENT_BUNDLE_UNSIGNED, 0xB00000A3, -2146762496);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)TempFolderPathCached,
      lpString1);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v73);
LABEL_27:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    if ( !v15 )
      return (unsigned int)TempFolderPathCached;
    goto LABEL_21;
  }
  v26 = v73;
  FootersStream = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateHeaderIfNeeded(
                    v73,
                    (struct Appx::Packaging::EncryptedAppxHeader *)v21,
                    *(const unsigned __int8 **)(a3 + 32));
  if ( FootersStream < 0 )
  {
    v28 = 98;
LABEL_47:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)FootersStream,
      lpString1);
    goto LABEL_134;
  }
  v29 = *(_QWORD *)(v21 + 8);
  v30 = v78;
  if ( (unsigned __int64)v78 <= v29 )
  {
    FootersStream = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)0x8007000DLL,
      lpString1);
    goto LABEL_50;
  }
  if ( *(_QWORD *)(v21 + 16) > 0xFFFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)0x800700DFLL,
      lpString1);
    goto LABEL_54;
  }
  FootersStream = (*(__int64 (__fastcall **)(Appx::Packaging *, unsigned __int64, _QWORD))(*(_QWORD *)v71 + 24LL))(
                    v71,
                    v29,
                    *(unsigned int *)(v21 + 16));
  if ( FootersStream < 0 )
  {
    v28 = 104;
    goto LABEL_47;
  }
  v31 = v79 & 1;
  v72 = 0;
  v79 = v31;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
  FootersStream = Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::Create(
                    (struct Appx::Packaging::EncryptedAppxHeader *)v21,
                    0,
                    (unsigned __int64)v30,
                    v80,
                    v31 != 0,
                    &v72);
  if ( FootersStream < 0 )
  {
    v32 = 114;
LABEL_60:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)FootersStream,
      lpString1a);
LABEL_133:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
LABEL_134:
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    if ( v15 )
LABEL_135:
      (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)FootersStream;
  }
  v33 = v72;
  FootersStream = (*(__int64 (__fastcall **)(Appx::Packaging *, __int64, Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *))(*(_QWORD *)v71 + 32LL))(
                    v71,
                    3,
                    v72);
  if ( FootersStream < 0 )
  {
    v32 = 116;
    goto LABEL_60;
  }
  if ( *((_DWORD *)v33 + 14) != 3 )
  {
    FootersStream = -2146958848;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)0x80080200LL,
      lpString1a);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
LABEL_50:
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    if ( v15 )
      goto LABEL_135;
    return (unsigned int)FootersStream;
  }
  v74 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  FootersStream = Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::GetFootersStream(v33, &v74);
  if ( FootersStream < 0 )
  {
    v34 = 121;
LABEL_67:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)FootersStream,
      lpString1a);
LABEL_132:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    goto LABEL_133;
  }
  FootersStream = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateFootersIfNeeded(v26, v74);
  if ( FootersStream < 0 )
  {
    v34 = 122;
    goto LABEL_67;
  }
  v76 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  v35 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(
          (const struct Appx::Packaging::EncryptedAppxHeader *)v21,
          a5,
          a6,
          &v76);
  FootersStream = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)v35,
      lpString1a);
LABEL_131:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
    goto LABEL_132;
  }
  v36 = v76;
  if ( *((struct Appx::Packaging::AppxEncryptionSettings **)v15 + 37) != v76 )
  {
    v73 = v76;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v73);
    v73 = (struct IStream *)*((_QWORD *)v15 + 37);
    *((_QWORD *)v15 + 37) = v36;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
  }
  v37 = (Appx::Packaging::Consumption::AppxEncryptedBundleReader *)*((_QWORD *)v33 + 3);
  v82 = v37;
  v75 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
  BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(
                            (const struct Appx::Packaging::EncryptedAppxHeader *)v21,
                            v37,
                            v36,
                            *((struct Appx::Packaging::FileNameHelper **)v15 + 38),
                            0,
                            &v75);
  if ( BlockMapEncryptedFile < 0 )
  {
    v39 = 132;
LABEL_76:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)(unsigned int)BlockMapEncryptedFile,
      lpString1b);
LABEL_77:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    if ( v15 )
      (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v15 + 16LL))(v15);
    return (unsigned int)BlockMapEncryptedFile;
  }
  BlockMapEncryptedFile = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v75,
                            (__int64)v15 + 48);
  if ( BlockMapEncryptedFile < 0 )
  {
    v39 = 133;
    goto LABEL_76;
  }
  v40 = v75;
  v41 = *(_QWORD *)(*((_QWORD *)v75 + 9) + 40LL);
  if ( v41 > 0xFFFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
      (const char *)0x800700DFLL,
      lpString1b);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
LABEL_54:
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    if ( v15 )
      goto LABEL_108;
    return 2147942623LL;
  }
  v77 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
  v42 = Appx::Packaging::DownloadToTempFileStream(
          v71,
          *(struct IAppxRangeRequestJob **)(*((_QWORD *)v40 + 9) + 16LL),
          (unsigned int)v41,
          (unsigned int)v80,
          a7,
          (struct IAppxFootprintFileDownloadProgressHandler *)&v77,
          v69);
  if ( v42 >= 0 )
  {
    v42 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateEncryptedBlockMapIfNeeded(v26, v77);
    if ( v42 < 0 )
    {
      v43 = 149;
      goto LABEL_86;
    }
    v42 = Appx::Packaging::Consumption::AppxEncryptedFile::SetFileStream(v40, v77);
    if ( v42 < 0 )
    {
      v43 = 150;
      goto LABEL_86;
    }
    v44 = (char *)v15 + 24;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v15 + 24);
    BlockMap = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(
                 (const struct Appx::Packaging::EncryptedAppxHeader *)v21,
                 v40,
                 (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)v15 + 3);
    BlockMapEncryptedFile = BlockMap;
    if ( BlockMap < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)BlockMap,
        lpString1c);
LABEL_96:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
      goto LABEL_77;
    }
    v46 = v83;
    if ( v83 )
    {
      BlockMapEncryptedFile = Appx::Packaging::CalculateDigestFromFootprintFiles((char *)v15 + 40, (char *)v15 + 224);
      if ( BlockMapEncryptedFile < 0 )
      {
        v48 = 156;
LABEL_100:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v48,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
          (const char *)(unsigned int)BlockMapEncryptedFile,
          lpString1c);
        goto LABEL_96;
      }
      BlockMapEncryptedFile = Appx::Packaging::VerifyDigest(v46, *((const unsigned __int16 **)v15 + 28), v47);
      if ( BlockMapEncryptedFile < 0 )
      {
        v48 = 157;
        goto LABEL_100;
      }
    }
    v49 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)(*(_QWORD *)v44 + 56LL));
    v78 = 0;
    v50 = v49;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
    matched = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(
                (int)v82,
                *(_QWORD *)v44,
                (int)v36,
                v51,
                L"AppxMetadata\\AppxBundleManifest.xml",
                0,
                (__int64)&v78,
                0,
                0);
    BlockMapEncryptedFile = matched;
    if ( matched < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)matched,
        lpString1d);
LABEL_105:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
      goto LABEL_96;
    }
    v53 = v78;
    v54 = *(_QWORD *)(*((_QWORD *)v78 + 9) + 40LL);
    if ( v54 > 0xFFFFFFFF )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)0x800700DFLL,
        lpString1d);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
      if ( v15 )
LABEL_108:
        (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v15 + 16LL))(v15);
      return 2147942623LL;
    }
    v73 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
    v42 = Appx::Packaging::DownloadToTempFileStream(
            v71,
            *(struct IAppxRangeRequestJob **)(*((_QWORD *)v53 + 9) + 16LL),
            (unsigned int)v54,
            (unsigned int)v80,
            v85,
            (struct IAppxFootprintFileDownloadProgressHandler *)&v73,
            v70);
    if ( v42 < 0 )
    {
      v55 = 187;
LABEL_112:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v55,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)v42,
        lpString1e);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
      goto LABEL_87;
    }
    v42 = Appx::Packaging::Consumption::AppxEncryptedFile::SetFileStream(v53, v73);
    if ( v42 < 0 )
    {
      v55 = 189;
      goto LABEL_112;
    }
    v42 = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v78,
            (__int64)v15 + 40);
    if ( v42 < 0 )
    {
      v55 = 190;
      goto LABEL_112;
    }
    v56 = (const unsigned __int16 *)*((_QWORD *)v26 + 3);
    pv = 0;
    BundleManifest = Appx::Packaging::Consumption::AppxEncryptedBundleReader::LoadBundleManifest(
                       v15,
                       v53,
                       v36,
                       v56,
                       (unsigned __int16 **)&pv);
    BlockMapEncryptedFile = BundleManifest;
    if ( BundleManifest < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)BundleManifest,
        lpString1f);
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      goto LABEL_105;
    }
    AppxFilesWithManifestData = Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateAppxFilesWithManifestData(
                                  v15,
                                  (const struct Appx::Packaging::EncryptedAppxHeader *)v21,
                                  v82,
                                  v50,
                                  v36);
    FootersStream = AppxFilesWithManifestData;
    if ( AppxFilesWithManifestData < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
        (const char *)(unsigned int)AppxFilesWithManifestData,
        lpString1g);
LABEL_130:
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
      goto LABEL_131;
    }
    if ( v79 && v56 )
    {
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) == 0 )
      {
LABEL_127:
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v59, EVENT_STREAMING_READER_CREATE_STOP, v60, 1);
        FootersStream = (**(__int64 (__fastcall ***)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *, GUID *, __int64))v15)(
                          v15,
                          &GUID_4d17e707_40f8_41d0_839c_870cd6ddf02a,
                          v84);
        goto LABEL_130;
      }
      McTemplateU0z_EventWriteTransfer(v59, EVENT_BUNDLE_SIGNATURE_VALIDATION_PASSED, v56);
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(v59, EVENT_BUNDLE_STREAMING_READER_CREATED, pv);
    goto LABEL_127;
  }
  v43 = 147;
LABEL_86:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v43,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedbundlestreamingreader.cpp",
    (const char *)(unsigned int)v42,
    lpString1c);
LABEL_87:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
  Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v26);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
  if ( v15 )
    (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x18006d578  mov     [rsp-8+arg_18], rbx
0x18006d57d  push    rbp
0x18006d57e  push    rsi
0x18006d57f  push    rdi
0x18006d580  push    r12
0x18006d582  push    r13
0x18006d584  push    r14
0x18006d586  push    r15
0x18006d588  lea     rbp, [rsp-7]
0x18006d58d  sub     rsp, 0E0h
0x18006d594  mov     rax, cs:__security_cookie
0x18006d59b  xor     rax, rsp
0x18006d59e  mov     [rbp+37h+var_40], rax
0x18006d5a2  mov     rax, [rbp+37h+arg_38]
0x18006d5a6  mov     rsi, r8
0x18006d5a9  mov     r13, [rbp+37h+arg_30]
0x18006d5ad  mov     ebx, edx
0x18006d5af  mov     r12, [rbp+37h+arg_28]
0x18006d5b3  mov     rdi, rcx
0x18006d5b6  mov     [rbp+37h+var_60], rax
0x18006d5ba  mov     rax, [rbp+37h+arg_40]
0x18006d5c1  mov     [rbp+37h+var_58], rax
0x18006d5c5  mov     [rbp+37h+var_88], r9
0x18006d5c9  mov     [rbp+37h+var_80], edx
0x18006d5cc  mov     [rbp+37h+var_50], r13
0x18006d5d0  test    rcx, rcx
0x18006d5d3  jnz     short loc_18006D5F7
0x18006d5d5  lea     edx, [rcx+2Ah]; void *
0x18006d5d8  mov     ebx, 80004003h
0x18006d5dd  mov     rcx, [rbp+3Fh]; this
0x18006d5e1  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d5e8  mov     r9d, ebx; char *
0x18006d5eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d5f0  mov     eax, ebx
0x18006d5f2  jmp     loc_18006E12B
0x18006d5f7  test    rsi, rsi
0x18006d5fa  jnz     short loc_18006D601
0x18006d5fc  lea     edx, [rsi+2Bh]
0x18006d5ff  jmp     short loc_18006D5D8
0x18006d601  cmp     [rbp+37h+arg_20], 0
0x18006d605  jbe     short loc_18006D618
0x18006d607  test    r12, r12
0x18006d60a  jnz     short loc_18006D61D
0x18006d60c  mov     ebx, 80070057h
0x18006d611  mov     edx, 2Ch ; ','
0x18006d616  jmp     short loc_18006D5DD
0x18006d618  test    r12, r12
0x18006d61b  jnz     short loc_18006D60C
0x18006d61d  test    rax, rax
0x18006d620  jnz     short loc_18006D627
0x18006d622  lea     edx, [rax+2Dh]
0x18006d625  jmp     short loc_18006D5D8
0x18006d627  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006d62e  jz      short loc_18006D63F
0x18006d630  mov     r8d, ebx
0x18006d633  lea     rdx, EVENT_STREAMING_READER_CREATE_START
0x18006d63a  call    McTemplateU0q_EventWriteTransfer
0x18006d63f  lea     rcx, [rbp+37h+var_68]
0x18006d643  call    ??$Make@VEncryptedBundleStreamingReader@Consumption@Packaging@Appx@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEncryptedBundleStreamingReader@Consumption@Packaging@Appx@@@12@XZ; Microsoft::WRL::Details::Make<Appx::Packaging::Consumption::EncryptedBundleStreamingReader,>(void)
0x18006d648  mov     r14, [rbp+37h+var_68]
0x18006d64c  test    r14, r14
0x18006d64f  jnz     short loc_18006D65C
0x18006d651  mov     ebx, 8007000Eh
0x18006d656  lea     edx, [r14+33h]
0x18006d65a  jmp     short loc_18006D5DD
0x18006d65c  lea     rcx, [r14+120h]
0x18006d663  mov     rdx, rdi
0x18006d666  call    ??4?$ComPtr@VManifestComparisonHelper@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@PEAVManifestComparisonHelper@Packaging@Appx@@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=(Appx::Packaging::ManifestComparisonHelper *)
0x18006d66b  lea     rcx, [r14+138h]
0x18006d672  mov     [r14+118h], ebx
0x18006d679  mov     rdx, r13
0x18006d67c  call    ??4?$ComPtr@VManifestComparisonHelper@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@PEAVManifestComparisonHelper@Packaging@Appx@@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=(Appx::Packaging::ManifestComparisonHelper *)
0x18006d681  lea     r15, [r14+130h]
0x18006d688  mov     rcx, r15; struct Appx::Packaging::FileNameHelper **
0x18006d68b  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x18006d690  mov     ebx, eax
0x18006d692  test    eax, eax
0x18006d694  jns     short loc_18006D6CB
0x18006d696  mov     edx, 38h ; '8'; void *
0x18006d69b  mov     rcx, [rbp+3Fh]; this
0x18006d69f  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d6a6  mov     r9d, ebx; char *
0x18006d6a9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d6ae  test    r14, r14
0x18006d6b1  jz      loc_18006D5F0
0x18006d6b7  mov     rcx, [r14]
0x18006d6ba  mov     rax, [rcx+10h]
0x18006d6be  mov     rcx, r14
0x18006d6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d6c6  jmp     loc_18006D5F0
0x18006d6cb  mov     rcx, [r15]; this
0x18006d6ce  lea     rdx, [rbp+37h+var_78]; unsigned __int16 **
0x18006d6d2  mov     [rbp+37h+var_78], 0
0x18006d6da  call    ?GetTempFolderPathCached@FileNameHelper@Packaging@Appx@@QEAAJPEAPEBG@Z; Appx::Packaging::FileNameHelper::GetTempFolderPathCached(ushort const * *)
0x18006d6df  mov     ebx, eax
0x18006d6e1  test    eax, eax
0x18006d6e3  jns     short loc_18006D6EC
0x18006d6e5  mov     edx, 3Ah ; ':'
0x18006d6ea  jmp     short loc_18006D69B
0x18006d6ec  mov     rax, [rdi]
0x18006d6ef  lea     rcx, [rsp+110h+var_C0]
0x18006d6f4  mov     [rsp+110h+var_C0], 0
0x18006d6fd  mov     rbx, [rax+20h]
0x18006d701  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d706  lea     rdx, [rsp+110h+var_C0]
0x18006d70b  mov     rcx, rdi
0x18006d70e  mov     rax, rbx
0x18006d711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d716  xor     edi, edi
0x18006d718  mov     ebx, eax
0x18006d71a  test    eax, eax
0x18006d71c  jns     short loc_18006D753
0x18006d71e  lea     edx, [rdi+3Dh]; void *
0x18006d721  mov     rcx, [rbp+3Fh]; this
0x18006d725  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d72c  mov     r9d, ebx; char *
0x18006d72f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d734  lea     rcx, [rsp+110h+var_C0]
0x18006d739  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d73e  test    r14, r14
0x18006d741  jz      loc_18006D5F0
0x18006d747  mov     rax, [r14]
0x18006d74a  mov     rax, [rax+10h]
0x18006d74e  jmp     loc_18006D6BE
0x18006d753  test    r13, r13
0x18006d756  jz      short loc_18006D77A
0x18006d758  mov     rax, [r13+0]
0x18006d75c  mov     rcx, r13
0x18006d75f  mov     rdx, [rsp+110h+var_C0]
0x18006d764  mov     rax, [rax+20h]
0x18006d768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d76d  mov     ebx, eax
0x18006d76f  test    eax, eax
0x18006d771  jns     short loc_18006D77A
0x18006d773  mov     edx, 43h ; 'C'
0x18006d778  jmp     short loc_18006D721
0x18006d77a  mov     r15, [rsi+18h]
0x18006d77e  cmp     [r15+30h], edi
0x18006d782  jbe     loc_18006D819
0x18006d788  lea     rcx, [rbp+37h+var_B0]
0x18006d78c  mov     [rbp+37h+var_B0], rdi
0x18006d790  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d795  mov     r9, [rbp+37h+var_78]; unsigned int
0x18006d799  lea     rax, [rbp+37h+var_B0]
0x18006d79d  mov     r8d, [r15+30h]; unsigned __int64
0x18006d7a1  mov     rdx, [r15+20h]; struct IAppxRangeRequestJob *
0x18006d7a5  mov     rcx, [rsp+110h+var_C0]; this
0x18006d7aa  mov     [rsp+110h+var_E8], rax; struct IAppxFootprintFileDownloadProgressHandler *
0x18006d7af  mov     [rsp+110h+lpString1], r13; int
0x18006d7b4  call    ?DownloadToTempFileStream@Packaging@Appx@@YAJPEAUIAppxRangeRequestJob@@_KIPEBGPEAUIAppxFootprintFileDownloadProgressHandler@@PEAPEAUIStream@@@Z; Appx::Packaging::DownloadToTempFileStream(IAppxRangeRequestJob *,unsigned __int64,uint,ushort const *,IAppxFootprintFileDownloadProgressHandler *,IStream * *)
0x18006d7b9  mov     ebx, eax
0x18006d7bb  test    eax, eax
0x18006d7bd  jns     short loc_18006D7E5
0x18006d7bf  mov     edx, 52h ; 'R'; void *
0x18006d7c4  mov     rcx, [rbp+3Fh]; this
0x18006d7c8  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d7cf  mov     r9d, ebx; char *
0x18006d7d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d7d7  lea     rcx, [rbp+37h+var_B0]
0x18006d7db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d7e0  jmp     loc_18006D734
0x18006d7e5  lea     rcx, [r14+38h]
0x18006d7e9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d7ee  mov     r8, [rbp+37h+var_78]; unsigned __int16 *
0x18006d7f2  lea     r9, [r14+38h]; struct IAppxFile **
0x18006d7f6  mov     edx, [r15+28h]; enum APPX_COMPRESSION_OPTION
0x18006d7fa  mov     rcx, [rbp+37h+var_B0]; struct IStream *
0x18006d7fe  call    ?LoadSignatureFile@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@W4APPX_COMPRESSION_OPTION@@PEBGPEAPEAUIAppxFile@@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadSignatureFile(IStream *,APPX_COMPRESSION_OPTION,ushort const *,IAppxFile * *)
0x18006d803  mov     ebx, eax
0x18006d805  test    eax, eax
0x18006d807  jns     short loc_18006D810
0x18006d809  mov     edx, 54h ; 'T'
0x18006d80e  jmp     short loc_18006D7C4
0x18006d810  lea     rcx, [rbp+37h+var_B0]
0x18006d814  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d819  mov     rdx, [r14+38h]
0x18006d81d  lea     r8, [rbp+37h+var_B0]
0x18006d821  mov     ecx, [rbp+37h+var_80]
0x18006d824  mov     [rbp+37h+var_B0], rdi
0x18006d828  call    ?Create@EncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@SAJW4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxFile@@PEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(APPX_PACKAGE_READER_OPTIONS,IAppxFile *,Appx::Packaging::Consumption::EncryptedAppxSignatureValidator * *)
0x18006d82d  mov     ebx, eax
0x18006d82f  test    eax, eax
0x18006d831  jns     short loc_18006D88E
0x18006d833  mov     esi, 800B0100h
0x18006d838  cmp     eax, esi
0x18006d83a  jnz     short loc_18006D868
0x18006d83c  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x18006d843  jz      short loc_18006D854
0x18006d845  mov     r8d, esi
0x18006d848  lea     rdx, EVENT_BUNDLE_UNSIGNED
0x18006d84f  call    McTemplateU0q_EventWriteTransfer
0x18006d854  mov     r8d, esi; int
0x18006d857  lea     rcx, EVENT_BUNDLE_UNSIGNED; struct _EVENT_DESCRIPTOR *
0x18006d85e  mov     edx, 0B00000A3h; unsigned int
0x18006d863  call    ?AppxPackagingLog@@YAJAEBU_EVENT_DESCRIPTOR@@KJ@Z; AppxPackagingLog(_EVENT_DESCRIPTOR const &,ulong,long)
0x18006d868  mov     rcx, [rbp+3Fh]; this
0x18006d86c  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d873  mov     r9d, ebx; char *
0x18006d876  mov     edx, 60h ; '`'; void *
0x18006d87b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d880  mov     rcx, [rbp+37h+var_B0]; void *
0x18006d884  call    ??$AutoPtrDeallocate@VEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(Appx::Packaging::Consumption::EncryptedAppxSignatureValidator *)
0x18006d889  jmp     loc_18006D734
0x18006d88e  mov     rbx, [rbp+37h+var_B0]
0x18006d892  mov     rdx, r15; struct Appx::Packaging::EncryptedAppxHeader *
0x18006d895  mov     r8, [rsi+20h]; unsigned __int8 *
0x18006d899  mov     rcx, rbx; this
0x18006d89c  call    ?ValidateHeaderIfNeeded@EncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@QEAAJPEAVEncryptedAppxHeader@34@PEBE@Z; Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateHeaderIfNeeded(Appx::Packaging::EncryptedAppxHeader *,uchar const *)
0x18006d8a1  mov     edi, eax
0x18006d8a3  test    eax, eax
0x18006d8a5  jns     short loc_18006D8C4
0x18006d8a7  mov     edx, 62h ; 'b'; void *
0x18006d8ac  mov     rcx, [rbp+3Fh]; this
0x18006d8b0  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d8b7  mov     r9d, edi; char *
0x18006d8ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d8bf  jmp     loc_18006E103
0x18006d8c4  mov     rdx, [r15+8]
0x18006d8c8  mov     rsi, [rbp+37h+var_88]
0x18006d8cc  cmp     rsi, rdx
0x18006d8cf  ja      short loc_18006D915
0x18006d8d1  mov     rcx, [rbp+3Fh]; this
0x18006d8d5  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d8dc  mov     edi, 8007000Dh
0x18006d8e1  mov     edx, 65h ; 'e'; void *
0x18006d8e6  mov     r9d, edi; char *
0x18006d8e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d8ee  mov     rcx, rbx; void *
0x18006d8f1  call    ??$AutoPtrDeallocate@VEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(Appx::Packaging::Consumption::EncryptedAppxSignatureValidator *)
0x18006d8f6  lea     rcx, [rsp+110h+var_C0]
0x18006d8fb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d900  test    r14, r14
0x18006d903  jz      loc_18006E129
0x18006d909  mov     rcx, [r14]
0x18006d90c  mov     rax, [rcx+10h]
0x18006d910  jmp     loc_18006E121
0x18006d915  mov     eax, 0FFFFFFFFh
0x18006d91a  cmp     [r15+10h], rax
0x18006d91e  jbe     short loc_18006D962
0x18006d920  mov     rcx, [rbp+3Fh]; this
0x18006d924  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d92b  mov     r9d, 800700DFh; char *
0x18006d931  mov     edx, 66h ; 'f'; void *
0x18006d936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d93b  mov     rcx, rbx; void *
0x18006d93e  call    ??$AutoPtrDeallocate@VEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(Appx::Packaging::Consumption::EncryptedAppxSignatureValidator *)
0x18006d943  lea     rcx, [rsp+110h+var_C0]
0x18006d948  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d94d  test    r14, r14
0x18006d950  jz      loc_18006DEEE
0x18006d956  mov     rax, [r14]
0x18006d959  mov     rax, [rax+10h]
0x18006d95d  jmp     loc_18006DEE6
0x18006d962  mov     rcx, [rsp+110h+var_C0]
0x18006d967  mov     r8d, [r15+10h]
0x18006d96b  mov     rax, [rcx]
0x18006d96e  mov     rax, [rax+18h]
0x18006d972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d977  mov     edi, eax
0x18006d979  test    eax, eax
0x18006d97b  jns     short loc_18006D987
0x18006d97d  mov     edx, 68h ; 'h'
0x18006d982  jmp     loc_18006D8AC
0x18006d987  mov     edi, [rbp+37h+var_80]
0x18006d98a  lea     rcx, [rsp+110h+var_B8]
0x18006d98f  and     edi, 1
0x18006d992  mov     [rsp+110h+var_B8], 0
0x18006d99b  mov     [rbp+37h+var_80], edi
0x18006d99e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006d9a3  mov     r9, [rbp+37h+var_78]; unsigned __int16 *
0x18006d9a7  lea     rcx, [rsp+110h+var_B8]
0x18006d9ac  mov     [rsp+110h+var_E8], rcx; struct Appx::Packaging::Consumption::EncryptedAppxFootersReceiver **
0x18006d9b1  test    edi, edi
0x18006d9b3  mov     r8, rsi; unsigned __int64
0x18006d9b6  mov     rcx, r15; struct Appx::Packaging::EncryptedAppxHeader *
0x18006d9b9  setnz   al
0x18006d9bc  xor     edx, edx; unsigned __int64
0x18006d9be  mov     byte ptr [rsp+110h+lpString1], al; int
0x18006d9c2  call    ?Create@EncryptedAppxFootersReceiver@Consumption@Packaging@Appx@@SAJPEAVEncryptedAppxHeader@34@_K1PEBG_NPEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::Create(Appx::Packaging::EncryptedAppxHeader *,unsigned __int64,unsigned __int64,ushort const *,bool,Appx::Packaging::Consumption::EncryptedAppxFootersReceiver * *)
0x18006d9c7  mov     edi, eax
0x18006d9c9  test    eax, eax
0x18006d9cb  jns     short loc_18006D9EA
0x18006d9cd  mov     edx, 72h ; 'r'; void *
0x18006d9d2  mov     rcx, [rbp+3Fh]; this
0x18006d9d6  lea     r8, aOnecorePrintsc_46; "onecore\\printscan\\appxpackaging\\cons"...
0x18006d9dd  mov     r9d, edi; char *
0x18006d9e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d9e5  jmp     loc_18006E0F9
0x18006d9ea  mov     rcx, [rsp+110h+var_C0]
0x18006d9ef  mov     edx, 3
0x18006d9f4  mov     rsi, [rsp+110h+var_B8]
0x18006d9f9  mov     r8, rsi
0x18006d9fc  mov     rax, [rcx]
0x18006d9ff  mov     rax, [rax+20h]
0x18006da03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da08  mov     edi, eax
0x18006da0a  test    eax, eax
0x18006da0c  jns     short loc_18006DA15
0x18006da0e  mov     edx, 74h ; 't'
0x18006da13  jmp     short loc_18006D9D2
  ... truncated ...
```
