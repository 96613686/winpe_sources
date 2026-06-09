# VerifyCustomCapabilityAuthorization(ulong,ushort const * *,bool,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18003bec4`
- end: `0x18003d80d`
- name: `?VerifyCustomCapabilityAuthorization@@YAJKPEAPEBG_NPEBG222@Z`
- size: `6473`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 **, bool, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180180530`

## callees

- `0x180009dc0`
- `0x180012fc8`
- `0x18001adb4`
- `0x18003157c`
- `0x18003bea4`
- `0x18003bec4`
- `0x18003d814`
- `0x18003d8b8`
- `0x18003d8f4`
- `0x18003d9b0`
- `0x18003dad0`
- `0x18004a838`
- `0x180064030`
- `0x180066780`
- `0x180069eb4`
- `0x180081b10`
- `0x180082ae0`
- `0x180086450`
- `0x18008768c`
- `0x180087ce8`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af918`
- `0x1800ba45d`
- `0x18010e3cc`
- `0x1801801f0`
- `0x180180250`
- `0x1801802ac`
- `0x1801802e4`
- `0x180180330`
- `0x180180350`
- `0x18018069c`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d206`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d3b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d206`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003d3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c3a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cb24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d470`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003d3e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003d3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d40c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d42a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d40c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d42a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c4ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c8ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cd43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d08e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d64c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c4ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c6ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c8ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ca73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cc4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003cd43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d08e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d5b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d64c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7c6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003d457`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003d457`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003c36f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003c36f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003bff7`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18003bff7`
- `capauthz!SCCDParseFile` at `0x18003cb0e`
- `capauthz!SCCDParseFile` at `0x18003cb0e`
- `capauthz!SCCDValidateCatalogFile` at `0x18003cd76`
- `capauthz!SCCDValidateCatalogFile` at `0x18003cd76`
- `capauthz!SCCDValidateAppxFile` at `0x18003d248`
- `capauthz!SCCDValidateAppxFile` at `0x18003d248`

## string_xrefs

- `0x18003c71e`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18003c763`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18003c7c5`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18003bf7e`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003bfb5`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c05c`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c3be`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c441`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c60e`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c817`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003c9bc`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003cb41`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003cb96`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003cc8c`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003cd9f`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003cf9b`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003d0ce`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003d2bc`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003d495`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003d51e`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18003d68c`: `onecore\admin\appmodel\common\customcapabilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 __fastcall VerifyCustomCapabilityAuthorization(
        __int64 a1,
        const unsigned __int16 **a2,
        char a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  char v7; // r12
  _BYTE *v8; // rsi
  int v10; // eax
  unsigned int v11; // ebx
  char v12; // al
  int MetadataPath; // eax
  unsigned int v14; // ebx
  const struct std::nothrow_t *v15; // rdx
  Common *v16; // rbx
  __int64 v17; // rax
  void *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  const WCHAR *v24; // rcx
  void *v25; // rdx
  Common *FirstFileW; // rdi
  DWORD LastError; // ebx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  LPCWSTR *v31; // r8
  LPCWSTR *v32; // r9
  unsigned int v33; // ebx
  const struct std::nothrow_t *v34; // rdx
  void *v35; // rcx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  void *v38; // rcx
  const struct std::nothrow_t *v39; // rdx
  __int64 v40; // rax
  const unsigned __int16 *v41; // rdx
  int v42; // eax
  __int64 v43; // r8
  unsigned int v44; // edi
  const struct std::nothrow_t *v45; // rdx
  void *v46; // rcx
  const struct std::nothrow_t *v47; // rdx
  __int64 v48; // r10
  WCHAR *cFileName; // rax
  unsigned int v50; // edi
  __int64 v51; // r14
  __int64 v52; // r15
  wil::details::in1diag3 *v53; // rcx
  unsigned __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // rdx
  int v57; // eax
  unsigned int v58; // r15d
  const struct std::nothrow_t *v59; // rdx
  void *v60; // rcx
  const struct std::nothrow_t *v61; // rdx
  int v62; // eax
  unsigned int v63; // edi
  const struct std::nothrow_t *v64; // rdx
  void *v65; // rcx
  const struct std::nothrow_t *v66; // rdx
  int v67; // edi
  char v68; // r14
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  const struct std::nothrow_t *v72; // rdx
  void *v73; // rcx
  const struct std::nothrow_t *v74; // rdx
  const struct std::nothrow_t *v75; // rdx
  void *v76; // rcx
  const struct std::nothrow_t *v77; // rdx
  const struct std::nothrow_t *v78; // rdx
  void *v79; // rcx
  const struct std::nothrow_t *v80; // rdx
  unsigned __int16 *v81; // rax
  _QWORD *v82; // rax
  char v83; // r14
  unsigned int i; // r13d
  const unsigned __int16 *v85; // rax
  unsigned int j; // r12d
  int appended; // eax
  unsigned int v88; // edi
  const struct std::nothrow_t *v89; // rdx
  Common *v90; // rcx
  void *v91; // rdx
  const struct std::nothrow_t *v92; // rdx
  void *v93; // rcx
  const struct std::nothrow_t *v94; // rdx
  int v95; // eax
  const struct std::nothrow_t *v96; // rdx
  unsigned int v97; // edi
  const struct std::nothrow_t *v98; // rdx
  const struct std::nothrow_t *v99; // rdx
  void *v100; // rcx
  const struct std::nothrow_t *v101; // rdx
  int v102; // eax
  bool v103; // cl
  const struct std::nothrow_t *v104; // rdx
  void *v105; // rcx
  const struct std::nothrow_t *v106; // rdx
  unsigned int v107; // edi
  const unsigned __int16 **v108; // r14
  char *v109; // rcx
  BOOL NextFileW; // eax
  DWORD v111; // edi
  __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // r8
  LPCWSTR *v115; // r8
  LPCWSTR *v116; // r9
  unsigned int v117; // edi
  const struct std::nothrow_t *v118; // rdx
  void *v119; // rcx
  const struct std::nothrow_t *v120; // rdx
  const struct std::nothrow_t *v121; // rdx
  void *v122; // rcx
  const struct std::nothrow_t *v123; // rdx
  int k; // ecx
  const struct std::nothrow_t *v125; // rdx
  void *v126; // rcx
  const struct std::nothrow_t *v127; // rdx
  const struct std::nothrow_t *v128; // rdx
  void *v129; // rcx
  const struct std::nothrow_t *v130; // rdx
  int v131; // [rsp+20h] [rbp-5F8h]
  unsigned int v132; // [rsp+20h] [rbp-5F8h]
  int *v133; // [rsp+20h] [rbp-5F8h]
  unsigned int v134; // [rsp+20h] [rbp-5F8h]
  bool v135; // [rsp+60h] [rbp-5B8h] BYREF
  __int16 v136; // [rsp+61h] [rbp-5B7h] BYREF
  char v137; // [rsp+63h] [rbp-5B5h] BYREF
  char v138; // [rsp+64h] [rbp-5B4h] BYREF
  char v139; // [rsp+65h] [rbp-5B3h] BYREF
  char v140; // [rsp+66h] [rbp-5B2h] BYREF
  char v141; // [rsp+67h] [rbp-5B1h] BYREF
  char v142; // [rsp+68h] [rbp-5B0h]
  HANDLE Token; // [rsp+70h] [rbp-5A8h] BYREF
  int v144; // [rsp+78h] [rbp-5A0h]
  unsigned __int16 *v145; // [rsp+80h] [rbp-598h] BYREF
  _QWORD *v146; // [rsp+88h] [rbp-590h]
  unsigned int v147; // [rsp+90h] [rbp-588h] BYREF
  unsigned int v148; // [rsp+94h] [rbp-584h] BYREF
  void *v149[2]; // [rsp+98h] [rbp-580h] BYREF
  int v150; // [rsp+A8h] [rbp-570h]
  const unsigned __int16 *v151; // [rsp+B0h] [rbp-568h]
  void *v152[2]; // [rsp+B8h] [rbp-560h] BYREF
  int v153; // [rsp+C8h] [rbp-550h]
  int v154; // [rsp+D0h] [rbp-548h] BYREF
  int v155; // [rsp+D4h] [rbp-544h]
  int v156; // [rsp+D8h] [rbp-540h] BYREF
  const unsigned __int16 *v157; // [rsp+E0h] [rbp-538h] BYREF
  _QWORD v158[4]; // [rsp+E8h] [rbp-530h] BYREF
  char v159; // [rsp+108h] [rbp-510h]
  __int64 v160; // [rsp+110h] [rbp-508h] BYREF
  __int64 v161; // [rsp+118h] [rbp-500h] BYREF
  __int64 v162; // [rsp+120h] [rbp-4F8h] BYREF
  __int64 v163; // [rsp+128h] [rbp-4F0h] BYREF
  __int64 v164; // [rsp+130h] [rbp-4E8h] BYREF
  unsigned __int16 *v165; // [rsp+138h] [rbp-4E0h] BYREF
  _QWORD v166[8]; // [rsp+140h] [rbp-4D8h] BYREF
  char v167; // [rsp+180h] [rbp-498h]
  void **v168; // [rsp+190h] [rbp-488h] BYREF
  void **v169; // [rsp+198h] [rbp-480h]
  void **v170; // [rsp+1A0h] [rbp-478h]
  const unsigned __int16 **v171; // [rsp+1A8h] [rbp-470h]
  LPVOID pv; // [rsp+1B0h] [rbp-468h] BYREF
  Common *v173; // [rsp+1B8h] [rbp-460h]
  const unsigned __int16 *v174; // [rsp+1C0h] [rbp-458h]
  _BYTE v175[80]; // [rsp+1D0h] [rbp-448h] BYREF
  __int128 v176; // [rsp+220h] [rbp-3F8h]
  int v177; // [rsp+230h] [rbp-3E8h]
  char v178; // [rsp+238h] [rbp-3E0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+280h] [rbp-398h] BYREF
  unsigned __int64 v180; // [rsp+298h] [rbp-380h]
  unsigned __int16 *v181[3]; // [rsp+2A0h] [rbp-378h] BYREF
  unsigned __int64 v182; // [rsp+2B8h] [rbp-360h]
  void *v183[2]; // [rsp+2C0h] [rbp-358h] BYREF
  int v184; // [rsp+2D0h] [rbp-348h]
  _QWORD v185[4]; // [rsp+2E0h] [rbp-338h] BYREF
  unsigned __int16 *v186[4]; // [rsp+300h] [rbp-318h] BYREF
  _BYTE v187[32]; // [rsp+320h] [rbp-2F8h] BYREF
  _BYTE v188[32]; // [rsp+340h] [rbp-2D8h] BYREF
  _BYTE v189[32]; // [rsp+360h] [rbp-2B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+380h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+0h]

  v7 = a3;
  v142 = a3;
  v171 = a2;
  v165 = a4;
  v174 = a5;
  v157 = a7;
  v138 = 0;
  v136 = 0;
  v139 = 0;
  v141 = 0;
  v140 = 0;
  wil::make_unique_cotaskmem_nothrow<bool [0]>(&pv, 1);
  v8 = pv;
  if ( !pv )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
      (const char *)0x8007000ELL,
      v131);
    return 2147942414LL;
  }
  v135 = 0;
  v10 = IsRetailUnlocked(&v135);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
      (const char *)(unsigned int)v10,
      v131);
    if ( v8 )
      CoTaskMemFree(v8);
    return v11;
  }
  v154 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v154, 0);
  if ( v7 && v154 == 3 || (v12 = 1, v135) )
    v12 = 0;
  v137 = v12;
  *(_OWORD *)v152 = 0;
  v153 = 0;
  MetadataPath = GetMetadataPath(v165, (struct Common::StringBuffer *)v152);
  v14 = MetadataPath;
  if ( MetadataPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
      (const char *)(unsigned int)MetadataPath,
      v131);
    if ( v152[1] )
      operator delete(v152[1], v15);
    if ( v8 )
      CoTaskMemFree(v8);
    return v14;
  }
  *(_OWORD *)v149 = 0;
  v150 = 0;
  v16 = 0;
  v173 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v176 = 0;
  v177 = 0;
  v169 = v149;
  v168 = &Common::StringBufferBuilder::`vftable';
  v170 = v149;
  v159 = 0;
  if ( a7 )
  {
    std::filesystem::path::path((__int64)v187);
    v17 = std::filesystem::path::path((__int64)v185, (__int64 *)&v157);
    v18 = (void *)std::filesystem::operator/(v188, v17, v187);
    std::_Optional_construct_base<std::filesystem::path>::_Assign<std::filesystem::path>(v158, v18);
    std::wstring::_Tidy_deallocate(v188);
    std::wstring::_Tidy_deallocate(v185);
    std::wstring::_Tidy_deallocate(v187);
  }
  v145 = (unsigned __int16 *)&Value;
  v146 = 0;
  std::wstring::wstring(v183, &v145);
  v19 = -1;
  do
    ++v19;
  while ( a6[v19] );
  v145 = a6;
  v146 = (_QWORD *)v19;
  std::wstring::wstring(v185, &v145);
  std::filesystem::operator/(v181, v185, v183);
  std::wstring::_Tidy_deallocate(v185);
  std::wstring::_Tidy_deallocate(v183);
  v20 = -1;
  do
    ++v20;
  while ( aSccd[v20] );
  v145 = L"*.sccd";
  v146 = (_QWORD *)v20;
  std::wstring::wstring(v187, &v145);
  v21 = -1;
  do
    ++v21;
  while ( a6[v21] );
  v145 = a6;
  v146 = (_QWORD *)v21;
  std::wstring::wstring(v188, &v145);
  v22 = -1;
  do
    ++v22;
  while ( Src[v22] );
  v145 = L"\\\\?\\";
  v146 = (_QWORD *)v22;
  std::wstring::wstring(v186, &v145);
  v23 = std::filesystem::operator/(v189, v186, v188);
  std::filesystem::operator/(lpFileName, v23, v187);
  std::wstring::_Tidy_deallocate(v189);
  std::wstring::_Tidy_deallocate(v186);
  std::wstring::_Tidy_deallocate(v188);
  std::wstring::_Tidy_deallocate(v187);
  v24 = (const WCHAR *)lpFileName;
  if ( v180 > 7 )
    v24 = lpFileName[0];
  FirstFileW = (Common *)FindFirstFileW(v24, &FindFileData);
  if ( FirstFileW )
  {
    Common::AutoHandleFreeFindFile(0, v25);
    v16 = FirstFileW;
    v173 = FirstFileW;
    if ( FirstFileW == (Common *)-1LL )
    {
      LastError = GetLastError();
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)0x80004005LL,
        v131);
      if ( (byte_18024560A & 0x10) != 0 )
      {
        v31 = lpFileName;
        if ( v180 > 7 )
          LODWORD(v31) = lpFileName[0];
        McTemplateU0zddq_EventWriteTransfer(v29, v28, (_DWORD)v31, -2147467259, LastError, 0);
      }
      v32 = lpFileName;
      if ( v180 > 7 )
        v32 = (LPCWSTR *)lpFileName[0];
      details::appxLog<unsigned short const *,long,unsigned long,int>(v29, v28, v30, v32);
      if ( LastError )
      {
        v33 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x92,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)LastError,
                v132);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::wstring::_Tidy_deallocate(v181);
        std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
        v35 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v35 )
          operator delete(v35, v34);
        Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v34);
        if ( v149[1] )
          operator delete(v149[1], v36);
        if ( v152[1] )
          operator delete(v152[1], v36);
        if ( v8 )
          CoTaskMemFree(v8);
        return v33;
      }
      else
      {
        std::wstring::_Tidy_deallocate(lpFileName);
        std::wstring::_Tidy_deallocate(v181);
        std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
        v38 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v38 )
          operator delete(v38, v37);
        Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v37);
        if ( v149[1] )
          operator delete(v149[1], v39);
        if ( v152[1] )
          operator delete(v152[1], v39);
        if ( v8 )
          CoTaskMemFree(v8);
        return 0;
      }
    }
  }
  v40 = lambda_fffa35bf74ee144ffb730385c523a244_::_lambda_fffa35bf74ee144ffb730385c523a244_(
          (unsigned int)&v178,
          (unsigned int)&v135,
          (unsigned int)&v137,
          (unsigned int)&v136 + 1,
          (__int64)&v136,
          (__int64)&v138,
          (__int64)&v139,
          (__int64)&v141,
          (__int64)&v140,
          (__int64)&v165);
  wil::scope_exit__lambda_fffa35bf74ee144ffb730385c523a244___(v175, v40);
  do
  {
    v41 = (const unsigned __int16 *)v181;
    if ( v182 > 7 )
      v41 = v181[0];
    v42 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v149, v41);
    v44 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)(unsigned int)v42,
        (int)v133);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      if ( v159 )
        std::wstring::_Tidy_deallocate(v158);
      v46 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v46 )
        operator delete(v46, v45);
      Common::AutoHandleFreeFindFile(v16, v45);
      if ( v149[1] )
        operator delete(v149[1], v47);
      if ( v152[1] )
        operator delete(v152[1], v47);
      if ( v8 )
        CoTaskMemFree(v8);
      return v44;
    }
    v48 = 0x3FFFFFFF;
    cFileName = FindFileData.cFileName;
    do
    {
      if ( !*cFileName )
        break;
      ++cFileName;
      --v48;
    }
    while ( v48 );
    v50 = v48 == 0 ? 0x80070057 : 0;
    v51 = (0x3FFFFFFF - v48) & ((unsigned __int128)-(__int128)(unsigned __int64)v48 >> 64) & -(__int64)(v48 != 0);
    if ( !v48 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v50,
        (int)v133);
LABEL_88:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)v50,
        (int)v133);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v60 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v60 )
        operator delete(v60, v59);
      Common::AutoHandleFreeFindFile(v16, v59);
      if ( v149[1] )
        operator delete(v149[1], v61);
      if ( v152[1] )
        operator delete(v152[1], v61);
      if ( v8 )
        CoTaskMemFree(v8);
      return v50;
    }
    v52 = *(unsigned int *)v169;
    v50 = ~(_DWORD)v51 < (unsigned int)v52 ? 0x80070216 : 0;
    v53 = retaddr;
    if ( (unsigned int)v52 > ~(_DWORD)v51 )
    {
      v54 = v50;
      v55 = 263;
LABEL_78:
      wil::details::in1diag3::_Log_Hr(
        v53,
        (void *)v55,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v54,
        (int)v133);
      goto LABEL_84;
    }
    v56 = (unsigned int)(v52 + v51);
    if ( (unsigned int)v56 <= 0x3FFFFFFF )
    {
      v57 = ((__int64 (__fastcall *)(void ***, __int64, __int64, __int64))*v168)(&v168, v56, v43, -v48);
      v50 = v57;
      v53 = retaddr;
      if ( v57 < 0 )
      {
        v54 = (unsigned int)v57;
        v55 = 269;
        goto LABEL_78;
      }
      v50 = 0;
    }
    else
    {
      v50 = -2147023613;
    }
LABEL_84:
    if ( (v50 & 0x80000000) == 0 )
    {
      memcpy_0((char *)v169[1] + 2 * v52, FindFileData.cFileName, 2LL * (unsigned int)v51);
      v58 = 0;
      v50 = 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)v50,
        (int)v133);
      v58 = 0;
    }
    if ( (v50 & 0x80000000) != 0 )
      goto LABEL_88;
    v148 = 0;
    v157 = 0;
    v156 = 0;
    v147 = 0;
    v160 = 0;
    v164 = 0;
    v161 = 0;
    v155 = 0;
    v163 = 0;
    v162 = 0;
    v166[0] = &v148;
    v166[1] = &v157;
    v166[2] = &v147;
    v166[3] = &v160;
    v166[4] = &v164;
    v166[5] = &v161;
    v166[6] = &v163;
    v166[7] = &v162;
    v167 = 1;
    Token = 0;
    v62 = Common::AutoNoImpersonateDuringScope::DropImpersonation(&Token);
    v63 = v62;
    if ( v62 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)(unsigned int)v62,
        (int)v133);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
      v167 = 0;
      lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v65 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v65 )
        operator delete(v65, v64);
      Common::AutoHandleFreeFindFile(v16, v64);
      if ( v149[1] )
        operator delete(v149[1], v66);
      if ( v152[1] )
        operator delete(v152[1], v66);
      if ( v8 )
        CoTaskMemFree(v8);
      return v63;
    }
    v133 = &v156;
    v67 = SCCDParseFile(v149[1], v152[1], &v148, &v157);
    if ( v67 < 0 )
    {
      v68 = GetLastError();
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)0x80004005LL,
        (int)&v156);
      if ( (byte_18024560A & 0x10) != 0 )
        McTemplateU0zddq_EventWriteTransfer(v70, v69, v149[1], v67, v68, 1);
      details::appxLog<unsigned short *,long,unsigned long,int>(v70, v69, v71, v149[1]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)(unsigned int)v67,
        v67);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
      v167 = 0;
      lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v73 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v73 )
        operator delete(v73, v72);
      Common::AutoHandleFreeFindFile(v16, v72);
      if ( v149[1] )
        operator delete(v149[1], v74);
      if ( v152[1] )
        operator delete(v152[1], v74);
      if ( v8 )
        CoTaskMemFree(v8);
      return (unsigned int)v67;
    }
    if ( v155 && !v7 )
    {
      LOBYTE(v136) = 1;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)0x800701CBLL,
        (int)&v156);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
      v167 = 0;
      lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v76 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v76 )
        operator delete(v76, v75);
      Common::AutoHandleFreeFindFile(v16, v75);
      if ( v149[1] )
        operator delete(v149[1], v77);
      if ( v152[1] )
        operator delete(v152[1], v77);
      if ( v8 )
        CoTaskMemFree(v8);
      return 2147942859LL;
    }
    LOBYTE(v136) = 0;
    if ( v137 && (int)SCCDValidateCatalogFile(v163, v162) < 0 )
    {
      HIBYTE(v136) = 1;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)0x800701C8LL,
        (int)&v156);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
      v167 = 0;
      lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v79 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v79 )
        operator delete(v79, v78);
      Common::AutoHandleFreeFindFile(v16, v78);
      if ( v149[1] )
        operator delete(v149[1], v80);
      if ( v152[1] )
        operator delete(v152[1], v80);
      if ( v8 )
        CoTaskMemFree(v8);
      return 2147942856LL;
    }
    HIBYTE(v136) = 0;
    v81 = (unsigned __int16 *)v181;
    if ( v182 > 7 )
      v81 = v181[0];
    v145 = v81;
    if ( v159 )
    {
      v82 = v158;
      if ( v158[3] > 7u )
        v82 = (_QWORD *)v158[0];
      v146 = v82;
    }
    else
    {
      v146 = 0;
    }
    v186[0] = L"AppxMetadata\\CodeIntegrity.cat";
    v186[1] = L"AppxSignature.p7x";
    v83 = 0;
    for ( i = 0; i < 2 && !v83; ++i )
    {
      v85 = (&v145)[i];
      v151 = v85;
      if ( v85 )
      {
        for ( j = 0; j < 2 && !v83; ++j )
        {
          *(_OWORD *)v183 = 0;
          v184 = 0;
          v185[1] = v183;
          v185[0] = &Common::StringBufferBuilder::`vftable';
          v185[2] = v183;
          appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v185, v85);
          v88 = appended;
          if ( appended < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x102,
              (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
              (const char *)(unsigned int)appended,
              (int)&v156);
            if ( v183[1] )
              operator delete(v183[1], v89);
            v90 = (Common *)Token;
            if ( Token )
            {
              Common::AutoNoImpersonateDuringScope::ChangeThreadToken(
                (Common::AutoNoImpersonateDuringScope *)Token,
                Token);
              Common::CloseHandleHelper((Common *)Token, v91);
              v90 = 0;
              Token = 0;
            }
            Common::CloseHandleHelper(v90, v89);
            v167 = 0;
            lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
            wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::wstring::_Tidy_deallocate(v181);
            if ( v159 )
              std::wstring::_Tidy_deallocate(v158);
            v93 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            if ( v93 )
              operator delete(v93, v92);
            Common::AutoHandleFreeFindFile(v16, v92);
            if ( v149[1] )
              operator delete(v149[1], v94);
            if ( v152[1] )
              operator delete(v152[1], v94);
            if ( v8 )
              CoTaskMemFree(v8);
            return v88;
          }
          v95 = Common::StringBuilder::AppendString((Common::StringBuilder *)v185, v186[j]);
          v97 = v95;
          if ( v95 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x103,
              (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
              (const char *)(unsigned int)v95,
              (int)&v156);
            if ( v183[1] )
              operator delete(v183[1], v98);
            Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
            v167 = 0;
            lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
            wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::wstring::_Tidy_deallocate(v181);
            std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
            v100 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            if ( v100 )
              operator delete(v100, v99);
            Common::AutoHandleFreeFindFile(v16, v99);
            if ( v149[1] )
              operator delete(v149[1], v101);
            if ( v152[1] )
              operator delete(v152[1], v101);
            if ( v8 )
              CoTaskMemFree(v8);
            return v97;
          }
          if ( !j )
            v139 = 1;
          if ( v156 )
          {
            v83 = 1;
            if ( v183[1] )
              operator delete(v183[1], v96);
            break;
          }
          while ( v58 < v147 )
          {
            v102 = _o__wcsicmp(v174, *(_QWORD *)(v161 + 8LL * v58));
            v144 = v102;
            if ( v137 )
            {
              v103 = (unsigned int)SCCDValidateAppxFile(
                                     v183[1],
                                     *(_QWORD *)(v160 + 8LL * v58),
                                     *(unsigned int *)(v164 + 4LL * v58)) == 0;
              v102 = v144;
            }
            else
            {
              v103 = 1;
            }
            if ( !v102 && v103 )
            {
              v83 = 1;
              break;
            }
            ++v58;
          }
          v58 = 0;
          if ( v183[1] )
            operator delete(v183[1], v96);
          v85 = v151;
        }
      }
    }
    v140 = v83;
    if ( !v83 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)0x800701C9LL,
        (int)&v156);
      Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&Token);
      v167 = 0;
      lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v105 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v105 )
        operator delete(v105, v104);
      Common::AutoHandleFreeFindFile(v16, v104);
      if ( v149[1] )
        operator delete(v149[1], v106);
      if ( v152[1] )
        operator delete(v152[1], v106);
      if ( v8 )
        CoTaskMemFree(v8);
      return 2147942857LL;
    }
    if ( !*v8 )
    {
      v107 = 0;
      v108 = v171;
      while ( v107 < v148 )
      {
        if ( !(unsigned int)_o__wcsicmp(*v108, *(_QWORD *)&v157[4 * v107]) )
        {
          *v8 = 1;
          break;
        }
        ++v107;
      }
    }
    v141 = 1;
    v109 = (char *)Token;
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
        GetLastError();
      if ( (char *)Token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(Token);
      v109 = 0;
      Token = 0;
    }
    if ( (unsigned __int64)(v109 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v109);
    v167 = 0;
    lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v166);
    NextFileW = FindNextFileW(v16, &FindFileData);
    v7 = v142;
  }
  while ( NextFileW );
  v111 = GetLastError();
  if ( v111 == 18 )
  {
    for ( k = 0; !k; k = 1 )
    {
      if ( !*v8 )
      {
        v138 = 1;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15A,
          (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
          (const char *)0x800701CCLL,
          (int)&v156);
        wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
        std::wstring::_Tidy_deallocate(lpFileName);
        std::wstring::_Tidy_deallocate(v181);
        std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
        v126 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        if ( v126 )
          operator delete(v126, v125);
        Common::AutoHandleFreeFindFile(v16, v125);
        if ( v149[1] )
          operator delete(v149[1], v127);
        if ( v152[1] )
          operator delete(v152[1], v127);
        if ( v8 )
          CoTaskMemFree(v8);
        return 2147942860LL;
      }
      v138 = 0;
    }
    wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
    std::wstring::_Tidy_deallocate(lpFileName);
    std::wstring::_Tidy_deallocate(v181);
    std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
    v129 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( v129 )
      operator delete(v129, v128);
    Common::AutoHandleFreeFindFile(v16, v128);
    if ( v149[1] )
      operator delete(v149[1], v130);
    if ( v152[1] )
      operator delete(v152[1], v130);
    if ( v8 )
      CoTaskMemFree(v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
      (const char *)0x80004005LL,
      (int)&v156);
    if ( (byte_18024560A & 0x10) != 0 )
    {
      v115 = lpFileName;
      if ( v180 > 7 )
        LODWORD(v115) = lpFileName[0];
      McTemplateU0zddq_EventWriteTransfer(v113, v112, (_DWORD)v115, -2147467259, v111, 2);
    }
    v116 = lpFileName;
    if ( v180 > 7 )
      v116 = (LPCWSTR *)lpFileName[0];
    details::appxLog<unsigned short const *,long,unsigned long,int>(v113, v112, v114, v116);
    if ( v111 )
    {
      v117 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x153,
               (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
               (const char *)v111,
               v134);
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v119 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v119 )
        operator delete(v119, v118);
      Common::AutoHandleFreeFindFile(v16, v118);
      if ( v149[1] )
        operator delete(v149[1], v120);
      if ( v152[1] )
        operator delete(v152[1], v120);
      if ( v8 )
        CoTaskMemFree(v8);
      return v117;
    }
    else
    {
      wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v175);
      std::wstring::_Tidy_deallocate(lpFileName);
      std::wstring::_Tidy_deallocate(v181);
      std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(v158);
      v122 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      if ( v122 )
        operator delete(v122, v121);
      Common::AutoHandleFreeFindFile(v16, v121);
      if ( v149[1] )
        operator delete(v149[1], v123);
      if ( v152[1] )
        operator delete(v152[1], v123);
      if ( v8 )
        CoTaskMemFree(v8);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x18003bec4  mov     r11, rsp
