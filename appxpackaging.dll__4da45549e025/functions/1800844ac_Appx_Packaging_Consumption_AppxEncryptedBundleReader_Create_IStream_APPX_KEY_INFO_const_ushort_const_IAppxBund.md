# Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(IStream *,APPX_KEY_INFO const *,ushort const *,IAppxBundleReader * *,Appx::Packaging::Encryption::EncryptionKeyType)

- ea: `0x1800844ac`
- end: `0x180084e1c`
- name: `?Create@AppxEncryptedBundleReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEBGPEAPEAUIAppxBundleReader@@W4EncryptionKeyType@Encryption@34@@Z`
- size: `2416`
- prototype: `static int __high(struct IStream *, const struct APPX_KEY_INFO *, const unsigned __int16 *, struct IAppxBundleReader **, enum Appx::Packaging::Encryption::EncryptionKeyType)`
- caller_count: `5`
- callee_count: `34`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007ef00`
- `0x180091410`
- `0x1800c4fa0`
- `0x1800c4fe0`
- `0x1800c5450`

## callees

- `0x180005eb8`
- `0x18000849c`
- `0x1800133fc`
- `0x180022b50`
- `0x180024894`
- `0x180024974`
- `0x180046da4`
- `0x180046e28`
- `0x18005dbd8`
- `0x18006c8e0`
- `0x18006f358`
- `0x18006ffd0`
- `0x180071f50`
- `0x1800728bc`
- `0x180082690`
- `0x180084398`
- `0x1800844ac`
- `0x180084e24`
- `0x1800850b0`
- `0x1800850dc`
- `0x180086460`
- `0x1800868e8`
- `0x180086918`
- `0x180086a74`
- `0x180086c80`
- `0x180086f40`
- `0x180086ffc`
- `0x180087058`
- `0x180087158`
- `0x1800871d4`
- `0x180087278`
- `0x1800992a0`
- `0x1800ca960`
- `0x180106010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800849a7`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x1800849a7`
- `OpcServices!__imp_GetCloneableStream` at `0x18008460e`
- `OpcServices!__imp_GetCloneableStream` at `0x18008460e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084cb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084d79`

## string_xrefs

