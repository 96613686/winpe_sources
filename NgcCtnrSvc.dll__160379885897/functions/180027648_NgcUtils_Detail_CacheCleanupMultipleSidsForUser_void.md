# NgcUtils::Detail::CacheCleanupMultipleSidsForUser(void)

- ea: `0x180027648`
- end: `0x18002819e`
- name: `?CacheCleanupMultipleSidsForUser@Detail@NgcUtils@@YAJXZ`
- size: `2902`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005c028`

## callees

- `0x1800066d0`
- `0x18000a8e0`
- `0x180018a9c`
- `0x1800193b0`
- `0x18001a77c`
- `0x180022e68`
- `0x180023278`
- `0x1800232a0`
- `0x180024dfc`
- `0x1800264b8`
- `0x180027648`
- `0x1800281a4`
- `0x18002820c`
- `0x18002856c`
- `0x180028598`
- `0x18002adf4`
- `0x18002c640`
- `0x180034870`
- `0x18005807c`
- `0x18005b6fc`
- `0x18005b730`
- `0x18005b874`
- `0x18005b964`
- `0x18005ba5c`
- `0x18005bbd4`
- `0x18005bbfc`
- `0x18005bd7c`
- `0x18005c3bc`
- `0x18005c5dc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027943`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027943`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800279c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800279fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027a83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027ac2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027fe8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800279c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800279fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027a83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027ac2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027fe8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027875`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027875`

## string_xrefs

- `0x1800276b1`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027ba2`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027c73`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027d3b`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027e0c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027ed7`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18002802b`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800280aa`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcUtils::Detail::CacheCleanupMultipleSidsForUser(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  const unsigned __int16 *v3; // rdx
  int v4; // esi
  int v5; // r13d
  __int64 v6; // rax
  const unsigned __int16 *v7; // r8
  int v8; // r15d
  int v9; // eax
  const unsigned __int16 *v10; // r8
  int v11; // r14d
  int v12; // r12d
  const WCHAR *v13; // rdx
  unsigned int ValueW; // eax
  __int64 v15; // rcx
  char v16; // al
  __int64 v17; // rdi
  __int64 v18; // rbx
  _QWORD *v19; // rax
  const WCHAR *v20; // rbx
  __int64 v21; // rax
  PSID *v22; // rax
  const WCHAR *v23; // rcx
  const char *v24; // r9
  PSID *v25; // rax
  int v26; // edx
  int v27; // ecx
  const char *v28; // r9
  unsigned __int16 **v29; // r8
  __int64 *v30; // rcx
  PSID *v31; // rax
  const char *v32; // r9
  PSID *v33; // rax
  const WCHAR *v34; // rcx
  int v35; // edx
  int v36; // ecx
  const char *v37; // r9
  unsigned __int16 **v38; // r8
  int LastError; // r14d
  _QWORD **v40; // rcx
  _QWORD *v41; // rsi
  _QWORD *v42; // rbx
  _QWORD **v43; // rcx
  _QWORD *v44; // rsi
  _QWORD *v45; // rbx
  _QWORD **v46; // rcx
  _QWORD *v47; // rsi
  _QWORD *v48; // rbx
  _QWORD **v49; // rcx
  _QWORD *v50; // rsi
  _QWORD *v51; // rbx
  _QWORD **v52; // rcx
  _QWORD *v53; // rsi
  _QWORD *v54; // rbx
  _QWORD *v55; // rdi
  _QWORD *i; // rbx
  const WCHAR *v57; // rsi
  const WCHAR *v58; // rcx
  int v59; // eax
  PSID *v60; // rax
  __int64 v61; // rcx
  const char *v62; // r9
  _QWORD **v63; // rdx
  _QWORD *v64; // rsi
  _QWORD *v65; // rbx
  _QWORD **v66; // rcx
  _QWORD *v67; // rsi
  _QWORD *v68; // rbx
  _QWORD **v69; // rcx
  _QWORD *v70; // rsi
  _QWORD *v71; // rbx
  unsigned __int16 **pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  __int128 v75; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v76; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v77; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+68h] [rbp-98h] BYREF
  __int64 v79; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  __int64 v81; // [rsp+80h] [rbp-80h] BYREF
  __int64 v82; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v83; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime1; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v86; // [rsp+A8h] [rbp-58h] BYREF
  int v87; // [rsp+B0h] [rbp-50h]
  char v88; // [rsp+C0h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hkey; // [rsp+E0h] [rbp-20h] BYREF
  int v91; // [rsp+E8h] [rbp-18h]
  FILETIME v92; // [rsp+ECh] [rbp-14h]
  char v93; // [rsp+F8h] [rbp-8h] BYREF
  HKEY v94; // [rsp+110h] [rbp+10h] BYREF
  int v95; // [rsp+118h] [rbp+18h]
  char v96; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v97[2]; // [rsp+140h] [rbp+40h] BYREF
  int v98; // [rsp+150h] [rbp+50h]
  _QWORD v99[2]; // [rsp+158h] [rbp+58h] BYREF
  int v100; // [rsp+168h] [rbp+68h]
  _QWORD v101[2]; // [rsp+170h] [rbp+70h] BYREF
  int v102; // [rsp+180h] [rbp+80h]
  _BYTE v103[16]; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int16 *v104[3]; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int64 v105; // [rsp+1B0h] [rbp+B0h]
  LPCWSTR StringSid[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned __int64 v107; // [rsp+1D0h] [rbp+D0h]
  LPCWSTR lpSubKey[4]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int16 *v109[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v110[16]; // [rsp+218h] [rbp+118h] BYREF
  __int64 v111; // [rsp+228h] [rbp+128h]
  _BYTE v112[40]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v83 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v83,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&v83,
                                        pdwType);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v75 = 0;
    std::list<std::wstring>::_Alloc_sentinel_and_proxy(&v75);
    v77 = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Alloc_sentinel_and_proxy(&v77);
    NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v86, HKEY_LOCAL_MACHINE, v83);
    v101[0] = v86;
    v101[1] = &v88;
    v4 = 0;
    v102 = 0;
    v5 = v87;
    while ( v4 != v5 )
    {
      NgcUtils::RegKeyIterator::Iterator::operator*(v101, StringSid);
      v6 = std::operator+<unsigned short>(v110, StringSid, L"\\");
      std::operator+<unsigned short>(v109, v6);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v110);
      v7 = (const unsigned __int16 *)v109;
      if ( v109[3] > (unsigned __int16 *)7 )
        v7 = v109[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v94, v86, v7);
      v99[0] = v94;
      v99[1] = &v96;
      v8 = 0;
      v100 = 0;
      v9 = v95;
      LODWORD(v76) = v95;
