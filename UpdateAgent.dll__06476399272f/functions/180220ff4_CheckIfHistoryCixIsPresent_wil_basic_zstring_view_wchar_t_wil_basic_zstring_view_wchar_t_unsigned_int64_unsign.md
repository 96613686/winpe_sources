# CheckIfHistoryCixIsPresent(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180220ff4`
- end: `0x180221bfc`
- name: `?CheckIfHistoryCixIsPresent@@YAJV?$basic_zstring_view@_W@wil@@0PEA_K11@Z`
- size: `3080`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f0b0`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006a18`
- `0x180008af0`
- `0x180008ed8`
- `0x18000998c`
- `0x180010af4`
- `0x180012b84`
- `0x180012ca0`
- `0x180012d94`
- `0x180023ab0`
- `0x180023b20`
- `0x180025650`
- `0x18007a13c`
- `0x180094d0c`
- `0x180094d2c`
- `0x18009b6b0`
- `0x18009b6cc`
- `0x18010daa0`
- `0x1801df624`
- `0x1801dfc4c`
- `0x1801e1000`
- `0x1801ea940`
- `0x1801f250c`
- `0x180218fbc`
- `0x180220e44`
- `0x180220ff4`
- `0x180221c04`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022182c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022185b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022187f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802218a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802218f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802219ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221aa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022182c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022185b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022187f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802218a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802218f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022193a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802219ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221aa0`
- `WIMGAPI!WIMCloseHandle` at `0x18022181c`
- `WIMGAPI!WIMCloseHandle` at `0x18022184b`
- `WIMGAPI!WIMCloseHandle` at `0x18022186f`
- `WIMGAPI!WIMCloseHandle` at `0x180221893`
- `WIMGAPI!WIMCloseHandle` at `0x1802218e2`
- `WIMGAPI!WIMCloseHandle` at `0x180221906`
- `WIMGAPI!WIMCloseHandle` at `0x18022192a`
- `WIMGAPI!WIMCloseHandle` at `0x18022181c`
- `WIMGAPI!WIMCloseHandle` at `0x18022184b`
- `WIMGAPI!WIMCloseHandle` at `0x18022186f`
- `WIMGAPI!WIMCloseHandle` at `0x180221893`
- `WIMGAPI!WIMCloseHandle` at `0x1802218e2`
- `WIMGAPI!WIMCloseHandle` at `0x180221906`
- `WIMGAPI!WIMCloseHandle` at `0x18022192a`

## string_xrefs

- `0x1802214ee`: `express.psf.cix.xml`
- `0x18022157d`: `express.psf.cix.xml`
- `0x1802219b3`: `Failed to open {}`
- `0x18022131d`: `WIMSetTemporaryPath`
- `0x18022128c`: `WIMCreateFile`
- `0x180221a08`: `Failed to open image from {}`
- `0x18022147d`: `history.cix.xml`
- `0x18022153e`: `WIMCreateImageFile`
- `0x180221608`: `WIMReadImageFile`
- `0x180221aba`: `Failed to open express CIX from {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall CheckIfHistoryCixIsPresent(
        _QWORD *a1,
        _QWORD *a2,
        struct std::nothrow_t *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  const char *v7; // r9
  __int128 *p_Src; // rax
  __int64 result; // rax
  __int128 *v10; // rax
  __int64 (__fastcall *FnInternal)(_QWORD, __int64, __int64); // rbx
  __int64 v12; // rsi
  unsigned int (__fastcall *v13)(__int64, _QWORD); // rbx
  const char *v14; // r9
  __int64 (__fastcall *v15)(__int64, __int64); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, const wchar_t *, _BYTE *); // rbx
  __int64 v18; // rax
  __int64 (__fastcall *v19)(__int64, const wchar_t *, _BYTE *); // rbx
  __int64 v20; // r12
  __int64 (__fastcall *v21)(__int64, const wchar_t *, __int64, __int64); // rbx
  __int64 v22; // r14
  int v23; // eax
  unsigned int (__fastcall *v24)(__int64, __int64, _QWORD, unsigned int *); // rbx
  const char *v25; // r9
  int v26; // eax
  unsigned int v27; // r8d
  wil::details::in1diag3 *v28; // rcx
  _QWORD *v29; // rbx
  _QWORD *i; // rbx
  int v31; // eax
  __int64 *v32; // rcx
  __int64 v33; // rcx
  struct std::nothrow_t *v34; // rdx
  __int64 v35; // rcx
  DWORD LastError; // ebx
  __int64 v37; // rcx
  DWORD v38; // ebx
  __int64 v39; // rcx
  DWORD v40; // ebx
  unsigned int v41; // eax
  __int64 v42; // rcx
  DWORD v43; // ebx
  unsigned int v44; // eax
  unsigned int v45; // [rsp+20h] [rbp-498h]
  unsigned int v46; // [rsp+20h] [rbp-498h]
  int *v47; // [rsp+20h] [rbp-498h]
  __int128 v48; // [rsp+40h] [rbp-478h] BYREF
  __int128 v49; // [rsp+50h] [rbp-468h]
  int v50; // [rsp+60h] [rbp-458h] BYREF
  __int128 v51; // [rsp+68h] [rbp-450h] BYREF
  __int128 v52; // [rsp+78h] [rbp-440h]
  __int64 v53; // [rsp+88h] [rbp-430h]
  __int64 v54; // [rsp+90h] [rbp-428h]
  __int64 v55; // [rsp+98h] [rbp-420h]
  struct std::nothrow_t *v56; // [rsp+A0h] [rbp-418h]
  _QWORD *v57; // [rsp+A8h] [rbp-410h]
  _QWORD *v58; // [rsp+B0h] [rbp-408h]
  __int64 v59; // [rsp+B8h] [rbp-400h]
  int v60; // [rsp+C0h] [rbp-3F8h]
  unsigned int v61; // [rsp+C4h] [rbp-3F4h] BYREF
  __int128 Src; // [rsp+C8h] [rbp-3F0h] BYREF
  __int128 v63; // [rsp+D8h] [rbp-3E0h]
  __int128 v64; // [rsp+E8h] [rbp-3D0h] BYREF
  __int64 v65; // [rsp+F8h] [rbp-3C0h]
  void **v66; // [rsp+100h] [rbp-3B8h] BYREF
  __int64 v67; // [rsp+108h] [rbp-3B0h]
  __int64 v68; // [rsp+110h] [rbp-3A8h]
  _QWORD v69[4]; // [rsp+118h] [rbp-3A0h] BYREF
  void *v70; // [rsp+138h] [rbp-380h]
  _BYTE v71[112]; // [rsp+140h] [rbp-378h] BYREF
  int v72[4]; // [rsp+1B0h] [rbp-308h] BYREF
  __int128 v73; // [rsp+1C0h] [rbp-2F8h]
  _BYTE v74[28]; // [rsp+1D0h] [rbp-2E8h] BYREF
  int v75; // [rsp+1ECh] [rbp-2CCh]
  unsigned int v76; // [rsp+1F0h] [rbp-2C8h]
  __int128 v77; // [rsp+420h] [rbp-98h]
  __int64 v78; // [rsp+430h] [rbp-88h]
  __int128 v79; // [rsp+438h] [rbp-80h]
  __int128 v80; // [rsp+448h] [rbp-70h]
  __int128 v81; // [rsp+458h] [rbp-60h]
  __int64 v82; // [rsp+468h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v59 = -2;
  v57 = a4;
  v56 = a3;
  v58 = a5;
  if ( a3 )
    *(_QWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoFix>::__private_IsEnabled() )
    {
      Src = 0;
      v63 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&Src);
      v48 = 0;
      v49 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v48);
      v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v51);
      ReplaceAll<std::wstring>(&Src);
      std::wstring::~wstring(&v51);
      std::wstring::~wstring(&v48);
      p_Src = &Src;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        p_Src = (__int128 *)Src;
      *(_QWORD *)&v51 = p_Src;
      *((_QWORD *)&v51 + 1) = v63;
      if ( (unsigned __int8)FileExists(&v51) )
        goto LABEL_12;
      std::wstring::_Assign<wchar_t>(&Src, *a1, a1[1]);
      v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v51);
      v48 = 0;
      v49 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v48);
      ReplaceAll<std::wstring>(&Src);
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v51);
      v10 = &Src;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v10 = (__int128 *)Src;
      *(_QWORD *)&v51 = v10;
      *((_QWORD *)&v51 + 1) = v63;
      if ( (unsigned __int8)FileExists(&v51) )
      {
LABEL_12:
        std::wstring::~wstring(&Src);
        result = 0;
      }
      else
      {
        WimgapiLoader::WimgapiLoader((WimgapiLoader *)v71);
        v60 = 0;
        v54 = 0;
        v48 = 0;
        v49 = 0;
        std::string::_Construct<1,char const *>(&v48, "WIMCreateFile", 13);
        FnInternal = (__int64 (__fastcall *)(_QWORD, __int64, __int64))DllLoader::GetFnInternal(v71, &v48);
        std::string::~string(&v48);
        v45 = 0;
        v12 = FnInternal(*a1, 0x80000000LL, 3);
        v54 = v12;
        if ( !v12 )
        {
          LastError = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
            LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(v35, 3, "Failed to open {}", a1, 0);
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
            (const char *)LastError,
            v45);
        }
        EnsureDirectoryExistsHr((__int64)a2);
        v48 = 0;
        v49 = 0;
        std::string::_Construct<1,char const *>(&v48, "WIMSetTemporaryPath", 19);
        v13 = (unsigned int (__fastcall *)(__int64, _QWORD))DllLoader::GetFnInternal(v71, &v48);
        std::string::~string(&v48);
        if ( !v13(v12, *a2) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x52,
            (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
            v14);
        v55 = 0;
        v48 = 0;
        v49 = 0;
        std::string::_Construct<1,char const *>(&v48, "WIMLoadImage", 12);
        v15 = (__int64 (__fastcall *)(__int64, __int64))DllLoader::GetFnInternal(v71, &v48);
        std::string::~string(&v48);
        v16 = v15(v12, 1);
        v55 = v16;
        if ( !v16 )
        {
          v38 = GetLastError();
          if ( *(_QWORD *)&LogAdapter::g_Logger )
            LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(v37, 3, "Failed to open image from {}", a1, 0);
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
            (const char *)v38,
            v45);
        }
        memset_0(v74, 0, 0x250u);
        v77 = 0;
        v78 = 0;
        v79 = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v53 = 0;
        v48 = 0;
        v49 = 0;
        std::string::_Construct<1,char const *>(&v48, "WIMFindFirstImageFile", 21);
        v17 = (__int64 (__fastcall *)(__int64, const wchar_t *, _BYTE *))DllLoader::GetFnInternal(v71, &v48);
        std::string::~string(&v48);
        v18 = v17(v16, L"history.cix.xml", v74);
        v53 = v18;
        if ( v18 )
        {
          if ( !(unsigned int)WIMCloseHandle(v18) )
          {
            GetLastError();
            __fastfail(7u);
          }
          if ( !(unsigned int)WIMCloseHandle(v16) )
          {
            GetLastError();
            __fastfail(7u);
          }
          if ( !(unsigned int)WIMCloseHandle(v12) )
          {
            GetLastError();
            __fastfail(7u);
          }
        }
        else
        {
          v48 = 0;
          v49 = 0;
          std::string::_Construct<1,char const *>(&v48, "WIMFindFirstImageFile", 21);
          v19 = (__int64 (__fastcall *)(__int64, const wchar_t *, _BYTE *))DllLoader::GetFnInternal(v71, &v48);
          std::string::~string(&v48);
          v20 = v19(v16, L"express.psf.cix.xml", v74);
          v53 = v20;
          if ( !v20 )
          {
            v40 = GetLastError();
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(
                v39,
                3,
                "Failed to find express CIX from {}",
                a1,
                0);
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x64,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)v40,
              v45);
          }
          if ( v75 )
          {
            v41 = EnsureNTSTATUS<long>(2147942487LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x65,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)v41,
              0);
          }
          *(_QWORD *)&v51 = 0;
          v48 = 0;
          v49 = 0;
          std::string::_Construct<1,char const *>(&v48, "WIMCreateImageFile", 18);
          v21 = (__int64 (__fastcall *)(__int64, const wchar_t *, __int64, __int64))DllLoader::GetFnInternal(v71, &v48);
          std::string::~string(&v48);
          v46 = 0;
          v22 = v21(v16, L"express.psf.cix.xml", 0x80000000LL, 3);
          *(_QWORD *)&v51 = v22;
          if ( !v22 )
          {
            v43 = GetLastError();
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(
                v42,
                3,
                "Failed to open express CIX from {}",
                a1,
                0);
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x6A,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)v43,
              v46);
          }
          v64 = 0;
          v65 = 0;
          v23 = RtlAllocateLBlob(v76, &v64);
          if ( v23 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x6D,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)(unsigned int)v23,
              0);
          v61 = 0;
          *(_OWORD *)v72 = 0;
          v73 = 0;
          v48 = 0;
          v49 = 0;
          std::string::_Construct<1,char const *>(&v48, "WIMReadImageFile", 16);
          v24 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))DllLoader::GetFnInternal(
                                                                                         v71,
                                                                                         &v48);
          std::string::~string(&v48);
          v47 = v72;
          if ( !v24(v22, v65, DWORD2(v64), &v61) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x72,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              v25);
          *(_QWORD *)&v64 = v61;
          v67 = 0;
          v66 = &XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::`vftable';
          v68 = 1024;
          v69[1] = 0;
          v69[0] = &Windows::Rtl::BlockPool::`vftable';
          v69[3] = 0;
          v69[2] = 1024;
          v70 = 0;
          v26 = XmlParserGenerator::AutoXpgParser<XmlParserGenerator::ERROR_CODE_STYLE_HRESULT,CiXParser::CiXDocument,1024>::ParseFromBlob(
                  &v66,
                  0,
                  &v64,
                  &CParseErrorCallback::s_Instance);
          v28 = retaddr;
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7A,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)(unsigned int)v26,
              (int)v72);
          v29 = *(_QWORD **)(v67 + 96);
          if ( !v29 )
          {
            v44 = EnsureNTSTATUS<long>(2147942487LL);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x7B,
              (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
              (const char *)v44,
              (int)v72);
          }
          for ( i = (_QWORD *)*v29; ; i = (_QWORD *)i[11] )
          {
            if ( !i )
            {
              if ( *(_QWORD *)&LogAdapter::g_Logger )
                LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(
                  v28,
                  3,
                  "Failed to find historycix.cab in {}",
                  a1,
                  v72);
              wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x84, v27, (const char *)0xC0000225LL, (int)v47);
            }
            v28 = (wil::details::in1diag3 *)(i + 1);
            if ( i[1] == 14 )
            {
              v50 = 0;
              v31 = Windows::StringUtil::Rtl::CompareStringsByOrdinalCaseInvariant<_LUTF8_STRING,_LUTF8_STRING>(
                      v28,
                      &___LiteralObject__2U__BaseLiteralBuffer__0P_U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0GI__0GJ__0HD__0HE__0GP__0HC__0HJ__0GD__0GJ__0HI__0CO__0GD__0GB__0GC__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__0M__0N__0O__Details_RtlStringLiterals__3U_LUTF8_STRING__B,
                      &v50);
              v27 = 0;
              if ( v50 || (LOBYTE(v28) = 1, v31 < 0) )
                LOBYTE(v28) = 0;
              if ( v31 < 0 )
                wil::details::in1diag3::_Throw_NtStatus(
                  retaddr,
                  (void *)0x159,
                  (unsigned int)"OneCore\\Private\\Base\\inc\\rtlexstringutil.h",
                  (const char *)(unsigned int)v31,
                  (int)v72);
              if ( (_BYTE)v28 )
                break;
            }
          }
          if ( i[10] != 1 )
          {
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(
                v28,
                3,
                "Invalid historycix.cab entry in {}",
                a1,
                v72);
            wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x85, v27, (const char *)0xC00000BBLL, (int)v47);
          }
          v32 = (__int64 *)i[9];
          if ( v32[1] != 1 )
          {
            if ( *(_QWORD *)&LogAdapter::g_Logger )
              LogAdapter::Logger::Log<wil::basic_zstring_view<wchar_t>>(
                v32,
                3,
                "Invalid historycix.cab entry in {}",
                a1,
                v72);
            wil::details::in1diag3::Throw_NtStatus(retaddr, (void *)0x86, v27, (const char *)0xC00000BBLL, (int)v47);
          }
          v33 = *v32;
          v34 = v56;
          *(_QWORD *)v56 = *(_QWORD *)(v33 + 32);
          *v57 = *(_QWORD *)(v33 + 40);
          *v58 = i[4];
          if ( v70 )
          {
            operator delete(v70, v34);
            v70 = 0;
          }
          Windows::Rtl::BlockPool::~BlockPool((Windows::Rtl::BlockPool *)v69);
          if ( v65 )
          {
            anonymous_namespace_::OurRtlFreeStringRoutine(v65);
            v64 = 0;
            v65 = 0;
          }
          if ( !(unsigned int)WIMCloseHandle(v22) )
          {
            GetLastError();
            __fastfail(7u);
          }
          if ( !(unsigned int)WIMCloseHandle(v20) )
          {
            GetLastError();
            __fastfail(7u);
          }
          if ( !(unsigned int)WIMCloseHandle(v16) )
          {
            GetLastError();
            __fastfail(7u);
          }
          if ( !(unsigned int)WIMCloseHandle(v12) )
          {
            GetLastError();
            __fastfail(7u);
          }
        }
        DllLoader::~DllLoader((DllLoader *)v71);
        std::wstring::~wstring(&Src);
        result = 0;
      }
    }
    else
    {
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8F,
                           (unsigned int)"onecore\\base\\servicing\\expander\\lib\\helpers.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x180220ff4  push    rbx
0x180220ff6  push    rsi
0x180220ff7  push    rdi
0x180220ff8  push    r12
0x180220ffa  push    r13
0x180220ffc  push    r14
0x180220ffe  push    r15
0x180221000  sub     rsp, 480h
0x180221007  mov     [rsp+4B8h+var_400], 0FFFFFFFFFFFFFFFEh
0x180221013  mov     rax, cs:__security_cookie
0x18022101a  xor     rax, rsp
0x18022101d  mov     [rsp+4B8h+var_48], rax
0x180221025  mov     [rsp+4B8h+var_410], r9
0x18022102d  mov     rax, r8
0x180221030  mov     [rsp+4B8h+var_418], rax
0x180221038  mov     rdi, rdx
0x18022103b  mov     r13, rcx
0x18022103e  mov     rcx, [rsp+4B8h+arg_20]
0x180221046  mov     [rsp+4B8h+var_408], rcx
0x18022104e  xor     r15d, r15d
0x180221051  test    rax, rax
0x180221054  jz      short loc_180221059
0x180221056  mov     [r8], r15
0x180221059  test    r9, r9
0x18022105c  jz      short loc_180221061
0x18022105e  mov     [r9], r15
0x180221061  test    rcx, rcx
0x180221064  jz      short loc_180221069
0x180221066  mov     [rcx], r15
0x180221069  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoFix> `wil::Feature<__WilFeatureTraits_Feature_AutoFix>::GetImpl(void)'::`2'::impl
0x180221070  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoFix>::__private_IsEnabled(void)
0x180221075  test    al, al
0x180221077  jz      loc_18022196A
0x18022107d  xorps   xmm0, xmm0
0x180221080  movups  [rsp+4B8h+Src], xmm0
0x180221088  xorps   xmm1, xmm1
0x18022108b  movdqu  [rsp+4B8h+var_3E0], xmm1
0x180221094  mov     r8, [r13+8]
0x180221098  mov     rdx, [r13+0]
0x18022109c  lea     rcx, [rsp+4B8h+Src]
0x1802210a4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1802210a9  nop
0x1802210aa  xorps   xmm0, xmm0
0x1802210ad  movups  [rsp+4B8h+var_478], xmm0
0x1802210b2  xorps   xmm1, xmm1
0x1802210b5  movdqu  [rsp+4B8h+var_468], xmm1
0x1802210bb  mov     r8d, 0Fh
0x1802210c1  lea     rdx, aHistorycixCab; ".historycix.cab"
0x1802210c8  lea     rcx, [rsp+4B8h+var_478]
0x1802210cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1802210d2  nop
0x1802210d3  xorps   xmm0, xmm0
0x1802210d6  movups  [rsp+4B8h+var_450], xmm0
0x1802210db  xorps   xmm1, xmm1
0x1802210de  movdqu  [rsp+4B8h+var_440], xmm1
0x1802210e4  mov     ebx, 4
0x1802210e9  mov     r8d, ebx
0x1802210ec  lea     rdx, aWim; ".wim"
0x1802210f3  lea     rcx, [rsp+4B8h+var_450]
0x1802210f8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1802210fd  nop
0x1802210fe  lea     r8, [rsp+4B8h+var_478]
0x180221103  lea     rdx, [rsp+4B8h+var_450]
0x180221108  lea     rcx, [rsp+4B8h+Src]; Src
0x180221110  call    ??$ReplaceAll@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV01@1@Z; ReplaceAll<std::wstring>(std::wstring &,std::wstring const &,std::wstring const &)
0x180221115  nop
0x180221116  lea     rcx, [rsp+4B8h+var_450]; void *
0x18022111b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180221120  nop
0x180221121  lea     rcx, [rsp+4B8h+var_478]; void *
0x180221126  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18022112b  mov     rcx, qword ptr [rsp+4B8h+var_3E0]
0x180221133  lea     rax, [rsp+4B8h+Src]
0x18022113b  lea     r12d, [rbx+3]
0x18022113f  cmp     qword ptr [rsp+4B8h+var_3E0+8], r12
0x180221147  cmova   rax, qword ptr [rsp+4B8h+Src]
0x180221150  mov     qword ptr [rsp+4B8h+var_450], rax
0x180221155  mov     qword ptr [rsp+4B8h+var_450+8], rcx
0x18022115a  lea     rcx, [rsp+4B8h+var_450]
0x18022115f  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x180221164  test    al, al
0x180221166  jz      short loc_18022117C
0x180221168  lea     rcx, [rsp+4B8h+Src]; void *
0x180221170  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180221175  xor     eax, eax
0x180221177  jmp     loc_180221975
0x18022117c  mov     r8, [r13+8]
0x180221180  mov     rdx, [r13+0]
0x180221184  lea     rcx, [rsp+4B8h+Src]
0x18022118c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180221191  xorps   xmm0, xmm0
0x180221194  movups  [rsp+4B8h+var_450], xmm0
0x180221199  xorps   xmm1, xmm1
0x18022119c  movdqu  [rsp+4B8h+var_440], xmm1
0x1802211a2  mov     r8, rbx
0x1802211a5  lea     rdx, aPsf; ".psf"
0x1802211ac  lea     rcx, [rsp+4B8h+var_450]
0x1802211b1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1802211b6  nop
0x1802211b7  xorps   xmm0, xmm0
0x1802211ba  movups  [rsp+4B8h+var_478], xmm0
0x1802211bf  xorps   xmm1, xmm1
0x1802211c2  movdqu  [rsp+4B8h+var_468], xmm1
0x1802211c8  mov     r8, rbx
0x1802211cb  lea     rdx, aWim; ".wim"
0x1802211d2  lea     rcx, [rsp+4B8h+var_478]
0x1802211d7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1802211dc  nop
0x1802211dd  lea     r8, [rsp+4B8h+var_450]
0x1802211e2  lea     rdx, [rsp+4B8h+var_478]
0x1802211e7  lea     rcx, [rsp+4B8h+Src]; Src
0x1802211ef  call    ??$ReplaceAll@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@YA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV01@1@Z; ReplaceAll<std::wstring>(std::wstring &,std::wstring const &,std::wstring const &)
0x1802211f4  nop
0x1802211f5  lea     rcx, [rsp+4B8h+var_478]; void *
0x1802211fa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802211ff  nop
0x180221200  lea     rcx, [rsp+4B8h+var_450]; void *
0x180221205  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18022120a  mov     rcx, qword ptr [rsp+4B8h+var_3E0]
0x180221212  lea     rax, [rsp+4B8h+Src]
0x18022121a  cmp     qword ptr [rsp+4B8h+var_3E0+8], r12
0x180221222  cmova   rax, qword ptr [rsp+4B8h+Src]
0x18022122b  mov     qword ptr [rsp+4B8h+var_450], rax
0x180221230  mov     qword ptr [rsp+4B8h+var_450+8], rcx
0x180221235  lea     rcx, [rsp+4B8h+var_450]
0x18022123a  call    ?FileExists@@YA_NAEBV?$basic_zstring_view@_W@wil@@@Z; FileExists(wil::basic_zstring_view<wchar_t> const &)
0x18022123f  test    al, al
0x180221241  jz      short loc_180221257
0x180221243  lea     rcx, [rsp+4B8h+Src]; void *
0x18022124b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180221250  xor     eax, eax
0x180221252  jmp     loc_180221975
0x180221257  lea     rcx, [rsp+4B8h+var_378]; this
0x18022125f  call    ??0WimgapiLoader@@QEAA@XZ; WimgapiLoader::WimgapiLoader(void)
0x180221264  nop
0x180221265  mov     [rsp+4B8h+var_3F8], r15d
0x18022126d  mov     [rsp+4B8h+var_428], r15
0x180221275  xorps   xmm0, xmm0
0x180221278  movups  [rsp+4B8h+var_478], xmm0
0x18022127d  xorps   xmm1, xmm1
0x180221280  movdqu  [rsp+4B8h+var_468], xmm1
0x180221286  mov     r8d, 0Dh
0x18022128c  lea     rdx, aWimcreatefile_0; "WIMCreateFile"
0x180221293  lea     rcx, [rsp+4B8h+var_478]
0x180221298  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022129d  nop
0x18022129e  lea     rdx, [rsp+4B8h+var_478]
0x1802212a3  lea     rcx, [rsp+4B8h+var_378]
0x1802212ab  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x1802212b0  mov     rbx, rax
0x1802212b3  lea     rcx, [rsp+4B8h+var_478]; void *
0x1802212b8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1802212bd  lea     rax, [rsp+4B8h+var_3F8]
0x1802212c5  mov     [rsp+4B8h+var_490], rax
0x1802212ca  mov     [rsp+4B8h+var_498], r15d; int
0x1802212cf  xor     r9d, r9d
0x1802212d2  lea     r14d, [r9+3]
0x1802212d6  mov     r8d, r14d
0x1802212d9  mov     edx, 80000000h
0x1802212de  mov     rcx, [r13+0]
0x1802212e2  mov     rax, rbx
0x1802212e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802212ea  mov     rsi, rax
0x1802212ed  mov     [rsp+4B8h+var_428], rax
0x1802212f5  test    rax, rax
0x1802212f8  jz      loc_180221999
0x1802212fe  mov     rcx, rdi
0x180221301  call    ?EnsureDirectoryExistsHr@@YAJAEBV?$basic_zstring_view@_W@wil@@@Z; EnsureDirectoryExistsHr(wil::basic_zstring_view<wchar_t> const &)
0x180221306  xorps   xmm0, xmm0
0x180221309  movups  [rsp+4B8h+var_478], xmm0
0x18022130e  xorps   xmm1, xmm1
0x180221311  movdqu  [rsp+4B8h+var_468], xmm1
0x180221317  mov     r8d, 13h
0x18022131d  lea     rdx, aWimsettemporar_0; "WIMSetTemporaryPath"
0x180221324  lea     rcx, [rsp+4B8h+var_478]
0x180221329  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022132e  nop
0x18022132f  lea     rdx, [rsp+4B8h+var_478]
0x180221334  lea     rcx, [rsp+4B8h+var_378]
0x18022133c  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x180221341  mov     rbx, rax
0x180221344  lea     rcx, [rsp+4B8h+var_478]; void *
0x180221349  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18022134e  mov     rdx, [rdi]
0x180221351  mov     rcx, rsi
0x180221354  mov     rax, rbx
0x180221357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022135c  mov     rcx, [rsp+4B8h]; this
0x180221364  test    eax, eax
0x180221366  jz      loc_1802219DE
0x18022136c  mov     [rsp+4B8h+var_420], r15
0x180221374  xorps   xmm0, xmm0
0x180221377  movups  [rsp+4B8h+var_478], xmm0
0x18022137c  xorps   xmm1, xmm1
0x18022137f  movdqu  [rsp+4B8h+var_468], xmm1
0x180221385  mov     r8d, 0Ch
0x18022138b  lea     rdx, aWimloadimage_0; "WIMLoadImage"
0x180221392  lea     rcx, [rsp+4B8h+var_478]
0x180221397  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022139c  nop
0x18022139d  lea     rdx, [rsp+4B8h+var_478]
0x1802213a2  lea     rcx, [rsp+4B8h+var_378]
0x1802213aa  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x1802213af  mov     rbx, rax
0x1802213b2  lea     rcx, [rsp+4B8h+var_478]; void *
0x1802213b7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1802213bc  mov     edx, 1
0x1802213c1  mov     rcx, rsi
0x1802213c4  mov     rax, rbx
0x1802213c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802213cc  mov     rdi, rax
0x1802213cf  mov     [rsp+4B8h+var_420], rax
0x1802213d7  test    rax, rax
0x1802213da  jz      loc_1802219EE
0x1802213e0  xor     edx, edx; Val
0x1802213e2  mov     r8d, 250h; Size
0x1802213e8  lea     rcx, [rsp+4B8h+var_2E8]; void *
0x1802213f0  call    memset_0
0x1802213f5  xorps   xmm0, xmm0
0x1802213f8  xor     eax, eax
0x1802213fa  movups  [rsp+4B8h+var_98], xmm0
0x180221402  mov     [rsp+4B8h+var_88], rax
0x18022140a  movups  [rsp+4B8h+var_80], xmm0
0x180221412  movups  [rsp+4B8h+var_70], xmm0
0x18022141a  movups  [rsp+4B8h+var_60], xmm0
0x180221422  mov     [rsp+4B8h+var_50], rax
0x18022142a  mov     [rsp+4B8h+var_430], r15
0x180221432  movups  [rsp+4B8h+var_478], xmm0
0x180221437  xorps   xmm1, xmm1
0x18022143a  movdqu  [rsp+4B8h+var_468], xmm1
0x180221440  lea     r8d, [rax+15h]
0x180221444  lea     rdx, aWimfindfirstim; "WIMFindFirstImageFile"
0x18022144b  lea     rcx, [rsp+4B8h+var_478]
0x180221450  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180221455  nop
0x180221456  lea     rdx, [rsp+4B8h+var_478]
0x18022145b  lea     rcx, [rsp+4B8h+var_378]
0x180221463  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x180221468  mov     rbx, rax
0x18022146b  lea     rcx, [rsp+4B8h+var_478]; void *
0x180221470  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180221475  lea     r8, [rsp+4B8h+var_2E8]
0x18022147d  lea     rdx, aHistoryCixXml; "history.cix.xml"
0x180221484  mov     rcx, rdi
0x180221487  mov     rax, rbx
0x18022148a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022148f  mov     [rsp+4B8h+var_430], rax
0x180221497  test    rax, rax
0x18022149a  jnz     loc_1802218DF
0x1802214a0  xorps   xmm0, xmm0
0x1802214a3  movups  [rsp+4B8h+var_478], xmm0
0x1802214a8  xorps   xmm1, xmm1
0x1802214ab  movdqu  [rsp+4B8h+var_468], xmm1
0x1802214b1  lea     r8d, [rax+15h]
0x1802214b5  lea     rdx, aWimfindfirstim; "WIMFindFirstImageFile"
0x1802214bc  lea     rcx, [rsp+4B8h+var_478]
0x1802214c1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802214c6  nop
0x1802214c7  lea     rdx, [rsp+4B8h+var_478]
0x1802214cc  lea     rcx, [rsp+4B8h+var_378]
0x1802214d4  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x1802214d9  mov     rbx, rax
0x1802214dc  lea     rcx, [rsp+4B8h+var_478]; void *
0x1802214e1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1802214e6  lea     r8, [rsp+4B8h+var_2E8]
0x1802214ee  lea     rdx, aExpressPsfCixX; "express.psf.cix.xml"
0x1802214f5  mov     rcx, rdi
0x1802214f8  mov     rax, rbx
0x1802214fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221500  mov     r12, rax
0x180221503  mov     [rsp+4B8h+var_430], rax
0x18022150b  test    rax, rax
0x18022150e  jz      loc_180221A34
0x180221514  cmp     [rsp+4B8h+var_2CC], r15d
0x18022151c  jnz     loc_180221A79
0x180221522  mov     qword ptr [rsp+4B8h+var_450], r15
0x180221527  xorps   xmm0, xmm0
0x18022152a  movups  [rsp+4B8h+var_478], xmm0
0x18022152f  xorps   xmm1, xmm1
0x180221532  movdqu  [rsp+4B8h+var_468], xmm1
0x180221538  mov     r8d, 12h
0x18022153e  lea     rdx, aWimcreateimage; "WIMCreateImageFile"
0x180221545  lea     rcx, [rsp+4B8h+var_478]
0x18022154a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18022154f  nop
0x180221550  lea     rdx, [rsp+4B8h+var_478]
0x180221555  lea     rcx, [rsp+4B8h+var_378]
0x18022155d  call    ?GetFnInternal@DllLoader@@AEAAP6A_JXZAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; DllLoader::GetFnInternal(std::string const &)
0x180221562  mov     rbx, rax
0x180221565  lea     rcx, [rsp+4B8h+var_478]; void *
0x18022156a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18022156f  mov     [rsp+4B8h+var_498], r15d; int
0x180221574  mov     r9d, r14d
0x180221577  mov     r8d, 80000000h
0x18022157d  lea     rdx, aExpressPsfCixX; "express.psf.cix.xml"
0x180221584  mov     rcx, rdi
0x180221587  mov     rax, rbx
0x18022158a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022158f  mov     r14, rax
0x180221592  mov     qword ptr [rsp+4B8h+var_450], rax
  ... truncated ...
```
