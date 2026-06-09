# Appx::Packaging::UpdateManifestInPlaceUnencrypted(IStream *,IStream *,ushort const *,bool,bool)

- ea: `0x1800c0f54`
- end: `0x1800c1a8e`
- name: `?UpdateManifestInPlaceUnencrypted@Packaging@Appx@@YAJPEAUIStream@@0PEBG_N2@Z`
- size: `2874`
- prototype: `__int64 __fastcall(Appx::Packaging *__hidden this, struct IStream *, struct IStream *, const unsigned __int16 *, bool, bool)`
- caller_count: `1`
- callee_count: `47`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c2960`

## callees

- `0x1800027f4`
- `0x1800029e4`
- `0x180002a70`
- `0x180004c24`
- `0x180004f9c`
- `0x1800056a4`
- `0x180005830`
- `0x180005eb8`
- `0x180008f4c`
- `0x180009eb8`
- `0x1800133fc`
- `0x180020ff0`
- `0x180046f00`
- `0x18005b1f0`
- `0x18005ccf0`
- `0x18005f144`
- `0x18007a498`
- `0x18007d684`
- `0x18007f72c`
- `0x1800804a8`
- `0x18008390c`
- `0x180087cb4`
- `0x1800992a0`
- `0x1800ac600`
- `0x1800b6980`
- `0x1800b6bac`
- `0x1800b6bec`
- `0x1800b6ddc`
- `0x1800b7174`
- `0x1800b7204`
- `0x1800b73bc`
- `0x1800b7838`
- `0x1800b78cc`
- `0x1800b7ad4`
- `0x1800b993c`
- `0x1800ba85c`
- `0x1800baa40`
- `0x1800bac08`
- `0x1800bc1f4`
- `0x1800bcbb8`
- `0x1800bd4a0`
- `0x1800c0f54`
- `0x1800e9968`
- `0x1800e99f8`
- `0x1800e9fe8`
- `0x1800f9dcc`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c153f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c1573`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c15a3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c15d3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c153f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c1573`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c15a3`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800c15d3`

## string_xrefs

- `0x1800c17fd`: `AppxManifest.xml`
- `0x1800c0fc0`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c103f`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c10f7`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c117f`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c11d4`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1240`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c12ba`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c131c`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c140a`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1497`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1656`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c16b0`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1724`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c18be`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c19d1`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c1520`: `AppxBlockMap.xml`
- `0x1800c1958`: `AppxBlockMap.xml`
- `0x1800c1558`: `AppxManifest.xml`
- `0x1800c1857`: `AppxManifest.xml`
- `0x1800c1638`: `TempAppxBlockMap`
- `0x1800c0fe9`: `Appx::Packaging::UpdateManifestInPlaceUnencrypted`
- `0x1800c109f`: `Consumption::AppxPackageReader::Create(trackingPackageStream.Get(), false, &packageReader)`
- `0x1800c13be`: `ZipEditor::Create(trackingPackageStream.Get(), workingDirectory, zipEditor)`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::UpdateManifestInPlaceUnencrypted(
        Appx::Packaging *this,
        struct IStream *a2,
        struct IStream *a3,
        const unsigned __int16 *a4,
        bool a5)
{
  char v6; // si
  int v9; // eax
  int v10; // ebx
  unsigned __int64 *v11; // r8
  int StreamSize; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  struct IAppxPackageReader *v16; // rdi
  HRESULT (__stdcall *GetFootprintFile)(IAppxPackageReader *, APPX_FOOTPRINT_FILE_TYPE, IAppxFile **); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, struct IStream **); // rbx
  int v21; // eax
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  _BOOL8 v24; // r8
  int v25; // eax
  __int64 v26; // rdx
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  void *v29; // rcx
  int v30; // eax
  void *v31; // rcx
  int v32; // eax
  Appx::Packaging::ZipLocalFileHeader *v33; // rbx
  int FirstFileItem; // edi
  __int64 v35; // rdx
  unsigned int v36; // edx
  Appx::Packaging::ZipFileItemEnumerator *v37; // rcx
  bool HasCurrent; // al
  PCNZCH *v39; // rdi
  struct IStream **v40; // r9
  __int64 v41; // rdx
  __int64 v42; // rdx
  int v43; // esi
  __int64 v44; // r14
  Appx::Packaging::BlockMap::BlockMapXmlWriter *v45; // r15
  int started; // esi
  __int64 v47; // rdx
  unsigned int v48; // edx
  Appx::Packaging::ZipFileItemEnumerator *v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rdx
  unsigned int v52; // edx
  Appx::Packaging::ZipLocalFileHeader *v53; // rcx
  unsigned int v54; // edx
  Appx::Packaging::ZipLocalFileHeader *v55; // rcx
  __int64 v56; // rdx
  int v57; // eax
  unsigned int v58; // edx
  Appx::Packaging::ZipFileItemEnumerator *v59; // rcx
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  bool v63[8]; // [rsp+40h] [rbp-C0h] BYREF
  Appx::Packaging::ZipFileItemEnumerator *v64; // [rsp+48h] [rbp-B8h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v65; // [rsp+50h] [rbp-B0h] BYREF
  Appx::Packaging *v66; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v67; // [rsp+60h] [rbp-A0h] BYREF
  Appx::Packaging::ZipLocalFileHeader *v68; // [rsp+68h] [rbp-98h] BYREF
  struct IAppxPackageReader *v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  struct Appx::Packaging::ZipFileItem *v71; // [rsp+80h] [rbp-80h] BYREF
  struct Appx::Packaging::ZipFileItemEnumerator *v72; // [rsp+88h] [rbp-78h] BYREF
  char v73; // [rsp+90h] [rbp-70h]
  struct IStream *v74; // [rsp+A0h] [rbp-60h] BYREF
  void *v75; // [rsp+A8h] [rbp-58h] BYREF
  struct IAppxManifestReader *v76; // [rsp+B0h] [rbp-50h] BYREF
  struct IStream *v77; // [rsp+B8h] [rbp-48h] BYREF
  Appx::Packaging::ZipFileItem *v78; // [rsp+C0h] [rbp-40h] BYREF
  int v79; // [rsp+CCh] [rbp-34h]
  _QWORD v80[42]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v81[42]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v82[42]; // [rsp+370h] [rbp+270h] BYREF
  _BYTE v83[336]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v84[336]; // [rsp+610h] [rbp+510h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+6A8h]

  v77 = 0;
  v6 = (char)a4;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
  v9 = CreatePerfLoggingStream(this, L"package", &v77);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x668,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v9,
      lpString2);
    goto LABEL_94;
  }
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v80);
  v80[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80,
    L"Appx::Packaging::UpdateManifestInPlaceUnencrypted");
  PerfLoggerDetails::PerfLoggerGlobals::BeginStack(&qword_180169AD0, v63, v80);
  v65 = 0;
  v78 = 0;
  StreamSize = Appx::Packaging::GetStreamSize(a2, (struct IStream *)&v78, v11);
  v10 = StreamSize;
  if ( StreamSize < 0 )
  {
    v13 = (unsigned int)StreamSize;
    v14 = 1647;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)v13,
      lpString2);