LABEL_8:
      if ( v8 != v9 )
      {
        NgcUtils::RegKeyIterator::Iterator::operator*(v99, v104);
        v10 = (const unsigned __int16 *)v104;
        if ( v105 > 7 )
          v10 = v104[0];
        NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, v94, v10);
        v97[0] = hkey;
        v97[1] = &v93;
        v11 = 0;
        v98 = 0;
        v12 = v91;
        while ( 1 )
        {
          if ( v11 == v12 )
            goto LABEL_47;
          NgcUtils::RegKeyIterator::Iterator::operator*(v97, lpSubKey);
          pvData = 0;
          pcbData = 4;
          v13 = (const WCHAR *)lpSubKey;
          if ( lpSubKey[3] > (LPCWSTR)7 )
            v13 = lpSubKey[0];
          ValueW = RegGetValueW(hkey, v13, L"UserEntered", 0x10u, 0, &pvData, &pcbData);
          if ( ValueW )
            break;
          if ( pvData )
          {
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
LABEL_47:
            NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
            v100 = ++v8;
            v9 = v76;
            goto LABEL_8;
          }
          FileTime1 = v92;
          std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
            &v77,
            v110,
            v104);
          v16 = std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                  v15,
                  v111,
                  v104);
          v17 = v77;
          if ( v16 )
            v17 = v111;
          if ( v17 == (_QWORD)v77 )
          {
            v18 = std::make_pair<std::wstring &,_FILETIME &>(v112, StringSid, &FileTime1);
            v19 = (_QWORD *)std::map<std::wstring,std::pair<std::wstring,_FILETIME>>::_Try_emplace<std::wstring const &,>(
                              &v77,
                              v103,
                              v104);
            std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(*v19 + 64LL, v18);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
          }
          else
          {
            FileTime2 = *(FILETIME *)(v17 + 96);
            v20 = (const WCHAR *)(v17 + 64);
            if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
            {
              std::list<std::wstring>::_Emplace<std::wstring const &>(&v75, v75, v17 + 64);
              v21 = std::make_pair<std::wstring &,_FILETIME &>(v110, StringSid, &FileTime1);
              std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(v17 + 64, v21);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v110);
              v79 = 0;
              v22 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v79);
              v23 = (const WCHAR *)StringSid;
              if ( v107 > 7 )
                v23 = StringSid[0];
              if ( !ConvertStringSidToSidW(v23, v22) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5DB,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v24);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v79);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
                v43 = (_QWORD **)v75;
                **(_QWORD **)(v75 + 8) = 0;
                v44 = *v43;
                if ( *v43 )
                {
                  do
                  {
                    v45 = (_QWORD *)*v44;
                    std::wstring::`scalar deleting destructor'(v44 + 2);
                    std::_Deallocate<16>(v44, 48);
                    v44 = v45;
                  }
                  while ( v45 );
                }
                goto LABEL_63;
              }
              v81 = 0;
              v25 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v81);
              if ( *(_QWORD *)(v17 + 88) > 7u )
                v20 = *(const WCHAR **)v20;
              if ( !ConvertStringSidToSidW(v20, v25) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5E0,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v28);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v79);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
                v40 = (_QWORD **)v75;
                **(_QWORD **)(v75 + 8) = 0;
                v41 = *v40;
                if ( *v40 )
                {
                  do
                  {
                    v42 = (_QWORD *)*v41;
                    std::wstring::`scalar deleting destructor'(v41 + 2);
                    std::_Deallocate<16>(v41, 48);
                    v41 = v42;
                  }
                  while ( v42 );
                }
                goto LABEL_63;
              }
              if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
              {
                v29 = v104;
                if ( v105 > 7 )
                  LODWORD(v29) = v104[0];
                McTemplateU0zkk_EventWriteTransfer(v27, v26, (_DWORD)v29, v79, v81);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81);
              v30 = &v79;
            }
            else
            {
              std::list<std::wstring>::_Emplace<std::wstring const &>(&v75, v75, StringSid);
              v80 = 0;
              v31 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v80);
              if ( *(_QWORD *)(v17 + 88) > 7u )
                v20 = *(const WCHAR **)v20;
              if ( !ConvertStringSidToSidW(v20, v31) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5EE,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v32);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v80);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
                v49 = (_QWORD **)v75;
                **(_QWORD **)(v75 + 8) = 0;
                v50 = *v49;
                if ( *v49 )
                {
                  do
                  {
                    v51 = (_QWORD *)*v50;
                    std::wstring::`scalar deleting destructor'(v50 + 2);
                    std::_Deallocate<16>(v50, 48);
                    v50 = v51;
                  }
                  while ( v51 );
                }
                goto LABEL_63;
              }
              v82 = 0;
              v33 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v82);
              v34 = (const WCHAR *)StringSid;
              if ( v107 > 7 )
                v34 = StringSid[0];
              if ( !ConvertStringSidToSidW(v34, v33) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5F3,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v37);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v82);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v80);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
                v46 = (_QWORD **)v75;
                **(_QWORD **)(v75 + 8) = 0;
                v47 = *v46;
                if ( *v46 )
                {
                  do
                  {
                    v48 = (_QWORD *)*v47;
                    std::wstring::`scalar deleting destructor'(v47 + 2);
                    std::_Deallocate<16>(v47, 48);
                    v47 = v48;
                  }
                  while ( v48 );
                }
                goto LABEL_63;
              }
              if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
              {
                v38 = v104;
                if ( v105 > 7 )
                  LODWORD(v38) = v104[0];
                McTemplateU0zkk_EventWriteTransfer(v36, v35, (_DWORD)v38, v80, v82);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v82);
              v30 = &v80;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v30);
          }
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
          v98 = ++v11;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x5BB,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      (const char *)ValueW,
                      pdwTypea);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v104);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
        v52 = (_QWORD **)v75;
        **(_QWORD **)(v75 + 8) = 0;
        v53 = *v52;
        if ( *v52 )
        {
          do
          {
            v54 = (_QWORD *)*v53;
            std::wstring::`scalar deleting destructor'(v53 + 2);
            std::_Deallocate<16>(v53, 48);
            v53 = v54;
          }
          while ( v54 );
        }
LABEL_63:
        std::_Deallocate<16>(v75, 48);
        v2 = LastError;
        goto LABEL_85;
      }
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v94);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v109);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      v102 = ++v4;
    }
    v55 = (_QWORD *)v75;
    for ( i = *(_QWORD **)v75; i != v55; i = (_QWORD *)*i )
    {
      v57 = (const WCHAR *)(i + 2);
      if ( i[5] <= 7u )
        v58 = (const WCHAR *)(i + 2);
      else
        v58 = *(const WCHAR **)v57;
      v59 = NgcUtils::Detail::CacheRemoveUser(v58, v3);
      LastError = v59;
      if ( v59 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x603,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
          (const char *)(unsigned int)v59,
          pdwTypea);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
        v66 = (_QWORD **)v75;
        **(_QWORD **)(v75 + 8) = 0;
        v67 = *v66;
        if ( *v66 )
        {
          do
          {
            v68 = (_QWORD *)*v67;
            std::wstring::`scalar deleting destructor'(v67 + 2);
            std::_Deallocate<16>(v67, 48);
            v67 = v68;
          }
          while ( v68 );
        }
        goto LABEL_63;
      }
      v76 = 0;
      v60 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v76);
      if ( i[5] > 7u )
        v57 = *(const WCHAR **)v57;
      if ( !ConvertStringSidToSidW(v57, v60) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x609,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      v62);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v76);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
        v63 = (_QWORD **)v75;
        **(_QWORD **)(v75 + 8) = 0;
        v64 = *v63;
        if ( *v63 )
        {
          do
          {
            v65 = (_QWORD *)*v64;
            std::wstring::`scalar deleting destructor'(v64 + 2);
            std::_Deallocate<16>(v64, 48);
            v64 = v65;
          }
          while ( v65 );
        }
        goto LABEL_63;
      }
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
        McTemplateU0k_EventWriteTransfer(v61, EVENT_HFB_USERNAMESIDCACHE_REMOVED_STALESID, v76);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v76);
    }
    NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v86);
    std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(&v77);
    v69 = (_QWORD **)v75;
    **(_QWORD **)(v75 + 8) = 0;
    v70 = *v69;
    if ( *v69 )
    {
      do
      {
        v71 = (_QWORD *)*v70;
        std::wstring::`scalar deleting destructor'(v70 + 2);
        std::_Deallocate<16>(v70, 48);
        v70 = v71;
      }
      while ( v71 );
    }
    std::_Deallocate<16>(v75, 48);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      pdwTypea);
  }
