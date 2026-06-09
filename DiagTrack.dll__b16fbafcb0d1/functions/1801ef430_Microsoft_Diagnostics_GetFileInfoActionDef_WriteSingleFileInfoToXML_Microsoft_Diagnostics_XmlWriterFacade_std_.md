# Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(Microsoft::Diagnostics::XmlWriterFacade &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,unsigned __int64,unsigned __int64,ulong,Microsoft::Diagnostics::GetFileInfoActionDef::FileInfoQueryState const &)

- ea: `0x1801ef430`
- end: `0x1801eff40`
- name: `?WriteSingleFileInfoToXML@GetFileInfoActionDef@Diagnostics@Microsoft@@CAXAEAVXmlWriterFacade@23@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N_K3KAEBUFileInfoQueryState@123@@Z`
- size: `2832`
- prototype: `__int64 __fastcall(__int64, _QWORD *, char, _QWORD *, __int64, int, _BYTE *)`
- caller_count: `2`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801ee3c0`
- `0x18032e768`

## callees

- `0x18001b010`
- `0x180025430`
- `0x180027c28`
- `0x18002ac10`
- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180035088`
- `0x1800f7f64`
- `0x1801e206c`
- `0x1801ef430`
- `0x18020aac0`
- `0x180312b68`
- `0x180312c78`
- `0x18031321c`
- `0x18031b008`
- `0x18032dd5c`
- `0x18032e0b8`
- `0x18032e2fc`

## import_xrefs

- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x1801eff09`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicFreeFileInfo` at `0x1801eff09`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb4f`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb72`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb4f`
- `ext-ms-win-appcompat-aepic-l1-1-0!PicRetrieveFileInfo` at `0x1801efb72`

## string_xrefs

- `0x1801ef588`: `Compressed`
- `0x1801ef867`: `ReparsePointQueryInfoError`
- `0x1801ef7d8`: `ReparsePoint`
- `0x1801ef8f1`: `ReparsePointSubstituteName`
- `0x1801ef8a3`: `ReparsePointTag`
- `0x1801ef78b`: `ReadOnly`
- `0x1801efab8`: `Temporary`
- `0x1801ef994`: `ReparsePointSecurityDescriptor`
- `0x1801ef943`: `ReparsePointPrintName`
- `0x1801ef9e9`: `SecurityDescriptor`
- `0x1801efcd0`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(
        __int64 a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        _BYTE *a7)
{
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // rdx
  __int64 v75; // r8
  __int64 v76; // r9
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // r9
  __int64 v83; // r8
  __int64 v84; // r9
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // r9
  __int64 v88; // r8
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  __int64 v92; // r9
  _QWORD *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // r9
  _QWORD *v100; // rax
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // r9
  __int64 v104; // rdx
  __int64 v105; // r8
  __int64 v106; // r9
  int v107; // r9d
  int v108; // r9d
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  __int64 v124; // rdx
  _QWORD *v125; // rcx
  __int64 v126; // r8
  _QWORD *v127; // rcx
  __int64 v128; // rax
  void *v129; // rax
  __int64 v130; // rdx
  __int64 v131; // r8
  __int64 v132; // r9
  __int64 v133; // rdx
  __int64 v134; // r8
  __int64 v135; // r9
  _QWORD *v136; // rdx
  __int64 v137; // rdx
  __int64 v138; // r8
  __int64 v139; // r9
  __int64 v140; // r9
  __int64 v141; // rdx
  __int64 v142; // r8
  __int64 v143; // r9
  __int64 v144; // r9
  __int64 v145; // rdx
  __int64 v146; // r8
  __int64 v147; // r9
  __int64 v148; // r9
  _QWORD *v149; // r9
  __int64 v150; // rdx
  __int64 v151; // r8
  __int64 v152; // r9
  __int64 v153; // r9
  __int64 v154; // rdx
  __int64 v155; // r8
  __int64 v156; // r9
  __int64 v157; // rdx
  __int64 v158; // rdx
  __int64 v159; // r8
  __int64 v160; // r9
  __int64 v161; // r9
  __int64 v162; // rdx
  __int64 v163; // r8
  __int64 v164; // r9
  __int64 v165; // r9
  __int64 v166; // rdx
  __int64 v167; // r8
  __int64 v168; // r9
  __int64 v169; // r9
  __int64 v170; // rdx
  __int64 v171; // r8
  __int64 v172; // r9
  __int64 v173; // r9
  __int64 v174; // rdx
  __int64 v175; // r8
  __int64 v176; // r9
  __int64 v177; // r9
  _BYTE v179[16]; // [rsp+30h] [rbp-C1h] BYREF
  __int128 v180; // [rsp+40h] [rbp-B1h] BYREF
  __int128 v181; // [rsp+50h] [rbp-A1h] BYREF
  _QWORD v182[2]; // [rsp+60h] [rbp-91h] BYREF
  _QWORD *v183; // [rsp+70h] [rbp-81h] BYREF
  __int64 v184; // [rsp+78h] [rbp-79h]
  int v185; // [rsp+80h] [rbp-71h] BYREF
  _QWORD v186[3]; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int64 v187; // [rsp+A0h] [rbp-51h]
  _QWORD Src[6]; // [rsp+A8h] [rbp-49h] BYREF
  _QWORD v189[4]; // [rsp+D8h] [rbp-19h] BYREF

  v183 = a4;
  std::wstring::wstring(v186, *a2, a2[1]);
  *(_QWORD *)&v181 = L"FileSize";
  *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"FileSize", v10, v11, v12);
  *(_QWORD *)&v180 = L"info";
  *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v13, v14, v15);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(
    a1,
    (unsigned int)&v180,
    (unsigned int)&v181,
    (unsigned int)&v183,
    0);
  v16 = Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601((STRSAFE_LPWSTR)Src);
  *(_QWORD *)&v180 = L"LastModifiedTime";
  *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"LastModifiedTime", v17, v18, v16);
  *(_QWORD *)&v181 = L"info";
  *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v19, v20, v21);
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v181, &v180);
  std::wstring::_Tidy_deallocate(Src);
  v25 = std::_WChar_traits<wchar_t>::length(L"info", v22, v23, v24);
  if ( a6 == -1 )
  {
    v179[0] = 1;
    *(_QWORD *)&v180 = L"InvalidFileAttributes";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"InvalidFileAttributes", v25, v26, v27);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = v124;
  }
  else
  {
    v179[0] = (a6 & 0x20) != 0;
    *(_QWORD *)&v180 = L"Archive";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Archive", v25, v26, v27);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = v28;
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x800) != 0;
    *(_QWORD *)&v180 = L"Compressed";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Compressed", v29, v30, v31);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v32, v33, v34);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x40) != 0;
    *(_QWORD *)&v180 = L"Device";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Device", v35, v36, v37);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v38, v39, v40);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x4000) != 0;
    *(_QWORD *)&v180 = L"Encrypted";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Encrypted", v41, v42, v43);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v44, v45, v46);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 2) != 0;
    *(_QWORD *)&v180 = L"Hidden";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Hidden", v47, v48, v49);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v50, v51, v52);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x80) != 0;
    *(_QWORD *)&v180 = L"Normal";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Normal", v53, v54, v55);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v56, v57, v58);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x2000) != 0;
    *(_QWORD *)&v180 = L"NotContentIndexed";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"NotContentIndexed", v59, v60, v61);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v62, v63, v64);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 0x1000) != 0;
    *(_QWORD *)&v180 = L"Offline";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Offline", v65, v66, v67);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v68, v69, v70);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = a6 & 1;
    *(_QWORD *)&v180 = L"ReadOnly";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReadOnly", v71, v72, v73);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v74, v75, v76);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    if ( (a6 & 0x400) != 0 )
    {
      v179[0] = 1;
      *(_QWORD *)&v180 = L"ReparsePoint";
      *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePoint", v77, v78, v79);
      *(_QWORD *)&v181 = L"info";
      *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v80, v81, v82);
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
      v185 = 0;
      std::wstring::wstring(Src);
      std::wstring::wstring(v189);
      v180 = *(_OWORD *)a2;
      LODWORD(v183) = Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(&v180, &v185, Src, v189);
      v86 = std::_WChar_traits<wchar_t>::length(L"info", (unsigned int)v183, v83, v84);
      if ( (int)v85 >= 0 )
      {
        *(_QWORD *)&v180 = L"ReparsePointTag";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointTag", v85, v86, v87);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = v89;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned long>(
          a1,
          (unsigned int)&v181,
          (unsigned int)&v180,
          (unsigned int)&v185,
          0);
        v93 = Src;
        if ( Src[3] > 7u )
          v93 = (_QWORD *)Src[0];
        v183 = v93;
        *(_QWORD *)&v180 = L"ReparsePointSubstituteName";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointSubstituteName", v90, v91, v92);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v94, v95, v96);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, &v183);
        v100 = v189;
        if ( v189[3] > 7u )
          v100 = (_QWORD *)v189[0];
        v183 = v100;
        *(_QWORD *)&v180 = L"ReparsePointPrintName";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointPrintName", v97, v98, v99);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v101, v102, v103);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, &v183);
        if ( a7[2] )
        {
          v181 = *(_OWORD *)a2;
          *(_QWORD *)&v180 = L"ReparsePointSecurityDescriptor";
          *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(
                                     L"ReparsePointSecurityDescriptor",
                                     v104,
                                     v105,
                                     v106);
          LOBYTE(v107) = a3;
          Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(
            a1,
            (unsigned int)&v180,
            (unsigned int)&v181,
            v107,
            1);
        }
      }
      else
      {
        *(_QWORD *)&v180 = L"ReparsePointQueryInfoError";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ReparsePointQueryInfoError", v85, v86, v87);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = v88;
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(a1, &v181, &v180, &v183);
      }
      std::wstring::_Tidy_deallocate(v189);
      std::wstring::_Tidy_deallocate(Src);
    }
    if ( a7[2] )
    {
      v181 = *(_OWORD *)a2;
      *(_QWORD *)&v180 = L"SecurityDescriptor";
      *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"SecurityDescriptor", v77, v78, v79);
      LOBYTE(v108) = a3;
      Microsoft::Diagnostics::GetFileInfoActionDef::QuerySecurity(a1, (unsigned int)&v180, (unsigned int)&v181, v108, 0);
    }
    v179[0] = (a6 & 0x200) != 0;
    *(_QWORD *)&v180 = L"SparseFile";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"SparseFile", v77, v78, v79);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v109, v110, v111);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = (a6 & 4) != 0;
    *(_QWORD *)&v180 = L"System";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"System", v112, v113, v114);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v115, v116, v117);
    Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
    v179[0] = BYTE1(a6) & 1;
    *(_QWORD *)&v180 = L"Temporary";
    *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Temporary", v118, v119, v120);
    *(_QWORD *)&v181 = L"info";
    *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v121, v122, v123);
  }
  Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(a1, &v181, &v180, v179);
  if ( !a3 && !*a7 )
  {
    v182[0] = 0;
    v125 = v186;
    if ( v187 > 7 )
      v125 = (_QWORD *)v186[0];
    if ( (int)PicRetrieveFileInfo(v125, 16, v182) >= 0 )
      goto LABEL_25;
    v127 = v186;
    if ( v187 > 7 )
      v127 = (_QWORD *)v186[0];
    if ( (int)PicRetrieveFileInfo(v127, 0, v182) >= 0 )
    {
LABEL_25:
      v183 = v182;
      LOBYTE(v184) = 1;
      v136 = (_QWORD *)v182[0];
      if ( *(_QWORD *)(v182[0] + 72LL) )
      {
        *(_QWORD *)&v180 = L"Architecture";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Architecture", v182[0], v126, v182[0] + 72LL);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v137, v138, v139);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v140);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[4] )
      {
        *(_QWORD *)&v180 = L"BinFileVersion";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"BinFileVersion", v136, v126, v136 + 4);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v141, v142, v143);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v144);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[7] )
      {
        *(_QWORD *)&v180 = L"CompanyName";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"CompanyName", v136, v126, v136 + 7);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v145, v146, v147);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v148);
        v136 = (_QWORD *)v182[0];
      }
      v149 = v136 + 2;
      if ( v136[2] )
      {
        *(_QWORD *)&v180 = L"FileDescription";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"FileDescription", v136, v126, v149);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v150, v151, v152);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v153);
        v136 = (_QWORD *)v182[0];
      }
      if ( *v136 )
      {
        *(_QWORD *)&v180 = L"FileID";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"FileID", v136, v126, v149);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v154, v155, v156);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v157);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[3] )
      {
        *(_QWORD *)&v180 = L"FileVersion";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"FileVersion", v136, v126, v136 + 3);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v158, v159, v160);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v161);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[6] )
      {
        *(_QWORD *)&v180 = L"ProductName";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ProductName", v136, v126, v136 + 6);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v162, v163, v164);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v165);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[8] )
      {
        *(_QWORD *)&v180 = L"ProductVersion";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ProductVersion", v136, v126, v136 + 8);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v166, v167, v168);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v169);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[1] )
      {
        *(_QWORD *)&v180 = L"ProgramID";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"ProgramID", v136, v126, v136 + 1);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v170, v171, v172);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v173);
        v136 = (_QWORD *)v182[0];
      }
      if ( v136[5] )
      {
        *(_QWORD *)&v180 = L"VerLanguage";
        *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"VerLanguage", v136, v126, v136 + 5);
        *(_QWORD *)&v181 = L"info";
        *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v174, v175, v176);
        Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(a1, &v181, &v180, v177);
        v136 = (_QWORD *)v182[0];
      }
      PicFreeFileInfo(v136);
    }
    else
    {
      Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
      v128 = Microsoft::Diagnostics::WideStringStream::operator<<(Src);
      WORD1(v180) = 0;
      LOBYTE(v183) = 1;
      *(_WORD *)((char *)&v183 + 1) = BYTE1(v180);
      BYTE3(v183) = 0;
      HIDWORD(v183) = 2097153;
      v184 = 0;
      v129 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v128, &v183);
      Microsoft::Diagnostics::WideStringStream::operator<<(v129);
      *(_QWORD *)&v180 = L"Error";
      *((_QWORD *)&v180 + 1) = std::_WChar_traits<wchar_t>::length(L"Error", v130, v131, v132);
      *(_QWORD *)&v181 = L"info";
      *((_QWORD *)&v181 + 1) = std::_WChar_traits<wchar_t>::length(L"info", v133, v134, v135);
      Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(a1, &v181, &v180);
      std::wstring::_Tidy_deallocate(Src);
    }
  }
  return std::wstring::_Tidy_deallocate(v186);
}

```