LABEL_6:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
    goto LABEL_94;
  }
  if ( (unsigned __int64)v78 > 0x7FFFFFFF )
  {
    v10 = -2147024809;
    v14 = 1649;
    v13 = 2147942487LL;
    goto LABEL_5;
  }
  v69 = 0;
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v81);
  v81[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81,
    L"Consumption::AppxPackageReader::Create(trackingPackageStream.Get(), false, &packageReader)");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v81);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
  v15 = Appx::Packaging::Consumption::AppxPackageReader::Create(v77, 0, 0, &v69);
  v10 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x677,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v15,
      lpString2);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81);
LABEL_11:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
    goto LABEL_6;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81);
  v16 = v69;
  v70 = 0;
  GetFootprintFile = v69->lpVtbl->GetFootprintFile;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
  v18 = ((__int64 (__fastcall *)(struct IAppxPackageReader *, __int64, __int64 *))GetFootprintFile)(v16, 1, &v70);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v18,
      lpString2);
LABEL_14:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
    goto LABEL_11;
  }
  v19 = v70;
  v74 = 0;
  v20 = *(__int64 (__fastcall **)(__int64, struct IStream **))(*(_QWORD *)v70 + 56LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  v21 = v20(v19, &v74);
  v10 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v21,
      lpString2);
LABEL_17:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
    goto LABEL_14;
  }
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[92]>((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v83);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  v23 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(v74, v22, &v65);
  v10 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x680,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v23,
      lpString2);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
    goto LABEL_17;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
  if ( v6 )
  {
    v76 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
    LOBYTE(v24) = 1;
    v25 = Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(a2, &v76, v24, 0);
    v10 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x685,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v25,
        lpString2);
