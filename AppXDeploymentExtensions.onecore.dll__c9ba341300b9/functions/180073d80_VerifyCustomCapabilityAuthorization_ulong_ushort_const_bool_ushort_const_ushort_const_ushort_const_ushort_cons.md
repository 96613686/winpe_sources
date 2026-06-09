# VerifyCustomCapabilityAuthorization(ulong,ushort const * *,bool,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180073d80`
- end: `0x1800754b1`
- name: `?VerifyCustomCapabilityAuthorization@@YAJKPEAPEBG_NPEBG222@Z`
- size: `5937`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 **, char, unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180089df0`
- `0x1801e9304`

## callees

- `0x18000e6e0`
- `0x18000fed0`
- `0x18001aba8`
- `0x18001c348`
- `0x18001c3c8`
- `0x18001c3fc`
- `0x18001c4fc`
- `0x18002cc90`
- `0x18004a648`
- `0x180073d80`
- `0x1800754b8`
- `0x1800755ec`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a2854`
- `0x1800a678c`
- `0x1800a67f0`
- `0x1800a6828`
- `0x1800af1c8`
- `0x1800b10c0`
- `0x1800b1804`
- `0x1800bd394`
- `0x1800cd264`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f10e4`
- `0x1801e8fd4`
- `0x1801e9030`
- `0x1801e9088`
- `0x1801e90c0`
- `0x1801e910c`
- `0x1801e912c`
- `0x1801e96bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180074f23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800750e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180074f23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800750e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007515f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007515f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800747b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800747b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074fec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075122`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180073eba`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180073eba`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007514c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007514c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007424c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007424c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007438a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800743fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007467d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007485c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074af2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074be8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007528d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007530d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800753cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075474`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073f4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007438a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800743fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074551`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007467d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007485c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074af2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074be8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007528d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007530d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800753cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075474`
- `capauthz!SCCDParseFile` at `0x1800748f1`
- `capauthz!SCCDParseFile` at `0x1800748f1`
- `capauthz!SCCDValidateAppxFile` at `0x180074f5f`
- `capauthz!SCCDValidateAppxFile` at `0x180074f5f`
- `capauthz!SCCDValidateCatalogFile` at `0x180074b1f`
- `capauthz!SCCDValidateCatalogFile` at `0x180074b1f`

## string_xrefs

