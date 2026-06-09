# NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)

- ea: `0x180026e6c`
- end: `0x180027641`
- name: `?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ`
- size: `2005`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005c028`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x180018a9c`
- `0x1800193b0`
- `0x18001a77c`
- `0x180022e68`
- `0x180023278`
- `0x1800232a0`
- `0x180024dfc`
- `0x1800264b8`
- `0x180026e6c`
- `0x1800281a4`
- `0x18002a838`
- `0x18002adf4`
- `0x18002c640`
- `0x18005b730`
- `0x18005b768`
- `0x18005b998`
- `0x18005bbac`
- `0x18005bbd4`
- `0x18005bbfc`
- `0x18005be8c`
- `0x18005c3f0`
- `0x18005c424`
- `0x18005c4e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027130`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180027130`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027113`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002749c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027113`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002749c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800270a1`

## string_xrefs

- `0x180026ed8`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800272c3`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027386`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x1800274e5`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x180027559`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::Detail::CacheCleanupMultipleUsersForSid(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  int v3; // ebx
  int v4; // r12d
  __int64 v5; // rax
  const unsigned __int16 *v6; // r8
  int v7; // edi
  unsigned int v8; // r14d
  const unsigned __int16 *v9; // r8
  int v10; // esi
  int v11; // r15d
  const WCHAR *v12; // rdx
  unsigned int ValueW; // eax
  PSID *v14; // rax
  const WCHAR *v15; // rcx
  const char *v16; // r9
  int v17; // edx
  int v18; // ecx
  _QWORD *v19; // rax
  unsigned __int16 **v20; // r9
  __int64 v21; // rax
  unsigned __int16 **v22; // rax
  _QWORD *v23; // r9
  __int64 v24; // rax
  unsigned int LastError; // r14d
  _QWORD **v26; // rcx
  _QWORD *v27; // rsi
  _QWORD *v28; // rbx
  _QWORD **v29; // rcx
  _QWORD *v30; // rsi
  _QWORD *v31; // rbx
  _QWORD *v32; // rdi
  _QWORD *i; // rbx
  __int64 *v34; // rsi
  __int64 v35; // rcx
  _QWORD *v36; // r14
  int v37; // eax
  int v38; // r15d
  PSID *v39; // rax
  const WCHAR *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  const char *v43; // r9
  _QWORD **v44; // rdx
  _QWORD *v45; // rsi
  _QWORD *v46; // rbx
  _QWORD **v47; // rcx
  _QWORD *v48; // rsi
  _QWORD *v49; // rbx
  _QWORD **v50; // rcx
  _QWORD *v51; // rsi
  _QWORD *v52; // rbx
  unsigned __int16 **pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  __int128 v56; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v60; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime1; // [rsp+78h] [rbp-88h] BYREF
  FILETIME FileTime2; // [rsp+80h] [rbp-80h] BYREF
  HKEY v64; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v65; // [rsp+90h] [rbp-70h]
  FILETIME v66; // [rsp+94h] [rbp-6Ch]
  char v67; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v68[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v69; // [rsp+C8h] [rbp-38h]
  _QWORD v70[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v71; // [rsp+E0h] [rbp-20h]
  HKEY v72; // [rsp+E8h] [rbp-18h] BYREF
  int v73; // [rsp+F0h] [rbp-10h]
  char v74; // [rsp+100h] [rbp+0h] BYREF
  HKEY hkey; // [rsp+118h] [rbp+18h] BYREF
  int v76; // [rsp+120h] [rbp+20h]
  FILETIME v77; // [rsp+124h] [rbp+24h]
  char v78; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 *v79[3]; // [rsp+148h] [rbp+48h] BYREF
  unsigned __int64 v80; // [rsp+160h] [rbp+60h]
  _QWORD v81[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int64 v82; // [rsp+180h] [rbp+80h]
  LPCWSTR StringSid[4]; // [rsp+188h] [rbp+88h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int16 *v85[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v86[2]; // [rsp+1E8h] [rbp+E8h] BYREF
  int v87; // [rsp+1F8h] [rbp+F8h]
  _BYTE v88[64]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v60 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v60,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&v60,
                                        pdwType);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v56 = 0;
    std::list<std::pair<std::wstring,std::wstring>>::_Alloc_sentinel_and_proxy(&v56);
    NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v72, HKEY_LOCAL_MACHINE, v60);
    v70[0] = v72;
    v70[1] = &v74;
    v3 = 0;
    v4 = v73;
    while ( 1 )
    {
      v71 = v3;
      if ( v3 == v4 )
        break;
      NgcUtils::RegKeyIterator::Iterator::operator*(v70, StringSid);
      v5 = std::operator+<unsigned short>(v86, StringSid, L"\\");
      std::operator+<unsigned short>(v85, v5);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v86);
      v6 = (const unsigned __int16 *)v85;
      if ( v85[3] > (unsigned __int16 *)7 )
        v6 = v85[0];
      NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&v64, v72, v6);
      if ( v65 >= 2 )
      {
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v81);
        FileTime2 = v66;
        v86[0] = v64;
        v86[1] = &v67;
        v7 = 0;
        v87 = 0;
        v8 = v65;
LABEL_9:
        if ( v7 != v8 )
        {
          NgcUtils::RegKeyIterator::Iterator::operator*(v86, v79);
          v9 = (const unsigned __int16 *)v79;
          if ( v80 > 7 )
            v9 = v79[0];
          NgcUtils::RegKeyIterator::RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey, v64, v9);
          v68[0] = hkey;
          v68[1] = &v78;
          v10 = 0;
          v69 = 0;
          v11 = v76;
          while ( 1 )
          {
            if ( v10 == v11 )
              goto LABEL_41;
            NgcUtils::RegKeyIterator::Iterator::operator*(v68, lpSubKey);
            pvData = 0;
            pcbData = 4;
            v12 = (const WCHAR *)lpSubKey;
            if ( lpSubKey[3] > (LPCWSTR)7 )
              v12 = lpSubKey[0];
            ValueW = RegGetValueW(hkey, v12, L"UserEntered", 0x10u, 0, &pvData, &pcbData);
            if ( ValueW )
              break;
            if ( pvData )
            {
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
LABEL_41:
              NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
              v87 = ++v7;
              goto LABEL_9;
            }
            FileTime1 = v77;
            if ( v81[2] )
            {
              v58 = 0;
              v14 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v58);
              v15 = (const WCHAR *)StringSid;
              if ( StringSid[3] > (LPCWSTR)7 )
                v15 = StringSid[0];
              if ( !ConvertStringSidToSidW(v15, v14) )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x64D,
                              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                              v16);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v58);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&hkey);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v79);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v81);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v64);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v85);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
                NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v72);
                v26 = (_QWORD **)v56;
                **(_QWORD **)(v56 + 8) = 0;
                v27 = *v26;
                if ( *v26 )
                {
                  do
                  {
                    v28 = (_QWORD *)*v27;
                    std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v27 + 2);
                    std::_Deallocate<16>(v27, 80);
                    v27 = v28;
                  }
                  while ( v28 );
                }
                goto LABEL_49;
              }
              if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v19 = v81;
                  if ( v82 > 7 )
                    v19 = (_QWORD *)v81[0];
                  v20 = v79;
                  if ( v80 > 7 )
                    LODWORD(v20) = v79[0];
                  McTemplateU0kzz_EventWriteTransfer(v18, v17, v58, (_DWORD)v20, (__int64)v19);
                }
                v21 = std::make_pair<std::wstring &,std::wstring &>(v88, StringSid, v81);
                std::list<std::pair<std::wstring,std::wstring>>::_Emplace<std::pair<std::wstring,std::wstring>>(
                  &v56,
                  v56,
                  v21);
                std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v88);
                std::wstring::operator=(v81, v79);
                FileTime2 = FileTime1;
              }
              else
              {
                if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
                {
                  v22 = v79;
                  if ( v80 > 7 )
                    v22 = (unsigned __int16 **)v79[0];
                  v23 = v81;
                  if ( v82 > 7 )
                    LODWORD(v23) = v81[0];
                  McTemplateU0kzz_EventWriteTransfer(v18, v17, v58, (_DWORD)v23, (__int64)v22);
                }
                v24 = std::make_pair<std::wstring &,std::wstring &>(v88, StringSid, v79);
                std::list<std::pair<std::wstring,std::wstring>>::_Emplace<std::pair<std::wstring,std::wstring>>(
                  &v56,
                  v56,
                  v24);
                std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v88);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v58);
            }
            else
            {
              std::wstring::operator=(v81, v79);
              FileTime2 = FileTime1;
            }
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
            v69 = ++v10;
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
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v81);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v64);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v85);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
          NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v72);
          v29 = (_QWORD **)v56;
          **(_QWORD **)(v56 + 8) = 0;
          v30 = *v29;
          if ( *v29 )
          {
            do
            {
              v31 = (_QWORD *)*v30;
              std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v30 + 2);
              std::_Deallocate<16>(v30, 80);
              v30 = v31;
            }
            while ( v31 );
          }
