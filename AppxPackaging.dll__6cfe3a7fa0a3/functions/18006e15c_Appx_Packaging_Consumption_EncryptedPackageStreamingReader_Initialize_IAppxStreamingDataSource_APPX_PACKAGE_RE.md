# Appx::Packaging::Consumption::EncryptedPackageStreamingReader::Initialize(IAppxStreamingDataSource *,APPX_PACKAGE_READER_OPTIONS,Appx::Packaging::Consumption::EncryptedAppxHeaderReceiver *,unsigned __int64,unsigned __int64,bool,Appx::Packaging::AppxEncryptionSettings *,IAppxFootprintFileDownloadProgressHandler *)

- ea: `0x18006e15c`
- end: `0x18006f1f1`
- name: `?Initialize@EncryptedPackageStreamingReader@Consumption@Packaging@Appx@@AEAAJPEAUIAppxStreamingDataSource@@W4APPX_PACKAGE_READER_OPTIONS@@PEAVEncryptedAppxHeaderReceiver@234@_K3_NPEAVAppxEncryptionSettings@34@PEAUIAppxFootprintFileDownloadProgressHandler@@@Z`
- size: `4245`
- prototype: ``
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c770`
- `0x18006d100`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180017b48`
- `0x180024894`
- `0x180024974`
- `0x180046da4`
- `0x180046e28`
- `0x18006c9dc`
- `0x18006ca18`
- `0x18006ca90`
- `0x18006cbc4`
- `0x18006cc64`
- `0x18006cd10`
- `0x18006ce48`
- `0x18006cf14`
- `0x18006e15c`
- `0x18006f1f8`
- `0x18006f310`
- `0x18006f358`
- `0x180071f50`
- `0x180084398`
- `0x180084e24`
- `0x1800850b0`
- `0x180086460`
- `0x180086918`
- `0x180086a74`
- `0x1800872ac`
- `0x18008c8ac`
- `0x180096a00`
- `0x1800992a0`
- `0x1800c9aac`
- `0x1800ccdfc`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f144`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006f144`

## string_xrefs

- `0x18006eb07`: `AppxManifest.xml`
- `0x18006e26b`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e292`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e2c9`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e322`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e379`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e414`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e4bc`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e572`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e622`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e719`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e76c`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e7b8`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e82e`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e89a`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e8ed`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006e997`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006ea88`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006eb2f`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006eb6a`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006ec14`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006ecd4`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006ed30`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006edcf`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006eeaa`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`
- `0x18006f0df`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagestreamingreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::EncryptedPackageStreamingReader::Initialize(
        Appx::Packaging::Consumption::AppxEncryptedPackageReader *a1,
        __int64 a2,
        __int64 a3,
        Appx::Packaging::Consumption::AppxEncryptedFile *a4,
        unsigned __int64 a5,
        __int64 a6,
        char a7,
        struct IStream *a8,
        unsigned __int16 *a9)
{
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int TempFolderPathCached; // eax
  unsigned __int64 v15; // r9
  unsigned int v16; // edx
  __int64 v17; // r13
  unsigned __int64 v18; // r12
  unsigned __int64 v19; // rsi
  int FootersStream; // edi
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, Appx::Packaging **); // rbx
  int v23; // eax
  unsigned __int16 *v24; // rdi
  int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // esi
  int v28; // ebx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rdx
  Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *v33; // r15
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r8
  __int64 v37; // rcx
  int v38; // eax
  int SignatureFile; // eax
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // rdx
  Appx::Packaging::Consumption::AppxEncryptedPackageReader *v43; // r12
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // rcx
  struct IStream *v47; // rbx
  int v48; // eax
  __int64 v49; // rdx
  struct IStream *v50; // rsi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rsi
  __int64 v54; // rcx
  __int64 v55; // r8
  Appx::Packaging::Consumption::AppxEncryptedFile *v56; // rdi
  unsigned __int64 v57; // r15
  __int64 v58; // rcx
  __int64 v59; // r8
  int v60; // r15d
  __int64 v61; // rdx
  int BlockMap; // eax
  int v63; // r9d
  int matched; // eax
  __int64 v65; // rcx
  __int64 v66; // r8
  Appx::Packaging::Consumption::AppxEncryptedFile *v67; // rdi
  unsigned __int64 v68; // r15
  __int64 v69; // rcx
  __int64 v70; // r8
  __int64 v71; // rdx
  Appx::Packaging::Consumption::AppxEncryptedPackageReader *v72; // r15
  const unsigned __int16 *v73; // r12
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  Appx::Packaging::Consumption::AppxEncryptedFile *v77; // rdi
  unsigned __int64 v78; // rsi
  unsigned __int16 *v79; // r15
  int v80; // eax
  __int64 v81; // rcx
  __int64 v82; // r8
  unsigned int v83; // esi
  __int64 v84; // rdx
  struct IAppxFile **v85; // rsi
  __int64 v86; // r8
  __int64 v87; // rcx
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // r8
  __int64 v91; // rcx
  int PackageFullName; // eax
  __int64 v93; // rcx
  __int64 v94; // r8
  char v95; // al
  int lpString1; // [rsp+20h] [rbp-128h]
  struct IStream **lpString1a; // [rsp+20h] [rbp-128h]
  int lpString1b; // [rsp+20h] [rbp-128h]
  int lpString1c; // [rsp+20h] [rbp-128h]
  Appx::Packaging::Consumption::AppxEncryptedFile **lpString1d; // [rsp+20h] [rbp-128h]
  int lpString1e; // [rsp+20h] [rbp-128h]
  int *lpString1f; // [rsp+20h] [rbp-128h]
  struct IStream **v104; // [rsp+30h] [rbp-118h]
  struct IStream **v105; // [rsp+30h] [rbp-118h]
  struct IStream **v106; // [rsp+30h] [rbp-118h]
  Appx::Packaging *v107; // [rsp+50h] [rbp-F8h] BYREF
  Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *v108; // [rsp+58h] [rbp-F0h] BYREF
  struct IStream *v109; // [rsp+60h] [rbp-E8h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedFile *v110; // [rsp+68h] [rbp-E0h] BYREF
  struct Appx::Packaging::AppxEncryptionSettings *v111; // [rsp+70h] [rbp-D8h] BYREF
  struct IStream *v112; // [rsp+78h] [rbp-D0h] BYREF
  struct IStream *v113; // [rsp+80h] [rbp-C8h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedFile *v114; // [rsp+88h] [rbp-C0h] BYREF
  unsigned __int16 *v115; // [rsp+90h] [rbp-B8h] BYREF
  int v116; // [rsp+98h] [rbp-B0h]
  unsigned __int16 *v117; // [rsp+A0h] [rbp-A8h]
  Appx::Packaging::Consumption::AppxEncryptedPackageReader *v118; // [rsp+A8h] [rbp-A0h]
  struct Appx::Packaging::FileNameHelper *v119; // [rsp+B0h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-90h] BYREF
  struct IStream *v121[2]; // [rsp+C0h] [rbp-88h] BYREF
  Appx::Packaging::Consumption::AppxEncryptedFile *v122[2]; // [rsp+D0h] [rbp-78h] BYREF
  struct IStream *v123[2]; // [rsp+E0h] [rbp-68h] BYREF
  int v124[4]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v118 = a1;
  v112 = a8;
  v117 = a9;
  v122[0] = a4;
  v116 = a3;
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    McTemplateU0q_EventWriteTransfer(a9, EVENT_STREAMING_READER_CREATE_START, a3);
  Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=((char *)a1 + 128, a2);
  v119 = 0;
  v12 = Appx::Packaging::FileNameHelper::Create(&v119);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = 133;
