# NgcUtils::Detail::CacheCleanupMultipleSidsForUser(void)

- ea: `0x180056438`
- end: `0x180057052`
- name: `?CacheCleanupMultipleSidsForUser@Detail@NgcUtils@@YAJXZ`
- size: `3098`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008c740`

## callees

- `0x180006b60`
- `0x18000782c`
- `0x180007964`
- `0x18000e960`
- `0x18000ff4c`
- `0x180010d1c`
- `0x1800129e0`
- `0x1800281e0`
- `0x1800288a0`
- `0x18002c850`
- `0x180048304`
- `0x180056438`
- `0x180057058`
- `0x18005cee0`
- `0x18005d2ec`
- `0x18008abb8`
- `0x18008abec`
- `0x18008ad0c`
- `0x18008adac`
- `0x18008aea8`
- `0x18008b148`
- `0x18008b1b4`
- `0x18008b404`
- `0x18008b5b0`
- `0x18008b5d8`
- `0x18008c4a4`
- `0x18008da40`
- `0x18008dc88`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180056bf6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180056d8d`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180056bf6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180056d8d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180056708`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180056708`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056697`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056697`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800567db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056809`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056900`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056938`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056ea5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800567db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056809`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056900`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056938`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180056ea5`

## string_xrefs

- `0x1800564a2`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056a6d`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056b36`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056c04`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056ccd`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056d9e`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056ed8`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180056f50`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NgcUtils::Detail::CacheCleanupMultipleSidsForUser(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  const unsigned __int16 *v5; // rdx
  int v6; // r15d
  int v7; // eax
  __int64 v8; // rax
  const WCHAR *v9; // r8
  int v10; // r12d
  int v11; // eax
  const WCHAR *v12; // r8
  int v13; // r14d
  int v14; // r13d
  const WCHAR *v15; // rdx
  unsigned int ValueW; // eax
  __int64 v17; // rsi
  __int64 v18; // rcx
  _QWORD **v19; // rdi
  const WCHAR *v20; // rsi
  _QWORD *v21; // rbx
  _QWORD *v22; // rcx
  __int64 v23; // rax
  const WCHAR *v24; // rcx
  const char *v25; // r9
  int v26; // ecx
  const char *v27; // r9
  LPCWSTR *v28; // r8
  PSID *p_Sid; // rcx
  _QWORD **v30; // rdi
  _QWORD *v31; // rbx
  _QWORD *v32; // rcx
  const WCHAR *v33; // rcx
  const char *v34; // r9
  const WCHAR *v35; // rcx
  int v36; // ecx
  const char *v37; // r9
  LPCWSTR *v38; // r8
  __int64 v39; // rbx
  _QWORD *v40; // rax
  int LastError; // esi
  _QWORD **v42; // rcx
  _QWORD *v43; // rdi
  _QWORD *v44; // rbx
  _QWORD **v45; // rcx
  _QWORD *v46; // rdi
  _QWORD *v47; // rbx
  _QWORD **v48; // rcx
  _QWORD *v49; // rdi
  _QWORD *v50; // rbx
  _QWORD **v51; // rcx
  _QWORD *v52; // rdi
  _QWORD *v53; // rbx
  _QWORD **v54; // rcx
  _QWORD *v55; // rdi
  _QWORD *v56; // rbx
  _QWORD **v57; // r14
  _QWORD *i; // rbx
  const WCHAR *v59; // rdi
  const WCHAR *v60; // rcx
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rcx
  const char *v64; // r9
  _QWORD **v65; // rdx
  _QWORD *v66; // rdi
  _QWORD *v67; // rbx
  _QWORD **v68; // rcx
  _QWORD *v69; // rdi
  _QWORD *v70; // rbx
  _QWORD **v72; // rcx
  _QWORD *v73; // rdi
  _QWORD *v74; // rbx
  unsigned __int16 **pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  _QWORD **v77; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v78; // [rsp+48h] [rbp-B8h]
  PSID v79; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  PSID v81; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v82[2]; // [rsp+68h] [rbp-98h] BYREF
  int pvData; // [rsp+78h] [rbp-88h] BYREF
  PSID v84; // [rsp+80h] [rbp-80h] BYREF
  PSID v85; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR v86; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp-68h] BYREF
  int v88; // [rsp+9Ch] [rbp-64h]
  FILETIME FileTime1; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD ***v90; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD *v91; // [rsp+B0h] [rbp-50h]
  _QWORD ***v92; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v93; // [rsp+C0h] [rbp-40h]
  HKEY hKey; // [rsp+C8h] [rbp-38h] BYREF
  int v95; // [rsp+D0h] [rbp-30h]
  char v96; // [rsp+E0h] [rbp-20h] BYREF
  FILETIME FileTime2; // [rsp+F8h] [rbp-8h] BYREF
  HKEY hkey; // [rsp+100h] [rbp+0h] BYREF
  int v99; // [rsp+108h] [rbp+8h]
  FILETIME v100; // [rsp+10Ch] [rbp+Ch]
  char v101; // [rsp+118h] [rbp+18h] BYREF
  HKEY v102; // [rsp+130h] [rbp+30h] BYREF
  int v103; // [rsp+138h] [rbp+38h]
  char v104; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v105[2]; // [rsp+160h] [rbp+60h] BYREF
  int v106; // [rsp+170h] [rbp+70h]
  _QWORD v107[2]; // [rsp+178h] [rbp+78h] BYREF
  int v108; // [rsp+188h] [rbp+88h]
  _QWORD v109[2]; // [rsp+190h] [rbp+90h] BYREF
  int v110; // [rsp+1A0h] [rbp+A0h]
  _BYTE v111[16]; // [rsp+1A8h] [rbp+A8h] BYREF
  LPCWSTR v112[3]; // [rsp+1B8h] [rbp+B8h] BYREF
  unsigned __int64 v113; // [rsp+1D0h] [rbp+D0h]
  LPCWSTR StringSid[3]; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int64 v115; // [rsp+1F0h] [rbp+F0h]
  LPCWSTR lpSubKey[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  LPCWSTR v117[4]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v118[16]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v119; // [rsp+248h] [rbp+148h]
  _BYTE v120[40]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v86 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v86,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&v86,
                                        pdwType);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v78 = 0;
    v3 = operator new(0x30u);
    *v3 = v3;
    v3[1] = v3;
    v77 = (_QWORD **)v3;
    v82[1] = 0;
    v4 = operator new(0x68u);
    *v4 = v4;
    v4[1] = v4;
    v4[2] = v4;
    *((_WORD *)v4 + 12) = 257;
    v82[0] = v4;
    NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey, HKEY_LOCAL_MACHINE, v86);
    v109[0] = hKey;
    v109[1] = &v96;
    v6 = 0;
    v110 = 0;
    v7 = v95;
    LODWORD(v79) = v95;
    while ( v6 != v7 )
    {
      NgcUtils::RegKeyIterator::Iterator::operator*(v109, StringSid);
      v8 = std::operator+<unsigned short>(v118, StringSid);
      std::operator+<unsigned short>(v117, v8);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v118);
      v9 = (const WCHAR *)v117;
      if ( v117[3] > (LPCWSTR)7 )
        v9 = v117[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v102, hKey, v9);
      v107[0] = v102;
      v107[1] = &v104;
      v10 = 0;
      v108 = 0;
      v11 = v103;
      v88 = v103;