- `0x180084bff`: `AppxMetadata\AppxBundleManifest.xml`
- `0x180084502`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084541`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x1800845ae`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084628`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x18008465d`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x18008469b`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084705`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084758`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x1800847c7`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084827`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084876`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x1800848eb`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084a1b`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084abe`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084b33`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084c24`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084c98`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180084d65`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(
        __int64 a1,
        struct APPX_KEY_INFO *a2,
        Appx::Packaging *a3,
        _QWORD *a4,
        int a5)
{
  _QWORD *v5; // rdi
  struct APPX_KEY_INFO *v6; // rbx
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int valid; // eax
  unsigned int v11; // edi
  int KeyInfo; // eax
  int CloneableStream; // eax
  unsigned int v15; // edi
  Appx::Packaging::Consumption::AppxEncryptedBundleReader *v16; // r15
  struct IStream **v17; // r13
  int Header; // eax
  struct IStream *v19; // rdx
  int v20; // eax
  struct Appx::Packaging::AppxEncryptionSettings *v21; // r14
  int v22; // eax
  int v23; // eax
  Appx::Packaging::FileNameHelper *v24; // rdi
  struct APPX_KEY_INFO *v25; // rbx
  int BlockMapEncryptedFile; // esi
  __int64 v27; // rdx
  struct Appx::Packaging::FileNameHelper *v28; // rsi
  __int64 v29; // rdx
  struct Appx::Packaging::FileNameHelper *v30; // rcx
  int v31; // eax
  const unsigned __int16 *v32; // r8
  int matched; // r12d
  __int64 v34; // rdx
  int v35; // r9d
  __int64 v36; // rdx
  int BundleManifest; // eax
  __int64 v38; // rcx
  __int64 v39; // r8
  int AppxFilesWithManifestData; // r14d
  __int64 v41; // rdx
  char v42; // al
  Appx::Packaging::Consumption::AppxEncryptedBundleReader **lpString1; // [rsp+20h] [rbp-1E8h]
  int lpString1a; // [rsp+20h] [rbp-1E8h]
  int lpString1b; // [rsp+20h] [rbp-1E8h]
  int lpString1c; // [rsp+20h] [rbp-1E8h]
  Appx::Packaging **lpString1d; // [rsp+20h] [rbp-1E8h]
  __int64 v48; // [rsp+50h] [rbp-1B8h] BYREF
  struct Appx::Packaging::AppxEncryptionSettings *v49; // [rsp+58h] [rbp-1B0h] BYREF
  struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *v50; // [rsp+60h] [rbp-1A8h] BYREF
  struct Appx::Packaging::FileNameHelper *v51; // [rsp+68h] [rbp-1A0h] BYREF
  struct APPX_KEY_INFO *v52; // [rsp+70h] [rbp-198h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-190h] BYREF
  unsigned int v54; // [rsp+80h] [rbp-188h]
  _QWORD *v55; // [rsp+88h] [rbp-180h]
  __int128 v56; // [rsp+90h] [rbp-178h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-168h]
  _DWORD v58[8]; // [rsp+B0h] [rbp-158h] BYREF
  unsigned __int64 v59; // [rsp+D0h] [rbp-138h]
  enum APPX_COMPRESSION_OPTION v60; // [rsp+D8h] [rbp-130h]
  unsigned __int64 v61; // [rsp+E0h] [rbp-128h]
  Appx::Packaging::Consumption::AppxEncryptedBundleReader *v62[2]; // [rsp+1A0h] [rbp-68h] BYREF
  Appx::Packaging *v63; // [rsp+1B0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  v55 = a4;
  v63 = a3;
  v5 = a4;
  v52 = a2;
  v6 = a2;
  if ( a1 )
  {
    if ( !a4 )
    {
      v8 = 51;
      goto LABEL_3;
    }
    if ( a2 )
    {
      valid = Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(a2);
      v11 = valid;
      if ( valid < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)(unsigned int)valid,
          (int)lpString1);
        return v11;
      }
      v5 = v55;
    }
    v57 = 0;
    v56 = 0;
    if ( !v6 )
    {
      if ( a5 == 1 )
      {
        KeyInfo = Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(
                    (Appx::Packaging::GlobalDevKeyInfo *)&v56,
                    (const struct APPX_KEY_INFO **)&v52);
        v9 = KeyInfo;
        if ( KeyInfo < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x3D,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
            (const char *)(unsigned int)KeyInfo,
            (int)lpString1);
LABEL_93:
          Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo((Appx::Packaging::GlobalDevKeyInfo *)&v56);
          return v9;
        }
        v6 = v52;
      }
      else if ( !a5 )
      {
        v9 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)0x80070057LL,
          (int)lpString1);
        goto LABEL_93;
      }
    }
    *v5 = 0;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      lpString1 = v62;
      McGenEventWrite_EventWriteTransfer(a1, EVENT_BUNDLE_READER_CREATE_START, a3, 1);
    }
    v48 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
    CloneableStream = GetCloneableStream(a1, &v48);
    v15 = CloneableStream;
    if ( CloneableStream < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)CloneableStream,
        (int)lpString1);
LABEL_19:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
      v9 = v15;
      goto LABEL_93;
    }
    Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxEncryptedBundleReader>,>(v62);
    v16 = v62[0];
    if ( !v62[0] )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)0x8007000ELL,
        (int)lpString1);
LABEL_24:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
      goto LABEL_93;
    }
    v17 = (struct IStream **)((char *)v62[0] + 240);
    Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=((char *)v62[0] + 240, &v48);
    Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
    Header = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadHeader(
               *v17,
               v6,
               (struct Appx::Packaging::EncryptedAppxHeader *)v58);
    v15 = Header;
    if ( Header < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)Header,
        (int)lpString1);
      goto LABEL_27;
    }
    if ( v58[0] != 1212307525 )
    {
      v9 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)0x8007000DLL,
        (int)lpString1);
      goto LABEL_31;
    }
    v19 = *v17;
    v52 = 0;
    v20 = Appx::Packaging::EncryptedAppxFootersReader::Create(
            (struct Appx::Packaging::EncryptedAppxHeader *)v58,
            v19,
            0,
            (struct Appx::Packaging::EncryptedAppxFootersReader **)&v52);
    v15 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)v20,
        (int)lpString1);
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v52);
LABEL_27:
      Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
      if ( v16 )
        (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v16 + 16LL))(v16);
      goto LABEL_19;
    }
    v49 = 0;
    v21 = 0;
    if ( v6 )
    {
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      v22 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(
              (const struct Appx::Packaging::EncryptedAppxHeader *)v58,
              v6->keyLength,
              v6->key,
              &v49);
      v9 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)(unsigned int)v22,
          (int)lpString1);
LABEL_38:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
        Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v52);
LABEL_31:
        Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
        if ( v16 )
          (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v16 + 16LL))(v16);
        goto LABEL_24;
      }
      v21 = v49;
    }
    v51 = 0;
    v23 = Appx::Packaging::FileNameHelper::Create(&v51);
    v9 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)v23,
        (int)lpString1);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v51);
      goto LABEL_38;
    }
    v50 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    v24 = v51;
    v25 = v52;
    BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(
                              (const struct Appx::Packaging::EncryptedAppxHeader *)v58,
                              (struct Appx::Packaging::EncryptedAppxFootersReader *)v52,
                              v21,
                              v51,
                              *v17,
                              &v50);
    if ( BlockMapEncryptedFile < 0 )
    {
      v27 = 103;
LABEL_44:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)BlockMapEncryptedFile,
        lpString1a);
LABEL_45:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v24);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v25);
      Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
      if ( v16 )
        (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v16 + 16LL))(v16);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
      v9 = BlockMapEncryptedFile;
      goto LABEL_93;
    }
    BlockMapEncryptedFile = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                              &v50,
                              (char *)v16 + 48);
    if ( BlockMapEncryptedFile < 0 )
    {
      v27 = 104;
      goto LABEL_44;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v16 + 24);
    BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(
                              (const struct Appx::Packaging::EncryptedAppxHeader *)v58,
                              v50,
                              (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)v16 + 3);
    if ( BlockMapEncryptedFile < 0 )
    {
      v27 = 105;
      goto LABEL_44;
    }
    v54 = RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)(*((_QWORD *)v16 + 3) + 56LL));
    v28 = 0;
    v51 = 0;
    v62[0] = 0;
    if ( (_DWORD)v61 )
    {
      v52 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
      BlockMapEncryptedFile = Appx::Packaging::SubStream::Create(*v17, v59, (unsigned int)v61, (struct IStream **)&v52);
      if ( BlockMapEncryptedFile < 0 )
      {
        v29 = 122;
LABEL_55:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)(unsigned int)BlockMapEncryptedFile,
          lpString1a);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
        v30 = 0;
LABEL_56:
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v30);
        goto LABEL_45;
      }
      v62[0] = 0;
      BlockMapEncryptedFile = Appx::Packaging::FileNameHelper::GetTempFolderPathCached(
                                v24,
                                (const unsigned __int16 **)v62);
      if ( BlockMapEncryptedFile < 0 )
      {
        v29 = 124;
        goto LABEL_55;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v16 + 56);
      BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadSignatureFile(
                                (struct IStream *)v52,
                                v60,
                                (const unsigned __int16 *)v62[0],
                                (struct IAppxFile **)v16 + 7);
      if ( BlockMapEncryptedFile < 0 )
      {
        v29 = 129;
        goto LABEL_55;
      }
      v31 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(0, *((_QWORD *)v16 + 7), &v51);
      BlockMapEncryptedFile = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)(unsigned int)v31,
          lpString1a);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
        v30 = v51;
        goto LABEL_56;
      }
      v28 = v51;
      v62[0] = *((Appx::Packaging::Consumption::AppxEncryptedBundleReader **)v51 + 3);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
    }
    if ( v63 )
    {
      matched = Appx::Packaging::CalculateDigestFromFootprintFiles((char *)v16 + 40, (char *)v16 + 224);
      if ( matched < 0 )
      {
        v34 = 141;
LABEL_67:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)(unsigned int)matched,
          lpString1a);
LABEL_68:
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v28);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
        Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v24);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
        Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v25);
        Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
        if ( v16 )
          (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v16 + 16LL))(v16);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
        v9 = matched;
        goto LABEL_93;
      }
      matched = Appx::Packaging::VerifyDigest(v63, *((const unsigned __int16 **)v16 + 28), v32);
      if ( matched < 0 )
      {
        v34 = 142;
        goto LABEL_67;
      }
    }
    v51 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
    matched = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(
                (int)v25,
                *((_QWORD *)v16 + 3),
                (int)v21,
                v35,
                L"AppxMetadata\\AppxBundleManifest.xml",
                *v17,
                (__int64)&v51,
                0,
                0);
    if ( matched < 0 )
    {
      v36 = 156;
LABEL_75:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)matched,
        lpString1b);
LABEL_76:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
      goto LABEL_68;
    }
    matched = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                &v51,
                (char *)v16 + 40);
    if ( matched < 0 )
    {
      v36 = 157;
      goto LABEL_75;
    }
    pv = 0;
    BundleManifest = Appx::Packaging::Consumption::AppxEncryptedBundleReader::LoadBundleManifest(
                       v16,
                       v51,
                       v21,
                       (const unsigned __int16 *)v62[0],
                       (unsigned __int16 **)&pv);
    matched = BundleManifest;
    if ( BundleManifest < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)BundleManifest,
        lpString1c);
      CoTaskMemFree(pv);
      goto LABEL_76;
    }
    AppxFilesWithManifestData = Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateAppxFilesWithManifestData(
                                  v16,
                                  (const struct Appx::Packaging::EncryptedAppxHeader *)v58,
                                  (struct Appx::Packaging::EncryptedAppxFootersReader *)v25,
                                  v54,
                                  v21);
    if ( AppxFilesWithManifestData >= 0 )
    {
      v42 = Microsoft_Windows_AppxPackagingOMEnableBits;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(v38, EVENT_BUNDLE_READER_CREATED, pv);
        v42 = Microsoft_Windows_AppxPackagingOMEnableBits;
      }
      if ( (v42 & 0x10) != 0 )
      {
        lpString1d = &v63;
        McGenEventWrite_EventWriteTransfer(v38, EVENT_BUNDLE_READER_CREATE_STOP, v39, 1);
      }
      AppxFilesWithManifestData = (**(__int64 (__fastcall ***)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *, GUID *, _QWORD *))v16)(
                                    v16,
                                    &GUID_dd75b8c0_ba76_43b0_ae0f_68656a1dc5c8,
                                    v55);
      if ( AppxFilesWithManifestData >= 0 )
        goto LABEL_90;
      v41 = 172;
    }
    else
    {
      v41 = 166;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
      (const char *)(unsigned int)AppxFilesWithManifestData,
      (int)lpString1d);
LABEL_90:
    CoTaskMemFree(pv);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v51);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v28);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
    Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v24);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v25);
    Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v58);
    if ( v16 )
      (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxEncryptedBundleReader *))(*(_QWORD *)v16 + 16LL))(v16);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
    v9 = AppxFilesWithManifestData;
    goto LABEL_93;
  }
  v8 = 50;
LABEL_3:
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
    (const char *)0x80004003LL,
    (int)lpString1);
  return v9;
}

```

