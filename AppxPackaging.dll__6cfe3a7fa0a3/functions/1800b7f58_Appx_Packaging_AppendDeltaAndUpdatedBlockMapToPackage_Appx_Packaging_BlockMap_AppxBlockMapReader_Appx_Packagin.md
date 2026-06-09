# Appx::Packaging::AppendDeltaAndUpdatedBlockMapToPackage(Appx::Packaging::BlockMap::AppxBlockMapReader *,Appx::Packaging::BlockMap::AppxBlockMapReader *,ushort const *,IOpcPackage *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,Appx::Packaging::ZipEditor *,ushort const *)

- ea: `0x1800b7f58`
- end: `0x1800b8e66`
- name: `?AppendDeltaAndUpdatedBlockMapToPackage@Packaging@Appx@@YAJPEAVAppxBlockMapReader@BlockMap@12@0PEBGPEAUIOpcPackage@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEAVZipEditor@12@1@Z`
- size: `3854`
- prototype: ``
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c1aa0`

## callees

- `0x1800029e4`
- `0x180002cdc`
- `0x1800059f0`
- `0x180005eb8`
- `0x1800133fc`
- `0x180039ef0`
- `0x18003d318`
- `0x1800446d0`
- `0x18004ccd0`
- `0x18004cf84`
- `0x18004ec7c`
- `0x180050ae8`
- `0x180051ec4`
- `0x18007861c`
- `0x18007cfac`
- `0x18007d684`
- `0x18007f72c`
- `0x1800804a8`
- `0x18008390c`
- `0x180087cb4`
- `0x18008c87c`
- `0x1800992a0`
- `0x1800992c4`
- `0x1800992d0`
- `0x1800b6d24`
- `0x1800b7018`
- `0x1800b7234`
- `0x1800b7430`
- `0x1800b79cc`
- `0x1800b7f58`
- `0x1800b9888`
- `0x1800bb70c`
- `0x1800bc9c8`
- `0x1800bcac8`
- `0x1800bd070`
- `0x1800bd190`
- `0x1800bd2b4`
- `0x1800bd648`
- `0x1800be16c`
- `0x1800e61f8`
- `0x1800e628c`
- `0x1800e95c4`
- `0x1800e9758`
- `0x1800f8af4`
- `0x1801051d8`
- `0x180106010`

## string_xrefs

- `0x1800b815c`: `AppxManifest.xml`
- `0x1800b8acb`: `AppxManifest.xml`
- `0x1800b8181`: `AppxContentGroupMap.xml`
- `0x1800b8ae1`: `AppxContentGroupMap.xml`
- `0x1800b8d02`: `AppxBlockMap.xml`
- `0x1800b80d1`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b811a`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b87b3`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8825`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b88d3`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b894c`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8971`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b89fa`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8a60`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8a99`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8c0f`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8c66`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8c8f`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8cb5`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8d5f`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8e1b`: `onecore\printscan\appxpackaging\dll\lib\appxpackageeditor.cpp`
- `0x1800b8d2f`: `AppxBlockMap.xml`
- `0x1800b81fc`: `.blockcache`
- `0x1800b8059`: `TempAppxBlockMap`
- `0x1800b7fae`: `AppendDeltaAndUpdatedBlockMapToPackage`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AppendDeltaAndUpdatedBlockMapToPackage(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 *a6,
        Appx::Packaging *a7)
{
  __int64 v7; // r12
  unsigned __int16 *v8; // r13
  enum APPX_PACKAGING_CONTEXT_CHANGE_TYPE v10; // r9d
  Appx::Packaging::BlockMap::BlockMapXmlWriter *v11; // rax
  Appx::Packaging::BlockMap::BlockMapXmlWriter *v12; // r15
  struct IStream **v13; // r9
  int TempFileStream; // eax
  int started; // ebx
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // edi
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rsi
  __int64 v25; // r14
  unsigned __int16 *v26; // rdi
  unsigned __int64 v27; // r13
  int v28; // eax
  const unsigned __int16 **v29; // r9
  Appx::Packaging::ZipFileItem *v30; // rsi
  unsigned __int64 v31; // r12
  __int64 v32; // rdx
  int v33; // r10d
  int v34; // eax
  int v35; // eax
  int Entry; // eax
  int v37; // eax
  unsigned __int64 v38; // rdx
  char *v39; // rsi
  void *v40; // rcx
  unsigned __int16 *v41; // rcx
  bool v42; // cl
  int StreamCurrentPosition; // eax
  __int64 v44; // rdi
  int v45; // ecx
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  unsigned int v48; // r13d
  __int64 v49; // rbx
  unsigned int v50; // eax
  unsigned __int64 v51; // rsi
  int v52; // eax
  unsigned int v53; // r9d
  unsigned __int64 v54; // rdx
  unsigned __int64 *v55; // r8
  int v56; // eax
  int LocalFileItemInfo; // eax
  Appx::Packaging::ZipFileItem *v58; // rcx
  const unsigned __int16 *v59; // r9
  int v60; // eax
  __int64 v61; // rsi
  unsigned __int64 i; // rbx
  const struct Appx::Packaging::BlockMap::AppxBlockMapFile *v63; // rsi
  __int64 v64; // rdx
  unsigned __int64 v65; // rdx
  void *v66; // rcx
  unsigned __int16 *v67; // rcx
  Appx::Packaging **v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // r9
  unsigned __int64 v71; // rdx
  void *v72; // rcx
  unsigned __int16 *v73; // rcx
  __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  unsigned __int16 *v76; // rcx
  Appx::Packaging **v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // r9
  __int64 v80; // rdx
  unsigned __int64 v81; // r9
  __int64 v82; // rdx
  unsigned __int64 v83; // rdx
  __int64 v84; // rdx
  __int64 v85; // r9
  __int64 v86; // rdx
  const unsigned __int16 *v87; // rdi
  const unsigned __int16 *v88; // r9
  int v89; // eax
  int v90; // esi
  int OpcFileStream; // eax
  int appended; // edi
  __int64 v93; // rdx
  unsigned __int64 v94; // rdx
  void *v95; // rcx
  __int64 v96; // rdx
  unsigned __int64 v97; // rdx
  void *v98; // rcx
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 v101; // rcx
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // rcx
  enum APPX_PACKAGING_CONTEXT_CHANGE_TYPE v105; // r9d
  unsigned int v106; // edx
  enum APPX_PACKAGING_CONTEXT_CHANGE_TYPE v107; // r9d
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // rcx
  unsigned int v111; // edx
  unsigned __int16 *v113; // [rsp+20h] [rbp-E0h]
  int v114; // [rsp+20h] [rbp-E0h]
  struct Appx::Packaging::ZipFileItem **v115; // [rsp+28h] [rbp-D8h]
  __int64 v116; // [rsp+60h] [rbp-A0h] BYREF
  void *v117; // [rsp+68h] [rbp-98h] BYREF
  struct IStream *v118; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v119; // [rsp+78h] [rbp-88h] BYREF
  void *v120; // [rsp+80h] [rbp-80h] BYREF
  Appx::Packaging::ZipFileItem *v121; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v122[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v123; // [rsp+A0h] [rbp-60h]
  char v124; // [rsp+A8h] [rbp-58h]
  __int64 v125; // [rsp+B0h] [rbp-50h] BYREF
  void *v126[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v127; // [rsp+C8h] [rbp-38h]
  Appx::Packaging *v128; // [rsp+D0h] [rbp-30h] BYREF
  char *v129; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v130[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct Appx::Packaging::ZipLocalFileItemInfo *v131; // [rsp+E8h] [rbp-18h] BYREF
  void **v132; // [rsp+F0h] [rbp-10h] BYREF
  char *v133; // [rsp+F8h] [rbp-8h] BYREF
  void **v134; // [rsp+100h] [rbp+0h]
  int v135[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v136; // [rsp+110h] [rbp+10h]
  struct Appx::Packaging::BlockMap::AppxBlockMapFile *v137; // [rsp+118h] [rbp+18h] BYREF
  struct Appx::Packaging::ZipEditor *v138; // [rsp+120h] [rbp+20h]
  __int64 v139; // [rsp+128h] [rbp+28h]
  __int64 v140; // [rsp+130h] [rbp+30h]
  int v141[2]; // [rsp+138h] [rbp+38h] BYREF
  int v142; // [rsp+140h] [rbp+40h] BYREF
  __int64 v143; // [rsp+144h] [rbp+44h]
  int v144; // [rsp+14Ch] [rbp+4Ch]
  struct Appx::Packaging::ZipLocalFileItemInfo *v145; // [rsp+150h] [rbp+50h]
  __int64 v146; // [rsp+158h] [rbp+58h]
  int v147; // [rsp+160h] [rbp+60h] BYREF
  __int64 v148; // [rsp+164h] [rbp+64h]
  int v149; // [rsp+16Ch] [rbp+6Ch]
  __int16 v150; // [rsp+170h] [rbp+70h]
  int v151; // [rsp+172h] [rbp+72h]
  __int16 v152; // [rsp+176h] [rbp+76h]
  __int64 v153; // [rsp+178h] [rbp+78h]
  __int64 v154; // [rsp+180h] [rbp+80h]
  Appx::Packaging::ZipFileItem *v155; // [rsp+188h] [rbp+88h]
  Appx::Packaging::ZipFileItem *v156; // [rsp+190h] [rbp+90h]
  unsigned __int16 *v157; // [rsp+198h] [rbp+98h]
  __int64 v158; // [rsp+1A0h] [rbp+A0h]
  _QWORD v159[34]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v160; // [rsp+2C0h] [rbp+1C0h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v7 = a2;
  v8 = a6;
  v158 = a2;
  v139 = a5;
  v136 = a6;
  v138 = a7;
  v140 = a4;
  v157 = a3;
  wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v159);
  v159[0] = &Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::`vftable';
  Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::StartActivity((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v159);
  wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
    v159,
    L"Appending file deltas");
  Appx::Packaging::details::SendPackagingContextToSink((Appx::Packaging::details *)(v160 + 40), 0, 0, v10);
  v11 = (Appx::Packaging::BlockMap::BlockMapXmlWriter *)operator new(
                                                          0x88u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11
    || (v12 = (Appx::Packaging::BlockMap::BlockMapXmlWriter *)Appx::Packaging::BlockMap::BlockMapXmlWriter::BlockMapXmlWriter(v11)) == 0 )
  {
    started = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x338,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)0x8007000ELL,
      (int)v113);
    goto LABEL_183;
  }
  *(_QWORD *)v130 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v130);
  TempFileStream = Appx::Packaging::CreateTempFileStream(a7, L"TempAppxBlockMap", v130, v13);
  started = TempFileStream;
  if ( TempFileStream < 0 )
  {
    v16 = (unsigned int)TempFileStream;
    v17 = 827;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)v16,
      (int)v113);
    goto LABEL_178;
  }
  v18 = *(_DWORD *)(v7 + 16);
  v19 = *(_QWORD *)(v7 + 24);
  if ( v18 < 2 )
    v18 = 2;
  v129 = *(char **)v130;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v129);
  started = Appx::Packaging::BlockMap::BlockMapXmlWriter::StartBlockMap((_DWORD)v12, (unsigned int)&v129, v19, v18, 0);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v129);
  if ( started < 0 )
  {
    v16 = (unsigned int)started;
    v17 = 830;
    goto LABEL_9;
  }
  v116 = 0;
  v126[0] = &v116;
  v126[1] = 0;
  LOBYTE(v127) = 1;
  started = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(a1, &v126[1]);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>(v126);
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x341,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)v113);
LABEL_175:
    v74 = v116;
    v116 = 0;
    goto LABEL_176;
  }
  v22 = v116;
  v23 = 0;
  v122[0] = 0;
  v24 = 0;
  v122[1] = 0;
  v123 = 0;
  v124 = 0;
  if ( !*(_BYTE *)(v116 + 24) )
  {
LABEL_79:
    for ( i = 0; i != v24; ++i )
    {
      if ( i < v24 )
      {
        _mm_lfence();
        v63 = *(const struct Appx::Packaging::BlockMap::AppxBlockMapFile **)(v23 + 8 * i);
      }
      else
      {
        v63 = 0;
      }
      v87 = (const unsigned __int16 *)*((_QWORD *)v63 + 7);
      if ( Common::String::CaseInsensitiveEquals(v87, L"AppxManifest.xml")
        || Common::String::CaseInsensitiveEquals(v87, L"AppxContentGroupMap.xml") )
      {
        Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::SetMessageCopy(
          (Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v159,
          v87);
        v89 = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(v12, v63, 0, v88, 0x10000u);
        v90 = v89;
        if ( v89 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EF,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)v89,
            v114);
          goto LABEL_166;
        }
        v125 = 0;
        *(_QWORD *)v135 = 0;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v125);
        v113 = (unsigned __int16 *)v135;
        OpcFileStream = Appx::Packaging::TryGetOpcFileStream(v140, v139, v87, &v125);
        v90 = OpcFileStream;
        if ( OpcFileStream < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F3,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)OpcFileStream,
            (int)v135);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v125);
LABEL_166:
          Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
          v104 = v116;
          v116 = 0;
          if ( v104 )
            Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(
              v104,
              v102,
              v103);
          started = v90;
          goto LABEL_178;
        }
        if ( !*(_QWORD *)v135 )
        {
          started = -2146958834;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F4,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)0x8008020ELL,
            (int)v135);
          v77 = (Appx::Packaging **)&v125;
          goto LABEL_110;
        }
        v117 = 0;
        v132 = &v117;
        v133 = 0;
        LOBYTE(v134) = 1;
        appended = Appx::Packaging::FileNameHelper::ConvertFileNameToOpcUtf8(v87, &v133);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v132);
        if ( appended < 0 )
        {
          v96 = 1015;
          goto LABEL_158;
        }
        v93 = -1;
        do
          ++v93;
        while ( *((_BYTE *)v117 + v93) );
        LODWORD(v113) = v125;
        appended = Appx::Packaging::ZipEditor::AppendFileStreamToArchive(v8, v93, v117);
        if ( appended < 0 )
        {
          v96 = 1018;
LABEL_158:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v96,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)appended,
            (int)v113);
          v98 = v117;
          v117 = 0;
          if ( v98 )
            operator delete(v98, v97);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v125);
          Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
          v101 = v116;
          v116 = 0;
          if ( v101 )
            Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(
              v101,
              v99,
              v100);
          started = appended;
          goto LABEL_178;
        }
        v95 = v117;
        v117 = 0;
        if ( v95 )
          operator delete(v95, v94);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v125);
      }
      v24 = v123;
      v23 = v122[0];
    }
    v60 = Appx::Packaging::BlockMap::BlockMapXmlWriter::EndBlockMap(v12);
    started = v60;
    if ( v60 < 0 )
    {
      v86 = 1022;
      goto LABEL_173;
    }
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
      v159,
      L"AppxBlockMap.xml");
    Appx::Packaging::details::SendPackagingContextToSink(
      (Appx::Packaging::details *)(v160 + 40),
      0,
      (const unsigned __int16 *)1,
      v105);
    LODWORD(v113) = *(_DWORD *)v130;
    v60 = Appx::Packaging::ZipEditor::AppendFileStreamToArchive(v8, 16, "AppxBlockMap.xml");
    started = v60;
    if ( v60 < 0 )
    {
      v86 = 1027;
      goto LABEL_173;
    }
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
      v159,
      L"Done");
    Appx::Packaging::details::SendPackagingContextToSink(
      (Appx::Packaging::details *)(v160 + 40),
      0,
      (const unsigned __int16 *)3,
      v107);
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v159);
    Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
    v110 = v116;
    v116 = 0;
    if ( v110 )
      Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(
        v110,
        v108,
        v109);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v130);
    Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v12, v111);
    Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::~AppendDeltaAndUpdatedBlockMapToPackage((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v159);
    return 0;
  }
  while ( 1 )
  {
    v25 = *(_QWORD *)(*(_QWORD *)(v22 + 16) + 8LL);
    v26 = *(unsigned __int16 **)(v25 + 56);
    v27 = *(_QWORD *)(v25 + 72);
    if ( Common::String::CaseInsensitiveEquals(v26, L"AppxManifest.xml")
      || Common::String::CaseInsensitiveEquals(v26, L"AppxContentGroupMap.xml") )
    {
      v60 = Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(
              v122,
              v24 + 1);
      started = v60;
      if ( v60 < 0 )
      {
        v86 = 849;
LABEL_173:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v86,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
          (const char *)(unsigned int)v60,
          (int)v113);
        goto LABEL_174;
      }
      v61 = v123;
      *(_QWORD *)(v122[0] + 8 * v123) = v25;
      v24 = v61 + 1;
      v123 = v24;
      goto LABEL_77;
    }
    Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::SetMessageCopy(
      (Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v159,
      v26);
    v137 = 0;
    if ( (int)Appx::Packaging::BlockMap::AppxBlockMapReader::GetFileInternal(
                (Appx::Packaging::BlockMap::AppxBlockMapReader *)v7,
                v26,
                &v137) >= 0 )
      break;
    v128 = 0;
    *(_QWORD *)v141 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v128);
    v56 = Appx::Packaging::TryGetOpcFileStream(v140, v139, v26, &v128);
    started = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v56,
        (int)v141);
      v77 = &v128;
      goto LABEL_110;
    }
    v121 = 0;
    LocalFileItemInfo = Appx::Packaging::AppendWholeDeltaFileToPackage(
                          v128,
                          (struct IStream *)v26,
                          v136,
                          v138,
                          (const unsigned __int16 *)&v121,
                          v115);
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v84 = 985;
LABEL_135:
      v85 = (unsigned int)LocalFileItemInfo;
LABEL_136:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v84,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)v85,
        (int)v113);
      v68 = &v128;
LABEL_91:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v68);
LABEL_174:
      Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
      goto LABEL_175;
    }
    v58 = v121;
    if ( *((_QWORD *)v121 + 3) != v27 )
    {
      started = -2147418113;
      v84 = 986;
      v85 = 2147549183LL;
      goto LABEL_136;
    }
    v121 = 0;
    LocalFileItemInfo = Appx::Packaging::ZipFileItem::GetLocalFileItemInfo(v58, &v121);
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v84 = 990;
      goto LABEL_135;
    }
    LocalFileItemInfo = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(
                          v12,
                          (const struct Appx::Packaging::BlockMap::AppxBlockMapFile *)v25,
                          *(unsigned __int16 *)v121,
                          v59,
                          *(_QWORD *)(v25 + 96));
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v84 = 991;
      goto LABEL_135;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v128);
LABEL_77:
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(v116);
    v22 = v116;
    if ( !*(_BYTE *)(v116 + 24) )
    {
      v23 = v122[0];
      v8 = v136;
      goto LABEL_79;
    }
  }
  v118 = 0;
  v121 = 0;
  v117 = 0;
  *(_OWORD *)v126 = 0;
  v127 = 0;
  v28 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v126, v26);
  started = v28;
  if ( v28 < 0 )
  {
    v82 = 869;
LABEL_129:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v82,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v28,
      (int)v113);
    if ( v126[1] )
      operator delete(v126[1], v83);
LABEL_109:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
    v77 = &v118;
LABEL_110:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v77);
    Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
    v74 = v116;
    v116 = 0;
    goto LABEL_176;
  }
  v133 = (char *)v126;
  v132 = &Common::StringBufferBuilder::`vftable';
  v134 = v126;
  v28 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v132, L".blockcache");
  started = v28;
  if ( v28 < 0 )
  {
    v82 = 870;
    goto LABEL_129;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v118);
  v113 = (unsigned __int16 *)&v121;
  v28 = Appx::Packaging::TryGetOpcFileStream(v140, v139, v126[1], &v118);
  started = v28;
  if ( v28 < 0 )
  {
    v82 = 871;
    goto LABEL_129;
  }
  v30 = v121;
  v147 = 17988;
  v148 = 1;
  v149 = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  if ( !v121 )
  {
    v39 = 0;
    v129 = 0;
    if ( v27 < *((_QWORD *)v137 + 9) )
      goto LABEL_36;
    v42 = 0;
    if ( *((_BYTE *)v137 + 159) )
      goto LABEL_36;
    goto LABEL_37;
  }
  v119 = 0;
  v132 = (void **)&v119;
  v31 = *((_QWORD *)v136 + 7);
  v133 = 0;
  LOBYTE(v134) = 1;
  started = Appx::Packaging::GetAppendedBlockcacheFileName(
              (Appx::Packaging *)v26,
              v157,
              (const unsigned __int16 *)&v133,
              v29);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v132);
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)&v121);
    v76 = v119;
    v119 = 0;
    if ( v76 )
      operator delete(v76, v75);