LABEL_9:
    v15 = v12;
    goto LABEL_10;
  }
  v115 = 0;
  TempFolderPathCached = Appx::Packaging::FileNameHelper::GetTempFolderPathCached(
                           v119,
                           (const unsigned __int16 **)&v115);
  v12 = TempFolderPathCached;
  if ( TempFolderPathCached >= 0 )
  {
    if ( a5 > ~a6 )
    {
      v12 = -2147024362;
      v13 = 138;
      goto LABEL_9;
    }
    v17 = *((_QWORD *)a4 + 3);
    v18 = a5 + a6;
    if ( a5 + a6 <= *(_QWORD *)(v17 + 8) )
    {
      v12 = -2147024883;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)0x8007000DLL,
        lpString1);
      goto LABEL_167;
    }
    v19 = v18 - *(_QWORD *)(v17 + 8);
    if ( v19 > 0xFFFFFFFF )
    {
      FootersStream = -2147024673;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)0x800700DFLL,
        lpString1);
LABEL_166:
      v12 = FootersStream;
      goto LABEL_167;
    }
    v21 = *((_QWORD *)a1 + 16);
    v107 = 0;
    v22 = *(__int64 (__fastcall **)(__int64, Appx::Packaging **))(*(_QWORD *)v21 + 32LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v107);
    v23 = v22(v21, &v107);
    v12 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)v23,
        lpString1);
LABEL_17:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v107);
      goto LABEL_167;
    }
    v24 = v117;
    if ( v117 )
    {
      v25 = (*(__int64 (__fastcall **)(unsigned __int16 *, Appx::Packaging *))(*(_QWORD *)v117 + 32LL))(v117, v107);
      v12 = v25;
      if ( v25 < 0 )
      {
        v26 = 156;
LABEL_21:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v26,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)v25,
          lpString1);
        goto LABEL_17;
      }
    }
    v25 = (*(__int64 (__fastcall **)(Appx::Packaging *, _QWORD, _QWORD))(*(_QWORD *)v107 + 24LL))(
            v107,
            *(_QWORD *)(v17 + 8),
            (unsigned int)v19);
    v12 = v25;
    if ( v25 < 0 )
    {
      v26 = 159;
      goto LABEL_21;
    }
    v27 = v116;
    v108 = 0;
    v28 = v116 & 1;
    v116 = v28;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v108);
    v29 = Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::Create(
            (struct Appx::Packaging::EncryptedAppxHeader *)v17,
            a5,
            v18,
            v115,
            v28 != 0,
            &v108);
    v12 = v29;
    if ( v29 < 0 )
    {
      v32 = 169;
LABEL_26:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)v29,
        (int)lpString1a);
