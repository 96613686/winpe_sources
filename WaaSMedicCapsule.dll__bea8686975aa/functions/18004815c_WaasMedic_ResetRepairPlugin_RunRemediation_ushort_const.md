# WaasMedic::ResetRepairPlugin::RunRemediation(ushort const *)

- ea: `0x18004815c`
- end: `0x180049751`
- name: `?RunRemediation@ResetRepairPlugin@WaasMedic@@AEAAJPEBG@Z`
- size: `5621`
- prototype: `__int64 __fastcall(WaasMedic::ResetRepairPlugin *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047580`

## callees

- `0x180003bb0`
- `0x180006fdc`
- `0x1800070cc`
- `0x180007520`
- `0x180007590`
- `0x18000ab8c`
- `0x180017a64`
- `0x180022210`
- `0x1800231d0`
- `0x18002543c`
- `0x18002acd8`
- `0x18002ad54`
- `0x18003199c`
- `0x18004489c`
- `0x1800449bc`
- `0x180044b00`
- `0x180044ee4`
- `0x1800455d4`
- `0x180045b98`
- `0x180045d60`
- `0x1800461a4`
- `0x180046c94`
- `0x180047a14`
- `0x18004815c`
- `0x180049758`
- `0x180049928`
- `0x180049b44`
- `0x18004a2b0`
- `0x18004a450`
- `0x18004a71c`
- `0x18004a79c`
- `0x18004a840`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004941d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004941d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800495b2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180049473`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180049473`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800494aa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800494aa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180049413`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800495a8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180049413`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800495a8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800484c3`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800484c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800495e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800495e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004954d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004954d`

## string_xrefs

