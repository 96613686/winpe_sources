# Appx::Packaging::UpdateManifestInPlaceEncrypted(IStream *,IStream *,ushort const *,bool,bool)

- ea: `0x1800c021c`
- end: `0x1800c0f4e`
- name: `?UpdateManifestInPlaceEncrypted@Packaging@Appx@@YAJPEAUIStream@@0PEBG_N2@Z`
- size: `3378`
- prototype: `__int64 __fastcall(Appx::Packaging *this, struct IStream *, struct IStream *, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `49`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c2960`

## callees

- `0x1800029e4`
- `0x180005eb8`
- `0x180009eb8`
- `0x1800133fc`
- `0x180020ff0`
- `0x18002cf44`
- `0x180047dcc`
- `0x18005ccf0`
- `0x18007c3d4`
- `0x180081b50`
- `0x180081cdc`
- `0x18008390c`
- `0x180087bec`
- `0x180087cb4`
- `0x1800992a0`
- `0x1800992d0`
- `0x1800ac600`
- `0x1800b6bac`
- `0x1800b6bec`
- `0x1800b6ddc`
- `0x1800b7150`
- `0x1800b7204`
- `0x1800b7264`
- `0x1800b72cc`
- `0x1800b7838`
- `0x1800b78cc`
- `0x1800b7950`
- `0x1800b79cc`
- `0x1800b7a24`
- `0x1800b7ad4`
- `0x1800b993c`
- `0x1800b9b44`
- `0x1800b9cec`
- `0x1800ba85c`
- `0x1800baa40`
- `0x1800bac08`
- `0x1800bc1f4`
- `0x1800bcbb8`
- `0x1800bd4a0`
- `0x1800c021c`
- `0x1800c2a48`
- `0x1800c2fb0`
- `0x1800e61f8`
- `0x1800e9030`
- `0x1800e9184`
- `0x1800eea94`
- `0x1800eeb68`
- `0x1800f9dcc`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x1800c030c`
- `OpcServices!__imp_GetCloneableStream` at `0x1800c030c`

## string_xrefs

- `0x1800c0cbe`: `AppxManifest.xml`
- `0x1800c0d0f`: `AppxManifest.xml`
- `0x1800c0288`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c032a`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c044e`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c04e6`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0570`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0605`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0693`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0796`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0848`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0972`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0a4e`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0b5a`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0c49`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0ce5`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0d9a`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0e87`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800c0702`: `TempAppxBlockMap`
- `0x1800c02b1`: `Appx::Packaging::UpdateManifestInPlaceEncrypted`
- `0x1800c03ee`: `AppxEncryptedPackageEditor::Create(cloneablePackageStream.Get(), wil::out_param(eappxEditor))`
- `0x1800c0912`: `CopyStreamOutOfEditor(eappxEditor.get(), &AppxEncryptedPackageEditor::GetFootersStream, workingDirectory, &footersStream)`
- `0x1800c09ec`: `CopyStreamOutOfEditor(eappxEditor.get(), &AppxEncryptedPackageEditor::GetRawCodeIntegrity, workingDirectory, &rawCIStream)`
- `0x1800c0bb6`: `Production::EncryptedPackageWriterHelper::CreateForEdit(cloneablePackageStream.Get(), nullptr, dummyKeyFromPackage.get(), updatedPackageId.Get(), packageOvewriteStartLocation, blockMapWriter.release(), tempBlockMapStream.Get(), footersStream.Get(), false , wil::out_param(packageWriter))`
- `0x1800c0d53`: `packageWriter->CloseForEdit(rawCIStream.Get())`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::UpdateManifestInPlaceEncrypted(
        Appx::Packaging *this,
        struct IStream *a2,
        struct IStream *a3,
        const unsigned __int16 *a4,
        bool a5)
{
  char v6; // si
  int v9; // eax
  unsigned int v10; // ebx
  struct IStream *v11; // rbx
  int CloneableStream; // edi
  __int64 v13; // rdx
  _BOOL8 v14; // r8
  struct IStream *v15; // r8
  Appx::Packaging::AppxEncryptedPackageEditor *v16; // rcx
  Appx::Packaging::AppxEncryptedPackageEditor *v17; // rdi
  __int64 v18; // rdx
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdx
  void *v25; // rcx
  void *v26; // rcx
  struct IStream **v27; // r9
  Appx::Packaging::BlockMap::BlockMapXmlWriter *v28; // rax
  Appx::Packaging::BlockMap::BlockMapXmlWriter *v29; // r14
  int v30; // edi
  __int64 v31; // rsi
  Appx::Packaging::AppxEncryptedPackageEditor *v32; // rcx
  unsigned int v33; // edx
  __int64 v34; // rdx
  int v35; // eax
  Appx::Packaging::AppxEncryptedPackageEditor *v36; // rax
  int v37; // eax
  Appx::Packaging::AppxEncryptedPackageEditor *v38; // rcx
  unsigned int v39; // edx
  unsigned __int64 v40; // r15
  Appx::Packaging::AppxEncryptedPackageEditor *v41; // rcx
  struct IAppxManifestReader *v42; // rsi
  HRESULT (__stdcall *GetPackageId)(IAppxManifestReader *, IAppxManifestPackageId **); // rdi
  unsigned __int64 v44; // r8
  __int64 v45; // rdx
  unsigned int v46; // edx
  Appx::Packaging::Production::EncryptedPackageWriterHelper *v47; // rcx
  __int64 v48; // rdx
  int v49; // eax
  unsigned int v50; // edx
  Appx::Packaging::Production::EncryptedPackageWriterHelper *v51; // rcx
  unsigned int v52; // edx
  Appx::Packaging::Production::EncryptedPackageWriterHelper *v53; // rcx
  Appx::Packaging::AppxEncryptedPackageEditor *v54; // rcx
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  int *v58; // [rsp+20h] [rbp-E0h]
  _BYTE v59[8]; // [rsp+50h] [rbp-B0h] BYREF
  Appx::Packaging::AppxEncryptedPackageEditor *v60; // [rsp+58h] [rbp-A8h] BYREF
  Appx::Packaging *v61; // [rsp+60h] [rbp-A0h] BYREF
  struct IStream *v62; // [rsp+68h] [rbp-98h] BYREF
  struct IAppxManifestReader *v63; // [rsp+70h] [rbp-90h] BYREF
  struct IStream *v64; // [rsp+78h] [rbp-88h] BYREF
  struct IStream *v65; // [rsp+80h] [rbp-80h] BYREF
  struct APPX_KEY_INFO *v66; // [rsp+88h] [rbp-78h] BYREF
  Appx::Packaging *v67; // [rsp+90h] [rbp-70h] BYREF
  struct Appx::Packaging::BlockMap::AppxBlockMapReader *v68; // [rsp+98h] [rbp-68h] BYREF
  Appx::Packaging::Production::EncryptedPackageWriterHelper *v69; // [rsp+A0h] [rbp-60h] BYREF
  int v70[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct Appx::Packaging::AppxKeyInfo *v71; // [rsp+B8h] [rbp-48h] BYREF
  char v72; // [rsp+C0h] [rbp-40h]
  struct IAppxManifestPackageId *v73; // [rsp+D0h] [rbp-30h] BYREF
  struct IStream *v74; // [rsp+D8h] [rbp-28h] BYREF
  void *v75; // [rsp+E0h] [rbp-20h] BYREF
  struct IStream *v76; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v77; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v78; // [rsp+100h] [rbp+0h]
  char v79; // [rsp+108h] [rbp+8h]
  _QWORD v80[42]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v81[42]; // [rsp+280h] [rbp+180h] BYREF
  _QWORD v82[42]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v83[42]; // [rsp+520h] [rbp+420h] BYREF
  _QWORD v84[42]; // [rsp+670h] [rbp+570h] BYREF
  _BYTE v85[336]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v86[336]; // [rsp+910h] [rbp+810h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AA8h] [rbp+9A8h]

  v76 = 0;
  v6 = (char)a4;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  v9 = CreatePerfLoggingStream(this, L"package", &v76);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x736,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v9,
      v56);
    goto LABEL_94;
  }
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v80);
  v80[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80,
    L"Appx::Packaging::UpdateManifestInPlaceEncrypted");
  PerfLoggerDetails::PerfLoggerGlobals::BeginStack(&qword_180169AD0, v59, v80);
  v11 = 0;
  v63 = 0;
  v64 = 0;
  v66 = 0;
  v62 = 0;
  v65 = 0;
  v61 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
  CloneableStream = GetCloneableStream(v76, &v61);
  if ( CloneableStream < 0 )
  {
    v13 = 1861;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v56);
LABEL_6:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
LABEL_7:
    wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>::reset(&v66, 0);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
    PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v59);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
    v10 = CloneableStream;
    goto LABEL_94;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
  LOBYTE(v14) = 1;
  CloneableStream = Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(a2, &v63, v14, 0);
  if ( CloneableStream < 0 )
  {
    v13 = 1863;
    goto LABEL_5;
  }
  CloneableStream = Appx::Packaging::VerifyFileEncryptionSettings(v61, a2, v15);
  if ( CloneableStream < 0 )
  {
    v13 = 1868;
    goto LABEL_5;
  }
  v60 = 0;
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[63]>(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85,
    L"AppxEncryptedPackageEditor::Create(cloneablePackageStream.Get(), wil::out_param(eappxEditor))");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v85);
  *(_QWORD *)v70 = &v60;
  v71 = 0;
  v72 = 1;
  CloneableStream = Appx::Packaging::AppxEncryptedPackageEditor::Create(v61, &v71);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::AppxEncryptedPackageEditor,wistd::default_delete<Appx::Packaging::AppxEncryptedPackageEditor>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::AppxEncryptedPackageEditor,wistd::default_delete<Appx::Packaging::AppxEncryptedPackageEditor>>>(v70);
  if ( CloneableStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v56);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85);
    goto LABEL_14;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v85);
  v17 = v60;
  v67 = 0;
  v74 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  CloneableStream = Appx::Packaging::AppxEncryptedPackageEditor::GetEncryptedBlockMap(v17, &v74);
  if ( CloneableStream < 0 )
  {
    v18 = 1877;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v56);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
LABEL_19:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
LABEL_14:
    v16 = v60;
    v60 = 0;
    if ( v16 )
      Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(v16, 1u);
    goto LABEL_6;
  }
  DWORD1(v77) = 0;
  CloneableStream = Appx::Packaging::AppxEncryptedPackageEditor::GetFooterByFileId(
                      v60,
                      *(_QWORD *)(*((_QWORD *)v60 + 4) + 80LL),
                      (struct Appx::Packaging::EncryptedAppxFooter *)&v77);
  if ( CloneableStream < 0 )
  {
    v18 = 1880;
    goto LABEL_18;
  }
  if ( DWORD1(v77) )
  {
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    CloneableStream = Appx::Packaging::ZipInflator::InflateToTempFileStream(v74, (const unsigned __int16 *)a3, &v67);
    if ( CloneableStream < 0 )
    {
      v18 = 1891;
      goto LABEL_18;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IStream>::operator=(&v67, &v74);
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v74);
  v68 = 0;
  CloneableStream = Appx::Packaging::SetStreamPosition(v67, 0, v19);
  if ( CloneableStream < 0 )
  {
    v20 = 1896;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v56);
LABEL_27:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    goto LABEL_19;
  }
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<unsigned short const (&)[92]>((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86);
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v86);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  v22 = Appx::Packaging::BlockMap::AppxBlockMapReader::Create(v67, v21, &v68);
  CloneableStream = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x769,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v22,
      v56);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86);
    goto LABEL_27;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v86);
  if ( v6 )
  {
    *(_QWORD *)v70 = &v75;
    v75 = 0;
    v71 = 0;
    v72 = 1;
    CloneableStream = Appx::Packaging::CreateFileMapFromBlockMapReader(v68, &v71);
    wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short const *,unsigned short const *>,wistd::default_delete<Common::GenericMap<unsigned short const *,unsigned short const *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<unsigned short const *,unsigned short const *>,wistd::default_delete<Common::GenericMap<unsigned short const *,unsigned short const *>>>>(v70);
    if ( CloneableStream < 0 )
    {
      v24 = 1902;
      goto LABEL_35;
    }
    LOBYTE(v23) = a5;
    CloneableStream = Appx::Packaging::PackageValidator::Validate(v63, v23, v75);
    if ( CloneableStream < 0 )
    {
      v24 = 1905;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)CloneableStream,
        v56);
      v25 = v75;
      v75 = 0;
      if ( v25 )
        Common::GenericMap<unsigned short const *,unsigned short const *>::`scalar deleting destructor'(v25);
      goto LABEL_27;
    }
    v26 = v75;
    v75 = 0;
    if ( v26 )
      Common::GenericMap<unsigned short const *,unsigned short const *>::`scalar deleting destructor'(v26);
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
  CloneableStream = Appx::Packaging::CreateTempFileStream(a3, L"TempAppxBlockMap", (const unsigned __int16 *)&v62, v27);
  if ( CloneableStream < 0 )
  {
    v20 = 1909;
    goto LABEL_26;
  }
  v28 = (Appx::Packaging::BlockMap::BlockMapXmlWriter *)operator new(
                                                          0x88u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
  if ( !v28
    || (v29 = (Appx::Packaging::BlockMap::BlockMapXmlWriter *)Appx::Packaging::BlockMap::BlockMapXmlWriter::BlockMapXmlWriter(v28)) == 0 )
  {
    v10 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x778,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)0x8007000ELL,
      v56);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    v54 = v60;
    v60 = 0;
    if ( v54 )
      Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(v54, 1u);
    goto LABEL_92;
  }
  v30 = *((_DWORD *)v68 + 4);
  v31 = *((_QWORD *)v68 + 3);
  *(_QWORD *)v70 = v62;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(v70);
  CloneableStream = Appx::Packaging::BlockMap::BlockMapXmlWriter::StartBlockMap(
                      (_DWORD)v29,
                      (unsigned int)v70,
                      v31,
                      v30,
                      1);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v70);
  if ( CloneableStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x779,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v57);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    v32 = v60;
    v60 = 0;
    if ( !v32 )
    {
LABEL_48:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v29, v33);
      goto LABEL_7;
    }
LABEL_47:
    Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(v32, 1u);
    goto LABEL_48;
  }
  *(_QWORD *)v70 = &Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal;
  LODWORD(v71) = 0;
  CloneableStream = Appx::Packaging::DuplicateFilesIntoNewBlockmap(v29);
  if ( CloneableStream < 0 )
  {
    v34 = 1915;
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v57);
    goto LABEL_52;
  }
  *(_QWORD *)v70 = &Appx::Packaging::BlockMap::AppxBlockMapReader::GetIgnoredFilesInternal;
  LODWORD(v71) = 0;
  CloneableStream = Appx::Packaging::DuplicateFilesIntoNewBlockmap(v29);
  if ( CloneableStream < 0 )
  {
    v34 = 1916;
    goto LABEL_51;
  }
  *(_QWORD *)v70 = &v66;
  v71 = 0;
  v72 = 1;
  CloneableStream = Appx::Packaging::AppxKeyInfo::Create(
                      *((const struct Appx::Packaging::EncryptedAppxHeader **)v60 + 4),
                      &v71);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>>(v70);
  if ( CloneableStream < 0 )
  {
    v34 = 1920;
    goto LABEL_51;
  }
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v81);
  v81[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81,
    L"CopyStreamOutOfEditor(eappxEditor.get(), &AppxEncryptedPackageEditor::GetFootersStream, workingDirectory, &footersStream)");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v81);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  v35 = Appx::Packaging::CopyStreamOutOfEditor(
          v60,
          Appx::Packaging::AppxEncryptedPackageEditor::GetFootersStream,
          a3,
          &v65);
  CloneableStream = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x783,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v35,
      v57);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81);
LABEL_52:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
    v32 = v60;
    v60 = 0;
    if ( !v32 )
      goto LABEL_48;
    goto LABEL_47;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v81);
  v36 = v60;
  if ( *(_DWORD *)(*((_QWORD *)v60 + 4) + 72LL) )
  {
    PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v82);
    v82[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
      (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82,
      L"CopyStreamOutOfEditor(eappxEditor.get(), &AppxEncryptedPackageEditor::GetRawCodeIntegrity, workingDirectory, &rawCIStream)");
    PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v82);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
    v37 = Appx::Packaging::CopyStreamOutOfEditor(
            v60,
            Appx::Packaging::AppxEncryptedPackageEditor::GetRawCodeIntegrity,
            a3,
            &v64);
    v10 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x786,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v37,
        v57);
      PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
      PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
      v38 = v60;
      v60 = 0;
      if ( v38 )
        Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(v38, 1u);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
      Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v29, v39);
      goto LABEL_93;
    }
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v82);
    v36 = v60;
    v11 = v64;
  }
  v40 = *(_QWORD *)(*((_QWORD *)v36 + 4) + 8LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v67);
  v41 = v60;
  v60 = 0;
  if ( v41 )
    Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(v41, 1u);
  v42 = v63;
  v73 = 0;
  GetPackageId = v63->lpVtbl->GetPackageId;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
  CloneableStream = ((__int64 (__fastcall *)(struct IAppxManifestReader *, struct IAppxManifestPackageId **))GetPackageId)(
                      v42,
                      &v73);
  if ( CloneableStream < 0 )
  {
    v45 = 1934;
LABEL_70:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      v57);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
    goto LABEL_48;
  }
  CloneableStream = Appx::Packaging::SetStreamPosition(v61, 0, v44);
  if ( CloneableStream < 0 )
  {
    v45 = 1936;
    goto LABEL_70;
  }
  v69 = 0;
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v83);
  v83[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83,
    L"Production::EncryptedPackageWriterHelper::CreateForEdit(cloneablePackageStream.Get(), nullptr, dummyKeyFromPackage.g"
     "et(), updatedPackageId.Get(), packageOvewriteStartLocation, blockMapWriter.release(), tempBlockMapStream.Get(), foo"
     "tersStream.Get(), false , wil::out_param(packageWriter))");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v83);
  *(_QWORD *)v70 = &v69;
  v71 = 0;
  v72 = 1;
  CloneableStream = Appx::Packaging::Production::EncryptedPackageWriterHelper::CreateForEdit(
                      v61,
                      0,
                      v66,
                      v73,
                      v40,
                      v29,
                      v62,
                      v65,
                      0,
                      &v71);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::Production::EncryptedPackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::EncryptedPackageWriterHelper>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::Production::EncryptedPackageWriterHelper,wistd::default_delete<Appx::Packaging::Production::EncryptedPackageWriterHelper>>>(v70);
  if ( CloneableStream < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x793,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      (int)v58);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
LABEL_75:
    v47 = v69;
    v69 = 0;
    if ( v47 )
      Appx::Packaging::Production::EncryptedPackageWriterHelper::`scalar deleting destructor'(v47, v46);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
    goto LABEL_6;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v83);
  *(_QWORD *)v70 = 0;
  v78 = 0;
  v79 = 1;
  v77 = 0;
  CloneableStream = Appx::Packaging::Production::EncryptionSettingsHelper::GetEncryptionSettingsByFileName(
                      (Appx::Packaging::Production::EncryptionSettingsHelper *)&v77,
                      L"AppxManifest.xml",
                      APPX_COMPRESSION_OPTION_NORMAL,
                      (struct Appx::Packaging::Production::EncryptedPackageFileSettings *)v70);
  if ( CloneableStream < 0 )
  {
    v48 = 1944;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v48,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)CloneableStream,
      (int)v58);
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(&v77);
    goto LABEL_75;
  }
  v58 = v70;
  CloneableStream = Appx::Packaging::Production::EncryptedPackageWriterHelper::AddFile(v69, L"AppxManifest.xml", 0, a2);
  if ( CloneableStream < 0 )
  {
    v48 = 1945;
    goto LABEL_80;
  }
  PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v84);
  v84[0] = &PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable';
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(
    (PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84,
    L"packageWriter->CloseForEdit(rawCIStream.Get())");
  PerfLoggerDetails::PerfLoggerGlobals::AddActivity(&qword_180169AD0, v59, v84);
  v49 = Appx::Packaging::Production::EncryptedPackageWriterHelper::CloseForEdit(v69, v11);
  v10 = v49;
  if ( v49 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v49,
      (int)v70);
    PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
    Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(&v77);
    v51 = v69;
    v69 = 0;
    if ( v51 )
      Appx::Packaging::Production::EncryptedPackageWriterHelper::`scalar deleting destructor'(v51, v50);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
LABEL_92:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
LABEL_93:
    wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>::reset(&v66, 0);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
    PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v59);
    PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
    goto LABEL_94;
  }
  PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity((PerfLoggerDetails::PerfLoggerGlobals *)&qword_180169AD0);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v84);
  Common::Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>::~Array<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::ContainerOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::NoKey,Common::ContainerOperations<Common::NoKey,__MIDL___MIDL_itf_appxdatasource_0000_0000_0003>,Common::ArrayOperations<__MIDL___MIDL_itf_appxdatasource_0000_0000_0003,Common::NoKey>>(&v77);
  v53 = v69;
  v69 = 0;
  if ( v53 )
    Appx::Packaging::Production::EncryptedPackageWriterHelper::`scalar deleting destructor'(v53, v52);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v61);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v62);
  wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>::reset(&v66, 0);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v63);
  PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover((PerfLoggerDetails::PerfLoggerGlobals::StackRemover *)v59);
  PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp((PerfLoggerDetails::PerfLoggerProvider::TrackedOp *)v80);
  v10 = 0;
