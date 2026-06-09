# Appx::Packaging::AppxPackageEditorImpl::UpdatePackage(IStream *,IStream *,APPX_PACKAGE_EDITOR_UPDATE_PACKAGE_OPTION)

- ea: `0x1800c1aa0`
- end: `0x1800c295a`
- name: `?UpdatePackage@AppxPackageEditorImpl@Packaging@Appx@@UEAAJPEAUIStream@@0W4APPX_PACKAGE_EDITOR_UPDATE_PACKAGE_OPTION@@@Z`
- size: `3770`
- prototype: `__int64 __fastcall(Appx::Packaging::AppxPackageEditorImpl *__hidden this, struct IStream *, struct IStream *, enum APPX_PACKAGE_EDITOR_UPDATE_PACKAGE_OPTION)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800027f4`
- `0x1800029e4`
- `0x180005830`
- `0x180005eb8`
- `0x180008114`
- `0x1800133fc`
- `0x180020ff0`
- `0x180028dd0`
- `0x1800455ec`
- `0x18005bed0`
- `0x18005ccf0`
- `0x18006bee8`
- `0x18007e684`
- `0x18008c87c`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800b6bac`
- `0x1800b6ddc`
- `0x1800b71d4`
- `0x1800b7838`
- `0x1800b78cc`
- `0x1800b7ad4`
- `0x1800b7f58`
- `0x1800b9704`
- `0x1800b993c`
- `0x1800baa40`
- `0x1800bad0c`
- `0x1800baf88`
- `0x1800bb058`
- `0x1800bb814`
- `0x1800bb998`
- `0x1800bc1f4`
- `0x1800bcbb8`
- `0x1800bccc4`
- `0x1800bd4a0`
- `0x1800be16c`
- `0x1800c1aa0`
- `0x1800e9968`
- `0x1800e9aa0`
- `0x180106010`

## string_xrefs

- `0x1800c2777`: `[Content_Types].xml`
- `0x1800c2123`: `AppxManifest.xml`
- `0x1800c1f8d`: `AppxBlockMap.xml`
- `0x1800c1af0`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1b42`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1b8b`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1c02`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1c66`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1cfa`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1dc7`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1e7b`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1ef8`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1fab`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1fe5`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2056`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c20c5`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2141`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2179`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c21ed`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2257`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c22c9`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2373`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c245c`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c24f9`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2584`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c25cd`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2636`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2666`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c279c`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c2834`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1bbe`: `Appx::Packaging::AppxPackageEditorImpl::UpdatePackage`
- `0x1800c1c9f`: `Appx::Packaging::Consumption::AppxPackageReader::Create(trackingBaselineStream.Get(), true , &baselinePackageReader)`
- `0x1800c1d5e`: `opcFactory->ReadPackageFromStream(trackingDeltaStream.Get(), OPC_READ_DEFAULT, &deltaOpcPackage)`
- `0x1800c1e1f`: `PackageReaderHelper::GetPackagePartsMap(trackingDeltaStream.Get(), wil::out_param(deltaPackagePartsMap))`
- `0x1800c2009`: `AppxBlockMapReader::Create(updatedBlockMapStream.Get(), nullptr, &updatedBlockMapReader)`
- `0x1800c219d`: `Manifest::AppxManifestReaderImpl::Create(updatedManifestStream.Get(), &updatedManifestReader)`
- `0x1800c2285`: `ZipEditor::Create(trackingBaselineStream.Get(), m_WorkingDirectory.GetChars(), baselinePackageZipEditor)`
- `0x1800c2327`: `RemoveFootprintFilesFromBaselinePackage(baselinePackageZipEditor)`
- `0x1800c2490`: `AppendDeltaAndUpdatedBlockMapToPackage(updatedBlockMapReader.Get(), baselineBlockMapReader.Get(), updatedPackageFullName.get(), deltaOpcPackage.Get(), deltaPackagePartsMap.get(), baselinePackageZipEditor, m_WorkingDirectory.GetChars())`
- `0x1800c2745`: `AppendWholeDeltaFileToPackage(contentTypesStream.Get(), ContentTypes::FileNameA, baselinePackageZipEditor, m_WorkingDirectory.GetChars(), nullptr)`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppxPackageEditorImpl::UpdatePackage(
        struct Appx::Packaging::ZipEditor **this,
        struct IStream *a2,
        struct IStream *a3,
        enum APPX_PACKAGE_EDITOR_UPDATE_PACKAGE_OPTION a4)
{
  __int64 v8; // rdx
  unsigned int PackagePartsMap; // ebx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  struct IOpcFactory **v15; // r8
  int OpcFactory; // eax
  struct IStream *v17; // rsi
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, struct IStream *, _QWORD, __int64 *); // rbx
  int v21; // eax
  unsigned __int64 v22; // r8
  void *v23; // rcx
  Appx::Packaging *v24; // rbx
  int v25; // eax
  int ContentTypesDeltaRelativeFileName; // edi
  void *v27; // rcx
  int OpcFileStream; // eax
  const unsigned __int16 *v29; // rdx
  int v30; // eax
  __int64 v31; // rdi
  int v32; // eax
  _BOOL8 v33; // r8
  int v34; // eax
  unsigned __int16 **v35; // r8
  int PackageFullNameFromManifest; // eax
  int v37; // eax
  struct Appx::Packaging::ZipFileItem **v38; // rbx
  struct Appx::Packaging::ZipEditor *v39; // rdx
  int v40; // eax
  unsigned int v41; // r14d
  void *v42; // rcx
  int updated; // eax
  int appended; // eax
  int v45; // eax
  const unsigned __int16 **v46; // rdx
  unsigned __int64 v47; // rdx
  void *v48; // rcx
  int v49; // eax
  unsigned __int64 v50; // rdx
  void *v51; // rcx
  void *v52; // rcx
  int v53; // eax
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp *v54; // rcx
  int v55; // eax
  unsigned __int64 v56; // rdx
  void *v57; // rcx
  void *v58; // rcx
  int v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  _BYTE v63[8]; // [rsp+40h] [rbp-C0h] BYREF
  void *v64; // [rsp+48h] [rbp-B8h] BYREF
  struct IStream *v65; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  Appx::Packaging *v68; // [rsp+68h] [rbp-98h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v69; // [rsp+70h] [rbp-90h] BYREF
  struct IStream *v70; // [rsp+78h] [rbp-88h] BYREF
  struct IStream *v71; // [rsp+80h] [rbp-80h] BYREF
  struct IAppxManifestReader *v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  struct IAppxManifestReader v74; // [rsp+98h] [rbp-68h] BYREF
  void *v75; // [rsp+A0h] [rbp-60h] BYREF
  Appx::Packaging *v76; // [rsp+A8h] [rbp-58h] BYREF
  int v77[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct IStream *v78; // [rsp+B8h] [rbp-48h] BYREF
  struct Appx::Packaging::ZipFileItem **v79; // [rsp+C0h] [rbp-40h] BYREF
  void **v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  char v82; // [rsp+D8h] [rbp-28h]
  _QWORD v83[42]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v84[42]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v85[42]; // [rsp+380h] [rbp+280h] BYREF
  _QWORD v86[42]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _QWORD v87[42]; // [rsp+620h] [rbp+520h] BYREF
  _QWORD v88[42]; // [rsp+770h] [rbp+670h] BYREF
  _QWORD v89[42]; // [rsp+8C0h] [rbp+7C0h] BYREF
  _BYTE v90[336]; // [rsp+A10h] [rbp+910h] BYREF
  _BYTE v91[336]; // [rsp+B60h] [rbp+A60h] BYREF
  _BYTE v92[336]; // [rsp+CB0h] [rbp+BB0h] BYREF
  _BYTE v93[336]; // [rsp+E00h] [rbp+D00h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F98h] [rbp+E98h]

  if ( a2 )
  {
    if ( !a3 )
    {
      v8 = 1040;
      goto LABEL_3;
    }
    v78 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
    v10 = CreatePerfLoggingStream(a2, L"baseline", &v78);
    PackagePartsMap = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v10,
        v60);
LABEL_94:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v78);
      return PackagePartsMap;
    }
    v65 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    v11 = CreatePerfLoggingStream(a3, L"delta", &v65);
    PackagePartsMap = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x416,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v11,
        v60);