LABEL_107:
    if ( v126[1] )
      operator delete(v126[1], v75);
    goto LABEL_109;
  }
  v132 = &v120;
  v120 = 0;
  v133 = 0;
  LOBYTE(v134) = 1;
  started = Appx::Packaging::FileNameHelper::ConvertFileNameToOpcUtf8(v119, &v133);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v132);
  if ( started < 0 )
  {
    v64 = 882;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v64,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)v113);
    v66 = v120;
    v120 = 0;
    if ( v66 )
      operator delete(v66, v65);
    v67 = v119;
    v119 = 0;
    if ( v67 )
      operator delete(v67, v65);
    goto LABEL_88;
  }
  v32 = -1;
  v33 = *((_DWORD *)v30 + 10);
  v121 = 0;
  do
    ++v32;
  while ( *((_BYTE *)v120 + v32) );
  LODWORD(v113) = v33;
  v34 = Appx::Packaging::ZipEditor::AppendZippedFileStreamToArchive(v136, v32, v120, 0);
  started = v34;
  if ( v34 >= 0 )
  {
    *(_QWORD *)v135 = 0;
    v35 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v118 + 40LL))(v118, 0, 0, 0);
    started = v35;
    if ( v35 < 0 )
    {
      v70 = (unsigned int)v35;
      v69 = 890;
      goto LABEL_93;
    }
    Entry = Appx::Packaging::BlockMapDeltaFileEntry::ReadEntry(
              v118,
              (struct Appx::Packaging::BlockMapDeltaFileEntry *)&v147);
    started = Entry;
    if ( Entry < 0 )
    {
      v70 = (unsigned int)Entry;
      v69 = 892;
      goto LABEL_93;
    }
    v131 = 0;
    v37 = Appx::Packaging::ZipFileItem::GetLocalFileItemInfo(v121, &v131);
    started = v37;
    if ( v37 < 0 )
    {
      v70 = (unsigned int)v37;
      v69 = 896;
      goto LABEL_93;
    }
    v38 = v31 + *(unsigned __int16 *)v131;
    if ( v38 < v31 )
    {
      started = -2147024362;
      v69 = 898;
      v70 = 2147942934LL;
      goto LABEL_93;
    }
    v39 = (char *)v155 + v38;
    v129 = (char *)v155 + v38;
    if ( (unsigned __int64)v155 + v38 < v38 )
    {
      started = -2147024362;
      v64 = 899;
      goto LABEL_84;
    }
    v40 = v120;
    v120 = 0;
    if ( v40 )
      operator delete(v40, v38);
    v41 = v119;
    v119 = 0;
    if ( v41 )
      operator delete(v41, v38);