LABEL_27:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v108);
      goto LABEL_17;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      lpString1a = v123;
      McGenEventWrite_EventWriteTransfer(v30, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v31, 1);
    }
    v33 = v108;
    v29 = (*(__int64 (__fastcall **)(Appx::Packaging *, __int64, Appx::Packaging::Consumption::EncryptedAppxFootersReceiver *))(*(_QWORD *)v107 + 32LL))(
            v107,
            3,
            v108);
    v12 = v29;
    if ( v29 < 0 )
    {
      v32 = 172;
      goto LABEL_26;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      lpString1a = v123;
      McGenEventWrite_EventWriteTransfer(v34, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v35, 1);
    }
    if ( *((_DWORD *)v33 + 14) != 3 )
    {
      v12 = -2146958848;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)0x80080200LL,
        (int)lpString1a);
      goto LABEL_27;
    }
    if ( *(_DWORD *)(v17 + 48) )
    {
      v123[0] = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v123);
      v123[0] = 0;
      if ( *((_DWORD *)v33 + 14) != 3 )
      {
        FootersStream = -2147019873;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedappxfootersreceiver.cpp",
          (const char *)0x8007139FLL,
          (int)lpString1a);
LABEL_42:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)FootersStream,
          lpString1b);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v123);
LABEL_165:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v107);
        goto LABEL_166;
      }
      v37 = *((_QWORD *)v33 + 10);
      if ( v37 )
      {
        v38 = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v37 + 104LL))(v37, v123);
        FootersStream = v38;
        if ( v38 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedappxfootersreceiver.cpp",
            (const char *)(unsigned int)v38,
            (int)lpString1a);
          goto LABEL_42;
        }
        v24 = v117;
      }
      if ( !v123[0] )
      {
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v37, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v36, 1);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v123);
        SignatureFile = Appx::Packaging::DownloadToTempFileStream(
                          v107,
                          *(struct IAppxRangeRequestJob **)(v17 + 32),
                          *(unsigned int *)(v17 + 48),
                          (unsigned int)v115,
                          v24,
                          (struct IAppxFootprintFileDownloadProgressHandler *)v123,
                          v104);
        v12 = SignatureFile;
        if ( SignatureFile < 0 )
        {
          v42 = 197;
LABEL_49:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v42,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
            (const char *)(unsigned int)SignatureFile,
            (int)lpString1a);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v123);
          goto LABEL_27;
        }
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
        {
          lpString1a = v121;
          McGenEventWrite_EventWriteTransfer(v40, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v41, 1);
        }
      }
      v43 = v118;
      SignatureFile = Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadSignatureFile(
                        v118,
                        v123[0],
                        *(enum APPX_COMPRESSION_OPTION *)(v17 + 40),
                        v115);
      v12 = SignatureFile;
      if ( SignatureFile < 0 )
      {
        v42 = 200;
        goto LABEL_49;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v123);
    }
    else
    {
      v43 = v118;
    }
    v44 = *((_QWORD *)v43 + 7);
    v121[0] = 0;
    v45 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(v27, v44, v121);
    v12 = v45;
    if ( v45 < 0 )
    {
      if ( v45 == -2146762496 )
      {
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 1) != 0 )
          McTemplateU0q_EventWriteTransfer(v46, &EVENT_PACKAGE_UNSIGNED, 2148204800LL);
        AppxPackagingLog(&EVENT_PACKAGE_UNSIGNED, 0xB000009C, -2146762496);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)v12,
        (int)lpString1a);
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v121[0]);
      goto LABEL_27;
    }
    v47 = v121[0];
    v48 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateHeaderIfNeeded(
            v121[0],
            (struct Appx::Packaging::EncryptedAppxHeader *)v17,
            *((const unsigned __int8 **)v122[0] + 4));
    FootersStream = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)v48,
        (int)lpString1a);
LABEL_164:
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v47);
      goto LABEL_165;
    }
    v109 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
    FootersStream = Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::GetFootersStream(v33, &v109);
    if ( FootersStream < 0 )
    {
      v49 = 217;
LABEL_66:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)FootersStream,
        (int)lpString1a);
LABEL_163:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
      goto LABEL_164;
    }
    FootersStream = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateFootersIfNeeded(v47, v109);
    if ( FootersStream < 0 )
    {
      v49 = 218;
      goto LABEL_66;
    }
    v50 = (struct IStream *)*((_QWORD *)v33 + 3);
    v121[0] = v50;
    v111 = 0;
    if ( a7 )
    {
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v111);
      v51 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreateEncryptionSettings(
              (const struct Appx::Packaging::EncryptedAppxHeader *)v17,
              v112,
              &v111);
      FootersStream = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)v51,
          (int)lpString1a);
LABEL_162:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v111);
        goto LABEL_163;
      }
      v112 = v111;
    }
    v110 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
    FootersStream = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::GetBlockMapEncryptedFile(
                      (const struct Appx::Packaging::EncryptedAppxHeader *)v17,
                      v50,
                      v112,
                      v119,
                      0,
                      &v110);
    if ( FootersStream < 0 )
    {
      v52 = 234;
LABEL_75:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v52,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)FootersStream,
        lpString1c);
LABEL_161:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
      goto LABEL_162;
    }
    v53 = (__int64)v43 + 40;
    FootersStream = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v110,
                      (__int64)v43 + 48);
    if ( FootersStream < 0 )
    {
      v52 = 235;
      goto LABEL_75;
    }
    v56 = v110;
    v57 = *(_QWORD *)(*((_QWORD *)v110 + 9) + 40LL);
    if ( v57 > 0xFFFFFFFF )
    {
      FootersStream = -2147024673;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)0x800700DFLL,
        lpString1c);
      goto LABEL_161;
    }
    v113 = 0;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(v54, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v55, 1);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v113);
    v60 = Appx::Packaging::DownloadToTempFileStream(
            v107,
            *(struct IAppxRangeRequestJob **)(*((_QWORD *)v56 + 9) + 16LL),
            (unsigned int)v57,
            (unsigned int)v115,
            v117,
            (struct IAppxFootprintFileDownloadProgressHandler *)&v113,
            v104);
    if ( v60 < 0 )
    {
      v61 = 250;
LABEL_84:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)v60,
        (int)lpString1d);