LABEL_10:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      goto LABEL_94;
    }
    wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v83);
    v83[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83,
      L"Appx::Packaging::AppxPackageEditorImpl::UpdatePackage");
    PerfLoggerDetails::PerfLoggerGlobals::BeginStack(&qword_180169AD0, v63, v83);
    if ( a4 )
    {
      PackagePartsMap = -2147024809;
      v12 = 1051;
      v13 = 2147942487LL;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)v13,
        v60);
LABEL_14:
      PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
      goto LABEL_10;
    }
    v14 = Appx::Packaging::AppxPackageEditorImpl::EnsureWorkingDirectory((Appx::Packaging::AppxPackageEditorImpl *)this);
    PackagePartsMap = v14;
    if ( v14 < 0 )
    {
      v13 = (unsigned int)v14;
      v12 = 1053;
      goto LABEL_13;
    }
    v67 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    OpcFactory = Appx::Packaging::CreateOpcFactory(0, (struct IAppxMessageHandler *)&v67, v15);
    PackagePartsMap = OpcFactory;
    if ( OpcFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x420,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)OpcFactory,
        v60);
LABEL_19:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      goto LABEL_14;
    }
    v68 = 0;
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v84);
    v84[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84,
      L"Appx::Packaging::Consumption::AppxPackageReader::Create(trackingBaselineStream.Get(), true , &baselinePackageReader)");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v84);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    v17 = v78;
    v18 = Appx::Packaging::Consumption::AppxPackageReader::Create((__int64)v78, 1, 0, &v68);
    PackagePartsMap = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x422,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v18,
        v60);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