LABEL_36:
    v42 = 1;
LABEL_37:
    StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(
                              v12,
                              v26,
                              v27,
                              *(_DWORD *)(v25 + 88),
                              v42,
                              *(_QWORD *)(v25 + 96));
    v44 = 0;
    started = StreamCurrentPosition;
    if ( StreamCurrentPosition < 0 )
    {
      v78 = 908;
      goto LABEL_112;
    }
    v142 = 16964;
    v144 = 0;
    v45 = 0;
    v46 = *(_QWORD *)(v25 + 120);
    v47 = 0;
    *(_QWORD *)v141 = v46;
    v143 = 1;
    v145 = 0;
    v146 = 0;
    v131 = 0;
    v121 = 0;
    while ( 1 )
    {
      LODWORD(v125) = v45;
      if ( v47 == v46 )
        break;
      if ( v47 < *(_QWORD *)(v25 + 120) )
      {
        _mm_lfence();
        v44 = *(_QWORD *)(*(_QWORD *)(v25 + 104) + 8 * v47);
      }
      v48 = 0;
      if ( (unsigned __int64)v45 >= *((_QWORD *)v137 + 15) )
        goto LABEL_49;
      _mm_lfence();
      v49 = *(_QWORD *)(*((_QWORD *)v137 + 13) + 8LL * v45);
      if ( !v49 )
        goto LABEL_49;
      if ( *(_BYTE *)(v44 + 48) )
        v48 = *(_DWORD *)(v49 + 28);
      v50 = *(_DWORD *)(v49 + 36);
      if ( v50 == *(_DWORD *)(v44 + 36) && !memcmp_0(*(const void **)(v49 + 56), *(const void **)(v44 + 56), v50) )
      {
        v51 = *(_QWORD *)(v49 + 40);
      }
      else
      {
LABEL_49:
        if ( !v118 )
        {
          started = -2146958834;
          v80 = 941;
LABEL_116:
          v81 = (unsigned int)started;
LABEL_117:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v80,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)v81,
            (int)v113);
          goto LABEL_107;
        }
        v51 = (unsigned __int64)&v39[v146];
        if ( v51 < (unsigned __int64)v129 )
        {
          started = -2147024362;
          v80 = 944;
          goto LABEL_116;
        }
        v52 = Appx::Packaging::BlockMapDeltaBlockEntry::ReadEntry(
                v118,
                (struct Appx::Packaging::BlockMapDeltaBlockEntry *)&v142,
                0);
        started = v52;
        if ( v52 < 0 )
        {
          v81 = (unsigned int)v52;
          v80 = 948;
          goto LABEL_117;
        }
        if ( v145 != v131 )
        {
          v80 = 949;
LABEL_115:
          started = -2146958833;
          goto LABEL_116;
        }
        if ( v146 != *(_DWORD *)(v44 + 24) )
        {
          v80 = 950;
          goto LABEL_115;
        }
        v121 = (Appx::Packaging::ZipFileItem *)((char *)v121 + 1);
        v129 = (char *)v51;
      }
      if ( *(_BYTE *)(v44 + 48) )
        v53 = *(_DWORD *)(v44 + 24);
      else
        v53 = 0;
      StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddBlockWithPackageOffset(
                                v12,
                                *(const unsigned __int8 **)(v44 + 56),
                                *(_DWORD *)(v44 + 36),
                                v53,
                                v51,
                                v48);
      v44 = 0;
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v78 = 958;
        goto LABEL_112;
      }
      v131 = (struct Appx::Packaging::ZipLocalFileItemInfo *)((char *)v131 + 0x10000);
      v45 = v125 + 1;
      v39 = v129;
      ++v47;
      v46 = *(_QWORD *)v141;
    }
    StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::CloseFile(v12, 0, 0);
    started = StreamCurrentPosition;
    if ( StreamCurrentPosition < 0 )
    {
      v78 = 965;
      goto LABEL_112;
    }
    if ( !v118 )
    {
LABEL_66:
      if ( v126[1] )
        operator delete(v126[1], v54);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v118);
      v24 = v123;
      v7 = v158;
      goto LABEL_77;
    }
    if ( v121 == v156 )
    {
      StreamCurrentPosition = Appx::Packaging::BlockMapDeltaBlockEntry::ReadEntry(
                                v118,
                                (struct Appx::Packaging::BlockMapDeltaBlockEntry *)&v142,
                                1);
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v78 = 972;
LABEL_112:
        v79 = (unsigned int)StreamCurrentPosition;
        goto LABEL_113;
      }
      v121 = 0;
      StreamCurrentPosition = Appx::Packaging::GetStreamCurrentPosition(v118, (struct IStream *)&v121, v55);
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v78 = 974;
        goto LABEL_112;
      }
      if ( v121 != v155 )
      {
        started = -2146958833;
        v78 = 975;
        v79 = 2148008463LL;
        goto LABEL_113;
      }
      goto LABEL_66;
    }
    started = -2146958833;
    v78 = 970;
    v79 = 2148008463LL;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v78,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)v79,
      (int)v113);