- `0x1800745bb`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180073e47`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180073e7e`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180073f27`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18007428f`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074312`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x1800744b1`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x1800745f8`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074786`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074918`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18007496d`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074a4c`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074b42`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074d25`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074e10`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180074fc1`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x18007517e`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180075207`: `onecore\admin\appmodel\common\customcapabilities.cpp`
- `0x180075347`: `onecore\admin\appmodel\common\customcapabilities.cpp`

## pseudocode

```c
__int64 __fastcall VerifyCustomCapabilityAuthorization(
        unsigned int a1,
        const unsigned __int16 **a2,
        char a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  char v7; // r15
  unsigned int v8; // r12d
  void *v10; // rsi
  int v11; // eax
  unsigned int v12; // ebx
  bool v13; // al
  int MetadataPath; // eax
  unsigned int v15; // ebx
  Common *v16; // rbx
  struct std::filesystem::path *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  struct std::filesystem::path *v23; // rdx
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
  void *v34; // rdx
  void *v35; // rdx
  __int64 v36; // rax
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  unsigned int v39; // edi
  void *v40; // rdx
  void *v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // r9
  WCHAR *cFileName; // rax
  unsigned int appended; // edi
  void *v46; // rdx
  int v47; // eax
  unsigned int v48; // edi
  void *v49; // rdx
  void *v50; // rcx
  unsigned __int64 v51; // rdx
  int v52; // edi
  char v53; // r15
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  void *v57; // rdx
  void *v58; // rdx
  void *v59; // rdx
  unsigned __int16 *v60; // rax
  _QWORD *v61; // rax
  char v62; // r15
  const unsigned __int16 *v63; // rax
  __int64 v64; // r13
  int v65; // eax
  unsigned int v66; // edi
  void *v67; // rdx
  int v68; // eax
  unsigned int v69; // edi
  void *v70; // rdx
  __int64 i; // r12
  int v72; // eax
  bool v73; // cl
  void *v74; // rdx
  void *v75; // rcx
  unsigned __int64 v76; // rdx
  unsigned int v77; // r12d
  unsigned int v78; // r13d
  __int64 v79; // rdi
  __int64 j; // r15
  BOOL NextFileW; // eax
  DWORD v82; // edi
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  LPCWSTR *v86; // r8
  LPCWSTR *v87; // r9
  unsigned int v88; // edi
  void *v89; // rdx
  void *v90; // rdx
  unsigned int k; // ecx
  void *v92; // rdx
  void *v93; // rdx
  void *v94; // rcx
  unsigned __int64 v95; // rdx
  int v96; // [rsp+20h] [rbp-608h]
  unsigned int v97; // [rsp+20h] [rbp-608h]
  int *v98; // [rsp+20h] [rbp-608h]
  unsigned int v99; // [rsp+20h] [rbp-608h]
  bool v100; // [rsp+60h] [rbp-5C8h] BYREF
  __int16 v101; // [rsp+61h] [rbp-5C7h] BYREF
  bool v102; // [rsp+63h] [rbp-5C5h] BYREF
  char v103; // [rsp+64h] [rbp-5C4h] BYREF
  char v104; // [rsp+65h] [rbp-5C3h] BYREF
  char v105; // [rsp+66h] [rbp-5C2h] BYREF
  char v106; // [rsp+67h] [rbp-5C1h] BYREF
  char v107; // [rsp+68h] [rbp-5C0h]
  HANDLE hObject; // [rsp+70h] [rbp-5B8h] BYREF
  unsigned int v109; // [rsp+78h] [rbp-5B0h]
  unsigned __int16 *v110; // [rsp+80h] [rbp-5A8h] BYREF
  _QWORD *v111; // [rsp+88h] [rbp-5A0h]
  unsigned int v112; // [rsp+90h] [rbp-598h] BYREF
  unsigned int v113; // [rsp+94h] [rbp-594h] BYREF
  unsigned int v114; // [rsp+98h] [rbp-590h]
  void *v115[2]; // [rsp+A0h] [rbp-588h] BYREF
  int v116; // [rsp+B0h] [rbp-578h]
  const unsigned __int16 *v117; // [rsp+B8h] [rbp-570h]
  void *v118[2]; // [rsp+C0h] [rbp-568h] BYREF
  int v119; // [rsp+D0h] [rbp-558h]
  int v120; // [rsp+D8h] [rbp-550h] BYREF
  int v121; // [rsp+DCh] [rbp-54Ch]
  int v122; // [rsp+E0h] [rbp-548h] BYREF
  int v123; // [rsp+E4h] [rbp-544h]
  const unsigned __int16 *v124; // [rsp+E8h] [rbp-540h] BYREF
  _QWORD v125[4]; // [rsp+F0h] [rbp-538h] BYREF
  char v126; // [rsp+110h] [rbp-518h]
  __int128 v127; // [rsp+118h] [rbp-510h] BYREF
  int v128; // [rsp+128h] [rbp-500h]
  __int64 v129; // [rsp+130h] [rbp-4F8h] BYREF
  __int64 v130; // [rsp+138h] [rbp-4F0h] BYREF
  __int64 v131; // [rsp+140h] [rbp-4E8h] BYREF
  __int64 v132; // [rsp+148h] [rbp-4E0h] BYREF
  __int64 v133; // [rsp+150h] [rbp-4D8h] BYREF
  unsigned __int16 *v134; // [rsp+158h] [rbp-4D0h] BYREF
  _QWORD v135[8]; // [rsp+160h] [rbp-4C8h] BYREF
  char v136; // [rsp+1A0h] [rbp-488h]
  Common *v137; // [rsp+1B0h] [rbp-478h]
  const unsigned __int16 *v138; // [rsp+1B8h] [rbp-470h]
  LPVOID pv; // [rsp+1C0h] [rbp-468h] BYREF
  const unsigned __int16 **v140; // [rsp+1C8h] [rbp-460h]
  _BYTE v141[80]; // [rsp+1D0h] [rbp-458h] BYREF
  _QWORD v142[3]; // [rsp+220h] [rbp-408h] BYREF
  char v143; // [rsp+238h] [rbp-3F0h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+280h] [rbp-3A8h] BYREF
  unsigned __int64 v145; // [rsp+298h] [rbp-390h]
  unsigned __int16 *v146[3]; // [rsp+2A0h] [rbp-388h] BYREF
  unsigned __int64 v147; // [rsp+2B8h] [rbp-370h]
  __int128 v148; // [rsp+2C0h] [rbp-368h] BYREF
  int v149; // [rsp+2D0h] [rbp-358h]
  _QWORD v150[4]; // [rsp+2E0h] [rbp-348h] BYREF
  unsigned __int16 *v151[4]; // [rsp+300h] [rbp-328h] BYREF
  _BYTE v152[32]; // [rsp+320h] [rbp-308h] BYREF
  _BYTE v153[32]; // [rsp+340h] [rbp-2E8h] BYREF
  _BYTE v154[32]; // [rsp+360h] [rbp-2C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+380h] [rbp-2A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+0h]

  v7 = a3;
  v107 = a3;
  v140 = a2;
  v114 = a1;
  v134 = a4;
  v138 = a5;
  v124 = a7;
  v8 = 0;
  v103 = 0;
  v101 = 0;
  v104 = 0;
  v106 = 0;
  v105 = 0;
  if ( !a1 )
    return 0;
  wil::make_unique_cotaskmem_nothrow<bool [0]>(&pv, a1);
  v10 = pv;
  if ( pv )
  {
    v100 = 0;
    v11 = IsRetailUnlocked(&v100);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v120 = 0;
      RtlGetDeviceFamilyInfoEnum(0, &v120, 0);
      v13 = (!v7 || v120 != 3) && !v100;
      v102 = v13;
      *(_OWORD *)v118 = 0;
      v119 = 0;
      MetadataPath = GetMetadataPath(v134, (struct Common::StringBuffer *)v118);
      v15 = MetadataPath;
      if ( MetadataPath >= 0 )
      {
        *(_OWORD *)v115 = 0;
        v116 = 0;
        v16 = 0;
        v137 = 0;
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        v127 = 0;
        v128 = 0;
        v142[1] = v115;
        v142[0] = &Common::StringBufferBuilder::`vftable';
        v142[2] = v115;
        v126 = 0;
        if ( a7 )
        {
          std::filesystem::path::path(v152);
          v17 = (struct std::filesystem::path *)std::filesystem::path::path(v150, &v124);
          v18 = std::filesystem::operator/((std::filesystem::path *)v153, v17);
          if ( v126 )
          {
            std::wstring::operator=(v125, v18);
          }
          else
          {
            std::wstring::wstring(v125, v18);
            v126 = 1;
          }
          std::wstring::_Tidy_deallocate(v153);
          std::wstring::_Tidy_deallocate(v150);
          std::wstring::_Tidy_deallocate(v152);
        }
        v110 = (unsigned __int16 *)&LocaleName;
        v111 = 0;
        std::wstring::wstring(&v148, &v110);
        v19 = -1;
        do
          ++v19;
        while ( a6[v19] );
        v110 = a6;
        v111 = (_QWORD *)v19;
        std::wstring::wstring(v150, &v110);
        std::filesystem::operator/((std::filesystem::path *)v146, (struct std::filesystem::path *)v150);
        std::wstring::_Tidy_deallocate(v150);
        std::wstring::_Tidy_deallocate(&v148);
        v20 = -1;
        do
          ++v20;
        while ( aSccd[v20] );
        v110 = L"*.sccd";
        v111 = (_QWORD *)v20;
        std::wstring::wstring(v152, &v110);
        v21 = -1;
        do
          ++v21;
        while ( a6[v21] );
        v110 = a6;
        v111 = (_QWORD *)v21;
        std::wstring::wstring(v153, &v110);
        v22 = -1;
        do
          ++v22;
        while ( asc_18023EB28[v22] );
        v110 = L"\\\\?\\";
        v111 = (_QWORD *)v22;
        std::wstring::wstring(v151, &v110);
        v23 = (struct std::filesystem::path *)std::filesystem::operator/(
                                                (std::filesystem::path *)v154,
                                                (struct std::filesystem::path *)v151);
        std::filesystem::operator/((std::filesystem::path *)lpFileName, v23);
        std::wstring::_Tidy_deallocate(v154);
        std::wstring::_Tidy_deallocate(v151);
        std::wstring::_Tidy_deallocate(v153);
        std::wstring::_Tidy_deallocate(v152);
        v24 = (const WCHAR *)lpFileName;
        if ( v145 > 7 )
          v24 = lpFileName[0];
        FirstFileW = (Common *)FindFirstFileW(v24, &FindFileData);
        if ( FirstFileW
          && (Common::AutoHandleFreeFindFile(0, v25), v16 = FirstFileW, v137 = FirstFileW, FirstFileW == (Common *)-1LL) )
        {
          LastError = GetLastError();
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x91,
            (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
            (const char *)0x80004005LL,
            v96);
          if ( (byte_1802E21CA & 0x10) != 0 )
          {
            v31 = lpFileName;
            if ( v145 > 7 )
              LODWORD(v31) = lpFileName[0];
            McTemplateU0zddq_EventWriteTransfer(v29, v28, (_DWORD)v31, -2147467259, LastError, 0);
          }
          v32 = lpFileName;
          if ( v145 > 7 )
            v32 = (LPCWSTR *)lpFileName[0];
          details::appxLog<unsigned short const *,long,unsigned long,int>(v29, v28, v30, v32);
          if ( LastError )
          {
            v33 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x92,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                    (const char *)LastError,
                    v97);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::wstring::_Tidy_deallocate(v146);
            std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
            Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v34);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
            if ( v10 )
              CoTaskMemFree(v10);
            return v33;
          }
          else
          {
            std::wstring::_Tidy_deallocate(lpFileName);
            std::wstring::_Tidy_deallocate(v146);
            std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
            Common::AutoHandleFreeFindFile((Common *)0xFFFFFFFFFFFFFFFFLL, v35);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
            if ( v10 )
              CoTaskMemFree(v10);
            return 0;
          }
        }
        else
        {
          v36 = lambda_fffa35bf74ee144ffb730385c523a244_::_lambda_fffa35bf74ee144ffb730385c523a244_(
                  (unsigned int)&v143,
                  (unsigned int)&v100,
                  (unsigned int)&v102,
                  (unsigned int)&v101 + 1,
                  (__int64)&v101,
                  (__int64)&v103,
                  (__int64)&v104,
                  (__int64)&v106,
                  (__int64)&v105,
                  (__int64)&v134);
          wil::scope_exit__lambda_fffa35bf74ee144ffb730385c523a244___(v141, v36);
          do
          {
            v37 = (const unsigned __int16 *)v146;
            if ( v147 > 7 )
              v37 = v146[0];
            v38 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v115, v37);
            v39 = v38;
            if ( v38 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA8,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)(unsigned int)v38,
                (int)v98);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              if ( v126 )
                std::wstring::_Tidy_deallocate(v125);
              v41 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
              if ( v41 )
                operator delete(v41, (unsigned __int64)v40);
              Common::AutoHandleFreeFindFile(v16, v40);
              if ( v115[1] )
                operator delete(v115[1], v42);
              if ( v118[1] )
                operator delete(v118[1], v42);
              if ( v10 )
                CoTaskMemFree(v10);
              return v39;
            }
            v43 = 0x3FFFFFFF;
            cFileName = FindFileData.cFileName;
            do
            {
              if ( !*cFileName )
                break;
              ++cFileName;
              --v43;
            }
            while ( v43 );
            appended = v43 == 0 ? 0x80070057 : 0;
            if ( !v43 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x35,
                (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
                (const char *)appended,
                (int)v98);
LABEL_69:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA9,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)appended,
                (int)v98);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v46);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return appended;
            }
            appended = Common::StringBuilder::AppendChars(
                         (Common::StringBuilder *)v142,
                         FindFileData.cFileName,
                         v43 != 0 ? (0x3FFFFFFF - v43) & ((unsigned __int128)-(__int128)(unsigned __int64)v43 >> 64) : 0);
            if ( (appended & 0x80000000) != 0 )
              goto LABEL_69;
            v113 = 0;
            v124 = 0;
            v122 = 0;
            v112 = 0;
            v132 = 0;
            v131 = 0;
            v130 = 0;
            v121 = 0;
            v129 = 0;
            v133 = 0;
            v135[0] = &v113;
            v135[1] = &v124;
            v135[2] = &v112;
            v135[3] = &v132;
            v135[4] = &v131;
            v135[5] = &v130;
            v135[6] = &v129;
            v135[7] = &v133;
            v136 = 1;
            hObject = 0;
            v47 = Common::AutoNoImpersonateDuringScope::DropImpersonation(&hObject);
            v48 = v47;
            if ( v47 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCD,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)(unsigned int)v47,
                (int)v98);
              Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
              v136 = 0;
              lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              if ( v126 )
                std::wstring::_Tidy_deallocate(v125);
              v50 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
              if ( v50 )
                operator delete(v50, (unsigned __int64)v49);
              Common::AutoHandleFreeFindFile(v16, v49);
              if ( v115[1] )
                operator delete(v115[1], v51);
              if ( v118[1] )
                operator delete(v118[1], v51);
              if ( v10 )
                CoTaskMemFree(v10);
              return v48;
            }
            v98 = &v122;
            v52 = SCCDParseFile(v115[1], v118[1], &v113, &v124);
            if ( v52 < 0 )
            {
              v53 = GetLastError();
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xE6,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)0x80004005LL,
                (int)&v122);
              if ( (byte_1802E21CA & 0x10) != 0 )
                McTemplateU0zddq_EventWriteTransfer(v55, v54, v115[1], v52, v53, 1);
              details::appxLog<unsigned short *,long,unsigned long,int>(v55, v54, v56, v115[1]);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE7,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)(unsigned int)v52,
                v52);
              Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
              v136 = 0;
              lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v57);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return (unsigned int)v52;
            }
            if ( v121 && !v7 )
            {
              LOBYTE(v101) = 1;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEB,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)0x800701CBLL,
                (int)&v122);
              Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
              v136 = 0;
              lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v58);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return 2147942859LL;
            }
            LOBYTE(v101) = 0;
            if ( v102 && (int)SCCDValidateCatalogFile(v129, v133) < 0 )
            {
              HIBYTE(v101) = 1;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEF,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)0x800701C8LL,
                (int)&v122);
              Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
              v136 = 0;
              lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v59);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return 2147942856LL;
            }
            HIBYTE(v101) = 0;
            v60 = (unsigned __int16 *)v146;
            if ( v147 > 7 )
              v60 = v146[0];
            v110 = v60;
            if ( v126 )
            {
              v61 = v125;
              if ( v125[3] > 7u )
                v61 = (_QWORD *)v125[0];
              v111 = v61;
            }
            else
            {
              v111 = 0;
            }
            v151[0] = L"AppxMetadata\\CodeIntegrity.cat";
            v151[1] = L"AppxSignature.p7x";
            v62 = 0;
            while ( 1 )
            {
              v109 = v8;
              if ( v8 >= 2 || v62 )
                break;
              v63 = (&v110)[v8];
              v117 = v63;
              if ( v63 )
              {
                v64 = 0;
                while ( 1 )
                {
                  if ( (unsigned int)v64 >= 2 || v62 )
                    goto LABEL_128;
                  v148 = 0;
                  v149 = 0;
                  v150[1] = &v148;
                  v150[0] = &Common::StringBufferBuilder::`vftable';
                  v150[2] = &v148;
                  v65 = Common::StringBuilder::AppendString((Common::StringBuilder *)v150, v63);
                  v66 = v65;
                  if ( v65 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x102,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                      (const char *)(unsigned int)v65,
                      (int)&v122);
                    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v148);
                    Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
                    v136 = 0;
                    lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
                    wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
                    std::wstring::_Tidy_deallocate(lpFileName);
                    std::wstring::_Tidy_deallocate(v146);
                    std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
                    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
                    Common::AutoHandleFreeFindFile(v16, v67);
                    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
                    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
                    if ( v10 )
                      CoTaskMemFree(v10);
                    return v66;
                  }
                  v68 = Common::StringBuilder::AppendString((Common::StringBuilder *)v150, v151[v64]);
                  v69 = v68;
                  if ( v68 < 0 )
                    break;
                  if ( !(_DWORD)v64 )
                    v104 = 1;
                  if ( v122 )
                  {
                    v62 = 1;
                    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v148);
LABEL_128:
                    v8 = v109;
                    goto LABEL_129;
                  }
                  for ( i = 0; (unsigned int)i < v112; i = (unsigned int)(i + 1) )
                  {
                    v72 = _o__wcsicmp(v138, *(_QWORD *)(v130 + 8 * i));
                    v123 = v72;
                    if ( v102 )
                    {
                      v73 = (unsigned int)SCCDValidateAppxFile(
                                            *((_QWORD *)&v148 + 1),
                                            *(_QWORD *)(v132 + 8 * i),
                                            *(unsigned int *)(v131 + 4 * i)) == 0;
                      v72 = v123;
                    }
                    else
                    {
                      v73 = 1;
                    }
                    if ( !v72 && v73 )
                    {
                      v62 = 1;
                      break;
                    }
                  }
                  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v148);
                  v64 = (unsigned int)(v64 + 1);
                  v63 = v117;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x103,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                  (const char *)(unsigned int)v68,
                  (int)&v122);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v148);
                Common::AutoNoImpersonateDuringScope::~AutoNoImpersonateDuringScope((Common::AutoNoImpersonateDuringScope *)&hObject);
                v136 = 0;
                lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
                wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
                std::wstring::_Tidy_deallocate(lpFileName);
                std::wstring::_Tidy_deallocate(v146);
                std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
                Common::AutoHandleFreeFindFile(v16, v70);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
                if ( v10 )
                  CoTaskMemFree(v10);
                return v69;
              }