0x18003bec7  mov     [r11+8], rbx
0x18003becb  mov     [r11+18h], rsi
0x18003becf  push    rdi
0x18003bed0  push    r12
0x18003bed2  push    r13
0x18003bed4  push    r14
0x18003bed6  push    r15
0x18003bed8  sub     rsp, 5F0h
0x18003bedf  movaps  xmmword ptr [r11-38h], xmm6
0x18003bee4  mov     rax, cs:__security_cookie
0x18003beeb  xor     rax, rsp
0x18003beee  mov     [rsp+618h+var_48], rax
0x18003bef6  mov     r12b, r8b
0x18003bef9  mov     [rsp+618h+var_5B0], r8b
0x18003befe  mov     [rsp+618h+var_470], rdx
0x18003bf06  mov     [r11-4E0h], r9
0x18003bf0d  mov     rax, [rsp+618h+arg_20]
0x18003bf15  mov     [rsp+618h+var_458], rax
0x18003bf1d  mov     rdi, [rsp+618h+arg_30]
0x18003bf25  mov     [r11-538h], rdi
0x18003bf2c  xor     r15d, r15d
0x18003bf2f  lea     r13d, [r15+1]
0x18003bf33  mov     byte ptr [rsp+618h+var_5B7+3], r15b
0x18003bf38  mov     byte ptr [rsp+618h+var_5B7], r15b
0x18003bf3d  mov     byte ptr [rsp+618h+var_5B7+1], r15b
0x18003bf42  mov     [rsp+618h+var_5B3], r15b
0x18003bf47  mov     [rsp+618h+var_5B1], r15b
0x18003bf4c  mov     [rsp+618h+var_5B2], r15b
0x18003bf51  mov     edx, r13d
0x18003bf54  lea     rcx, [r11-468h]
0x18003bf5b  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@_N@wil@@YA?AV?$unique_ptr@$$BY0A@_NU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<bool [0]>(unsigned __int64)
0x18003bf60  nop
0x18003bf61  mov     rsi, [rsp+618h+pv]
0x18003bf69  test    rsi, rsi
0x18003bf6c  jnz     short loc_18003BF95
0x18003bf6e  mov     rcx, [rsp+618h]; this
0x18003bf76  mov     ebx, 8007000Eh
0x18003bf7b  mov     r9d, ebx; char *
0x18003bf7e  lea     r8, aOnecoreAdminAp_102; "onecore\\admin\\appmodel\\common\\custo"...
0x18003bf85  lea     edx, [rsi+65h]; void *
0x18003bf88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bf8d  nop
0x18003bf8e  mov     eax, ebx
0x18003bf90  jmp     loc_18003D7DA
0x18003bf95  mov     [rsp+618h+var_5B8], r15b
0x18003bf9a  lea     rcx, [rsp+618h+var_5B8]; bool *
0x18003bf9f  call    ?IsRetailUnlocked@@YAJPEA_N@Z; IsRetailUnlocked(bool *)
0x18003bfa4  mov     ebx, eax
0x18003bfa6  test    eax, eax
0x18003bfa8  jns     short loc_18003BFE2
0x18003bfaa  mov     rcx, [rsp+618h]; this
0x18003bfb2  mov     r9d, eax; char *
0x18003bfb5  lea     r8, aOnecoreAdminAp_102; "onecore\\admin\\appmodel\\common\\custo"...
0x18003bfbc  mov     edx, 69h ; 'i'; void *
0x18003bfc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bfc6  nop
0x18003bfc7  test    rsi, rsi
0x18003bfca  jz      short loc_18003BFDB
0x18003bfcc  mov     rcx, rsi; pv
0x18003bfcf  call    cs:__imp_CoTaskMemFree
0x18003bfd6  nop     dword ptr [rax+rax+00h]
0x18003bfdb  mov     eax, ebx
0x18003bfdd  jmp     loc_18003D7DA
0x18003bfe2  mov     [rsp+618h+var_548], r15d
0x18003bfea  xor     r8d, r8d
0x18003bfed  lea     rdx, [rsp+618h+var_548]
0x18003bff5  xor     ecx, ecx
0x18003bff7  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003bffe  nop     dword ptr [rax+rax+00h]
0x18003c003  test    r12b, r12b
0x18003c006  jz      short loc_18003C012
0x18003c008  cmp     [rsp+618h+var_548], 3
0x18003c010  jz      short loc_18003C01C
0x18003c012  cmp     [rsp+618h+var_5B8], r15b
0x18003c017  mov     al, r13b
0x18003c01a  jz      short loc_18003C01F
0x18003c01c  mov     al, r15b
0x18003c01f  mov     byte ptr [rsp+618h+var_5B7+2], al
0x18003c023  xorps   xmm0, xmm0
0x18003c026  movups  xmmword ptr [rsp+618h+var_560], xmm0
0x18003c02e  mov     [rsp+618h+var_550], r15d
0x18003c036  lea     rdx, [rsp+618h+var_560]; struct Common::StringBuffer *
0x18003c03e  mov     rcx, [rsp+618h+var_4E0]; unsigned __int16 *
0x18003c046  call    ?GetMetadataPath@@YAJPEBGPEAVStringBuffer@Common@@@Z; GetMetadataPath(ushort const *,Common::StringBuffer *)
0x18003c04b  mov     ebx, eax
0x18003c04d  test    eax, eax
0x18003c04f  jns     short loc_18003C09C
0x18003c051  mov     rcx, [rsp+618h]; this
0x18003c059  mov     r9d, eax; char *
0x18003c05c  lea     r8, aOnecoreAdminAp_102; "onecore\\admin\\appmodel\\common\\custo"...
0x18003c063  mov     edx, 72h ; 'r'; void *
0x18003c068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c06d  nop
0x18003c06e  mov     rcx, [rsp+618h+var_560+8]; void *
0x18003c076  test    rcx, rcx
0x18003c079  jz      short loc_18003C081
0x18003c07b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c080  nop
0x18003c081  test    rsi, rsi
0x18003c084  jz      short loc_18003C095
0x18003c086  mov     rcx, rsi; pv
0x18003c089  call    cs:__imp_CoTaskMemFree
0x18003c090  nop     dword ptr [rax+rax+00h]
0x18003c095  mov     eax, ebx
0x18003c097  jmp     loc_18003D7DA
0x18003c09c  xorps   xmm0, xmm0
0x18003c09f  movups  xmmword ptr [rsp+618h+var_580], xmm0
0x18003c0a7  mov     [rsp+618h+var_570], r15d
0x18003c0af  mov     rbx, r15
0x18003c0b2  mov     [rsp+618h+var_460], rbx
0x18003c0ba  xor     edx, edx; Val
0x18003c0bc  mov     r8d, 250h; Size
0x18003c0c2  lea     rcx, [rsp+618h+FindFileData]; void *
0x18003c0ca  call    memset_0
0x18003c0cf  xorps   xmm6, xmm6
0x18003c0d2  movups  [rsp+618h+var_3F8], xmm6
0x18003c0da  mov     [rsp+618h+var_3E8], r15d
0x18003c0e2  lea     rax, [rsp+618h+var_580]
0x18003c0ea  mov     [rsp+618h+var_480], rax
0x18003c0f2  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18003c0f9  mov     [rsp+618h+var_488], rax
0x18003c101  lea     rax, [rsp+618h+var_580]
0x18003c109  mov     [rsp+618h+var_478], rax
0x18003c111  mov     [rsp+618h+var_510], r15b
0x18003c119  test    rdi, rdi
0x18003c11c  jz      short loc_18003C193
0x18003c11e  lea     rcx, [rsp+618h+var_2F8]
0x18003c126  call    ??$?0$$BY00G$0A@@path@filesystem@std@@QEAA@AEAY00$$CBGW4format@012@@Z; std::filesystem::path::path(ushort const (&)[1],std::filesystem::path::format)
0x18003c12b  nop
0x18003c12c  lea     rdx, [rsp+618h+var_538]
0x18003c134  lea     rcx, [rsp+618h+var_338]
0x18003c13c  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x18003c141  nop
0x18003c142  lea     r8, [rsp+618h+var_2F8]
0x18003c14a  mov     rdx, rax
0x18003c14d  lea     rcx, [rsp+618h+var_2D8]
0x18003c155  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18003c15a  mov     rdx, rax
0x18003c15d  lea     rcx, [rsp+618h+var_530]
0x18003c165  call    ??$_Assign@Vpath@filesystem@std@@@?$_Optional_construct_base@Vpath@filesystem@std@@@std@@QEAAX$$QEAVpath@filesystem@1@@Z; std::_Optional_construct_base<std::filesystem::path>::_Assign<std::filesystem::path>(std::filesystem::path &&)
0x18003c16a  lea     rcx, [rsp+618h+var_2D8]
0x18003c172  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c177  nop
0x18003c178  lea     rcx, [rsp+618h+var_338]
0x18003c180  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c185  nop
0x18003c186  lea     rcx, [rsp+618h+var_2F8]
0x18003c18e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c193  lea     rax, Value
0x18003c19a  mov     [rsp+618h+var_598], rax
0x18003c1a2  mov     [rsp+618h+var_590], r15
0x18003c1aa  lea     rdx, [rsp+618h+var_598]
0x18003c1b2  lea     rcx, [rsp+618h+var_358]
0x18003c1ba  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18003c1bf  nop
0x18003c1c0  mov     rdi, [rsp+618h+arg_28]
0x18003c1c8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003c1cc  mov     rax, r14
0x18003c1cf  inc     rax
0x18003c1d2  cmp     [rdi+rax*2], r15w
0x18003c1d7  jnz     short loc_18003C1CF
0x18003c1d9  mov     [rsp+618h+var_598], rdi
0x18003c1e1  mov     [rsp+618h+var_590], rax
0x18003c1e9  lea     rdx, [rsp+618h+var_598]
0x18003c1f1  lea     rcx, [rsp+618h+var_338]
0x18003c1f9  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18003c1fe  nop
0x18003c1ff  lea     r8, [rsp+618h+var_358]
0x18003c207  lea     rdx, [rsp+618h+var_338]
0x18003c20f  lea     rcx, [rsp+618h+var_378]
0x18003c217  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18003c21c  nop
0x18003c21d  lea     rcx, [rsp+618h+var_338]
0x18003c225  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c22a  nop
0x18003c22b  lea     rcx, [rsp+618h+var_358]
0x18003c233  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c238  mov     rcx, cs:off_1801AE1D8; "*.sccd"
0x18003c23f  mov     rax, r14
0x18003c242  inc     rax
0x18003c245  cmp     [rcx+rax*2], r15w
0x18003c24a  jnz     short loc_18003C242
0x18003c24c  mov     [rsp+618h+var_598], rcx
0x18003c254  mov     [rsp+618h+var_590], rax
0x18003c25c  lea     rdx, [rsp+618h+var_598]
0x18003c264  lea     rcx, [rsp+618h+var_2F8]
0x18003c26c  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18003c271  nop
0x18003c272  mov     rax, r14
0x18003c275  inc     rax
0x18003c278  cmp     [rdi+rax*2], r15w
0x18003c27d  jnz     short loc_18003C275
0x18003c27f  mov     [rsp+618h+var_598], rdi
0x18003c287  mov     [rsp+618h+var_590], rax
0x18003c28f  lea     rdx, [rsp+618h+var_598]
0x18003c297  lea     rcx, [rsp+618h+var_2D8]
0x18003c29f  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18003c2a4  nop
0x18003c2a5  mov     rcx, cs:off_1801AE1C8; "\\\\?\\"
0x18003c2ac  mov     rax, r14
0x18003c2af  inc     rax
0x18003c2b2  cmp     [rcx+rax*2], r15w
0x18003c2b7  jnz     short loc_18003C2AF
0x18003c2b9  mov     [rsp+618h+var_598], rcx
0x18003c2c1  mov     [rsp+618h+var_590], rax
0x18003c2c9  lea     rdx, [rsp+618h+var_598]
0x18003c2d1  lea     rcx, [rsp+618h+var_318]
0x18003c2d9  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18003c2de  nop
0x18003c2df  lea     r8, [rsp+618h+var_2D8]
0x18003c2e7  lea     rdx, [rsp+618h+var_318]
0x18003c2ef  lea     rcx, [rsp+618h+var_2B8]
0x18003c2f7  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18003c2fc  nop
0x18003c2fd  lea     r8, [rsp+618h+var_2F8]
0x18003c305  mov     rdx, rax
0x18003c308  lea     rcx, [rsp+618h+lpFileName]
0x18003c310  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18003c315  nop
0x18003c316  lea     rcx, [rsp+618h+var_2B8]
0x18003c31e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c323  nop
0x18003c324  lea     rcx, [rsp+618h+var_318]
0x18003c32c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c331  nop
0x18003c332  lea     rcx, [rsp+618h+var_2D8]
0x18003c33a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c33f  nop
0x18003c340  lea     rcx, [rsp+618h+var_2F8]
0x18003c348  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c34d  lea     rcx, [rsp+618h+lpFileName]
0x18003c355  cmp     [rsp+618h+var_380], 7
0x18003c35e  cmova   rcx, [rsp+618h+lpFileName]; lpFileName
0x18003c367  lea     rdx, [rsp+618h+FindFileData]; lpFindFileData
0x18003c36f  call    cs:__imp_FindFirstFileW
0x18003c376  nop     dword ptr [rax+rax+00h]
0x18003c37b  mov     rdi, rax
0x18003c37e  test    rax, rax
0x18003c381  jz      loc_18003C566
0x18003c387  xor     ecx, ecx; this
0x18003c389  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18003c38e  mov     rbx, rdi
0x18003c391  mov     [rsp+618h+var_460], rbx
0x18003c399  cmp     rdi, r14
0x18003c39c  jnz     loc_18003C566
0x18003c3a2  call    cs:__imp_GetLastError
0x18003c3a9  nop     dword ptr [rax+rax+00h]
0x18003c3ae  mov     ebx, eax
0x18003c3b0  mov     rcx, [rsp+618h]; this
0x18003c3b8  mov     r9d, 80004005h; char *
0x18003c3be  lea     r8, aOnecoreAdminAp_102; "onecore\\admin\\appmodel\\common\\custo"...
0x18003c3c5  mov     edx, 91h; void *
0x18003c3ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c3cf  test    cs:byte_18024560A, 10h
0x18003c3d6  jz      short loc_18003C406
0x18003c3d8  lea     r8, [rsp+618h+lpFileName]
0x18003c3e0  cmp     [rsp+618h+var_380], 7
0x18003c3e9  cmova   r8, [rsp+618h+lpFileName]
0x18003c3f2  mov     dword ptr [rsp+618h+var_5F0], r15d
0x18003c3f7  mov     [rsp+618h+var_5F8], ebx; unsigned int
0x18003c3fb  mov     r9d, 80004005h
0x18003c401  call    McTemplateU0zddq_EventWriteTransfer
0x18003c406  lea     r9, [rsp+618h+lpFileName]
0x18003c40e  cmp     [rsp+618h+var_380], 7
0x18003c417  cmova   r9, [rsp+618h+lpFileName]
0x18003c420  mov     dword ptr [rsp+618h+var_5E8], r15d
0x18003c425  mov     dword ptr [rsp+618h+var_5F0], ebx
0x18003c429  call    ??$appxLog@PEBGJKH@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGJKH@Z; details::appxLog<ushort const *,long,ulong,int>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,long,ulong,int)
0x18003c42e  test    ebx, ebx
0x18003c430  jz      loc_18003C4DD
0x18003c436  mov     rcx, [rsp+618h]; this
0x18003c43e  mov     r9d, ebx; char *
0x18003c441  lea     r8, aOnecoreAdminAp_102; "onecore\\admin\\appmodel\\common\\custo"...
0x18003c448  mov     edx, 92h; void *
0x18003c44d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003c452  mov     ebx, eax
0x18003c454  lea     rcx, [rsp+618h+lpFileName]
0x18003c45c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c461  nop
0x18003c462  lea     rcx, [rsp+618h+var_378]
0x18003c46a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c46f  nop
0x18003c470  lea     rcx, [rsp+618h+var_530]
0x18003c478  call    ??1?$_Optional_destruct_base@VKeyPath@RegistryCompatibility@DEH@OSIntegration@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>::~_Optional_destruct_base<OSIntegration::DEH::RegistryCompatibility::KeyPath,0>(void)
0x18003c47d  nop
0x18003c47e  psrldq  xmm6, 8
0x18003c483  movq    rcx, xmm6; void *
0x18003c488  test    rcx, rcx
0x18003c48b  jz      short loc_18003C493
0x18003c48d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c492  nop
0x18003c493  mov     rcx, r14; this
0x18003c496  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x18003c49b  nop
0x18003c49c  mov     rcx, [rsp+618h+var_580+8]; void *
0x18003c4a4  test    rcx, rcx
0x18003c4a7  jz      short loc_18003C4AF
0x18003c4a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003c4ae  nop
  ... truncated ...
```
