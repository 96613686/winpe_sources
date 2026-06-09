# wpcplugs::Sync::SyncAppInventory::Desktop::GetInstalledAppsForUser(Sid const &)

- ea: `0x18002dbec`
- end: `0x18002eb36`
- name: `?GetInstalledAppsForUser@Desktop@SyncAppInventory@Sync@wpcplugs@@YA?AV?$vector@U?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEBVSid@@@Z`
- size: `3914`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800875c4`
- `0x1800887b4`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180006ee0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x180009b30`
- `0x180009de0`
- `0x18000bba8`
- `0x18000e8b0`
- `0x18000ecc0`
- `0x18001484c`
- `0x18001ccf0`
- `0x18002ca60`
- `0x18002cad8`
- `0x18002cbb4`
- `0x18002ce48`
- `0x18002d15c`
- `0x18002d43c`
- `0x18002dbec`
- `0x18002ec00`
- `0x180035340`
- `0x18003547c`
- `0x180035e0c`
- `0x1800717b8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e283`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e283`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e4f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e8af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e5d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e524`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e5d7`

## string_xrefs

- `0x18002ea65`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002eb24`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002dcd4`: `Found {0} installed applications`
- `0x18002ddc9`: `Found installed app: {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
_QWORD *__fastcall wpcplugs::Sync::SyncAppInventory::Desktop::GetInstalledAppsForUser(_QWORD *a1, const WCHAR *a2)
{
  _QWORD *v3; // r12
  char **v4; // rax
  int v5; // r15d
  Private::Format *v6; // rcx
  __int64 v7; // rax
  HSTRING v8; // r13
  HSTRING v9; // rcx
  __int64 v10; // rax
  volatile signed __int32 *v11; // rdi
  Private::Format *v12; // rax
  Private::Format *v13; // rax
  __int64 v14; // rax
  char **v15; // rbx
  __int64 v16; // rax
  int v17; // r15d
  unsigned __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  HRESULT v21; // eax
  int v22; // ebx
  LPVOID v23; // rdi
  __int64 (__fastcall *v24)(LPVOID, PVOID, char **); // rbx
  unsigned int v25; // r8d
  const WCHAR *v26; // rax
  HSTRING_HEADER *v27; // rax
  int v28; // ebx
  int v29; // eax
  int v30; // ebx
  Private::Format *v31; // rax
  __int64 v32; // rax
  char *v33; // rbx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  char *v37; // rbx
  __int64 (__fastcall *v38)(char *, __int64, __int64 *); // rdi
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, HSTRING *); // rbx
  int v43; // eax
  int v44; // ebx
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, HSTRING *); // rbx
  int v47; // eax
  int v48; // ebx
  PCWSTR StringRawBuffer; // rdi
  Private::Format *v50; // rbx
  __int64 v51; // rax
  PCWSTR v52; // rax
  unsigned __int64 v53; // r8
  unsigned __int64 v54; // r8
  char **v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rcx
  Private::Format *v61; // rax
  Private::Format *v62; // rax
  int ppv; // [rsp+20h] [rbp-338h]
  int v64; // [rsp+30h] [rbp-328h]
  int v65; // [rsp+38h] [rbp-320h] BYREF
  HSTRING v66; // [rsp+40h] [rbp-318h] BYREF
  HSTRING string; // [rsp+48h] [rbp-310h] BYREF
  char **v68; // [rsp+50h] [rbp-308h]
  int v69; // [rsp+58h] [rbp-300h] BYREF
  char *v70; // [rsp+60h] [rbp-2F8h] BYREF
  const WCHAR *v71; // [rsp+68h] [rbp-2F0h] BYREF
  const WCHAR *v72; // [rsp+70h] [rbp-2E8h] BYREF
  LPVOID v73; // [rsp+78h] [rbp-2E0h] BYREF
  char **v74; // [rsp+80h] [rbp-2D8h] BYREF
  volatile signed __int32 *v75; // [rsp+88h] [rbp-2D0h]
  _QWORD *v76; // [rsp+90h] [rbp-2C8h]
  HSTRING v77; // [rsp+98h] [rbp-2C0h] BYREF
  HSTRING v78; // [rsp+A0h] [rbp-2B8h]
  _QWORD v79[2]; // [rsp+B0h] [rbp-2A8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+C0h] [rbp-298h] BYREF
  _BYTE v81[40]; // [rsp+E8h] [rbp-270h] BYREF
  _BYTE v82[40]; // [rsp+110h] [rbp-248h] BYREF
  _BYTE v83[40]; // [rsp+138h] [rbp-220h] BYREF
  _BYTE v84[40]; // [rsp+160h] [rbp-1F8h] BYREF
  __int128 v85; // [rsp+188h] [rbp-1D0h] BYREF
  char *v86; // [rsp+198h] [rbp-1C0h]
  __int64 v87; // [rsp+1A0h] [rbp-1B8h]
  __int128 v88; // [rsp+1A8h] [rbp-1B0h] BYREF
  volatile signed __int32 *v89; // [rsp+1B8h] [rbp-1A0h]
  unsigned __int64 v90; // [rsp+1C0h] [rbp-198h]
  char *v91; // [rsp+1C8h] [rbp-190h] BYREF
  unsigned int v92; // [rsp+1D0h] [rbp-188h]
  __int64 v93[3]; // [rsp+1D8h] [rbp-180h] BYREF
  int v94; // [rsp+1F0h] [rbp-168h] BYREF
  __int128 v95; // [rsp+1F8h] [rbp-160h] BYREF
  __int64 v96; // [rsp+208h] [rbp-150h]
  __int64 v97; // [rsp+210h] [rbp-148h]
  char v98; // [rsp+218h] [rbp-140h]
  __int128 v99; // [rsp+220h] [rbp-138h] BYREF
  __int128 v100; // [rsp+230h] [rbp-128h]
  __int128 v101; // [rsp+240h] [rbp-118h] BYREF
  char *v102; // [rsp+250h] [rbp-108h]
  __int64 v103; // [rsp+258h] [rbp-100h]
  char *v104[4]; // [rsp+260h] [rbp-F8h] BYREF
  char v105; // [rsp+280h] [rbp-D8h]
  __int128 Src; // [rsp+288h] [rbp-D0h] BYREF
  __int64 v107; // [rsp+298h] [rbp-C0h]
  __int64 v108; // [rsp+2A0h] [rbp-B8h]
  __int128 v109; // [rsp+2B0h] [rbp-A8h] BYREF
  char *v110; // [rsp+2C0h] [rbp-98h]
  __int64 v111; // [rsp+2C8h] [rbp-90h]
  __int128 v112; // [rsp+2D0h] [rbp-88h] BYREF
  char *v113; // [rsp+2E0h] [rbp-78h] BYREF
  __int64 v114; // [rsp+2E8h] [rbp-70h]
  HSTRING_HEADER v115; // [rsp+300h] [rbp-58h] BYREF
  __int64 v116; // [rsp+318h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v72 = a2;
  v3 = a1;
  v76 = a1;
  v71 = a2;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (char **)operator new(0x20u);
  v68 = v4;
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *v4 = (char *)&std::_Ref_count_obj2<wpcplugs::AppRepository::StateRepo::AppRepository>::`vftable';
  v4[2] = (char *)&wpcplugs::AppRepository::StateRepo::AppRepository::`vftable';
  *((_BYTE *)v4 + 24) = 0;
  v79[0] = v4 + 2;
  v79[1] = v4;
  v5 = 7;
  v64 = 7;
  wpcplugs::AppRepository::StateRepo::AppRepository::GetPackageFamiliesForUser(v4 + 2, &v77, a2);
  v88 = 0;
  v89 = 0;
  v90 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v88, L"Found {0} installed applications", 0x20u);
  v6 = (Private::Format *)StringAlgo::FormatString(v104, &v88);
  v66 = (HSTRING)(((char *)v78 - (char *)v77) >> 4);
  v7 = Private::Format::operator%<unsigned __int64>(v6);
  v65 = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v65, v7);
  std::wstring::~wstring(v104);
  v8 = v77;
  v9 = v78;
  for ( string = v78; ; v9 = string )
  {
    v66 = v8;
    if ( v8 == v9 )
      break;
    v10 = *((_QWORD *)v8 + 1);
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v68 = *(char ***)v8;
    v74 = v68;
    v11 = (volatile signed __int32 *)*((_QWORD *)v8 + 1);
    v75 = v11;
    (*((void (__fastcall **)(char **, char **))*v68 + 1))(v68, &v91);
    v85 = 0;
    v86 = 0;
    v87 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v85, L"Found installed app: {0}", 0x18u);
    v12 = (Private::Format *)StringAlgo::FormatString(v104, &v85);
    v13 = Private::Format::operator%<std::wstring>(v12, (__int64)&v91);
    v65 = 3;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v65, v13);
    std::wstring::~wstring(v104);
    try
    {
      v88 = 0;
      v89 = 0;
      v90 = 7;
      LOWORD(v88) = 0;
      v14 = (*((__int64 (__fastcall **)(char **, __int128 *))*v68 + 2))(v68, &v85);
      std::wstring::operator=(&v88, v14);
      std::wstring::~wstring((char **)&v85);
    }
    catch ( ... )
    {
      v85 = 0;
      v86 = 0;
      v87 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        (char **)&v85,
        L"Error in retrieving localized display name for app: {0}",
        0x37u);
      v61 = (Private::Format *)StringAlgo::FormatString(v104, &v85);
      v62 = Private::Format::operator%<std::wstring>(v61, (__int64)&v91);
      v65 = 1;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v65, v62);
      std::wstring::~wstring(v104);
      v8 = v66;
      v11 = v75;
      v5 = v64;
      v3 = v76;
      v72 = v71;
    }
    v15 = (char **)std::wstring::wstring((__int64)&v115, (__int64)&v91);
    v68 = v15;
    v16 = std::wstring::wstring((__int64)&Src, (__int64)v15);
    StringAlgo::ToLower<unsigned short>(&v85, v16);
    std::wstring::~wstring(v15);
    v109 = v85;
    v110 = v86;
    v111 = v87;
    v86 = 0;
    v87 = 7;
    LOWORD(v85) = 0;
    std::wstring::wstring((__int64)&v112, (__int64)&v88);
    v17 = v5 | 8;
    v68 = (char **)&v94;
    std::wstring::wstring((__int64)v104, (__int64)&v109);
    v105 = 0;
    v94 = 0;
    std::wstring::~wstring(v104);
    std::wstring::wstring((__int64)&v95, (__int64)&v109);
    v98 = 0;
    std::wstring::wstring((__int64)v104, (__int64)&v109);
    v105 = 0;
    Src = 0;
    v107 = 0;
    v108 = 0;
    v18 = -1;
    do
      ++v18;
    while ( aAppx_0[v18] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"appx:", v18);
    v19 = std::wstring::append(&Src);
    v99 = 0;
    v100 = 0u;
    v99 = *(_OWORD *)v19;
    v100 = *(_OWORD *)(v19 + 16);
    *(_QWORD *)(v19 + 16) = 0;
    *(_QWORD *)(v19 + 24) = 7;
    *(_WORD *)v19 = 0;
    std::wstring::~wstring((char **)&Src);
    v5 = v17 | 0xFF0;
    v64 = v5;
    if ( v105 != -1 )
      std::wstring::~wstring(v104);
    v101 = v112;
    v102 = v113;
    v103 = v114;
    v113 = 0;
    v114 = 7;
    LOWORD(v112) = 0;
    v20 = v3[1];
    if ( v20 == v3[2] )
    {
      std::vector<std::pair<appids::AnyRuntimeApp,std::wstring>>::_Emplace_reallocate<std::pair<appids::AnyRuntimeApp,std::wstring>>(
        v3,
        v3[1],
        &v94);
    }
    else
    {
      std::pair<appids::AnyRuntimeApp,std::wstring>::pair<appids::AnyRuntimeApp,std::wstring>(v20, &v94);
      v3[1] += 112LL;
    }
    std::wstring::~wstring((char **)&v101);
    std::wstring::~wstring((char **)&v99);
    if ( v98 != -1 )
      std::wstring::~wstring((char **)&v95);
    std::wstring::~wstring((char **)&v112);
    std::wstring::~wstring((char **)&v109);
    std::wstring::~wstring((char **)&v85);
    std::wstring::~wstring((char **)&v88);
    std::wstring::~wstring(&v91);
    if ( v11 && _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
    v8 += 4;
  }
  v73 = 0;
  v21 = CoCreateInstance(&rclsid, 0, 1u, &GUID_222eb002_1c9e_515d_9965_e5231a6d4574, &v73);
  v22 = v21;
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_102d4a6ff8d03f8218079dbfbd127e76_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v22);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v70 = 0;
  v23 = v73;
  v24 = *(__int64 (__fastcall **)(LPVOID, PVOID, char **))(*(_QWORD *)v73 + 72LL);
  v70 = 0;
  std::wstring::wstring((__int64)&v88, (__int64)(v72 + 36));
  v26 = (const WCHAR *)&v88;
  if ( v90 > 7 )
    v26 = (const WCHAR *)v88;
  v71 = v26;
  v27 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v115, &v71, v25);
  v28 = v24(v23, v27[1].Reserved.Reserved1, &v70);
  v116 = 0;
  std::wstring::~wstring((char **)&v88);
  if ( v28 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_102d4a6ff8d03f8218079dbfbd127e76_Traceguids,
        (unsigned int)v28);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v81, v28);
    throw (ErrorCodeException *)v81;
  }
  v69 = 0;
  v29 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v70 + 56LL))(v70, &v69);
  v30 = v29;
  if ( v29 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_102d4a6ff8d03f8218079dbfbd127e76_Traceguids,
        (unsigned int)v29);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v82, v30);
    throw (ErrorCodeException *)v82;
  }
  v88 = 0;
  v89 = 0;
  v90 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v88, L"Found {0} Win32 applications", 0x1Cu);
  v31 = (Private::Format *)StringAlgo::FormatString(v104, &v88);
  v32 = Private::Format::operator%<unsigned long>(v31);
  v65 = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v65, v32);
  std::wstring::~wstring(v104);
  v33 = v70;
  v91 = v70;
  v92 = 0;
  v93[0] = 0;
  v65 = 0;
  v34 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v70 + 56LL))(v70, &v65);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v34,
      ppv);
  *(_QWORD *)&Src = v33;
  v35 = v65;
  DWORD2(Src) = v65;
  v107 = 0;
  v36 = v92;
  while ( (_DWORD)v36 != v35 )
  {
    v37 = v91;
    v38 = *(__int64 (__fastcall **)(char *, __int64, __int64 *))(*(_QWORD *)v91 + 48LL);
    v39 = v93[0];
    if ( v93[0] )
    {
      v93[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v36 = v92;
    }
    v40 = v38(v37, v36, v93);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v40,
        ppv);
    v66 = 0;
    string = 0;
    v41 = v93[0];
    v42 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v93[0] + 48LL);
    WindowsDeleteString(0);
    v66 = 0;
    v43 = v42(v41, &v66);
    v44 = v43;
    if ( v43 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          WPP_102d4a6ff8d03f8218079dbfbd127e76_Traceguids,
          (unsigned int)v43);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v84, v44);
      throw (ErrorCodeException *)v84;
    }
    v45 = v93[0];
    v46 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v93[0] + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v47 = v46(v45, &string);
    v48 = v47;
    if ( v47 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_102d4a6ff8d03f8218079dbfbd127e76_Traceguids,
          (unsigned int)v47);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v83, v48);
      throw (ErrorCodeException *)v83;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v66, 0);
    v88 = 0;
    v89 = 0;
    v90 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v88, L"Found a Win32 app: {0}", 0x16u);
    v50 = (Private::Format *)StringAlgo::FormatString(v104, &v88);
    v51 = StringAlgo::ToString(&v115, StringRawBuffer);
    if ( *(_QWORD *)(v51 + 24) > 7u )
      v51 = *(_QWORD *)v51;
    Private::Format::Replace(v50, (const unsigned __int16 *)v51);
    std::wstring::~wstring((char **)&v115);
    LODWORD(v72) = 3;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v72, v50);
    std::wstring::~wstring(v104);
    v52 = WindowsGetStringRawBuffer(string, 0);
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v53 = -1;
    do
      ++v53;
    while ( v52[v53] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v85, v52, v53);
    v88 = 0;
    v89 = 0;
    v90 = 0;
    v54 = -1;
    do
      ++v54;
    while ( StringRawBuffer[v54] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v88, StringRawBuffer, v54);
    v55 = (char **)&v88;
    if ( v90 > 7 )
      v55 = (char **)v88;
    v74 = v55;
    v75 = v89;
    v56 = appids::AnyRuntimeApp::FromPlatformIndependentId(&v109, &v74);
    v94 = *(_DWORD *)v56;
    v98 = -1;
    v57 = *(char *)(v56 + 40) + 1LL;
    if ( *(char *)(v56 + 40) != -1 )
    {
      v96 = 0;
      v97 = 0;
      v95 = 0;
      v95 = *(_OWORD *)(v56 + 8);
      v96 = *(_QWORD *)(v56 + 24);
      v97 = *(_QWORD *)(v56 + 32);
      *(_QWORD *)(v56 + 24) = 0;
      *(_QWORD *)(v56 + 32) = 7;
      *(_WORD *)(v56 + 8) = 0;
      v98 = v57 != 1;
    }
    v99 = 0;
    v100 = 0u;
    v99 = *(_OWORD *)(v56 + 48);
    v100 = *(_OWORD *)(v56 + 64);
    *(_QWORD *)(v56 + 64) = 0;
    *(_QWORD *)(v56 + 72) = 7;
    *(_WORD *)(v56 + 48) = 0;
    v101 = v85;
    v102 = v86;
    v103 = v87;
    v86 = 0;
    v87 = 7;
    LOWORD(v85) = 0;
    v58 = v3[1];
    if ( v58 == v3[2] )
    {
      std::vector<std::pair<appids::AnyRuntimeApp,std::wstring>>::_Emplace_reallocate<std::pair<appids::AnyRuntimeApp,std::wstring>>(
        v3,
        v3[1],
        &v94);
    }
    else
    {
      std::pair<appids::AnyRuntimeApp,std::wstring>::pair<appids::AnyRuntimeApp,std::wstring>(v58, &v94);
      v3[1] += 112LL;
    }
    std::wstring::~wstring((char **)&v101);
    std::wstring::~wstring((char **)&v99);
    if ( v98 != -1 )
      std::wstring::~wstring((char **)&v95);
    std::wstring::~wstring(&v113);
    if ( SBYTE8(v112) != -1 )
      std::wstring::~wstring((char **)&v109 + 1);
    std::wstring::~wstring((char **)&v88);
    std::wstring::~wstring((char **)&v85);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v66);
    v36 = ++v92;
    v35 = v65;
  }
  v59 = v93[0];
  if ( v93[0] )
  {
    v93[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
  }
  if ( v70 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v70 + 16LL))(v70);
  if ( v73 )
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v73 + 16LL))(v73, *(_QWORD *)v73);
  std::vector<std::shared_ptr<wpcplugs::AppRepository::IAppPackageFamily>>::_Tidy(&v77);
  Lazy<IO::Path,Optional>::~Lazy<IO::Path,Optional>((__int64)v79);
  return v3;
}