LABEL_129:
              ++v8;
            }
            v105 = v62;
            if ( !v62 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x12F,
                (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                (const char *)0x800701C9LL,
                (int)&v122);
              Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
              v136 = 0;
              lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              if ( v126 )
                std::wstring::_Tidy_deallocate(v125);
              v75 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
              if ( v75 )
                operator delete(v75, (unsigned __int64)v74);
              Common::AutoHandleFreeFindFile(v16, v74);
              if ( v115[1] )
                operator delete(v115[1], v76);
              if ( v118[1] )
                operator delete(v118[1], v76);
              if ( v10 )
                CoTaskMemFree(v10);
              return 2147942857LL;
            }
            v77 = 0;
            v78 = v114;
            if ( v114 )
            {
              v79 = 0;
              do
              {
                if ( !*((_BYTE *)v10 + v79) )
                {
                  for ( j = 0; (unsigned int)j < v113; j = (unsigned int)(j + 1) )
                  {
                    if ( !(unsigned int)_o__wcsicmp(v140[v79], *(_QWORD *)&v124[4 * j]) )
                    {
                      *((_BYTE *)v10 + v79) = 1;
                      break;
                    }
                  }
                }
                if ( !v77 )
                  v106 = 1;
                ++v77;
                ++v79;
              }
              while ( v77 < v78 );
            }
            Common::AutoNoImpersonateDuringScope::RestoreImpersonation((Common::AutoNoImpersonateDuringScope *)&hObject);
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(hObject);
            v8 = 0;
            v136 = 0;
            lambda_29d07d461f4d265dacbe5268462cb0c2_::operator()(v135);
            NextFileW = FindNextFileW(v16, &FindFileData);
            v7 = v107;
          }
          while ( NextFileW );
          v82 = GetLastError();
          if ( v82 == 18 )
          {
            for ( k = 0; k < v78; ++k )
            {
              if ( !*((_BYTE *)v10 + k) )
              {
                v103 = 1;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x15A,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                  (const char *)0x800701CCLL,
                  (int)&v122);
                wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
                std::wstring::_Tidy_deallocate(lpFileName);
                std::wstring::_Tidy_deallocate(v146);
                std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
                Common::AutoHandleFreeFindFile(v16, v92);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
                if ( v10 )
                  CoTaskMemFree(v10);
                return 2147942860LL;
              }
              v103 = 0;
            }
            wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
            std::wstring::_Tidy_deallocate(lpFileName);
            std::wstring::_Tidy_deallocate(v146);
            if ( v126 )
              std::wstring::_Tidy_deallocate(v125);
            v94 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            if ( v94 )
              operator delete(v94, (unsigned __int64)v93);
            Common::AutoHandleFreeFindFile(v16, v93);
            if ( v115[1] )
              operator delete(v115[1], v95);
            if ( v118[1] )
              operator delete(v118[1], v95);
            if ( v10 )
              CoTaskMemFree(v10);
            return 0;
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x152,
              (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
              (const char *)0x80004005LL,
              (int)&v122);
            if ( (byte_1802E21CA & 0x10) != 0 )
            {
              v86 = lpFileName;
              if ( v145 > 7 )
                LODWORD(v86) = lpFileName[0];
              McTemplateU0zddq_EventWriteTransfer(v84, v83, (_DWORD)v86, -2147467259, v82, 2);
            }
            v87 = lpFileName;
            if ( v145 > 7 )
              v87 = (LPCWSTR *)lpFileName[0];
            details::appxLog<unsigned short const *,long,unsigned long,int>(v84, v83, v85, v87);
            if ( v82 )
            {
              v88 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x153,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
                      (const char *)v82,
                      v99);
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v89);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return v88;
            }
            else
            {
              wil::details::lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___::_lambda_call__lambda_fffa35bf74ee144ffb730385c523a244___(v141);
              std::wstring::_Tidy_deallocate(lpFileName);
              std::wstring::_Tidy_deallocate(v146);
              std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(v125);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v127);
              Common::AutoHandleFreeFindFile(v16, v90);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v115);
              Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
              if ( v10 )
                CoTaskMemFree(v10);
              return 0;
            }
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72,
          (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
          (const char *)(unsigned int)MetadataPath,
          v96);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v118);
        if ( v10 )
          CoTaskMemFree(v10);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
        (const char *)(unsigned int)v11,
        v96);
      if ( v10 )
        CoTaskMemFree(v10);
      return v12;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\admin\\appmodel\\common\\customcapabilities.cpp",
      (const char *)0x8007000ELL,
      v96);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180073d80  mov     r11, rsp
