# Appx::Packaging::Consumption::AppxEncryptedPackageReader::Initialize(IStream *,APPX_KEY_INFO const *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::Encryption::EncryptionKeyType)

- ea: `0x18006f3a8`
- end: `0x18006fbc3`
- name: `?Initialize@AppxEncryptedPackageReader@Consumption@Packaging@Appx@@AEAAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEAVAppxEncryptionSettings@34@W4EncryptionKeyType@Encryption@34@@Z`
- size: `2075`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d39c`
- `0x18006d488`
- `0x18008fe34`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180022b50`
- `0x180024894`
- `0x180024974`
- `0x180046da4`
- `0x180046e28`
- `0x18006c9dc`
- `0x18006cc64`
- `0x18006cf14`
- `0x18006f358`
- `0x18006f3a8`
- `0x18006ffd0`
- `0x180071f50`
- `0x180084398`
- `0x180084e24`
- `0x1800850b0`
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
- `0x18008c8ac`
- `0x1800992a0`
- `0x1800ccdfc`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x18006f429`
- `OpcServices!__imp_GetCloneableStream` at `0x18006f429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fb27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fb27`

## string_xrefs

- `0x18006f91d`: `AppxManifest.xml`
- `0x18006f443`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f4bc`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f50c`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f53a`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f584`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f61a`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f65a`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f6cf`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f782`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f822`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f88f`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f93d`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006f9a6`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006fa48`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`
- `0x18006fac2`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedpackagereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::AppxEncryptedPackageReader::Initialize(
        __int64 a1,
        __int64 a2,
        struct APPX_KEY_INFO *a3,
        struct Appx::Packaging::AppxEncryptionSettings *a4,
        int a5)
{
  struct APPX_KEY_INFO *v6; // rdi
  int CloneableStream; // eax
  unsigned int v10; // ebx
  struct IStream **v11; // r12
  int KeyInfo; // eax
  int Header; // eax
  struct IStream *v14; // rdx
  int v15; // eax
  struct Appx::Packaging::AppxEncryptionSettings *v16; // r14
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  Appx::Packaging::FileNameHelper *v20; // rbx
  struct IStream *v21; // rdi
  int BlockMapEncryptedFile; // esi
  __int64 v23; // rdx
  struct Appx::Packaging::FileNameHelper *v24; // rsi
  int TempFolderPathCached; // eax
  unsigned int v26; // r15d
  struct Appx::Packaging::FileNameHelper *v27; // rcx
  __int64 v28; // rdx
  struct Appx::Packaging::FileNameHelper *v29; // rcx
  int v30; // eax
  int v31; // r9d
  int matched; // eax
  int Manifest; // r14d
  __int64 v34; // rdx
  __int64 v35; // rdx
  int PackageFullName; // eax
  __int64 v37; // rcx
  __int64 v38; // r8
  char v39; // al
  unsigned __int16 **lpString1; // [rsp+20h] [rbp-1D8h]
  int lpString1a; // [rsp+20h] [rbp-1D8h]
  int lpString1b; // [rsp+20h] [rbp-1D8h]
  struct Appx::Packaging::AppxEncryptionSettings *v44; // [rsp+50h] [rbp-1A8h] BYREF
  struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *v45; // [rsp+58h] [rbp-1A0h] BYREF
  struct IStream *v46; // [rsp+60h] [rbp-198h] BYREF
  struct Appx::Packaging::FileNameHelper *v47; // [rsp+68h] [rbp-190h] BYREF
  __int64 v48; // [rsp+70h] [rbp-188h] BYREF
  struct Appx::Packaging::Consumption::AppxEncryptedFile *v49; // [rsp+78h] [rbp-180h] BYREF
  __int64 v50; // [rsp+80h] [rbp-178h] BYREF
  struct APPX_KEY_INFO *v51; // [rsp+88h] [rbp-170h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-168h] BYREF
  __int128 v53; // [rsp+98h] [rbp-160h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-150h]
  _DWORD v55[8]; // [rsp+B0h] [rbp-148h] BYREF
  unsigned __int64 v56; // [rsp+D0h] [rbp-128h]
  enum APPX_COMPRESSION_OPTION v57; // [rsp+D8h] [rbp-120h]
  unsigned __int64 v58; // [rsp+E0h] [rbp-118h]
  unsigned __int64 v59; // [rsp+E8h] [rbp-110h]
  enum APPX_COMPRESSION_OPTION v60; // [rsp+F0h] [rbp-108h]
  unsigned __int64 v61; // [rsp+F8h] [rbp-100h]
  unsigned __int16 *v62; // [rsp+1A0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v51 = a3;
  v6 = a3;
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
  {
    lpString1 = &v62;
    McGenEventWrite_EventWriteTransfer(a1, EVENT_PACKAGE_READER_CREATE_START, a3, 1);
  }
  v50 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  CloneableStream = GetCloneableStream(a2, &v50);
  v10 = CloneableStream;
  if ( CloneableStream >= 0 )
  {
    v11 = (struct IStream **)(a1 + 104);
    Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(a1 + 104, &v50);
    v54 = 0;
    v53 = 0;
    if ( !v6 && !a4 && a5 == 1 )
    {
      KeyInfo = Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(
                  (Appx::Packaging::GlobalDevKeyInfo *)&v53,
                  (const struct APPX_KEY_INFO **)&v51);
      v10 = KeyInfo;
      if ( KeyInfo < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x97,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
          (const char *)(unsigned int)KeyInfo,
          (int)lpString1);
LABEL_76:
        Appx::Packaging::GlobalDevKeyInfo::~GlobalDevKeyInfo((Appx::Packaging::GlobalDevKeyInfo *)&v53);
        goto LABEL_77;
      }
      v6 = v51;
    }
    Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v55);
    Header = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadHeader(
               *v11,
               v6,
               (struct Appx::Packaging::EncryptedAppxHeader *)v55);
    v10 = Header;
    if ( Header < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)Header,
        (int)lpString1);
LABEL_75:
      Appx::Packaging::EncryptedAppxHeader::~EncryptedAppxHeader((Appx::Packaging::EncryptedAppxHeader *)v55);
      goto LABEL_76;
    }
    if ( v55[0] != 1213225029 )
    {
      v10 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)0x8007000DLL,
        (int)lpString1);
      goto LABEL_75;
    }
    v14 = *v11;
    v46 = 0;
    v15 = Appx::Packaging::EncryptedAppxFootersReader::Create(
            (struct Appx::Packaging::EncryptedAppxHeader *)v55,
            v14,
            0,
            &v46);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)v15,
        (int)lpString1);
LABEL_17:
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v46);
      goto LABEL_75;
    }
    v44 = 0;
    v16 = 0;
    if ( a4 )
    {
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      v17 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(
              (const struct Appx::Packaging::EncryptedAppxHeader *)v55,
              a4,
              &v44);
      v10 = v17;
      if ( v17 < 0 )
      {
        v18 = 172;
LABEL_24:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
          (const char *)(unsigned int)v17,
          (int)lpString1);
LABEL_25:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
        goto LABEL_17;
      }
    }
    else
    {
      if ( !v6 )
        goto LABEL_27;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      v17 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(
              (const struct Appx::Packaging::EncryptedAppxHeader *)v55,
              v6->keyLength,
              v6->key,
              &v44);
      v10 = v17;
      if ( v17 < 0 )
      {
        v18 = 177;
        goto LABEL_24;
      }
    }
    v16 = v44;
LABEL_27:
    v47 = 0;
    v19 = Appx::Packaging::FileNameHelper::Create(&v47);
    v10 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)v19,
        (int)lpString1);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v47);
      goto LABEL_25;
    }
    v45 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
    v20 = v47;
    v21 = v46;
    BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(
                              (const struct Appx::Packaging::EncryptedAppxHeader *)v55,
                              v46,
                              v16,
                              v47,
                              *v11,
                              &v45);
    if ( BlockMapEncryptedFile < 0 )
    {
      v23 = 190;
LABEL_31:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)BlockMapEncryptedFile,
        lpString1a);
LABEL_32:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v20);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v21);
      v10 = BlockMapEncryptedFile;
      goto LABEL_75;
    }
    BlockMapEncryptedFile = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                              &v45,
                              a1 + 48);
    if ( BlockMapEncryptedFile < 0 )
    {
      v23 = 191;
      goto LABEL_31;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 24);
    BlockMapEncryptedFile = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(
                              (const struct Appx::Packaging::EncryptedAppxHeader *)v55,
                              v45,
                              (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)(a1 + 24));
    if ( BlockMapEncryptedFile < 0 )
    {
      v23 = 193;
      goto LABEL_31;
    }
    v47 = 0;
    v51 = 0;
    v24 = 0;
    TempFolderPathCached = Appx::Packaging::FileNameHelper::GetTempFolderPathCached(
                             v20,
                             (const unsigned __int16 **)&v51);
    v26 = TempFolderPathCached;
    if ( TempFolderPathCached < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)TempFolderPathCached,
        lpString1a);
      v27 = 0;
LABEL_39:
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v27);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v20);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v21);
      v10 = v26;
      goto LABEL_75;
    }
    v62 = 0;
    if ( (_DWORD)v58 )
    {
      v46 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
      BlockMapEncryptedFile = Appx::Packaging::SubStream::Create(*v11, v56, (unsigned int)v58, &v46);
      if ( BlockMapEncryptedFile < 0 )
      {
        v28 = 210;
LABEL_43:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
          (const char *)(unsigned int)BlockMapEncryptedFile,
          lpString1a);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        v29 = 0;
LABEL_44:
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v29);
        goto LABEL_32;
      }
      BlockMapEncryptedFile = Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadSignatureFile(
                                (Appx::Packaging::Consumption::AppxEncryptedPackageReader *)a1,
                                v46,
                                v57,
                                (const unsigned __int16 *)v51);
      if ( BlockMapEncryptedFile < 0 )
      {
        v28 = 211;
        goto LABEL_43;
      }
      v30 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(0, *(_QWORD *)(a1 + 56), &v47);
      BlockMapEncryptedFile = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
          (const char *)(unsigned int)v30,
          lpString1a);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
        v29 = v47;
        goto LABEL_44;
      }
      v24 = v47;
      v62 = (unsigned __int16 *)*((_QWORD *)v47 + 3);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v46);
    }
    v49 = 0;
    v48 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
    matched = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(
                (int)v21,
                *(_QWORD *)(a1 + 24),
                (int)v16,
                v31,
                L"AppxManifest.xml",
                *v11,
                (__int64)&v49,
                (__int64)&v48,
                a1 + 80);
    v26 = matched;
    if ( matched < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)matched,
        lpString1b);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      v27 = v24;
      goto LABEL_39;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(a1 + 32);
    Manifest = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadManifest(
                 v49,
                 v16,
                 v62,
                 (struct IAppxManifestReader **)(a1 + 32));
    if ( Manifest < 0 )
    {
      v34 = 234;
LABEL_54:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)Manifest,
        lpString1b);
LABEL_74:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v49);
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v24);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v45);
      Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v20);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v44);
      Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(v21);
      v10 = Manifest;
      goto LABEL_75;
    }
    Manifest = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(&v49, a1 + 40);
    if ( Manifest < 0 )
    {
      v34 = 235;
      goto LABEL_54;
    }
    if ( v48 )
    {
      Manifest = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(&v48, a1 + 72);
      if ( Manifest < 0 )
      {
        v34 = 239;
        goto LABEL_54;
      }
    }
    if ( (_DWORD)v61 )
    {
      v47 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
      Manifest = Appx::Packaging::SubStream::Create(*v11, v59, (unsigned int)v61, &v47);
      if ( Manifest < 0 )
      {
        v35 = 248;
LABEL_63:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
          (const char *)(unsigned int)Manifest,
          lpString1b);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
        goto LABEL_74;
      }
      Manifest = Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadCodeIntegrityFile(
                   (Appx::Packaging::Consumption::AppxEncryptedPackageReader *)a1,
                   v47,
                   v60,
                   (const unsigned __int16 *)v51);
      if ( Manifest < 0 )
      {
        v35 = 249;
        goto LABEL_63;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v47);
    }
    pv = 0;
    PackageFullName = Appx::Packaging::Consumption::AppxEncryptedPackageReader::GetPackageFullName(
                        (Appx::Packaging::Consumption::AppxEncryptedPackageReader *)a1,
                        (unsigned __int16 **)&pv);
    Manifest = PackageFullName;
    if ( PackageFullName >= 0 )
    {
      v39 = Microsoft_Windows_AppxPackagingOMEnableBits;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(v37, EVENT_PACKAGE_READER_CREATED, pv);
        v39 = Microsoft_Windows_AppxPackagingOMEnableBits;
      }
      if ( (v39 & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(v37, EVENT_PACKAGE_READER_CREATE_STOP, v38, 1);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
        (const char *)(unsigned int)PackageFullName,
        lpString1b);
    }
    CoTaskMemFree(pv);
    goto LABEL_74;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x8E,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedpackagereader.cpp",
    (const char *)(unsigned int)CloneableStream,
    (int)lpString1);
LABEL_77:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  return v10;
}

```

