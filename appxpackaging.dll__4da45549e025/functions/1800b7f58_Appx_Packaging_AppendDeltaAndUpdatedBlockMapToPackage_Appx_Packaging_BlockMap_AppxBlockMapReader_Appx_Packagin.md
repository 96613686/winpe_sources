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
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rsi
  __int64 v23; // r14
  unsigned __int16 *v24; // rdi
  unsigned __int64 v25; // r13
  int v26; // eax
  const unsigned __int16 **v27; // r9
  Appx::Packaging::ZipFileItem *v28; // rsi
  unsigned __int64 v29; // r12
  __int64 v30; // rdx
  int v31; // r10d
  int v32; // eax
  int v33; // eax
  int Entry; // eax
  int v35; // eax
  unsigned __int64 v36; // rdx
  char *v37; // rsi
  void *v38; // rcx
  unsigned __int16 *v39; // rcx
  bool v40; // cl
  int StreamCurrentPosition; // eax
  __int64 v42; // rdi
  int v43; // ecx
  __int64 v44; // rax
  unsigned __int64 v45; // r12
  unsigned int v46; // r13d
  __int64 v47; // rbx
  unsigned int v48; // eax
  unsigned __int64 v49; // rsi
  int v50; // eax
  unsigned int v51; // r9d
  unsigned __int64 v52; // rdx
  unsigned __int64 *v53; // r8
  int v54; // eax
  int LocalFileItemInfo; // eax
  Appx::Packaging::ZipFileItem *v56; // rcx
  const unsigned __int16 *v57; // r9
  int v58; // eax
  __int64 v59; // rsi
  unsigned __int64 i; // rbx
  const struct Appx::Packaging::BlockMap::AppxBlockMapFile *v61; // rsi
  __int64 v62; // rdx
  unsigned __int64 v63; // rdx
  void *v64; // rcx
  unsigned __int16 *v65; // rcx
  Appx::Packaging **v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // r9
  unsigned __int64 v69; // rdx
  void *v70; // rcx
  unsigned __int16 *v71; // rcx
  __int64 v72; // rcx
  unsigned __int64 v73; // rdx
  unsigned __int16 *v74; // rcx
  Appx::Packaging **v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // r9
  __int64 v78; // rdx
  unsigned __int64 v79; // r9
  __int64 v80; // rdx
  unsigned __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // r9
  __int64 v84; // rdx
  const unsigned __int16 *v85; // rdi
  const unsigned __int16 *v86; // r9
  int v87; // eax
  int v88; // esi
  int OpcFileStream; // eax
  int appended; // edi
  __int64 v91; // rdx
  unsigned __int64 v92; // rdx
  void *v93; // rcx
  __int64 v94; // rdx
  unsigned __int64 v95; // rdx
  void *v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  enum APPX_PACKAGING_CONTEXT_CHANGE_TYPE v99; // r9d
  unsigned int v100; // edx
  enum APPX_PACKAGING_CONTEXT_CHANGE_TYPE v101; // r9d
  __int64 v102; // rcx
  unsigned int v103; // edx
  unsigned __int16 *v105; // [rsp+20h] [rbp-E0h]
  int v106; // [rsp+20h] [rbp-E0h]
  struct Appx::Packaging::ZipFileItem **v107; // [rsp+28h] [rbp-D8h]
  __int64 v108; // [rsp+60h] [rbp-A0h] BYREF
  void *v109; // [rsp+68h] [rbp-98h] BYREF
  struct IStream *v110; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v111; // [rsp+78h] [rbp-88h] BYREF
  void *v112; // [rsp+80h] [rbp-80h] BYREF
  Appx::Packaging::ZipFileItem *v113; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v114[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v115; // [rsp+A0h] [rbp-60h]
  char v116; // [rsp+A8h] [rbp-58h]
  __int64 v117; // [rsp+B0h] [rbp-50h] BYREF
  void *v118[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v119; // [rsp+C8h] [rbp-38h]
  Appx::Packaging *v120; // [rsp+D0h] [rbp-30h] BYREF
  char *v121; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v122[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct Appx::Packaging::ZipLocalFileItemInfo *v123; // [rsp+E8h] [rbp-18h] BYREF
  void **v124; // [rsp+F0h] [rbp-10h] BYREF
  char *v125; // [rsp+F8h] [rbp-8h] BYREF
  void **v126; // [rsp+100h] [rbp+0h]
  int v127[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 *v128; // [rsp+110h] [rbp+10h]
  struct Appx::Packaging::BlockMap::AppxBlockMapFile *v129; // [rsp+118h] [rbp+18h] BYREF
  struct Appx::Packaging::ZipEditor *v130; // [rsp+120h] [rbp+20h]
  __int64 v131; // [rsp+128h] [rbp+28h]
  __int64 v132; // [rsp+130h] [rbp+30h]
  int v133[2]; // [rsp+138h] [rbp+38h] BYREF
  int v134; // [rsp+140h] [rbp+40h] BYREF
  __int64 v135; // [rsp+144h] [rbp+44h]
  int v136; // [rsp+14Ch] [rbp+4Ch]
  struct Appx::Packaging::ZipLocalFileItemInfo *v137; // [rsp+150h] [rbp+50h]
  __int64 v138; // [rsp+158h] [rbp+58h]
  int v139; // [rsp+160h] [rbp+60h] BYREF
  __int64 v140; // [rsp+164h] [rbp+64h]
  int v141; // [rsp+16Ch] [rbp+6Ch]
  __int16 v142; // [rsp+170h] [rbp+70h]
  int v143; // [rsp+172h] [rbp+72h]
  __int16 v144; // [rsp+176h] [rbp+76h]
  __int64 v145; // [rsp+178h] [rbp+78h]
  __int64 v146; // [rsp+180h] [rbp+80h]
  Appx::Packaging::ZipFileItem *v147; // [rsp+188h] [rbp+88h]
  Appx::Packaging::ZipFileItem *v148; // [rsp+190h] [rbp+90h]
  unsigned __int16 *v149; // [rsp+198h] [rbp+98h]
  __int64 v150; // [rsp+1A0h] [rbp+A0h]
  _QWORD v151[34]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v152; // [rsp+2C0h] [rbp+1C0h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v7 = a2;
  v8 = a6;
  v150 = a2;
  v131 = a5;
  v128 = a6;
  v130 = a7;
  v132 = a4;
  v149 = a3;
  wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v151);
  v151[0] = &Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::`vftable';
  Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::StartActivity((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v151);
  wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
    v151,
    L"Appending file deltas");
  Appx::Packaging::details::SendPackagingContextToSink((Appx::Packaging::details *)(v152 + 40), 0, 0, v10);
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
      (int)v105);
    goto LABEL_183;
  }
  *(_QWORD *)v122 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
  TempFileStream = Appx::Packaging::CreateTempFileStream(a7, L"TempAppxBlockMap", v122, v13);
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
      (int)v105);
    goto LABEL_178;
  }
  v18 = *(_DWORD *)(v7 + 16);
  v19 = *(_QWORD *)(v7 + 24);
  if ( v18 < 2 )
    v18 = 2;
  v121 = *(char **)v122;
  Microsoft::WRL::ComPtr<IXMLDOMNodeList>::InternalAddRef(&v121);
  started = Appx::Packaging::BlockMap::BlockMapXmlWriter::StartBlockMap((_DWORD)v12, (unsigned int)&v121, v19, v18, 0);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v121);
  if ( started < 0 )
  {
    v16 = (unsigned int)started;
    v17 = 830;
    goto LABEL_9;
  }
  v108 = 0;
  v118[0] = &v108;
  v118[1] = 0;
  LOBYTE(v119) = 1;
  started = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(a1, &v118[1]);
  wil::details::out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>::~out_param_t<wistd::unique_ptr<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>,wistd::default_delete<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>>>(v118);
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x341,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)v105);
LABEL_175:
    v72 = v108;
    v108 = 0;
    goto LABEL_176;
  }
  v20 = v108;
  v21 = 0;
  v114[0] = 0;
  v22 = 0;
  v114[1] = 0;
  v115 = 0;
  v116 = 0;
  if ( !*(_BYTE *)(v108 + 24) )
  {
LABEL_79:
    for ( i = 0; i != v22; ++i )
    {
      if ( i < v22 )
      {
        _mm_lfence();
        v61 = *(const struct Appx::Packaging::BlockMap::AppxBlockMapFile **)(v21 + 8 * i);
      }
      else
      {
        v61 = 0;
      }
      v85 = (const unsigned __int16 *)*((_QWORD *)v61 + 7);
      if ( Common::String::CaseInsensitiveEquals(v85, L"AppxManifest.xml")
        || Common::String::CaseInsensitiveEquals(v85, L"AppxContentGroupMap.xml") )
      {
        Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::SetMessageCopy(
          (Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v151,
          v85);
        v87 = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(v12, v61, 0, v86, 0x10000u);
        v88 = v87;
        if ( v87 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EF,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)v87,
            v106);
          goto LABEL_166;
        }
        v117 = 0;
        *(_QWORD *)v127 = 0;
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
        v105 = (unsigned __int16 *)v127;
        OpcFileStream = Appx::Packaging::TryGetOpcFileStream(v132, v131, v85, &v117);
        v88 = OpcFileStream;
        if ( OpcFileStream < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F3,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)OpcFileStream,
            (int)v127);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
LABEL_166:
          Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
          v98 = v108;
          v108 = 0;
          if ( v98 )
            Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'();
          started = v88;
          goto LABEL_178;
        }
        if ( !*(_QWORD *)v127 )
        {
          started = -2146958834;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F4,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)0x8008020ELL,
            (int)v127);
          v75 = (Appx::Packaging **)&v117;
          goto LABEL_110;
        }
        v109 = 0;
        v124 = &v109;
        v125 = 0;
        LOBYTE(v126) = 1;
        appended = Appx::Packaging::FileNameHelper::ConvertFileNameToOpcUtf8(v85, &v125);
        wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v124);
        if ( appended < 0 )
        {
          v94 = 1015;
          goto LABEL_158;
        }
        v91 = -1;
        do
          ++v91;
        while ( *((_BYTE *)v109 + v91) );
        LODWORD(v105) = v117;
        appended = Appx::Packaging::ZipEditor::AppendFileStreamToArchive(v8, v91, v109);
        if ( appended < 0 )
        {
          v94 = 1018;
LABEL_158:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v94,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)(unsigned int)appended,
            (int)v105);
          v96 = v109;
          v109 = 0;
          if ( v96 )
            operator delete(v96, v95);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
          Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
          v97 = v108;
          v108 = 0;
          if ( v97 )
            Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'();
          started = appended;
          goto LABEL_178;
        }
        v93 = v109;
        v109 = 0;
        if ( v93 )
          operator delete(v93, v92);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v117);
      }
      v22 = v115;
      v21 = v114[0];
    }
    v58 = Appx::Packaging::BlockMap::BlockMapXmlWriter::EndBlockMap(v12);
    started = v58;
    if ( v58 < 0 )
    {
      v84 = 1022;
      goto LABEL_173;
    }
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
      v151,
      L"AppxBlockMap.xml");
    Appx::Packaging::details::SendPackagingContextToSink(
      (Appx::Packaging::details *)(v152 + 40),
      0,
      (const unsigned __int16 *)1,
      v99);
    LODWORD(v105) = *(_DWORD *)v122;
    v58 = Appx::Packaging::ZipEditor::AppendFileStreamToArchive(v8, 16, "AppxBlockMap.xml");
    started = v58;
    if ( v58 < 0 )
    {
      v84 = 1027;
      goto LABEL_173;
    }
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
      v151,
      L"Done");
    Appx::Packaging::details::SendPackagingContextToSink(
      (Appx::Packaging::details *)(v152 + 40),
      0,
      (const unsigned __int16 *)3,
      v101);
    wil::ActivityBase<Appx::Packaging::AppxPackagingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v151);
    Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
    v102 = v108;
    v108 = 0;
    if ( v102 )
      Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'();
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
    Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v12, v103);
    Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::~AppendDeltaAndUpdatedBlockMapToPackage((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v151);
    return 0;
  }
  while ( 1 )
  {
    v23 = *(_QWORD *)(*(_QWORD *)(v20 + 16) + 8LL);
    v24 = *(unsigned __int16 **)(v23 + 56);
    v25 = *(_QWORD *)(v23 + 72);
    if ( Common::String::CaseInsensitiveEquals(v24, L"AppxManifest.xml")
      || Common::String::CaseInsensitiveEquals(v24, L"AppxContentGroupMap.xml") )
    {
      v58 = Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(
              v114,
              v22 + 1);
      started = v58;
      if ( v58 < 0 )
      {
        v84 = 849;
LABEL_173:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v84,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
          (const char *)(unsigned int)v58,
          (int)v105);
        goto LABEL_174;
      }
      v59 = v115;
      *(_QWORD *)(v114[0] + 8 * v115) = v23;
      v22 = v59 + 1;
      v115 = v22;
      goto LABEL_77;
    }
    Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::SetMessageCopy(
      (Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v151,
      v24);
    v129 = 0;
    if ( (int)Appx::Packaging::BlockMap::AppxBlockMapReader::GetFileInternal(
                (Appx::Packaging::BlockMap::AppxBlockMapReader *)v7,
                v24,
                &v129) >= 0 )
      break;
    v120 = 0;
    *(_QWORD *)v133 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v120);
    v54 = Appx::Packaging::TryGetOpcFileStream(v132, v131, v24, &v120);
    started = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)(unsigned int)v54,
        (int)v133);
      v75 = &v120;
      goto LABEL_110;
    }
    v113 = 0;
    LocalFileItemInfo = Appx::Packaging::AppendWholeDeltaFileToPackage(
                          v120,
                          (struct IStream *)v24,
                          v128,
                          v130,
                          (const unsigned __int16 *)&v113,
                          v107);
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v82 = 985;
LABEL_135:
      v83 = (unsigned int)LocalFileItemInfo;
LABEL_136:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v82,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
        (const char *)v83,
        (int)v105);
      v66 = &v120;
LABEL_91:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v66);
LABEL_174:
      Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
      goto LABEL_175;
    }
    v56 = v113;
    if ( *((_QWORD *)v113 + 3) != v25 )
    {
      started = -2147418113;
      v82 = 986;
      v83 = 2147549183LL;
      goto LABEL_136;
    }
    v113 = 0;
    LocalFileItemInfo = Appx::Packaging::ZipFileItem::GetLocalFileItemInfo(v56, &v113);
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v82 = 990;
      goto LABEL_135;
    }
    LocalFileItemInfo = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(
                          v12,
                          (const struct Appx::Packaging::BlockMap::AppxBlockMapFile *)v23,
                          *(unsigned __int16 *)v113,
                          v57,
                          *(_QWORD *)(v23 + 96));
    started = LocalFileItemInfo;
    if ( LocalFileItemInfo < 0 )
    {
      v82 = 991;
      goto LABEL_135;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v120);
LABEL_77:
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(v108);
    v20 = v108;
    if ( !*(_BYTE *)(v108 + 24) )
    {
      v21 = v114[0];
      v8 = v128;
      goto LABEL_79;
    }
  }
  v110 = 0;
  v113 = 0;
  v109 = 0;
  *(_OWORD *)v118 = 0;
  v119 = 0;
  v26 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v118, v24);
  started = v26;
  if ( v26 < 0 )
  {
    v80 = 869;
LABEL_129:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v80,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)v26,
      (int)v105);
    if ( v118[1] )
      operator delete(v118[1], v81);
LABEL_109:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
    v75 = &v110;
LABEL_110:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v75);
    Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
    v72 = v108;
    v108 = 0;
    goto LABEL_176;
  }
  v125 = (char *)v118;
  v124 = &Common::StringBufferBuilder::`vftable';
  v126 = v118;
  v26 = Common::StringBuilder::AppendString((Common::StringBuilder *)&v124, L".blockcache");
  started = v26;
  if ( v26 < 0 )
  {
    v80 = 870;
    goto LABEL_129;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
  v105 = (unsigned __int16 *)&v113;
  v26 = Appx::Packaging::TryGetOpcFileStream(v132, v131, v118[1], &v110);
  started = v26;
  if ( v26 < 0 )
  {
    v80 = 871;
    goto LABEL_129;
  }
  v28 = v113;
  v139 = 17988;
  v140 = 1;
  v141 = 0;
  v142 = 0;
  v143 = 0;
  v144 = 0;
  v145 = 0;
  v146 = 0;
  v147 = 0;
  v148 = 0;
  if ( !v113 )
  {
    v37 = 0;
    v121 = 0;
    if ( v25 < *((_QWORD *)v129 + 9) )
      goto LABEL_36;
    v40 = 0;
    if ( *((_BYTE *)v129 + 159) )
      goto LABEL_36;
    goto LABEL_37;
  }
  v111 = 0;
  v124 = (void **)&v111;
  v29 = *((_QWORD *)v128 + 7);
  v125 = 0;
  LOBYTE(v126) = 1;
  started = Appx::Packaging::GetAppendedBlockcacheFileName(
              (Appx::Packaging *)v24,
              v149,
              (const unsigned __int16 *)&v125,
              v27);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v124);
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)&v113);
    v74 = v111;
    v111 = 0;
    if ( v74 )
      operator delete(v74, v73);
LABEL_107:
    if ( v118[1] )
      operator delete(v118[1], v73);
    goto LABEL_109;
  }
  v124 = &v112;
  v112 = 0;
  v125 = 0;
  LOBYTE(v126) = 1;
  started = Appx::Packaging::FileNameHelper::ConvertFileNameToOpcUtf8(v111, &v125);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>::~out_param_t<wistd::unique_ptr<unsigned short const [0],wistd::default_delete<unsigned short const [0]>>>(&v124);
  if ( started < 0 )
  {
    v62 = 882;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v62,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)(unsigned int)started,
      (int)v105);
    v64 = v112;
    v112 = 0;
    if ( v64 )
      operator delete(v64, v63);
    v65 = v111;
    v111 = 0;
    if ( v65 )
      operator delete(v65, v63);
    goto LABEL_88;
  }
  v30 = -1;
  v31 = *((_DWORD *)v28 + 10);
  v113 = 0;
  do
    ++v30;
  while ( *((_BYTE *)v112 + v30) );
  LODWORD(v105) = v31;
  v32 = Appx::Packaging::ZipEditor::AppendZippedFileStreamToArchive(v128, v30, v112, 0);
  started = v32;
  if ( v32 >= 0 )
  {
    *(_QWORD *)v127 = 0;
    v33 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v110 + 40LL))(v110, 0, 0, 0);
    started = v33;
    if ( v33 < 0 )
    {
      v68 = (unsigned int)v33;
      v67 = 890;
      goto LABEL_93;
    }
    Entry = Appx::Packaging::BlockMapDeltaFileEntry::ReadEntry(
              v110,
              (struct Appx::Packaging::BlockMapDeltaFileEntry *)&v139);
    started = Entry;
    if ( Entry < 0 )
    {
      v68 = (unsigned int)Entry;
      v67 = 892;
      goto LABEL_93;
    }
    v123 = 0;
    v35 = Appx::Packaging::ZipFileItem::GetLocalFileItemInfo(v113, &v123);
    started = v35;
    if ( v35 < 0 )
    {
      v68 = (unsigned int)v35;
      v67 = 896;
      goto LABEL_93;
    }
    v36 = v29 + *(unsigned __int16 *)v123;
    if ( v36 < v29 )
    {
      started = -2147024362;
      v67 = 898;
      v68 = 2147942934LL;
      goto LABEL_93;
    }
    v37 = (char *)v147 + v36;
    v121 = (char *)v147 + v36;
    if ( (unsigned __int64)v147 + v36 < v36 )
    {
      started = -2147024362;
      v62 = 899;
      goto LABEL_84;
    }
    v38 = v112;
    v112 = 0;
    if ( v38 )
      operator delete(v38, v36);
    v39 = v111;
    v111 = 0;
    if ( v39 )
      operator delete(v39, v36);