## disassembly

```asm
0x1801ef430  mov     [rsp-8+arg_10], rbx
0x1801ef435  push    rbp
0x1801ef436  push    rsi
0x1801ef437  push    rdi
0x1801ef438  push    r12
0x1801ef43a  push    r13
0x1801ef43c  push    r14
0x1801ef43e  push    r15
0x1801ef440  lea     rbp, [rsp-0Fh]
0x1801ef445  sub     rsp, 100h
0x1801ef44c  mov     rax, cs:__security_cookie
0x1801ef453  xor     rax, rsp
0x1801ef456  mov     [rbp+3Fh+var_38], rax
0x1801ef45a  mov     r15b, r8b
0x1801ef45d  mov     r14, rdx
0x1801ef460  mov     rdi, rcx
0x1801ef463  mov     [rsp+130h+var_C0], r9
0x1801ef468  mov     rbx, [rbp+3Fh+arg_20]
0x1801ef46c  mov     r8, [rdx+8]
0x1801ef470  mov     rdx, [rdx]
0x1801ef473  lea     rcx, [rbp+3Fh+var_A8]
0x1801ef477  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x1801ef47c  nop
0x1801ef47d  lea     rcx, aFilesize; "FileSize"
0x1801ef484  mov     qword ptr [rsp+130h+var_E0], rcx
0x1801ef489  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef48e  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef493  lea     r13, aInfo_0; "info"
0x1801ef49a  mov     qword ptr [rsp+130h+var_F0], r13
0x1801ef49f  mov     rcx, r13
0x1801ef4a2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4a7  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef4ac  mov     [rsp+130h+var_110], 0
0x1801ef4b1  lea     r9, [rsp+130h+var_C0]
0x1801ef4b6  lea     r8, [rsp+130h+var_E0]
0x1801ef4bb  lea     rdx, [rsp+130h+var_F0]
0x1801ef4c0  mov     rcx, rdi
0x1801ef4c3  call    ??$WriteInfoElement@_K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_K_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<unsigned __int64>(std::wstring_view,std::wstring_view,unsigned __int64 const &,bool)
0x1801ef4c8  mov     rdx, rbx
0x1801ef4cb  lea     rcx, [rbp+3Fh+Src]; pszDest
0x1801ef4cf  call    ?FileTimeToPrecise8601@Time@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; Microsoft::Diagnostics::Utils::Time::FileTimeToPrecise8601(unsigned __int64)
0x1801ef4d4  mov     r9, rax
0x1801ef4d7  lea     rcx, aLastmodifiedti; "LastModifiedTime"
0x1801ef4de  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef4e3  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4e8  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef4ed  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef4f2  mov     rcx, r13
0x1801ef4f5  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef4fa  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef4ff  lea     r8, [rsp+130h+var_F0]
0x1801ef504  lea     rdx, [rsp+130h+var_E0]
0x1801ef509  mov     rcx, rdi
0x1801ef50c  call    ??$WriteInfoElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<std::wstring>(std::wstring_view,std::wstring_view,std::wstring const &,bool)
0x1801ef511  nop
0x1801ef512  lea     rcx, [rbp+3Fh+Src]
0x1801ef516  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ef51b  mov     rcx, r13
0x1801ef51e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef523  mov     rdx, rax
0x1801ef526  mov     r12, [rbp+3Fh+arg_30]
0x1801ef52a  mov     esi, [rbp+3Fh+arg_28]
0x1801ef52d  mov     ebx, 1
0x1801ef532  cmp     esi, 0FFFFFFFFh
0x1801ef535  jz      loc_1801EFAE2
0x1801ef53b  mov     ecx, esi
0x1801ef53d  shr     ecx, 5
0x1801ef540  and     cl, bl
0x1801ef542  mov     [rsp+130h+var_100], cl
0x1801ef546  lea     rcx, aArchive; "Archive"
0x1801ef54d  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef552  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef557  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef55c  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef561  mov     qword ptr [rsp+130h+var_E0+8], rdx
0x1801ef566  lea     r9, [rsp+130h+var_100]
0x1801ef56b  lea     r8, [rsp+130h+var_F0]
0x1801ef570  lea     rdx, [rsp+130h+var_E0]
0x1801ef575  mov     rcx, rdi
0x1801ef578  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef57d  mov     eax, esi
0x1801ef57f  shr     eax, 0Bh
0x1801ef582  and     al, bl
0x1801ef584  mov     [rsp+130h+var_100], al
0x1801ef588  lea     rcx, aCompressed; "Compressed"
0x1801ef58f  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef594  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef599  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef59e  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef5a3  mov     rcx, r13
0x1801ef5a6  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5ab  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef5b0  lea     r9, [rsp+130h+var_100]
0x1801ef5b5  lea     r8, [rsp+130h+var_F0]
0x1801ef5ba  lea     rdx, [rsp+130h+var_E0]
0x1801ef5bf  mov     rcx, rdi
0x1801ef5c2  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef5c7  mov     eax, esi
0x1801ef5c9  shr     eax, 6
0x1801ef5cc  and     al, bl
0x1801ef5ce  mov     [rsp+130h+var_100], al
0x1801ef5d2  lea     rcx, aDevice_0; "Device"
0x1801ef5d9  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef5de  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5e3  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef5e8  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef5ed  mov     rcx, r13
0x1801ef5f0  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef5f5  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef5fa  lea     r9, [rsp+130h+var_100]
0x1801ef5ff  lea     r8, [rsp+130h+var_F0]
0x1801ef604  lea     rdx, [rsp+130h+var_E0]
0x1801ef609  mov     rcx, rdi
0x1801ef60c  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef611  mov     eax, esi
0x1801ef613  shr     eax, 0Eh
0x1801ef616  and     al, bl
0x1801ef618  mov     [rsp+130h+var_100], al
0x1801ef61c  lea     rcx, aEncrypted; "Encrypted"
0x1801ef623  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef628  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef62d  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef632  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef637  mov     rcx, r13
0x1801ef63a  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef63f  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef644  lea     r9, [rsp+130h+var_100]
0x1801ef649  lea     r8, [rsp+130h+var_F0]
0x1801ef64e  lea     rdx, [rsp+130h+var_E0]
0x1801ef653  mov     rcx, rdi
0x1801ef656  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef65b  mov     eax, esi
0x1801ef65d  shr     eax, 1
0x1801ef65f  and     al, bl
0x1801ef661  mov     [rsp+130h+var_100], al
0x1801ef665  lea     rcx, aHidden; "Hidden"
0x1801ef66c  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef671  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef676  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef67b  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef680  mov     rcx, r13
0x1801ef683  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef688  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef68d  lea     r9, [rsp+130h+var_100]
0x1801ef692  lea     r8, [rsp+130h+var_F0]
0x1801ef697  lea     rdx, [rsp+130h+var_E0]
0x1801ef69c  mov     rcx, rdi
0x1801ef69f  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef6a4  mov     eax, esi
0x1801ef6a6  shr     eax, 7
0x1801ef6a9  and     al, bl
0x1801ef6ab  mov     [rsp+130h+var_100], al
0x1801ef6af  lea     rcx, aNormal; "Normal"
0x1801ef6b6  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef6bb  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef6c0  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef6c5  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef6ca  mov     rcx, r13
0x1801ef6cd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef6d2  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef6d7  lea     r9, [rsp+130h+var_100]
0x1801ef6dc  lea     r8, [rsp+130h+var_F0]
0x1801ef6e1  lea     rdx, [rsp+130h+var_E0]
0x1801ef6e6  mov     rcx, rdi
0x1801ef6e9  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef6ee  mov     eax, esi
0x1801ef6f0  shr     eax, 0Dh
0x1801ef6f3  and     al, bl
0x1801ef6f5  mov     [rsp+130h+var_100], al
0x1801ef6f9  lea     rcx, aNotcontentinde; "NotContentIndexed"
0x1801ef700  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef705  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef70a  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef70f  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef714  mov     rcx, r13
0x1801ef717  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef71c  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef721  lea     r9, [rsp+130h+var_100]
0x1801ef726  lea     r8, [rsp+130h+var_F0]
0x1801ef72b  lea     rdx, [rsp+130h+var_E0]
0x1801ef730  mov     rcx, rdi
0x1801ef733  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef738  mov     eax, esi
0x1801ef73a  shr     eax, 0Ch
0x1801ef73d  and     al, bl
0x1801ef73f  mov     [rsp+130h+var_100], al
0x1801ef743  lea     rcx, aOffline; "Offline"
0x1801ef74a  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef74f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef754  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef759  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef75e  mov     rcx, r13
0x1801ef761  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef766  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef76b  lea     r9, [rsp+130h+var_100]
0x1801ef770  lea     r8, [rsp+130h+var_F0]
0x1801ef775  lea     rdx, [rsp+130h+var_E0]
0x1801ef77a  mov     rcx, rdi
0x1801ef77d  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef782  mov     al, sil
0x1801ef785  and     al, bl
0x1801ef787  mov     [rsp+130h+var_100], al
0x1801ef78b  lea     rcx, aReadonly; "ReadOnly"
0x1801ef792  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef797  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef79c  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef7a1  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef7a6  mov     rcx, r13
0x1801ef7a9  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7ae  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef7b3  lea     r9, [rsp+130h+var_100]
0x1801ef7b8  lea     r8, [rsp+130h+var_F0]
0x1801ef7bd  lea     rdx, [rsp+130h+var_E0]
0x1801ef7c2  mov     rcx, rdi
0x1801ef7c5  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef7ca  bt      esi, 0Ah
0x1801ef7ce  jnb     loc_1801EF9D7
0x1801ef7d4  mov     [rsp+130h+var_100], bl
0x1801ef7d8  lea     rcx, aReparsepoint; "ReparsePoint"
0x1801ef7df  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef7e4  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7e9  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef7ee  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef7f3  mov     rcx, r13
0x1801ef7f6  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef7fb  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef800  lea     r9, [rsp+130h+var_100]
0x1801ef805  lea     r8, [rsp+130h+var_F0]
0x1801ef80a  lea     rdx, [rsp+130h+var_E0]
0x1801ef80f  mov     rcx, rdi
0x1801ef812  call    ??$WriteInfoElement@_N@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEB_N_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<bool>(std::wstring_view,std::wstring_view,bool const &,bool)
0x1801ef817  mov     [rbp+3Fh+var_B0], 0
0x1801ef81e  lea     rcx, [rbp+3Fh+Src]; void *
0x1801ef822  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ef827  nop
0x1801ef828  lea     rcx, [rbp+3Fh+var_58]; void *
0x1801ef82c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ef831  nop
0x1801ef832  movaps  xmm0, xmmword ptr [r14]
0x1801ef836  movdqa  [rsp+130h+var_F0], xmm0
0x1801ef83c  lea     r9, [rbp+3Fh+var_58]
0x1801ef840  lea     r8, [rbp+3Fh+Src]
0x1801ef844  lea     rdx, [rbp+3Fh+var_B0]
0x1801ef848  lea     rcx, [rsp+130h+var_F0]
0x1801ef84d  call    ?GetReparsePointInfo@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@2@Z; Microsoft::Diagnostics::Utils::FileSystem::GetReparsePointInfo(std::wstring_view,ulong &,std::wstring &,std::wstring &)
0x1801ef852  mov     edx, eax
0x1801ef854  mov     dword ptr [rsp+130h+var_C0], eax
0x1801ef858  mov     rcx, r13
0x1801ef85b  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef860  mov     r8, rax
0x1801ef863  test    edx, edx
0x1801ef865  jns     short loc_1801EF8A3
0x1801ef867  lea     rcx, aReparsepointqu; "ReparsePointQueryInfoError"
0x1801ef86e  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef873  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef878  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef87d  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef882  mov     qword ptr [rsp+130h+var_E0+8], r8
0x1801ef887  lea     r9, [rsp+130h+var_C0]
0x1801ef88c  lea     r8, [rsp+130h+var_F0]
0x1801ef891  lea     rdx, [rsp+130h+var_E0]
0x1801ef896  mov     rcx, rdi
0x1801ef899  call    ??$WriteInfoElement@J@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBJ_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<long>(std::wstring_view,std::wstring_view,long const &,bool)
0x1801ef89e  jmp     loc_1801EF9C4
0x1801ef8a3  lea     rcx, aReparsepointta; "ReparsePointTag"
0x1801ef8aa  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef8af  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef8b4  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef8b9  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef8be  mov     qword ptr [rsp+130h+var_E0+8], r8
0x1801ef8c3  mov     [rsp+130h+var_110], 0
0x1801ef8c8  lea     r9, [rbp+3Fh+var_B0]
0x1801ef8cc  lea     r8, [rsp+130h+var_F0]
0x1801ef8d1  lea     rdx, [rsp+130h+var_E0]
0x1801ef8d6  mov     rcx, rdi
0x1801ef8d9  call    ??$WriteInfoElement@K@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBK_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<ulong>(std::wstring_view,std::wstring_view,ulong const &,bool)
0x1801ef8de  lea     rax, [rbp+3Fh+Src]
0x1801ef8e2  cmp     [rbp+3Fh+var_70], 7
0x1801ef8e7  cmova   rax, [rbp+3Fh+Src]
0x1801ef8ec  mov     [rsp+130h+var_C0], rax
0x1801ef8f1  lea     rcx, aReparsepointsu; "ReparsePointSubstituteName"
0x1801ef8f8  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef8fd  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef902  mov     qword ptr [rsp+130h+var_F0+8], rax
0x1801ef907  mov     qword ptr [rsp+130h+var_E0], r13
0x1801ef90c  mov     rcx, r13
0x1801ef90f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801ef914  mov     qword ptr [rsp+130h+var_E0+8], rax
0x1801ef919  lea     r9, [rsp+130h+var_C0]
0x1801ef91e  lea     r8, [rsp+130h+var_F0]
0x1801ef923  lea     rdx, [rsp+130h+var_E0]
0x1801ef928  mov     rcx, rdi
0x1801ef92b  call    ??$WriteInfoElement@PEA_W@XmlWriterFacade@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBQEA_W_N@Z; Microsoft::Diagnostics::XmlWriterFacade::WriteInfoElement<wchar_t *>(std::wstring_view,std::wstring_view,wchar_t * const &,bool)
0x1801ef930  lea     rax, [rbp+3Fh+var_58]
0x1801ef934  cmp     [rbp+3Fh+var_40], 7
0x1801ef939  cmova   rax, [rbp+3Fh+var_58]
0x1801ef93e  mov     [rsp+130h+var_C0], rax
0x1801ef943  lea     rcx, aReparsepointpr; "ReparsePointPrintName"
0x1801ef94a  mov     qword ptr [rsp+130h+var_F0], rcx
0x1801ef94f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
  ... truncated ...
```