LABEL_23:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
      goto LABEL_17;
    }
    v71 = (struct Appx::Packaging::ZipFileItem *)&v75;
    v75 = 0;
    v72 = 0;
    v73 = 1;
    v10 = Appx::Packaging::CreateFileMapFromBlockMapReader(v65, &v72);
    wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short const *,unsigned short const *>,wistd::default_delete<Common::GenericMap<unsigned short const *,unsigned short const *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short const *,unsigned short const *>,wistd::default_delete<Common::GenericMap<unsigned short const *,unsigned short const *>>>>(&v71);
    if ( v10 < 0 )
    {
      v27 = (unsigned int)v10;
      v28 = 1672;
      goto LABEL_26;
    }
    LOBYTE(v26) = a5;
    v30 = Appx::Packaging::PackageValidator::Validate(v76, v26, (struct _RTL_AVL_TABLE *)v75);
    v10 = v30;
    if ( v30 < 0 )
    {
      v27 = (unsigned int)v30;
      v28 = 1675;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)v27,
        lpString2);
      v29 = v75;
      v75 = 0;
      if ( v29 )
        Common::GenericMap<unsigned short const *,unsigned short const *>::`scalar deleting destructor'(v29);
      goto LABEL_23;
    }
    v31 = v75;
    v75 = 0;
    if ( v31 )
      Common::GenericMap<unsigned short const *,unsigned short const *>::`scalar deleting destructor'(v31);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v69);
  v68 = 0;
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v82);
  v82[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82,
    L"ZipEditor::Create(trackingPackageStream.Get(), workingDirectory, zipEditor)");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v82);
  v32 = Appx::Packaging::ZipEditor::Create(v77, a3, &v68);
  v10 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x690,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v32,
      lpString2);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82);
    Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v68);
    goto LABEL_6;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82);
  v33 = v68;
  v71 = (struct Appx::Packaging::ZipFileItem *)&v64;
  v64 = 0;
  v72 = 0;
  v73 = 1;
  FirstFileItem = Appx::Packaging::ZipEditor::GetFirstFileItem(v68, &v72);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::ZipFileItemEnumerator,wistd::default_delete<Appx::Packaging::ZipFileItemEnumerator>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::ZipFileItemEnumerator,wistd::default_delete<Appx::Packaging::ZipFileItemEnumerator>>>(&v71);
  if ( FirstFileItem < 0 )
  {
    v35 = 1683;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)FirstFileItem,
      lpString2);
    goto LABEL_38;
  }
  HasCurrent = Appx::Packaging::ZipFileItemEnumerator::HasCurrent(v64);
  v63[0] = HasCurrent;
  while ( HasCurrent )
  {
    v71 = 0;
    FirstFileItem = Appx::Packaging::ZipFileItemEnumerator::GetCurrent(v64, &v71);
    if ( FirstFileItem < 0 )
    {
      v35 = 1688;
      goto LABEL_37;
    }
    v39 = (PCNZCH *)v71;
    if ( CompareStringA(0x7Fu, 1u, *((PCNZCH *)v71 + 8), -1, "AppxBlockMap.xml", -1) == 2
      || CompareStringA(0x7Fu, 1u, v39[8], -1, "AppxManifest.xml", -1) == 2
      || CompareStringA(0x7Fu, 1u, v39[8], -1, "AppxSignature.p7x", -1) == 2
      || CompareStringA(0x7Fu, 1u, v39[8], -1, "AppxMetadata/CodeIntegrity.cat", -1) == 2 )
    {
      FirstFileItem = Appx::Packaging::ZipEditor::RemoveFileItem(v33, (struct Appx::Packaging::ZipFileItem *)v39);
      if ( FirstFileItem < 0 )
      {
        v35 = 1698;
        goto LABEL_37;
      }
    }
    Appx::Packaging::ZipFileItemEnumerator::MoveNext(v64, v63);
    HasCurrent = v63[0];
  }
  v66 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
  FirstFileItem = Appx::Packaging::CreateTempFileStream(a3, L"TempAppxBlockMap", (const unsigned __int16 *)&v66, v40);
  if ( FirstFileItem < 0 )
  {
    v41 = 1704;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)FirstFileItem,
      lpString2);