## disassembly

```asm
0x18006f3a8  mov     r11, rsp
0x18006f3ab  push    rbx
0x18006f3ac  push    rsi
0x18006f3ad  push    rdi
0x18006f3ae  push    r12
0x18006f3b0  push    r13
0x18006f3b2  push    r14
0x18006f3b4  push    r15
0x18006f3b6  sub     rsp, 1C0h
0x18006f3bd  mov     rax, cs:__security_cookie
0x18006f3c4  xor     rax, rsp
0x18006f3c7  mov     [rsp+1F8h+var_48], rax
0x18006f3cf  mov     [r11-170h], r8
0x18006f3d6  mov     rsi, r9
0x18006f3d9  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006f3e0  mov     rdi, r8
0x18006f3e3  mov     rbx, rdx
0x18006f3e6  mov     r13, rcx
0x18006f3e9  jz      short loc_18006F406
0x18006f3eb  lea     rax, [r11-58h]
0x18006f3ef  mov     r9d, 1
0x18006f3f5  lea     rdx, EVENT_PACKAGE_READER_CREATE_START
0x18006f3fc  mov     [rsp+1F8h+lpString1], rax; int
0x18006f401  call    McGenEventWrite_EventWriteTransfer
0x18006f406  xor     r15d, r15d
0x18006f409  lea     rcx, [rsp+1F8h+var_178]
0x18006f411  mov     [rsp+1F8h+var_178], r15
0x18006f419  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f41e  lea     rdx, [rsp+1F8h+var_178]
0x18006f426  mov     rcx, rbx
0x18006f429  call    cs:__imp_GetCloneableStream
0x18006f430  nop     dword ptr [rax+rax+00h]
0x18006f435  mov     ebx, eax
0x18006f437  test    eax, eax
0x18006f439  jns     short loc_18006F45C
0x18006f43b  mov     rcx, [rsp+1F8h]; this
0x18006f443  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f44a  mov     r9d, eax; char *
0x18006f44d  mov     edx, 8Eh; void *
0x18006f452  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f457  jmp     loc_18006FB90
0x18006f45c  lea     r12, [r13+68h]
0x18006f460  mov     rcx, r12
0x18006f463  lea     rdx, [rsp+1F8h+var_178]
0x18006f46b  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x18006f470  xor     eax, eax
0x18006f472  xorps   xmm0, xmm0
0x18006f475  mov     [rsp+1F8h+var_150], rax
0x18006f47d  movups  [rsp+1F8h+var_160], xmm0
0x18006f485  test    rdi, rdi
0x18006f488  jnz     short loc_18006F4DD
0x18006f48a  test    rsi, rsi
0x18006f48d  jnz     short loc_18006F4DD
0x18006f48f  cmp     [rsp+1F8h+arg_20], 1
0x18006f497  jnz     short loc_18006F4DD
0x18006f499  lea     rdx, [rsp+1F8h+var_170]; struct APPX_KEY_INFO **
0x18006f4a1  lea     rcx, [rsp+1F8h+var_160]; this
0x18006f4a9  call    ?GetKeyInfo@GlobalDevKeyInfo@Packaging@Appx@@QEAAJPEAPEBUAPPX_KEY_INFO@@@Z; Appx::Packaging::GlobalDevKeyInfo::GetKeyInfo(APPX_KEY_INFO const * *)
0x18006f4ae  mov     ebx, eax
0x18006f4b0  test    eax, eax
0x18006f4b2  jns     short loc_18006F4D5
0x18006f4b4  mov     rcx, [rsp+1F8h]; this
0x18006f4bc  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f4c3  mov     r9d, eax; char *
0x18006f4c6  mov     edx, 97h; void *
0x18006f4cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f4d0  jmp     loc_18006FB83
0x18006f4d5  mov     rdi, [rsp+1F8h+var_170]
0x18006f4dd  lea     rcx, [rsp+1F8h+var_148]; this
0x18006f4e5  call    ??0EncryptedAppxHeader@Packaging@Appx@@QEAA@XZ; Appx::Packaging::EncryptedAppxHeader::EncryptedAppxHeader(void)
0x18006f4ea  mov     rcx, [r12]; struct IStream *
0x18006f4ee  lea     r8, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f4f6  mov     rdx, rdi; struct APPX_KEY_INFO *
0x18006f4f9  call    ?LoadHeader@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@AEAVEncryptedAppxHeader@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadHeader(IStream *,APPX_KEY_INFO const *,Appx::Packaging::EncryptedAppxHeader &)
0x18006f4fe  mov     ebx, eax
0x18006f500  test    eax, eax
0x18006f502  jns     short loc_18006F525
0x18006f504  mov     rcx, [rsp+1F8h]; this
0x18006f50c  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f513  mov     r9d, eax; char *
0x18006f516  mov     edx, 0A0h; void *
0x18006f51b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f520  jmp     loc_18006FB76
0x18006f525  cmp     [rsp+1F8h+var_148], 48505845h
0x18006f530  jz      short loc_18006F558
0x18006f532  mov     rcx, [rsp+1F8h]; this
0x18006f53a  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f541  mov     ebx, 8007000Dh
0x18006f546  mov     edx, 0A3h; void *
0x18006f54b  mov     r9d, ebx; char *
0x18006f54e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f553  jmp     loc_18006FB76
0x18006f558  mov     rdx, [r12]; struct IStream *
0x18006f55c  lea     r9, [rsp+1F8h+var_198]; struct Appx::Packaging::EncryptedAppxFootersReader **
0x18006f561  xor     r8d, r8d; unsigned __int64
0x18006f564  mov     [rsp+1F8h+var_198], r15
0x18006f569  lea     rcx, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f571  call    ?Create@EncryptedAppxFootersReader@Packaging@Appx@@SAJPEAVEncryptedAppxHeader@23@PEAUIStream@@_KPEAPEAV123@@Z; Appx::Packaging::EncryptedAppxFootersReader::Create(Appx::Packaging::EncryptedAppxHeader *,IStream *,unsigned __int64,Appx::Packaging::EncryptedAppxFootersReader * *)
0x18006f576  mov     ebx, eax
0x18006f578  test    eax, eax
0x18006f57a  jns     short loc_18006F5A7
0x18006f57c  mov     rcx, [rsp+1F8h]; this
0x18006f584  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f58b  mov     r9d, eax; char *
0x18006f58e  mov     edx, 0A6h; void *
0x18006f593  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f598  mov     rcx, [rsp+1F8h+var_198]; void *
0x18006f59d  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x18006f5a2  jmp     loc_18006FB76
0x18006f5a7  mov     [rsp+1F8h+var_1A8], r15
0x18006f5ac  mov     r14, r15
0x18006f5af  test    rsi, rsi
0x18006f5b2  jz      short loc_18006F5E0
0x18006f5b4  lea     rcx, [rsp+1F8h+var_1A8]
0x18006f5b9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f5be  lea     r8, [rsp+1F8h+var_1A8]; struct Appx::Packaging::AppxEncryptionSettings **
0x18006f5c3  mov     rdx, rsi; struct Appx::Packaging::AppxEncryptionSettings *
0x18006f5c6  lea     rcx, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f5ce  call    ?CreateEncryptionSettings@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@PEAVAppxEncryptionSettings@34@PEAPEAV634@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::AppxEncryptionSettings * *)
0x18006f5d3  mov     ebx, eax
0x18006f5d5  test    eax, eax
0x18006f5d7  jns     short loc_18006F638
0x18006f5d9  mov     edx, 0ACh
0x18006f5de  jmp     short loc_18006F612
0x18006f5e0  test    rdi, rdi
0x18006f5e3  jz      short loc_18006F63D
0x18006f5e5  lea     rcx, [rsp+1F8h+var_1A8]
0x18006f5ea  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f5ef  mov     r8, [rdi+8]; unsigned __int8 *
0x18006f5f3  lea     r9, [rsp+1F8h+var_1A8]; struct Appx::Packaging::AppxEncryptionSettings **
0x18006f5f8  mov     edx, [rdi]; unsigned int
0x18006f5fa  lea     rcx, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f602  call    ?CreateEncryptionSettings@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@IPEBEPEAPEAVAppxEncryptionSettings@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(Appx::Packaging::EncryptedAppxHeader const &,uint,uchar const *,Appx::Packaging::AppxEncryptionSettings * *)
0x18006f607  mov     ebx, eax
0x18006f609  test    eax, eax
0x18006f60b  jns     short loc_18006F638
0x18006f60d  mov     edx, 0B1h; void *
0x18006f612  mov     rcx, [rsp+1F8h]; this
0x18006f61a  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f621  mov     r9d, eax; char *
0x18006f624  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f629  lea     rcx, [rsp+1F8h+var_1A8]
0x18006f62e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f633  jmp     loc_18006F598
0x18006f638  mov     r14, [rsp+1F8h+var_1A8]
0x18006f63d  lea     rcx, [rsp+1F8h+var_190]; struct Appx::Packaging::FileNameHelper **
0x18006f642  mov     [rsp+1F8h+var_190], r15
0x18006f647  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x18006f64c  mov     ebx, eax
0x18006f64e  test    eax, eax
0x18006f650  jns     short loc_18006F67A
0x18006f652  mov     rcx, [rsp+1F8h]; this
0x18006f65a  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f661  mov     r9d, eax; char *
0x18006f664  mov     edx, 0B5h; void *
0x18006f669  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f66e  mov     rcx, [rsp+1F8h+var_190]
0x18006f673  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x18006f678  jmp     short loc_18006F629
0x18006f67a  lea     rcx, [rsp+1F8h+var_1A0]
0x18006f67f  mov     [rsp+1F8h+var_1A0], r15
0x18006f684  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f689  mov     rbx, [rsp+1F8h+var_190]
0x18006f68e  lea     rax, [rsp+1F8h+var_1A0]
0x18006f693  mov     rdi, [rsp+1F8h+var_198]
0x18006f698  lea     rcx, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f6a0  mov     [rsp+1F8h+var_1D0], rax; struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile **
0x18006f6a5  mov     r9, rbx; struct Appx::Packaging::FileNameHelper *
0x18006f6a8  mov     rax, [r12]
0x18006f6ac  mov     r8, r14; struct Appx::Packaging::AppxEncryptionSettings *
0x18006f6af  mov     rdx, rdi; struct Appx::Packaging::EncryptedAppxFootersReader *
0x18006f6b2  mov     [rsp+1F8h+lpString1], rax; int
0x18006f6b7  call    ?GetBlockMapEncryptedFile@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@PEAVEncryptedAppxFootersReader@34@PEAVAppxEncryptionSettings@34@PEAVFileNameHelper@34@PEAUIStream@@PEAPEAVAppxEncryptedBlockMapFile@234@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::EncryptedAppxFootersReader *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::FileNameHelper *,IStream *,Appx::Packaging::Consumption::AppxEncryptedBlockMapFile * *)
0x18006f6bc  mov     esi, eax
0x18006f6be  test    eax, eax
0x18006f6c0  jns     short loc_18006F709
0x18006f6c2  mov     edx, 0BEh; void *
0x18006f6c7  mov     rcx, [rsp+1F8h]; this
0x18006f6cf  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f6d6  mov     r9d, esi; char *
0x18006f6d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f6de  lea     rcx, [rsp+1F8h+var_1A0]
0x18006f6e3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f6e8  mov     rcx, rbx
0x18006f6eb  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x18006f6f0  lea     rcx, [rsp+1F8h+var_1A8]
0x18006f6f5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f6fa  mov     rcx, rdi; void *
0x18006f6fd  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x18006f702  mov     ebx, esi
0x18006f704  jmp     loc_18006FB76
0x18006f709  lea     rdx, [r13+30h]
0x18006f70d  lea     rcx, [rsp+1F8h+var_1A0]
0x18006f712  call    ??$As@UIAppxFile@@@?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxFile@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxFile>>)
0x18006f717  mov     esi, eax
0x18006f719  test    eax, eax
0x18006f71b  jns     short loc_18006F724
0x18006f71d  mov     edx, 0BFh
0x18006f722  jmp     short loc_18006F6C7
0x18006f724  lea     rcx, [r13+18h]
0x18006f728  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f72d  mov     rdx, [rsp+1F8h+var_1A0]; struct Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *
0x18006f732  lea     r8, [r13+18h]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x18006f736  lea     rcx, [rsp+1F8h+var_148]; struct Appx::Packaging::EncryptedAppxHeader *
0x18006f73e  call    ?LoadBlockMap@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJAEBVEncryptedAppxHeader@34@PEAVAppxEncryptedBlockMapFile@234@PEAPEAVAppxBlockMapReader@BlockMap@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::Consumption::AppxEncryptedBlockMapFile *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x18006f743  mov     esi, eax
0x18006f745  test    eax, eax
0x18006f747  jns     short loc_18006F753
0x18006f749  mov     edx, 0C1h
0x18006f74e  jmp     loc_18006F6C7
0x18006f753  lea     rdx, [rsp+1F8h+var_170]; unsigned __int16 **
0x18006f75b  mov     [rsp+1F8h+var_190], r15
0x18006f760  mov     rcx, rbx; this
0x18006f763  mov     [rsp+1F8h+var_170], r15
0x18006f76b  mov     rsi, r15
0x18006f76e  call    ?GetTempFolderPathCached@FileNameHelper@Packaging@Appx@@QEAAJPEAPEBG@Z; Appx::Packaging::FileNameHelper::GetTempFolderPathCached(ushort const * *)
0x18006f773  mov     r15d, eax
0x18006f776  test    eax, eax
0x18006f778  jns     short loc_18006F7C9
0x18006f77a  mov     rcx, [rsp+1F8h]; this
0x18006f782  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f789  mov     r9d, eax; char *
0x18006f78c  mov     edx, 0C7h; void *
0x18006f791  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f796  xor     ecx, ecx; void *
0x18006f798  call    ??$AutoPtrDeallocate@VEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(Appx::Packaging::Consumption::EncryptedAppxSignatureValidator *)
0x18006f79d  lea     rcx, [rsp+1F8h+var_1A0]
0x18006f7a2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f7a7  mov     rcx, rbx
0x18006f7aa  call    ??$AutoPtrDeallocate@VFileNameHelper@Packaging@Appx@@@Common@@YAXPEAVFileNameHelper@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(Appx::Packaging::FileNameHelper *)
0x18006f7af  lea     rcx, [rsp+1F8h+var_1A8]
0x18006f7b4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f7b9  mov     rcx, rdi; void *
0x18006f7bc  call    ??$AutoPtrDeallocate@VEncryptedAppxFootersReader@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxFootersReader@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::EncryptedAppxFootersReader>(Appx::Packaging::EncryptedAppxFootersReader *)
0x18006f7c1  mov     ebx, r15d
0x18006f7c4  jmp     loc_18006FB76
0x18006f7c9  xor     r15d, r15d
0x18006f7cc  mov     [rsp+1F8h+var_58], r15
0x18006f7d4  cmp     dword ptr [rsp+1F8h+var_118], r15d
0x18006f7dc  jbe     loc_18006F8CF
0x18006f7e2  lea     rcx, [rsp+1F8h+var_198]
0x18006f7e7  mov     [rsp+1F8h+var_198], r15
0x18006f7ec  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f7f1  mov     r8d, dword ptr [rsp+1F8h+var_118]; unsigned __int64
0x18006f7f9  lea     r9, [rsp+1F8h+var_198]; struct IStream **
0x18006f7fe  mov     rdx, [rsp+1F8h+var_128]; unsigned __int64
0x18006f806  mov     rcx, [r12]; struct IStream *
0x18006f80a  call    ?Create@SubStream@Packaging@Appx@@SAJPEAUIStream@@_K1PEAPEAU4@@Z; Appx::Packaging::SubStream::Create(IStream *,unsigned __int64,unsigned __int64,IStream * *)
0x18006f80f  mov     esi, eax
0x18006f811  test    eax, eax
0x18006f813  jns     short loc_18006F847
0x18006f815  mov     edx, 0D2h; void *
0x18006f81a  mov     rcx, [rsp+1F8h]; this
0x18006f822  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f829  mov     r9d, esi; char *
0x18006f82c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f831  lea     rcx, [rsp+1F8h+var_198]
0x18006f836  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f83b  xor     ecx, ecx; void *
0x18006f83d  call    ??$AutoPtrDeallocate@VEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Common@@YAXPEAVEncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(Appx::Packaging::Consumption::EncryptedAppxSignatureValidator *)
0x18006f842  jmp     loc_18006F6DE
0x18006f847  mov     r9, [rsp+1F8h+var_170]; unsigned __int16 *
0x18006f84f  mov     rcx, r13; this
0x18006f852  mov     r8d, [rsp+1F8h+var_120]; enum APPX_COMPRESSION_OPTION
0x18006f85a  mov     rdx, [rsp+1F8h+var_198]; struct IStream *
0x18006f85f  call    ?LoadSignatureFile@AppxEncryptedPackageReader@Consumption@Packaging@Appx@@IEAAJPEAUIStream@@W4APPX_COMPRESSION_OPTION@@PEBG@Z; Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadSignatureFile(IStream *,APPX_COMPRESSION_OPTION,ushort const *)
0x18006f864  mov     esi, eax
0x18006f866  test    eax, eax
0x18006f868  jns     short loc_18006F871
0x18006f86a  mov     edx, 0D3h
0x18006f86f  jmp     short loc_18006F81A
0x18006f871  mov     rdx, [r13+38h]
0x18006f875  lea     r8, [rsp+1F8h+var_190]
0x18006f87a  xor     ecx, ecx
0x18006f87c  call    ?Create@EncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@SAJW4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxFile@@PEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(APPX_PACKAGE_READER_OPTIONS,IAppxFile *,Appx::Packaging::Consumption::EncryptedAppxSignatureValidator * *)
0x18006f881  mov     esi, eax
0x18006f883  test    eax, eax
0x18006f885  jns     short loc_18006F8B4
0x18006f887  mov     rcx, [rsp+1F8h]; this
0x18006f88f  lea     r8, aOnecorePrintsc_168; "onecore\\printscan\\appxpackaging\\cons"...
0x18006f896  mov     r9d, eax; char *
0x18006f899  mov     edx, 0D8h; void *
0x18006f89e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f8a3  lea     rcx, [rsp+1F8h+var_198]
0x18006f8a8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f8ad  mov     rcx, [rsp+1F8h+var_190]
0x18006f8b2  jmp     short loc_18006F83D
0x18006f8b4  mov     rsi, [rsp+1F8h+var_190]
0x18006f8b9  lea     rcx, [rsp+1F8h+var_198]
0x18006f8be  mov     rax, [rsi+18h]
0x18006f8c2  mov     [rsp+1F8h+var_58], rax
0x18006f8ca  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f8cf  lea     rcx, [rsp+1F8h+var_188]
0x18006f8d4  mov     [rsp+1F8h+var_180], r15
0x18006f8d9  mov     [rsp+1F8h+var_188], r15
0x18006f8de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f8e3  lea     rcx, [rsp+1F8h+var_180]
0x18006f8e8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006f8ed  mov     rdx, [r13+18h]; int
0x18006f8f1  lea     rax, [r13+50h]
  ... truncated ...
```