LABEL_85:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v113);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v111);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
      Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v47);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v108);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v107);
      v12 = v60;
      goto LABEL_167;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      lpString1d = v122;
      McGenEventWrite_EventWriteTransfer(v58, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v59, 1);
    }
    v60 = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateEncryptedBlockMapIfNeeded(v47, v113);
    if ( v60 < 0 )
    {
      v61 = 253;
      goto LABEL_84;
    }
    v60 = Appx::Packaging::Consumption::AppxEncryptedFile::SetFileStream(v56, v113);
    if ( v60 < 0 )
    {
      v61 = 254;
      goto LABEL_84;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v43 + 24);
    BlockMap = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadBlockMap(
                 (const struct Appx::Packaging::EncryptedAppxHeader *)v17,
                 v56,
                 (struct Appx::Packaging::BlockMap::AppxBlockMapReader **)v43 + 3);
    FootersStream = BlockMap;
    if ( BlockMap < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)BlockMap,
        (int)lpString1d);
LABEL_160:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v113);
      goto LABEL_161;
    }
    v122[0] = 0;
    v114 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v114);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
    matched = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(
                (int)v121[0],
                *((_QWORD *)v43 + 3),
                (int)v112,
                v63,
                L"AppxManifest.xml",
                0,
                (__int64)v122,
                (__int64)&v114,
                (__int64)v43 + 80);
    FootersStream = matched;
    if ( matched < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)matched,
        lpString1e);
LABEL_159:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v114);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
      goto LABEL_160;
    }
    v67 = v122[0];
    v68 = *(_QWORD *)(*((_QWORD *)v122[0] + 9) + 40LL);
    if ( v68 > 0xFFFFFFFF )
    {
      FootersStream = -2147024673;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)0x800700DFLL,
        lpString1e);
      goto LABEL_159;
    }
    v121[0] = 0;
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(v65, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v66, 1);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v121);
    v60 = Appx::Packaging::DownloadToTempFileStream(
            v107,
            *(struct IAppxRangeRequestJob **)(*((_QWORD *)v67 + 9) + 16LL),
            (unsigned int)v68,
            (unsigned int)v115,
            v117,
            (struct IAppxFootprintFileDownloadProgressHandler *)v121,
            v105);
    if ( v60 < 0 )
    {
      v71 = 282;
LABEL_102:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v71,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)v60,
        (int)lpString1f);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v121);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v114);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
      goto LABEL_85;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      lpString1f = v124;
      McGenEventWrite_EventWriteTransfer(v69, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v70, 1);
    }
    v60 = Appx::Packaging::Consumption::AppxEncryptedFile::SetFileStream(v67, v121[0]);
    if ( v60 < 0 )
    {
      v71 = 285;
      goto LABEL_102;
    }
    v72 = v118;
    v73 = (const unsigned __int16 *)*((_QWORD *)v47 + 3);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease((char *)v118 + 32);
    FootersStream = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::LoadManifest(
                      v67,
                      v112,
                      v73,
                      (struct IAppxManifestReader **)v72 + 4);
    if ( FootersStream < 0 )
    {
      v74 = 289;
LABEL_109:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v74,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
        (const char *)(unsigned int)FootersStream,
        (int)lpString1f);