## disassembly

```asm
0x1800844ac  push    rbx
0x1800844ae  push    rsi
0x1800844af  push    rdi
0x1800844b0  push    r12
0x1800844b2  push    r13
0x1800844b4  push    r14
0x1800844b6  push    r15
0x1800844b8  sub     rsp, 1D0h
0x1800844bf  mov     rax, cs:__security_cookie
0x1800844c6  xor     rax, rsp
0x1800844c9  mov     [rsp+208h+var_48], rax
0x1800844d1  xor     r12d, r12d
0x1800844d4  mov     [rsp+208h+var_180], r9
0x1800844dc  mov     [rsp+208h+var_58], r8
0x1800844e4  mov     rdi, r9
0x1800844e7  mov     [rsp+208h+var_198], rdx
0x1800844ec  mov     rbx, rdx
0x1800844ef  mov     rsi, rcx
0x1800844f2  test    rcx, rcx
0x1800844f5  jnz     short loc_18008451B
0x1800844f7  lea     edx, [rcx+32h]; void *
0x1800844fa  mov     rcx, [rsp+208h]; this
0x180084502  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180084509  mov     ebx, 80004003h
0x18008450e  mov     r9d, ebx; char *
0x180084511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084516  jmp     loc_180084DF6
0x18008451b  test    r9, r9
0x18008451e  jnz     short loc_180084526
0x180084520  lea     edx, [r9+33h]
0x180084524  jmp     short loc_1800844FA
0x180084526  test    rbx, rbx
0x180084529  jz      short loc_180084564
0x18008452b  mov     rcx, rbx; struct APPX_KEY_INFO *
0x18008452e  call    ?ValidAppxKeyInfo@EncryptionHelper@Packaging@Appx@@SAJAEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::EncryptionHelper::ValidAppxKeyInfo(APPX_KEY_INFO const &)
0x180084533  mov     edi, eax
0x180084535  test    eax, eax
0x180084537  jns     short loc_18008455C
0x180084539  mov     rcx, [rsp+208h]; this
0x180084541  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180084548  mov     r9d, eax; char *
0x18008454b  mov     edx, 35h ; '5'; void *
0x180084550  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180084555  mov     eax, edi
0x180084557  jmp     loc_180084DF8
0x18008455c  mov     rdi, [rsp+208h+var_180]
0x180084564  xor     eax, eax
0x180084566  xorps   xmm0, xmm0
0x180084569  mov     [rsp+208h+var_168], rax
0x180084571  movups  [rsp+208h+var_178], xmm0
0x180084579  test    rbx, rbx
0x18008457c  jnz     short loc_1800845CC
0x18008457e  mov     eax, [rsp+208h+arg_20]
0x180084585  cmp     eax, 1
0x180084588  jnz     loc_18008464D
0x18008458e  lea     rdx, [rsp+208h+var_198]; struct APPX_KEY_INFO **
0x180084593  lea     rcx, [rsp+208h+var_178]; this
0x18008459b  call    ?GetKeyInfo@GlobalDevKeyInfo@Packaging@Appx@@QEAAJPEAPEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(APPX_KEY_INFO const * *)
0x1800845a0  mov     ebx, eax
0x1800845a2  test    eax, eax
0x1800845a4  jns     short loc_1800845C7
0x1800845a6  mov     rcx, [rsp+208h]; this
0x1800845ae  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x1800845b5  mov     r9d, eax; char *
0x1800845b8  mov     edx, 3Dh ; '='; void *
0x1800845bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800845c2  jmp     loc_180084DE9
0x1800845c7  mov     rbx, [rsp+208h+var_198]
0x1800845cc  mov     [rdi], r12
0x1800845cf  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x1800845d6  jz      short loc_1800845F7
0x1800845d8  lea     rax, [rsp+208h+var_68]
0x1800845e0  mov     r9d, 1
0x1800845e6  lea     rdx, EVENT_BUNDLE_READER_CREATE_START
0x1800845ed  mov     [rsp+208h+lpString1], rax; int
0x1800845f2  call    McGenEventWrite_EventWriteTransfer
0x1800845f7  lea     rcx, [rsp+208h+var_1B8]
0x1800845fc  mov     [rsp+208h+var_1B8], r12
0x180084601  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084606  lea     rdx, [rsp+208h+var_1B8]
0x18008460b  mov     rcx, rsi
0x18008460e  call    cs:__imp_GetCloneableStream
0x180084615  nop     dword ptr [rax+rax+00h]
0x18008461a  mov     edi, eax
0x18008461c  test    eax, eax
0x18008461e  jns     short loc_180084679
0x180084620  mov     rcx, [rsp+208h]; this
0x180084628  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18008462f  mov     r9d, eax; char *
0x180084632  mov     edx, 4Ch ; 'L'; void *
0x180084637  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008463c  lea     rcx, [rsp+208h+var_1B8]
0x180084641  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084646  mov     ebx, edi
0x180084648  jmp     loc_180084DE9
0x18008464d  test    eax, eax
0x18008464f  jnz     loc_1800845CC
0x180084655  mov     rcx, [rsp+208h]; this
0x18008465d  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180084664  mov     ebx, 80070057h
0x180084669  lea     edx, [rax+41h]; void *
0x18008466c  mov     r9d, ebx; char *
0x18008466f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084674  jmp     loc_180084DE9
0x180084679  lea     rcx, [rsp+208h+var_68]
0x180084681  call    ??$Make@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxEncryptedBundleReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxEncryptedBundleReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@12@XZ; Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxEncryptedBundleReader>,>(void)
0x180084686  mov     r15, [rsp+208h+var_68]
0x18008468e  test    r15, r15
0x180084691  jnz     short loc_1800846C2
0x180084693  mov     rcx, [rsp+208h]; this
0x18008469b  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x1800846a2  mov     ebx, 8007000Eh
0x1800846a7  lea     edx, [r15+4Fh]; void *
0x1800846ab  mov     r9d, ebx; char *
0x1800846ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800846b3  lea     rcx, [rsp+208h+var_1B8]
0x1800846b8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800846bd  jmp     loc_180084DE9
0x1800846c2  lea     r13, [r15+0F0h]
0x1800846c9  mov     rcx, r13
0x1800846cc  lea     rdx, [rsp+208h+var_1B8]
0x1800846d1  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800846d6  lea     rcx, [rsp+208h+var_158]; this
0x1800846de  call    ??0EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader(void)
0x1800846e3  mov     rcx, [r13+0]; struct IStream *
0x1800846e7  lea     r8, [rsp+208h+var_158]; struct Appx::Packaging::EncryptedAppxHeader *
0x1800846ef  mov     rdx, rbx; struct APPX_KEY_INFO *
0x1800846f2  call    ?LoadHeader@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@AEAVEncryptedAppxHeader@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadHeader(IStream *,APPX_KEY_INFO const *,Appx::Packaging::EncryptedAppxHeader &)
0x1800846f7  mov     edi, eax
0x1800846f9  test    eax, eax
0x1800846fb  jns     short loc_180084743
0x1800846fd  mov     rcx, [rsp+208h]; this
0x180084705  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18008470c  mov     r9d, eax; char *
0x18008470f  mov     edx, 53h ; 'S'; void *
0x180084714  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180084719  lea     rcx, [rsp+208h+var_158]; this
0x180084721  call    ??1EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader(void)
0x180084726  test    r15, r15
0x180084729  jz      loc_18008463C
0x18008472f  mov     rax, [r15]
0x180084732  mov     rcx, r15
0x180084735  mov     rax, [rax+10h]
0x180084739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008473e  jmp     loc_18008463C
0x180084743  cmp     [rsp+208h+var_158], 48425845h
0x18008474e  jz      short loc_18008479B
0x180084750  mov     rcx, [rsp+208h]; this
0x180084758  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18008475f  mov     ebx, 8007000Dh
0x180084764  mov     edx, 56h ; 'V'; void *
0x180084769  mov     r9d, ebx; char *
0x18008476c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084771  lea     rcx, [rsp+208h+var_158]; this
0x180084779  call    ??1EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader(void)
0x18008477e  test    r15, r15
0x180084781  jz      loc_1800846B3
0x180084787  mov     rax, [r15]
0x18008478a  mov     rcx, r15
0x18008478d  mov     rax, [rax+10h]
0x180084791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084796  jmp     loc_1800846B3
0x18008479b  mov     rdx, [r13+0]; struct IStream *
0x18008479f  lea     r9, [rsp+208h+var_198]; struct Appx::Packaging::EncryptedAppxFootersReader **
0x1800847a4  xor     r8d, r8d; unsigned __int64
0x1800847a7  mov     [rsp+208h+var_198], r12
0x1800847ac  lea     rcx, [rsp+208h+var_158]; struct Appx::Packaging::EncryptedAppxHeader *
0x1800847b4  call    ?Create@EncryptedAppxFootersReader@Packaging@Appx@@SAJPEAVEncryptedAppxHeader@23@PEAUIStream@@_KPEAPEAV123@@Z; Appx::Packaging::EncryptedAppxFootersReader::Create(Appx::Packaging::EncryptedAppxHeader *,IStream *,unsigned __int64,Appx::Packaging::EncryptedAppxFootersReader * *)
0x1800847b9  mov     edi, eax
0x1800847bb  test    eax, eax
0x1800847bd  jns     short loc_1800847EA
0x1800847bf  mov     rcx, [rsp+208h]; this
0x1800847c7  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x1800847ce  mov     r9d, eax; char *
0x1800847d1  mov     edx, 59h ; 'Y'; void *
0x1800847d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800847db  mov     rcx, [rsp+208h+var_198]; void *
0x1800847e0  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x1800847e5  jmp     loc_180084719
0x1800847ea  mov     [rsp+208h+var_1B0], r12
0x1800847ef  mov     r14, r12
0x1800847f2  test    rbx, rbx
0x1800847f5  jz      short loc_180084859
0x1800847f7  lea     rcx, [rsp+208h+var_1B0]
0x1800847fc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084801  mov     r8, [rbx+8]; unsigned __int8 *
0x180084805  lea     r9, [rsp+208h+var_1B0]; struct Appx::Packaging::AppxEncryptionSettings **
0x18008480a  mov     edx, [rbx]; unsigned int
0x18008480c  lea     rcx, [rsp+208h+var_158]; struct Appx::Packaging::EncryptedAppxHeader *
0x180084814  call    ?CreateEncryptionSettings@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@IPEBEPEAPEAVAppxEncryptionSettings@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(Appx::Packaging::EncryptedAppxHeader const &,uint,uchar const *,Appx::Packaging::AppxEncryptionSettings * *)
0x180084819  mov     ebx, eax
0x18008481b  test    eax, eax
0x18008481d  jns     short loc_180084854
0x18008481f  mov     rcx, [rsp+208h]; this
0x180084827  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18008482e  mov     r9d, eax; char *
0x180084831  mov     edx, 5Eh ; '^'; void *
0x180084836  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008483b  lea     rcx, [rsp+208h+var_1B0]
0x180084840  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084845  mov     rcx, [rsp+208h+var_198]; void *
0x18008484a  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x18008484f  jmp     loc_180084771
0x180084854  mov     r14, [rsp+208h+var_1B0]
0x180084859  lea     rcx, [rsp+208h+var_1A0]; struct Appx::Packaging::FileNameHelper **
0x18008485e  mov     [rsp+208h+var_1A0], r12
0x180084863  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x180084868  mov     ebx, eax
0x18008486a  test    eax, eax
0x18008486c  jns     short loc_180084896
0x18008486e  mov     rcx, [rsp+208h]; this
0x180084876  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18008487d  mov     r9d, eax; char *
0x180084880  mov     edx, 62h ; 'b'; void *
0x180084885  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008488a  mov     rcx, [rsp+208h+var_1A0]
0x18008488f  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x180084894  jmp     short loc_18008483B
0x180084896  lea     rcx, [rsp+208h+var_1A8]
0x18008489b  mov     [rsp+208h+var_1A8], r12
0x1800848a0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800848a5  mov     rdi, [rsp+208h+var_1A0]
0x1800848aa  lea     rax, [rsp+208h+var_1A8]
0x1800848af  mov     rbx, [rsp+208h+var_198]
0x1800848b4  lea     rcx, [rsp+208h+var_158]; struct Appx::Packaging::EncryptedAppxHeader *
0x1800848bc  mov     [rsp+208h+var_1E0], rax; struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile **
0x1800848c1  mov     r9, rdi; struct Appx::Packaging::FileNameHelper *
0x1800848c4  mov     rax, [r13+0]
0x1800848c8  mov     r8, r14; struct Appx::Packaging::AppxEncryptionSettings *
0x1800848cb  mov     rdx, rbx; struct Appx::Packaging::EncryptedAppxFootersReader *
0x1800848ce  mov     [rsp+208h+lpString1], rax; int
0x1800848d3  call    ?GetBlockMapEncryptedFile@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@PEAVEncryptedAppxFootersReader@34@PEAVAppxEncryptionSettings@34@PEAVFileNameHelper@34@PEAUIStream@@PEAPEAVAppxEncryptedBlockMapFile@234@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::EncryptedAppxFootersReader *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::FileNameHelper *,IStream *,Appx::Packaging::Consumption::AppxEncryptedBlockMapFile * *)
0x1800848d8  mov     esi, eax
0x1800848da  test    eax, eax
0x1800848dc  jns     short loc_180084950
0x1800848de  mov     edx, 67h ; 'g'; void *
0x1800848e3  mov     rcx, [rsp+208h]; this
0x1800848eb  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x1800848f2  mov     r9d, esi; char *
0x1800848f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800848fa  lea     rcx, [rsp+208h+var_1A8]
0x1800848ff  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084904  mov     rcx, rdi
0x180084907  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x18008490c  lea     rcx, [rsp+208h+var_1B0]
0x180084911  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084916  mov     rcx, rbx; void *
0x180084919  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x18008491e  lea     rcx, [rsp+208h+var_158]; this
0x180084926  call    ??1EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader(void)
0x18008492b  test    r15, r15
0x18008492e  jz      short loc_18008493F
0x180084930  mov     rax, [r15]
0x180084933  mov     rcx, r15
0x180084936  mov     rax, [rax+10h]
0x18008493a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008493f  lea     rcx, [rsp+208h+var_1B8]
0x180084944  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180084949  mov     ebx, esi
0x18008494b  jmp     loc_180084DE9
0x180084950  lea     rdx, [r15+30h]
0x180084954  lea     rcx, [rsp+208h+var_1A8]
0x180084959  call    ??$As@UIAppxFile@@@?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxFile@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxFile>>)
0x18008495e  mov     esi, eax
0x180084960  test    eax, eax
0x180084962  jns     short loc_18008496E
0x180084964  mov     edx, 68h ; 'h'
0x180084969  jmp     loc_1800848E3
0x18008496e  lea     r12, [r15+18h]
0x180084972  mov     rcx, r12
0x180084975  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008497a  mov     rdx, [rsp+208h+var_1A8]; struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *
0x18008497f  lea     rcx, [rsp+208h+var_158]; struct Appx::Packaging::EncryptedAppxHeader *
0x180084987  mov     r8, r12; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x18008498a  call    ?LoadBlockMap@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@PEAVAppxEncryptedBlockMapFile@234@PEAPEAVAppxBlockMapReader@BlockMap@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x18008498f  mov     esi, eax
0x180084991  test    eax, eax
0x180084993  jns     short loc_18008499F
0x180084995  mov     edx, 69h ; 'i'
0x18008499a  jmp     loc_1800848E3
0x18008499f  mov     rcx, [r12]
0x1800849a3  mov     rcx, [rcx+38h]; Table
0x1800849a7  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x1800849ae  nop     dword ptr [rax+rax+00h]
0x1800849b3  xor     r12d, r12d
0x1800849b6  mov     [rsp+208h+var_188], eax
0x1800849bd  mov     esi, r12d
0x1800849c0  mov     [rsp+208h+var_1A0], r12
0x1800849c5  mov     [rsp+208h+var_68], r12
0x1800849cd  cmp     dword ptr [rsp+208h+var_128], r12d
0x1800849d5  jbe     loc_180084B01
0x1800849db  lea     rcx, [rsp+208h+var_198]
0x1800849e0  mov     [rsp+208h+var_198], r12
0x1800849e5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800849ea  mov     r8d, dword ptr [rsp+208h+var_128]; unsigned __int64
0x1800849f2  lea     r9, [rsp+208h+var_198]; struct IStream **
0x1800849f7  mov     rdx, [rsp+208h+var_138]; unsigned __int64
0x1800849ff  mov     rcx, [r13+0]; struct IStream *
0x180084a03  call    ?Create@SubStream@Packaging@Appx@@SAJPEAUIStream@@_K1PEAPEAU4@@Z; Appx::Packaging::SubStream::Create(IStream *,unsigned __int64,unsigned __int64,IStream * *)
0x180084a08  mov     esi, eax
  ... truncated ...
```