LABEL_36:
    v40 = 1;
LABEL_37:
    StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddFile(
                              v12,
                              v24,
                              v25,
                              *(_DWORD *)(v23 + 88),
                              v40,
                              *(_QWORD *)(v23 + 96));
    v42 = 0;
    started = StreamCurrentPosition;
    if ( StreamCurrentPosition < 0 )
    {
      v76 = 908;
      goto LABEL_112;
    }
    v134 = 16964;
    v136 = 0;
    v43 = 0;
    v44 = *(_QWORD *)(v23 + 120);
    v45 = 0;
    *(_QWORD *)v133 = v44;
    v135 = 1;
    v137 = 0;
    v138 = 0;
    v123 = 0;
    v113 = 0;
    while ( 1 )
    {
      LODWORD(v117) = v43;
      if ( v45 == v44 )
        break;
      if ( v45 < *(_QWORD *)(v23 + 120) )
      {
        _mm_lfence();
        v42 = *(_QWORD *)(*(_QWORD *)(v23 + 104) + 8 * v45);
      }
      v46 = 0;
      if ( (unsigned __int64)v43 >= *((_QWORD *)v129 + 15) )
        goto LABEL_49;
      _mm_lfence();
      v47 = *(_QWORD *)(*((_QWORD *)v129 + 13) + 8LL * v43);
      if ( !v47 )
        goto LABEL_49;
      if ( *(_BYTE *)(v42 + 48) )
        v46 = *(_DWORD *)(v47 + 28);
      v48 = *(_DWORD *)(v47 + 36);
      if ( v48 == *(_DWORD *)(v42 + 36) && !memcmp_0(*(const void **)(v47 + 56), *(const void **)(v42 + 56), v48) )
      {
        v49 = *(_QWORD *)(v47 + 40);
      }
      else
      {
LABEL_49:
        if ( !v110 )
        {
          started = -2146958834;
          v78 = 941;
LABEL_116:
          v79 = (unsigned int)started;
LABEL_117:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v78,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
            (const char *)v79,
            (int)v105);
          goto LABEL_107;
        }
        v49 = (unsigned __int64)&v37[v138];
        if ( v49 < (unsigned __int64)v121 )
        {
          started = -2147024362;
          v78 = 944;
          goto LABEL_116;
        }
        v50 = Appx::Packaging::BlockMapDeltaBlockEntry::ReadEntry(
                v110,
                (struct Appx::Packaging::BlockMapDeltaBlockEntry *)&v134,
                0);
        started = v50;
        if ( v50 < 0 )
        {
          v79 = (unsigned int)v50;
          v78 = 948;
          goto LABEL_117;
        }
        if ( v137 != v123 )
        {
          v78 = 949;
LABEL_115:
          started = -2146958833;
          goto LABEL_116;
        }
        if ( v138 != *(_DWORD *)(v42 + 24) )
        {
          v78 = 950;
          goto LABEL_115;
        }
        v113 = (Appx::Packaging::ZipFileItem *)((char *)v113 + 1);
        v121 = (char *)v49;
      }
      if ( *(_BYTE *)(v42 + 48) )
        v51 = *(_DWORD *)(v42 + 24);
      else
        v51 = 0;
      StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::AddBlockWithPackageOffset(
                                v12,
                                *(const unsigned __int8 **)(v42 + 56),
                                *(_DWORD *)(v42 + 36),
                                v51,
                                v49,
                                v46);
      v42 = 0;
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v76 = 958;
        goto LABEL_112;
      }
      v123 = (struct Appx::Packaging::ZipLocalFileItemInfo *)((char *)v123 + 0x10000);
      v43 = v117 + 1;
      v37 = v121;
      ++v45;
      v44 = *(_QWORD *)v133;
    }
    StreamCurrentPosition = Appx::Packaging::BlockMap::BlockMapXmlWriter::CloseFile(v12, 0, 0);
    started = StreamCurrentPosition;
    if ( StreamCurrentPosition < 0 )
    {
      v76 = 965;
      goto LABEL_112;
    }
    if ( !v110 )
    {
LABEL_66:
      if ( v118[1] )
        operator delete(v118[1], v52);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
      v22 = v115;
      v7 = v150;
      goto LABEL_77;
    }
    if ( v113 == v148 )
    {
      StreamCurrentPosition = Appx::Packaging::BlockMapDeltaBlockEntry::ReadEntry(
                                v110,
                                (struct Appx::Packaging::BlockMapDeltaBlockEntry *)&v134,
                                1);
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v76 = 972;
LABEL_112:
        v77 = (unsigned int)StreamCurrentPosition;
        goto LABEL_113;
      }
      v113 = 0;
      StreamCurrentPosition = Appx::Packaging::GetStreamCurrentPosition(v110, (struct IStream *)&v113, v53);
      started = StreamCurrentPosition;
      if ( StreamCurrentPosition < 0 )
      {
        v76 = 974;
        goto LABEL_112;
      }
      if ( v113 != v147 )
      {
        started = -2146958833;
        v76 = 975;
        v77 = 2148008463LL;
        goto LABEL_113;
      }
      goto LABEL_66;
    }
    started = -2146958833;
    v76 = 970;
    v77 = 2148008463LL;