LABEL_158:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v121);
      goto LABEL_159;
    }
    FootersStream = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                      (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v122,
                      v53);
    if ( FootersStream < 0 )
    {
      v74 = 290;
      goto LABEL_109;
    }
    v77 = v114;
    if ( v114 )
    {
      v78 = *(_QWORD *)(*((_QWORD *)v114 + 9) + 40LL);
      if ( v78 > 0xFFFFFFFF )
      {
        FootersStream = -2147024673;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)0x800700DFLL,
          (int)lpString1f);
        goto LABEL_158;
      }
      v112 = 0;
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(v75, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v76, 1);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
      v79 = v117;
      v80 = Appx::Packaging::DownloadToTempFileStream(
              v107,
              *(struct IAppxRangeRequestJob **)(*((_QWORD *)v77 + 9) + 16LL),
              (unsigned int)v78,
              (unsigned int)v115,
              v117,
              (struct IAppxFootprintFileDownloadProgressHandler *)&v112,
              v106);
      v83 = v80;
      if ( v80 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)v80,
          (int)lpString1f);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v121);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v114);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v113);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v111);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::EncryptedAppxSignatureValidator>(v47);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v107);
        v12 = v83;
        goto LABEL_167;
      }
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
      {
        lpString1f = v124;
        McGenEventWrite_EventWriteTransfer(v81, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v82, 1);
      }
      FootersStream = Appx::Packaging::Consumption::AppxEncryptedFile::SetFileStream(v77, v112);
      if ( FootersStream < 0 )
      {
        v84 = 309;
LABEL_123:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v84,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)FootersStream,
          (int)lpString1f);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
        goto LABEL_158;
      }
      v85 = (struct IAppxFile **)v118;
      FootersStream = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(
                        (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v114,
                        (__int64)v118 + 72);
      if ( FootersStream < 0 )
      {
        v84 = 311;
        goto LABEL_123;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
    }
    else
    {
      v85 = (struct IAppxFile **)v72;
      v79 = v117;
    }
    if ( *(_DWORD *)(v17 + 72) )
    {
      v112 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
      v112 = 0;
      if ( *((_DWORD *)v108 + 14) != 3 )
      {
        FootersStream = -2147019873;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedappxfootersreceiver.cpp",
          (const char *)0x8007139FLL,
          (int)lpString1f);
LABEL_134:
        v84 = 318;
        goto LABEL_123;
      }
      v87 = *((_QWORD *)v108 + 9);
      if ( v87 )
      {
        v88 = (*(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v87 + 104LL))(v87, &v112);
        FootersStream = v88;
        if ( v88 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x15C,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedappxfootersreceiver.cpp",
            (const char *)(unsigned int)v88,
            (int)lpString1f);
          goto LABEL_134;
        }
      }
      if ( !v112 )
      {
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v87, EVENT_PACKAGE_METADATA_DOWNLOAD_START, v86, 1);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
        FootersStream = Appx::Packaging::DownloadToTempFileStream(
                          v107,
                          *(struct IAppxRangeRequestJob **)(v17 + 56),
                          *(unsigned int *)(v17 + 72),
                          (unsigned int)v115,
                          v79,
                          (struct IAppxFootprintFileDownloadProgressHandler *)&v112,
                          v106);
        if ( FootersStream < 0 )
        {
          v84 = 331;
          goto LABEL_123;
        }
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
        {
          lpString1f = v124;
          McGenEventWrite_EventWriteTransfer(v89, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP, v90, 1);
        }
      }
      FootersStream = Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadCodeIntegrityFile(
                        (Appx::Packaging::Consumption::AppxEncryptedPackageReader *)v85,
                        v112,
                        (enum APPX_COMPRESSION_OPTION)*(_DWORD *)(v17 + 64),
                        v115);
      if ( FootersStream < 0 )
      {
        v84 = 334;
        goto LABEL_123;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v112);
    }
    FootersStream = Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::ValidateCodeIntegrityIfNeeded(
                      v47,
                      v85[8]);
    if ( FootersStream >= 0 )
    {
      if ( v116 && v73 && (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v91, EVENT_SIGNATURE_VALIDATION_PASSED, v73);
      pv = 0;
      PackageFullName = Appx::Packaging::Consumption::AppxEncryptedPackageReader::GetPackageFullName(
                          (Appx::Packaging::Consumption::AppxEncryptedPackageReader *)v85,
                          (unsigned __int16 **)&pv);
      FootersStream = PackageFullName;
      if ( PackageFullName >= 0 )
      {
        v95 = Microsoft_Windows_AppxPackagingOMEnableBits;
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v93, EVENT_STREAMING_READER_CREATED, pv);
          v95 = Microsoft_Windows_AppxPackagingOMEnableBits;
        }
        if ( (v95 & 0x10) != 0 )
          McGenEventWrite_EventWriteTransfer(v93, EVENT_STREAMING_READER_CREATE_STOP, v94, 1);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
          (const char *)(unsigned int)PackageFullName,
          (int)lpString1f);
      }
      CoTaskMemFree(pv);
      goto LABEL_158;
    }
    v74 = 337;
    goto LABEL_109;
  }
  v15 = (unsigned int)TempFolderPathCached;
  v13 = 135;
LABEL_10:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagestreamingreader.cpp",
    (const char *)v15,
    lpString1);
LABEL_167:
  Common::AutoPtrDeallocate<Appx::Packaging::FileNameHelper>(v119, v16);
  return v12;
}