LABEL_22:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      goto LABEL_19;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
    v66 = 0;
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v85);
    v85[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85,
      L"opcFactory->ReadPackageFromStream(trackingDeltaStream.Get(), OPC_READ_DEFAULT, &deltaOpcPackage)");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v85);
    v19 = v67;
    v20 = *(__int64 (__fastcall **)(__int64, struct IStream *, _QWORD, __int64 *))(*(_QWORD *)v67 + 56LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
    v21 = v20(v19, v65, 0, &v66);
    PackagePartsMap = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x424,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v21,
        v60);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85);
LABEL_25:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      goto LABEL_22;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85);
    v64 = 0;
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v90,
      L"PackageReaderHelper::GetPackagePartsMap(trackingDeltaStream.Get(), wil::out_param(deltaPackagePartsMap))");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v90);
    v80 = &v64;
    v81 = 0;
    v82 = 1;
    PackagePartsMap = Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(v65, &v81, v22);
    wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>,wistd::default_delete<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>,wistd::default_delete<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>>>(&v80);
    if ( (PackagePartsMap & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)PackagePartsMap,
        v60);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v90);
      goto LABEL_28;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v90);
    v24 = v68;
    v25 = Appx::Packaging::EnsureBaselineAndDeltaSourceVersionsMatch(v68);
    ContentTypesDeltaRelativeFileName = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x429,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v25,
        v60);
LABEL_32:
      v27 = v64;
      v64 = 0;
      if ( v27 )
        Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(v27);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      PackagePartsMap = ContentTypesDeltaRelativeFileName;
      goto LABEL_94;
    }
    v69 = 0;
    v70 = 0;
    *(_QWORD *)v77 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
    OpcFileStream = Appx::Packaging::TryGetOpcFileStream(v66, v64, L"AppxBlockMap.xml", &v70);
    ContentTypesDeltaRelativeFileName = OpcFileStream;
    if ( OpcFileStream < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)OpcFileStream,
        (int)v77);
LABEL_37:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
      goto LABEL_32;
    }
    if ( !*(_QWORD *)v77 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x430,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)0x8008020ELL,
        (int)v77);
LABEL_81:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
      v52 = v64;
      v64 = 0;
      if ( v52 )
        Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(v52);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      PackagePartsMap = -2146958834;
      goto LABEL_94;
    }
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v91,
      L"AppxBlockMapReader::Create(updatedBlockMapStream.Get(), nullptr, &updatedBlockMapReader)");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v91);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
    v30 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(v70, v29, &v69);
    ContentTypesDeltaRelativeFileName = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x431,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v30,
        (int)v77);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v91);
      goto LABEL_37;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v91);
    v73 = *((_QWORD *)v24 + 6);
    v31 = v73;
    Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v73);
    if ( !Common::String::Equals(*(const unsigned __int16 **)(v31 + 24), *((const unsigned __int16 **)v69 + 3)) )
    {
      PackagePartsMap = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x437,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)0x80070057LL,
        (int)v77);
LABEL_44:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
LABEL_28:
      v23 = v64;
      v64 = 0;
      if ( v23 )
        Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(v23);
      goto LABEL_25;
    }
    v72 = 0;
    v71 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
    v32 = Appx::Packaging::TryGetOpcFileStream(v66, v64, L"AppxManifest.xml", &v71);
    PackagePartsMap = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v32,
        (int)v77);
LABEL_47:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
      goto LABEL_44;
    }
    if ( !*(_QWORD *)v77 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)0x8008020ELL,
        (int)v77);