LABEL_113:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v76,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
      (const char *)v77,
      (int)v105);
LABEL_88:
    if ( v118[1] )
      operator delete(v118[1], v63);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
    v66 = &v110;
    goto LABEL_91;
  }
  v68 = (unsigned int)v32;
  v67 = 887;
LABEL_93:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v67,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\appxpackageeditor.cpp",
    (const char *)v68,
    (int)v105);
  v70 = v112;
  v112 = 0;
  if ( v70 )
    operator delete(v70, v69);
  v71 = v111;
  v111 = 0;
  if ( v71 )
    operator delete(v71, v69);
  if ( v118[1] )
    operator delete(v118[1], v69);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v109);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v110);
  Common::Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>::~Array<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::ContainerOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::BlockMap::AppxBlockMapFile>,Common::ArrayOperations<Appx::Packaging::BlockMap::AppxBlockMapFile,Common::NoKey>>(v114);
  v72 = v108;
  v108 = 0;
LABEL_176:
  if ( v72 )
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::`scalar deleting destructor'();
LABEL_178:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v122);
  Appx::Packaging::BlockMap::BlockMapXmlWriter::`scalar deleting destructor'(v12, v100);
LABEL_183:
  Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage::~AppendDeltaAndUpdatedBlockMapToPackage((Appx::Packaging::AppxPackagingProvider::AppendDeltaAndUpdatedBlockMapToPackage *)v151);
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