LABEL_8:
      if ( v10 != v11 )
      {
        NgcUtils::RegKeyIterator::Iterator::operator*(v107, v112);
        v12 = (const WCHAR *)v112;
        if ( v113 > 7 )
          v12 = v112[0];
        NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, v102, v12);
        v105[0] = hkey;
        v105[1] = &v101;
        v13 = 0;
        v106 = 0;
        v14 = v99;
        while ( 1 )
        {
          if ( v13 == v14 )
            goto LABEL_48;
          NgcUtils::RegKeyIterator::Iterator::operator*(v105, lpSubKey);
          pvData = 0;
          pcbData = 4;
          v15 = (const WCHAR *)lpSubKey;
          if ( lpSubKey[3] > (LPCWSTR)7 )
            v15 = lpSubKey[0];
          ValueW = RegGetValueW(hkey, v15, L"UserEntered", 0x10u, 0, &pvData, &pcbData);
          if ( ValueW )
            break;
          if ( pvData )
          {
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
LABEL_48:
            NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
            v108 = ++v10;
            v11 = v88;
            goto LABEL_8;
          }
          FileTime1 = v100;
          std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
            v82,
            v118,
            v112);
          v17 = v119;
          if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Lower_bound_duplicate<std::wstring>(
                                   v18,
                                   v119,
                                   v112)
            || v17 == v82[0] )
          {
            v39 = std::make_pair<std::wstring &,_FILETIME &>(v120, StringSid, &FileTime1);
            v40 = (_QWORD *)std::map<std::wstring,std::pair<std::wstring,_FILETIME>>::_Try_emplace<std::wstring const &,>(
                              v82,
                              v111,
                              v112);
            std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(*v40 + 64LL, v39);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v120);
          }
          else
          {
            FileTime2 = *(FILETIME *)(v17 + 96);
            if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
            {
              if ( v78 == 0x555555555555555LL )
                std::_Xlength_error("list too long");
              v19 = v77;
              v20 = (const WCHAR *)(v17 + 64);
              v90 = &v77;
              v91 = 0;
              v21 = operator new(0x30u);
              v91 = v21;
              std::wstring::wstring(v21 + 2, v20);
              ++v78;
              v22 = v19[1];
              *v21 = v19;
              v21[1] = v22;
              v91 = 0;
              v19[1] = v21;
              *v22 = v21;
              std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&v90);
              v23 = std::make_pair<std::wstring &,_FILETIME &>(v118, StringSid, &FileTime1);
              std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(v20, v23);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v118);
              Sid = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &Sid,
                0);
              v24 = (const WCHAR *)StringSid;
              if ( v115 > 7 )
                v24 = StringSid[0];
              if ( !ConvertStringSidToSidW(v24, &Sid) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5DB,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v25);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
                v45 = v77;
                *v77[1] = 0;
                v46 = *v45;
                if ( *v45 )
                {
                  do
                  {
                    v47 = (_QWORD *)*v46;
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v46 + 2);
                    std::_Deallocate<16>(v46, 0x30u);
                    v46 = v47;
                  }
                  while ( v47 );
                }
                goto LABEL_84;
              }
              v84 = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v84,
                0);
              if ( *((_QWORD *)v20 + 3) > 7u )
                v20 = *(const WCHAR **)v20;
              if ( !ConvertStringSidToSidW(v20, &v84) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5E0,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v27);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
                v42 = v77;
                *v77[1] = 0;
                v43 = *v42;
                if ( *v42 )
                {
                  do
                  {
                    v44 = (_QWORD *)*v43;
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v43 + 2);
                    std::_Deallocate<16>(v43, 0x30u);
                    v43 = v44;
                  }
                  while ( v44 );
                }
                goto LABEL_84;
              }
              if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
              {
                v28 = v112;
                if ( v113 > 7 )
                  LODWORD(v28) = v112[0];
                McTemplateU0zkk_EventWriteTransfer(
                  v26,
                  (unsigned int)EVENT_HFB_USERNAMESIDCACHE_FOUND_STALESID,
                  (_DWORD)v28,
                  (_DWORD)Sid,
                  (__int64)v84);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
              p_Sid = &Sid;
            }
            else
            {
              if ( v78 == 0x555555555555555LL )
                std::_Xlength_error("list too long");
              v30 = v77;
              v92 = &v77;
              v93 = 0;
              v31 = operator new(0x30u);
              v93 = v31;
              std::wstring::wstring(v31 + 2, StringSid);
              ++v78;
              v32 = v30[1];
              *v31 = v30;
              v31[1] = v32;
              v93 = 0;
              v30[1] = v31;
              *v32 = v31;
              std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&v92);
              v81 = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v81,
                0);
              v33 = (const WCHAR *)(v17 + 64);
              if ( *(_QWORD *)(v17 + 88) > 7u )
                v33 = *(const WCHAR **)v33;
              if ( !ConvertStringSidToSidW(v33, &v81) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5EE,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v34);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
                v51 = v77;
                *v77[1] = 0;
                v52 = *v51;
                if ( *v51 )
                {
                  do
                  {
                    v53 = (_QWORD *)*v52;
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v52 + 2);
                    std::_Deallocate<16>(v52, 0x30u);
                    v52 = v53;
                  }
                  while ( v53 );
                }
                goto LABEL_84;
              }
              v85 = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &v85,
                0);
              v35 = (const WCHAR *)StringSid;
              if ( v115 > 7 )
                v35 = StringSid[0];
              if ( !ConvertStringSidToSidW(v35, &v85) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x5F3,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v37);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
                std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
                v48 = v77;
                *v77[1] = 0;
                v49 = *v48;
                if ( *v48 )
                {
                  do
                  {
                    v50 = (_QWORD *)*v49;
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v49 + 2);
                    std::_Deallocate<16>(v49, 0x30u);
                    v49 = v50;
                  }
                  while ( v50 );
                }
                goto LABEL_84;
              }
              if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
              {
                v38 = v112;
                if ( v113 > 7 )
                  LODWORD(v38) = v112[0];
                McTemplateU0zkk_EventWriteTransfer(
                  v36,
                  (unsigned int)EVENT_HFB_USERNAMESIDCACHE_FOUND_STALESID,
                  (_DWORD)v38,
                  (_DWORD)v81,
                  (__int64)v85);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
              p_Sid = &v81;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(p_Sid);
          }
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
          v106 = ++v13;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x5BB,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      (const char *)ValueW,
                      pdwTypea);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v112);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
        v54 = v77;
        *v77[1] = 0;
        v55 = *v54;
        if ( *v54 )
        {
          do
          {
            v56 = (_QWORD *)*v55;
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v55 + 2);
            std::_Deallocate<16>(v55, 0x30u);
            v55 = v56;
          }
          while ( v56 );
        }