LABEL_80:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
      goto LABEL_81;
    }
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v92,
      L"Manifest::AppxManifestReaderImpl::Create(updatedManifestStream.Get(), &updatedManifestReader)");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v92);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
    LOBYTE(v33) = 1;
    v34 = Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(v71, &v72, v33, 0);
    PackagePartsMap = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v34,
        (int)v77);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v92);
      goto LABEL_47;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v92);
    v74.lpVtbl = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v74,
      0);
    PackageFullNameFromManifest = Appx::Packaging::GetPackageFullNameFromManifest((Appx::Packaging *)v72, &v74, v35);
    PackagePartsMap = PackageFullNameFromManifest;
    if ( PackageFullNameFromManifest >= 0 )
    {
      v79 = 0;
      PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
        (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v93,
        L"ZipEditor::Create(trackingBaselineStream.Get(), m_WorkingDirectory.GetChars(), baselinePackageZipEditor)");
      PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v93);
      v37 = Appx::Packaging::ZipEditor::Create(v17, this[3], &v79);
      PackagePartsMap = v37;
      if ( v37 >= 0 )
      {
        PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
        PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v93);
        PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
        wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
        v86[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
        PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
          (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86,
          L"RemoveFootprintFilesFromBaselinePackage(baselinePackageZipEditor)");
        PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v86);
        v38 = v79;
        v40 = Appx::Packaging::RemoveFootprintFilesFromBaselinePackage((Appx::Packaging *)v79, v39);
        v41 = v40;
        if ( v40 >= 0 )
        {
          PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
          PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86);
          updated = Appx::Packaging::ZipEditor::UpdateLocalFileItemsInArchiveStream(v38);
          v41 = updated;
          if ( updated >= 0 )
          {
            PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
            wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v87);
            v87[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
            PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
              (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v87,
              L"AppendDeltaAndUpdatedBlockMapToPackage(updatedBlockMapReader.Get(), baselineBlockMapReader.Get(), updatedP"
               "ackageFullName.get(), deltaOpcPackage.Get(), deltaPackagePartsMap.get(), baselinePackageZipEditor, m_Work"
               "ingDirectory.GetChars())");
            PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v87);
            v61 = (int)v64;
            appended = Appx::Packaging::AppendDeltaAndUpdatedBlockMapToPackage(v69, v31, v74.lpVtbl, v66);
            ContentTypesDeltaRelativeFileName = appended;
            if ( appended >= 0 )
            {
              PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
              PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v87);
              v45 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD))(*(_QWORD *)v17 + 64LL))(v17, 0);
              ContentTypesDeltaRelativeFileName = v45;
              if ( v45 >= 0 )
              {
                v75 = 0;
                v80 = &v75;
                v81 = 0;
                v82 = 1;
                ContentTypesDeltaRelativeFileName = Appx::Packaging::GetContentTypesDeltaRelativeFileName(
                                                      (Appx::Packaging *)&v81,
                                                      v46);
                wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v80);
                if ( ContentTypesDeltaRelativeFileName >= 0 )
                {
                  v76 = 0;
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
                  v49 = Appx::Packaging::TryGetOpcFileStream(v66, v64, v75, &v76);
                  ContentTypesDeltaRelativeFileName = v49;
                  if ( v49 >= 0 )
                  {
                    if ( !*(_QWORD *)v77 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x457,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                        (const char *)0x8008020ELL,
                        (int)v77);
                      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
                      v51 = v75;
                      v75 = 0;
                      if ( v51 )
                        operator delete(v51, v50);
                      Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v38);
                      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
                      goto LABEL_80;
                    }
                    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                    wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v88);
                    v88[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
                    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
                      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v88,
                      L"AppendWholeDeltaFileToPackage(contentTypesStream.Get(), ContentTypes::FileNameA, baselinePackageZi"
                       "pEditor, m_WorkingDirectory.GetChars(), nullptr)");
                    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v88);
                    v53 = Appx::Packaging::AppendWholeDeltaFileToPackage(
                            v76,
                            (struct IStream *)"[Content_Types].xml",
                            (const char *)v38,
                            this[3],
                            0,
                            v38);
                    ContentTypesDeltaRelativeFileName = v53;
                    if ( v53 >= 0 )
                    {
                      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v88);
                      PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                      wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v89);
                      v89[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
                      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
                        (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v89,
                        L"baselinePackageZipEditor->Flush(ZipEditorBehaviorFlags::OptimizeForTailEdits)");
                      PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v89);
                      v55 = Appx::Packaging::ZipEditor::Flush(v38);
                      ContentTypesDeltaRelativeFileName = v55;
                      if ( v55 >= 0 )
                      {
                        PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                        PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v89);
                        Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v38);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
                        v57 = v75;
                        v75 = 0;
                        if ( v57 )
                          operator delete(v57, v56);
                        Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(0);
                        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
                        v58 = v64;
                        v64 = 0;
                        if ( v58 )
                          Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(v58);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
                        PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
                        PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
                        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
                        PackagePartsMap = 0;
                        goto LABEL_94;
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x45B,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                        (const char *)(unsigned int)v55,
                        v62);
                      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                      v54 = (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v89;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x458,
                        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                        (const char *)(unsigned int)v53,
                        v62);
                      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
                      v54 = (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v88;
                    }
                    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(v54);
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x456,
                      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                      (const char *)(unsigned int)v49,
                      (int)v77);
                  }
                  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x454,
                    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                    (const char *)(unsigned int)ContentTypesDeltaRelativeFileName,
                    v61);
                }
                v48 = v75;
                v75 = 0;
                if ( v48 )
                  operator delete(v48, v47);
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x450,
                  (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                  (const char *)(unsigned int)v45,
                  v61);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x44F,
                (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
                (const char *)(unsigned int)appended,
                v61);
              PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
              PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v87);
            }
            Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v38);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
            Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
            goto LABEL_37;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44A,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)updated,
            (int)v77);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x447,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)v40,
            (int)v77);
          PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
          PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86);
        }
        Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v38);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v72);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
        v42 = v64;
        v64 = 0;
        if ( v42 )
          Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(v42);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
        PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
        PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
        PackagePartsMap = v41;
        goto LABEL_94;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x444,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v37,
        (int)v77);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v93);
      Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v79);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x440,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)PackageFullNameFromManifest,
        (int)v77);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
    goto LABEL_47;
  }
  v8 = 1039;
