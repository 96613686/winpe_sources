# NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)

- ea: `0x18008b900`
- end: `0x18008c0cf`
- name: `?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ`
- size: `1999`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008c740`

## callees

- `0x180006b60`
- `0x18000782c`
- `0x180007964`
- `0x18000e960`
- `0x18000fbcc`
- `0x18000ff4c`
- `0x180010d1c`
- `0x1800281e0`
- `0x1800288a0`
- `0x18002c850`
- `0x180036f50`
- `0x180048304`
- `0x18005cee0`
- `0x18005d2ec`
- `0x18008abec`
- `0x18008b178`
- `0x18008b1b4`
- `0x18008b5b0`
- `0x18008b5d8`
- `0x18008b900`
- `0x18008c5ac`
- `0x18008d9b8`
- `0x18008dac8`
- `0x18008db88`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008bbd2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18008bbd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bb4b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bb4b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008bbbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008bf37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008bbbb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18008bf37`

## string_xrefs

- `0x18008b96c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008bd63`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008be22`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008bf7a`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008bfea`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall NgcUtils::Detail::CacheCleanupMultipleUsersForSid(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rax
  int v4; // ebx
  int v5; // r12d
  __int64 v6; // rax
  const WCHAR *v7; // r8
  unsigned int v8; // r15d
  int v9; // edi
  const WCHAR *v10; // r8
  int v11; // esi
  int v12; // r14d
  const WCHAR *v13; // rdx
  unsigned int ValueW; // eax
  const WCHAR *v15; // rcx
  const char *v16; // r9
  int v17; // ecx
  __int128 *v18; // rax
  LPCWSTR *v19; // r9
  __int64 v20; // rax
  LPCWSTR *v21; // rax
  __int128 *v22; // r9
  __int64 v23; // rax
  unsigned int LastError; // esi
  _QWORD **v25; // rcx
  _QWORD *v26; // rdi
  _QWORD *v27; // rbx
  _QWORD **v28; // rcx
  _QWORD *v29; // rdi
  _QWORD *v30; // rbx
  char *v31; // r15
  char *i; // rbx
  const WCHAR *v33; // rdi
  WCHAR *v34; // rcx
  _QWORD *v35; // rsi
  int v36; // eax
  int v37; // r14d
  __int64 v38; // rdx
  __int64 v39; // rcx
  const char *v40; // r9
  _QWORD **v41; // rdx
  _QWORD *v42; // rdi
  _QWORD *v43; // rbx
  _QWORD **v44; // rcx
  _QWORD *v45; // rdi
  _QWORD *v46; // rbx
  _QWORD **v47; // rcx
  _QWORD *v48; // rdi
  _QWORD *v49; // rbx
  unsigned __int16 **pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  void *v53[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  PSID v56; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR v57; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp-88h] BYREF
  FILETIME FileTime2; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v61[2]; // [rsp+88h] [rbp-78h] BYREF
  int v62; // [rsp+98h] [rbp-68h]
  _QWORD v63[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v64; // [rsp+B0h] [rbp-50h]
  HKEY v65; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v66; // [rsp+C0h] [rbp-40h]
  FILETIME v67; // [rsp+C4h] [rbp-3Ch]
  char v68; // [rsp+D0h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp-18h] BYREF
  int v70; // [rsp+F0h] [rbp-10h]
  char v71; // [rsp+100h] [rbp+0h] BYREF
  HKEY hkey; // [rsp+118h] [rbp+18h] BYREF
  int v73; // [rsp+120h] [rbp+20h]
  FILETIME v74; // [rsp+124h] [rbp+24h]
  char v75; // [rsp+130h] [rbp+30h] BYREF
  __int128 v76; // [rsp+148h] [rbp+48h] BYREF
  __int64 v77; // [rsp+158h] [rbp+58h]
  unsigned __int64 v78; // [rsp+160h] [rbp+60h]
  LPCWSTR v79[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v80; // [rsp+180h] [rbp+80h]
  LPCWSTR StringSid[4]; // [rsp+188h] [rbp+88h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  LPCWSTR v83[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v84[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  int v85; // [rsp+1F8h] [rbp+F8h]
  _BYTE v86[64]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v57 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v57,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&v57,
                                        pdwType);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v53[1] = 0;
    v3 = operator new(0x50u);
    *v3 = v3;
    v3[1] = v3;
    v53[0] = v3;
    NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey, HKEY_LOCAL_MACHINE, v57);
    v63[0] = hKey;
    v63[1] = &v71;
    v4 = 0;
    v5 = v70;
    while ( 1 )
    {
      v64 = v4;
      if ( v4 == v5 )
        break;
      NgcUtils::RegKeyIterator::Iterator::operator*(v63, StringSid);
      v6 = std::operator+<unsigned short>(v84, StringSid);
      std::operator+<unsigned short>(v83, v6);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v84);
      v7 = (const WCHAR *)v83;
      if ( v83[3] > (LPCWSTR)7 )
        v7 = v83[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v65, hKey, v7);
      v8 = v66;
      if ( v66 >= 2 )
      {
        v76 = 0;
        v77 = 0;
        v78 = 7;
        LOWORD(v76) = 0;
        FileTime2 = v67;
        v84[0] = v65;
        v84[1] = &v68;
        v9 = 0;
        v85 = 0;
LABEL_9:
        if ( v9 != v8 )
        {
          NgcUtils::RegKeyIterator::Iterator::operator*(v84, v79);
          v10 = (const WCHAR *)v79;
          if ( v80 > 7 )
            v10 = v79[0];
          NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, v65, v10);
          v61[0] = hkey;
          v61[1] = &v75;
          v11 = 0;
          v62 = 0;
          v12 = v73;
          while ( 1 )
          {
            if ( v11 == v12 )
              goto LABEL_41;
            NgcUtils::RegKeyIterator::Iterator::operator*(v61, lpSubKey);
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
LABEL_41:
              NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
              v85 = ++v9;
              goto LABEL_9;
            }
            FileTime1 = v74;
            if ( v77 )
            {
              Sid = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                &Sid,
                0);
              v15 = (const WCHAR *)StringSid;
              if ( StringSid[3] > (LPCWSTR)7 )
                v15 = StringSid[0];
              if ( !ConvertStringSidToSidW(v15, &Sid) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x64D,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v16);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v76);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v65);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v83);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
                v25 = (_QWORD **)v53[0];
                **((_QWORD **)v53[0] + 1) = 0;
                v26 = *v25;
                if ( *v25 )
                {
                  do
                  {
                    v27 = (_QWORD *)*v26;
                    std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v26 + 2);
                    std::_Deallocate<16>(v26, 0x50u);
                    v26 = v27;
                  }
                  while ( v27 );
                }
                goto LABEL_49;
              }
              if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v18 = &v76;
                  if ( v78 > 7 )
                    v18 = (__int128 *)v76;
                  v19 = v79;
                  if ( v80 > 7 )
                    LODWORD(v19) = v79[0];
                  McTemplateU0kzz_EventWriteTransfer(
                    v17,
                    (unsigned int)EVENT_HFB_USERNAMESIDCACHE_FOUND_STALEUSERNAME,
                    (_DWORD)Sid,
                    (_DWORD)v19,
                    (__int64)v18);
                }
                v20 = std::make_pair<std::wstring &,std::wstring &>(v86, StringSid, &v76);
                std::list<std::pair<std::wstring,std::wstring>>::push_back(v53, v20);
                std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v86);
                std::wstring::operator=(&v76, v79);
                FileTime2 = FileTime1;
              }
              else
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v21 = v79;
                  if ( v80 > 7 )
                    v21 = (LPCWSTR *)v79[0];
                  v22 = &v76;
                  if ( v78 > 7 )
                    LODWORD(v22) = v76;
                  McTemplateU0kzz_EventWriteTransfer(
                    v17,
                    (unsigned int)EVENT_HFB_USERNAMESIDCACHE_FOUND_STALEUSERNAME,
                    (_DWORD)Sid,
                    (_DWORD)v22,
                    (__int64)v21);
                }
                v23 = std::make_pair<std::wstring &,std::wstring &>(v86, StringSid, v79);
                std::list<std::pair<std::wstring,std::wstring>>::push_back(v53, v23);
                std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v86);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
            }
            else
            {
              std::wstring::operator=(&v76, v79);
              FileTime2 = FileTime1;
            }
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
            v62 = ++v11;
          }
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x636,
                        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                        (const char *)ValueW,
                        pdwTypea);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v76);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v65);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v83);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
          v28 = (_QWORD **)v53[0];
          **((_QWORD **)v53[0] + 1) = 0;
          v29 = *v28;
          if ( *v28 )
          {
            do
            {
              v30 = (_QWORD *)*v29;
              std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v29 + 2);
              std::_Deallocate<16>(v29, 0x50u);
              v29 = v30;
            }
            while ( v30 );
          }
LABEL_49:
          std::_Deallocate<16>(v53[0], 0x50u);
          v2 = LastError;
          goto LABEL_73;
        }
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v76);
      }
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v65);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v83);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      ++v4;
    }
    v31 = (char *)v53[0];
    for ( i = *(char **)v53[0]; i != v31; i = *(char **)i )
    {
      v33 = (const WCHAR *)(i + 16);
      if ( *((_QWORD *)i + 5) <= 7u )
        v34 = (WCHAR *)(i + 16);
      else
        v34 = *(WCHAR **)v33;
      v35 = i + 48;
      v36 = NgcUtils::Detail::CacheRemoveUser(v34, (LPCWSTR)i + 24);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x670,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
          (const char *)(unsigned int)v36,
          pdwTypea);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
        v44 = (_QWORD **)v53[0];
        **((_QWORD **)v53[0] + 1) = 0;
        v45 = *v44;
        if ( *v44 )
        {
          do
          {
            v46 = (_QWORD *)*v45;
            std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v45 + 2);
            std::_Deallocate<16>(v45, 0x50u);
            v45 = v46;
          }
          while ( v46 );
        }
        std::_Deallocate<16>(v53[0], 0x50u);
        v2 = v37;
        goto LABEL_73;
      }
      v56 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &v56,
        0);
      if ( *((_QWORD *)i + 5) > 7u )
        v33 = *(const WCHAR **)v33;
      if ( !ConvertStringSidToSidW(v33, &v56) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x675,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      v40);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v56);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
        v41 = (_QWORD **)v53[0];
        **((_QWORD **)v53[0] + 1) = 0;
        v42 = *v41;
        if ( *v41 )
        {
          do
          {
            v43 = (_QWORD *)*v42;
            std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v42 + 2);
            std::_Deallocate<16>(v42, 0x50u);
            v42 = v43;
          }
          while ( v43 );
        }
        goto LABEL_49;
      }
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      {
        if ( *((_QWORD *)i + 9) > 7u )
          v35 = (_QWORD *)*v35;
        McTemplateU0kz_EventWriteTransfer(v39, v38, v56, v35);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v56);
    }
    NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hKey);
    v47 = (_QWORD **)v53[0];
    **((_QWORD **)v53[0] + 1) = 0;
    v48 = *v47;
    if ( *v47 )
    {
      do
      {
        v49 = (_QWORD *)*v48;
        std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v48 + 2);
        std::_Deallocate<16>(v48, 0x50u);
        v48 = v49;
      }
      while ( v49 );
    }
    std::_Deallocate<16>(v53[0], 0x50u);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x618,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      pdwTypea);
  }
LABEL_73:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v57);
  return v2;
}

```