```

## disassembly

```asm
0x18006e15c  push    rbx
0x18006e15e  push    rsi
0x18006e15f  push    rdi
0x18006e160  push    r12
0x18006e162  push    r13
0x18006e164  push    r15
0x18006e166  sub     rsp, 118h
0x18006e16d  mov     rax, cs:__security_cookie
0x18006e174  xor     rax, rsp
0x18006e177  mov     [rsp+148h+var_48], rax
0x18006e17f  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006e186  mov     r15, rcx
0x18006e189  mov     [rsp+148h+var_A0], rcx
0x18006e191  mov     rsi, r9
0x18006e194  mov     rcx, [rsp+148h+arg_38]
0x18006e19c  mov     rbx, rdx
0x18006e19f  mov     [rsp+148h+var_D0], rcx
0x18006e1a4  mov     rcx, [rsp+148h+arg_40]
0x18006e1ac  mov     [rsp+148h+var_A8], rcx
0x18006e1b4  mov     [rsp+148h+var_78], r9
0x18006e1bc  mov     [rsp+148h+var_B0], r8d
0x18006e1c4  jz      short loc_18006E1D2
0x18006e1c6  lea     rdx, EVENT_STREAMING_READER_CREATE_START
0x18006e1cd  call    McTemplateU0q_EventWriteTransfer
0x18006e1d2  lea     rdi, [r15+80h]
0x18006e1d9  mov     rdx, rbx
0x18006e1dc  mov     rcx, rdi
0x18006e1df  call    ??4?$ComPtr@VManifestComparisonHelper@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@PEAVManifestComparisonHelper@Packaging@Appx@@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::ManifestComparisonHelper>::operator=(Appx::Packaging::ManifestComparisonHelper *)
0x18006e1e4  lea     rcx, [rsp+148h+var_98]; struct Appx::Packaging::FileNameHelper **
0x18006e1ec  mov     [rsp+148h+var_98], 0
0x18006e1f8  call    ?Create@FileNameHelper@Packaging@Appx@@SAJPEAPEAV123@@Z; Appx::Packaging::FileNameHelper::Create(Appx::Packaging::FileNameHelper * *)
0x18006e1fd  mov     ebx, eax
0x18006e1ff  test    eax, eax
0x18006e201  jns     short loc_18006E20A
0x18006e203  mov     edx, 85h
0x18006e208  jmp     short loc_18006E260
0x18006e20a  mov     rcx, [rsp+148h+var_98]; this
0x18006e212  lea     rdx, [rsp+148h+var_B8]; unsigned __int16 **
0x18006e21a  mov     [rsp+148h+var_B8], 0
0x18006e226  call    ?GetTempFolderPathCached@FileNameHelper@Packaging@Appx@@QEAAJPEAPEBG@Z; Appx::Packaging::FileNameHelper::GetTempFolderPathCached(ushort const * *)
0x18006e22b  mov     ebx, eax
0x18006e22d  test    eax, eax
0x18006e22f  jns     short loc_18006E23B
0x18006e231  mov     r9d, eax
0x18006e234  mov     edx, 87h
0x18006e239  jmp     short loc_18006E263
0x18006e23b  mov     rcx, [rsp+148h+arg_28]
0x18006e243  mov     r15, [rsp+148h+arg_20]
0x18006e24b  mov     rax, rcx
0x18006e24e  not     rax
0x18006e251  cmp     r15, rax
0x18006e254  jbe     short loc_18006E27C
0x18006e256  mov     ebx, 80070216h
0x18006e25b  mov     edx, 8Ah; void *
0x18006e260  mov     r9d, ebx; char *
0x18006e263  mov     rcx, [rsp+148h]; this
0x18006e26b  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e272  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e277  jmp     loc_18006F1C0
0x18006e27c  mov     r13, [rsi+18h]
0x18006e280  lea     r12, [r15+rcx]
0x18006e284  cmp     r12, [r13+8]
0x18006e288  ja      short loc_18006E2B0
0x18006e28a  mov     rcx, [rsp+148h]; this
0x18006e292  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e299  mov     ebx, 8007000Dh
0x18006e29e  mov     edx, 91h; void *
0x18006e2a3  mov     r9d, ebx; char *
0x18006e2a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e2ab  jmp     loc_18006F1C0
0x18006e2b0  mov     rsi, r12
0x18006e2b3  mov     eax, 0FFFFFFFFh
0x18006e2b8  sub     rsi, [r13+8]
0x18006e2bc  cmp     rsi, rax
0x18006e2bf  jbe     short loc_18006E2E7
0x18006e2c1  mov     rcx, [rsp+148h]; this
0x18006e2c9  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e2d0  mov     edi, 800700DFh
0x18006e2d5  mov     edx, 94h; void *
0x18006e2da  mov     r9d, edi; char *
0x18006e2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e2e2  jmp     loc_18006F1BE
0x18006e2e7  mov     rdi, [rdi]
0x18006e2ea  lea     rcx, [rsp+148h+var_F8]
0x18006e2ef  mov     [rsp+148h+var_F8], 0
0x18006e2f8  mov     rax, [rdi]
0x18006e2fb  mov     rbx, [rax+20h]
0x18006e2ff  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e304  lea     rdx, [rsp+148h+var_F8]
0x18006e309  mov     rcx, rdi
0x18006e30c  mov     rax, rbx
0x18006e30f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e314  mov     ebx, eax
0x18006e316  test    eax, eax
0x18006e318  jns     short loc_18006E345
0x18006e31a  mov     rcx, [rsp+148h]; this
0x18006e322  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e329  mov     r9d, eax; char *
0x18006e32c  mov     edx, 96h; void *
0x18006e331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e336  lea     rcx, [rsp+148h+var_F8]
0x18006e33b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e340  jmp     loc_18006F1C0
0x18006e345  mov     rdi, [rsp+148h+var_A8]
0x18006e34d  test    rdi, rdi
0x18006e350  jz      short loc_18006E38A
0x18006e352  mov     rax, [rdi]
0x18006e355  mov     rcx, rdi
0x18006e358  mov     rdx, [rsp+148h+var_F8]
0x18006e35d  mov     rax, [rax+20h]
0x18006e361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e366  mov     ebx, eax
0x18006e368  test    eax, eax
0x18006e36a  jns     short loc_18006E38A
0x18006e36c  mov     edx, 9Ch; void *
0x18006e371  mov     rcx, [rsp+148h]; this
0x18006e379  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e380  mov     r9d, eax; char *
0x18006e383  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e388  jmp     short loc_18006E336
0x18006e38a  mov     rcx, [rsp+148h+var_F8]
0x18006e38f  mov     r8d, esi
0x18006e392  mov     rdx, [r13+8]
0x18006e396  mov     rax, [rcx]
0x18006e399  mov     rax, [rax+18h]
0x18006e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3a2  mov     ebx, eax
0x18006e3a4  test    eax, eax
0x18006e3a6  jns     short loc_18006E3AF
0x18006e3a8  mov     edx, 9Fh
0x18006e3ad  jmp     short loc_18006E371
0x18006e3af  mov     esi, [rsp+148h+var_B0]
0x18006e3b6  lea     rcx, [rsp+148h+var_F0]
0x18006e3bb  mov     ebx, esi
0x18006e3bd  mov     [rsp+148h+var_F0], 0
0x18006e3c6  and     ebx, 1
0x18006e3c9  mov     [rsp+148h+var_B0], ebx
0x18006e3d0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e3d5  mov     r9, [rsp+148h+var_B8]; unsigned __int16 *
0x18006e3dd  lea     rcx, [rsp+148h+var_F0]
0x18006e3e2  mov     [rsp+148h+var_120], rcx; struct Appx::Packaging::Consumption::EncryptedAppxFootersReceiver **
0x18006e3e7  test    ebx, ebx
0x18006e3e9  mov     r8, r12; unsigned __int64
0x18006e3ec  mov     rdx, r15; unsigned __int64
0x18006e3ef  setnz   al
0x18006e3f2  mov     rcx, r13; struct Appx::Packaging::EncryptedAppxHeader *
0x18006e3f5  mov     byte ptr [rsp+148h+lpString1], al; int
0x18006e3f9  call    ?Create@EncryptedAppxFootersReceiver@Consumption@Packaging@Appx@@SAJPEAVEncryptedAppxHeader@34@_K1PEBG_NPEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedAppxFootersReceiver::Create(Appx::Packaging::EncryptedAppxHeader *,unsigned __int64,unsigned __int64,ushort const *,bool,Appx::Packaging::Consumption::EncryptedAppxFootersReceiver * *)
0x18006e3fe  xor     r12d, r12d
0x18006e401  mov     ebx, eax
0x18006e403  test    eax, eax
0x18006e405  jns     short loc_18006E432
0x18006e407  mov     edx, 0A9h; void *
0x18006e40c  mov     rcx, [rsp+148h]; this
0x18006e414  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e41b  mov     r9d, eax; char *
0x18006e41e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e423  lea     rcx, [rsp+148h+var_F0]
0x18006e428  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e42d  jmp     loc_18006E336
0x18006e432  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006e439  jz      short loc_18006E45A
0x18006e43b  lea     rax, [rsp+148h+var_68]
0x18006e443  mov     r9d, 1
0x18006e449  lea     rdx, EVENT_PACKAGE_METADATA_DOWNLOAD_START
0x18006e450  mov     [rsp+148h+lpString1], rax
0x18006e455  call    McGenEventWrite_EventWriteTransfer
0x18006e45a  mov     rcx, [rsp+148h+var_F8]
0x18006e45f  mov     edx, 3
0x18006e464  mov     r15, [rsp+148h+var_F0]
0x18006e469  mov     r8, r15
0x18006e46c  mov     rax, [rcx]
0x18006e46f  mov     rax, [rax+20h]
0x18006e473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e478  mov     ebx, eax
0x18006e47a  test    eax, eax
0x18006e47c  jns     short loc_18006E485
0x18006e47e  mov     edx, 0ACh
0x18006e483  jmp     short loc_18006E40C
0x18006e485  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006e48c  jz      short loc_18006E4AD
0x18006e48e  lea     rax, [rsp+148h+var_68]
0x18006e496  mov     r9d, 1
0x18006e49c  lea     rdx, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP
0x18006e4a3  mov     [rsp+148h+lpString1], rax; int
0x18006e4a8  call    McGenEventWrite_EventWriteTransfer
0x18006e4ad  cmp     dword ptr [r15+38h], 3
0x18006e4b2  jz      short loc_18006E4DA
0x18006e4b4  mov     rcx, [rsp+148h]; this
0x18006e4bc  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e4c3  mov     ebx, 80080200h
0x18006e4c8  mov     edx, 0B1h; void *
0x18006e4cd  mov     r9d, ebx; char *
0x18006e4d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e4d5  jmp     loc_18006E423
0x18006e4da  cmp     [r13+30h], r12d
0x18006e4de  jbe     loc_18006E6AE
0x18006e4e4  lea     rcx, [rsp+148h+var_68]
0x18006e4ec  mov     [rsp+148h+var_68], r12
0x18006e4f4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e4f9  mov     [rsp+148h+var_68], r12
0x18006e501  cmp     dword ptr [r15+38h], 3
0x18006e506  jz      short loc_18006E52B
0x18006e508  mov     rcx, [rsp+148h]; this
0x18006e510  lea     r8, aOnecorePrintsc_59; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e517  mov     edi, 8007139Fh
0x18006e51c  mov     edx, 169h; void *
0x18006e521  mov     r9d, edi; char *
0x18006e524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e529  jmp     short loc_18006E56A
0x18006e52b  mov     rcx, [r15+50h]
0x18006e52f  test    rcx, rcx
0x18006e532  jz      short loc_18006E5A0
0x18006e534  mov     rax, [rcx]
0x18006e537  lea     rdx, [rsp+148h+var_68]
0x18006e53f  mov     rax, [rax+68h]
0x18006e543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e548  mov     edi, eax
0x18006e54a  test    eax, eax
0x18006e54c  jns     short loc_18006E598
0x18006e54e  mov     rcx, [rsp+148h]; this
0x18006e556  lea     r8, aOnecorePrintsc_59; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e55d  mov     r9d, eax; char *
0x18006e560  mov     edx, 16Ch; void *
0x18006e565  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e56a  mov     rcx, [rsp+148h]; this
0x18006e572  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e579  mov     r9d, edi; char *
0x18006e57c  mov     edx, 0B8h; void *
0x18006e581  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e586  lea     rcx, [rsp+148h+var_68]
0x18006e58e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e593  jmp     loc_18006F1AA
0x18006e598  mov     rdi, [rsp+148h+var_A8]
0x18006e5a0  cmp     [rsp+148h+var_68], r12
0x18006e5a8  jnz     loc_18006E66B
0x18006e5ae  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006e5b5  jz      short loc_18006E5D6
0x18006e5b7  lea     rax, [rsp+148h+var_88]
0x18006e5bf  mov     r9d, 1
0x18006e5c5  lea     rdx, EVENT_PACKAGE_METADATA_DOWNLOAD_START
0x18006e5cc  mov     [rsp+148h+lpString1], rax
0x18006e5d1  call    McGenEventWrite_EventWriteTransfer
0x18006e5d6  lea     rcx, [rsp+148h+var_68]
0x18006e5de  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e5e3  mov     r9, [rsp+148h+var_B8]; unsigned int
0x18006e5eb  lea     rax, [rsp+148h+var_68]
0x18006e5f3  mov     r8d, [r13+30h]; unsigned __int64
0x18006e5f7  mov     rdx, [r13+20h]; struct IAppxRangeRequestJob *
0x18006e5fb  mov     rcx, [rsp+148h+var_F8]; this
0x18006e600  mov     [rsp+148h+var_120], rax; struct IAppxFootprintFileDownloadProgressHandler *
0x18006e605  mov     [rsp+148h+lpString1], rdi; int
0x18006e60a  call    ?DownloadToTempFileStream@Packaging@Appx@@YAJPEAUIAppxRangeRequestJob@@_KIPEBGPEAUIAppxFootprintFileDownloadProgressHandler@@PEAPEAUIStream@@@Z; Appx::Packaging::DownloadToTempFileStream(IAppxRangeRequestJob *,unsigned __int64,uint,ushort const *,IAppxFootprintFileDownloadProgressHandler *,IStream * *)
0x18006e60f  mov     ebx, eax
0x18006e611  test    eax, eax
0x18006e613  jns     short loc_18006E643
0x18006e615  mov     edx, 0C5h; void *
0x18006e61a  mov     rcx, [rsp+148h]; this
0x18006e622  lea     r8, aOnecorePrintsc_24; "onecore\\printscan\\appxpackaging\\cons"...
0x18006e629  mov     r9d, eax; char *
0x18006e62c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006e631  lea     rcx, [rsp+148h+var_68]
0x18006e639  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e63e  jmp     loc_18006E423
0x18006e643  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x18006e64a  jz      short loc_18006E66B
0x18006e64c  lea     rax, [rsp+148h+var_88]
0x18006e654  mov     r9d, 1
0x18006e65a  lea     rdx, EVENT_PACKAGE_METADATA_DOWNLOAD_STOP
0x18006e661  mov     [rsp+148h+lpString1], rax
0x18006e666  call    McGenEventWrite_EventWriteTransfer
0x18006e66b  mov     r12, [rsp+148h+var_A0]
0x18006e673  mov     r9, [rsp+148h+var_B8]; unsigned __int16 *
0x18006e67b  mov     rcx, r12; this
0x18006e67e  mov     r8d, [r13+28h]; enum APPX_COMPRESSION_OPTION
0x18006e682  mov     rdx, [rsp+148h+var_68]; struct IStream *
0x18006e68a  call    ?LoadSignatureFile@AppxEncryptedPackageReader@Consumption@Packaging@Appx@@IEAAJPEAUIStream@@W4APPX_COMPRESSION_OPTION@@PEBG@Z; Appx::Packaging::Consumption::AppxEncryptedPackageReader::LoadSignatureFile(IStream *,APPX_COMPRESSION_OPTION,ushort const *)
0x18006e68f  mov     ebx, eax
0x18006e691  test    eax, eax
0x18006e693  jns     short loc_18006E69F
0x18006e695  mov     edx, 0C8h
0x18006e69a  jmp     loc_18006E61A
0x18006e69f  lea     rcx, [rsp+148h+var_68]
0x18006e6a7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18006e6ac  jmp     short loc_18006E6B6
0x18006e6ae  mov     r12, [rsp+148h+var_A0]
0x18006e6b6  mov     rdx, [r12+38h]
0x18006e6bb  lea     r8, [rsp+148h+var_88]
0x18006e6c3  mov     ecx, esi
0x18006e6c5  mov     [rsp+148h+var_88], 0
0x18006e6d1  call    ?Create@EncryptedAppxSignatureValidator@Consumption@Packaging@Appx@@SAJW4APPX_PACKAGE_READER_OPTIONS@@PEAUIAppxFile@@PEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedAppxSignatureValidator::Create(APPX_PACKAGE_READER_OPTIONS,IAppxFile *,Appx::Packaging::Consumption::EncryptedAppxSignatureValidator * *)
0x18006e6d6  mov     ebx, eax
0x18006e6d8  test    eax, eax
0x18006e6da  jns     short loc_18006E73F
0x18006e6dc  mov     edi, 800B0100h
0x18006e6e1  cmp     eax, edi
0x18006e6e3  jnz     short loc_18006E711
0x18006e6e5  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 1
0x18006e6ec  jz      short loc_18006E6FD
0x18006e6ee  mov     r8d, edi
  ... truncated ...
```