0x180073d83  push    rbx
0x180073d84  push    rsi
0x180073d85  push    rdi
0x180073d86  push    r12
0x180073d88  push    r13
0x180073d8a  push    r14
0x180073d8c  push    r15
0x180073d8e  sub     rsp, 5F0h
0x180073d95  movaps  xmmword ptr [r11-48h], xmm6
0x180073d9a  mov     rax, cs:__security_cookie
0x180073da1  xor     rax, rsp
0x180073da4  mov     [rsp+628h+var_58], rax
0x180073dac  mov     r15b, r8b
0x180073daf  mov     [rsp+628h+var_5C0], r8b
0x180073db4  mov     [rsp+628h+var_460], rdx
0x180073dbc  mov     r13d, ecx
0x180073dbf  mov     [rsp+628h+var_590], r13d
0x180073dc7  mov     [r11-4D0h], r9
0x180073dce  mov     rax, [rsp+628h+arg_20]
0x180073dd6  mov     [rsp+628h+var_470], rax
0x180073dde  mov     rdi, [rsp+628h+arg_30]
0x180073de6  mov     [r11-540h], rdi
0x180073ded  xor     r12d, r12d
0x180073df0  mov     byte ptr [rsp+628h+var_5C7+3], r12b
0x180073df5  mov     byte ptr [rsp+628h+var_5C7], r12b
0x180073dfa  mov     byte ptr [rsp+628h+var_5C7+1], r12b
0x180073dff  mov     [rsp+628h+var_5C3], r12b
0x180073e04  mov     [rsp+628h+var_5C1], r12b
0x180073e09  mov     [rsp+628h+var_5C2], r12b
0x180073e0e  test    ecx, ecx
0x180073e10  jnz     short loc_180073E19
0x180073e12  xor     eax, eax
0x180073e14  jmp     loc_180075485
0x180073e19  mov     rdx, r13
0x180073e1c  lea     rcx, [rsp+628h+pv]
0x180073e24  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@_N@wil@@YA?AV?$unique_ptr@$$BY0A@_NU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<bool [0]>(unsigned __int64)
0x180073e29  nop
0x180073e2a  mov     rsi, [rsp+628h+pv]
0x180073e32  test    rsi, rsi
0x180073e35  jnz     short loc_180073E5E
0x180073e37  mov     rcx, [rsp+628h]; this
0x180073e3f  mov     ebx, 8007000Eh
0x180073e44  mov     r9d, ebx; char *
0x180073e47  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\custo"...
0x180073e4e  lea     edx, [rsi+65h]; void *
0x180073e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073e56  nop
0x180073e57  mov     eax, ebx
0x180073e59  jmp     loc_180075485
0x180073e5e  mov     [rsp+628h+var_5C8], r12b
0x180073e63  lea     rcx, [rsp+628h+var_5C8]; bool *
0x180073e68  call    ?IsRetailUnlocked@@YAJPEA_N@Z; IsRetailUnlocked(bool *)
0x180073e6d  mov     ebx, eax
0x180073e6f  test    eax, eax
0x180073e71  jns     short loc_180073EA5
0x180073e73  mov     rcx, [rsp+628h]; this
0x180073e7b  mov     r9d, eax; char *
0x180073e7e  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\custo"...
0x180073e85  mov     edx, 69h ; 'i'; void *
0x180073e8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073e8f  nop
0x180073e90  test    rsi, rsi
0x180073e93  jz      short loc_180073E9E
0x180073e95  mov     rcx, rsi; pv
0x180073e98  call    cs:__imp_CoTaskMemFree
0x180073e9e  mov     eax, ebx
0x180073ea0  jmp     loc_180075485
0x180073ea5  mov     [rsp+628h+var_550], r12d
0x180073ead  xor     r8d, r8d
0x180073eb0  lea     rdx, [rsp+628h+var_550]
0x180073eb8  xor     ecx, ecx
0x180073eba  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180073ec0  test    r15b, r15b
0x180073ec3  jz      short loc_180073ECF
0x180073ec5  cmp     [rsp+628h+var_550], 3
0x180073ecd  jz      short loc_180073EE1
0x180073ecf  cmp     [rsp+628h+var_5C8], r12b
0x180073ed4  jnz     short loc_180073EE1
0x180073ed6  mov     r14d, 1
0x180073edc  mov     al, r14b
0x180073edf  jmp     short loc_180073EEA
0x180073ee1  mov     al, r12b
0x180073ee4  mov     r14d, 1
0x180073eea  mov     byte ptr [rsp+628h+var_5C7+2], al
0x180073eee  xorps   xmm0, xmm0
0x180073ef1  movups  xmmword ptr [rsp+628h+var_568], xmm0
0x180073ef9  mov     [rsp+628h+var_558], r12d
0x180073f01  lea     rdx, [rsp+628h+var_568]; struct Common::StringBuffer *
0x180073f09  mov     rcx, [rsp+628h+var_4D0]; unsigned __int16 *
0x180073f11  call    ?GetMetadataPath@@YAJPEBGPEAVStringBuffer@Common@@@Z; GetMetadataPath(ushort const *,Common::StringBuffer *)
0x180073f16  mov     ebx, eax
0x180073f18  test    eax, eax
0x180073f1a  jns     short loc_180073F5C
0x180073f1c  mov     rcx, [rsp+628h]; this
0x180073f24  mov     r9d, eax; char *
0x180073f27  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\custo"...
0x180073f2e  mov     edx, 72h ; 'r'; void *
0x180073f33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073f38  nop
0x180073f39  lea     rcx, [rsp+628h+var_568]; this
0x180073f41  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180073f46  nop
0x180073f47  test    rsi, rsi
0x180073f4a  jz      short loc_180073F55
0x180073f4c  mov     rcx, rsi; pv
0x180073f4f  call    cs:__imp_CoTaskMemFree
0x180073f55  mov     eax, ebx
0x180073f57  jmp     loc_180075485
0x180073f5c  xorps   xmm0, xmm0
0x180073f5f  movups  xmmword ptr [rsp+628h+var_588], xmm0
0x180073f67  mov     [rsp+628h+var_578], r12d
0x180073f6f  mov     rbx, r12
0x180073f72  mov     [rsp+628h+var_478], rbx
0x180073f7a  xor     edx, edx; Val
0x180073f7c  mov     r8d, 250h; Size
0x180073f82  lea     rcx, [rsp+628h+FindFileData]; void *
0x180073f8a  call    memset_0
0x180073f8f  xorps   xmm6, xmm6
0x180073f92  movups  [rsp+628h+var_510], xmm6
0x180073f9a  mov     [rsp+628h+var_500], r12d
0x180073fa2  lea     rax, [rsp+628h+var_588]
0x180073faa  mov     [rsp+628h+var_400], rax
0x180073fb2  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180073fb9  mov     [rsp+628h+var_408], rax
0x180073fc1  lea     rax, [rsp+628h+var_588]
0x180073fc9  mov     [rsp+628h+var_3F8], rax
0x180073fd1  mov     [rsp+628h+var_518], r12b
0x180073fd9  test    rdi, rdi
0x180073fdc  jz      loc_180074070
0x180073fe2  lea     rcx, [rsp+628h+var_308]
0x180073fea  call    ??$?0$$BY00G$0A@@path@filesystem@std@@QEAA@AEAY00$$CBGW4format@012@@Z; std::filesystem::path::path(ushort const (&)[1],std::filesystem::path::format)
0x180073fef  nop
0x180073ff0  lea     rdx, [rsp+628h+var_540]
0x180073ff8  lea     rcx, [rsp+628h+var_348]
0x180074000  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x180074005  nop
0x180074006  lea     r8, [rsp+628h+var_308]
0x18007400e  mov     rdx, rax; struct std::filesystem::path *
0x180074011  lea     rcx, [rsp+628h+var_2E8]; this
0x180074019  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18007401e  mov     rdx, rax
0x180074021  lea     rcx, [rsp+628h+var_538]
0x180074029  cmp     [rsp+628h+var_518], r12b
0x180074031  jz      short loc_18007403A
0x180074033  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180074038  jmp     short loc_180074047
0x18007403a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18007403f  mov     [rsp+628h+var_518], r14b
0x180074047  lea     rcx, [rsp+628h+var_2E8]
0x18007404f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074054  nop
0x180074055  lea     rcx, [rsp+628h+var_348]
0x18007405d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074062  nop
0x180074063  lea     rcx, [rsp+628h+var_308]
0x18007406b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074070  lea     rax, LocaleName
0x180074077  mov     [rsp+628h+var_5A8], rax
0x18007407f  mov     [rsp+628h+var_5A0], r12
0x180074087  lea     rdx, [rsp+628h+var_5A8]
0x18007408f  lea     rcx, [rsp+628h+var_368]
0x180074097  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18007409c  nop
0x18007409d  mov     rdi, [rsp+628h+arg_28]
0x1800740a5  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800740a9  mov     rax, r13
0x1800740ac  inc     rax
0x1800740af  cmp     [rdi+rax*2], r12w
0x1800740b4  jnz     short loc_1800740AC
0x1800740b6  mov     [rsp+628h+var_5A8], rdi
0x1800740be  mov     [rsp+628h+var_5A0], rax
0x1800740c6  lea     rdx, [rsp+628h+var_5A8]
0x1800740ce  lea     rcx, [rsp+628h+var_348]
0x1800740d6  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x1800740db  nop
0x1800740dc  lea     r8, [rsp+628h+var_368]
0x1800740e4  lea     rdx, [rsp+628h+var_348]; struct std::filesystem::path *
0x1800740ec  lea     rcx, [rsp+628h+var_388]; this
0x1800740f4  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800740f9  nop
0x1800740fa  lea     rcx, [rsp+628h+var_348]
0x180074102  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074107  nop
0x180074108  lea     rcx, [rsp+628h+var_368]
0x180074110  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074115  mov     rcx, cs:off_180214B90; "*.sccd"
0x18007411c  mov     rax, r13
0x18007411f  inc     rax
0x180074122  cmp     [rcx+rax*2], r12w
0x180074127  jnz     short loc_18007411F
0x180074129  mov     [rsp+628h+var_5A8], rcx
0x180074131  mov     [rsp+628h+var_5A0], rax
0x180074139  lea     rdx, [rsp+628h+var_5A8]
0x180074141  lea     rcx, [rsp+628h+var_308]
0x180074149  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x18007414e  nop
0x18007414f  mov     rax, r13
0x180074152  inc     rax
0x180074155  cmp     [rdi+rax*2], r12w
0x18007415a  jnz     short loc_180074152
0x18007415c  mov     [rsp+628h+var_5A8], rdi
0x180074164  mov     [rsp+628h+var_5A0], rax
0x18007416c  lea     rdx, [rsp+628h+var_5A8]
0x180074174  lea     rcx, [rsp+628h+var_2E8]
0x18007417c  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x180074181  nop
0x180074182  mov     rcx, cs:off_180214B80; "\\\\?\\"
0x180074189  mov     rax, r13
0x18007418c  inc     rax
0x18007418f  cmp     [rcx+rax*2], r12w
0x180074194  jnz     short loc_18007418C
0x180074196  mov     [rsp+628h+var_5A8], rcx
0x18007419e  mov     [rsp+628h+var_5A0], rax
0x1800741a6  lea     rdx, [rsp+628h+var_5A8]
0x1800741ae  lea     rcx, [rsp+628h+var_328]
0x1800741b6  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x1800741bb  nop
0x1800741bc  lea     r8, [rsp+628h+var_2E8]
0x1800741c4  lea     rdx, [rsp+628h+var_328]; struct std::filesystem::path *
0x1800741cc  lea     rcx, [rsp+628h+var_2C8]; this
0x1800741d4  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800741d9  nop
0x1800741da  lea     r8, [rsp+628h+var_308]
0x1800741e2  mov     rdx, rax; struct std::filesystem::path *
0x1800741e5  lea     rcx, [rsp+628h+lpFileName]; this
0x1800741ed  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800741f2  nop
0x1800741f3  lea     rcx, [rsp+628h+var_2C8]
0x1800741fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074200  nop
0x180074201  lea     rcx, [rsp+628h+var_328]
0x180074209  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007420e  nop
0x18007420f  lea     rcx, [rsp+628h+var_2E8]
0x180074217  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007421c  nop
0x18007421d  lea     rcx, [rsp+628h+var_308]
0x180074225  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007422a  lea     rcx, [rsp+628h+lpFileName]
0x180074232  cmp     [rsp+628h+var_390], 7
0x18007423b  cmova   rcx, [rsp+628h+lpFileName]; lpFileName
0x180074244  lea     rdx, [rsp+628h+FindFileData]; lpFindFileData
0x18007424c  call    cs:__imp_FindFirstFileW
0x180074252  mov     rdi, rax
0x180074255  test    rax, rax
0x180074258  jz      loc_180074409
0x18007425e  xor     ecx, ecx; this
0x180074260  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180074265  mov     rbx, rdi
0x180074268  mov     [rsp+628h+var_478], rbx
0x180074270  cmp     rdi, r13
0x180074273  jnz     loc_180074409
0x180074279  call    cs:__imp_GetLastError
0x18007427f  mov     ebx, eax
0x180074281  mov     rcx, [rsp+628h]; this
0x180074289  mov     r9d, 80004005h; char *
0x18007428f  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\custo"...
0x180074296  mov     edx, 91h; void *
0x18007429b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800742a0  test    cs:byte_1802E21CA, 10h
0x1800742a7  jz      short loc_1800742D7
0x1800742a9  lea     r8, [rsp+628h+lpFileName]
0x1800742b1  cmp     [rsp+628h+var_390], 7
0x1800742ba  cmova   r8, [rsp+628h+lpFileName]
0x1800742c3  mov     dword ptr [rsp+628h+var_600], r12d
0x1800742c8  mov     [rsp+628h+var_608], ebx; unsigned int
0x1800742cc  mov     r9d, 80004005h
0x1800742d2  call    McTemplateU0zddq_EventWriteTransfer
0x1800742d7  lea     r9, [rsp+628h+lpFileName]
0x1800742df  cmp     [rsp+628h+var_390], 7
0x1800742e8  cmova   r9, [rsp+628h+lpFileName]
0x1800742f1  mov     dword ptr [rsp+628h+var_5F8], r12d
0x1800742f6  mov     dword ptr [rsp+628h+var_600], ebx
0x1800742fa  call    ??$appxLog@PEBGJKH@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@PEBGJKH@Z; details::appxLog<ushort const *,long,ulong,int>(long,_GUID const &,_EVENT_DESCRIPTOR const &,ushort const *,long,ulong,int)
0x1800742ff  test    ebx, ebx
0x180074301  jz      loc_180074397
0x180074307  mov     rcx, [rsp+628h]; this
0x18007430f  mov     r9d, ebx; char *
0x180074312  lea     r8, aOnecoreAdminAp_108; "onecore\\admin\\appmodel\\common\\custo"...
0x180074319  mov     edx, 92h; void *
0x18007431e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180074323  mov     ebx, eax
0x180074325  lea     rcx, [rsp+628h+lpFileName]
0x18007432d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074332  nop
0x180074333  lea     rcx, [rsp+628h+var_388]
0x18007433b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180074340  nop
0x180074341  lea     rcx, [rsp+628h+var_538]
0x180074349  call    ??1?$_Optional_destruct_base@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::wstring,0>::~_Optional_destruct_base<std::wstring,0>(void)
0x18007434e  nop
0x18007434f  lea     rcx, [rsp+628h+var_510]; this
0x180074357  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18007435c  nop
0x18007435d  mov     rcx, r13; this
0x180074360  call    ?AutoHandleFreeFindFile@Common@@YAXPEAX@Z; Common::AutoHandleFreeFindFile(void *)
0x180074365  nop
0x180074366  lea     rcx, [rsp+628h+var_588]; this
0x18007436e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
  ... truncated ...
```
