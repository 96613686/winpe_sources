# Utility::VerifyAndNormalizeFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long &)

- ea: `0x180042ddc`
- end: `0x180043e46`
- name: `?VerifyAndNormalizeFilePath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEAJ@Z`
- size: `4202`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180042170`

## callees

- `0x180004ea0`
- `0x180006c20`
- `0x180006c40`
- `0x18000712e`
- `0x18000fb60`
- `0x180010640`
- `0x180011fcc`
- `0x18001209c`
- `0x1800134b8`
- `0x1800149a8`
- `0x180014a48`
- `0x1800276cc`
- `0x1800276fc`
- `0x180027cb0`
- `0x18002cd04`
- `0x180031224`
- `0x1800397d0`
- `0x180042bb0`
- `0x180042c58`
- `0x180042ddc`
- `0x180044a1c`
- `0x18004c020`
- `0x180055060`
- `0x1800e67d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043342`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043791`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800439fc`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043ac1`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043342`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043791`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800439fc`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180043ac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800439ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800439ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043c8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043cb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180043cb1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043b9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043c5c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043b9e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180043c5c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180043863`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x180043863`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180043b0a`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180043b0a`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180042e98`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x180042e98`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004397e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18004397e`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x180043bd4`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x180043bd4`

## string_xrefs

- `0x180042f35`: `PathCchCanonicalizeEx failed: [0x%08x]`
- `0x180042f42`: `Utility::VerifyAndNormalizeFilePath`
- `0x180043b3f`: `Utility::VerifyAndNormalizeFilePath`
- `0x180043b32`: `Unsupported network path: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_OWORD *__fastcall Utility::VerifyAndNormalizeFilePath(_OWORD *a1, __int64 a2, signed int *a3)
{
  const WCHAR *v4; // r8
  WCHAR *v5; // rcx
  HRESULT v6; // edi
  LPCWSTR *v7; // rax
  unsigned __int64 v8; // r12
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  char **v12; // rdi
  char *v13; // rbx
  __int64 last_trivial_2; // rax
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  LPCWSTR *v17; // rdx
  __int64 v18; // rax
  LPCWSTR v19; // rdx
  __int64 *v20; // rdi
  __int64 *v21; // r8
  LPCWSTR *v22; // rsi
  char *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  LPCWSTR *v26; // rax
  unsigned __int16 **v27; // rcx
  __int64 *v28; // r8
  LPCWSTR *v29; // rdi
  char *v30; // rbx
  __int64 v31; // rax
  unsigned __int16 *v32; // rdx
  wchar_t *v33; // rcx
  unsigned __int16 **v34; // rax
  __int64 v35; // rdx
  unsigned __int16 **v36; // rcx
  unsigned __int16 **v37; // rax
  unsigned __int16 **v38; // rax
  LPCWSTR *v39; // rax
  unsigned __int64 v40; // rcx
  __int64 *v41; // r8
  LPCWSTR *v42; // rdi
  char *v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  LPCWSTR *v46; // rax
  unsigned __int16 *v47; // rdx
  wchar_t *v48; // rcx
  unsigned __int16 **v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // rcx
  __int64 *v52; // rdi
  LPCWSTR *v53; // rsi
  char *v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rax
  unsigned __int64 v57; // r8
  LPCWSTR *v58; // rax
  __int64 *v59; // r8
  LPCWSTR *v60; // rdi
  char *v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rax
  unsigned __int16 **v64; // rcx
  unsigned __int16 **v65; // rax
  unsigned __int16 **v66; // rax
  LPCWSTR *v67; // rax
  LPCWSTR *v68; // rax
  unsigned __int64 v69; // r8
  unsigned __int64 v70; // r8
  __int128 *v71; // rdx
  __int64 v72; // rax
  const WCHAR *v73; // rcx
  LPCWSTR *v74; // rax
  signed int LastError; // eax
  LPCWSTR *v76; // rcx
  int v77; // eax
  LPCWSTR *v78; // rax
  LPCWSTR *v79; // rax
  LPCWSTR *v80; // rax
  LPCWSTR *v81; // rax
  LPCWSTR *v82; // rax
  LPCWSTR *v83; // rcx
  int v84; // eax
  LPCWSTR *v85; // rax
  LPCWSTR *v86; // rcx
  LPCWSTR *v87; // rax
  LPCWSTR *v88; // rax
  const WCHAR *v89; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v91; // rcx
  LPWSTR *v92; // rbx
  __int64 v93; // r8
  LPWSTR v94; // r9
  LPCWSTR *v95; // rsi
  const WCHAR *v96; // rcx
  LPCWSTR *v97; // rax
  signed int v98; // eax
  LPCWSTR *v99; // rax
  __int64 LongPath; // rax
  LPCWSTR *v101; // rax
  LPCWSTR *v102; // rax
  _OWORD *v103; // rbx
  _OWORD *result; // rax
  const struct wil::FailureInfo *v105; // r9
  signed int v106; // eax
  unsigned int v107; // edx
  const char *v108; // rcx
  int pNumArgs; // [rsp+4Ch] [rbp-145Ch] BYREF
  _OWORD *v111; // [rsp+50h] [rbp-1458h]
  _OWORD *v112; // [rsp+58h] [rbp-1450h]
  LPWSTR *v113; // [rsp+60h] [rbp-1448h]
  void **v114; // [rsp+68h] [rbp-1440h] BYREF
  const char *v115; // [rsp+70h] [rbp-1438h] BYREF
  _BYTE v116[40]; // [rsp+80h] [rbp-1428h] BYREF
  __int128 v117; // [rsp+A8h] [rbp-1400h]
  __int128 v118; // [rsp+B8h] [rbp-13F0h]
  __int128 v119; // [rsp+C8h] [rbp-13E0h]
  __int128 v120; // [rsp+D8h] [rbp-13D0h]
  __int128 v121; // [rsp+E8h] [rbp-13C0h]
  __int128 v122; // [rsp+F8h] [rbp-13B0h]
  __int128 v123; // [rsp+108h] [rbp-13A0h]
  __int128 v124; // [rsp+118h] [rbp-1390h]
  __int64 v125; // [rsp+128h] [rbp-1380h]
  LPCWSTR pszPath[2]; // [rsp+150h] [rbp-1358h] BYREF
  unsigned __int64 v127; // [rsp+160h] [rbp-1348h]
  unsigned __int64 v128; // [rsp+168h] [rbp-1340h]
  __int128 v129; // [rsp+170h] [rbp-1338h] BYREF
  __int128 v130; // [rsp+180h] [rbp-1328h]
  unsigned __int16 *v131[2]; // [rsp+190h] [rbp-1318h] BYREF
  __m128i v132; // [rsp+1A0h] [rbp-1308h]
  unsigned __int16 *v133[2]; // [rsp+1B0h] [rbp-12F8h] BYREF
  __m128i si128; // [rsp+1C0h] [rbp-12E8h]
  char *v135[2]; // [rsp+1D0h] [rbp-12D8h] BYREF
  __int64 v136; // [rsp+1E0h] [rbp-12C8h]
  unsigned __int64 v137; // [rsp+1E8h] [rbp-12C0h]
  _OWORD v138[2]; // [rsp+1F0h] [rbp-12B8h] BYREF
  PWSTR pszPathOut[3]; // [rsp+210h] [rbp-1298h] BYREF
  size_t cchPathOut; // [rsp+228h] [rbp-1280h]
  _OWORD Src[2]; // [rsp+230h] [rbp-1278h] BYREF
  WCHAR Buffer[8]; // [rsp+250h] [rbp-1258h] BYREF
  __int128 v143; // [rsp+260h] [rbp-1248h]
  __int128 v144; // [rsp+270h] [rbp-1238h]
  __int128 v145; // [rsp+280h] [rbp-1228h]
  __int128 v146; // [rsp+290h] [rbp-1218h]
  __int128 v147; // [rsp+2A0h] [rbp-1208h]
  __int128 v148; // [rsp+2B0h] [rbp-11F8h]
  __int128 v149; // [rsp+2C0h] [rbp-11E8h]
  __int128 v150; // [rsp+2D0h] [rbp-11D8h]
  __int64 v151; // [rsp+2E0h] [rbp-11C8h]
  _BYTE v152[4096]; // [rsp+460h] [rbp-1048h] BYREF

  v111 = a1;
  v112 = a1;
  *(_OWORD *)pszPath = 0;
  v127 = 0;
  v128 = 7;
  LOWORD(pszPath[0]) = 0;
  try
  {
    std::wstring::wstring();
    while ( 1 )
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v4 = (const WCHAR *)a2;
      else
        v4 = *(const WCHAR **)a2;
      v5 = (WCHAR *)pszPathOut;
      if ( cchPathOut > 7 )
        v5 = pszPathOut[0];
      v6 = PathCchCanonicalizeEx(v5, cchPathOut, v4, 1u);
      if ( (_WORD)v6 != 122 || cchPathOut >= 0x8000 )
        break;
      std::wstring::resize(pszPathOut);
    }
    std::wstring::operator=(pszPath, pszPathOut);
    if ( v6 < 0 )
    {
      std::wstring::operator=(pszPath, a2);
      AslLogCallPrintf(1, "Utility::VerifyAndNormalizeFilePath", 1703, "PathCchCanonicalizeEx failed: [0x%08x]", v6);
      v8 = -1;
    }
    else
    {
      v7 = pszPath;
      if ( v128 > 7 )
        v7 = (LPCWSTR *)pszPath[0];
      v8 = -1;
      v9 = -1;
      do
        ++v9;
      while ( *((_WORD *)v7 + v9) );
      std::wstring::resize(pszPath);
    }
    v10 = Utility::TrimSpace(pszPath);
    std::wstring::operator=(pszPath, v10);
    std::wstring::wstring((__int64)v135, (__int64)pszPath);
    v11 = Utility::TrimSpace(v135);
    std::wstring::operator=(v135, v11);
    v12 = v135;
    if ( v137 > 7 )
      v12 = (char **)v135[0];
    if ( !v136
      || (v13 = (char *)v12 + 2 * v136,
          last_trivial_2 = _std_find_last_trivial_2(v12, v13, 92),
          (char *)last_trivial_2 == v13) )
    {
      v15 = -1;
    }
    else
    {
      v15 = (last_trivial_2 - (__int64)v12) >> 1;
    }
    if ( v15 == v136 - 1 )
    {
      v129 = 0;
      v130 = 0;
      v16 = v127;
      if ( v127 >= v15 )
        v16 = v15;
      v17 = pszPath;
      if ( v128 > 7 )
        v17 = (LPCWSTR *)pszPath[0];
      std::wstring::_Construct<1,unsigned short const *>((char **)&v129, v17, v16);
      std::wstring::operator=(v135, &v129);
      std::wstring::~wstring((char **)&v129);
    }
    std::wstring::operator=(pszPath, v135);
    std::wstring::~wstring(v135);
    v18 = Utility::ToLower(v138, pszPath);
    std::wstring::operator=(pszPath, v18);
    std::wstring::~wstring((char **)v138);
    v19 = pszPath[0];
    if ( v127 >= 0x104 )
    {
      v20 = &Utility::PathPrefixLongPath;
      v21 = &Utility::PathPrefixLongPath;
      if ( (unsigned __int64)qword_18011B9E8 > 7 )
        v21 = (__int64 *)Utility::PathPrefixLongPath;
      v22 = pszPath;
      if ( v128 > 7 )
        v22 = (LPCWSTR *)pszPath[0];
      if ( qword_18011B9E0 > v127 )
      {
        v25 = -1;
      }
      else
      {
        if ( !qword_18011B9E0 )
          goto LABEL_146;
        v23 = (char *)v22 + 2 * v127;
        v24 = _std_search_2(v22, v23, v21, qword_18011B9E0);
        v19 = pszPath[0];
        if ( (char *)v24 == v23 )
        {
LABEL_40:
          if ( 0x7FFFFFFFFFFFFFFELL - qword_18011B9E0 < v127 )
            std::_Xlen_string();
          if ( (unsigned __int64)qword_18011B9E8 > 7 )
            v20 = (__int64 *)Utility::PathPrefixLongPath;
          v26 = pszPath;
          if ( v128 > 7 )
            v26 = (LPCWSTR *)v19;
          std::wstring::wstring(v138, v19, v127, v20, qword_18011B9E0, v26, v127);
          std::wstring::operator=(pszPath, v138);
          v27 = (unsigned __int16 **)v138;
LABEL_145:
          std::wstring::~wstring((char **)v27);
          v19 = pszPath[0];
          goto LABEL_146;
        }
        v25 = (v24 - (__int64)v22) >> 1;
      }
      if ( v25 )
        goto LABEL_40;
LABEL_146:
      if ( v127 >= 2 )
      {
        v67 = pszPath;
        if ( v128 > 7 )
          v67 = (LPCWSTR *)v19;
        if ( *(_WORD *)v67 == 92 )
        {
          v68 = pszPath;
          if ( v128 > 7 )
            v68 = (LPCWSTR *)v19;
          if ( *((_WORD *)v68 + 1) != 92 )
          {
            GetCurrentDirectoryW(0x104u, Buffer);
            v129 = 0;
            v130 = 0;
            v69 = -1;
            do
              ++v69;
            while ( Buffer[v69] );
            std::wstring::_Construct<1,unsigned short const *>((char **)&v129, Buffer, v69);
            memset(Src, 0, sizeof(Src));
            v70 = 2;
            if ( (unsigned __int64)v130 < 2 )
              v70 = v130;
            v71 = &v129;
            if ( *((_QWORD *)&v130 + 1) > 7u )
              v71 = (__int128 *)v129;
            std::wstring::_Construct<1,unsigned short const *>((char **)Src, v71, v70);
            v72 = std::wstring::append(Src);
            v138[0] = *(_OWORD *)v72;
            v138[1] = *(_OWORD *)(v72 + 16);
            *(_QWORD *)(v72 + 16) = 0;
            *(_QWORD *)(v72 + 24) = 7;
            *(_WORD *)v72 = 0;
            std::wstring::operator=(pszPath, v138);
            std::wstring::~wstring((char **)v138);
            std::wstring::~wstring((char **)Src);
            v73 = (const WCHAR *)pszPath;
            if ( v128 > 7 )
              v73 = pszPath[0];
            if ( !PathFileExistsW(v73) )
            {
              v74 = pszPath;
              if ( v128 > 7 )
                v74 = (LPCWSTR *)pszPath[0];
              v127 = 0;
              *(_WORD *)v74 = 0;
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              *a3 = LastError;
            }
            std::wstring::~wstring((char **)&v129);
            v19 = pszPath[0];
          }
        }
        if ( v127 >= 2 )
        {
          v76 = pszPath;
          if ( v128 > 7 )
            v76 = (LPCWSTR *)v19;
          v77 = _o_iswalpha(*(unsigned __int16 *)v76);
          v19 = pszPath[0];
          if ( v77 )
          {
            v78 = pszPath;
            if ( v128 > 7 )
              v78 = (LPCWSTR *)pszPath[0];
            if ( *((_WORD *)v78 + 1) == 58 )
              goto LABEL_194;
          }
        }
      }
      if ( v127 <= 0x104 )
        goto LABEL_234;
      v79 = pszPath;
      if ( v128 > 7 )
        v79 = (LPCWSTR *)v19;
      if ( *(_WORD *)v79 != 92 )
        goto LABEL_234;
      v80 = pszPath;
      if ( v128 > 7 )
        v80 = (LPCWSTR *)v19;
      if ( *((_WORD *)v80 + 1) != 92 )
        goto LABEL_234;
      v81 = pszPath;
      if ( v128 > 7 )
        v81 = (LPCWSTR *)v19;
      if ( *((_WORD *)v81 + 2) != 63 )
        goto LABEL_234;
      v82 = pszPath;
      if ( v128 > 7 )
        v82 = (LPCWSTR *)v19;
      if ( *((_WORD *)v82 + 3) != 92 )
        goto LABEL_234;
      v83 = pszPath;
      if ( v128 > 7 )
        v83 = (LPCWSTR *)v19;
      v84 = _o_iswalpha(*((unsigned __int16 *)v83 + 4));
      v19 = pszPath[0];
      if ( !v84 )
        goto LABEL_234;
      v85 = pszPath;
      if ( v128 > 7 )
        v85 = (LPCWSTR *)pszPath[0];
      if ( *((_WORD *)v85 + 5) == 58 )
      {
LABEL_194:
        v86 = pszPath;
        if ( v128 > 7 )
          v86 = (LPCWSTR *)v19;
        if ( PathIsNetworkPathW((LPCWSTR)v86) )
        {
          v87 = pszPath;
          if ( v128 > 7 )
            v87 = (LPCWSTR *)pszPath[0];
          AslLogCallPrintf(3, "Utility::VerifyAndNormalizeFilePath", 1833, "Unsupported network path: %ws", v87);
          v88 = pszPath;
          if ( v128 > 7 )
            v88 = (LPCWSTR *)pszPath[0];
          v127 = 0;
          *(_WORD *)v88 = 0;
          *a3 = -2147467259;
        }
        else
        {
          v89 = (const WCHAR *)pszPath;
          if ( v128 > 7 )
            v89 = pszPath[0];
          FileAttributesW = GetFileAttributesW(v89);
          if ( FileAttributesW == -1 )
          {
            pNumArgs = 0;
            v91 = (const WCHAR *)pszPath;
            if ( v128 > 7 )
              v91 = pszPath[0];
            v92 = CommandLineToArgvW(v91, &pNumArgs);
            v113 = v92;
            v94 = *v92;
            do
              ++v8;
            while ( v94[v8] );
            if ( v8 > v128 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                pszPath,
                v8,
                v93,
                v94);
            }
            else
            {
              v95 = pszPath;
              if ( v128 > 7 )
                v95 = (LPCWSTR *)pszPath[0];
              v127 = v8;
              memmove_0(v95, v94, 2 * v8);
              *((_WORD *)v95 + v8) = 0;
            }
            v96 = (const WCHAR *)pszPath;
            if ( v128 > 7 )
              v96 = pszPath[0];
            if ( GetFileAttributesW(v96) == -1 )
            {
              v97 = pszPath;
              if ( v128 > 7 )
                v97 = (LPCWSTR *)pszPath[0];
              v127 = 0;
              *(_WORD *)v97 = 0;
              v98 = GetLastError();
              if ( v98 > 0 )
                v98 = (unsigned __int16)v98 | 0x80070000;
              *a3 = v98;
            }
            if ( v92 )
              LocalFree(v92);
          }
          else if ( (FileAttributesW & 0x11440) != 0 )
          {
            v101 = pszPath;
            if ( v128 > 7 )
              v101 = (LPCWSTR *)pszPath[0];
            v127 = 0;
            *(_WORD *)v101 = 0;
            *a3 = -2147024864;
          }
          else if ( (FileAttributesW & 0x10) != 0 )
          {
            v99 = pszPath;
            if ( v128 > 7 )
              v99 = (LPCWSTR *)pszPath[0];
            v127 = 0;
            *(_WORD *)v99 = 0;
            *a3 = -2147024894;
          }
          else if ( std::wstring::find(pszPath, L"~") != -1 )
          {
            LongPath = Utility::GetLongPath(v138, pszPath);
            std::wstring::operator=(pszPath, LongPath);
            std::wstring::~wstring((char **)v138);
            *a3 = 0;
          }
        }
      }
      else
      {
LABEL_234:
        v102 = pszPath;
        if ( v128 > 7 )
          v102 = (LPCWSTR *)v19;
        v127 = 0;
        *(_WORD *)v102 = 0;
        *a3 = -2147024893;
      }
      v103 = v111;
      Utility::ToLower(v111, pszPath);
      std::wstring::~wstring((char **)pszPathOut);
      std::wstring::~wstring((char **)pszPath);
      return v103;
    }
    v28 = &Utility::PathPrefixDeviceDrivePath;
    if ( (unsigned __int64)qword_18011BA28 > 7 )
      v28 = (__int64 *)Utility::PathPrefixDeviceDrivePath;
    v29 = pszPath;
    if ( v128 > 7 )
      v29 = (LPCWSTR *)pszPath[0];
    if ( qword_18011BA20 <= v127 )
    {
      if ( qword_18011BA20 )
      {
        v30 = (char *)v29 + 2 * v127;
        v31 = _std_search_2(v29, v30, v28, qword_18011BA20);
        if ( (char *)v31 == v30 || ((v31 - (_QWORD)v29) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          v19 = pszPath[0];
          goto LABEL_78;
        }
        v19 = pszPath[0];
      }
      if ( v127 < 0x104 )
      {
        *(_OWORD *)v133 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v133[0]) = 0;
        std::wstring::resize(v133);
        v32 = (unsigned __int16 *)v133;
        if ( si128.m128i_i64[1] > 7uLL )
          v32 = v133[0];
        v33 = (wchar_t *)pszPath;
        if ( v128 > 7 )
          v33 = (wchar_t *)pszPath[0];
        if ( (int)ConvertDevicePathToDrivePath(v33, v32) >= 0 )
        {
          v34 = v133;
          if ( si128.m128i_i64[1] > 7uLL )
            v34 = (unsigned __int16 **)v133[0];
          v35 = -1;
          do
            ++v35;
          while ( *((_WORD *)v34 + v35) );
          std::wstring::resize(v133);
          if ( si128.m128i_i64[0] >= 3uLL )
          {
            v36 = v133;
            if ( si128.m128i_i64[1] > 7uLL )
              v36 = (unsigned __int16 **)v133[0];
            if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v36) )
            {
              v37 = v133;
              if ( si128.m128i_i64[1] > 7uLL )
                v37 = (unsigned __int16 **)v133[0];
              if ( *((_WORD *)v37 + 1) == 58 )
              {
                v38 = v133;
                if ( si128.m128i_i64[1] > 7uLL )
                  v38 = (unsigned __int16 **)v133[0];
                if ( *((_WORD *)v38 + 2) == 92 )
                  std::wstring::operator=(pszPath, v133);
              }
            }
          }
        }
        v27 = v133;
        goto LABEL_145;
      }
    }
LABEL_78:
    if ( !v127 )
      goto LABEL_146;
    v39 = pszPath;
    if ( v128 > 7 )
      v39 = (LPCWSTR *)v19;
    if ( *(_WORD *)v39 != 92 )
      goto LABEL_146;
    *(_OWORD *)v131 = 0;
    v132 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v131[0]) = 0;
    v40 = qword_18011B9C0;
    v41 = &Utility::PathPrefixGlobal;
    if ( (unsigned __int64)qword_18011B9C8 > 7 )
      v41 = (__int64 *)Utility::PathPrefixGlobal;
    v42 = pszPath;
    if ( v128 > 7 )
      v42 = (LPCWSTR *)v19;
    if ( qword_18011B9C0 > v127 )
    {
      v45 = -1;
    }
    else
    {
      if ( !qword_18011B9C0 )
      {
LABEL_92:
        v129 = 0;
        v130 = 0;
        if ( v127 < v40 )
          std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v40, v19, v41);
        v46 = pszPath;
        if ( v128 > 7 )
          v46 = (LPCWSTR *)v19;
        std::wstring::_Construct<1,unsigned short const *>((char **)&v129, (char *)v46 + 2 * v40, v127 - v40);
        std::wstring::operator=(pszPath, &v129);
        std::wstring::~wstring((char **)&v129);
        if ( v127 < 0x104 )
        {
          std::wstring::resize(v131);
          v47 = (unsigned __int16 *)v131;
          if ( v132.m128i_i64[1] > 7uLL )
            v47 = v131[0];
          v48 = (wchar_t *)pszPath;
          if ( v128 > 7 )
            v48 = (wchar_t *)pszPath[0];
          if ( (int)ConvertDevicePathToDrivePath(v48, v47) >= 0 )
          {
            v49 = v131;
            if ( v132.m128i_i64[1] > 7uLL )
              v49 = (unsigned __int16 **)v131[0];
            v50 = -1;
            do
              ++v50;
            while ( *((_WORD *)v49 + v50) );
            std::wstring::resize(v131);
          }
        }
        goto LABEL_133;
      }
      v43 = (char *)v42 + 2 * v127;
      v44 = _std_search_2(v42, v43, v41, qword_18011B9C0);
      v19 = pszPath[0];
      if ( (char *)v44 == v43 )
      {
LABEL_106:
        v51 = qword_18011B9E0;
        v52 = &Utility::PathPrefixLongPath;
        if ( (unsigned __int64)qword_18011B9E8 > 7 )
          v52 = (__int64 *)Utility::PathPrefixLongPath;
        v53 = pszPath;
        if ( v128 > 7 )
          v53 = (LPCWSTR *)v19;
        if ( qword_18011B9E0 > v127 )
        {
          v56 = -1;
        }
        else
        {
          if ( !qword_18011B9E0 )
          {
LABEL_116:
            v129 = 0;
            v130 = 0;
            if ( v127 < v51 )
              std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v51, v19, v41);
            v57 = v127 - v51;
            v58 = pszPath;
            if ( v128 > 7 )
              v58 = (LPCWSTR *)v19;
LABEL_132:
            std::wstring::_Construct<1,unsigned short const *>((char **)&v129, (char *)v58 + 2 * v51, v57);
            std::wstring::operator=(v131, &v129);
            std::wstring::~wstring((char **)&v129);
            goto LABEL_133;
          }
          v54 = (char *)v53 + 2 * v127;
          v55 = _std_search_2(v53, v54, v52, qword_18011B9E0);
          v19 = pszPath[0];
          if ( (char *)v55 == v54 )
          {
LABEL_119:
            v51 = qword_18011BA00;
            v59 = &Utility::PathPrefixDrivePath;
            if ( (unsigned __int64)qword_18011BA08 > 7 )
              v59 = (__int64 *)Utility::PathPrefixDrivePath;
            v60 = pszPath;
            if ( v128 > 7 )
              v60 = (LPCWSTR *)v19;
            if ( qword_18011BA00 > v127 )
            {
              v63 = -1;
            }
            else
            {
              if ( !qword_18011BA00 )
              {
LABEL_129:
                v129 = 0;
                v130 = 0;
                if ( v127 < v51 )
                  std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v51, v19, v59);
                v57 = v127 - v51;
                v58 = pszPath;
                if ( v128 > 7 )
                  v58 = (LPCWSTR *)v19;
                goto LABEL_132;
              }
              v61 = (char *)v60 + 2 * v127;
              v62 = _std_search_2(v60, v61, v59, qword_18011BA00);
              if ( (char *)v62 == v61 )
              {
LABEL_133:
                if ( v132.m128i_i64[0] >= 3uLL )
                {
                  v64 = v131;
                  if ( v132.m128i_i64[1] > 7uLL )
                    v64 = (unsigned __int16 **)v131[0];
                  if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v64) )
                  {
                    v65 = v131;
                    if ( v132.m128i_i64[1] > 7uLL )
                      v65 = (unsigned __int16 **)v131[0];
                    if ( *((_WORD *)v65 + 1) == 58 )
                    {
                      v66 = v131;
                      if ( v132.m128i_i64[1] > 7uLL )
                        v66 = (unsigned __int16 **)v131[0];
                      if ( *((_WORD *)v66 + 2) == 92 )
                        std::wstring::operator=(pszPath, v131);
                    }
                  }
                }
                v27 = v131;
                goto LABEL_145;
              }
              v63 = (v62 - (__int64)v60) >> 1;
              v19 = pszPath[0];
              v51 = qword_18011BA00;
            }
            if ( !v63 )
              goto LABEL_129;
            goto LABEL_133;
          }
          v56 = (v55 - (__int64)v53) >> 1;
          v51 = qword_18011B9E0;
        }
        if ( !v56 )
          goto LABEL_116;
        goto LABEL_119;
      }
      v45 = (v44 - (__int64)v42) >> 1;
      v40 = qword_18011B9C0;
    }
    if ( !v45 )
      goto LABEL_92;
    goto LABEL_106;
  }
  catch ( wil::ResultException v116 )
  {
    memset_0(v152, 0, sizeof(v152));
    *(_OWORD *)Buffer = *(_OWORD *)&v116[24];
    v143 = v117;
    v144 = v118;
    v145 = v119;
    v146 = v120;
    v147 = v121;
    v148 = v122;
    v149 = v123;
    v150 = v124;
    v151 = v125;
    wil::GetFailureLogString((wil *)v152, (unsigned __int16 *)0x800, (unsigned __int64)Buffer, v105);
    AslLogCallPrintf(1, "Utility::VerifyAndNormalizeFilePath", 1890, "%ws", v152);
    wil::ResultException::~ResultException((wil::ResultException *)v116);
    result = v112;
    *v112 = 0;
    *((_QWORD *)result + 2) = 0;
    *((_QWORD *)result + 3) = 7;
    *(_WORD *)result = 0;
    return result;
  }
  catch ( std::exception v114 )
  {
    v106 = GetLastError();
    v107 = v106;
    if ( v106 > 0 )
      v107 = (unsigned __int16)v106 | 0x80070000;
    v108 = "Unknown exception";
    if ( v115 )
      v108 = v115;
    AslLogCallPrintf(1, "Utility::VerifyAndNormalizeFilePath", 1895, "Exception: 0x%08x %s", v107, v108);
    v114 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v115);
    result = v112;
    *v112 = 0;
    *((_QWORD *)result + 2) = 0;
    *((_QWORD *)result + 3) = 7;
    *(_WORD *)result = 0;
    return result;
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "Utility::VerifyAndNormalizeFilePath", 1900, "Exception: [0x%08x]", -2147024322);
    result = v112;
    *v112 = 0;
    *((_QWORD *)result + 2) = 0;
    *((_QWORD *)result + 3) = 7;
    *(_WORD *)result = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180042ddc  push    rbx
0x180042dde  push    rsi
0x180042ddf  push    rdi
0x180042de0  push    r12
0x180042de2  push    r13
0x180042de4  push    r14
0x180042de6  push    r15
0x180042de8  mov     eax, 1470h
0x180042ded  call    _alloca_probe
0x180042df2  sub     rsp, rax
0x180042df5  mov     rax, cs:__security_cookie
0x180042dfc  xor     rax, rsp
0x180042dff  mov     [rsp+14A8h+var_48], rax
0x180042e07  mov     [rsp+14A8h+var_1468], r8
0x180042e0c  mov     rbx, rdx
0x180042e0f  mov     [rsp+14A8h+var_1458], rcx
0x180042e14  mov     [rsp+14A8h+var_1450], rcx
0x180042e19  xor     r14d, r14d
0x180042e1c  mov     esi, r14d
0x180042e1f  mov     [rsp+14A8h+var_1460], r14d
0x180042e24  xorps   xmm0, xmm0
0x180042e27  movups  xmmword ptr [rsp+14A8h+pszPath], xmm0
0x180042e2f  mov     [rsp+14A8h+var_1348], r14
0x180042e37  lea     r15d, [r14+7]
0x180042e3b  mov     [rsp+14A8h+var_1340], r15
0x180042e43  mov     word ptr [rsp+14A8h+pszPath], r14w
0x180042e4c  xor     r8d, r8d
0x180042e4f  mov     edx, 105h
0x180042e54  lea     rcx, [rsp+14A8h+pszPathOut]
0x180042e5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180042e61  nop
0x180042e62  mov     r12d, 8000h
0x180042e68  cmp     [rbx+18h], r15
0x180042e6c  jbe     short loc_180042E73
0x180042e6e  mov     r8, [rbx]
0x180042e71  jmp     short loc_180042E76
0x180042e73  mov     r8, rbx; pszPathIn
0x180042e76  mov     rdx, [rsp+14A8h+cchPathOut]; cchPathOut
0x180042e7e  lea     rcx, [rsp+14A8h+pszPathOut]
0x180042e86  cmp     rdx, r15
0x180042e89  cmova   rcx, [rsp+14A8h+pszPathOut]; pszPathOut
0x180042e92  mov     r9d, 1; dwFlags
0x180042e98  call    cs:__imp_PathCchCanonicalizeEx
0x180042e9e  mov     edi, eax
0x180042ea0  cmp     ax, 7Ah ; 'z'
0x180042ea4  jnz     short loc_180042ECC
0x180042ea6  mov     rdx, [rsp+14A8h+cchPathOut]
0x180042eae  cmp     rdx, r12
0x180042eb1  jnb     short loc_180042ECC
0x180042eb3  add     rdx, rdx
0x180042eb6  cmp     rdx, r12
0x180042eb9  cmova   rdx, r12
0x180042ebd  lea     rcx, [rsp+14A8h+pszPathOut]; Src
0x180042ec5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180042eca  jmp     short loc_180042E68
0x180042ecc  lea     rdx, [rsp+14A8h+pszPathOut]
0x180042ed4  lea     rcx, [rsp+14A8h+pszPath]
0x180042edc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180042ee1  test    edi, edi
0x180042ee3  js      short loc_180042F21
0x180042ee5  lea     rax, [rsp+14A8h+pszPath]
0x180042eed  cmp     [rsp+14A8h+var_1340], r15
0x180042ef5  cmova   rax, [rsp+14A8h+pszPath]
0x180042efe  or      r12, 0FFFFFFFFFFFFFFFFh
0x180042f02  mov     rdx, r12
0x180042f05  inc     rdx
0x180042f08  cmp     [rax+rdx*2], r14w
0x180042f0d  jnz     short loc_180042F05
0x180042f0f  inc     rdx
0x180042f12  lea     rcx, [rsp+14A8h+pszPath]; Src
0x180042f1a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180042f1f  jmp     short loc_180042F57
0x180042f21  mov     rdx, rbx
0x180042f24  lea     rcx, [rsp+14A8h+pszPath]
0x180042f2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180042f31  mov     dword ptr [rsp+14A8h+var_1488], edi
0x180042f35  lea     r9, aPathcchcanonic; "PathCchCanonicalizeEx failed: [0x%08x]"
0x180042f3c  mov     r8d, 6A7h
0x180042f42  lea     rdx, aUtilityVerifya; "Utility::VerifyAndNormalizeFilePath"
0x180042f49  mov     ecx, 1
0x180042f4e  call    AslLogCallPrintf
0x180042f53  or      r12, 0FFFFFFFFFFFFFFFFh
0x180042f57  lea     rcx, [rsp+14A8h+pszPath]
0x180042f5f  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180042f64  mov     rdx, rax
0x180042f67  lea     rcx, [rsp+14A8h+pszPath]
0x180042f6f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180042f74  nop
0x180042f75  lea     rdx, [rsp+14A8h+pszPath]
0x180042f7d  lea     rcx, [rsp+14A8h+var_12D8]
0x180042f85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180042f8a  or      esi, 2
0x180042f8d  mov     [rsp+14A8h+var_1460], esi
0x180042f91  lea     rcx, [rsp+14A8h+var_12D8]
0x180042f99  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180042f9e  mov     rdx, rax
0x180042fa1  lea     rcx, [rsp+14A8h+var_12D8]
0x180042fa9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180042fae  mov     rax, [rsp+14A8h+var_12C8]
0x180042fb6  lea     rdi, [rsp+14A8h+var_12D8]
0x180042fbe  cmp     [rsp+14A8h+var_12C0], r15
0x180042fc6  cmova   rdi, [rsp+14A8h+var_12D8]
0x180042fcf  mov     r13d, 5Ch ; '\'
0x180042fd5  test    rax, rax
0x180042fd8  jz      short loc_180043009
0x180042fda  dec     rax
0x180042fdd  cmp     rax, r12
0x180042fe0  cmovnb  rax, r12
0x180042fe4  inc     rax
0x180042fe7  lea     rbx, [rdi+rax*2]
0x180042feb  mov     r8d, r13d
0x180042fee  mov     rdx, rbx
0x180042ff1  mov     rcx, rdi
0x180042ff4  call    __std_find_last_trivial_2
0x180042ff9  mov     rcx, rax
0x180042ffc  cmp     rax, rbx
0x180042fff  jz      short loc_180043009
0x180043001  sub     rcx, rdi
0x180043004  sar     rcx, 1
0x180043007  jmp     short loc_18004300C
0x180043009  mov     rcx, r12
0x18004300c  mov     rax, [rsp+14A8h+var_12C8]
0x180043014  dec     rax
0x180043017  cmp     rcx, rax
0x18004301a  jnz     short loc_18004308A
0x18004301c  xorps   xmm0, xmm0
0x18004301f  movups  [rsp+14A8h+var_1338], xmm0
0x180043027  xorps   xmm1, xmm1
0x18004302a  movdqu  [rsp+14A8h+var_1328], xmm1
0x180043033  mov     r8, [rsp+14A8h+var_1348]
0x18004303b  cmp     r8, rcx
0x18004303e  cmovnb  r8, rcx
0x180043042  lea     rdx, [rsp+14A8h+pszPath]
0x18004304a  cmp     [rsp+14A8h+var_1340], r15
0x180043052  cmova   rdx, [rsp+14A8h+pszPath]
0x18004305b  lea     rcx, [rsp+14A8h+var_1338]
0x180043063  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180043068  lea     rdx, [rsp+14A8h+var_1338]
0x180043070  lea     rcx, [rsp+14A8h+var_12D8]
0x180043078  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004307d  lea     rcx, [rsp+14A8h+var_1338]
0x180043085  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004308a  lea     rdx, [rsp+14A8h+var_12D8]
0x180043092  lea     rcx, [rsp+14A8h+pszPath]
0x18004309a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004309f  nop
0x1800430a0  lea     rcx, [rsp+14A8h+var_12D8]
0x1800430a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800430ad  lea     rdx, [rsp+14A8h+pszPath]
0x1800430b5  lea     rcx, [rsp+14A8h+var_12B8]
0x1800430bd  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800430c2  mov     rdx, rax
0x1800430c5  lea     rcx, [rsp+14A8h+pszPath]
0x1800430cd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800430d2  lea     rcx, [rsp+14A8h+var_12B8]
0x1800430da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800430df  mov     rax, [rsp+14A8h+var_1348]
0x1800430e7  mov     esi, 104h
0x1800430ec  mov     rdx, [rsp+14A8h+pszPath]
0x1800430f4  cmp     rax, rsi
0x1800430f7  jb      loc_1800431F8
0x1800430fd  mov     r9, cs:qword_18011B9E0
0x180043104  lea     rdi, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x18004310b  mov     r8, rdi
0x18004310e  cmp     cs:qword_18011B9E8, r15
0x180043115  cmova   r8, cs:?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x18004311d  lea     rsi, [rsp+14A8h+pszPath]
0x180043125  cmp     [rsp+14A8h+var_1340], r15
0x18004312d  cmova   rsi, rdx
0x180043131  cmp     r9, rax
0x180043134  ja      short loc_180043163
0x180043136  test    r9, r9
0x180043139  jz      loc_180043806
0x18004313f  lea     rbx, [rsi+rax*2]
0x180043143  mov     rdx, rbx
0x180043146  mov     rcx, rsi
0x180043149  call    __std_search_2
0x18004314e  mov     rdx, [rsp+14A8h+pszPath]
0x180043156  cmp     rax, rbx
0x180043159  jz      short loc_18004316F
0x18004315b  sub     rax, rsi
0x18004315e  sar     rax, 1
0x180043161  jmp     short loc_180043166
0x180043163  mov     rax, r12
0x180043166  test    rax, rax
0x180043169  jz      loc_180043806
0x18004316f  mov     rcx, cs:qword_18011B9E0
0x180043176  mov     r8, [rsp+14A8h+var_1348]
0x18004317e  mov     rax, 7FFFFFFFFFFFFFFEh
0x180043188  sub     rax, rcx
0x18004318b  cmp     rax, r8
0x18004318e  jb      loc_180043E2F
0x180043194  cmp     cs:qword_18011B9E8, r15
0x18004319b  cmova   rdi, cs:?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x1800431a3  lea     rax, [rsp+14A8h+pszPath]
0x1800431ab  cmp     [rsp+14A8h+var_1340], r15
0x1800431b3  cmova   rax, rdx
0x1800431b7  mov     [rsp+14A8h+var_1478], r8
0x1800431bc  mov     [rsp+14A8h+var_1480], rax
0x1800431c1  mov     [rsp+14A8h+var_1488], rcx
0x1800431c6  mov     r9, rdi
0x1800431c9  lea     rcx, [rsp+14A8h+var_12B8]
0x1800431d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800431d6  lea     rdx, [rsp+14A8h+var_12B8]
0x1800431de  lea     rcx, [rsp+14A8h+pszPath]
0x1800431e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800431eb  lea     rcx, [rsp+14A8h+var_12B8]
0x1800431f3  jmp     loc_1800437F9
0x1800431f8  mov     r9, cs:qword_18011BA20
0x1800431ff  lea     r8, ?PathPrefixDeviceDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDeviceDrivePath
0x180043206  cmp     cs:qword_18011BA28, r15
0x18004320d  cmova   r8, cs:?PathPrefixDeviceDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDeviceDrivePath
0x180043215  lea     rdi, [rsp+14A8h+pszPath]
0x18004321d  cmp     [rsp+14A8h+var_1340], r15
0x180043225  cmova   rdi, rdx
0x180043229  cmp     r9, rax
0x18004322c  ja      loc_1800433B7
0x180043232  test    r9, r9
0x180043235  jz      short loc_180043266
0x180043237  lea     rbx, [rdi+rax*2]
0x18004323b  mov     rdx, rbx
0x18004323e  mov     rcx, rdi
0x180043241  call    __std_search_2
0x180043246  cmp     rax, rbx
0x180043249  jz      loc_1800433AF
0x18004324f  sub     rax, rdi
0x180043252  test    rax, 0FFFFFFFFFFFFFFFEh
0x180043258  jnz     loc_1800433AF
0x18004325e  mov     rdx, [rsp+14A8h+pszPath]
0x180043266  cmp     [rsp+14A8h+var_1348], rsi
0x18004326e  jnb     loc_1800433B7
0x180043274  xorps   xmm0, xmm0
0x180043277  movups  xmmword ptr [rsp+14A8h+var_12F8], xmm0
0x18004327f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180043287  movdqu  [rsp+14A8h+var_12E8], xmm1
0x180043290  mov     word ptr [rsp+14A8h+var_12F8], r14w
0x180043299  mov     rdx, rsi
0x18004329c  lea     rcx, [rsp+14A8h+var_12F8]; Src
0x1800432a4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800432a9  lea     rdx, [rsp+14A8h+var_12F8]
0x1800432b1  cmp     qword ptr [rsp+14A8h+var_12E8+8], r15
0x1800432b9  cmova   rdx, [rsp+14A8h+var_12F8]; unsigned __int16 *
0x1800432c2  lea     rcx, [rsp+14A8h+pszPath]
0x1800432ca  cmp     [rsp+14A8h+var_1340], r15
0x1800432d2  cmova   rcx, [rsp+14A8h+pszPath]; String1
0x1800432db  call    ?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z; ConvertDevicePathToDrivePath(ushort const *,ushort *)
0x1800432e0  test    eax, eax
0x1800432e2  js      loc_1800433A2
0x1800432e8  lea     rax, [rsp+14A8h+var_12F8]
0x1800432f0  cmp     qword ptr [rsp+14A8h+var_12E8+8], r15
0x1800432f8  cmova   rax, [rsp+14A8h+var_12F8]
0x180043301  mov     rdx, r12
0x180043304  inc     rdx
0x180043307  cmp     [rax+rdx*2], r14w
0x18004330c  jnz     short loc_180043304
0x18004330e  lea     rcx, [rsp+14A8h+var_12F8]; Src
0x180043316  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004331b  cmp     qword ptr [rsp+14A8h+var_12E8], 3
0x180043324  jb      short loc_1800433A2
0x180043326  lea     rcx, [rsp+14A8h+var_12F8]
0x18004332e  cmp     qword ptr [rsp+14A8h+var_12E8+8], r15
0x180043336  cmova   rcx, [rsp+14A8h+var_12F8]
0x18004333f  movzx   ecx, word ptr [rcx]
0x180043342  call    cs:__imp__o_iswalpha
0x180043348  test    eax, eax
0x18004334a  jz      short loc_1800433A2
0x18004334c  lea     rax, [rsp+14A8h+var_12F8]
0x180043354  cmp     qword ptr [rsp+14A8h+var_12E8+8], r15
0x18004335c  cmova   rax, [rsp+14A8h+var_12F8]
0x180043365  cmp     word ptr [rax+2], 3Ah ; ':'
0x18004336a  jnz     short loc_1800433A2
0x18004336c  lea     rax, [rsp+14A8h+var_12F8]
0x180043374  cmp     qword ptr [rsp+14A8h+var_12E8+8], r15
0x18004337c  cmova   rax, [rsp+14A8h+var_12F8]
0x180043385  cmp     [rax+4], r13w
0x18004338a  jnz     short loc_1800433A2
0x18004338c  lea     rdx, [rsp+14A8h+var_12F8]
0x180043394  lea     rcx, [rsp+14A8h+pszPath]
0x18004339c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800433a1  nop
0x1800433a2  lea     rcx, [rsp+14A8h+var_12F8]
0x1800433aa  jmp     loc_1800437F9
0x1800433af  mov     rdx, [rsp+14A8h+pszPath]
0x1800433b7  mov     r9, [rsp+14A8h+var_1348]
0x1800433bf  cmp     r9, 1
0x1800433c3  jb      loc_180043806
0x1800433c9  lea     rax, [rsp+14A8h+pszPath]
0x1800433d1  cmp     [rsp+14A8h+var_1340], r15
0x1800433d9  cmova   rax, rdx
0x1800433dd  cmp     [rax], r13w
0x1800433e1  jnz     loc_180043806
0x1800433e7  xorps   xmm0, xmm0
0x1800433ea  movups  xmmword ptr [rsp+14A8h+var_1318], xmm0
0x1800433f2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800433fa  movdqu  [rsp+14A8h+var_1308], xmm1
0x180043403  mov     word ptr [rsp+14A8h+var_1318], r14w
0x18004340c  mov     rcx, cs:qword_18011B9C0
0x180043413  lea     r8, ?PathPrefixGlobal@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixGlobal
0x18004341a  cmp     cs:qword_18011B9C8, r15
0x180043421  cmova   r8, cs:?PathPrefixGlobal@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixGlobal
  ... truncated ...
```