LABEL_94:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v76);
  return v10;
}

```

## disassembly

```asm
0x1800c021c  mov     [rsp-8+arg_18], rbx
0x1800c0221  push    rbp
0x1800c0222  push    rsi
0x1800c0223  push    rdi
0x1800c0224  push    r12
0x1800c0226  push    r13
0x1800c0228  push    r14
0x1800c022a  push    r15
0x1800c022c  lea     rbp, [rsp-970h]
0x1800c0234  sub     rsp, 0A70h
0x1800c023b  mov     rax, cs:__security_cookie
0x1800c0242  xor     rax, rsp
0x1800c0245  mov     [rbp+9A0h+var_40], rax
0x1800c024c  mov     rbx, rcx
0x1800c024f  xor     r13d, r13d
0x1800c0252  lea     rcx, [rbp+9A0h+var_9B8]
0x1800c0256  mov     [rbp+9A0h+var_9B8], r13
0x1800c025a  mov     sil, r9b
0x1800c025d  mov     r15, r8
0x1800c0260  mov     r12, rdx
0x1800c0263  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0268  lea     r8, [rbp+9A0h+var_9B8]; struct IStream **
0x1800c026c  mov     rcx, rbx; struct IStream *
0x1800c026f  lea     rdx, aPackage; "package"
0x1800c0276  call    ?CreatePerfLoggingStream@@YAJPEAUIStream@@PEBGPEAPEAU1@@Z; CreatePerfLoggingStream(IStream *,ushort const *,IStream * *)
0x1800c027b  mov     ebx, eax
0x1800c027d  test    eax, eax
0x1800c027f  jns     short loc_1800C02A1
0x1800c0281  mov     rcx, [rbp+9A8h]; this
0x1800c0288  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c028f  mov     r9d, eax; char *
0x1800c0292  mov     edx, 736h; void *
0x1800c0297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c029c  jmp     loc_1800C0F18
0x1800c02a1  lea     rcx, [rbp+9A0h+var_970]; struct wil::details::IFailureCallback *
0x1800c02a5  call    ??0?$ActivityBase@VPerfLoggerProvider@PerfLoggerDetails@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PerfLoggerDetails::PerfLoggerProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c02aa  lea     rax, ??_7TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@6B@; const PerfLoggerDetails::PerfLoggerProvider::TrackedOp::`vftable'
0x1800c02b1  lea     rdx, aAppxPackagingU; "Appx::Packaging::UpdateManifestInPlaceE"...
0x1800c02b8  mov     [rbp+9A0h+var_970], rax
0x1800c02bc  lea     rcx, [rbp+9A0h+var_970]; this
0x1800c02c0  call    ?StartActivity@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAAXPEBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::StartActivity(ushort const *)
0x1800c02c5  lea     r8, [rbp+9A0h+var_970]
0x1800c02c9  lea     rdx, [rsp+0AA0h+var_A50]
0x1800c02ce  lea     rcx, qword_180169AD0
0x1800c02d5  call    ?BeginStack@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUStackRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::BeginStack(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c02da  mov     rbx, r13
0x1800c02dd  mov     [rsp+0AA0h+var_A30], r13
0x1800c02e2  lea     rcx, [rsp+0AA0h+var_A40]
0x1800c02e7  mov     [rsp+0AA0h+var_A28], rbx
0x1800c02ec  mov     [rbp+9A0h+var_A18], r13
0x1800c02f0  mov     [rsp+0AA0h+var_A38], r13
0x1800c02f5  mov     [rbp+9A0h+var_A20], r13
0x1800c02f9  mov     [rsp+0AA0h+var_A40], r13
0x1800c02fe  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0303  mov     rcx, [rbp+9A0h+var_9B8]
0x1800c0307  lea     rdx, [rsp+0AA0h+var_A40]
0x1800c030c  call    cs:__imp_GetCloneableStream
0x1800c0313  nop     dword ptr [rax+rax+00h]
0x1800c0318  mov     edi, eax
0x1800c031a  test    eax, eax
0x1800c031c  jns     short loc_1800C038F
0x1800c031e  mov     edx, 745h; void *
0x1800c0323  mov     rcx, [rbp+9A8h]; this
0x1800c032a  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c0331  mov     r9d, edi; char *
0x1800c0334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0339  lea     rcx, [rsp+0AA0h+var_A40]
0x1800c033e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0343  lea     rcx, [rsp+0AA0h+var_A28]
0x1800c0348  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c034d  lea     rcx, [rbp+9A0h+var_A20]
0x1800c0351  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0356  lea     rcx, [rsp+0AA0h+var_A38]
0x1800c035b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0360  xor     edx, edx
0x1800c0362  lea     rcx, [rbp+9A0h+var_A18]
0x1800c0366  call    ?reset@?$unique_ptr@UAppxKeyInfo@Packaging@Appx@@U?$default_delete@UAppxKeyInfo@Packaging@Appx@@@wistd@@@wistd@@QEAAXPEAUAppxKeyInfo@Packaging@Appx@@@Z; wistd::unique_ptr<Appx::Packaging::AppxKeyInfo,wistd::default_delete<Appx::Packaging::AppxKeyInfo>>::reset(Appx::Packaging::AppxKeyInfo *)
0x1800c036b  lea     rcx, [rsp+0AA0h+var_A30]
0x1800c0370  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0375  lea     rcx, [rsp+0AA0h+var_A50]; this
0x1800c037a  call    ??1StackRemover@PerfLoggerGlobals@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerGlobals::StackRemover::~StackRemover(void)
0x1800c037f  lea     rcx, [rbp+9A0h+var_970]; this
0x1800c0383  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c0388  mov     ebx, edi
0x1800c038a  jmp     loc_1800C0F18
0x1800c038f  lea     rcx, [rsp+0AA0h+var_A30]
0x1800c0394  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0399  xor     r9d, r9d; unsigned __int16 **
0x1800c039c  lea     rdx, [rsp+0AA0h+var_A30]; struct IAppxManifestReader **
0x1800c03a1  mov     rcx, r12; struct IStream *
0x1800c03a4  lea     r14d, [r9+1]
0x1800c03a8  mov     r8b, r14b; bool
0x1800c03ab  call    ?Create@AppxManifestReaderImpl@Manifest@Packaging@Appx@@SAJPEAUIStream@@PEAPEAUIAppxManifestReader@@_NPEAPEAG@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(IStream *,IAppxManifestReader * *,bool,ushort * *)
0x1800c03b0  mov     edi, eax
0x1800c03b2  test    eax, eax
0x1800c03b4  jns     short loc_1800C03C0
0x1800c03b6  mov     edx, 747h
0x1800c03bb  jmp     loc_1800C0323
0x1800c03c0  mov     rcx, [rsp+0AA0h+var_A40]; this
0x1800c03c5  mov     rdx, r12; struct IStream *
0x1800c03c8  call    ?VerifyFileEncryptionSettings@Packaging@Appx@@YAJPEAUIStream@@0@Z; Appx::Packaging::VerifyFileEncryptionSettings(IStream *,IStream *)
0x1800c03cd  mov     edi, eax
0x1800c03cf  test    eax, eax
0x1800c03d1  jns     short loc_1800C03DD
0x1800c03d3  mov     edx, 74Ch
0x1800c03d8  jmp     loc_1800C0323
0x1800c03dd  lea     rcx, qword_180169AD0; this
0x1800c03e4  mov     [rsp+0AA0h+var_A48], r13
0x1800c03e9  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c03ee  lea     rdx, aAppxencryptedp_0; "AppxEncryptedPackageEditor::Create(clon"...
0x1800c03f5  lea     rcx, [rbp+9A0h+var_2E0]; this
0x1800c03fc  call    ??$Start@AEAY0DP@$$CBG@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@SA?AV012@AEAY0DP@$$CBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<ushort const (&)[63]>(ushort const (&)[63])
0x1800c0401  lea     r8, [rbp+9A0h+var_2E0]
0x1800c0408  lea     rdx, [rsp+0AA0h+var_A50]
0x1800c040d  lea     rcx, qword_180169AD0
0x1800c0414  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c0419  mov     rcx, [rsp+0AA0h+var_A40]; struct IStream *
0x1800c041e  lea     rax, [rsp+0AA0h+var_A48]
0x1800c0423  lea     rdx, [rbp+9A0h+var_9E8]; struct Appx::Packaging::AppxEncryptedPackageEditor **
0x1800c0427  mov     qword ptr [rbp+9A0h+var_9F0], rax
0x1800c042b  mov     [rbp+9A0h+var_9E8], r13
0x1800c042f  mov     [rbp+9A0h+var_9E0], r14b
0x1800c0433  call    ?Create@AppxEncryptedPackageEditor@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV123@@Z; Appx::Packaging::AppxEncryptedPackageEditor::Create(IStream *,Appx::Packaging::AppxEncryptedPackageEditor * *)
0x1800c0438  lea     rcx, [rbp+9A0h+var_9F0]
0x1800c043c  mov     edi, eax
0x1800c043e  call    ??1?$out_param_t@V?$unique_ptr@VAppxEncryptedPackageEditor@Packaging@Appx@@U?$default_delete@VAppxEncryptedPackageEditor@Packaging@Appx@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::AppxEncryptedPackageEditor,wistd::default_delete<Appx::Packaging::AppxEncryptedPackageEditor>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::AppxEncryptedPackageEditor,wistd::default_delete<Appx::Packaging::AppxEncryptedPackageEditor>>>(void)
0x1800c0443  test    edi, edi
0x1800c0445  jns     short loc_1800C049A
0x1800c0447  mov     rcx, [rbp+9A8h]; this
0x1800c044e  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c0455  mov     r9d, edi; char *
0x1800c0458  mov     edx, 74Fh; void *
0x1800c045d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0462  lea     rcx, qword_180169AD0; this
0x1800c0469  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c046e  lea     rcx, [rbp+9A0h+var_2E0]; this
0x1800c0475  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c047a  mov     rcx, [rsp+0AA0h+var_A48]; this
0x1800c047f  mov     [rsp+0AA0h+var_A48], r13
0x1800c0484  test    rcx, rcx
0x1800c0487  jz      loc_1800C0339
0x1800c048d  mov     edx, r14d; unsigned int
0x1800c0490  call    ??_GAppxEncryptedPackageEditor@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::AppxEncryptedPackageEditor::`scalar deleting destructor'(uint)
0x1800c0495  jmp     loc_1800C0339
0x1800c049a  lea     rcx, qword_180169AD0; this
0x1800c04a1  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c04a6  lea     rcx, [rbp+9A0h+var_2E0]; this
0x1800c04ad  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c04b2  mov     rdi, [rsp+0AA0h+var_A48]
0x1800c04b7  lea     rcx, [rbp+9A0h+var_9C8]
0x1800c04bb  mov     [rbp+9A0h+var_A10], r13
0x1800c04bf  mov     [rbp+9A0h+var_9C8], r13
0x1800c04c3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c04c8  lea     rdx, [rbp+9A0h+var_9C8]; struct IStream **
0x1800c04cc  mov     rcx, rdi; this
0x1800c04cf  call    ?GetEncryptedBlockMap@AppxEncryptedPackageEditor@Packaging@Appx@@QEAAJPEAPEAUIStream@@@Z; Appx::Packaging::AppxEncryptedPackageEditor::GetEncryptedBlockMap(IStream * *)
0x1800c04d4  mov     edi, eax
0x1800c04d6  test    eax, eax
0x1800c04d8  jns     short loc_1800C050C
0x1800c04da  mov     edx, 755h; void *
0x1800c04df  mov     rcx, [rbp+9A8h]; this
0x1800c04e6  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c04ed  mov     r9d, edi; char *
0x1800c04f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c04f5  lea     rcx, [rbp+9A0h+var_9C8]
0x1800c04f9  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c04fe  lea     rcx, [rbp+9A0h+var_A10]
0x1800c0502  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0507  jmp     loc_1800C047A
0x1800c050c  mov     rcx, [rsp+0AA0h+var_A48]; this
0x1800c0511  lea     r8, [rbp+9A0h+var_9B0]; struct Appx::Packaging::EncryptedAppxFooter *
0x1800c0515  mov     dword ptr [rbp+9A0h+var_9B0+4], r13d
0x1800c0519  mov     rdx, [rcx+20h]
0x1800c051d  mov     rdx, [rdx+50h]; unsigned __int64
0x1800c0521  call    ?GetFooterByFileId@AppxEncryptedPackageEditor@Packaging@Appx@@QEAAJ_KPEAVEncryptedAppxFooter@23@@Z; Appx::Packaging::AppxEncryptedPackageEditor::GetFooterByFileId(unsigned __int64,Appx::Packaging::EncryptedAppxFooter *)
0x1800c0526  mov     edi, eax
0x1800c0528  test    eax, eax
0x1800c052a  jns     short loc_1800C0533
0x1800c052c  mov     edx, 758h
0x1800c0531  jmp     short loc_1800C04DF
0x1800c0533  lea     rcx, [rbp+9A0h+var_A10]
0x1800c0537  cmp     dword ptr [rbp+9A0h+var_9B0+4], r13d
0x1800c053b  jnz     short loc_1800C058D
0x1800c053d  lea     rdx, [rbp+9A0h+var_9C8]
0x1800c0541  call    ??4?$ComPtr@UIStream@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IStream>::operator=(Microsoft::WRL::ComPtr<IStream> &&)
0x1800c0546  lea     rcx, [rbp+9A0h+var_9C8]
0x1800c054a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c054f  mov     rcx, [rbp+9A0h+var_A10]; this
0x1800c0553  xor     edx, edx; struct IStream *
0x1800c0555  mov     [rbp+9A0h+var_A08], r13
0x1800c0559  call    ?SetStreamPosition@Packaging@Appx@@YAJPEAUIStream@@_K@Z; Appx::Packaging::SetStreamPosition(IStream *,unsigned __int64)
0x1800c055e  mov     edi, eax
0x1800c0560  test    eax, eax
0x1800c0562  jns     short loc_1800C05B2
0x1800c0564  mov     edx, 768h; void *
0x1800c0569  mov     rcx, [rbp+9A8h]; this
0x1800c0570  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c0577  mov     r9d, edi; char *
0x1800c057a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c057f  lea     rcx, [rbp+9A0h+var_A08]
0x1800c0583  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0588  jmp     loc_1800C04FE
0x1800c058d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c0592  mov     rcx, [rbp+9A0h+var_9C8]; struct IStream *
0x1800c0596  lea     r8, [rbp+9A0h+var_A10]; struct IStream **
0x1800c059a  mov     rdx, r15; unsigned __int16 *
0x1800c059d  call    ?InflateToTempFileStream@ZipInflator@Packaging@Appx@@SAJPEAUIStream@@PEBGPEAPEAU4@@Z; Appx::Packaging::ZipInflator::InflateToTempFileStream(IStream *,ushort const *,IStream * *)
0x1800c05a2  mov     edi, eax
0x1800c05a4  test    eax, eax
0x1800c05a6  jns     short loc_1800C0546
0x1800c05a8  mov     edx, 763h
0x1800c05ad  jmp     loc_1800C04DF
0x1800c05b2  lea     rcx, qword_180169AD0; this
0x1800c05b9  call    ?LogIntermediate@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::LogIntermediate(void)
0x1800c05be  lea     rcx, [rbp+9A0h+var_190]; this
0x1800c05c5  call    ??$Start@AEAY0FM@$$CBG@TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@SA?AV012@AEAY0FM@$$CBG@Z; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::Start<ushort const (&)[92]>(ushort const (&)[92])
0x1800c05ca  lea     r8, [rbp+9A0h+var_190]
0x1800c05d1  lea     rdx, [rsp+0AA0h+var_A50]
0x1800c05d6  lea     rcx, qword_180169AD0
0x1800c05dd  call    ?AddActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAA?AUActivityRemover@12@AEAVTrackedOp@PerfLoggerProvider@2@@Z; PerfLoggerDetails::PerfLoggerGlobals::AddActivity(PerfLoggerDetails::PerfLoggerProvider::TrackedOp &)
0x1800c05e2  lea     rcx, [rbp+9A0h+var_A08]
0x1800c05e6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c05eb  mov     rcx, [rbp+9A0h+var_A10]; struct IStream *
0x1800c05ef  lea     r8, [rbp+9A0h+var_A08]; struct Appx::Packaging::BlockMap::AppxBlockMapReader **
0x1800c05f3  call    ?Create@AppxBlockMapReader@BlockMap@Packaging@Appx@@SAJPEAUIStream@@PEBGPEAPEAV1234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::Create(IStream *,ushort const *,Appx::Packaging::BlockMap::AppxBlockMapReader * *)
0x1800c05f8  mov     edi, eax
0x1800c05fa  test    eax, eax
0x1800c05fc  jns     short loc_1800C0636
0x1800c05fe  mov     rcx, [rbp+9A8h]; this
0x1800c0605  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c060c  mov     r9d, eax; char *
0x1800c060f  mov     edx, 769h; void *
0x1800c0614  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0619  lea     rcx, qword_180169AD0; this
0x1800c0620  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c0625  lea     rcx, [rbp+9A0h+var_190]; this
0x1800c062c  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c0631  jmp     loc_1800C057F
0x1800c0636  lea     rcx, qword_180169AD0; this
0x1800c063d  call    ?RemoveActivity@PerfLoggerGlobals@PerfLoggerDetails@@QEAAXXZ; PerfLoggerDetails::PerfLoggerGlobals::RemoveActivity(void)
0x1800c0642  lea     rcx, [rbp+9A0h+var_190]; this
0x1800c0649  call    ??1TrackedOp@PerfLoggerProvider@PerfLoggerDetails@@QEAA@XZ; PerfLoggerDetails::PerfLoggerProvider::TrackedOp::~TrackedOp(void)
0x1800c064e  test    sil, sil
0x1800c0651  jz      loc_1800C06F0
0x1800c0657  mov     rcx, [rbp+9A0h+var_A08]
0x1800c065b  lea     rax, [rbp+9A0h+var_9C0]
0x1800c065f  lea     rdx, [rbp+9A0h+var_9E8]
0x1800c0663  mov     qword ptr [rbp+9A0h+var_9F0], rax
0x1800c0667  mov     [rbp+9A0h+var_9C0], r13
0x1800c066b  mov     [rbp+9A0h+var_9E8], r13
0x1800c066f  mov     [rbp+9A0h+var_9E0], r14b
0x1800c0673  call    ?CreateFileMapFromBlockMapReader@Packaging@Appx@@YAJPEAVAppxBlockMapReader@BlockMap@12@PEAPEAV?$GenericMap@PEBGPEBG@Common@@@Z; Appx::Packaging::CreateFileMapFromBlockMapReader(Appx::Packaging::BlockMap::AppxBlockMapReader *,Common::GenericMap<ushort const *,ushort const *> * *)
0x1800c0678  lea     rcx, [rbp+9A0h+var_9F0]
0x1800c067c  mov     edi, eax
0x1800c067e  call    ??1?$out_param_t@V?$unique_ptr@V?$GenericMap@PEBGPEBG@Common@@U?$default_delete@V?$GenericMap@PEBGPEBG@Common@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Common::GenericMap<ushort const *,ushort const *>,wistd::default_delete<Common::GenericMap<ushort const *,ushort const *>>>>::~out_param_t<wistd::unique_ptr<Common::GenericMap<ushort const *,ushort const *>,wistd::default_delete<Common::GenericMap<ushort const *,ushort const *>>>>(void)
0x1800c0683  test    edi, edi
0x1800c0685  jns     short loc_1800C06BD
0x1800c0687  mov     edx, 76Eh; void *
0x1800c068c  mov     rcx, [rbp+9A8h]; this
0x1800c0693  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800c069a  mov     r9d, edi; char *
0x1800c069d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c06a2  mov     rcx, [rbp+9A0h+var_9C0]; void *
0x1800c06a6  mov     [rbp+9A0h+var_9C0], r13
0x1800c06aa  test    rcx, rcx
0x1800c06ad  jz      loc_1800C057F
0x1800c06b3  call    ??_G?$GenericMap@PEBGPEBG@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort const *,ushort const *>::`scalar deleting destructor'(uint)
0x1800c06b8  jmp     loc_1800C057F
0x1800c06bd  mov     r8, [rbp+9A0h+var_9C0]
0x1800c06c1  mov     dl, [rbp+9A0h+arg_20]
0x1800c06c7  mov     rcx, [rsp+0AA0h+var_A30]
0x1800c06cc  call    ?Validate@PackageValidator@Packaging@Appx@@SAJPEAUIAppxManifestReader@@_NAEBV?$GenericMap@PEBGPEBG@Common@@@Z; Appx::Packaging::PackageValidator::Validate(IAppxManifestReader *,bool,Common::GenericMap<ushort const *,ushort const *> const &)
0x1800c06d1  mov     edi, eax
0x1800c06d3  test    eax, eax
0x1800c06d5  jns     short loc_1800C06DE
0x1800c06d7  mov     edx, 771h
0x1800c06dc  jmp     short loc_1800C068C
0x1800c06de  mov     rcx, [rbp+9A0h+var_9C0]; void *
0x1800c06e2  mov     [rbp+9A0h+var_9C0], r13
0x1800c06e6  test    rcx, rcx
0x1800c06e9  jz      short loc_1800C06F0
0x1800c06eb  call    ??_G?$GenericMap@PEBGPEBG@Common@@QEAAPEAXI@Z; Common::GenericMap<ushort const *,ushort const *>::`scalar deleting destructor'(uint)
0x1800c06f0  lea     rcx, [rsp+0AA0h+var_A38]
0x1800c06f5  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800c06fa  lea     r8, [rsp+0AA0h+var_A38]; unsigned __int16 *
0x1800c06ff  mov     rcx, r15; this
0x1800c0702  lea     rdx, aTempappxblockm; "TempAppxBlockMap"
0x1800c0709  call    ?CreateTempFileStream@Packaging@Appx@@YAJPEBG0PEAPEAUIStream@@@Z; Appx::Packaging::CreateTempFileStream(ushort const *,ushort const *,IStream * *)
0x1800c070e  mov     edi, eax
0x1800c0710  test    eax, eax
0x1800c0712  jns     short loc_1800C071E
0x1800c0714  mov     edx, 775h
0x1800c0719  jmp     loc_1800C0569
0x1800c071e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c0725  mov     ecx, 88h; unsigned __int64
0x1800c072a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c072f  test    rax, rax
0x1800c0732  jz      loc_1800C0E80
0x1800c0738  mov     rcx, rax; this
0x1800c073b  call    ??0BlockMapXmlWriter@BlockMap@Packaging@Appx@@QEAA@XZ; Appx::Packaging::BlockMap::BlockMapXmlWriter::BlockMapXmlWriter(void)
  ... truncated ...
```