- `0x1800489f2`: `Failed to create new Path node. Err=0x%08x`
- `0x1800489ba`: `Phase doesn't have path node, create path node`
- `0x180048aca`: `Failed to add new Path node as child. Err=0x%08x`
- `0x1800487a8`: `Failed to get text from child node Path. Err=0x%08x`
- `0x180048282`: `\ResetConfig.xml`
- `0x180048444`: `Failed to load xml [%s]. Err=0x%08x`
- `0x18004818f`: `ResetRepairPlugin: RunRemediation starts`
- `0x180048406`: `Find existing ResetConfig.xml`
- `0x180048369`: `ResetConfig_F62B90D4-A654-4CFE-B625-213D47A83416.xml`
- `0x1800484e7`: `Failed to copy security from OEM folder to backup file. Err=0x%08x`
- `0x18004935a`: `CopyFile for %s to %s failed. Err=0x%08x`
- `0x180048725`: `Failed to get Path attribute. Err=0x%08x`
- `0x180048b94`: `Failed to get Path node from Reset End phase. Err=0x%08x`
- `0x180048887`: `Failed to create target CMD file. Err=0x%08x`
- `0x180048db3`: `Failed to create target CMD file. Err=0x%08x`
- `0x180049623`: `Failed to create target CMD file. Err=0x%08x`
- `0x180048c81`: `Failed to update target cmd file path. Err=0x%08x`
- `0x180048c52`: `Update path info`
- `0x180048ea0`: `Failed to create new Reset node. Err=0x%08x`
- `0x180048e68`: `Config doesn't have Reset node`
- `0x180049045`: `Failed to create new Run node. Err=0x%08x`
- `0x18004919c`: `Failed to set Path text. Err=0x%08x`
- `0x180049284`: `Save changes to ResetConfig.xml`
- `0x180049397`: `No existing ResetConfig.xml`
- `0x1800492b3`: `Failed to save updates to ResetConfig.xml. Err=0x%08x`
- `0x18004943c`: `Failed to create %s. Err=0x%08x`
- `0x1800495ce`: `Failed to create %s. Err=0x%08x`
- `0x1800493f5`: `Create [%s]`
- `0x1800494ee`: `Create [%s]`
- `0x180049668`: `Create ResetConfig.xml`
- `0x180049654`: `<?xml version="1.0" encoding="utf-8"?><Reset>  <Run Phase="FactoryReset_AfterImageApply">    <Path>AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd</Path>    <Duration>2</Duration>  </Run></Reset>`
- `0x1800496bf`: `ResetRepairPlugin: RunRemediation completes`
- `0x180049693`: `Failed to create new ResetConfig.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall WaasMedic::ResetRepairPlugin::RunRemediation(
        WaasMedic::ResetRepairPlugin *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  LPCWSTR *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  LPCWSTR *v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r8
  LPCWSTR *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  LPCWSTR *v16; // r9
  __int64 v17; // rax
  LPCWSTR *v18; // rax
  const unsigned __int16 *v19; // rcx
  int File; // eax
  signed int v21; // ebx
  LPCWSTR *v22; // r8
  __int64 v23; // rcx
  LPCWSTR *v24; // r9
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rcx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rcx
  WaasMedic *v30; // rdi
  int CommandForPhase; // eax
  unsigned __int8 v32; // r14
  int v33; // eax
  char v34; // bl
  bool *AddressOf; // rax
  int NodeForPhase; // eax
  int v37; // ecx
  __int64 v38; // r8
  __int64 v39; // r9
  int v40; // esi
  WaasMedic::XmlNode *v41; // rbx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  WaasMedic::XmlNode *v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  int ChildText; // eax
  signed int v50; // r14d
  WaasMedic::XmlNode *v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  WaasMedic::XmlNode *v55; // rbx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  int v59; // eax
  __int128 *v60; // rcx
  int v61; // eax
  WaasMedic::XmlNode *v62; // rbx
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  WaasMedic::XmlNode *v66; // rbx
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  WaasMedic::XmlNode *v70; // rbx
  struct WaasMedic::XmlNode **v71; // rax
  int v72; // eax
  struct WaasMedic::XmlNode **v73; // rax
  int Element; // eax
  WaasMedic::XmlNode *v75; // rbx
  __int64 v76; // rcx
  __int64 v77; // rcx
  WaasMedic::XmlNode *v78; // rbx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  int v82; // eax
  WaasMedic::XmlNode *v83; // rbx
  __int64 v84; // rcx
  __int64 v85; // rcx
  WaasMedic::XmlNode *v86; // rbx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  WaasMedic::XmlNode *v90; // rbx
  __int64 v91; // rcx
  __int64 v92; // rcx
  WaasMedic::XmlNode *v93; // rbx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  int v97; // eax
  WaasMedic::XmlNode *v98; // rbx
  __int64 v99; // rcx
  __int64 v100; // rcx
  WaasMedic::XmlNode *v101; // rbx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  WaasMedic::XmlNode *v105; // rbx
  __int64 v106; // rcx
  __int64 v107; // rcx
  int v108; // eax
  WaasMedic::XmlNode *v109; // rbx
  __int64 v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rcx
  struct WaasMedic::XmlNode **v113; // rax
  const unsigned __int16 *v114; // r8
  int v115; // eax
  struct WaasMedic::XmlNode **v116; // rax
  int v117; // eax
  WaasMedic::XmlNode *v118; // rbx
  __int64 v119; // rcx
  __int64 v120; // rcx
  WaasMedic::XmlNode *v121; // rbx
  __int64 v122; // rcx
  __int64 v123; // rcx
  __int64 v124; // rcx
  int v125; // eax
  __int64 v126; // rcx
  __int64 v127; // rcx
  struct WaasMedic::XmlNode **v128; // rax
  int v129; // eax
  __int64 v130; // rcx
  int v131; // eax
  const unsigned __int16 *v132; // rdx
  const unsigned __int16 *v133; // r8
  __int64 v134; // rcx
  int v135; // eax
  __int64 v136; // rcx
  int v137; // eax
  __int64 v138; // rcx
  int v139; // eax
  __int64 v140; // rcx
  const unsigned __int16 *v141; // rdx
  int v142; // eax
  __int64 v143; // rcx
  __int64 v144; // rcx
  signed int v145; // eax
  LPCWSTR *v146; // r9
  LPCWSTR *v147; // r8
  __int64 v148; // rcx
  void *v149; // rax
  int v150; // ecx
  int v151; // r9d
  void *v152; // rax
  LPCWSTR *v153; // r8
  const WCHAR *v154; // rcx
  signed int LastError; // eax
  LPCWSTR *v156; // r8
  LPCWSTR *v157; // r8
  const WCHAR *v158; // rcx
  DWORD FileAttributesW; // eax
  signed int v160; // eax
  const unsigned __int16 *v161; // rdx
  DWORD v162; // eax
  const WCHAR *v163; // rcx
  LPCWSTR *v164; // r8
  LPCWSTR *v165; // r8
  PSECURITY_DESCRIPTOR *v166; // rax
  const WCHAR *v167; // rcx
  signed int v168; // eax
  LPCWSTR *v169; // r8
  const WCHAR *v170; // rcx
  signed int v171; // eax
  LPCWSTR *v172; // r8
  int CMDFile; // eax
  __int64 v174; // rcx
  struct WaasMedic::XmlNode **v176; // [rsp+20h] [rbp-E0h]
  ULONG SecurityDescriptorSize[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v178; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v179; // [rsp+4Ah] [rbp-B6h] BYREF
  WaasMedic::XmlNode *v180; // [rsp+50h] [rbp-B0h] BYREF
  WaasMedic::XmlNode *v181; // [rsp+58h] [rbp-A8h] BYREF
  struct WaasMedic::XmlNode *v182; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v186; // [rsp+A8h] [rbp-58h]
  LPCWSTR v187[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct WaasMedic::XmlNode **v188; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v189; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpExistingFileName[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v191; // [rsp+F0h] [rbp-10h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i si128; // [rsp+108h] [rbp+8h]
  LPCWSTR lpNewFileName[2]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v195; // [rsp+128h] [rbp+28h]
  __int128 v196; // [rsp+138h] [rbp+38h] BYREF
  __int64 v197; // [rsp+148h] [rbp+48h]
  unsigned __int64 v198; // [rsp+150h] [rbp+50h]
  _OWORD v199[2]; // [rsp+158h] [rbp+58h] BYREF
  __int128 v200; // [rsp+178h] [rbp+78h] BYREF
  __int128 v201; // [rsp+188h] [rbp+88h]
  _OWORD Src[2]; // [rsp+198h] [rbp+98h] BYREF

  LogLevelW(5u, L"ResetRepairPlugin: RunRemediation starts");
  *(_OWORD *)StringSecurityDescriptor = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LODWORD(StringSecurityDescriptor[0]) = *a2;
  v3 = std::wstring::append(StringSecurityDescriptor, L":\\Recovery");
  *(_OWORD *)lpPathName = 0;
  v186 = 0;
  *(_OWORD *)lpPathName = *(_OWORD *)v3;
  v186 = *(_OWORD *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 7;
  *(_WORD *)v3 = 0;
  std::wstring::~wstring(StringSecurityDescriptor);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v186) < 4 )
    std::_Xlen_string();
  v6 = lpPathName;
  if ( *((_QWORD *)&v186 + 1) > 7u )
    v6 = (LPCWSTR *)lpPathName[0];
  std::wstring::wstring(v187, v4, v5, v6, v186, L"\\OEM", 4);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v188) < 0x10 )
    std::_Xlen_string();
  v9 = v187;
  if ( v189 > 7 )
    v9 = (LPCWSTR *)v187[0];
  std::wstring::wstring(lpExistingFileName, v7, v8, v9, v188, L"\\ResetConfig.xml", 16);
  if ( 0x7FFFFFFFFFFFFFFELL == (_QWORD)v188 )
    std::_Xlen_string();
  v12 = v187;
  if ( v189 > 7 )
    v12 = (LPCWSTR *)v187[0];
  std::wstring::wstring(Src, v10, v11, v12, v188, L"\\", 1);
  v13 = std::wstring::append(Src, (void *)L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd");
  v200 = 0;
  v201 = 0;
  v200 = *(_OWORD *)v13;
  v201 = *(_OWORD *)(v13 + 16);
  *(_QWORD *)(v13 + 16) = 0;
  *(_QWORD *)(v13 + 24) = 7;
  *(_WORD *)v13 = 0;
  std::wstring::~wstring(Src);
  if ( 0x7FFFFFFFFFFFFFFELL == (_QWORD)v188 )
    std::_Xlen_string();
  v16 = v187;
  if ( v189 > 7 )
    v16 = (LPCWSTR *)v187[0];
  std::wstring::wstring(StringSecurityDescriptor, v14, v15, v16, v188, L"\\", 1);
  v17 = std::wstring::append(StringSecurityDescriptor, L"ResetConfig_F62B90D4-A654-4CFE-B625-213D47A83416.xml");
  *(_OWORD *)lpNewFileName = 0;
  v195 = 0;
  *(_OWORD *)lpNewFileName = *(_OWORD *)v17;
  v195 = *(_OWORD *)(v17 + 16);
  *(_QWORD *)(v17 + 16) = 0;
  *(_QWORD *)(v17 + 24) = 7;
  *(_WORD *)v17 = 0;
  std::wstring::~wstring(StringSecurityDescriptor);
  v199[0] = 0;
  v199[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v199[0]) = 0;
  v196 = 0;
  v197 = 0;
  v198 = 7;
  LOWORD(v196) = 0;
  v18 = lpExistingFileName;
  if ( v191 > 7 )
    v18 = (LPCWSTR *)lpExistingFileName[0];
  hMem[0] = v18;
  hMem[1] = (HLOCAL)lpExistingFileName[2];
  if ( !(unsigned __int8)WaasMedic::FileExists(hMem) )
  {
    LogLevelW(5u, L"No existing ResetConfig.xml");
    v149 = (void *)std::wstring::wstring(StringSecurityDescriptor, v187);
    if ( (unsigned __int8)WaasMedic::FolderExists(v149) )
    {
LABEL_310:
      LOBYTE(v151) = 1;
      CMDFile = WaasMedic::ResetRepairPlugin::GenerateCMDFile(
                  v150,
                  (unsigned int)&v200,
                  (unsigned int)v187,
                  v151,
                  (__int64)v199,
                  (__int64)&v196);
      v21 = CMDFile;
      if ( CMDFile < 0 )
      {
        LogLevelW(2u, L"Failed to create target CMD file. Err=0x%08x", (unsigned int)CMDFile);
        goto LABEL_316;
      }
      memset(Src, 0, sizeof(Src));
      std::string::_Construct<1,char const *>(
        Src,
        "<?xml version=\"1.0\" encoding=\"utf-8\"?><Reset>  <Run Phase=\"FactoryReset_AfterImageApply\">    <Path>AfterIm"
        "ageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd</Path>    <Duration>2</Duration>  </Run></Reset>",
        204);
      LogLevelW(4u, L"Create ResetConfig.xml");
      v21 = WaasMedic::ResetRepairPlugin::WriteToFile(v174, Src, lpExistingFileName, v187);
      if ( v21 < 0 )
      {
        LogLevelW(2u, L"Failed to create new ResetConfig.xml");
        std::string::~string(Src);
        goto LABEL_316;
      }
      std::string::~string(Src);
      goto LABEL_315;
    }
    v152 = (void *)std::wstring::wstring(&SecurityAttributes, lpPathName);
    if ( !(unsigned __int8)WaasMedic::FolderExists(v152) )
    {
      v153 = lpPathName;
      if ( *((_QWORD *)&v186 + 1) > 7u )
        v153 = (LPCWSTR *)lpPathName[0];
      LogLevelW(5u, L"Create [%s]", v153);
      v154 = (const WCHAR *)lpPathName;
      if ( *((_QWORD *)&v186 + 1) > 7u )
        v154 = lpPathName[0];
      if ( !CreateDirectoryW(v154, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v156 = lpPathName;
        if ( *((_QWORD *)&v186 + 1) > 7u )
          v156 = (LPCWSTR *)lpPathName[0];
        LogLevelW(3u, L"Failed to create %s. Err=0x%08x", v156, (unsigned int)LastError);
      }
      v157 = lpPathName;
      if ( *((_QWORD *)&v186 + 1) > 7u )
        v157 = (LPCWSTR *)lpPathName[0];
      LogLevelW(5u, L"Set attributes to [%s]", v157);
      v158 = (const WCHAR *)lpPathName;
      if ( *((_QWORD *)&v186 + 1) > 7u )
        v158 = lpPathName[0];
      FileAttributesW = GetFileAttributesW(v158);
      if ( FileAttributesW == -1 )
      {
        v160 = GetLastError();
        if ( v160 > 0 )
          v160 = (unsigned __int16)v160 | 0x80070000;
        v161 = L"Failed to get file attributes for [%s]. Err=0x%08x";
      }
      else
      {
        v162 = FileAttributesW | 0x2006;
        v163 = (const WCHAR *)lpPathName;
        if ( *((_QWORD *)&v186 + 1) > 7u )
          v163 = lpPathName[0];
        if ( SetFileAttributesW(v163, v162) )
          goto LABEL_289;
        v160 = GetLastError();
        if ( v160 > 0 )
          v160 = (unsigned __int16)v160 | 0x80070000;
        v161 = L"Failed to set attributes to[%s]. Err=0x%08x";
      }
      v164 = lpPathName;
      if ( *((_QWORD *)&v186 + 1) > 7u )
        v164 = (LPCWSTR *)lpPathName[0];
      LogLevelW(3u, v161, v164, (unsigned int)v160);
    }
LABEL_289:
    v165 = v187;
    if ( v189 > 7 )
      v165 = (LPCWSTR *)v187[0];
    LogLevelW(5u, L"Create [%s]", v165);
    *(_OWORD *)StringSecurityDescriptor = 0;
    si128 = 0;
    std::wstring::_Construct<1,unsigned short const *>(StringSecurityDescriptor, L"D:PAI(A;;FA;;;BA)(A;;FA;;;SY)", 29);
    hMem[0] = 0;
    SecurityDescriptorSize[0] = 0;
    v166 = (PSECURITY_DESCRIPTOR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator&(hMem);
    v167 = (const WCHAR *)StringSecurityDescriptor;
    if ( si128.m128i_i64[1] > 7uLL )
      v167 = StringSecurityDescriptor[0];
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v167, 1u, v166, SecurityDescriptorSize) )
    {
      *(&SecurityAttributes.nLength + 1) = 0;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = hMem[0];
      SecurityAttributes.nLength = SecurityDescriptorSize[0];
      v170 = (const WCHAR *)v187;
      if ( v189 > 7 )
        v170 = v187[0];
      if ( !CreateDirectoryW(v170, &SecurityAttributes) )
      {
        v171 = GetLastError();
        if ( v171 > 0 )
          v171 = (unsigned __int16)v171 | 0x80070000;
        v172 = v187;
        if ( v189 > 7 )
          v172 = (LPCWSTR *)v187[0];
        LogLevelW(3u, L"Failed to create %s. Err=0x%08x", v172, (unsigned int)v171);
      }
    }
    else
    {
      v168 = GetLastError();
      if ( v168 > 0 )
        v168 = (unsigned __int16)v168 | 0x80070000;
      v169 = StringSecurityDescriptor;
      if ( si128.m128i_i64[1] > 7uLL )
        v169 = (LPCWSTR *)StringSecurityDescriptor[0];
      LogLevelW(3u, L"Failed to parse SDDL string [%s]. Err=0x%08x", v169, (unsigned int)v168);
    }
    if ( hMem[0] )
      LocalFree(hMem[0]);
    std::wstring::~wstring(StringSecurityDescriptor);
    goto LABEL_310;
  }
  LogLevelW(5u, L"Find existing ResetConfig.xml");
  hMem[0] = 0;
  v19 = (const unsigned __int16 *)lpExistingFileName;
  if ( v191 > 7 )
    v19 = lpExistingFileName[0];
  File = WaasMedic::XmlDocument::LoadFile(v19, (struct WaasMedic::XmlDocument **)hMem);
  v21 = File;
  v22 = lpExistingFileName;
  if ( File < 0 )
  {
    if ( v191 > 7 )
      v22 = (LPCWSTR *)lpExistingFileName[0];
    LogLevelW(2u, L"Failed to load xml [%s]. Err=0x%08x", v22, (unsigned int)File);
    if ( hMem[0] )
    {
      v23 = *(_QWORD *)hMem[0];
      if ( *(_QWORD *)hMem[0] )
      {
        *(_QWORD *)hMem[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    goto LABEL_316;
  }
  v24 = lpNewFileName;
  if ( *((_QWORD *)&v195 + 1) > 7u )
    v24 = (LPCWSTR *)lpNewFileName[0];
  if ( v191 > 7 )
    v22 = (LPCWSTR *)lpExistingFileName[0];
  LogLevelW(4u, L"Backup [%s] as [%s]", v22, v24);
  v25 = (const WCHAR *)lpNewFileName;
  if ( *((_QWORD *)&v195 + 1) > 7u )
    v25 = lpNewFileName[0];
  v26 = (const WCHAR *)lpExistingFileName;
  if ( v191 > 7 )
    v26 = lpExistingFileName[0];
  if ( CopyFileW(v26, v25, 0) )
  {
    v28 = WaasMedic::ResetRepairPlugin::CopySecurity(v27, v187, lpNewFileName);
    v21 = v28;
    if ( v28 < 0 )
    {
      LogLevelW(2u, L"Failed to copy security from OEM folder to backup file. Err=0x%08x", (unsigned int)v28);
      if ( hMem[0] )
      {
        v29 = *(_QWORD *)hMem[0];
        if ( *(_QWORD *)hMem[0] )
        {
          *(_QWORD *)hMem[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
      }
      goto LABEL_316;
    }
    v178 = 0;
    LOBYTE(v179) = 0;
    v30 = (WaasMedic *)hMem[0];
    CommandForPhase = WaasMedic::GetCommandForPhase(
                        (WaasMedic *)hMem[0],
                        (struct WaasMedic::XmlDocument *)L"FactoryReset_BeforeImageApply",
                        &v178);
    if ( CommandForPhase >= 0 )
    {
      v32 = v178;
    }
    else
    {
      LogLevelW(
        3u,
        L"Failed to check whether phase [%s] exists. Err=0x%08x",
        L"FactoryReset_BeforeImageApply",
        (unsigned int)CommandForPhase);
      v32 = 0;
    }
    v33 = WaasMedic::GetCommandForPhase(
            v30,
            (struct WaasMedic::XmlDocument *)L"FactoryReset_AfterDiskFormat",
            (unsigned __int16 *)((char *)&v178 + 1));
    if ( v33 >= 0 )
    {
      v34 = HIBYTE(v178);
    }
    else
    {
      LogLevelW(
        3u,
        L"Failed to check whether phase [%s] exists. Err=0x%08x",
        L"FactoryReset_AfterDiskFormat",
        (unsigned int)v33);
      v34 = 0;
    }
    *(_QWORD *)SecurityDescriptorSize = 0;
    AddressOf = (bool *)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(SecurityDescriptorSize);
    NodeForPhase = WaasMedic::GetNodeForPhase(
                     v30,
                     (struct WaasMedic::XmlDocument *)L"FactoryReset_AfterImageApply",
                     &v179,
                     AddressOf,
                     v176);
    v40 = NodeForPhase;
    if ( NodeForPhase < 0 )
    {
      LogLevelW(
        2u,
        L"Failed to get node for phase [%s]. Err=0x%08x",
        L"FactoryReset_AfterImageApply",
        (unsigned int)NodeForPhase);
      v41 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
      if ( *(_QWORD *)SecurityDescriptorSize )
      {
        *(_QWORD *)SecurityDescriptorSize = 0;
        v42 = *((_QWORD *)v41 + 1);
        if ( v42 )
        {
          *((_QWORD *)v41 + 1) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        }
        v43 = *((_QWORD *)v41 + 2);
        if ( v43 )
        {
          *((_QWORD *)v41 + 2) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        }
      }
      if ( v30 )
      {
        v44 = *(_QWORD *)v30;
        if ( *(_QWORD *)v30 )
        {
          *(_QWORD *)v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
      }
LABEL_54:
      v21 = v40;
      goto LABEL_316;
    }
    LOBYTE(v37) = v179;
    LOBYTE(v39) = (v32 | (unsigned __int8)(v34 | v179)) == 0;
    if ( (_BYTE)v179 )
    {
      if ( !*(_QWORD *)SecurityDescriptorSize )
      {
        LogLevelW(2u, L"node cannot be null", v38, v39);
        v45 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v46 = *((_QWORD *)v45 + 1);
          if ( v46 )
          {
            *((_QWORD *)v45 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          }
          v47 = *((_QWORD *)v45 + 2);
          if ( v47 )
          {
            *((_QWORD *)v45 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
          }
        }
        if ( v30 )
        {
          v48 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
          }
        }
        v21 = -2147024809;
        goto LABEL_316;
      }
      ChildText = WaasMedic::XmlNode::GetChildText(*(WaasMedic::XmlNode **)SecurityDescriptorSize, L"Path");
      v50 = ChildText;
      v40 = -2147023728;
      if ( ChildText == -2147023728 )
      {
        LogLevelW(2u, L"Failed to get Path attribute. Err=0x%08x", 2147943568LL);
        v51 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v52 = *((_QWORD *)v51 + 1);
          if ( v52 )
          {
            *((_QWORD *)v51 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          }
          v53 = *((_QWORD *)v51 + 2);
          if ( v53 )
          {
            *((_QWORD *)v51 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
          }
        }
        if ( v30 )
        {
          v54 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          }
        }
        goto LABEL_54;
      }
      if ( ChildText < 0 )
      {
        LogLevelW(2u, L"Failed to get text from child node Path. Err=0x%08x", (unsigned int)ChildText);
        v55 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v56 = *((_QWORD *)v55 + 1);
          if ( v56 )
          {
            *((_QWORD *)v55 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          }
          v57 = *((_QWORD *)v55 + 2);
          if ( v57 )
          {
            *((_QWORD *)v55 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          }
        }
        if ( v30 )
        {
          v58 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
        }
LABEL_85:
        v21 = v50;
        goto LABEL_316;
      }
      v59 = WaasMedic::XmlNode::GetChildText(*(WaasMedic::XmlNode **)SecurityDescriptorSize, L"Param");
      v50 = v59;
      if ( v59 == -2147023728 )
      {
        v197 = 0;
        v60 = &v196;
        if ( v198 > 7 )
          v60 = (__int128 *)v196;
        *(_WORD *)v60 = 0;
      }
      else if ( v59 < 0 )
      {
        LogLevelW(2u, L"Failed to get text from child node Param. Err=0x%08x", (unsigned int)v59);
        v66 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v67 = *((_QWORD *)v66 + 1);
          if ( v67 )
          {
            *((_QWORD *)v66 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          }
          v68 = *((_QWORD *)v66 + 2);
          if ( v68 )
          {
            *((_QWORD *)v66 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
          }
        }
        if ( v30 )
        {
          v69 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          }
        }
        goto LABEL_85;
      }
      v61 = WaasMedic::ResetRepairPlugin::GenerateCMDFile(
              (_DWORD)v60,
              (unsigned int)&v200,
              (unsigned int)v187,
              0,
              (__int64)v199,
              (__int64)&v196);
      v50 = v61;
      if ( v61 < 0 )
      {
        LogLevelW(2u, L"Failed to create target CMD file. Err=0x%08x", (unsigned int)v61);
        v62 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v63 = *((_QWORD *)v62 + 1);
          if ( v63 )
          {
            *((_QWORD *)v62 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
          }
          v64 = *((_QWORD *)v62 + 2);
          if ( v64 )
          {
            *((_QWORD *)v62 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          }
        }
        if ( v30 )
        {
          v65 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
          }
        }
        goto LABEL_85;
      }
      v180 = 0;
      v70 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
      v71 = (struct WaasMedic::XmlNode **)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(&v180);
      v72 = WaasMedic::XmlNode::SelectNode(v70, v71, L"Path");
      v50 = v72;
      if ( v72 == -2147023728 )
      {
        LogLevelW(5u, L"Phase doesn't have path node, create path node");
        v73 = (struct WaasMedic::XmlNode **)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(&v180);
        Element = WaasMedic::XmlDocument::CreateElement(v30, v73, L"Path");
        v40 = Element;
        if ( Element < 0 )
        {
          LogLevelW(2u, L"Failed to create new Path node. Err=0x%08x", (unsigned int)Element);
          v75 = v180;
          if ( v180 )
          {
            v180 = 0;
            v76 = *((_QWORD *)v75 + 1);
            if ( v76 )
            {
              *((_QWORD *)v75 + 1) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            }
            v77 = *((_QWORD *)v75 + 2);
            if ( v77 )
            {
              *((_QWORD *)v75 + 2) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
            }
          }
          v78 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
          if ( *(_QWORD *)SecurityDescriptorSize )
          {
            *(_QWORD *)SecurityDescriptorSize = 0;
            v79 = *((_QWORD *)v78 + 1);
            if ( v79 )
            {
              *((_QWORD *)v78 + 1) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            }
            v80 = *((_QWORD *)v78 + 2);
            if ( v80 )
            {
              *((_QWORD *)v78 + 2) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
            }
          }
          if ( v30 )
          {
            v81 = *(_QWORD *)v30;
            if ( *(_QWORD *)v30 )
            {
              *(_QWORD *)v30 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
            }
          }
          goto LABEL_54;
        }
        v82 = WaasMedic::XmlNode::AddChild(v180, v180);
        v40 = v82;
        if ( v82 < 0 )
        {
          LogLevelW(2u, L"Failed to add new Path node as child. Err=0x%08x", (unsigned int)v82);
          v83 = v180;
          if ( v180 )
          {
            v180 = 0;
            v84 = *((_QWORD *)v83 + 1);
            if ( v84 )
            {
              *((_QWORD *)v83 + 1) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
            }
            v85 = *((_QWORD *)v83 + 2);
            if ( v85 )
            {
              *((_QWORD *)v83 + 2) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
            }
          }
          v86 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
          if ( *(_QWORD *)SecurityDescriptorSize )
          {
            *(_QWORD *)SecurityDescriptorSize = 0;
            v87 = *((_QWORD *)v86 + 1);
            if ( v87 )
            {
              *((_QWORD *)v86 + 1) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
            }
            v88 = *((_QWORD *)v86 + 2);
            if ( v88 )
            {
              *((_QWORD *)v86 + 2) = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
            }
          }
          if ( v30 )
          {
            v89 = *(_QWORD *)v30;
            if ( *(_QWORD *)v30 )
            {
              *(_QWORD *)v30 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
            }
          }
          goto LABEL_54;
        }
      }
      else if ( v72 < 0 )
      {
        LogLevelW(2u, L"Failed to get Path node from Reset End phase. Err=0x%08x", (unsigned int)v72);
        v90 = v180;
        if ( v180 )
        {
          v180 = 0;
          v91 = *((_QWORD *)v90 + 1);
          if ( v91 )
          {
            *((_QWORD *)v90 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
          }
          v92 = *((_QWORD *)v90 + 2);
          if ( v92 )
          {
            *((_QWORD *)v90 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
          }
        }
        v93 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v94 = *((_QWORD *)v93 + 1);
          if ( v94 )
          {
            *((_QWORD *)v93 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
          }
          v95 = *((_QWORD *)v93 + 2);
          if ( v95 )
          {
            *((_QWORD *)v93 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
          }
        }
        if ( v30 )
        {
          v96 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
          }
        }
        goto LABEL_85;
      }
      LogLevelW(4u, L"Update path info");
      v97 = WaasMedic::XmlNode::SetText(v180, L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd");
      v40 = v97;
      if ( v97 < 0 )
      {
        LogLevelW(2u, L"Failed to update target cmd file path. Err=0x%08x", (unsigned int)v97);
        v98 = v180;
        if ( v180 )
        {
          v180 = 0;
          v99 = *((_QWORD *)v98 + 1);
          if ( v99 )
          {
            *((_QWORD *)v98 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
          }
          v100 = *((_QWORD *)v98 + 2);
          if ( v100 )
          {
            *((_QWORD *)v98 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
          }
        }
        v101 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v102 = *((_QWORD *)v101 + 1);
          if ( v102 )
          {
            *((_QWORD *)v101 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
          }
          v103 = *((_QWORD *)v101 + 2);
          if ( v103 )
          {
            *((_QWORD *)v101 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
          }
        }
        if ( v30 )
        {
          v104 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
          }
        }
        goto LABEL_54;
      }
      v105 = v180;
      if ( v180 )
      {
        v180 = 0;
        v106 = *((_QWORD *)v105 + 1);
        if ( v106 )
        {
          *((_QWORD *)v105 + 1) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v106 + 16LL))(v106);
        }
        v107 = *((_QWORD *)v105 + 2);
        if ( v107 )
        {
          *((_QWORD *)v105 + 2) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 16LL))(v107);
        }
      }
      goto LABEL_239;
    }
    v108 = WaasMedic::ResetRepairPlugin::GenerateCMDFile(
             v37,
             (unsigned int)&v200,
             (unsigned int)v187,
             v39,
             (__int64)v199,
             (__int64)&v196);
    v40 = v108;
    if ( v108 < 0 )
    {
      LogLevelW(2u, L"Failed to create target CMD file. Err=0x%08x", (unsigned int)v108);
      v109 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
      if ( *(_QWORD *)SecurityDescriptorSize )
      {
        *(_QWORD *)SecurityDescriptorSize = 0;
        v110 = *((_QWORD *)v109 + 1);
        if ( v110 )
        {
          *((_QWORD *)v109 + 1) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        }
        v111 = *((_QWORD *)v109 + 2);
        if ( v111 )
        {
          *((_QWORD *)v109 + 2) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v111 + 16LL))(v111);
        }
      }
      if ( v30 )
      {
        v112 = *(_QWORD *)v30;
        if ( *(_QWORD *)v30 )
        {
          *(_QWORD *)v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v112 + 16LL))(v112);
        }
      }
      goto LABEL_54;
    }
    LogLevelW(4u, L"Adding new node for Reset End phase");
    v181 = 0;
    v113 = (struct WaasMedic::XmlNode **)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(&v181);
    v115 = WaasMedic::XmlDocument::SelectNode(v30, v113, v114);
    v21 = v115;
    if ( v115 == -2147023728 )
    {
      LogLevelW(5u, L"Config doesn't have Reset node");
      v116 = (struct WaasMedic::XmlNode **)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(&v181);
      v117 = WaasMedic::XmlDocument::CreateElement(v30, v116, L"Reset");
      v40 = v117;
      if ( v117 < 0 )
      {
        LogLevelW(2u, L"Failed to create new Reset node. Err=0x%08x", (unsigned int)v117);
        v118 = v181;
        if ( v181 )
        {
          v181 = 0;
          v119 = *((_QWORD *)v118 + 1);
          if ( v119 )
          {
            *((_QWORD *)v118 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
          }
          v120 = *((_QWORD *)v118 + 2);
          if ( v120 )
          {
            *((_QWORD *)v118 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
          }
        }
        v121 = *(WaasMedic::XmlNode **)SecurityDescriptorSize;
        if ( *(_QWORD *)SecurityDescriptorSize )
        {
          *(_QWORD *)SecurityDescriptorSize = 0;
          v122 = *((_QWORD *)v121 + 1);
          if ( v122 )
          {
            *((_QWORD *)v121 + 1) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
          }
          v123 = *((_QWORD *)v121 + 2);
          if ( v123 )
          {
            *((_QWORD *)v121 + 2) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v123 + 16LL))(v123);
          }
        }
        if ( v30 )
        {
          v124 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
          }
        }
        goto LABEL_54;
      }
      v125 = WaasMedic::XmlDocument::SetRoot(v30, v181);
      v21 = v125;
      if ( v125 < 0 )
      {
        LogLevelW(2u, L"Failed to set new Reset node as Root. Err=0x%08x", (unsigned int)v125);
        WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
        WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
        if ( v30 )
        {
          v126 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
          }
        }
        goto LABEL_316;
      }
    }
    else if ( v115 < 0 )
    {
      LogLevelW(2u, L"Failed to get Reset node. Err=0x%08x", (unsigned int)v115);
      WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
      WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
      if ( v30 )
      {
        v127 = *(_QWORD *)v30;
        if ( *(_QWORD *)v30 )
        {
          *(_QWORD *)v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
        }
      }
      goto LABEL_316;
    }
    v182 = 0;
    v128 = (struct WaasMedic::XmlNode **)WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(&v182);
    v129 = WaasMedic::XmlDocument::CreateElement(v30, v128, L"Run");
    v21 = v129;
    if ( v129 >= 0 )
    {
      v131 = WaasMedic::XmlNode::AddChild(v181, v182);
      v21 = v131;
      if ( v131 >= 0 )
      {
        v135 = WaasMedic::XmlNode::SetAttribute(v182, v132, v133);
        v21 = v135;
        if ( v135 >= 0 )
        {
          v137 = WaasMedic::XmlNode::SetChildTest(
                   v182,
                   L"Path",
                   L"AfterImageApply_BDB0C1E8-6951-46C4-AB7F-C07B29F462FD.cmd");
          v21 = v137;
          if ( v137 >= 0 )
          {
            v139 = WaasMedic::XmlNode::SetChildTest(v182, L"Duration", L"2");
            v21 = v139;
            if ( v139 >= 0 )
            {
              WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
              WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
LABEL_239:
              LogLevelW(4u, L"Save changes to ResetConfig.xml");
              v141 = (const unsigned __int16 *)lpExistingFileName;
              if ( v191 > 7 )
                v141 = lpExistingFileName[0];
              v142 = WaasMedic::XmlDocument::SaveFile(v30, v141);
              v21 = v142;
              if ( v142 < 0 )
              {
                LogLevelW(2u, L"Failed to save updates to ResetConfig.xml. Err=0x%08x", (unsigned int)v142);
                WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
                if ( v30 )
                {
                  v143 = *(_QWORD *)v30;
                  if ( *(_QWORD *)v30 )
                  {
                    *(_QWORD *)v30 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v143 + 16LL))(v143);
                  }
                }
                goto LABEL_316;
              }
              WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
              if ( v30 )
              {
                v144 = *(_QWORD *)v30;
                if ( *(_QWORD *)v30 )
                {
                  *(_QWORD *)v30 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v144 + 16LL))(v144);
                }
              }
LABEL_315:
              LogLevelW(5u, L"ResetRepairPlugin: RunRemediation completes");
              goto LABEL_316;
            }
            LogLevelW(2u, L"Failed to set Duration text. Err=0x%08x", (unsigned int)v139);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
            if ( v30 )
            {
              v140 = *(_QWORD *)v30;
              if ( *(_QWORD *)v30 )
              {
                *(_QWORD *)v30 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v140 + 16LL))(v140);
              }
            }
          }
          else
          {
            LogLevelW(2u, L"Failed to set Path text. Err=0x%08x", (unsigned int)v137);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
            WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
            if ( v30 )
            {
              v138 = *(_QWORD *)v30;
              if ( *(_QWORD *)v30 )
              {
                *(_QWORD *)v30 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v138 + 16LL))(v138);
              }
            }
          }
        }
        else
        {
          LogLevelW(2u, L"Failed to set phase. Err=0x%08x", (unsigned int)v135);
          WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
          WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
          WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
          if ( v30 )
          {
            v136 = *(_QWORD *)v30;
            if ( *(_QWORD *)v30 )
            {
              *(_QWORD *)v30 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v136 + 16LL))(v136);
            }
          }
        }
      }
      else
      {
        LogLevelW(2u, L"Failed to add new Reset node as child. Err=0x%08x", (unsigned int)v131);
        WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
        WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
        WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
        if ( v30 )
        {
          v134 = *(_QWORD *)v30;
          if ( *(_QWORD *)v30 )
          {
            *(_QWORD *)v30 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
          }
        }
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to create new Run node. Err=0x%08x", (unsigned int)v129);
      WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v182);
      WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(&v181);
      WaasMedic::XInterface<WaasMedic::XmlNode>::~XInterface<WaasMedic::XmlNode>(SecurityDescriptorSize);
      if ( v30 )
      {
        v130 = *(_QWORD *)v30;
        if ( *(_QWORD *)v30 )
        {
          *(_QWORD *)v30 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
        }
      }
    }
  }
  else
  {
    v145 = GetLastError();
    v21 = v145;
    if ( v145 > 0 )
      v21 = (unsigned __int16)v145 | 0x80070000;
    v146 = lpNewFileName;
    if ( *((_QWORD *)&v195 + 1) > 7u )
      v146 = (LPCWSTR *)lpNewFileName[0];
    v147 = lpExistingFileName;
    if ( v191 > 7 )
      v147 = (LPCWSTR *)lpExistingFileName[0];
    LODWORD(v176) = v21;
    LogLevelW(2u, L"CopyFile for %s to %s failed. Err=0x%08x", v147, v146, v176);
    if ( hMem[0] )
    {
      v148 = *(_QWORD *)hMem[0];
      if ( *(_QWORD *)hMem[0] )
      {
        *(_QWORD *)hMem[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v148 + 16LL))(v148);
      }
    }
  }
LABEL_316:
  std::wstring::~wstring(&v196);
  std::wstring::~wstring(v199);
  std::wstring::~wstring(lpNewFileName);
  std::wstring::~wstring(&v200);
  std::wstring::~wstring(lpExistingFileName);
  std::wstring::~wstring(v187);
  std::wstring::~wstring(lpPathName);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18004815c  push    rbp
0x18004815e  push    rbx
0x18004815f  push    rsi
0x180048160  push    rdi
0x180048161  push    r12
0x180048163  push    r13
0x180048165  push    r14
0x180048167  push    r15
0x180048169  lea     rbp, [rsp-0C8h]
0x180048171  sub     rsp, 1C8h
0x180048178  mov     rax, cs:__security_cookie
0x18004817f  xor     rax, rsp
0x180048182  mov     [rbp+100h+var_48], rax
0x180048189  mov     rbx, rdx
0x18004818c  xor     r15d, r15d
0x18004818f  lea     rdx, aResetrepairplu_12; "ResetRepairPlugin: RunRemediation start"...
0x180048196  lea     r13d, [r15+5]
0x18004819a  mov     ecx, r13d; unsigned __int8
0x18004819d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800481a2  xorps   xmm0, xmm0
0x1800481a5  movups  xmmword ptr [rbp+100h+StringSecurityDescriptor], xmm0
0x1800481a9  movdqa  xmm1, cs:__xmm@00000000000000070000000000000001
0x1800481b1  movdqu  [rbp+100h+var_F8], xmm1
0x1800481b6  movzx   eax, word ptr [rbx]
0x1800481b9  mov     word ptr [rbp+100h+StringSecurityDescriptor], ax
0x1800481bd  mov     word ptr [rbp+100h+StringSecurityDescriptor+2], r15w
0x1800481c2  lea     rdx, aRecovery; ":\\Recovery"
0x1800481c9  lea     rcx, [rbp+100h+StringSecurityDescriptor]; Src
0x1800481cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800481d2  xorps   xmm0, xmm0
0x1800481d5  movups  xmmword ptr [rbp+100h+lpPathName], xmm0
0x1800481d9  xorps   xmm1, xmm1
0x1800481dc  movdqu  [rbp+100h+var_158], xmm1
0x1800481e1  movups  xmm0, xmmword ptr [rax]
0x1800481e4  movups  xmmword ptr [rbp+100h+lpPathName], xmm0
0x1800481e8  movups  xmm1, xmmword ptr [rax+10h]
0x1800481ec  movups  [rbp+100h+var_158], xmm1
0x1800481f0  mov     [rax+10h], r15
0x1800481f4  lea     r12d, [r15+7]
0x1800481f8  mov     [rax+18h], r12
0x1800481fc  mov     [rax], r15w
0x180048200  lea     rcx, [rbp+100h+StringSecurityDescriptor]; void *
0x180048204  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048209  mov     rcx, qword ptr [rbp+100h+var_158]
0x18004820d  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180048217  mov     rax, rbx
0x18004821a  sub     rax, rcx
0x18004821d  cmp     rax, 4
0x180048221  jb      loc_18004973F
0x180048227  lea     r9, [rbp+100h+lpPathName]
0x18004822b  cmp     qword ptr [rbp+100h+var_158+8], r12
0x18004822f  cmova   r9, [rbp+100h+lpPathName]
0x180048234  mov     [rsp+200h+var_1D0], 4
0x18004823d  lea     rax, aOem; "\\OEM"
0x180048244  mov     [rsp+200h+var_1D8], rax
0x180048249  mov     [rsp+200h+var_1E0], rcx
0x18004824e  lea     rcx, [rbp+100h+var_148]
0x180048252  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180048257  nop
0x180048258  mov     rcx, [rbp+100h+var_138]
0x18004825c  mov     rax, rbx
0x18004825f  sub     rax, rcx
0x180048262  cmp     rax, 10h
0x180048266  jb      loc_180049745
0x18004826c  lea     r9, [rbp+100h+var_148]
0x180048270  cmp     [rbp+100h+var_130], r12
0x180048274  cmova   r9, [rbp+100h+var_148]
0x180048279  mov     [rsp+200h+var_1D0], 10h
0x180048282  lea     rax, aResetconfigXml_0; "\\ResetConfig.xml"
0x180048289  mov     [rsp+200h+var_1D8], rax
0x18004828e  mov     [rsp+200h+var_1E0], rcx
0x180048293  lea     rcx, [rbp+100h+lpExistingFileName]
0x180048297  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004829c  nop
0x18004829d  mov     rcx, [rbp+100h+var_138]
0x1800482a1  mov     rax, rbx
0x1800482a4  sub     rax, rcx
0x1800482a7  lea     esi, [r15+1]
0x1800482ab  cmp     rax, rsi
0x1800482ae  jb      loc_18004974B
0x1800482b4  lea     r9, [rbp+100h+var_148]
0x1800482b8  cmp     [rbp+100h+var_130], r12
0x1800482bc  cmova   r9, [rbp+100h+var_148]
0x1800482c1  mov     [rsp+200h+var_1D0], rsi
0x1800482c6  lea     rdi, asc_18006E878; "\\"
0x1800482cd  mov     [rsp+200h+var_1D8], rdi
0x1800482d2  mov     [rsp+200h+var_1E0], rcx
0x1800482d7  lea     rcx, [rbp+100h+Src]
0x1800482de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800482e3  nop
0x1800482e4  lea     rdx, aAfterimageappl; "AfterImageApply_BDB0C1E8-6951-46C4-AB7F"...
0x1800482eb  lea     rcx, [rbp+100h+Src]; Src
0x1800482f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800482f7  xorps   xmm0, xmm0
0x1800482fa  movups  [rbp+100h+var_88], xmm0
0x1800482fe  xorps   xmm1, xmm1
0x180048301  movdqu  [rbp+100h+var_78], xmm1
0x180048309  movups  xmm0, xmmword ptr [rax]
0x18004830c  movups  [rbp+100h+var_88], xmm0
0x180048310  movups  xmm1, xmmword ptr [rax+10h]
0x180048314  movups  [rbp+100h+var_78], xmm1
0x18004831b  mov     [rax+10h], r15
0x18004831f  mov     [rax+18h], r12
0x180048323  mov     [rax], r15w
0x180048327  lea     rcx, [rbp+100h+Src]; void *
0x18004832e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048333  mov     rax, [rbp+100h+var_138]
0x180048337  sub     rbx, rax
0x18004833a  cmp     rbx, rsi
0x18004833d  jb      loc_180049739
0x180048343  lea     r9, [rbp+100h+var_148]
0x180048347  cmp     [rbp+100h+var_130], r12
0x18004834b  cmova   r9, [rbp+100h+var_148]
0x180048350  mov     [rsp+200h+var_1D0], rsi
0x180048355  mov     [rsp+200h+var_1D8], rdi
0x18004835a  mov     [rsp+200h+var_1E0], rax; struct WaasMedic::XmlNode **
0x18004835f  lea     rcx, [rbp+100h+StringSecurityDescriptor]
0x180048363  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180048368  nop
0x180048369  lea     rdx, aResetconfigF62; "ResetConfig_F62B90D4-A654-4CFE-B625-213"...
0x180048370  lea     rcx, [rbp+100h+StringSecurityDescriptor]; Src
0x180048374  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180048379  xorps   xmm0, xmm0
0x18004837c  movups  xmmword ptr [rbp+100h+lpNewFileName], xmm0
0x180048380  xorps   xmm1, xmm1
0x180048383  movdqu  [rbp+100h+var_D8], xmm1
0x180048388  movups  xmm0, xmmword ptr [rax]
0x18004838b  movups  xmmword ptr [rbp+100h+lpNewFileName], xmm0
0x18004838f  movups  xmm1, xmmword ptr [rax+10h]
0x180048393  movups  [rbp+100h+var_D8], xmm1
0x180048397  mov     [rax+10h], r15
0x18004839b  mov     [rax+18h], r12
0x18004839f  mov     [rax], r15w
0x1800483a3  lea     rcx, [rbp+100h+StringSecurityDescriptor]; void *
0x1800483a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800483ac  xorps   xmm0, xmm0
0x1800483af  movups  [rbp+100h+var_A8], xmm0
0x1800483b3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800483bb  movdqu  [rbp+100h+var_98], xmm1
0x1800483c0  mov     word ptr [rbp+100h+var_A8], r15w
0x1800483c5  movups  [rbp+100h+var_C8], xmm0
0x1800483c9  mov     [rbp+100h+var_B8], r15
0x1800483cd  mov     [rbp+100h+var_B0], r12
0x1800483d1  mov     word ptr [rbp+100h+var_C8], r15w
0x1800483d6  lea     rax, [rbp+100h+lpExistingFileName]
0x1800483da  cmp     [rbp+100h+var_110], r12
0x1800483de  cmova   rax, [rbp+100h+lpExistingFileName]
0x1800483e3  mov     [rsp+200h+hMem], rax
0x1800483e8  mov     rax, [rbp+100h+var_118]
0x1800483ec  mov     [rsp+200h+var_190], rax
0x1800483f1  lea     rcx, [rsp+200h+hMem]
0x1800483f6  call    ?FileExists@WaasMedic@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::FileExists(std::basic_string_view<ushort> const &)
0x1800483fb  mov     ecx, r13d; unsigned __int8
0x1800483fe  test    al, al
0x180048400  jz      loc_180049397
0x180048406  lea     rdx, aFindExistingRe; "Find existing ResetConfig.xml"
0x18004840d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048412  mov     [rsp+200h+hMem], r15
0x180048417  lea     rcx, [rbp+100h+lpExistingFileName]
0x18004841b  cmp     [rbp+100h+var_110], r12
0x18004841f  cmova   rcx, [rbp+100h+lpExistingFileName]; unsigned __int16 *
0x180048424  lea     rdx, [rsp+200h+hMem]; struct WaasMedic::XmlDocument **
0x180048429  call    ?LoadFile@XmlDocument@WaasMedic@@SAJPEBGPEAPEAV12@@Z; WaasMedic::XmlDocument::LoadFile(ushort const *,WaasMedic::XmlDocument * *)
0x18004842e  mov     ebx, eax
0x180048430  lea     r8, [rbp+100h+lpExistingFileName]
0x180048434  test    eax, eax
0x180048436  jns     short loc_18004847F
0x180048438  cmp     [rbp+100h+var_110], r12
0x18004843c  cmova   r8, [rbp+100h+lpExistingFileName]
0x180048441  mov     r9d, eax
0x180048444  lea     rdx, aFailedToLoadXm; "Failed to load xml [%s]. Err=0x%08x"
0x18004844b  lea     ecx, [rsi+1]; unsigned __int8
0x18004844e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048453  nop
0x180048454  mov     rax, [rsp+200h+hMem]
0x180048459  test    rax, rax
0x18004845c  jz      loc_1800496CF
0x180048462  mov     rcx, [rax]
0x180048465  test    rcx, rcx
0x180048468  jz      short loc_18004847A
0x18004846a  mov     [rax], r15
0x18004846d  mov     rax, [rcx]
0x180048470  mov     rax, [rax+10h]
0x180048474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048479  nop
0x18004847a  jmp     loc_1800496CF
0x18004847f  lea     r9, [rbp+100h+lpNewFileName]
0x180048483  cmp     qword ptr [rbp+100h+var_D8+8], r12
0x180048487  cmova   r9, [rbp+100h+lpNewFileName]
0x18004848c  cmp     [rbp+100h+var_110], r12
0x180048490  cmova   r8, [rbp+100h+lpExistingFileName]
0x180048495  lea     rdx, aBackupSAsS; "Backup [%s] as [%s]"
0x18004849c  mov     ecx, 4; unsigned __int8
0x1800484a1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800484a6  lea     rdx, [rbp+100h+lpNewFileName]
0x1800484aa  cmp     qword ptr [rbp+100h+var_D8+8], r12
0x1800484ae  cmova   rdx, [rbp+100h+lpNewFileName]; lpNewFileName
0x1800484b3  lea     rcx, [rbp+100h+lpExistingFileName]
0x1800484b7  cmp     [rbp+100h+var_110], r12
0x1800484bb  cmova   rcx, [rbp+100h+lpExistingFileName]; lpExistingFileName
0x1800484c0  xor     r8d, r8d; bFailIfExists
0x1800484c3  call    cs:__imp_CopyFileW
0x1800484c9  test    eax, eax
0x1800484cb  jz      loc_180049327
0x1800484d1  lea     r8, [rbp+100h+lpNewFileName]
0x1800484d5  lea     rdx, [rbp+100h+var_148]
0x1800484d9  call    ?CopySecurity@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WaasMedic::ResetRepairPlugin::CopySecurity(std::wstring const &,std::wstring const &)
0x1800484de  mov     ebx, eax
0x1800484e0  test    eax, eax
0x1800484e2  jns     short loc_180048524
0x1800484e4  mov     r8d, eax
0x1800484e7  lea     rdx, aFailedToCopySe; "Failed to copy security from OEM folder"...
0x1800484ee  mov     ecx, 2; unsigned __int8
0x1800484f3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800484f8  nop
0x1800484f9  mov     rax, [rsp+200h+hMem]
0x1800484fe  test    rax, rax
0x180048501  jz      loc_1800496CF
0x180048507  mov     rcx, [rax]
0x18004850a  test    rcx, rcx
0x18004850d  jz      short loc_18004851F
0x18004850f  mov     [rax], r15
0x180048512  mov     rax, [rcx]
0x180048515  mov     rax, [rax+10h]
0x180048519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004851e  nop
0x18004851f  jmp     loc_1800496CF
0x180048524  mov     byte ptr [rsp+200h+var_1B8], r15b
0x180048529  mov     byte ptr [rsp+200h+var_1B8+1], r15b
0x18004852e  mov     byte ptr [rsp+200h+var_1B6], r15b
0x180048533  xor     r9d, r9d
0x180048536  lea     r8, [rsp+200h+var_1B8]; unsigned __int16 *
0x18004853b  lea     rdx, aFactoryresetBe; "FactoryReset_BeforeImageApply"
0x180048542  mov     rdi, [rsp+200h+hMem]
0x180048547  mov     rcx, rdi; this
0x18004854a  call    ?GetCommandForPhase@WaasMedic@@YAJPEAVXmlDocument@1@PEBGAEA_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@33@Z; WaasMedic::GetCommandForPhase(WaasMedic::XmlDocument *,ushort const *,bool &,std::wstring *,std::wstring *,std::wstring *)
0x18004854f  mov     ebx, 3
0x180048554  test    eax, eax
0x180048556  jns     short loc_180048575
0x180048558  mov     r9d, eax
0x18004855b  lea     r8, aFactoryresetBe; "FactoryReset_BeforeImageApply"
0x180048562  lea     rdx, aFailedToCheckW; "Failed to check whether phase [%s] exis"...
0x180048569  mov     ecx, ebx; unsigned __int8
0x18004856b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048570  mov     r14b, r15b
0x180048573  jmp     short loc_18004857A
0x180048575  mov     r14b, byte ptr [rsp+200h+var_1B8]
0x18004857a  xor     r9d, r9d
0x18004857d  lea     r8, [rsp+200h+var_1B8+1]; unsigned __int16 *
0x180048582  lea     rdx, aFactoryresetAf_0; "FactoryReset_AfterDiskFormat"
0x180048589  mov     rcx, rdi; this
0x18004858c  call    ?GetCommandForPhase@WaasMedic@@YAJPEAVXmlDocument@1@PEBGAEA_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@33@Z; WaasMedic::GetCommandForPhase(WaasMedic::XmlDocument *,ushort const *,bool &,std::wstring *,std::wstring *,std::wstring *)
0x180048591  test    eax, eax
0x180048593  jns     short loc_1800485B2
0x180048595  mov     r9d, eax
0x180048598  lea     r8, aFactoryresetAf_0; "FactoryReset_AfterDiskFormat"
0x18004859f  lea     rdx, aFailedToCheckW; "Failed to check whether phase [%s] exis"...
0x1800485a6  mov     ecx, ebx; unsigned __int8
0x1800485a8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800485ad  mov     bl, r15b
0x1800485b0  jmp     short loc_1800485B6
0x1800485b2  mov     bl, byte ptr [rsp+200h+var_1B8+1]
0x1800485b6  mov     qword ptr [rsp+200h+SecurityDescriptorSize], r15
0x1800485bb  lea     rcx, [rsp+200h+SecurityDescriptorSize]
0x1800485c0  call    ?ReleaseAndGetAddressOf@?$XInterface@VXmlNode@WaasMedic@@@WaasMedic@@QEAAPEAPEAVXmlNode@2@XZ; WaasMedic::XInterface<WaasMedic::XmlNode>::ReleaseAndGetAddressOf(void)
0x1800485c5  mov     r9, rax; bool *
0x1800485c8  lea     r8, [rsp+200h+var_1B6]; unsigned __int16 *
0x1800485cd  lea     rdx, aFactoryresetAf; "FactoryReset_AfterImageApply"
0x1800485d4  mov     rcx, rdi; this
0x1800485d7  call    ?GetNodeForPhase@WaasMedic@@YAJPEAVXmlDocument@1@PEBGAEA_NPEAPEAVXmlNode@1@@Z; WaasMedic::GetNodeForPhase(WaasMedic::XmlDocument *,ushort const *,bool &,WaasMedic::XmlNode * *)
0x1800485dc  mov     esi, eax
0x1800485de  test    eax, eax
0x1800485e0  jns     loc_180048669
0x1800485e6  mov     r9d, eax
0x1800485e9  lea     r8, aFactoryresetAf; "FactoryReset_AfterImageApply"
0x1800485f0  lea     rdx, aFailedToGetNod; "Failed to get node for phase [%s]. Err="...
0x1800485f7  mov     ecx, 2; unsigned __int8
0x1800485fc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048601  nop
0x180048602  mov     rbx, qword ptr [rsp+200h+SecurityDescriptorSize]
0x180048607  test    rbx, rbx
0x18004860a  jz      short loc_180048645
0x18004860c  mov     qword ptr [rsp+200h+SecurityDescriptorSize], r15
0x180048611  mov     rcx, [rbx+8]
0x180048615  test    rcx, rcx
0x180048618  jz      short loc_18004862B
0x18004861a  mov     [rbx+8], r15
0x18004861e  mov     rax, [rcx]
0x180048621  mov     rax, [rax+10h]
0x180048625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004862a  nop
0x18004862b  mov     rcx, [rbx+10h]
0x18004862f  test    rcx, rcx
0x180048632  jz      short loc_180048645
0x180048634  mov     [rbx+10h], r15
0x180048638  mov     rax, [rcx]
0x18004863b  mov     rax, [rax+10h]
0x18004863f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048644  nop
0x180048645  test    rdi, rdi
  ... truncated ...
```