LABEL_49:
          std::_Deallocate<16>(v56, 80);
          v2 = LastError;
          goto LABEL_74;
        }
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v81);
      }
      NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v64);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v85);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      ++v3;
    }
    v32 = (_QWORD *)v56;
    for ( i = *(_QWORD **)v56; i != v32; i = (_QWORD *)*i )
    {
      v34 = i + 2;
      if ( i[5] <= 7u )
        v35 = (__int64)(i + 2);
      else
        v35 = *v34;
      v36 = i + 6;
      v37 = NgcUtils::Detail::CacheRemoveUser(v35, (const WCHAR *)i + 24);
      v38 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x670,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
          (const char *)(unsigned int)v37,
          pdwTypea);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v72);
        v47 = (_QWORD **)v56;
        **(_QWORD **)(v56 + 8) = 0;
        v48 = *v47;
        if ( *v47 )
        {
          do
          {
            v49 = (_QWORD *)*v48;
            std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v48 + 2);
            std::_Deallocate<16>(v48, 80);
            v48 = v49;
          }
          while ( v49 );
        }
        std::_Deallocate<16>(v56, 80);
        v2 = v38;
        goto LABEL_74;
      }
      v59 = 0;
      v39 = (PSID *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(&v59);
      if ( i[5] <= 7u )
        v40 = (const WCHAR *)(i + 2);
      else
        v40 = (const WCHAR *)*v34;
      if ( !ConvertStringSidToSidW(v40, v39) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x675,
                      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
                      v43);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v59);
        NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v72);
        v44 = (_QWORD **)v56;
        **(_QWORD **)(v56 + 8) = 0;
        v45 = *v44;
        if ( *v44 )
        {
          do
          {
            v46 = (_QWORD *)*v45;
            std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v45 + 2);
            std::_Deallocate<16>(v45, 80);
            v45 = v46;
          }
          while ( v46 );
        }
        goto LABEL_49;
      }
      if ( (Microsoft_Windows_HelloForBusinessEnableBits & 4) != 0 )
      {
        if ( i[9] > 7u )
          v36 = (_QWORD *)*v36;
        McTemplateU0kz_EventWriteTransfer(v42, v41, v59, v36);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v59);
    }
    NgcUtils::RegKeyIterator::~RegKeyIterator((NgcUtils::RegKeyIterator *)&v72);
    v50 = (_QWORD **)v56;
    **(_QWORD **)(v56 + 8) = 0;
    v51 = *v50;
    if ( *v50 )
    {
      do
      {
        v52 = (_QWORD *)*v51;
        std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(v51 + 2);
        std::_Deallocate<16>(v51, 80);
        v51 = v52;
      }
      while ( v52 );
    }
    std::_Deallocate<16>(v56, 80);
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
LABEL_74:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v60);
  return v2;
}