LABEL_84:
        std::_Deallocate<16>(v77, 0x30u);
        v2 = LastError;
        goto LABEL_85;
      }
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v102);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v117);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      v110 = ++v6;
      v7 = (int)v79;
    }
    v57 = v77;
    for ( i = *v77; i != v57; i = (_QWORD *)*i )
    {
      v59 = (const WCHAR *)(i + 2);
      if ( i[5] <= 7u )
        v60 = (const WCHAR *)(i + 2);
      else
        v60 = *(const WCHAR **)v59;
      v61 = NgcUtils::Detail::CacheRemoveUser(v60, v5);
      LastError = v61;
      if ( v61 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x603,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
          (const char *)(unsigned int)v61,
          pdwTypea);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
        v68 = v77;
        *v77[1] = 0;
        v69 = *v68;
        if ( *v68 )
        {
          do
          {
            v70 = (_QWORD *)*v69;
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v69 + 2);
            std::_Deallocate<16>(v69, 0x30u);
            v69 = v70;
          }
          while ( v70 );
        }
        goto LABEL_84;
      }
      v79 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v79,
        0);
      if ( i[5] > 7u )
        v59 = *(const WCHAR **)v59;
      if ( !ConvertStringSidToSidW(v59, &v79) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x609,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      v64);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v79);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
        std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
        v65 = v77;
        *v77[1] = 0;
        v66 = *v65;
        if ( *v65 )
        {
          do
          {
            v67 = (_QWORD *)*v66;
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v66 + 2);
            std::_Deallocate<16>(v66, 0x30u);
            v66 = v67;
          }
          while ( v67 );
        }
        goto LABEL_84;
      }
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
        McTemplateU0k_EventWriteTransfer(v63, v62, v79);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v79);
    }
    NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
    std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>(v82);
    v72 = v77;
    *v77[1] = 0;
    v73 = *v72;
    if ( *v72 )
    {
      do
      {
        v74 = (_QWORD *)*v73;
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v73 + 2);
        std::_Deallocate<16>(v73, 0x30u);
        v73 = v74;
      }
      while ( v74 );
    }
    std::_Deallocate<16>(v77, 0x30u);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v86);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      pdwTypea);