## disassembly

```asm
0x18008b900  push    rbp
0x18008b902  push    rbx
0x18008b903  push    rsi
0x18008b904  push    rdi
0x18008b905  push    r12
0x18008b907  push    r13
0x18008b909  push    r14
0x18008b90b  push    r15
0x18008b90d  lea     rbp, [rsp-168h]
0x18008b915  sub     rsp, 268h
0x18008b91c  mov     rax, cs:__security_cookie
0x18008b923  xor     rax, rsp
0x18008b926  mov     [rbp+1A0h+var_50], rax
0x18008b92d  xor     r13d, r13d
0x18008b930  mov     [rsp+2A0h+var_238], r13
0x18008b935  xor     edx, edx
0x18008b937  lea     rcx, [rsp+2A0h+var_238]
0x18008b93c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008b941  lea     r9, [rsp+2A0h+var_238]; unsigned __int16 *
0x18008b946  xor     r8d, r8d; unsigned __int16 *
0x18008b949  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008b950  lea     rcx, aNgccredprov; "NgcCredprov"
0x18008b957  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18008b95c  mov     ebx, eax
0x18008b95e  test    eax, eax
0x18008b960  jns     short loc_18008B982
0x18008b962  mov     rcx, [rbp+1A8h]; this
0x18008b969  mov     r9d, eax; char *
0x18008b96c  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008b973  mov     edx, 618h; void *
0x18008b978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b97d  jmp     loc_18008C0A0
0x18008b982  mov     [rsp+2A0h+var_260], r13
0x18008b987  mov     [rsp+2A0h+var_258], r13
0x18008b98c  mov     ecx, 50h ; 'P'; Size
0x18008b991  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008b996  mov     [rax], rax
0x18008b999  mov     [rax+8], rax
0x18008b99d  mov     [rsp+2A0h+var_260], rax
0x18008b9a2  mov     r8, [rsp+2A0h+var_238]; lpSubKey
0x18008b9a7  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18008b9ae  lea     rcx, [rbp+1A0h+hKey]; this
0x18008b9b2  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008b9b7  nop
0x18008b9b8  mov     rax, [rbp+1A0h+hKey]
0x18008b9bc  mov     [rbp+1A0h+var_200], rax
0x18008b9c0  lea     rax, [rbp+1A0h+var_1A0]
0x18008b9c4  mov     [rbp+1A0h+var_1F8], rax
0x18008b9c8  mov     ebx, r13d
0x18008b9cb  mov     r12d, [rbp+1A0h+var_1B0]
0x18008b9cf  mov     [rbp+1A0h+var_1F0], ebx
0x18008b9d2  cmp     ebx, r12d
0x18008b9d5  jz      loc_18008BED9
0x18008b9db  lea     rdx, [rbp+1A0h+StringSid]
0x18008b9e2  lea     rcx, [rbp+1A0h+var_200]
0x18008b9e6  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008b9eb  nop
0x18008b9ec  lea     rdx, [rbp+1A0h+StringSid]
0x18008b9f3  lea     rcx, [rbp+1A0h+var_B8]
0x18008b9fa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18008b9ff  nop
0x18008ba00  mov     rdx, rax
0x18008ba03  lea     rcx, [rbp+1A0h+var_D8]
0x18008ba0a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18008ba0f  nop
0x18008ba10  lea     rcx, [rbp+1A0h+var_B8]
0x18008ba17  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008ba1c  lea     r8, [rbp+1A0h+var_D8]
0x18008ba23  cmp     [rbp+1A0h+var_C0], 7
0x18008ba2b  cmova   r8, [rbp+1A0h+var_D8]; lpSubKey
0x18008ba33  mov     rdx, [rbp+1A0h+hKey]; hKey
0x18008ba37  lea     rcx, [rbp+1A0h+var_1E8]; this
0x18008ba3b  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008ba40  nop
0x18008ba41  mov     r15d, [rbp+1A0h+var_1E0]
0x18008ba45  cmp     r15d, 2
0x18008ba49  jb      loc_18008BD32
0x18008ba4f  xorps   xmm0, xmm0
0x18008ba52  movups  [rbp+1A0h+var_158], xmm0
0x18008ba56  mov     [rbp+1A0h+var_148], r13
0x18008ba5a  mov     [rbp+1A0h+var_140], 7
0x18008ba62  mov     word ptr [rbp+1A0h+var_158], r13w
0x18008ba67  mov     rax, [rbp+1A0h+var_1DC]
0x18008ba6b  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x18008ba6f  mov     rax, [rbp+1A0h+var_1E8]
0x18008ba73  mov     [rbp+1A0h+var_B8], rax
0x18008ba7a  lea     rax, [rbp+1A0h+var_1D0]
0x18008ba7e  mov     [rbp+1A0h+var_B0], rax
0x18008ba85  mov     edi, r13d
0x18008ba88  mov     [rbp+1A0h+var_A8], r13d
0x18008ba8f  cmp     edi, r15d
0x18008ba92  jz      loc_18008BD28
0x18008ba98  lea     rdx, [rbp+1A0h+var_138]
0x18008ba9c  lea     rcx, [rbp+1A0h+var_B8]
0x18008baa3  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008baa8  nop
0x18008baa9  lea     r8, [rbp+1A0h+var_138]
0x18008baad  cmp     [rbp+1A0h+var_120], 7
0x18008bab5  cmova   r8, [rbp+1A0h+var_138]; lpSubKey
0x18008baba  mov     rdx, [rbp+1A0h+var_1E8]; hKey
0x18008babe  lea     rcx, [rbp+1A0h+hkey]; this
0x18008bac2  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18008bac7  nop
0x18008bac8  mov     rax, [rbp+1A0h+hkey]
0x18008bacc  mov     [rbp+1A0h+var_218], rax
0x18008bad0  lea     rax, [rbp+1A0h+var_170]
0x18008bad4  mov     [rbp+1A0h+var_210], rax
0x18008bad8  mov     esi, r13d
0x18008badb  mov     [rbp+1A0h+var_208], r13d
0x18008badf  mov     r14d, [rbp+1A0h+var_180]
0x18008bae3  cmp     esi, r14d
0x18008bae6  jz      loc_18008BD08
0x18008baec  lea     rdx, [rbp+1A0h+lpSubKey]
0x18008baf3  lea     rcx, [rbp+1A0h+var_218]
0x18008baf7  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x18008bafc  nop
0x18008bafd  mov     [rsp+2A0h+var_248], r13d
0x18008bb02  mov     [rsp+2A0h+var_230], 4
0x18008bb0a  lea     rdx, [rbp+1A0h+lpSubKey]
0x18008bb11  cmp     [rbp+1A0h+var_E0], 7
0x18008bb19  cmova   rdx, [rbp+1A0h+lpSubKey]; lpSubKey
0x18008bb21  lea     rax, [rsp+2A0h+var_230]
0x18008bb26  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18008bb2b  lea     rax, [rsp+2A0h+var_248]
0x18008bb30  mov     [rsp+2A0h+pvData], rax; pvData
0x18008bb35  mov     [rsp+2A0h+pdwType], r13; unsigned int
0x18008bb3a  mov     r9d, 10h; dwFlags
0x18008bb40  lea     r8, aUserentered; "UserEntered"
0x18008bb47  mov     rcx, [rbp+1A0h+hkey]; hkey
0x18008bb4b  call    cs:__imp_RegGetValueW
0x18008bb51  test    eax, eax
0x18008bb53  jnz     loc_18008BE18
0x18008bb59  cmp     [rsp+2A0h+var_248], r13d
0x18008bb5e  jnz     loc_18008BCFB
0x18008bb64  mov     rax, [rbp+1A0h+var_17C]
0x18008bb68  mov     qword ptr [rsp+2A0h+FileTime1.dwLowDateTime], rax
0x18008bb6d  cmp     [rbp+1A0h+var_148], r13
0x18008bb71  jnz     short loc_18008BB8E
0x18008bb73  lea     rdx, [rbp+1A0h+var_138]
0x18008bb77  lea     rcx, [rbp+1A0h+var_158]
0x18008bb7b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008bb80  mov     rax, qword ptr [rsp+2A0h+FileTime1.dwLowDateTime]
0x18008bb85  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x18008bb89  jmp     loc_18008BCE5
0x18008bb8e  mov     [rsp+2A0h+Sid], r13
0x18008bb93  xor     edx, edx
0x18008bb95  lea     rcx, [rsp+2A0h+Sid]
0x18008bb9a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18008bb9f  lea     rcx, [rbp+1A0h+StringSid]
0x18008bba6  cmp     [rbp+1A0h+var_100], 7
0x18008bbae  cmova   rcx, [rbp+1A0h+StringSid]; StringSid
0x18008bbb6  lea     rdx, [rsp+2A0h+Sid]; Sid
0x18008bbbb  call    cs:__imp_ConvertStringSidToSidW
0x18008bbc1  test    eax, eax
0x18008bbc3  jz      loc_18008BD5C
0x18008bbc9  lea     rdx, [rbp+1A0h+FileTime2]; lpFileTime2
0x18008bbcd  lea     rcx, [rsp+2A0h+FileTime1]; lpFileTime1
0x18008bbd2  call    cs:__imp_CompareFileTime
0x18008bbd8  cmp     eax, 1
0x18008bbdb  jnz     loc_18008BC69
0x18008bbe1  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18008bbe8  jz      short loc_18008BC1F
0x18008bbea  lea     rax, [rbp+1A0h+var_158]
0x18008bbee  cmp     [rbp+1A0h+var_140], 7
0x18008bbf3  cmova   rax, qword ptr [rbp+1A0h+var_158]
0x18008bbf8  lea     r9, [rbp+1A0h+var_138]
0x18008bbfc  cmp     [rbp+1A0h+var_120], 7
0x18008bc04  cmova   r9, [rbp+1A0h+var_138]
0x18008bc09  mov     [rsp+2A0h+pdwType], rax
0x18008bc0e  mov     r8, [rsp+2A0h+Sid]
0x18008bc13  lea     rdx, EVENT_HFB_USERNAMESIDCACHE_FOUND_STALEUSERNAME
0x18008bc1a  call    McTemplateU0kzz_EventWriteTransfer
0x18008bc1f  lea     r8, [rbp+1A0h+var_158]
0x18008bc23  lea     rdx, [rbp+1A0h+StringSid]
0x18008bc2a  lea     rcx, [rbp+1A0h+var_90]
0x18008bc31  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::make_pair<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x18008bc36  nop
0x18008bc37  mov     rdx, rax
0x18008bc3a  lea     rcx, [rsp+2A0h+var_260]
0x18008bc3f  call    ?push_back@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::list<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x18008bc44  nop
0x18008bc45  lea     rcx, [rbp+1A0h+var_90]
0x18008bc4c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x18008bc51  lea     rdx, [rbp+1A0h+var_138]
0x18008bc55  lea     rcx, [rbp+1A0h+var_158]
0x18008bc59  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008bc5e  mov     rax, qword ptr [rsp+2A0h+FileTime1.dwLowDateTime]
0x18008bc63  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x18008bc67  jmp     short loc_18008BCDA
0x18008bc69  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18008bc70  jz      short loc_18008BCA7
0x18008bc72  lea     rax, [rbp+1A0h+var_138]
0x18008bc76  cmp     [rbp+1A0h+var_120], 7
0x18008bc7e  cmova   rax, [rbp+1A0h+var_138]
0x18008bc83  lea     r9, [rbp+1A0h+var_158]
0x18008bc87  cmp     [rbp+1A0h+var_140], 7
0x18008bc8c  cmova   r9, qword ptr [rbp+1A0h+var_158]
0x18008bc91  mov     [rsp+2A0h+pdwType], rax
0x18008bc96  mov     r8, [rsp+2A0h+Sid]
0x18008bc9b  lea     rdx, EVENT_HFB_USERNAMESIDCACHE_FOUND_STALEUSERNAME
0x18008bca2  call    McTemplateU0kzz_EventWriteTransfer
0x18008bca7  lea     r8, [rbp+1A0h+var_138]
0x18008bcab  lea     rdx, [rbp+1A0h+StringSid]
0x18008bcb2  lea     rcx, [rbp+1A0h+var_90]
0x18008bcb9  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::make_pair<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x18008bcbe  nop
0x18008bcbf  mov     rdx, rax
0x18008bcc2  lea     rcx, [rsp+2A0h+var_260]
0x18008bcc7  call    ?push_back@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::list<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x18008bccc  nop
0x18008bccd  lea     rcx, [rbp+1A0h+var_90]
0x18008bcd4  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x18008bcd9  nop
0x18008bcda  lea     rcx, [rsp+2A0h+Sid]; void *
0x18008bcdf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008bce4  nop
0x18008bce5  lea     rcx, [rbp+1A0h+lpSubKey]
0x18008bcec  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bcf1  inc     esi
0x18008bcf3  mov     [rbp+1A0h+var_208], esi
0x18008bcf6  jmp     loc_18008BAE3
0x18008bcfb  lea     rcx, [rbp+1A0h+lpSubKey]
0x18008bd02  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd07  nop
0x18008bd08  lea     rcx, [rbp+1A0h+hkey]; this
0x18008bd0c  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008bd11  nop
0x18008bd12  lea     rcx, [rbp+1A0h+var_138]
0x18008bd16  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd1b  inc     edi
0x18008bd1d  mov     [rbp+1A0h+var_A8], edi
0x18008bd23  jmp     loc_18008BA8F
0x18008bd28  lea     rcx, [rbp+1A0h+var_158]
0x18008bd2c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd31  nop
0x18008bd32  lea     rcx, [rbp+1A0h+var_1E8]; this
0x18008bd36  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008bd3b  nop
0x18008bd3c  lea     rcx, [rbp+1A0h+var_D8]
0x18008bd43  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd48  nop
0x18008bd49  lea     rcx, [rbp+1A0h+StringSid]
0x18008bd50  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd55  inc     ebx
0x18008bd57  jmp     loc_18008B9CF
0x18008bd5c  mov     rcx, [rbp+1A8h]; this
0x18008bd63  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008bd6a  mov     edx, 64Dh; void *
0x18008bd6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008bd74  mov     esi, eax
0x18008bd76  lea     rcx, [rsp+2A0h+Sid]; void *
0x18008bd7b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008bd80  nop
0x18008bd81  lea     rcx, [rbp+1A0h+lpSubKey]
0x18008bd88  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bd8d  nop
0x18008bd8e  lea     rcx, [rbp+1A0h+hkey]; this
0x18008bd92  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008bd97  nop
0x18008bd98  lea     rcx, [rbp+1A0h+var_138]
0x18008bd9c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bda1  nop
0x18008bda2  lea     rcx, [rbp+1A0h+var_158]
0x18008bda6  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bdab  nop
0x18008bdac  lea     rcx, [rbp+1A0h+var_1E8]; this
0x18008bdb0  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008bdb5  nop
0x18008bdb6  lea     rcx, [rbp+1A0h+var_D8]
0x18008bdbd  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bdc2  nop
0x18008bdc3  lea     rcx, [rbp+1A0h+StringSid]
0x18008bdca  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18008bdcf  nop
0x18008bdd0  lea     rcx, [rbp+1A0h+hKey]; this
0x18008bdd4  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18008bdd9  nop
0x18008bdda  mov     rcx, [rsp+2A0h+var_260]
0x18008bddf  mov     rax, [rcx+8]
0x18008bde3  mov     [rax], r13
0x18008bde6  mov     rdi, [rcx]
0x18008bde9  test    rdi, rdi
0x18008bdec  jz      loc_18008BEC3
0x18008bdf2  mov     rbx, [rdi]
0x18008bdf5  lea     rcx, [rdi+10h]
0x18008bdf9  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x18008bdfe  mov     edx, 50h ; 'P'
0x18008be03  mov     rcx, rdi
0x18008be06  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008be0b  mov     rdi, rbx
0x18008be0e  test    rbx, rbx
0x18008be11  jnz     short loc_18008BDF2
0x18008be13  jmp     loc_18008BEC3
0x18008be18  mov     rcx, [rbp+1A8h]; this
0x18008be1f  mov     r9d, eax; char *
0x18008be22  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008be29  mov     edx, 636h; void *
0x18008be2e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008be33  mov     esi, eax
0x18008be35  lea     rcx, [rbp+1A0h+lpSubKey]
  ... truncated ...
```