```

## disassembly

```asm
0x180026e6c  push    rbp
0x180026e6e  push    rbx
0x180026e6f  push    rsi
0x180026e70  push    rdi
0x180026e71  push    r12
0x180026e73  push    r13
0x180026e75  push    r14
0x180026e77  push    r15
0x180026e79  lea     rbp, [rsp-168h]
0x180026e81  sub     rsp, 268h
0x180026e88  mov     rax, cs:__security_cookie
0x180026e8f  xor     rax, rsp
0x180026e92  mov     [rbp+1A0h+var_50], rax
0x180026e99  xor     r13d, r13d
0x180026e9c  mov     [rsp+2A0h+var_238], r13
0x180026ea1  xor     edx, edx
0x180026ea3  lea     rcx, [rsp+2A0h+var_238]
0x180026ea8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026ead  lea     r9, [rsp+2A0h+var_238]; unsigned __int16 *
0x180026eb2  xor     r8d, r8d; unsigned __int16 *
0x180026eb5  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180026ebc  lea     rcx, aNgccredprov; "NgcCredprov"
0x180026ec3  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x180026ec8  mov     ebx, eax
0x180026eca  test    eax, eax
0x180026ecc  jns     short loc_180026EEE
0x180026ece  mov     rcx, [rbp+1A8h]; this
0x180026ed5  mov     r9d, eax; char *
0x180026ed8  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180026edf  mov     edx, 618h; void *
0x180026ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ee9  jmp     loc_180027611
0x180026eee  xorps   xmm0, xmm0
0x180026ef1  movdqu  [rsp+2A0h+var_260], xmm0
0x180026ef7  lea     rcx, [rsp+2A0h+var_260]
0x180026efc  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<std::wstring,std::wstring>>::_Alloc_sentinel_and_proxy(void)
0x180026f01  nop
0x180026f02  mov     r8, [rsp+2A0h+var_238]; unsigned __int16 *
0x180026f07  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180026f0e  lea     rcx, [rbp+1A0h+var_1B8]; this
0x180026f12  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180026f17  nop
0x180026f18  mov     rax, [rbp+1A0h+var_1B8]
0x180026f1c  mov     [rbp+1A0h+var_1D0], rax
0x180026f20  lea     rax, [rbp+1A0h+var_1A0]
0x180026f24  mov     [rbp+1A0h+var_1C8], rax
0x180026f28  mov     ebx, r13d
0x180026f2b  mov     r12d, [rbp+1A0h+var_1B0]
0x180026f2f  mov     [rbp+1A0h+var_1C0], ebx
0x180026f32  cmp     ebx, r12d
0x180026f35  jz      loc_180027440
0x180026f3b  lea     rdx, [rbp+1A0h+StringSid]
0x180026f42  lea     rcx, [rbp+1A0h+var_1D0]
0x180026f46  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180026f4b  nop
0x180026f4c  lea     r8, asc_18008F0A4; "\\"
0x180026f53  lea     rdx, [rbp+1A0h+StringSid]
0x180026f5a  lea     rcx, [rbp+1A0h+var_B8]
0x180026f61  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180026f66  nop
0x180026f67  mov     rdx, rax
0x180026f6a  lea     rcx, [rbp+1A0h+var_D8]
0x180026f71  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180026f76  nop
0x180026f77  lea     rcx, [rbp+1A0h+var_B8]
0x180026f7e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180026f83  lea     r8, [rbp+1A0h+var_D8]
0x180026f8a  cmp     [rbp+1A0h+var_C0], 7
0x180026f92  cmova   r8, [rbp+1A0h+var_D8]; unsigned __int16 *
0x180026f9a  mov     rdx, [rbp+1A0h+var_1B8]; HKEY
0x180026f9e  lea     rcx, [rbp+1A0h+var_218]; this
0x180026fa2  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x180026fa7  nop
0x180026fa8  cmp     [rbp+1A0h+var_210], 2
0x180026fac  jb      loc_180027292
0x180026fb2  lea     rcx, [rbp+1A0h+var_138]
0x180026fb6  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180026fbb  nop
0x180026fbc  mov     rax, [rbp+1A0h+var_20C]
0x180026fc0  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x180026fc4  mov     rax, [rbp+1A0h+var_218]
0x180026fc8  mov     [rbp+1A0h+var_B8], rax
0x180026fcf  lea     rax, [rbp+1A0h+var_200]
0x180026fd3  mov     [rbp+1A0h+var_B0], rax
0x180026fda  mov     edi, r13d
0x180026fdd  mov     [rbp+1A0h+var_A8], r13d
0x180026fe4  mov     r14d, [rbp+1A0h+var_210]
0x180026fe8  cmp     edi, r14d
0x180026feb  jz      loc_180027288
0x180026ff1  lea     rdx, [rbp+1A0h+var_158]
0x180026ff5  lea     rcx, [rbp+1A0h+var_B8]
0x180026ffc  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180027001  nop
0x180027002  lea     r8, [rbp+1A0h+var_158]
0x180027006  cmp     [rbp+1A0h+var_140], 7
0x18002700b  cmova   r8, [rbp+1A0h+var_158]; unsigned __int16 *
0x180027010  mov     rdx, [rbp+1A0h+var_218]; HKEY
0x180027014  lea     rcx, [rbp+1A0h+hkey]; this
0x180027018  call    ??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z; NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)
0x18002701d  nop
0x18002701e  mov     rax, [rbp+1A0h+hkey]
0x180027022  mov     [rbp+1A0h+var_1E8], rax
0x180027026  lea     rax, [rbp+1A0h+var_170]
0x18002702a  mov     [rbp+1A0h+var_1E0], rax
0x18002702e  mov     esi, r13d
0x180027031  mov     [rbp+1A0h+var_1D8], r13d
0x180027035  mov     r15d, [rbp+1A0h+var_180]
0x180027039  cmp     esi, r15d
0x18002703c  jz      loc_180027268
0x180027042  lea     rdx, [rbp+1A0h+lpSubKey]
0x180027049  lea     rcx, [rbp+1A0h+var_1E8]
0x18002704d  call    ??DIterator@RegKeyIterator@NgcUtils@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; NgcUtils::RegKeyIterator::Iterator::operator*(void)
0x180027052  nop
0x180027053  mov     [rsp+2A0h+var_250], r13d
0x180027058  mov     [rsp+2A0h+var_230], 4
0x180027060  lea     rdx, [rbp+1A0h+lpSubKey]
0x180027067  cmp     [rbp+1A0h+var_E0], 7
0x18002706f  cmova   rdx, [rbp+1A0h+lpSubKey]; lpSubKey
0x180027077  lea     rax, [rsp+2A0h+var_230]
0x18002707c  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180027081  lea     rax, [rsp+2A0h+var_250]
0x180027086  mov     [rsp+2A0h+pvData], rax; pvData
0x18002708b  mov     [rsp+2A0h+pdwType], r13; unsigned int
0x180027090  mov     r9d, 10h; dwFlags
0x180027096  lea     r8, aUserentered; "UserEntered"
0x18002709d  mov     rcx, [rbp+1A0h+hkey]; hkey
0x1800270a1  call    cs:__imp_RegGetValueW
0x1800270a8  nop     dword ptr [rax+rax+00h]
0x1800270ad  test    eax, eax
0x1800270af  jnz     loc_18002737C
0x1800270b5  cmp     [rsp+2A0h+var_250], r13d
0x1800270ba  jnz     loc_18002725B
0x1800270c0  mov     rax, [rbp+1A0h+var_17C]
0x1800270c4  mov     qword ptr [rsp+2A0h+FileTime1.dwLowDateTime], rax
0x1800270c9  cmp     [rbp+1A0h+var_128], r13
0x1800270cd  jnz     short loc_1800270EA
0x1800270cf  lea     rdx, [rbp+1A0h+var_158]
0x1800270d3  lea     rcx, [rbp+1A0h+var_138]
0x1800270d7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800270dc  mov     rax, qword ptr [rsp+2A0h+FileTime1.dwLowDateTime]
0x1800270e1  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x1800270e5  jmp     loc_180027245
0x1800270ea  mov     [rsp+2A0h+var_248], r13
0x1800270ef  lea     rcx, [rsp+2A0h+var_248]
0x1800270f4  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::put(void)
0x1800270f9  lea     rcx, [rbp+1A0h+StringSid]
0x180027100  cmp     [rbp+1A0h+var_100], 7
0x180027108  cmova   rcx, [rbp+1A0h+StringSid]; StringSid
0x180027110  mov     rdx, rax; Sid
0x180027113  call    cs:__imp_ConvertStringSidToSidW
0x18002711a  nop     dword ptr [rax+rax+00h]
0x18002711f  test    eax, eax
0x180027121  jz      loc_1800272BC
0x180027127  lea     rdx, [rbp+1A0h+FileTime2]; lpFileTime2
0x18002712b  lea     rcx, [rsp+2A0h+FileTime1]; lpFileTime1
0x180027130  call    cs:__imp_CompareFileTime
0x180027137  nop     dword ptr [rax+rax+00h]
0x18002713c  cmp     eax, 1
0x18002713f  jnz     loc_1800271CB
0x180027145  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x18002714c  jz      short loc_18002717C
0x18002714e  lea     rax, [rbp+1A0h+var_138]
0x180027152  cmp     [rbp+1A0h+var_120], 7
0x18002715a  cmova   rax, [rbp+1A0h+var_138]
0x18002715f  lea     r9, [rbp+1A0h+var_158]
0x180027163  cmp     [rbp+1A0h+var_140], 7
0x180027168  cmova   r9, [rbp+1A0h+var_158]
0x18002716d  mov     [rsp+2A0h+pdwType], rax
0x180027172  mov     r8, [rsp+2A0h+var_248]
0x180027177  call    McTemplateU0kzz_EventWriteTransfer
0x18002717c  lea     r8, [rbp+1A0h+var_138]
0x180027180  lea     rdx, [rbp+1A0h+StringSid]
0x180027187  lea     rcx, [rbp+1A0h+var_90]
0x18002718e  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::make_pair<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x180027193  nop
0x180027194  mov     r8, rax
0x180027197  mov     rdx, qword ptr [rsp+2A0h+var_260]
0x18002719c  lea     rcx, [rsp+2A0h+var_260]
0x1800271a1  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_List_node@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@QEAU21@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::list<std::pair<std::wstring,std::wstring>>::_Emplace<std::pair<std::wstring,std::wstring>>(std::_List_node<std::pair<std::wstring,std::wstring>,void *> * const,std::pair<std::wstring,std::wstring> &&)
0x1800271a6  nop
0x1800271a7  lea     rcx, [rbp+1A0h+var_90]
0x1800271ae  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x1800271b3  lea     rdx, [rbp+1A0h+var_158]
0x1800271b7  lea     rcx, [rbp+1A0h+var_138]
0x1800271bb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800271c0  mov     rax, qword ptr [rsp+2A0h+FileTime1.dwLowDateTime]
0x1800271c5  mov     qword ptr [rbp+1A0h+FileTime2.dwLowDateTime], rax
0x1800271c9  jmp     short loc_18002723A
0x1800271cb  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 4
0x1800271d2  jz      short loc_180027202
0x1800271d4  lea     rax, [rbp+1A0h+var_158]
0x1800271d8  cmp     [rbp+1A0h+var_140], 7
0x1800271dd  cmova   rax, [rbp+1A0h+var_158]
0x1800271e2  lea     r9, [rbp+1A0h+var_138]
0x1800271e6  cmp     [rbp+1A0h+var_120], 7
0x1800271ee  cmova   r9, [rbp+1A0h+var_138]
0x1800271f3  mov     [rsp+2A0h+pdwType], rax
0x1800271f8  mov     r8, [rsp+2A0h+var_248]
0x1800271fd  call    McTemplateU0kzz_EventWriteTransfer
0x180027202  lea     r8, [rbp+1A0h+var_158]
0x180027206  lea     rdx, [rbp+1A0h+StringSid]
0x18002720d  lea     rcx, [rbp+1A0h+var_90]
0x180027214  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::make_pair<std::wstring &,std::wstring &>(std::wstring &,std::wstring &)
0x180027219  nop
0x18002721a  mov     r8, rax
0x18002721d  mov     rdx, qword ptr [rsp+2A0h+var_260]
0x180027222  lea     rcx, [rsp+2A0h+var_260]
0x180027227  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$list@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAPEAU?$_List_node@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@QEAU21@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::list<std::pair<std::wstring,std::wstring>>::_Emplace<std::pair<std::wstring,std::wstring>>(std::_List_node<std::pair<std::wstring,std::wstring>,void *> * const,std::pair<std::wstring,std::wstring> &&)
0x18002722c  nop
0x18002722d  lea     rcx, [rbp+1A0h+var_90]
0x180027234  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x180027239  nop
0x18002723a  lea     rcx, [rsp+2A0h+var_248]
0x18002723f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027244  nop
0x180027245  lea     rcx, [rbp+1A0h+lpSubKey]
0x18002724c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027251  inc     esi
0x180027253  mov     [rbp+1A0h+var_1D8], esi
0x180027256  jmp     loc_180027039
0x18002725b  lea     rcx, [rbp+1A0h+lpSubKey]
0x180027262  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027267  nop
0x180027268  lea     rcx, [rbp+1A0h+hkey]; this
0x18002726c  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x180027271  nop
0x180027272  lea     rcx, [rbp+1A0h+var_158]
0x180027276  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002727b  inc     edi
0x18002727d  mov     [rbp+1A0h+var_A8], edi
0x180027283  jmp     loc_180026FE8
0x180027288  lea     rcx, [rbp+1A0h+var_138]
0x18002728c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027291  nop
0x180027292  lea     rcx, [rbp+1A0h+var_218]; this
0x180027296  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18002729b  nop
0x18002729c  lea     rcx, [rbp+1A0h+var_D8]
0x1800272a3  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800272a8  nop
0x1800272a9  lea     rcx, [rbp+1A0h+StringSid]
0x1800272b0  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800272b5  inc     ebx
0x1800272b7  jmp     loc_180026F2F
0x1800272bc  mov     rcx, [rbp+1A8h]; this
0x1800272c3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800272ca  mov     edx, 64Dh; void *
0x1800272cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800272d4  mov     r14d, eax
0x1800272d7  lea     rcx, [rsp+2A0h+var_248]
0x1800272dc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800272e1  nop
0x1800272e2  lea     rcx, [rbp+1A0h+lpSubKey]
0x1800272e9  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800272ee  nop
0x1800272ef  lea     rcx, [rbp+1A0h+hkey]; this
0x1800272f3  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x1800272f8  nop
0x1800272f9  lea     rcx, [rbp+1A0h+var_158]
0x1800272fd  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027302  nop
0x180027303  lea     rcx, [rbp+1A0h+var_138]
0x180027307  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002730c  nop
0x18002730d  lea     rcx, [rbp+1A0h+var_218]; this
0x180027311  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x180027316  nop
0x180027317  lea     rcx, [rbp+1A0h+var_D8]
0x18002731e  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027323  nop
0x180027324  lea     rcx, [rbp+1A0h+StringSid]
0x18002732b  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180027330  nop
0x180027331  lea     rcx, [rbp+1A0h+var_1B8]; this
0x180027335  call    ??1RegKeyIterator@NgcUtils@@QEAA@XZ; NgcUtils::RegKeyIterator::~RegKeyIterator(void)
0x18002733a  nop
0x18002733b  mov     rcx, qword ptr [rsp+2A0h+var_260]
0x180027340  mov     rax, [rcx+8]
0x180027344  mov     [rax], r13
0x180027347  mov     rsi, [rcx]
0x18002734a  mov     edi, 50h ; 'P'
0x18002734f  test    rsi, rsi
0x180027352  jz      loc_18002742B
0x180027358  mov     rbx, [rsi]
0x18002735b  lea     rcx, [rsi+10h]
0x18002735f  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::pair<std::wstring,_FILETIME>>::~pair<std::wstring const,std::pair<std::wstring,_FILETIME>>(void)
0x180027364  mov     rdx, rdi
0x180027367  mov     rcx, rsi
0x18002736a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002736f  mov     rsi, rbx
0x180027372  test    rbx, rbx
0x180027375  jnz     short loc_180027358
0x180027377  jmp     loc_18002742B
0x18002737c  mov     rcx, [rbp+1A8h]; this
0x180027383  mov     r9d, eax; char *
0x180027386  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002738d  mov     edx, 636h; void *
0x180027392  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027397  mov     r14d, eax
0x18002739a  lea     rcx, [rbp+1A0h+lpSubKey]
  ... truncated ...
```