LABEL_88:
    if ( v126[1] )
      operator delete(v126[1], v65);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
    v68 = &v118;
    goto LABEL_91;
  }
  v70 = (unsigned int)v34;
  v69 = 887;
LABEL_93:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v69,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
    (const char *)v70,
    (int)v113);
  v72 = v120;
  v120 = 0;
  if ( v72 )
    operator delete(v72, v71);
  v73 = v119;
  v119 = 0;
  if ( v73 )
    operator delete(v73, v71);
  if ( v126[1] )
    operator delete(v126[1], v71);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v118);
  Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v122);
  v74 = v116;
  v116 = 0;
LABEL_176:
  if ( v74 )
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'(
      v74,
      v20,
      v21);
LABEL_178:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v130);
  Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v12, v106);
LABEL_183:
  Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::~AppendDeltaAndUpdatedBlockMapToPackage((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v159);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800b7f58  push    rbp
0x1800b7f5a  push    rbx
0x1800b7f5b  push    rsi
0x1800b7f5c  push    rdi
0x1800b7f5d  push    r12
0x1800b7f5f  push    r13
0x1800b7f61  push    r14
0x1800b7f63  push    r15
0x1800b7f65  lea     rbp, [rsp-218h]
0x1800b7f6d  sub     rsp, 318h
0x1800b7f74  mov     rax, cs:__security_cookie
0x1800b7f7b  xor     rax, rsp
0x1800b7f7e  mov     [rbp+250h+var_50], rax
0x1800b7f85  mov     rax, [rbp+250h+arg_20]
0x1800b7f8c  mov     r12, rdx
0x1800b7f8f  mov     r13, [rbp+250h+arg_28]
0x1800b7f96  mov     rsi, rcx
0x1800b7f99  mov     r14, [rbp+250h+arg_30]
0x1800b7fa0  lea     rcx, [rbp+250h+var_1A0]; struct wil::details::IFailureCallback *
0x1800b7fa7  mov     [rbp+250h+var_1B0], rdx
0x1800b7fae  lea     rdx, aAppenddeltaand_0; "AppendDeltaAndUpdatedBlockMapToPackage"
0x1800b7fb5  mov     [rbp+250h+var_228], rax
0x1800b7fb9  mov     [rbp+250h+var_240], r13
0x1800b7fbd  mov     [rbp+250h+var_230], r14
0x1800b7fc1  mov     [rbp+250h+var_220], r9
0x1800b7fc5  mov     [rbp+250h+var_1B8], r8
0x1800b7fcc  call    ??0?$ActivityBase@VAppxPackagingProvider@Packaging@Appx@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800b7fd1  lea     rax, ??_7AppendDeltaAndUpdatedBlockMapToPackage@AppxPackagingProvider@Packaging@Appx@@6B@; const Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::`vftable'
0x1800b7fd8  lea     rcx, [rbp+250h+var_1A0]; this
0x1800b7fdf  mov     [rbp+250h+var_1A0], rax
0x1800b7fe6  call    ?StartActivity@AppendDeltaAndUpdatedBlockMapToPackage@AppxPackagingProvider@Packaging@Appx@@QEAAXXZ; Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::StartActivity(void)
0x1800b7feb  lea     rdx, aAppendingFileD; "Appending file deltas"
0x1800b7ff2  lea     rcx, [rbp+250h+var_1A0]
0x1800b7ff9  call    ?SetMessage@?$ActivityBase@VAppxPackagingProvider@Packaging@Appx@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXPEBG@Z; wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(ushort const *)
0x1800b7ffe  mov     rcx, [rbp+250h+var_90]
0x1800b8005  xor     r8d, r8d; unsigned __int16 *
0x1800b8008  add     rcx, 28h ; '('; this
0x1800b800c  xor     edx, edx; struct wil::CallContextInfo *
0x1800b800e  call    ?SendPackagingContextToSink@details@Packaging@Appx@@YAXAEBUCallContextInfo@wil@@PEBGW4APPX_PACKAGING_CONTEXT_CHANGE_TYPE@@@Z; Appx::Packaging::details::SendPackagingContextToSink(wil::CallContextInfo const &,ushort const *,APPX_PACKAGING_CONTEXT_CHANGE_TYPE)
0x1800b8013  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b801a  mov     ecx, 88h; unsigned __int64
0x1800b801f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8024  test    rax, rax
0x1800b8027  jz      loc_1800B8E14
0x1800b802d  mov     rcx, rax; this
0x1800b8030  call    ??0BlockMapXmlWriter@BlockMap@Packaging@Appx@@QEAA@XZ; Appx::Packaging::BlockMap::BlockMapXmlWriter::BlockMapXmlWriter(void)
0x1800b8035  mov     r15, rax
0x1800b8038  test    rax, rax
0x1800b803b  jz      loc_1800B8E14
0x1800b8041  lea     rcx, [rbp+250h+var_270]
0x1800b8045  mov     qword ptr [rbp+250h+var_270], 0
0x1800b804d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b8052  lea     r8, [rbp+250h+var_270]; unsigned __int16 *
0x1800b8056  mov     rcx, r14; this
0x1800b8059  lea     rdx, aTempappxblockm; "TempAppxBlockMap"
0x1800b8060  call    ?CreateTempFileStream@Packaging@Appx@@YAJPEBG0PEAPEAUIStream@@@Z; Appx::Packaging::CreateTempFileStream(ushort const *,ushort const *,IStream * *)
0x1800b8065  mov     ebx, eax
0x1800b8067  test    eax, eax
0x1800b8069  jns     short loc_1800B8075
0x1800b806b  mov     r9d, eax
0x1800b806e  mov     edx, 33Bh
0x1800b8073  jmp     short loc_1800B80CA
0x1800b8075  mov     edi, [r12+10h]
0x1800b807a  lea     rcx, [rbp+250h+var_278]
0x1800b807e  mov     rbx, [r12+18h]
0x1800b8083  mov     eax, 2
0x1800b8088  cmp     edi, eax
0x1800b808a  cmovl   edi, eax
0x1800b808d  mov     rax, qword ptr [rbp+250h+var_270]
0x1800b8091  mov     [rbp+250h+var_278], rax
0x1800b8095  call    ?InternalAddRef@?$ComPtr@UIXMLDOMNodeList@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(void)
0x1800b809a  mov     r9d, edi
0x1800b809d  mov     byte ptr [rsp+350h+var_330], 0; int
0x1800b80a2  mov     r8, rbx
0x1800b80a5  lea     rdx, [rbp+250h+var_278]
0x1800b80a9  mov     rcx, r15
0x1800b80ac  call    ?StartBlockMap@BlockMapXmlWriter@BlockMap@Packaging@Appx@@QEAAJAEBV?$ComPtr@UIStream@@@WRL@Microsoft@@PEBGW4BlockMapVersion@234@_N@Z; Appx::Packaging::BlockMap::BlockMapXmlWriter::StartBlockMap(Microsoft::WRL::ComPtr<IStream> const &,ushort const *,Appx::Packaging::BlockMap::BlockMapVersion,bool)
0x1800b80b1  lea     rcx, [rbp+250h+var_278]
0x1800b80b5  mov     ebx, eax
0x1800b80b7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b80bc  xor     edi, edi
0x1800b80be  test    ebx, ebx
0x1800b80c0  jns     short loc_1800B80E2
0x1800b80c2  mov     r9d, ebx; char *
0x1800b80c5  mov     edx, 33Eh; void *
0x1800b80ca  mov     rcx, [rbp+258h]; this
0x1800b80d1  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b80d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b80dd  jmp     loc_1800B8D8B
0x1800b80e2  lea     rax, [rsp+350h+var_2F0]
0x1800b80e7  mov     [rsp+350h+var_2F0], rdi
0x1800b80ec  lea     rdx, [rbp+250h+var_298+8]
0x1800b80f0  mov     [rbp+250h+var_298], rax
0x1800b80f4  mov     rcx, rsi
0x1800b80f7  mov     [rbp+250h+var_298+8], rdi
0x1800b80fb  mov     byte ptr [rbp+250h+var_288], 1
0x1800b80ff  call    ?GetFilesInternal@AppxBlockMapReader@BlockMap@Packaging@Appx@@QEAAJPEAPEAV?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@34@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> * *)
0x1800b8104  lea     rcx, [rbp+250h+var_298]
0x1800b8108  mov     ebx, eax
0x1800b810a  call    ??1?$out_param_t@V?$unique_ptr@V?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@U?$default_delete@V?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>(void)
0x1800b810f  test    ebx, ebx
0x1800b8111  jns     short loc_1800B8133
0x1800b8113  mov     rcx, [rbp+258h]; this
0x1800b811a  lea     r8, aOnecorePrintsc_192; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b8121  mov     r9d, ebx; char *
0x1800b8124  mov     edx, 341h; void *
0x1800b8129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b812e  jmp     loc_1800B8D77
0x1800b8133  mov     rax, [rsp+350h+var_2F0]
0x1800b8138  mov     rcx, rdi
0x1800b813b  mov     [rbp+250h+var_2C0], rcx
0x1800b813f  mov     rsi, rdi
0x1800b8142  mov     [rbp+250h+var_2B8], rdi
0x1800b8146  mov     [rbp+250h+var_2B0], rdi
0x1800b814a  mov     [rbp+250h+var_2A8], dil
0x1800b814e  cmp     [rax+18h], dil
0x1800b8152  jz      loc_1800B8788
0x1800b8158  mov     rcx, [rax+10h]
0x1800b815c  lea     rdx, ?FileName@Manifest@Packaging@Appx@@3QBGB; "AppxManifest.xml"
0x1800b8163  mov     r14, [rcx+8]
0x1800b8167  mov     rdi, [r14+38h]
0x1800b816b  mov     r13, [r14+48h]
0x1800b816f  mov     rcx, rdi; unsigned __int16 *
0x1800b8172  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800b8177  xor     ebx, ebx
0x1800b8179  test    eax, eax
0x1800b817b  jnz     loc_1800B8737
0x1800b8181  lea     rdx, ?FileName@ContentGroupMap@Packaging@Appx@@3QBGB; "AppxContentGroupMap.xml"
0x1800b8188  mov     rcx, rdi; unsigned __int16 *
0x1800b818b  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800b8190  test    eax, eax
0x1800b8192  jnz     loc_1800B8737
0x1800b8198  mov     rdx, rdi; unsigned __int16 *
0x1800b819b  lea     rcx, [rbp+250h+var_1A0]; this
0x1800b81a2  call    ?SetMessageCopy@AppendDeltaAndUpdatedBlockMapToPackage@AppxPackagingProvider@Packaging@Appx@@QEAAXPEBG@Z; Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::SetMessageCopy(ushort const *)
0x1800b81a7  lea     r8, [rbp+250h+var_238]; struct Appx::Packaging::BlockMap::AppxBlockMapFile **
0x1800b81ab  mov     [rbp+250h+var_238], rbx
0x1800b81af  mov     rdx, rdi; unsigned __int16 *
0x1800b81b2  mov     rcx, r12; this
0x1800b81b5  call    ?GetFileInternal@AppxBlockMapReader@BlockMap@Packaging@Appx@@QEAAJPEBGPEAPEAVAppxBlockMapFile@234@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::GetFileInternal(ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile * *)
0x1800b81ba  test    eax, eax
0x1800b81bc  js      loc_1800B8678
0x1800b81c2  xor     r12d, r12d
0x1800b81c5  lea     rcx, [rbp+250h+var_298]; this
0x1800b81c9  xorps   xmm0, xmm0
0x1800b81cc  mov     [rsp+350h+var_2E0], r12
0x1800b81d1  mov     rdx, rdi; unsigned __int16 *
0x1800b81d4  mov     [rbp+250h+var_2C8], r12
0x1800b81d8  mov     [rsp+350h+var_2E8], r12
0x1800b81dd  movups  xmmword ptr [rbp+250h+var_298], xmm0
0x1800b81e1  mov     [rbp+250h+var_288], r12d
0x1800b81e5  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800b81ea  mov     ebx, eax
0x1800b81ec  test    eax, eax
0x1800b81ee  js      loc_1800B8A4A
0x1800b81f4  lea     rax, [rbp+250h+var_298]
0x1800b81f8  mov     [rbp+250h+var_258], rax
0x1800b81fc  lea     rdx, aBlockcache; ".blockcache"
0x1800b8203  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x1800b820a  mov     [rbp+250h+var_260], rax
0x1800b820e  lea     rcx, [rbp+250h+var_260]; this
0x1800b8212  lea     rax, [rbp+250h+var_298]
0x1800b8216  mov     [rbp+250h+var_250], rax
0x1800b821a  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1800b821f  mov     ebx, eax
0x1800b8221  test    eax, eax
0x1800b8223  js      loc_1800B8A43
0x1800b8229  lea     rcx, [rsp+350h+var_2E0]
0x1800b822e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b8233  mov     r8, [rbp+250h+var_298+8]
0x1800b8237  lea     rax, [rbp+250h+var_2C8]
0x1800b823b  mov     rdx, [rbp+250h+var_228]
0x1800b823f  lea     r9, [rsp+350h+var_2E0]
0x1800b8244  mov     rcx, [rbp+250h+var_220]
0x1800b8248  mov     [rsp+350h+var_330], rax; int
0x1800b824d  call    ?TryGetOpcFileStream@Packaging@Appx@@YAJPEAUIOpcPackage@@PEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBGPEAPEAUIStream@@PEAPEBUAppxFileInfo@Consumption@12@@Z; Appx::Packaging::TryGetOpcFileStream(IOpcPackage *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,IStream * *,Appx::Packaging::Consumption::AppxFileInfo const * *)
0x1800b8252  mov     ebx, eax
0x1800b8254  test    eax, eax
0x1800b8256  js      loc_1800B89EE
0x1800b825c  mov     rsi, [rbp+250h+var_2C8]
0x1800b8260  xor     eax, eax
0x1800b8262  mov     [rbp+250h+var_1F0], 4644h
0x1800b8269  mov     [rbp+250h+var_1EC], 1
0x1800b8271  mov     [rbp+250h+var_1E4], r12d
0x1800b8275  mov     [rbp+250h+var_1E0], r12w
0x1800b827a  mov     [rbp+250h+var_1DE], eax
0x1800b827d  mov     [rbp+250h+var_1DA], ax
0x1800b8281  mov     [rbp+250h+var_1D8], r12
0x1800b8285  mov     [rbp+250h+var_1D0], r12
0x1800b828c  mov     [rbp+250h+var_1C8], r12
0x1800b8293  mov     [rbp+250h+var_1C0], r12
0x1800b829a  test    rsi, rsi
0x1800b829d  jz      loc_1800B8446
0x1800b82a3  mov     r12, [rbp+250h+var_240]
0x1800b82a7  lea     r8, [rbp+250h+var_258]; unsigned __int16 *
0x1800b82ab  mov     rdx, [rbp+250h+var_1B8]; unsigned __int16 *
0x1800b82b2  mov     rcx, rdi; this
0x1800b82b5  mov     [rsp+350h+var_2D8], rax
0x1800b82ba  lea     rax, [rsp+350h+var_2D8]
0x1800b82bf  mov     [rbp+250h+var_260], rax
0x1800b82c3  mov     r12, [r12+38h]
0x1800b82c8  mov     [rbp+250h+var_258], 0
0x1800b82d0  mov     byte ptr [rbp+250h+var_250], 1
0x1800b82d4  call    ?GetAppendedBlockcacheFileName@Packaging@Appx@@YAJPEBG0PEAPEBG@Z; Appx::Packaging::GetAppendedBlockcacheFileName(ushort const *,ushort const *,ushort const * *)
0x1800b82d9  lea     rcx, [rbp+250h+var_260]
0x1800b82dd  mov     ebx, eax
0x1800b82df  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@$$CBGU?$default_delete@$$BY0A@$$CBG@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort const [0],wistd::default_delete<ushort const [0]>>>::~out_param_t<wistd::unique_ptr<ushort const [0],wistd::default_delete<ushort const [0]>>>(void)
0x1800b82e4  test    ebx, ebx
0x1800b82e6  js      loc_1800B88CC
0x1800b82ec  mov     rcx, [rsp+350h+var_2D8]; unsigned __int16 *
0x1800b82f1  lea     rax, [rbp+250h+var_2D0]
0x1800b82f5  lea     rdx, [rbp+250h+var_258]; char **
0x1800b82f9  mov     [rbp+250h+var_260], rax
0x1800b82fd  mov     [rbp+250h+var_2D0], 0
0x1800b8305  mov     [rbp+250h+var_258], 0
0x1800b830d  mov     byte ptr [rbp+250h+var_250], 1
0x1800b8311  call    ?ConvertFileNameToOpcUtf8@FileNameHelper@Packaging@Appx@@SAJPEBGPEAPEAD@Z; Appx::Packaging::FileNameHelper::ConvertFileNameToOpcUtf8(ushort const *,char * *)
0x1800b8316  lea     rcx, [rbp+250h+var_260]
0x1800b831a  mov     ebx, eax
0x1800b831c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@$$CBGU?$default_delete@$$BY0A@$$CBG@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort const [0],wistd::default_delete<ushort const [0]>>>::~out_param_t<wistd::unique_ptr<ushort const [0],wistd::default_delete<ushort const [0]>>>(void)
0x1800b8321  test    ebx, ebx
0x1800b8323  js      loc_1800B88C2
0x1800b8329  mov     rcx, [rsi+18h]
0x1800b832d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b8331  mov     r9, [rsi+20h]
0x1800b8335  mov     r10d, [rsi+28h]
0x1800b8339  xor     esi, esi
0x1800b833b  mov     rax, [rsp+350h+var_2E0]
0x1800b8340  mov     r8, [rbp+250h+var_2D0]
0x1800b8344  mov     [rbp+250h+var_2C8], 0
0x1800b834c  inc     rdx
0x1800b834f  cmp     [r8+rdx], sil
0x1800b8353  jnz     short loc_1800B834C
0x1800b8355  lea     r11, [rbp+250h+var_2C8]
0x1800b8359  mov     [rsp+350h+var_300], r11
0x1800b835e  mov     r11, [rbp+250h+var_230]
0x1800b8362  mov     [rsp+350h+var_308], r11
0x1800b8367  mov     [rsp+350h+var_318], rax
0x1800b836c  mov     [rsp+350h+var_320], rcx
0x1800b8371  mov     rcx, [rbp+250h+var_240]
0x1800b8375  mov     qword ptr [rsp+350h+var_328], r9
0x1800b837a  xor     r9d, r9d
0x1800b837d  mov     dword ptr [rsp+350h+var_330], r10d; int
0x1800b8382  call    ?AppendZippedFileStreamToArchive@ZipEditor@Packaging@Appx@@QEAAJIPEBDW4ZipCompressionType@23@I_K2PEAUIStream@@PEBU_FILETIME@@PEBGPEAPEAVZipFileItem@23@@Z; Appx::Packaging::ZipEditor::AppendZippedFileStreamToArchive(uint,char const *,Appx::Packaging::ZipCompressionType,uint,unsigned __int64,unsigned __int64,IStream *,_FILETIME const *,ushort const *,Appx::Packaging::ZipFileItem * *)
0x1800b8387  mov     ebx, eax
0x1800b8389  test    eax, eax
0x1800b838b  js      loc_1800B88B5
0x1800b8391  mov     rcx, [rsp+350h+var_2E0]
0x1800b8396  xor     r9d, r9d
0x1800b8399  xor     r8d, r8d
0x1800b839c  mov     qword ptr [rbp+250h+var_248], rsi
0x1800b83a0  mov     rdx, rsi
0x1800b83a3  mov     rax, [rcx]
0x1800b83a6  mov     rax, [rax+28h]
0x1800b83aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b83af  mov     ebx, eax
0x1800b83b1  test    eax, eax
0x1800b83b3  js      loc_1800B88A8
0x1800b83b9  mov     rcx, [rsp+350h+var_2E0]; struct IStream *
0x1800b83be  lea     rdx, [rbp+250h+var_1F0]; struct Appx::Packaging::BlockMapDeltaFileEntry *
0x1800b83c2  call    ?ReadEntry@BlockMapDeltaFileEntry@Packaging@Appx@@SAJPEAUIStream@@AEAU123@@Z; Appx::Packaging::BlockMapDeltaFileEntry::ReadEntry(IStream *,Appx::Packaging::BlockMapDeltaFileEntry &)
0x1800b83c7  mov     ebx, eax
0x1800b83c9  test    eax, eax
0x1800b83cb  js      loc_1800B889B
0x1800b83d1  mov     rcx, [rbp+250h+var_2C8]; this
0x1800b83d5  lea     rdx, [rbp+250h+var_268]; struct Appx::Packaging::ZipLocalFileItemInfo **
0x1800b83d9  mov     [rbp+250h+var_268], rsi
0x1800b83dd  call    ?GetLocalFileItemInfo@ZipFileItem@Packaging@Appx@@QEBAJPEAPEBUZipLocalFileItemInfo@23@@Z; Appx::Packaging::ZipFileItem::GetLocalFileItemInfo(Appx::Packaging::ZipLocalFileItemInfo const * *)
0x1800b83e2  mov     ebx, eax
0x1800b83e4  test    eax, eax
0x1800b83e6  js      loc_1800B8891
0x1800b83ec  mov     rax, [rbp+250h+var_268]
0x1800b83f0  movzx   edx, word ptr [rax]
0x1800b83f3  add     rdx, r12; unsigned __int64
0x1800b83f6  cmp     rdx, r12
0x1800b83f9  jb      loc_1800B8811
0x1800b83ff  mov     rsi, [rbp+250h+var_1C8]
0x1800b8406  add     rsi, rdx
0x1800b8409  mov     [rbp+250h+var_278], rsi
0x1800b840d  cmp     rsi, rdx
0x1800b8410  jb      loc_1800B87A2
0x1800b8416  mov     rcx, [rbp+250h+var_2D0]; void *
0x1800b841a  mov     [rbp+250h+var_2D0], 0
0x1800b8422  test    rcx, rcx
0x1800b8425  jz      short loc_1800B842C
0x1800b8427  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b842c  mov     rcx, [rsp+350h+var_2D8]; void *
0x1800b8431  mov     [rsp+350h+var_2D8], 0
0x1800b843a  test    rcx, rcx
0x1800b843d  jz      short loc_1800B8463
0x1800b843f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b8444  jmp     short loc_1800B8463
0x1800b8446  mov     rax, [rbp+250h+var_238]
0x1800b844a  mov     rsi, r12
0x1800b844d  mov     [rbp+250h+var_278], r12
0x1800b8451  cmp     r13, [rax+48h]
0x1800b8455  jb      short loc_1800B8463
0x1800b8457  mov     cl, r12b
0x1800b845a  cmp     [rax+9Fh], r12b
0x1800b8461  jz      short loc_1800B8465
  ... truncated ...
```