LABEL_55:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
LABEL_38:
    v37 = v64;
    v64 = 0;
    if ( v37 )
      Appx::Packaging::ZipFileItemEnumerator::`scalar deleting destructor'(v37, v36);
    Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v33);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
    v10 = FirstFileItem;
    goto LABEL_94;
  }
  v67 = 0;
  v71 = (struct Appx::Packaging::ZipFileItem *)*((_QWORD *)v65 + 8);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
  FirstFileItem = Microsoft::WRL::Details::MakeAndInitialize<Appx::Packaging::BlockMapWriterWithBlockHashingListener,Appx::Packaging::BlockMapWriterWithBlockHashingListener,Appx::Packaging::HashProvider *>(
                    &v67,
                    &v71);
  if ( FirstFileItem < 0 )
  {
    v42 = 1709;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v42,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)FirstFileItem,
      lpString2);
LABEL_59:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    goto LABEL_55;
  }
  v43 = *((_DWORD *)v65 + 4);
  v44 = *((_QWORD *)v65 + 3);
  v45 = (Appx::Packaging::BlockMap::BlockMapXmlWriter *)(v67 + 24);
  v71 = v66;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v71);
  started = Appx::Packaging::BlockMap::BlockMapXmlWriter::StartBlockMap((_DWORD)v45, (unsigned int)&v71, v44, v43, 0);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v71);
  if ( started < 0 )
  {
    v47 = 1712;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      lpString2a);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
    v49 = v64;
    v64 = 0;
    if ( v49 )
      Appx::Packaging::ZipFileItemEnumerator::`scalar deleting destructor'(v49, v48);
    Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v33);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
    v10 = started;
    goto LABEL_94;
  }
  v71 = (struct Appx::Packaging::ZipFileItem *)Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal;
  HIDWORD(v72) = v79;
  LODWORD(v72) = 0;
  started = Appx::Packaging::DuplicateFilesIntoNewBlockmap(v45);
  if ( started < 0 )
  {
    v47 = 1714;
    goto LABEL_62;
  }
  v71 = (struct Appx::Packaging::ZipFileItem *)Appx::Packaging::BlockMap::AppxBlockMapReader::GetIgnoredFilesInternal;
  HIDWORD(v72) = v79;
  LODWORD(v72) = 0;
  started = Appx::Packaging::DuplicateFilesIntoNewBlockmap(v45);
  if ( started < 0 )
  {
    v47 = 1715;
    goto LABEL_62;
  }
  started = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(
              v45,
              L"AppxManifest.xml",
              (unsigned __int64)v78,
              0x2Eu,
              0,
              0x10000u);
  if ( started < 0 )
  {
    v47 = 1718;
    goto LABEL_62;
  }
  started = Appx::Packaging::SetStreamPosition(a2, 0);
  if ( started < 0 )
  {
    v47 = 1720;
    goto LABEL_62;
  }
  v78 = 0;
  lpString2 = (int)a2;
  FirstFileItem = Appx::Packaging::ZipEditor::AddFileItem(v33, v50, "AppxManifest.xml");
  if ( FirstFileItem < 0 )
  {
    v42 = 1722;
    goto LABEL_58;
  }
  v71 = (struct Appx::Packaging::ZipFileItem *)&v68;
  v68 = 0;
  v72 = 0;
  v73 = 1;
  FirstFileItem = Appx::Packaging::ZipFileItem::GetLocalFileHeader(v78, &v72);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::ZipLocalFileHeader,wistd::default_delete<Appx::Packaging::ZipLocalFileHeader>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::ZipLocalFileHeader,wistd::default_delete<Appx::Packaging::ZipLocalFileHeader>>>(&v71);
  if ( FirstFileItem < 0 )
  {
    v51 = 1726;
    goto LABEL_77;
  }
  FirstFileItem = Appx::Packaging::BlockMap::BlockMapXmlWriter::CloseFile(v45, 0, 0);
  if ( FirstFileItem < 0 )
  {
    v51 = 1730;
    goto LABEL_77;
  }
  FirstFileItem = Appx::Packaging::BlockMap::BlockMapXmlWriter::EndBlockMap(v45);
  if ( FirstFileItem < 0 )
  {
    v51 = 1732;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v51,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)FirstFileItem,
      (int)a2);
    v53 = v68;
    v68 = 0;
    if ( v53 )
      Appx::Packaging::ZipLocalFileHeader::`scalar deleting destructor'(v53, v52);
    goto LABEL_59;
  }
  v55 = v68;
  v68 = 0;
  if ( v55 )
    Appx::Packaging::ZipLocalFileHeader::`scalar deleting destructor'(v55, v54);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
  FirstFileItem = Appx::Packaging::SetStreamPosition(v66, 0);
  if ( FirstFileItem < 0 )
  {
    v41 = 1736;
    goto LABEL_54;
  }
  lpString2 = (int)v66;
  FirstFileItem = Appx::Packaging::ZipEditor::AddFileItem(v33, v56, "AppxBlockMap.xml");
  if ( FirstFileItem < 0 )
  {
    v41 = 1737;
    goto LABEL_54;
  }
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84,
    L"zipEditor->Flush(ZipEditorBehaviorFlags::OptimizeForTailEdits)");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v63, v84);
  v57 = Appx::Packaging::ZipEditor::Flush(v33);
  FirstFileItem = v57;
  if ( v57 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6CB,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v57,
      lpString2);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
    goto LABEL_55;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v66);
  v59 = v64;
  v64 = 0;
  if ( v59 )
    Appx::Packaging::ZipFileItemEnumerator::`scalar deleting destructor'(v59, v58);
  Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(v33);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v63);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
  v10 = 0;
LABEL_94:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v77);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800c0f54  mov     [rsp-8+arg_18], rbx
0x1800c0f59  push    rbp
0x1800c0f5a  push    rsi
0x1800c0f5b  push    rdi
0x1800c0f5c  push    r12
0x1800c0f5e  push    r13
0x1800c0f60  push    r14
0x1800c0f62  push    r15
0x1800c0f64  lea     rbp, [rsp-670h]
0x1800c0f6c  sub     rsp, 770h
0x1800c0f73  mov     rax, cs:__security_cookie
0x1800c0f7a  xor     rax, rsp
0x1800c0f7d  mov     [rbp+6A0h+var_40], rax
0x1800c0f84  mov     rbx, rcx
0x1800c0f87  xor     r13d, r13d
0x1800c0f8a  lea     rcx, [rbp+6A0h+var_6E8]
0x1800c0f8e  mov     [rbp+6A0h+var_6E8], r13
0x1800c0f92  mov     sil, r9b
0x1800c0f95  mov     r14, r8
0x1800c0f98  mov     r12, rdx
0x1800c0f9b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0fa0  lea     r8, [rbp+6A0h+var_6E8]; struct IStream **
0x1800c0fa4  mov     rcx, rbx; struct IStream *
0x1800c0fa7  lea     rdx, aPackage; "package"
0x1800c0fae  call    ?CreatePerfLoggingStream@@YAJPEAUIStream@@PEBGPEAPEAU1@@Z; CreatePerfLoggingStream(IStream *,ushort const *,IStream * *)
0x1800c0fb3  mov     ebx, eax
0x1800c0fb5  test    eax, eax
0x1800c0fb7  jns     short loc_1800C0FD9
0x1800c0fb9  mov     rcx, [rbp+6A8h]; this
0x1800c0fc0  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c0fc7  mov     r9d, eax; char *
0x1800c0fca  mov     edx, 668h; void *
0x1800c0fcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0fd4  jmp     loc_1800C1A58
0x1800c0fd9  lea     rcx, [rbp+6A0h+var_6D0]; struct wil::details::IFailureCallback *
0x1800c0fdd  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c0fe2  lea     rdi, ??_7TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@6B@; const PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable'
0x1800c0fe9  lea     rdx, aAppxPackagingU_0; "Appx::Packaging::UpdateManifestInPlaceU"...
0x1800c0ff0  mov     [rbp+6A0h+var_6D0], rdi
0x1800c0ff4  lea     rcx, [rbp+6A0h+var_6D0]; this
0x1800c0ff8  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c0ffd  lea     r15, qword_180169AD0
0x1800c1004  mov     rcx, r15
0x1800c1007  lea     r8, [rbp+6A0h+var_6D0]
0x1800c100b  lea     rdx, [rsp+7A0h+var_760]
0x1800c1010  call    ?BeginStack@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUStackRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::BeginStack(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c1015  lea     rdx, [rbp+6A0h+var_6E0]; struct IStream *
0x1800c1019  mov     [rsp+7A0h+var_750], r13
0x1800c101e  mov     rcx, r12; this
0x1800c1021  mov     [rbp+6A0h+var_6E0], r13
0x1800c1025  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x1800c102a  mov     ebx, eax
0x1800c102c  test    eax, eax
0x1800c102e  jns     short loc_1800C106D
0x1800c1030  mov     r9d, eax; char *
0x1800c1033  mov     edx, 66Fh; void *
0x1800c1038  mov     rcx, [rbp+6A8h]; this
0x1800c103f  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c104b  lea     rcx, [rsp+7A0h+var_750]
0x1800c1050  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1055  lea     rcx, [rsp+7A0h+var_760]; this
0x1800c105a  call    ??1StackRemover@PerfLoggerGlobals@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover(void)
0x1800c105f  lea     rcx, [rbp+6A0h+var_6D0]; this
0x1800c1063  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1068  jmp     loc_1800C1A58
0x1800c106d  cmp     [rbp+6A0h+var_6E0], 7FFFFFFFh
0x1800c1075  jbe     short loc_1800C1086
0x1800c1077  mov     ebx, 80070057h
0x1800c107c  mov     edx, 671h
0x1800c1081  mov     r9d, ebx
0x1800c1084  jmp     short loc_1800C1038
0x1800c1086  mov     rcx, r15; this
0x1800c1089  mov     [rsp+7A0h+var_730], r13
0x1800c108e  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c1093  lea     rcx, [rbp+6A0h+var_580]; struct wil::details::IFailureCallback *
0x1800c109a  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c109f  lea     rdx, aConsumptionApp; "Consumption::AppxPackageReader::Create("...
0x1800c10a6  mov     [rbp+6A0h+var_580], rdi
0x1800c10ad  lea     rcx, [rbp+6A0h+var_580]; this
0x1800c10b4  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c10b9  lea     r8, [rbp+6A0h+var_580]
0x1800c10c0  mov     rcx, r15
0x1800c10c3  lea     rdx, [rsp+7A0h+var_760]
0x1800c10c8  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c10cd  lea     rcx, [rsp+7A0h+var_730]
0x1800c10d2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c10d7  mov     rcx, [rbp+6A0h+var_6E8]; struct IStream *
0x1800c10db  lea     r9, [rsp+7A0h+var_730]; struct IAppxPackageReader **
0x1800c10e0  xor     r8d, r8d; unsigned __int16 *
0x1800c10e3  xor     edx, edx; bool
0x1800c10e5  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,IAppxPackageReader * *)
0x1800c10ea  mov     ebx, eax
0x1800c10ec  test    eax, eax
0x1800c10ee  jns     short loc_1800C112E
0x1800c10f0  mov     rcx, [rbp+6A8h]; this
0x1800c10f7  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c10fe  mov     r9d, eax; char *
0x1800c1101  mov     edx, 677h; void *
0x1800c1106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c110b  mov     rcx, r15; this
0x1800c110e  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1113  lea     rcx, [rbp+6A0h+var_580]; this
0x1800c111a  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c111f  lea     rcx, [rsp+7A0h+var_730]
0x1800c1124  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1129  jmp     loc_1800C104B
0x1800c112e  mov     rcx, r15; this
0x1800c1131  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1136  lea     rcx, [rbp+6A0h+var_580]; this
0x1800c113d  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1142  mov     rdi, [rsp+7A0h+var_730]
0x1800c1147  lea     rcx, [rsp+7A0h+var_728]
0x1800c114c  mov     [rsp+7A0h+var_728], r13
0x1800c1151  mov     rax, [rdi]
0x1800c1154  mov     rbx, [rax+20h]
0x1800c1158  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c115d  lea     r8, [rsp+7A0h+var_728]
0x1800c1162  mov     edx, 1
0x1800c1167  mov     rcx, rdi
0x1800c116a  mov     rax, rbx
0x1800c116d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1172  mov     ebx, eax
0x1800c1174  test    eax, eax
0x1800c1176  jns     short loc_1800C119F
0x1800c1178  mov     rcx, [rbp+6A8h]; this
0x1800c117f  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1186  mov     r9d, eax; char *
0x1800c1189  mov     edx, 67Bh; void *
0x1800c118e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1193  lea     rcx, [rsp+7A0h+var_728]
0x1800c1198  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c119d  jmp     short loc_1800C111F
0x1800c119f  mov     rdi, [rsp+7A0h+var_728]
0x1800c11a4  lea     rcx, [rbp+6A0h+var_700]
0x1800c11a8  mov     [rbp+6A0h+var_700], r13
0x1800c11ac  mov     rax, [rdi]
0x1800c11af  mov     rbx, [rax+38h]
0x1800c11b3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c11b8  lea     rdx, [rbp+6A0h+var_700]
0x1800c11bc  mov     rcx, rdi
0x1800c11bf  mov     rax, rbx
0x1800c11c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c11c7  mov     ebx, eax
0x1800c11c9  test    eax, eax
0x1800c11cb  jns     short loc_1800C11F3
0x1800c11cd  mov     rcx, [rbp+6A8h]; this
0x1800c11d4  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c11db  mov     r9d, eax; char *
0x1800c11de  mov     edx, 67Eh; void *
0x1800c11e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c11e8  lea     rcx, [rbp+6A0h+var_700]
0x1800c11ec  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c11f1  jmp     short loc_1800C1193
0x1800c11f3  mov     rcx, r15; this
0x1800c11f6  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c11fb  lea     rcx, [rbp+6A0h+var_2E0]; this
0x1800c1202  call    ??$Start@AEAY0FM@$$CBG@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@SA?AV012@AEAY0FM@$$CBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<ushort const (&)[92]>(ushort const (&)[92])
0x1800c1207  lea     r8, [rbp+6A0h+var_2E0]
0x1800c120e  mov     rcx, r15
0x1800c1211  lea     rdx, [rsp+7A0h+var_760]
0x1800c1216  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c121b  lea     rcx, [rsp+7A0h+var_750]
0x1800c1220  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1225  mov     rcx, [rbp+6A0h+var_700]; struct IStream *
0x1800c1229  lea     r8, [rsp+7A0h+var_750]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x1800c122e  call    ?Create@AppxBlockMapReader@BlockMap@Packaging@Appx@@SAJPEAUIStream@@PEBGPEAPEAV1234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::Create(IStream *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x1800c1233  mov     ebx, eax
0x1800c1235  test    eax, eax
0x1800c1237  jns     short loc_1800C126D
0x1800c1239  mov     rcx, [rbp+6A8h]; this
0x1800c1240  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1247  mov     r9d, eax; char *
0x1800c124a  mov     edx, 680h; void *
0x1800c124f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1254  mov     rcx, r15; this
0x1800c1257  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c125c  lea     rcx, [rbp+6A0h+var_2E0]; this
0x1800c1263  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1268  jmp     loc_1800C11E8
0x1800c126d  mov     rcx, r15; this
0x1800c1270  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1275  lea     rcx, [rbp+6A0h+var_2E0]; this
0x1800c127c  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1281  test    sil, sil
0x1800c1284  jz      loc_1800C137C
0x1800c128a  lea     rcx, [rbp+6A0h+var_6F0]
0x1800c128e  mov     [rbp+6A0h+var_6F0], r13
0x1800c1292  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1297  xor     r9d, r9d; unsigned __int16 **
0x1800c129a  lea     rdx, [rbp+6A0h+var_6F0]; struct IAppxManifestReader **
0x1800c129e  mov     rcx, r12; struct IStream *
0x1800c12a1  lea     esi, [r9+1]
0x1800c12a5  mov     r8b, sil; bool
0x1800c12a8  call    ?Create@AppxManifestReaderImpl@Manifest@Packaging@Appx@@SAJPEAUIStream@@PEAPEAUIAppxManifestReader@@_NPEAPEAG@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(IStream *,IAppxManifestReader * *,bool,ushort * *)
0x1800c12ad  mov     ebx, eax
0x1800c12af  test    eax, eax
0x1800c12b1  jns     short loc_1800C12DC
0x1800c12b3  mov     rcx, [rbp+6A8h]; this
0x1800c12ba  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c12c1  mov     r9d, eax; char *
0x1800c12c4  mov     edx, 685h; void *
0x1800c12c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c12ce  lea     rcx, [rbp+6A0h+var_6F0]
0x1800c12d2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c12d7  jmp     loc_1800C11E8
0x1800c12dc  mov     rcx, [rsp+7A0h+var_750]
0x1800c12e1  lea     rax, [rbp+6A0h+var_6F8]
0x1800c12e5  lea     rdx, [rbp+6A0h+var_718]
0x1800c12e9  mov     [rbp+6A0h+var_720], rax
0x1800c12ed  mov     [rbp+6A0h+var_6F8], r13
0x1800c12f1  mov     [rbp+6A0h+var_718], r13
0x1800c12f5  mov     [rbp+6A0h+var_710], sil
0x1800c12f9  call    ?CreateFileMapFromBlockMapReader@Packaging@Appx@@YAJPEAVAppxBlockMapReader@BlockMap@12@PEAPEAV?$GenericMap@PEBGPEBG@Common@@@Z; Appx::Packaging::CreateFileMapFromBlockMapReader(Appx::Packaging::BlockMap::AppxBlockMapReader *,Common::GenericMap<ushort const *,ushort const *> * *)
0x1800c12fe  lea     rcx, [rbp+6A0h+var_720]
0x1800c1302  mov     ebx, eax
0x1800c1304  call    ??1?$out_param_t@V?$unique_ptr@V?$GenericMap@PEBGPEBG@Common@@U?$default_delete@V?$GenericMap@PEBGPEBG@Common@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<ushort const *,ushort const *>,wistd::default_delete<Common::GenericMap<ushort const *,ushort const *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<ushort const *,ushort const *>,wistd::default_delete<Common::GenericMap<ushort const *,ushort const *>>>>(void)
0x1800c1309  test    ebx, ebx
0x1800c130b  jns     short loc_1800C133C
0x1800c130d  mov     r9d, ebx; char *
0x1800c1310  mov     edx, 688h; void *
0x1800c1315  mov     rcx, [rbp+6A8h]; this
0x1800c131c  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1328  mov     rcx, [rbp+6A0h+var_6F8]; void *
0x1800c132c  mov     [rbp+6A0h+var_6F8], r13
0x1800c1330  test    rcx, rcx
0x1800c1333  jz      short loc_1800C12CE
0x1800c1335  call    ??_G?$GenericMap@PEBGPEBG@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort const *,ushort const *>::`scalar deleting destructor'(uint)
0x1800c133a  jmp     short loc_1800C12CE
0x1800c133c  mov     r8, [rbp+6A0h+var_6F8]
0x1800c1340  mov     dl, [rbp+6A0h+arg_20]
0x1800c1346  mov     rcx, [rbp+6A0h+var_6F0]
0x1800c134a  call    ?Validate@PackageValidator@Packaging@Appx@@SAJPEAUIAppxManifestReader@@_NAEBV?$GenericMap@PEBGPEBG@Common@@@Z; Appx::Packaging::PackageValidator::Validate(IAppxManifestReader *,bool,Common::GenericMap<ushort const *,ushort const *> const &)
0x1800c134f  mov     ebx, eax
0x1800c1351  test    eax, eax
0x1800c1353  jns     short loc_1800C135F
0x1800c1355  mov     r9d, eax
0x1800c1358  mov     edx, 68Bh
0x1800c135d  jmp     short loc_1800C1315
0x1800c135f  mov     rcx, [rbp+6A0h+var_6F8]; void *
0x1800c1363  mov     [rbp+6A0h+var_6F8], r13
0x1800c1367  test    rcx, rcx
0x1800c136a  jz      short loc_1800C1371
0x1800c136c  call    ??_G?$GenericMap@PEBGPEBG@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort const *,ushort const *>::`scalar deleting destructor'(uint)
0x1800c1371  lea     rcx, [rbp+6A0h+var_6F0]
0x1800c1375  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c137a  jmp     short loc_1800C1381
0x1800c137c  mov     esi, 1
0x1800c1381  lea     rcx, [rbp+6A0h+var_700]
0x1800c1385  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c138a  lea     rcx, [rsp+7A0h+var_728]
0x1800c138f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c1394  lea     rcx, [rsp+7A0h+var_730]
0x1800c1399  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c139e  mov     rcx, r15; this
0x1800c13a1  mov     [rsp+7A0h+var_738], r13
0x1800c13a6  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c13ab  lea     rcx, [rbp+6A0h+var_430]; struct wil::details::IFailureCallback *
0x1800c13b2  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c13b7  lea     rax, ??_7TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@6B@; const PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable'
0x1800c13be  lea     rdx, aZipeditorCreat; "ZipEditor::Create(trackingPackageStream"...
0x1800c13c5  mov     [rbp+6A0h+var_430], rax
0x1800c13cc  lea     rcx, [rbp+6A0h+var_430]; this
0x1800c13d3  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c13d8  lea     r8, [rbp+6A0h+var_430]
0x1800c13df  mov     rcx, r15
0x1800c13e2  lea     rdx, [rsp+7A0h+var_760]
0x1800c13e7  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c13ec  mov     rcx, [rbp+6A0h+var_6E8]
0x1800c13f0  lea     r8, [rsp+7A0h+var_738]
0x1800c13f5  mov     rdx, r14
0x1800c13f8  call    ?Create@ZipEditor@Packaging@Appx@@SAJPEAUIStream@@PEBGAEAV?$AutoPtr@VZipEditor@Packaging@Appx@@$1??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAV123@@Z@Common@@@Z; Appx::Packaging::ZipEditor::Create(IStream *,ushort const *,Common::AutoPtr<Appx::Packaging::ZipEditor,&Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)> &)
0x1800c13fd  mov     ebx, eax
0x1800c13ff  test    eax, eax
0x1800c1401  jns     short loc_1800C1441
0x1800c1403  mov     rcx, [rbp+6A8h]; this
0x1800c140a  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c1411  mov     r9d, eax; char *
0x1800c1414  mov     edx, 690h; void *
0x1800c1419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c141e  mov     rcx, r15; this
0x1800c1421  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1426  lea     rcx, [rbp+6A0h+var_430]; this
0x1800c142d  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1432  mov     rcx, [rsp+7A0h+var_738]; void *
0x1800c1437  call    ??$AutoPtrDeallocate@VZipEditor@Packaging@Appx@@@Common@@YAXPEAVZipEditor@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::ZipEditor>(Appx::Packaging::ZipEditor *)
0x1800c143c  jmp     loc_1800C104B
0x1800c1441  mov     rcx, r15; this
0x1800c1444  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c1449  lea     rcx, [rbp+6A0h+var_430]; this
0x1800c1450  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c1455  mov     rbx, [rsp+7A0h+var_738]
0x1800c145a  lea     rax, [rsp+7A0h+var_758]
0x1800c145f  mov     rcx, rbx; this
0x1800c1462  mov     [rbp+6A0h+var_720], rax
0x1800c1466  lea     rdx, [rbp+6A0h+var_718]; struct Appx::Packaging::ZipFileItemEnumerator **
0x1800c146a  mov     [rsp+7A0h+var_758], r13
0x1800c146f  mov     [rbp+6A0h+var_718], r13
0x1800c1473  mov     [rbp+6A0h+var_710], sil
  ... truncated ...
```