LABEL_3:
  PackagePartsMap = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
    (const char *)0x80070057LL,
    v60);
  return PackagePartsMap;
}

```

## disassembly

```asm
0x1800c1aa0  mov     [rsp-8+arg_18], rbx
0x1800c1aa5  push    rbp
0x1800c1aa6  push    rsi
0x1800c1aa7  push    rdi
0x1800c1aa8  push    r12
0x1800c1aaa  push    r13
0x1800c1aac  push    r14
0x1800c1aae  push    r15
0x1800c1ab0  lea     rbp, [rsp-0E60h]
0x1800c1ab8  sub     rsp, 0F60h
0x1800c1abf  mov     rax, cs:__security_cookie
0x1800c1ac6  xor     rax, rsp
0x1800c1ac9  mov     [rbp+0E90h+var_40], rax
0x1800c1ad0  xor     r12d, r12d
0x1800c1ad3  mov     esi, r9d
0x1800c1ad6  mov     rdi, r8
0x1800c1ad9  mov     rbx, rdx
0x1800c1adc  mov     r15, rcx
0x1800c1adf  test    rdx, rdx
0x1800c1ae2  jnz     short loc_1800C1B09
0x1800c1ae4  mov     edx, 40Fh; void *
0x1800c1ae9  mov     rcx, [rbp+0E98h]; this
0x1800c1af0  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1af7  mov     ebx, 80070057h
0x1800c1afc  mov     r9d, ebx; char *
0x1800c1aff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b04  jmp     loc_1800C292D
0x1800c1b09  test    rdi, rdi
0x1800c1b0c  jnz     short loc_1800C1B15
0x1800c1b0e  mov     edx, 410h
0x1800c1b13  jmp     short loc_1800C1AE9
0x1800c1b15  lea     rcx, [rbp+0E90h+var_ED8]
0x1800c1b19  mov     [rbp+0E90h+var_ED8], r12
0x1800c1b1d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1b22  lea     r8, [rbp+0E90h+var_ED8]; struct IStream **
0x1800c1b26  mov     rcx, rbx; struct IStream *
0x1800c1b29  lea     rdx, aBaseline; "baseline"
0x1800c1b30  call    ?CreatePerfLoggingStream@@YAJPEAUIStream@@PEBGPEAPEAU1@@Z; CreatePerfLoggingStream(IStream *,ushort const *,IStream * *)
0x1800c1b35  mov     ebx, eax
0x1800c1b37  test    eax, eax
0x1800c1b39  jns     short loc_1800C1B5B
0x1800c1b3b  mov     rcx, [rbp+0E98h]; this
0x1800c1b42  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1b49  mov     r9d, eax; char *
0x1800c1b4c  mov     edx, 414h; void *
0x1800c1b51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b56  jmp     loc_1800C2924
0x1800c1b5b  lea     rcx, [rsp+0F90h+var_F40]
0x1800c1b60  mov     [rsp+0F90h+var_F40], r12
0x1800c1b65  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1b6a  lea     r8, [rsp+0F90h+var_F40]; struct IStream **
0x1800c1b6f  mov     rcx, rdi; struct IStream *
0x1800c1b72  lea     rdx, aDelta; "delta"
0x1800c1b79  call    ?CreatePerfLoggingStream@@YAJPEAUIStream@@PEBGPEAPEAU1@@Z; CreatePerfLoggingStream(IStream *,ushort const *,IStream * *)
0x1800c1b7e  mov     ebx, eax
0x1800c1b80  test    eax, eax
0x1800c1b82  jns     short loc_1800C1BAE
0x1800c1b84  mov     rcx, [rbp+0E98h]; this
0x1800c1b8b  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1b92  mov     r9d, eax; char *
0x1800c1b95  mov     edx, 416h; void *
0x1800c1b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1b9f  lea     rcx, [rsp+0F90h+var_F40]
0x1800c1ba4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1ba9  jmp     loc_1800C2924
0x1800c1bae  lea     rcx, [rbp+0E90h+var_EB0]; struct wil::details::IFailureCallback *
0x1800c1bb2  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c1bb7  lea     r14, ??_7TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@6B@; const PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable'
0x1800c1bbe  lea     rdx, aAppxPackagingA_0; "Appx::Packaging::AppxPackageEditorImpl:"...
0x1800c1bc5  mov     [rbp+0E90h+var_EB0], r14
0x1800c1bc9  lea     rcx, [rbp+0E90h+var_EB0]; this
0x1800c1bcd  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c1bd2  lea     r13, qword_180169AD0
0x1800c1bd9  mov     rcx, r13
0x1800c1bdc  lea     r8, [rbp+0E90h+var_EB0]
0x1800c1be0  lea     rdx, [rsp+0F90h+var_F50]
0x1800c1be5  call    ?BeginStack@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUStackRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::BeginStack(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c1bea  test    esi, esi
0x1800c1bec  jz      short loc_1800C1C26
0x1800c1bee  mov     ebx, 80070057h
0x1800c1bf3  mov     edx, 41Bh; void *
0x1800c1bf8  mov     r9d, ebx; char *
0x1800c1bfb  mov     rcx, [rbp+0E98h]; this
0x1800c1c02  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1c0e  lea     rcx, [rsp+0F90h+var_F50]; this
0x1800c1c13  call    ??1StackRemover@PerfLoggerGlobals@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover(void)
0x1800c1c18  lea     rcx, [rbp+0E90h+var_EB0]; this
0x1800c1c1c  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1c21  jmp     loc_1800C1B9F
0x1800c1c26  mov     rcx, r15; this
0x1800c1c29  call    ?EnsureWorkingDirectory@AppxPackageEditorImpl@Packaging@Appx@@AEAAJXZ; Appx::Packaging::AppxPackageEditorImpl::EnsureWorkingDirectory(void)
0x1800c1c2e  mov     ebx, eax
0x1800c1c30  test    eax, eax
0x1800c1c32  jns     short loc_1800C1C3E
0x1800c1c34  mov     r9d, eax
0x1800c1c37  mov     edx, 41Dh
0x1800c1c3c  jmp     short loc_1800C1BFB
0x1800c1c3e  lea     rcx, [rsp+0F90h+var_F30]
0x1800c1c43  mov     [rsp+0F90h+var_F30], r12
0x1800c1c48  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1c4d  lea     rdx, [rsp+0F90h+var_F30]; struct IAppxMessageHandler *
0x1800c1c52  xor     ecx, ecx; this
0x1800c1c54  call    ?CreateOpcFactory@Packaging@Appx@@YAJPEAUIAppxMessageHandler@@PEAPEAUIOpcFactory@@@Z; Appx::Packaging::CreateOpcFactory(IAppxMessageHandler *,IOpcFactory * *)
0x1800c1c59  mov     ebx, eax
0x1800c1c5b  test    eax, eax
0x1800c1c5d  jns     short loc_1800C1C86
0x1800c1c5f  mov     rcx, [rbp+0E98h]; this
0x1800c1c66  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1c6d  mov     r9d, eax; char *
0x1800c1c70  mov     edx, 420h; void *
0x1800c1c75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1c7a  lea     rcx, [rsp+0F90h+var_F30]
0x1800c1c7f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1c84  jmp     short loc_1800C1C0E
0x1800c1c86  mov     rcx, r13; this
0x1800c1c89  mov     [rsp+0F90h+var_F28], r12
0x1800c1c8e  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c1c93  lea     rcx, [rbp+0E90h+var_D60]; struct wil::details::IFailureCallback *
0x1800c1c9a  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c1c9f  lea     rdx, aAppxPackagingC_5; "Appx::Packaging::Consumption::AppxPacka"...
0x1800c1ca6  mov     [rbp+0E90h+var_D60], r14
0x1800c1cad  lea     rcx, [rbp+0E90h+var_D60]; this
0x1800c1cb4  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c1cb9  lea     r8, [rbp+0E90h+var_D60]
0x1800c1cc0  mov     rcx, r13
0x1800c1cc3  lea     rdx, [rsp+0F90h+var_F50]
0x1800c1cc8  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c1ccd  lea     rcx, [rsp+0F90h+var_F28]
0x1800c1cd2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1cd7  mov     rsi, [rbp+0E90h+var_ED8]
0x1800c1cdb  lea     r9, [rsp+0F90h+var_F28]
0x1800c1ce0  mov     rcx, rsi
0x1800c1ce3  xor     r8d, r8d
0x1800c1ce6  mov     dl, 1
0x1800c1ce8  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader> * *)
0x1800c1ced  mov     ebx, eax
0x1800c1cef  test    eax, eax
0x1800c1cf1  jns     short loc_1800C1D31
0x1800c1cf3  mov     rcx, [rbp+0E98h]; this
0x1800c1cfa  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1d01  mov     r9d, eax; char *
0x1800c1d04  mov     edx, 422h; void *
0x1800c1d09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1d0e  mov     rcx, r13; this
0x1800c1d11  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1d16  lea     rcx, [rbp+0E90h+var_D60]; this
0x1800c1d1d  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1d22  lea     rcx, [rsp+0F90h+var_F28]
0x1800c1d27  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1d2c  jmp     loc_1800C1C7A
0x1800c1d31  mov     rcx, r13; this
0x1800c1d34  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1d39  lea     rcx, [rbp+0E90h+var_D60]; this
0x1800c1d40  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1d45  mov     rcx, r13; this
0x1800c1d48  mov     [rsp+0F90h+var_F38], r12
0x1800c1d4d  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c1d52  lea     rcx, [rbp+0E90h+var_C10]; struct wil::details::IFailureCallback *
0x1800c1d59  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c1d5e  lea     rdx, aOpcfactoryRead; "opcFactory->ReadPackageFromStream(track"...
0x1800c1d65  mov     [rbp+0E90h+var_C10], r14
0x1800c1d6c  lea     rcx, [rbp+0E90h+var_C10]; this
0x1800c1d73  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c1d78  lea     r8, [rbp+0E90h+var_C10]
0x1800c1d7f  mov     rcx, r13
0x1800c1d82  lea     rdx, [rsp+0F90h+var_F50]
0x1800c1d87  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c1d8c  mov     rdi, [rsp+0F90h+var_F30]
0x1800c1d91  lea     rcx, [rsp+0F90h+var_F38]
0x1800c1d96  mov     rax, [rdi]
0x1800c1d99  mov     rbx, [rax+38h]
0x1800c1d9d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1da2  mov     rdx, [rsp+0F90h+var_F40]
0x1800c1da7  lea     r9, [rsp+0F90h+var_F38]
0x1800c1dac  xor     r8d, r8d
0x1800c1daf  mov     rcx, rdi
0x1800c1db2  mov     rax, rbx
0x1800c1db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1dba  mov     ebx, eax
0x1800c1dbc  test    eax, eax
0x1800c1dbe  jns     short loc_1800C1DFE
0x1800c1dc0  mov     rcx, [rbp+0E98h]; this
0x1800c1dc7  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1dce  mov     r9d, eax; char *
0x1800c1dd1  mov     edx, 424h; void *
0x1800c1dd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1ddb  mov     rcx, r13; this
0x1800c1dde  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1de3  lea     rcx, [rbp+0E90h+var_C10]; this
0x1800c1dea  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1def  lea     rcx, [rsp+0F90h+var_F38]
0x1800c1df4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1df9  jmp     loc_1800C1D22
0x1800c1dfe  mov     rcx, r13; this
0x1800c1e01  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1e06  lea     rcx, [rbp+0E90h+var_C10]; this
0x1800c1e0d  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1e12  mov     rcx, r13; this
0x1800c1e15  mov     [rsp+0F90h+var_F48], r12
0x1800c1e1a  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c1e1f  lea     rdx, aPackagereaderh; "PackageReaderHelper::GetPackagePartsMap"...
0x1800c1e26  lea     rcx, [rbp+0E90h+var_580]; this
0x1800c1e2d  call    ??$Start@AEAY0DP@$$CBG@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@SA?AV012@AEAY0DP@$$CBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<ushort const (&)[63]>(ushort const (&)[63])
0x1800c1e32  lea     r8, [rbp+0E90h+var_580]
0x1800c1e39  mov     rcx, r13
0x1800c1e3c  lea     rdx, [rsp+0F90h+var_F50]
0x1800c1e41  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c1e46  mov     rcx, [rsp+0F90h+var_F40]
0x1800c1e4b  lea     rax, [rsp+0F90h+var_F48]
0x1800c1e50  lea     rdx, [rbp+0E90h+var_EC0]
0x1800c1e54  mov     [rbp+0E90h+var_EC8], rax
0x1800c1e58  mov     [rbp+0E90h+var_EC0], r12
0x1800c1e5c  mov     [rbp+0E90h+var_EB8], 1
0x1800c1e60  call    ?GetPackagePartsMap@PackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> * *)
0x1800c1e65  lea     rcx, [rbp+0E90h+var_EC8]
0x1800c1e69  mov     ebx, eax
0x1800c1e6b  call    ??1?$out_param_t@V?$unique_ptr@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@U?$default_delete@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>,wistd::default_delete<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>,wistd::default_delete<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>>>(void)
0x1800c1e70  test    ebx, ebx
0x1800c1e72  jns     short loc_1800C1EC0
0x1800c1e74  mov     rcx, [rbp+0E98h]; this
0x1800c1e7b  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1e82  mov     r9d, ebx; char *
0x1800c1e85  mov     edx, 426h; void *
0x1800c1e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1e8f  mov     rcx, r13; this
0x1800c1e92  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1e97  lea     rcx, [rbp+0E90h+var_580]; this
0x1800c1e9e  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1ea3  mov     rcx, [rsp+0F90h+var_F48]; void *
0x1800c1ea8  mov     [rsp+0F90h+var_F48], r12
0x1800c1ead  test    rcx, rcx
0x1800c1eb0  jz      loc_1800C1DEF
0x1800c1eb6  call    ??_G?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(uint)
0x1800c1ebb  jmp     loc_1800C1DEF
0x1800c1ec0  mov     rcx, r13; this
0x1800c1ec3  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1ec8  lea     rcx, [rbp+0E90h+var_580]; this
0x1800c1ecf  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1ed4  mov     rbx, [rsp+0F90h+var_F28]
0x1800c1ed9  mov     r8, [rsp+0F90h+var_F48]
0x1800c1ede  mov     rcx, rbx; this
0x1800c1ee1  mov     rdx, [rsp+0F90h+var_F38]
0x1800c1ee6  call    ?EnsureBaselineAndDeltaSourceVersionsMatch@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEAUIOpcPackage@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Z; Appx::Packaging::EnsureBaselineAndDeltaSourceVersionsMatch(IAppxPackageReader *,IOpcPackage *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x1800c1eeb  mov     edi, eax
0x1800c1eed  test    eax, eax
0x1800c1eef  jns     short loc_1800C1F62
0x1800c1ef1  mov     rcx, [rbp+0E98h]; this
0x1800c1ef8  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1eff  mov     r9d, eax; char *
0x1800c1f02  mov     edx, 429h; void *
0x1800c1f07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1f0c  mov     rcx, [rsp+0F90h+var_F48]; void *
0x1800c1f11  mov     [rsp+0F90h+var_F48], r12
0x1800c1f16  test    rcx, rcx
0x1800c1f19  jz      short loc_1800C1F20
0x1800c1f1b  call    ??_G?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>::`scalar deleting destructor'(uint)
0x1800c1f20  lea     rcx, [rsp+0F90h+var_F38]
0x1800c1f25  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1f2a  lea     rcx, [rsp+0F90h+var_F28]
0x1800c1f2f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1f34  lea     rcx, [rsp+0F90h+var_F30]
0x1800c1f39  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1f3e  lea     rcx, [rsp+0F90h+var_F50]; this
0x1800c1f43  call    ??1StackRemover@PerfLoggerGlobals@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover(void)
0x1800c1f48  lea     rcx, [rbp+0E90h+var_EB0]; this
0x1800c1f4c  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1f51  lea     rcx, [rsp+0F90h+var_F40]
0x1800c1f56  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1f5b  mov     ebx, edi
0x1800c1f5d  jmp     loc_1800C2924
0x1800c1f62  lea     rcx, [rsp+0F90h+var_F18]
0x1800c1f67  mov     [rsp+0F90h+var_F20], r12
0x1800c1f6c  mov     [rsp+0F90h+var_F18], r12
0x1800c1f71  mov     qword ptr [rbp+0E90h+var_EE0], r12
0x1800c1f75  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1f7a  mov     rdx, [rsp+0F90h+var_F48]
0x1800c1f7f  lea     rax, [rbp+0E90h+var_EE0]
0x1800c1f83  mov     rcx, [rsp+0F90h+var_F38]
0x1800c1f88  lea     r9, [rsp+0F90h+var_F18]
0x1800c1f8d  lea     r8, ?FileName@BlockMap@Packaging@Appx@@3QBGB; "AppxBlockMap.xml"
0x1800c1f94  mov     [rsp+0F90h+var_F70], rax; int
0x1800c1f99  call    ?TryGetOpcFileStream@Packaging@Appx@@YAJPEAUIOpcPackage@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAPEAUIStream@@PEAPEBUAppxFileInfo@Consumption@12@@Z; Appx::Packaging::TryGetOpcFileStream(IOpcPackage *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,IStream * *,Appx::Packaging::Consumption::AppxFileInfo const * *)
0x1800c1f9e  mov     edi, eax
0x1800c1fa0  test    eax, eax
0x1800c1fa2  jns     short loc_1800C1FD8
0x1800c1fa4  mov     rcx, [rbp+0E98h]; this
0x1800c1fab  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1fb2  mov     r9d, eax; char *
0x1800c1fb5  mov     edx, 42Fh; void *
0x1800c1fba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1fbf  lea     rcx, [rsp+0F90h+var_F18]
0x1800c1fc4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1fc9  lea     rcx, [rsp+0F90h+var_F20]
0x1800c1fce  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1fd3  jmp     loc_1800C1F0C
0x1800c1fd8  cmp     qword ptr [rbp+0E90h+var_EE0], r12
0x1800c1fdc  jnz     short loc_1800C2001
0x1800c1fde  mov     rcx, [rbp+0E98h]; this
0x1800c1fe5  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
  ... truncated ...
```