```

## disassembly

```asm
0x18002dbec  mov     [rsp+arg_10], rbx
0x18002dbf1  push    rsi
0x18002dbf2  push    rdi
0x18002dbf3  push    r12
0x18002dbf5  push    r13
0x18002dbf7  push    r15
0x18002dbf9  sub     rsp, 330h
0x18002dc00  mov     rax, cs:__security_cookie
0x18002dc07  xor     rax, rsp
0x18002dc0a  mov     [rsp+358h+var_38], rax
0x18002dc12  mov     rdi, rdx
0x18002dc15  mov     [rsp+358h+var_2E8], rdx
0x18002dc1a  mov     r12, rcx
0x18002dc1d  mov     [rsp+358h+var_2C8], rcx
0x18002dc25  mov     [rsp+358h+var_2F0], rdx
0x18002dc2a  xor     esi, esi
0x18002dc2c  mov     [rsp+358h+var_328], esi
0x18002dc30  mov     [rcx], rsi
0x18002dc33  mov     [rcx+8], rsi
0x18002dc37  mov     [rcx+10h], rsi
0x18002dc3b  mov     [rsp+358h+var_328], 1
0x18002dc43  lea     r13d, [rsi+20h]
0x18002dc47  mov     ecx, r13d; Size
0x18002dc4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dc4f  mov     [rsp+358h+var_308], rax
0x18002dc54  xorps   xmm0, xmm0
0x18002dc57  movups  xmmword ptr [rax], xmm0
0x18002dc5a  mov     dword ptr [rax+8], 1
0x18002dc61  mov     dword ptr [rax+0Ch], 1
0x18002dc68  lea     rcx, ??_7?$_Ref_count_obj2@VAppRepository@StateRepo@1wpcplugs@@@std@@6B@; const std::_Ref_count_obj2<wpcplugs::AppRepository::StateRepo::AppRepository>::`vftable'
0x18002dc6f  mov     [rax], rcx
0x18002dc72  lea     rcx, [rax+10h]
0x18002dc76  lea     rdx, ??_7AppRepository@StateRepo@0wpcplugs@@6B@; const wpcplugs::AppRepository::StateRepo::AppRepository::`vftable'
0x18002dc7d  mov     [rcx], rdx
0x18002dc80  mov     [rcx+8], sil
0x18002dc84  mov     [rsp+358h+var_2A8], rcx
0x18002dc8c  mov     [rsp+358h+var_2A0], rax
0x18002dc94  lea     ebx, [rsi+7]
0x18002dc97  mov     r15d, ebx
0x18002dc9a  mov     [rsp+358h+var_328], ebx
0x18002dc9e  mov     r8, rdi
0x18002dca1  lea     rdx, [rsp+358h+var_2C0]
0x18002dca9  mov     rax, cs:off_1800AF608
0x18002dcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcb5  nop
0x18002dcb6  xorps   xmm0, xmm0
0x18002dcb9  movups  [rsp+358h+var_1B0], xmm0
0x18002dcc1  mov     [rsp+358h+var_1A0], rsi
0x18002dcc9  mov     [rsp+358h+var_198], rsi
0x18002dcd1  mov     r8d, r13d
0x18002dcd4  lea     rdx, aFound0Installe; "Found {0} installed applications"
0x18002dcdb  lea     rcx, [rsp+358h+var_1B0]
0x18002dce3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002dce8  lea     rdx, [rsp+358h+var_1B0]
0x18002dcf0  lea     rcx, [rsp+358h+var_F8]
0x18002dcf8  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002dcfd  mov     rcx, rax; this
0x18002dd00  mov     rax, [rsp+358h+var_2B8]
0x18002dd08  sub     rax, [rsp+358h+var_2C0]
0x18002dd10  sar     rax, 4
0x18002dd14  mov     [rsp+358h+var_318], rax
0x18002dd19  lea     rdx, [rsp+358h+var_318]
0x18002dd1e  call    ??$?L_K@Format@Private@@QEAAAEAV01@AEB_K@Z; Private::Format::operator%<unsigned __int64>(unsigned __int64 const &)
0x18002dd23  mov     [rsp+358h+var_320], 2
0x18002dd2b  mov     rdx, rax
0x18002dd2e  lea     rcx, [rsp+358h+var_320]
0x18002dd33  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002dd38  nop
0x18002dd39  lea     rcx, [rsp+358h+var_F8]
0x18002dd41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dd46  mov     r13, [rsp+358h+var_2C0]
0x18002dd4e  mov     rcx, [rsp+358h+var_2B8]
0x18002dd56  mov     [rsp+358h+string], rcx
0x18002dd5b  mov     [rsp+358h+var_318], r13
0x18002dd60  cmp     r13, rcx
0x18002dd63  jz      loc_18002E260
0x18002dd69  mov     rax, [r13+8]
0x18002dd6d  test    rax, rax
0x18002dd70  jz      short loc_18002DD76
0x18002dd72  lock inc dword ptr [rax+8]
0x18002dd76  mov     rcx, [r13+0]
0x18002dd7a  mov     [rsp+358h+var_308], rcx
0x18002dd7f  mov     [rsp+358h+var_2D8], rcx
0x18002dd87  mov     rdi, [r13+8]
0x18002dd8b  mov     [rsp+358h+var_2D0], rdi
0x18002dd93  mov     rax, [rcx]
0x18002dd96  lea     rdx, [rsp+358h+var_190]
0x18002dd9e  mov     rax, [rax+8]
0x18002dda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda7  nop
0x18002dda8  xorps   xmm0, xmm0
0x18002ddab  movups  [rsp+358h+var_1D0], xmm0
0x18002ddb3  mov     [rsp+358h+var_1C0], rsi
0x18002ddbb  mov     [rsp+358h+var_1B8], rsi
0x18002ddc3  mov     r8d, 18h
0x18002ddc9  lea     rdx, aFoundInstalled; "Found installed app: {0}"
0x18002ddd0  lea     rcx, [rsp+358h+var_1D0]
0x18002ddd8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002dddd  lea     rdx, [rsp+358h+var_1D0]
0x18002dde5  lea     rcx, [rsp+358h+var_F8]
0x18002dded  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18002ddf2  nop
0x18002ddf3  lea     rdx, [rsp+358h+var_190]
0x18002ddfb  mov     rcx, rax; this
0x18002ddfe  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18002de03  mov     [rsp+358h+var_320], 3
0x18002de0b  mov     rdx, rax
0x18002de0e  lea     rcx, [rsp+358h+var_320]
0x18002de13  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18002de18  nop
0x18002de19  lea     rcx, [rsp+358h+var_F8]
0x18002de21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002de26  xorps   xmm0, xmm0
0x18002de29  movups  [rsp+358h+var_1B0], xmm0
0x18002de31  mov     [rsp+358h+var_1A0], rsi
0x18002de39  mov     [rsp+358h+var_198], rbx
0x18002de41  mov     word ptr [rsp+358h+var_1B0], si
0x18002de49  mov     rcx, [rsp+358h+var_308]
0x18002de4e  mov     rax, [rcx]
0x18002de51  lea     rdx, [rsp+358h+var_1D0]
0x18002de59  mov     rax, [rax+10h]
0x18002de5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de62  mov     rdx, rax
0x18002de65  lea     rcx, [rsp+358h+var_1B0]
0x18002de6d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002de72  lea     rcx, [rsp+358h+var_1D0]
0x18002de7a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002de7f  nop
0x18002de80  jmp     short loc_18002DEA8
0x18002de82  xor     esi, esi
0x18002de84  mov     r13, [rsp+358h+var_318]
0x18002de89  mov     rdi, [rsp+358h+var_2D0]
0x18002de91  mov     r15d, [rsp+358h+var_328]
0x18002de96  mov     r12, [rsp+358h+var_2C8]
0x18002de9e  mov     rax, [rsp+358h+var_2F0]
0x18002dea3  mov     [rsp+358h+var_2E8], rax
0x18002dea8  lea     rdx, [rsp+358h+var_190]
0x18002deb0  lea     rcx, [rsp+358h+var_58]
0x18002deb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002debd  mov     rbx, rax
0x18002dec0  mov     [rsp+358h+var_308], rax
0x18002dec5  mov     rdx, rax
0x18002dec8  lea     rcx, [rsp+358h+Src]
0x18002ded0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ded5  mov     rdx, rax
0x18002ded8  lea     rcx, [rsp+358h+var_1D0]
0x18002dee0  call    ??$ToLower@G@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@Z; StringAlgo::ToLower<ushort>(std::wstring)
0x18002dee5  nop
0x18002dee6  mov     rcx, rbx
0x18002dee9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002deee  nop
0x18002deef  xorps   xmm0, xmm0
0x18002def2  movups  [rsp+358h+var_A8], xmm0
0x18002defa  movzx   eax, word ptr [rsp+358h+var_1D0]
0x18002df02  mov     word ptr [rsp+358h+var_A8], ax
0x18002df0a  movsd   xmm0, qword ptr [rsp+358h+var_1D0+2]
0x18002df13  movsd   qword ptr [rsp+358h+var_A8+2], xmm0
0x18002df1c  mov     eax, dword ptr [rsp+358h+var_1D0+0Ah]
0x18002df23  mov     dword ptr [rsp+358h+var_A8+0Ah], eax
0x18002df2a  movzx   eax, word ptr [rsp+358h+var_1D0+0Eh]
0x18002df32  mov     word ptr [rsp+358h+var_A8+0Eh], ax
0x18002df3a  mov     rax, [rsp+358h+var_1C0]
0x18002df42  mov     [rsp+358h+var_98], rax
0x18002df4a  mov     rax, [rsp+358h+var_1B8]
0x18002df52  mov     [rsp+358h+var_90], rax
0x18002df5a  mov     [rsp+358h+var_1C0], rsi
0x18002df62  mov     ebx, 7
0x18002df67  mov     [rsp+358h+var_1B8], rbx
0x18002df6f  mov     word ptr [rsp+358h+var_1D0], si
0x18002df77  lea     rdx, [rsp+358h+var_1B0]
0x18002df7f  lea     rcx, [rsp+358h+var_88]
0x18002df87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002df8c  nop
0x18002df8d  or      r15d, 8
0x18002df91  mov     [rsp+358h+var_328], r15d
0x18002df96  lea     rax, [rsp+358h+var_168]
0x18002df9e  mov     [rsp+358h+var_308], rax
0x18002dfa3  lea     rdx, [rsp+358h+var_A8]
0x18002dfab  lea     rcx, [rsp+358h+var_F8]
0x18002dfb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dfb8  mov     [rsp+358h+var_D8], sil
0x18002dfc0  mov     [rsp+358h+var_168], esi
0x18002dfc7  lea     rcx, [rsp+358h+var_F8]
0x18002dfcf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dfd4  lea     rdx, [rsp+358h+var_A8]
0x18002dfdc  lea     rcx, [rsp+358h+var_160]
0x18002dfe4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dfe9  mov     [rsp+358h+var_140], sil
0x18002dff1  lea     rdx, [rsp+358h+var_A8]
0x18002dff9  lea     rcx, [rsp+358h+var_F8]
0x18002e001  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002e006  mov     [rsp+358h+var_D8], sil
0x18002e00e  xorps   xmm0, xmm0
0x18002e011  movups  [rsp+358h+Src], xmm0
0x18002e019  mov     [rsp+358h+var_C0], rsi
0x18002e021  mov     [rsp+358h+var_B8], rsi
0x18002e029  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e02d  lea     rax, aAppx_0; "appx:"
0x18002e034  inc     r8
0x18002e037  cmp     [rax+r8*2], si
0x18002e03c  jnz     short loc_18002E034
0x18002e03e  mov     rdx, rax
0x18002e041  lea     rcx, [rsp+358h+Src]
0x18002e049  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002e04e  nop
0x18002e04f  lea     rdx, [rsp+358h+var_F8]
0x18002e057  lea     rcx, [rsp+358h+Src]; Src
0x18002e05f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002e064  xorps   xmm0, xmm0
0x18002e067  movups  [rsp+358h+var_138], xmm0
0x18002e06f  mov     qword ptr [rsp+358h+var_128], rsi
0x18002e077  mov     qword ptr [rsp+358h+var_128+8], rsi
0x18002e07f  movups  xmm0, xmmword ptr [rax]
0x18002e082  movaps  [rsp+358h+var_138], xmm0
0x18002e08a  movups  xmm1, xmmword ptr [rax+10h]
0x18002e08e  movaps  [rsp+358h+var_128], xmm1
0x18002e096  mov     [rax+10h], rsi
0x18002e09a  mov     [rax+18h], rbx
0x18002e09e  mov     [rax], si
0x18002e0a1  or      r15d, 0C00h
0x18002e0a8  lea     rcx, [rsp+358h+Src]
0x18002e0b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e0b5  or      r15d, 380h
0x18002e0bc  or      r15d, 70h
0x18002e0c0  mov     [rsp+358h+var_328], r15d
0x18002e0c5  movsx   rax, [rsp+358h+var_D8]
0x18002e0ce  add     rax, 1
0x18002e0d2  jz      short loc_18002E0E2
0x18002e0d4  lea     rcx, [rsp+358h+var_F8]
0x18002e0dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e0e1  nop
0x18002e0e2  xorps   xmm0, xmm0
0x18002e0e5  movups  [rsp+358h+var_118], xmm0
0x18002e0ed  movzx   eax, [rsp+358h+var_88]
0x18002e0f5  mov     word ptr [rsp+358h+var_118], ax
0x18002e0fd  movsd   xmm0, [rsp+358h+var_86]
0x18002e106  movsd   qword ptr [rsp+358h+var_118+2], xmm0
0x18002e10f  mov     eax, [rsp+358h+var_7E]
0x18002e116  mov     dword ptr [rsp+358h+var_118+0Ah], eax
0x18002e11d  movzx   eax, [rsp+358h+var_7A]
0x18002e125  mov     word ptr [rsp+358h+var_118+0Eh], ax
0x18002e12d  mov     rax, [rsp+358h+var_78]
0x18002e135  mov     [rsp+358h+var_108], rax
0x18002e13d  mov     rax, [rsp+358h+var_70]
0x18002e145  mov     [rsp+358h+var_100], rax
0x18002e14d  mov     [rsp+358h+var_78], rsi
0x18002e155  mov     [rsp+358h+var_70], rbx
0x18002e15d  mov     [rsp+358h+var_88], si
0x18002e165  mov     rcx, [r12+8]
0x18002e16a  cmp     rcx, [r12+10h]
0x18002e16f  jz      short loc_18002E186
0x18002e171  lea     rdx, [rsp+358h+var_168]
0x18002e179  call    ??0?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@$$QEAU01@@Z; std::pair<appids::AnyRuntimeApp,std::wstring>::pair<appids::AnyRuntimeApp,std::wstring>(std::pair<appids::AnyRuntimeApp,std::wstring> &&)
0x18002e17e  add     qword ptr [r12+8], 70h ; 'p'
0x18002e184  jmp     short loc_18002E19A
0x18002e186  lea     r8, [rsp+358h+var_168]
0x18002e18e  mov     rdx, rcx
0x18002e191  mov     rcx, r12
0x18002e194  call    ??$_Emplace_reallocate@U?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$vector@U?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$allocator@U?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@VAnyRuntimeApp@appids@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<appids::AnyRuntimeApp,std::wstring>>::_Emplace_reallocate<std::pair<appids::AnyRuntimeApp,std::wstring>>(std::pair<appids::AnyRuntimeApp,std::wstring> * const,std::pair<appids::AnyRuntimeApp,std::wstring> &&)
0x18002e199  nop
0x18002e19a  lea     rcx, [rsp+358h+var_118]
0x18002e1a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1a7  lea     rcx, [rsp+358h+var_138]
0x18002e1af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1b4  movsx   rax, [rsp+358h+var_140]
0x18002e1bd  add     rax, 1
0x18002e1c1  jz      short loc_18002E1D1
0x18002e1c3  lea     rcx, [rsp+358h+var_160]
0x18002e1cb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1d0  nop
0x18002e1d1  lea     rcx, [rsp+358h+var_88]
0x18002e1d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1de  lea     rcx, [rsp+358h+var_A8]
0x18002e1e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1eb  nop
0x18002e1ec  lea     rcx, [rsp+358h+var_1D0]
0x18002e1f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e1f9  nop
0x18002e1fa  lea     rcx, [rsp+358h+var_1B0]
0x18002e202  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e207  nop
0x18002e208  lea     rcx, [rsp+358h+var_190]
0x18002e210  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002e215  nop
0x18002e216  test    rdi, rdi
0x18002e219  jz      short loc_18002E252
0x18002e21b  or      eax, 0FFFFFFFFh
0x18002e21e  lock xadd [rdi+8], eax
0x18002e223  cmp     eax, 1
0x18002e226  jnz     short loc_18002E252
0x18002e228  mov     rax, [rdi]
0x18002e22b  mov     rcx, rdi
0x18002e22e  mov     rax, [rax]
0x18002e231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e236  or      eax, 0FFFFFFFFh
0x18002e239  lock xadd [rdi+0Ch], eax
0x18002e23e  cmp     eax, 1
0x18002e241  jnz     short loc_18002E252
0x18002e243  mov     rax, [rdi]
0x18002e246  mov     rcx, rdi
  ... truncated ...
```