LABEL_85:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v86);
    return v2;
  }
}

```

## disassembly

```asm
0x180056438  push    rbp
0x18005643a  push    rbx
0x18005643b  push    rsi
0x18005643c  push    rdi
0x18005643d  push    r12
0x18005643f  push    r13
0x180056441  push    r14
0x180056443  push    r15
0x180056445  lea     rbp, [rsp-198h]
0x18005644d  sub     rsp, 298h
0x180056454  mov     rax, cs:__security_cookie
0x18005645b  xor     rax, rsp
0x18005645e  mov     [rbp+1D0h+var_48], rax
0x180056465  mov     [rbp+1D0h+var_240], 0
0x18005646d  xor     edx, edx
0x18005646f  lea     rcx, [rbp+1D0h+var_240]
0x180056473  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180056478  lea     r9, [rbp+1D0h+var_240]; unsigned __int16 *
0x18005647c  xor     r8d, r8d; unsigned __int16 *
0x18005647f  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180056486  lea     rcx, aNgccredprov; "NgcCredprov"
0x18005648d  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180056492  mov     ebx, eax
0x180056494  test    eax, eax
0x180056496  jns     short loc_1800564B8
0x180056498  mov     rcx, [rbp+1D8h]; this
0x18005649f  mov     r9d, eax; char *
0x1800564a2  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800564a9  mov     edx, 5A3h; void *
0x1800564ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800564b3  jmp     loc_180056FBD
0x1800564b8  xor     ebx, ebx
0x1800564ba  mov     [rsp+2D0h+var_290], rbx
0x1800564bf  mov     [rsp+2D0h+var_288], rbx
0x1800564c4  lea     ecx, [rbx+30h]; Size
0x1800564c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800564cc  mov     [rax], rax
0x1800564cf  mov     [rax+8], rax
0x1800564d3  mov     [rsp+2D0h+var_290], rax
0x1800564d8  mov     [rsp+2D0h+var_268], rbx
0x1800564dd  mov     [rsp+2D0h+var_260], rbx
0x1800564e2  lea     ecx, [rbx+68h]; Size
0x1800564e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800564ea  mov     [rax], rax
0x1800564ed  mov     [rax+8], rax
0x1800564f1  mov     [rax+10h], rax
0x1800564f5  mov     word ptr [rax+18h], 101h
0x1800564fb  mov     [rsp+2D0h+var_268], rax
0x180056500  mov     r8, [rbp+1D0h+var_240]; lpSubKey
0x180056504  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18005650b  lea     rcx, [rbp+1D0h+hKey]; this
0x18005650f  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180056514  nop
0x180056515  mov     rax, [rbp+1D0h+hKey]
0x180056519  mov     [rbp+1D0h+var_140], rax
0x180056520  lea     rax, [rbp+1D0h+var_1F0]
0x180056524  mov     [rbp+1D0h+var_138], rax
0x18005652b  mov     r15d, ebx
0x18005652e  mov     [rbp+1D0h+var_130], ebx
0x180056534  mov     eax, [rbp+1D0h+var_200]
0x180056537  mov     dword ptr [rsp+2D0h+var_280], eax
0x18005653b  mov     rdi, 555555555555555h
0x180056545  cmp     r15d, eax
0x180056548  jz      loc_180056E4C
0x18005654e  lea     rdx, [rbp+1D0h+StringSid]
0x180056555  lea     rcx, [rbp+1D0h+var_140]
0x18005655c  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180056561  nop
0x180056562  lea     rdx, [rbp+1D0h+StringSid]
0x180056569  lea     rcx, [rbp+1D0h+var_98]
0x180056570  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180056575  nop
0x180056576  mov     rdx, rax
0x180056579  lea     rcx, [rbp+1D0h+var_B8]
0x180056580  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180056585  nop
0x180056586  lea     rcx, [rbp+1D0h+var_98]
0x18005658d  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180056592  lea     r8, [rbp+1D0h+var_B8]
0x180056599  cmp     [rbp+1D0h+var_A0], 7
0x1800565a1  cmova   r8, [rbp+1D0h+var_B8]; lpSubKey
0x1800565a9  mov     rdx, [rbp+1D0h+hKey]; hKey
0x1800565ad  lea     rcx, [rbp+1D0h+var_1A0]; this
0x1800565b1  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x1800565b6  nop
0x1800565b7  mov     rax, [rbp+1D0h+var_1A0]
0x1800565bb  mov     [rbp+1D0h+var_158], rax
0x1800565bf  lea     rax, [rbp+1D0h+var_188]
0x1800565c3  mov     [rbp+1D0h+var_150], rax
0x1800565ca  mov     r12d, ebx
0x1800565cd  mov     [rbp+1D0h+var_148], ebx
0x1800565d3  mov     eax, [rbp+1D0h+var_198]
0x1800565d6  mov     [rbp+1D0h+var_234], eax
0x1800565d9  cmp     r12d, eax
0x1800565dc  jz      loc_180056A30
0x1800565e2  lea     rdx, [rbp+1D0h+var_118]
0x1800565e9  lea     rcx, [rbp+1D0h+var_158]
0x1800565ed  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x1800565f2  nop
0x1800565f3  lea     r8, [rbp+1D0h+var_118]
0x1800565fa  cmp     [rbp+1D0h+var_100], 7
0x180056602  cmova   r8, [rbp+1D0h+var_118]; lpSubKey
0x18005660a  mov     rdx, [rbp+1D0h+var_1A0]; hKey
0x18005660e  lea     rcx, [rbp+1D0h+hkey]; this
0x180056612  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180056617  nop
0x180056618  mov     rax, [rbp+1D0h+hkey]
0x18005661c  mov     [rbp+1D0h+var_170], rax
0x180056620  lea     rax, [rbp+1D0h+var_1B8]
0x180056624  mov     [rbp+1D0h+var_168], rax
0x180056628  mov     r14d, ebx
0x18005662b  mov     [rbp+1D0h+var_160], ebx
0x18005662e  mov     r13d, [rbp+1D0h+var_1C8]
0x180056632  cmp     r14d, r13d
0x180056635  jz      loc_180056A08
0x18005663b  lea     rdx, [rbp+1D0h+lpSubKey]
0x180056642  lea     rcx, [rbp+1D0h+var_170]
0x180056646  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18005664b  nop
0x18005664c  mov     [rsp+2D0h+var_258], ebx
0x180056650  mov     [rbp+1D0h+var_238], 4
0x180056657  lea     rdx, [rbp+1D0h+lpSubKey]
0x18005665e  cmp     [rbp+1D0h+var_C0], 7
0x180056666  cmova   rdx, [rbp+1D0h+lpSubKey]; lpSubKey
0x18005666e  lea     rax, [rbp+1D0h+var_238]
0x180056672  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180056677  lea     rax, [rsp+2D0h+var_258]
0x18005667c  mov     [rsp+2D0h+pvData], rax; pvData
0x180056681  mov     [rsp+2D0h+pdwType], rbx; unsigned int
0x180056686  mov     r9d, 10h; dwFlags
0x18005668c  lea     r8, aUserentered; "UserEntered"
0x180056693  mov     rcx, [rbp+1D0h+hkey]; hkey
0x180056697  call    cs:__imp_RegGetValueW
0x18005669d  test    eax, eax
0x18005669f  jnz     loc_180056D94
0x1800566a5  cmp     [rsp+2D0h+var_258], ebx
0x1800566a9  jnz     loc_1800569FB
0x1800566af  mov     rax, [rbp+1D0h+var_1C4]
0x1800566b3  mov     qword ptr [rbp+1D0h+FileTime1.dwLowDateTime], rax
0x1800566b7  lea     r8, [rbp+1D0h+var_118]
0x1800566be  lea     rdx, [rbp+1D0h+var_98]
0x1800566c5  lea     rcx, [rsp+2D0h+var_268]
0x1800566ca  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800566cf  lea     r8, [rbp+1D0h+var_118]
0x1800566d6  mov     rsi, [rbp+1D0h+var_88]
0x1800566dd  mov     rdx, rsi
0x1800566e0  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::pair<std::wstring,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>,void *> * const,std::wstring const &)
0x1800566e5  test    al, al
0x1800566e7  jz      loc_180056993
0x1800566ed  cmp     rsi, [rsp+2D0h+var_268]
0x1800566f2  jz      loc_180056993
0x1800566f8  mov     rax, [rsi+60h]
0x1800566fc  mov     qword ptr [rbp+1D0h+FileTime2.dwLowDateTime], rax
0x180056700  lea     rdx, [rbp+1D0h+FileTime2]; lpFileTime2
0x180056704  lea     rcx, [rbp+1D0h+FileTime1]; lpFileTime1
0x180056708  call    cs:__imp_CompareFileTime
0x18005670e  cmp     eax, 1
0x180056711  jnz     loc_180056873
0x180056717  cmp     [rsp+2D0h+var_288], rdi
0x18005671c  jz      loc_180056BEF
0x180056722  mov     rdi, [rsp+2D0h+var_290]
0x180056727  add     rsi, 40h ; '@'
0x18005672b  lea     rax, [rsp+2D0h+var_290]
0x180056730  mov     [rbp+1D0h+var_228], rax
0x180056734  mov     [rbp+1D0h+var_220], rbx
0x180056738  mov     ecx, 30h ; '0'; Size
0x18005673d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056742  mov     rbx, rax
0x180056745  mov     [rbp+1D0h+var_220], rax
0x180056749  lea     rcx, [rax+10h]
0x18005674d  mov     rdx, rsi
0x180056750  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180056755  nop
0x180056756  inc     [rsp+2D0h+var_288]
0x18005675b  mov     rcx, [rdi+8]
0x18005675f  mov     [rbx], rdi
0x180056762  mov     [rbx+8], rcx
0x180056766  mov     [rbp+1D0h+var_220], 0
0x18005676e  mov     [rdi+8], rbx
0x180056772  mov     [rcx], rbx
0x180056775  lea     rcx, [rbp+1D0h+var_228]
0x180056779  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x18005677e  lea     r8, [rbp+1D0h+FileTime1]
0x180056782  lea     rdx, [rbp+1D0h+StringSid]
0x180056789  lea     rcx, [rbp+1D0h+var_98]
0x180056790  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_FILETIME@@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAU_FILETIME@@@Z; std::make_pair<std::wstring &,_FILETIME &>(std::wstring &,_FILETIME &)
0x180056795  mov     rdx, rax
0x180056798  mov     rcx, rsi
0x18005679b  call    ??$?4U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@$0A@@?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<std::wstring,_FILETIME>::operator=<std::pair<std::wstring,_FILETIME>,0>(std::pair<std::wstring,_FILETIME> &&)
0x1800567a0  lea     rcx, [rbp+1D0h+var_98]
0x1800567a7  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800567ac  xor     ebx, ebx
0x1800567ae  mov     [rsp+2D0h+Sid], rbx
0x1800567b3  xor     edx, edx
0x1800567b5  lea     rcx, [rsp+2D0h+Sid]
0x1800567ba  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800567bf  lea     rcx, [rbp+1D0h+StringSid]
0x1800567c6  cmp     [rbp+1D0h+var_E0], 7
0x1800567ce  cmova   rcx, [rbp+1D0h+StringSid]; StringSid
0x1800567d6  lea     rdx, [rsp+2D0h+Sid]; Sid
0x1800567db  call    cs:__imp_ConvertStringSidToSidW
0x1800567e1  test    eax, eax
0x1800567e3  jz      loc_180056B2F
0x1800567e9  mov     [rbp+1D0h+var_250], rbx
0x1800567ed  xor     edx, edx
0x1800567ef  lea     rcx, [rbp+1D0h+var_250]
0x1800567f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800567f8  cmp     qword ptr [rsi+18h], 7
0x1800567fd  jbe     short loc_180056802
0x1800567ff  mov     rsi, [rsi]
0x180056802  lea     rdx, [rbp+1D0h+var_250]; Sid
0x180056806  mov     rcx, rsi; StringSid
0x180056809  call    cs:__imp_ConvertStringSidToSidW
0x18005680f  test    eax, eax
0x180056811  jz      loc_180056A66
0x180056817  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18005681e  jz      short loc_180056851
0x180056820  mov     rax, [rbp+1D0h+var_250]
0x180056824  lea     r8, [rbp+1D0h+var_118]
0x18005682b  cmp     [rbp+1D0h+var_100], 7
0x180056833  cmova   r8, [rbp+1D0h+var_118]
0x18005683b  mov     [rsp+2D0h+pdwType], rax
0x180056840  mov     r9, [rsp+2D0h+Sid]
0x180056845  lea     rdx, EVENT_HFB_USERNAMESIDCACHE_FOUND_STALESID
0x18005684c  call    McTemplateU0zkk_EventWriteTransfer
0x180056851  lea     rcx, [rbp+1D0h+var_250]; void *
0x180056855  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005685a  lea     rcx, [rsp+2D0h+Sid]; void *
0x18005685f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180056864  mov     rdi, 555555555555555h
0x18005686e  jmp     loc_1800569E3
0x180056873  cmp     [rsp+2D0h+var_288], rdi
0x180056878  jz      loc_180056D86
0x18005687e  mov     rdi, [rsp+2D0h+var_290]
0x180056883  lea     rax, [rsp+2D0h+var_290]
0x180056888  mov     [rbp+1D0h+var_218], rax
0x18005688c  mov     [rbp+1D0h+var_210], rbx
0x180056890  mov     ecx, 30h ; '0'; Size
0x180056895  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005689a  mov     rbx, rax
0x18005689d  mov     [rbp+1D0h+var_210], rax
0x1800568a1  lea     rcx, [rax+10h]
0x1800568a5  lea     rdx, [rbp+1D0h+StringSid]
0x1800568ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800568b1  nop
0x1800568b2  inc     [rsp+2D0h+var_288]
0x1800568b7  mov     rcx, [rdi+8]
0x1800568bb  mov     [rbx], rdi
0x1800568be  mov     [rbx+8], rcx
0x1800568c2  mov     [rbp+1D0h+var_210], 0
0x1800568ca  mov     [rdi+8], rbx
0x1800568ce  mov     [rcx], rbx
0x1800568d1  lea     rcx, [rbp+1D0h+var_218]
0x1800568d5  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x1800568da  xor     ebx, ebx
0x1800568dc  mov     [rsp+2D0h+var_270], rbx
0x1800568e1  xor     edx, edx
0x1800568e3  lea     rcx, [rsp+2D0h+var_270]
0x1800568e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800568ed  lea     rcx, [rsi+40h]
0x1800568f1  cmp     qword ptr [rcx+18h], 7
0x1800568f6  jbe     short loc_1800568FB
0x1800568f8  mov     rcx, [rcx]; StringSid
0x1800568fb  lea     rdx, [rsp+2D0h+var_270]; Sid
0x180056900  call    cs:__imp_ConvertStringSidToSidW
0x180056906  test    eax, eax
0x180056908  jz      loc_180056CC6
0x18005690e  mov     [rbp+1D0h+var_248], rbx
0x180056912  xor     edx, edx
0x180056914  lea     rcx, [rbp+1D0h+var_248]
0x180056918  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18005691d  lea     rcx, [rbp+1D0h+StringSid]
0x180056924  cmp     [rbp+1D0h+var_E0], 7
0x18005692c  cmova   rcx, [rbp+1D0h+StringSid]; StringSid
0x180056934  lea     rdx, [rbp+1D0h+var_248]; Sid
0x180056938  call    cs:__imp_ConvertStringSidToSidW
0x18005693e  test    eax, eax
0x180056940  jz      loc_180056BFD
0x180056946  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18005694d  jz      short loc_180056980
0x18005694f  mov     rax, [rbp+1D0h+var_248]
0x180056953  lea     r8, [rbp+1D0h+var_118]
0x18005695a  cmp     [rbp+1D0h+var_100], 7
0x180056962  cmova   r8, [rbp+1D0h+var_118]
0x18005696a  mov     [rsp+2D0h+pdwType], rax
0x18005696f  mov     r9, [rsp+2D0h+var_270]
0x180056974  lea     rdx, EVENT_HFB_USERNAMESIDCACHE_FOUND_STALESID
0x18005697b  call    McTemplateU0zkk_EventWriteTransfer
0x180056980  lea     rcx, [rbp+1D0h+var_248]; void *
0x180056984  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180056989  lea     rcx, [rsp+2D0h+var_270]
0x18005698e  jmp     loc_18005685F
0x180056993  lea     r8, [rbp+1D0h+FileTime1]
0x180056997  lea     rdx, [rbp+1D0h+StringSid]
0x18005699e  lea     rcx, [rbp+1D0h+var_70]
0x1800569a5  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_FILETIME@@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAU_FILETIME@@@Z; std::make_pair<std::wstring &,_FILETIME &>(std::wstring &,_FILETIME &)
0x1800569aa  mov     rbx, rax
0x1800569ad  lea     r8, [rbp+1D0h+var_118]
0x1800569b4  lea     rdx, [rbp+1D0h+var_128]
0x1800569bb  lea     rcx, [rsp+2D0h+var_268]
  ... truncated ...
```