LABEL_85:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v83);
  return v2;
}

```

## disassembly

```asm
0x180027648  push    rbp
0x18002764a  push    rbx
0x18002764b  push    rsi
0x18002764c  push    rdi
0x18002764d  push    r12
0x18002764f  push    r13
0x180027651  push    r14
0x180027653  push    r15
0x180027655  lea     rbp, [rsp-178h]
0x18002765d  sub     rsp, 278h
0x180027664  mov     rax, cs:__security_cookie
0x18002766b  xor     rax, rsp
0x18002766e  mov     [rbp+1B0h+var_48], rax
0x180027675  xor     r12d, r12d
0x180027678  mov     [rbp+1B0h+var_220], r12
0x18002767c  xor     edx, edx
0x18002767e  lea     rcx, [rbp+1B0h+var_220]
0x180027682  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180027687  lea     r9, [rbp+1B0h+var_220]; unsigned __int16 *
0x18002768b  xor     r8d, r8d; unsigned __int16 *
0x18002768e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027695  lea     rcx, aNgccredprov; "NgcCredprov"
0x18002769c  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x1800276a1  mov     ebx, eax
0x1800276a3  test    eax, eax
0x1800276a5  jns     short loc_1800276C7
0x1800276a7  mov     rcx, [rbp+1B8h]; this
0x1800276ae  mov     r9d, eax; char *
0x1800276b1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800276b8  mov     edx, 5A3h; void *
0x1800276bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276c2  jmp     loc_18002816F
0x1800276c7  xorps   xmm0, xmm0
0x1800276ca  movdqu  [rsp+2B0h+var_270], xmm0
0x1800276d0  lea     rcx, [rsp+2B0h+var_270]
0x1800276d5  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x1800276da  nop
0x1800276db  xorps   xmm0, xmm0
0x1800276de  movdqu  [rsp+2B0h+var_258], xmm0
0x1800276e4  lea     rcx, [rsp+2B0h+var_258]
0x1800276e9  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800276ee  nop
0x1800276ef  mov     r8, [rbp+1B0h+var_220]; unsigned __int16 *
0x1800276f3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800276fa  lea     rcx, [rbp+1B0h+var_208]; this
0x1800276fe  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180027703  nop
0x180027704  mov     rax, [rbp+1B0h+var_208]
0x180027708  mov     [rbp+1B0h+var_140], rax
0x18002770c  lea     rax, [rbp+1B0h+var_1F0]
0x180027710  mov     [rbp+1B0h+var_138], rax
0x180027714  mov     esi, r12d
0x180027717  mov     [rbp+1B0h+var_130], r12d
0x18002771e  mov     r13d, [rbp+1B0h+var_200]
0x180027722  cmp     esi, r13d
0x180027725  jz      loc_180027F95
0x18002772b  lea     rdx, [rbp+1B0h+StringSid]
0x180027732  lea     rcx, [rbp+1B0h+var_140]
0x180027736  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18002773b  nop
0x18002773c  lea     r8, asc_18008F0A4; "\\"
0x180027743  lea     rdx, [rbp+1B0h+StringSid]
0x18002774a  lea     rcx, [rbp+1B0h+var_98]
0x180027751  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180027756  nop
0x180027757  mov     rdx, rax
0x18002775a  lea     rcx, [rbp+1B0h+var_B8]
0x180027761  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180027766  nop
0x180027767  lea     rcx, [rbp+1B0h+var_98]
0x18002776e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027773  lea     r8, [rbp+1B0h+var_B8]
0x18002777a  cmp     [rbp+1B0h+var_A0], 7
0x180027782  cmova   r8, [rbp+1B0h+var_B8]; unsigned __int16 *
0x18002778a  mov     rdx, [rbp+1B0h+var_208]; HKEY
0x18002778e  lea     rcx, [rbp+1B0h+var_1A0]; this
0x180027792  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180027797  nop
0x180027798  mov     rax, [rbp+1B0h+var_1A0]
0x18002779c  mov     [rbp+1B0h+var_158], rax
0x1800277a0  lea     rax, [rbp+1B0h+var_188]
0x1800277a4  mov     [rbp+1B0h+var_150], rax
0x1800277a8  mov     r15d, r12d
0x1800277ab  mov     [rbp+1B0h+var_148], r12d
0x1800277af  mov     eax, [rbp+1B0h+var_198]
0x1800277b2  mov     dword ptr [rsp+2B0h+var_260], eax
0x1800277b6  cmp     r15d, eax
0x1800277b9  jz      loc_180027B6B
0x1800277bf  lea     rdx, [rbp+1B0h+var_118]
0x1800277c6  lea     rcx, [rbp+1B0h+var_158]
0x1800277ca  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x1800277cf  nop
0x1800277d0  lea     r8, [rbp+1B0h+var_118]
0x1800277d7  cmp     [rbp+1B0h+var_100], 7
0x1800277df  cmova   r8, [rbp+1B0h+var_118]; unsigned __int16 *
0x1800277e7  mov     rdx, [rbp+1B0h+var_1A0]; HKEY
0x1800277eb  lea     rcx, [rbp+1B0h+hkey]; this
0x1800277ef  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x1800277f4  nop
0x1800277f5  mov     rax, [rbp+1B0h+hkey]
0x1800277f9  mov     [rbp+1B0h+var_170], rax
0x1800277fd  lea     rax, [rbp+1B0h+var_1B8]
0x180027801  mov     [rbp+1B0h+var_168], rax
0x180027805  mov     r14d, r12d
0x180027808  mov     [rbp+1B0h+var_160], r12d
0x18002780c  mov     r12d, [rbp+1B0h+var_1C8]
0x180027810  cmp     r14d, r12d
0x180027813  jz      loc_180027B42
0x180027819  lea     rdx, [rbp+1B0h+lpSubKey]
0x180027820  lea     rcx, [rbp+1B0h+var_170]
0x180027824  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180027829  nop
0x18002782a  xor     ebx, ebx
0x18002782c  mov     [rsp+2B0h+var_248], ebx
0x180027830  mov     [rbp+1B0h+var_218], 4
0x180027837  lea     rdx, [rbp+1B0h+lpSubKey]
0x18002783e  cmp     [rbp+1B0h+var_C0], 7
0x180027846  cmova   rdx, [rbp+1B0h+lpSubKey]; lpSubKey
0x18002784e  lea     rax, [rbp+1B0h+var_218]
0x180027852  mov     [rsp+2B0h+pcbData], rax; pcbData
0x180027857  lea     rax, [rsp+2B0h+var_248]
0x18002785c  mov     [rsp+2B0h+pvData], rax; pvData
0x180027861  mov     [rsp+2B0h+pdwType], rbx; unsigned int
0x180027866  lea     r9d, [rbx+10h]; dwFlags
0x18002786a  lea     r8, aUserentered; "UserEntered"
0x180027871  mov     rcx, [rbp+1B0h+hkey]; hkey
0x180027875  call    cs:__imp_RegGetValueW
0x18002787c  nop     dword ptr [rax+rax+00h]
0x180027881  test    eax, eax
0x180027883  jnz     loc_180027ECD
0x180027889  cmp     [rsp+2B0h+var_248], ebx
0x18002788d  jnz     loc_180027B35
0x180027893  mov     rax, [rbp+1B0h+var_1C4]
0x180027897  mov     qword ptr [rbp+1B0h+FileTime1.dwLowDateTime], rax
0x18002789b  lea     r8, [rbp+1B0h+var_118]
0x1800278a2  lea     rdx, [rbp+1B0h+var_98]
0x1800278a9  lea     rcx, [rsp+2B0h+var_258]
0x1800278ae  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800278b3  lea     r8, [rbp+1B0h+var_118]
0x1800278ba  mov     rdx, [rbp+1B0h+var_88]
0x1800278c1  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>,void *> * const,std::wstring const &)
0x1800278c6  mov     rdi, qword ptr [rsp+2B0h+var_258]
0x1800278cb  test    al, al
0x1800278cd  cmovnz  rdi, [rbp+1B0h+var_88]
0x1800278d5  cmp     rdi, qword ptr [rsp+2B0h+var_258]
0x1800278da  jnz     short loc_18002792F
0x1800278dc  lea     r8, [rbp+1B0h+FileTime1]
0x1800278e0  lea     rdx, [rbp+1B0h+StringSid]
0x1800278e7  lea     rcx, [rbp+1B0h+var_70]
0x1800278ee  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_FILETIME@@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAU_FILETIME@@@Z; std::make_pair<std::wstring &,_FILETIME &>(std::wstring &,_FILETIME &)
0x1800278f3  mov     rbx, rax
0x1800278f6  lea     r8, [rbp+1B0h+var_118]
0x1800278fd  lea     rdx, [rbp+1B0h+var_128]
0x180027904  lea     rcx, [rsp+2B0h+var_258]
0x180027909  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::pair<std::wstring,_FILETIME>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002790e  mov     rcx, [rax]
0x180027911  add     rcx, 40h ; '@'
0x180027915  mov     rdx, rbx
0x180027918  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(std::pair<std::wstring,_FILETIME> &&)
0x18002791d  nop
0x18002791e  lea     rcx, [rbp+1B0h+var_70]
0x180027925  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002792a  jmp     loc_180027B1D
0x18002792f  mov     rax, [rdi+60h]
0x180027933  mov     qword ptr [rbp+1B0h+FileTime2.dwLowDateTime], rax
0x180027937  lea     rbx, [rdi+40h]
0x18002793b  lea     rdx, [rbp+1B0h+FileTime2]; lpFileTime2
0x18002793f  lea     rcx, [rbp+1B0h+FileTime1]; lpFileTime1
0x180027943  call    cs:__imp_CompareFileTime
0x18002794a  nop     dword ptr [rax+rax+00h]
0x18002794f  mov     rdx, qword ptr [rsp+2B0h+var_270]
0x180027954  lea     rcx, [rsp+2B0h+var_270]
0x180027959  cmp     eax, 1
0x18002795c  jnz     loc_180027A54
0x180027962  mov     r8, rbx
0x180027965  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring const &>(std::_List_node<std::wstring,void *> * const,std::wstring const &)
0x18002796a  lea     r8, [rbp+1B0h+FileTime1]
0x18002796e  lea     rdx, [rbp+1B0h+StringSid]
0x180027975  lea     rcx, [rbp+1B0h+var_98]
0x18002797c  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_FILETIME@@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAU_FILETIME@@@Z; std::make_pair<std::wstring &,_FILETIME &>(std::wstring &,_FILETIME &)
0x180027981  mov     rdx, rax
0x180027984  mov     rcx, rbx
0x180027987  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(std::pair<std::wstring,_FILETIME> &&)
0x18002798c  lea     rcx, [rbp+1B0h+var_98]
0x180027993  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027998  mov     [rsp+2B0h+var_240], 0
0x1800279a1  lea     rcx, [rsp+2B0h+var_240]
0x1800279a6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1800279ab  lea     rcx, [rbp+1B0h+StringSid]
0x1800279b2  cmp     [rbp+1B0h+var_E0], 7
0x1800279ba  cmova   rcx, [rbp+1B0h+StringSid]; StringSid
0x1800279c2  mov     rdx, rax; Sid
0x1800279c5  call    cs:__imp_ConvertStringSidToSidW
0x1800279cc  nop     dword ptr [rax+rax+00h]
0x1800279d1  test    eax, eax
0x1800279d3  jz      loc_180027C6C
0x1800279d9  mov     [rbp+1B0h+var_230], 0
0x1800279e1  lea     rcx, [rbp+1B0h+var_230]
0x1800279e5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1800279ea  cmp     qword ptr [rdi+58h], 7
0x1800279ef  jbe     short loc_1800279F4
0x1800279f1  mov     rbx, [rbx]
0x1800279f4  mov     rdx, rax; Sid
0x1800279f7  mov     rcx, rbx; StringSid
0x1800279fa  call    cs:__imp_ConvertStringSidToSidW
0x180027a01  nop     dword ptr [rax+rax+00h]
0x180027a06  test    eax, eax
0x180027a08  jz      loc_180027B9B
0x180027a0e  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180027a15  jz      short loc_180027A41
0x180027a17  mov     rax, [rbp+1B0h+var_230]
0x180027a1b  lea     r8, [rbp+1B0h+var_118]
0x180027a22  cmp     [rbp+1B0h+var_100], 7
0x180027a2a  cmova   r8, [rbp+1B0h+var_118]
0x180027a32  mov     [rsp+2B0h+pdwType], rax
0x180027a37  mov     r9, [rsp+2B0h+var_240]
0x180027a3c  call    McTemplateU0zkk_EventWriteTransfer
0x180027a41  lea     rcx, [rbp+1B0h+var_230]
0x180027a45  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027a4a  lea     rcx, [rsp+2B0h+var_240]
0x180027a4f  jmp     loc_180027B17
0x180027a54  lea     r8, [rbp+1B0h+StringSid]
0x180027a5b  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::list<std::wstring>::_Emplace<std::wstring const &>(std::_List_node<std::wstring,void *> * const,std::wstring const &)
0x180027a60  mov     [rsp+2B0h+var_238], 0
0x180027a69  lea     rcx, [rsp+2B0h+var_238]
0x180027a6e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x180027a73  cmp     qword ptr [rbx+18h], 7
0x180027a78  jbe     short loc_180027A7D
0x180027a7a  mov     rbx, [rbx]
0x180027a7d  mov     rdx, rax; Sid
0x180027a80  mov     rcx, rbx; StringSid
0x180027a83  call    cs:__imp_ConvertStringSidToSidW
0x180027a8a  nop     dword ptr [rax+rax+00h]
0x180027a8f  test    eax, eax
0x180027a91  jz      loc_180027E05
0x180027a97  mov     [rbp+1B0h+var_228], 0
0x180027a9f  lea     rcx, [rbp+1B0h+var_228]
0x180027aa3  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x180027aa8  lea     rcx, [rbp+1B0h+StringSid]
0x180027aaf  cmp     [rbp+1B0h+var_E0], 7
0x180027ab7  cmova   rcx, [rbp+1B0h+StringSid]; StringSid
0x180027abf  mov     rdx, rax; Sid
0x180027ac2  call    cs:__imp_ConvertStringSidToSidW
0x180027ac9  nop     dword ptr [rax+rax+00h]
0x180027ace  test    eax, eax
0x180027ad0  jz      loc_180027D34
0x180027ad6  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x180027add  jz      short loc_180027B09
0x180027adf  mov     rax, [rbp+1B0h+var_228]
0x180027ae3  lea     r8, [rbp+1B0h+var_118]
0x180027aea  cmp     [rbp+1B0h+var_100], 7
0x180027af2  cmova   r8, [rbp+1B0h+var_118]
0x180027afa  mov     [rsp+2B0h+pdwType], rax
0x180027aff  mov     r9, [rsp+2B0h+var_238]
0x180027b04  call    McTemplateU0zkk_EventWriteTransfer
0x180027b09  lea     rcx, [rbp+1B0h+var_228]
0x180027b0d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027b12  lea     rcx, [rsp+2B0h+var_238]
0x180027b17  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027b1c  nop
0x180027b1d  lea     rcx, [rbp+1B0h+lpSubKey]
0x180027b24  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027b29  inc     r14d
0x180027b2c  mov     [rbp+1B0h+var_160], r14d
0x180027b30  jmp     loc_180027810
0x180027b35  lea     rcx, [rbp+1B0h+lpSubKey]
0x180027b3c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027b41  nop
0x180027b42  lea     rcx, [rbp+1B0h+hkey]; this
0x180027b46  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x180027b4b  nop
0x180027b4c  lea     rcx, [rbp+1B0h+var_118]
0x180027b53  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027b58  inc     r15d
0x180027b5b  mov     [rbp+1B0h+var_148], r15d
0x180027b5f  mov     eax, dword ptr [rsp+2B0h+var_260]
0x180027b63  xor     r12d, r12d
0x180027b66  jmp     loc_1800277B6
0x180027b6b  lea     rcx, [rbp+1B0h+var_1A0]; this
0x180027b6f  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x180027b74  nop
0x180027b75  lea     rcx, [rbp+1B0h+var_B8]
0x180027b7c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027b81  nop
0x180027b82  lea     rcx, [rbp+1B0h+StringSid]
0x180027b89  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027b8e  inc     esi
0x180027b90  mov     [rbp+1B0h+var_130], esi
0x180027b96  jmp     loc_180027722
0x180027b9b  mov     rcx, [rbp+1B8h]; this
0x180027ba2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180027ba9  mov     edx, 5E0h; void *
0x180027bae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027bb3  mov     r14d, eax
0x180027bb6  lea     rcx, [rbp+1B0h+var_230]
0x180027bba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027bbf  lea     rcx, [rsp+2B0h+var_240]
0x180027bc4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027bc9  nop
0x180027bca  lea     rcx, [rbp+1B0h+lpSubKey]
  ... truncated ...
```
