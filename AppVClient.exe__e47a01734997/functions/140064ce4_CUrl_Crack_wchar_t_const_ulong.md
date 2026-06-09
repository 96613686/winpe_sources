# CUrl::Crack(wchar_t const *,ulong)

- ea: `0x140064ce4`
- end: `0x1400658ad`
- name: `?Crack@CUrl@@QEAA_NPEB_WK@Z`
- size: `3017`
- prototype: `bool __fastcall(CUrl *__hidden this, const wchar_t *Str, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005b1e0`

## callees

- `0x140004280`
- `0x140004558`
- `0x140004910`
- `0x1400050e0`
- `0x140006061`
- `0x1400060e8`
- `0x140006304`
- `0x140007404`
- `0x140013cc0`
- `0x140018c64`
- `0x140019da0`
- `0x14001a08c`
- `0x14001a100`
- `0x140020c60`
- `0x140064ce4`
- `0x1400658b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140064ecf`
- `KERNEL32!GetLastError` at `0x140064f1d`
- `KERNEL32!GetLastError` at `0x14006505c`
- `KERNEL32!GetLastError` at `0x1400650b1`
- `KERNEL32!GetLastError` at `0x140065564`
- `KERNEL32!GetLastError` at `0x140065600`
- `KERNEL32!GetLastError` at `0x1400656df`
- `KERNEL32!GetLastError` at `0x14006572d`
- `KERNEL32!GetLastError` at `0x140065786`
- `KERNEL32!GetLastError` at `0x140064ecf`
- `KERNEL32!GetLastError` at `0x140064f1d`
- `KERNEL32!GetLastError` at `0x14006505c`
- `KERNEL32!GetLastError` at `0x1400650b1`
- `KERNEL32!GetLastError` at `0x140065564`
- `KERNEL32!GetLastError` at `0x140065600`
- `KERNEL32!GetLastError` at `0x1400656df`
- `KERNEL32!GetLastError` at `0x14006572d`
- `KERNEL32!GetLastError` at `0x140065786`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1400650cd`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x1400650cd`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140064e5c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140064e5c`
- `WININET!InternetCanonicalizeUrlW` at `0x140064ec5`
- `WININET!InternetCanonicalizeUrlW` at `0x140064f13`
- `WININET!InternetCanonicalizeUrlW` at `0x140064ec5`
- `WININET!InternetCanonicalizeUrlW` at `0x140064f13`
- `WININET!InternetCreateUrlW` at `0x1400656d2`
- `WININET!InternetCreateUrlW` at `0x140065723`
- `WININET!InternetCreateUrlW` at `0x1400656d2`
- `WININET!InternetCreateUrlW` at `0x140065723`
- `WININET!InternetCrackUrlW` at `0x140065050`
- `WININET!InternetCrackUrlW` at `0x140065050`
- `Normaliz!IdnToNameprepUnicode` at `0x140065556`
- `Normaliz!IdnToNameprepUnicode` at `0x1400655a3`
- `Normaliz!IdnToNameprepUnicode` at `0x1400655f4`
- `Normaliz!IdnToNameprepUnicode` at `0x140065556`
- `Normaliz!IdnToNameprepUnicode` at `0x1400655a3`
- `Normaliz!IdnToNameprepUnicode` at `0x1400655f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall CUrl::Crack(CUrl *this, const wchar_t *Str)
{
  char *v2; // r15
  _WORD *v3; // rcx
  _WORD *v4; // rcx
  _WORD *v5; // rcx
  LPWSTR *lpszHostName; // r12
  LPWSTR v7; // rcx
  char *v8; // r14
  char *v9; // rcx
  _WORD *v10; // rcx
  _WORD *v11; // rcx
  unsigned __int64 v12; // r13
  __int64 v13; // rbx
  unsigned __int64 v14; // rbx
  WCHAR *v15; // rsi
  WCHAR *v16; // rdi
  const WCHAR *v17; // rbx
  WCHAR *v18; // rcx
  DWORD v19; // esi
  size_t v20; // rbx
  bool v21; // zf
  __int64 v22; // r8
  wchar_t *v23; // r9
  unsigned __int64 v24; // rdx
  const wchar_t *v25; // rsi
  unsigned __int64 v26; // rax
  wchar_t *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // r8
  const void *v30; // r9
  unsigned __int64 v31; // rdx
  LPWSTR v32; // rax
  __int64 v33; // rbx
  __int64 v34; // r8
  const void *v35; // r9
  unsigned __int64 v36; // rdx
  char *v37; // rax
  unsigned __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // r8
  const void *v41; // r9
  unsigned __int64 v42; // rdx
  char *v43; // rax
  unsigned __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // r8
  const void *v47; // r9
  unsigned __int64 v48; // rdx
  char *v49; // rax
  __int64 v50; // rbx
  __int64 v51; // r8
  const void *v52; // r9
  char **v53; // rcx
  unsigned __int64 v54; // rdx
  char *v55; // rax
  __int64 v56; // rbx
  const wchar_t *v57; // rcx
  __int64 last_of; // rax
  unsigned __int64 v59; // rbx
  unsigned __int64 v60; // rcx
  unsigned __int64 v61; // rax
  unsigned __int64 v62; // rax
  unsigned __int64 v63; // r8
  char *v64; // rax
  bool v65; // cc
  WCHAR *v66; // r14
  WCHAR *v67; // rbx
  const WCHAR *v68; // rdx
  __int64 v69; // r8
  DWORD LastError; // eax
  const WCHAR *v71; // rdx
  int cchNameprepChar; // esi
  const WCHAR *v73; // rdx
  unsigned __int64 v74; // rdx
  LPWSTR v75; // rax
  WCHAR *v76; // rcx
  __int64 v77; // rsi
  __int64 v78; // rax
  WCHAR *v79; // r12
  WCHAR *v80; // rsi
  __int64 v81; // r8
  WCHAR *v82; // rcx
  DWORD dwBufferLength; // [rsp+30h] [rbp-D0h] BYREF
  char *v85; // [rsp+38h] [rbp-C8h]
  WCHAR *v86; // [rsp+40h] [rbp-C0h]
  _QWORD *v87; // [rsp+48h] [rbp-B8h]
  _QWORD *v88; // [rsp+50h] [rbp-B0h]
  wchar_t *String[3]; // [rsp+58h] [rbp-A8h] BYREF
  void *v90[3]; // [rsp+70h] [rbp-90h] BYREF
  void *v91[3]; // [rsp+88h] [rbp-78h] BYREF
  void *v92[3]; // [rsp+A0h] [rbp-60h] BYREF
  void *v93[3]; // [rsp+B8h] [rbp-48h] BYREF
  void *Src[3]; // [rsp+D0h] [rbp-30h] BYREF
  char *v95; // [rsp+E8h] [rbp-18h]
  LPCWSTR lpszUrl; // [rsp+F0h] [rbp-10h]
  WCHAR *v97; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v98; // [rsp+100h] [rbp+0h]
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+110h] [rbp+10h] BYREF
  __int128 v100; // [rsp+180h] [rbp+80h] BYREF
  __int64 v101; // [rsp+190h] [rbp+90h]
  __int64 v102; // [rsp+198h] [rbp+98h]

  lpszUrl = Str;
  v2 = (char *)this;
  v98 = (unsigned __int64 *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  if ( *((_QWORD *)this + 3) > 7u )
    this = *(CUrl **)this;
  *(_WORD *)this = 0;
  *((_QWORD *)v2 + 14) = 0;
  if ( *((_QWORD *)v2 + 15) <= 7u )
    v3 = v2 + 96;
  else
    v3 = (_WORD *)*((_QWORD *)v2 + 12);
  *v3 = 0;
  *((_DWORD *)v2 + 32) = 0;
  v2[132] = 0;
  v95 = v2 + 32;
  v87 = v2 + 48;
  *((_QWORD *)v2 + 6) = 0;
  if ( *((_QWORD *)v2 + 7) <= 7u )
    v4 = v2 + 32;
  else
    v4 = (_WORD *)*((_QWORD *)v2 + 4);
  *v4 = 0;
  v85 = v2 + 64;
  v88 = v2 + 80;
  *((_QWORD *)v2 + 10) = 0;
  if ( *((_QWORD *)v2 + 11) <= 7u )
    v5 = v2 + 64;
  else
    v5 = (_WORD *)*((_QWORD *)v2 + 8);
  *v5 = 0;
  lpszHostName = (LPWSTR *)(v2 + 136);
  *((_QWORD *)v2 + 19) = 0;
  if ( *((_QWORD *)v2 + 20) <= 7u )
    v7 = (LPWSTR)(v2 + 136);
  else
    v7 = *lpszHostName;
  *v7 = 0;
  *((_WORD *)v2 + 84) = 0;
  v8 = v2 + 176;
  *((_QWORD *)v2 + 24) = 0;
  if ( *((_QWORD *)v2 + 25) <= 7u )
    v9 = v2 + 176;
  else
    v9 = *(char **)v8;
  *(_WORD *)v9 = 0;
  *((_QWORD *)v2 + 28) = 0;
  if ( *((_QWORD *)v2 + 29) <= 7u )
    v10 = v2 + 208;
  else
    v10 = (_WORD *)*((_QWORD *)v2 + 26);
  *v10 = 0;
  *((_QWORD *)v2 + 32) = 0;
  if ( *((_QWORD *)v2 + 33) <= 7u )
    v11 = v2 + 240;
  else
    v11 = (_WORD *)*((_QWORD *)v2 + 30);
  *v11 = 0;
  *((_DWORD *)v2 + 76) = 0;
  if ( !Str )
    goto LABEL_173;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( Str[v13] );
  if ( !(_DWORD)v13 )
  {
LABEL_173:
    *((_DWORD *)v2 + 76) = 87;
    return 0;
  }
  if ( !wcsstr(Str, L"://") )
  {
    *((_DWORD *)v2 + 76) = 12008;
    return 0;
  }
  dwBufferLength = v13 + 32;
  v14 = saturated_mul((unsigned int)(v13 + 32), 2u);
  v15 = (WCHAR *)operator new[](v14);
  v86 = v15;
  memset_0(v15, 0, v14);
  v16 = v15;
  v97 = v15;
  v17 = lpszUrl;
  if ( !InternetCanonicalizeUrlW(lpszUrl, v15, &dwBufferLength, 0) )
  {
    if ( GetLastError() != 122 )
    {
      *((_DWORD *)v2 + 76) = GetLastError();
      v18 = v15;
      goto LABEL_35;
    }
    v16 = (WCHAR *)operator new[](saturated_mul(dwBufferLength, 2u));
    v97 = v16;
    operator delete(v15);
    if ( !InternetCanonicalizeUrlW(v17, v16, &dwBufferLength, 0) )
    {
      *((_DWORD *)v2 + 76) = GetLastError();
LABEL_34:
      v18 = v16;
LABEL_35:
      operator delete(v18);
      return 0;
    }
    v86 = v16;
  }
  v19 = dwBufferLength + 1;
  std::vector<wchar_t>::vector<wchar_t>(String, dwBufferLength + 1);
  v20 = 2LL * v19;
  memset_0(String[0], 0, v20);
  std::vector<wchar_t>::vector<wchar_t>(Src, v19);
  memset_0(Src[0], 0, v20);
  std::vector<wchar_t>::vector<wchar_t>(v93, v19);
  memset_0(v93[0], 0, v20);
  std::vector<wchar_t>::vector<wchar_t>(v92, v19);
  memset_0(v92[0], 0, v20);
  std::vector<wchar_t>::vector<wchar_t>(v91, v19);
  memset_0(v91[0], 0, v20);
  std::vector<wchar_t>::vector<wchar_t>(v90, v19);
  memset_0(v90[0], 0, v20);
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszScheme = String[0];
  UrlComponents.dwSchemeLength = v19;
  UrlComponents.lpszHostName = (LPWSTR)Src[0];
  UrlComponents.dwHostNameLength = v19;
  UrlComponents.lpszUserName = (LPWSTR)v93[0];
  UrlComponents.dwUserNameLength = v19;
  UrlComponents.lpszPassword = (LPWSTR)v92[0];
  UrlComponents.dwPasswordLength = v19;
  UrlComponents.lpszUrlPath = (LPWSTR)v91[0];
  UrlComponents.dwUrlPathLength = v19;
  UrlComponents.lpszExtraInfo = (LPWSTR)v90[0];
  UrlComponents.dwExtraInfoLength = v19;
  if ( !InternetCrackUrlW(v16, v19, 0x90000000, &UrlComponents) )
  {
    *((_DWORD *)v2 + 76) = GetLastError();
    std::vector<wchar_t>::~vector<wchar_t>((char **)v90);
    std::vector<wchar_t>::~vector<wchar_t>((char **)v91);
    std::vector<wchar_t>::~vector<wchar_t>((char **)v92);
    std::vector<wchar_t>::~vector<wchar_t>((char **)v93);
    std::vector<wchar_t>::~vector<wchar_t>((char **)Src);
    std::vector<wchar_t>::~vector<wchar_t>((char **)String);
    v21 = v86 == 0;
    goto LABEL_163;
  }
  _wcslwr_s(String[0], v19);
  v23 = String[0];
  v24 = -1;
  do
    ++v24;
  while ( String[0][v24] );
  v25 = (const wchar_t *)(v2 + 96);
  v26 = *((_QWORD *)v2 + 15);
  if ( v24 > v26 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 12,
      v24,
      v22,
      String[0]);
  }
  else
  {
    if ( v26 <= 7 )
      v27 = (wchar_t *)(v2 + 96);
    else
      v27 = *(wchar_t **)v25;
    v86 = v27;
    *((_QWORD *)v2 + 14) = v24;
    v28 = v24;
    memmove_0(v27, v23, 2 * v24);
    v86[v28] = 0;
  }
  *((_DWORD *)v2 + 32) = UrlComponents.nScheme;
  v30 = Src[0];
  v31 = -1;
  do
    ++v31;
  while ( *((_WORD *)Src[0] + v31) );
  if ( v31 > *((_QWORD *)v2 + 20) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 17,
      v31,
      v29,
      Src[0]);
  }
  else
  {
    if ( *((_QWORD *)v2 + 20) <= 7u )
      v32 = (LPWSTR)(v2 + 136);
    else
      v32 = *lpszHostName;
    v86 = v32;
    *((_QWORD *)v2 + 19) = v31;
    v33 = v31;
    memmove_0(v32, v30, 2 * v31);
    v86[v33] = 0;
  }
  *((_WORD *)v2 + 84) = UrlComponents.nPort;
  v35 = v93[0];
  v36 = -1;
  do
    ++v36;
  while ( *((_WORD *)v93[0] + v36) );
  v37 = v2 + 32;
  v38 = *((_QWORD *)v2 + 7);
  if ( v36 > v38 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 4,
      v36,
      v34,
      v93[0]);
  }
  else
  {
    if ( v38 > 7 )
    {
      v37 = *(char **)v37;
      v95 = v37;
    }
    *v87 = v36;
    v39 = 2 * v36;
    memmove_0(v37, v35, 2 * v36);
    *(_WORD *)&v95[v39] = 0;
  }
  v41 = v92[0];
  v42 = -1;
  do
    ++v42;
  while ( *((_WORD *)v92[0] + v42) );
  v43 = v2 + 64;
  v44 = *((_QWORD *)v2 + 11);
  if ( v42 > v44 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 8,
      v42,
      v40,
      v92[0]);
  }
  else
  {
    if ( v44 > 7 )
    {
      v43 = *(char **)v43;
      v85 = v43;
    }
    *v88 = v42;
    v45 = 2 * v42;
    memmove_0(v43, v41, 2 * v42);
    *(_WORD *)&v85[v45] = 0;
  }
  v47 = v91[0];
  v48 = -1;
  do
    ++v48;
  while ( *((_WORD *)v91[0] + v48) );
  if ( v48 > *((_QWORD *)v2 + 25) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 22,
      v48,
      v46,
      v91[0]);
  }
  else
  {
    if ( *((_QWORD *)v2 + 25) <= 7u )
      v49 = v2 + 176;
    else
      v49 = *(char **)v8;
    v85 = v49;
    *((_QWORD *)v2 + 24) = v48;
    v50 = 2 * v48;
    memmove_0(v49, v47, 2 * v48);
    *(_WORD *)&v85[v50] = 0;
  }
  v52 = v90[0];
  v53 = (char **)(v2 + 272);
  v54 = -1;
  do
    ++v54;
  while ( *((_WORD *)v90[0] + v54) );
  if ( v54 > *((_QWORD *)v2 + 37) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v53, v54, v51, v90[0]);
  }
  else
  {
    if ( *((_QWORD *)v2 + 37) <= 7u )
      v55 = v2 + 272;
    else
      v55 = *v53;
    v85 = v55;
    *((_QWORD *)v2 + 36) = v54;
    v56 = 2 * v54;
    memmove_0(v55, v52, 2 * v54);
    *(_WORD *)&v85[v56] = 0;
  }
  switch ( UrlComponents.nScheme )
  {
    case INTERNET_SCHEME_HTTP:
      if ( !*((_WORD *)v2 + 84) )
        *((_WORD *)v2 + 84) = 80;
      break;
    case INTERNET_SCHEME_HTTPS:
      v2[132] = 1;
      if ( !*((_WORD *)v2 + 84) )
        *((_WORD *)v2 + 84) = 443;
      break;
    case INTERNET_SCHEME_UNKNOWN:
      if ( *((_QWORD *)v2 + 15) <= 7u )
        v57 = (const wchar_t *)(v2 + 96);
      else
        v57 = *(const wchar_t **)v25;
      if ( *((_QWORD *)v2 + 14) == 4 && !wmemcmp(v57, L"rtsp", 4u) )
      {
        if ( !*((_WORD *)v2 + 84) )
          *((_WORD *)v2 + 84) = 554;
      }
      else
      {
        if ( *((_QWORD *)v2 + 15) > 7u )
          v25 = *(const wchar_t **)v25;
        if ( *((_QWORD *)v2 + 14) == 5 && !wmemcmp(v25, L"rtsps", 5u) )
        {
          v2[132] = 1;
          if ( !*((_WORD *)v2 + 84) )
            *((_WORD *)v2 + 84) = 322;
        }
      }
      break;
  }
  last_of = std::wstring::find_last_of(v2 + 176, L"/");
  v59 = last_of;
  if ( last_of == -1 && (last_of = std::wstring::find_last_of(v2 + 176, L"\\"), v59 = last_of, last_of == -1) )
  {
    std::wstring::operator=(v2 + 208, v2 + 176);
  }
  else
  {
    v60 = last_of + 1;
    v61 = *((_QWORD *)v2 + 24);
    v102 = 0;
    v101 = 0;
    v100 = 0;
    if ( v61 < v60 )
      std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
    v62 = v61 - v60;
    v63 = -1;
    if ( v62 != -1 )
      v63 = v62;
    if ( *((_QWORD *)v2 + 25) <= 7u )
      v64 = v2 + 176;
    else
      v64 = *(char **)v8;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v100, &v64[2 * v60], v63);
    std::wstring::operator=((char **)v2 + 26, (__int64)&v100);
    std::wstring::~wstring((char **)&v100);
    if ( *((_QWORD *)v2 + 24) < v59 )
      v59 = *((_QWORD *)v2 + 24);
    v65 = *((_QWORD *)v2 + 25) <= 7u;
    v102 = 0;
    v101 = 0;
    v100 = 0;
    if ( !v65 )
      v8 = *(char **)v8;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v100, v8, v59);
    std::wstring::operator=((char **)v2 + 30, (__int64)&v100);
    std::wstring::~wstring((char **)&v100);
  }
  v66 = (WCHAR *)operator new[](0x4ECu);
  memset_0(v66, 0, 0x4ECu);
  v67 = v66;
  v88 = v66;
  if ( *((_QWORD *)v2 + 20) <= 7u )
    v68 = (const WCHAR *)(v2 + 136);
  else
    v68 = *lpszHostName;
  if ( !IdnToNameprepUnicode(2u, v68, *((_DWORD *)v2 + 38) + 1, v66, 630) )
  {
    LastError = GetLastError();
    *((_DWORD *)v2 + 76) = LastError;
    if ( LastError != 122 )
    {
      v76 = v66;
LABEL_161:
      operator delete(v76);
      goto LABEL_162;
    }
    if ( *((_QWORD *)v2 + 20) <= 7u )
      v71 = (const WCHAR *)(v2 + 136);
    else
      v71 = *lpszHostName;
    cchNameprepChar = IdnToNameprepUnicode(2u, v71, *((_DWORD *)v2 + 38) + 1, v66, 0);
    v67 = (WCHAR *)operator new[](saturated_mul(cchNameprepChar, 2u));
    v88 = v67;
    operator delete(v66);
    if ( *((_QWORD *)v2 + 20) <= 7u )
      v73 = (const WCHAR *)(v2 + 136);
    else
      v73 = *lpszHostName;
    if ( !IdnToNameprepUnicode(2u, v73, *((_DWORD *)v2 + 38) + 1, v67, cchNameprepChar) )
    {
      *((_DWORD *)v2 + 76) = GetLastError();
LABEL_160:
      v76 = v67;
      goto LABEL_161;
    }
    v66 = v67;
  }
  v74 = -1;
  do
    ++v74;
  while ( v66[v74] );
  if ( v74 > *((_QWORD *)v2 + 20) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)v2 + 17,
      v74,
      v69,
      v66);
  }
  else
  {
    if ( *((_QWORD *)v2 + 20) <= 7u )
      v75 = (LPWSTR)(v2 + 136);
    else
      v75 = *lpszHostName;
    v85 = (char *)v75;
    *((_QWORD *)v2 + 19) = v74;
    v77 = 2 * v74;
    memmove_0(v75, v66, 2 * v74);
    *(_WORD *)&v85[v77] = 0;
  }
  if ( *((_QWORD *)v2 + 20) > 7u )
  {
    UrlComponents.lpszHostName = *lpszHostName;
    lpszHostName = (LPWSTR *)UrlComponents.lpszHostName;
  }
  else
  {
    UrlComponents.lpszHostName = (LPWSTR)(v2 + 136);
  }
  v78 = -1;
  do
    ++v78;
  while ( *((_WORD *)lpszHostName + v78) );
  UrlComponents.dwHostNameLength = v78;
  v79 = (WCHAR *)operator new[](saturated_mul(dwBufferLength, 2u));
  v80 = v79;
  v87 = v79;
  if ( !InternetCreateUrlW(&UrlComponents, 0, v79, &dwBufferLength) )
  {
    if ( GetLastError() != 122 )
    {
      *((_DWORD *)v2 + 76) = GetLastError();
      v82 = v79;
LABEL_159:
      operator delete(v82);
      if ( !v67 )
      {
LABEL_162:
        std::vector<wchar_t>::~vector<wchar_t>((char **)v90);
        std::vector<wchar_t>::~vector<wchar_t>((char **)v91);
        std::vector<wchar_t>::~vector<wchar_t>((char **)v92);
        std::vector<wchar_t>::~vector<wchar_t>((char **)v93);
        std::vector<wchar_t>::~vector<wchar_t>((char **)Src);
        std::vector<wchar_t>::~vector<wchar_t>((char **)String);
        v21 = v16 == 0;
LABEL_163:
        if ( v21 )
          return 0;
        goto LABEL_34;
      }
      goto LABEL_160;
    }
    v80 = (WCHAR *)operator new[](saturated_mul(dwBufferLength, 2u));
    v87 = v80;
    operator delete(v79);
    if ( !InternetCreateUrlW(&UrlComponents, 0, v80, &dwBufferLength) )
    {
      *((_DWORD *)v2 + 76) = GetLastError();
      v82 = v80;
      goto LABEL_159;
    }
    v79 = v80;
  }
  do
    ++v12;
  while ( v79[v12] );
  if ( v12 > *((_QWORD *)v2 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>((char **)v2, v12, v81, v79);
  }
  else
  {
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(char **)v2;
    *v98 = v12;
    memmove_0(v2, v79, 2 * v12);
    *(_WORD *)&v2[2 * v12] = 0;
  }
  if ( v79 )
    operator delete(v80);
  if ( v67 )
    operator delete(v67);
  std::vector<wchar_t>::~vector<wchar_t>((char **)v90);
  std::vector<wchar_t>::~vector<wchar_t>((char **)v91);
  std::vector<wchar_t>::~vector<wchar_t>((char **)v92);
  std::vector<wchar_t>::~vector<wchar_t>((char **)v93);
  std::vector<wchar_t>::~vector<wchar_t>((char **)Src);
  std::vector<wchar_t>::~vector<wchar_t>((char **)String);
  if ( v16 )
    operator delete(v16);
  return 1;
}

```

## disassembly

```asm
0x140064ce4  mov     [rsp-8+arg_10], rbx
0x140064ce9  push    rbp
0x140064cea  push    rsi
0x140064ceb  push    rdi
0x140064cec  push    r12
0x140064cee  push    r13
0x140064cf0  push    r14
0x140064cf2  push    r15
0x140064cf4  lea     rbp, [rsp-0B0h]
0x140064cfc  sub     rsp, 1B0h
0x140064d03  mov     rax, cs:__security_cookie
0x140064d0a  xor     rax, rsp
0x140064d0d  mov     [rbp+0E0h+var_40], rax
0x140064d14  mov     r8, rdx
0x140064d17  mov     [rbp+0E0h+lpszUrl], rdx
0x140064d1b  mov     r15, rcx
0x140064d1e  xor     edi, edi
0x140064d20  lea     rax, [rcx+10h]
0x140064d24  mov     [rbp+0E0h+var_E0], rax
0x140064d28  mov     [rax], rdi
0x140064d2b  cmp     qword ptr [rcx+18h], 7
0x140064d30  jbe     short loc_140064D35
0x140064d32  mov     rcx, [rcx]
0x140064d35  mov     [rcx], di
0x140064d38  mov     [r15+70h], rdi
0x140064d3c  cmp     qword ptr [r15+78h], 7
0x140064d41  jbe     short loc_140064D49
0x140064d43  mov     rcx, [r15+60h]
0x140064d47  jmp     short loc_140064D4D
0x140064d49  lea     rcx, [r15+60h]
0x140064d4d  mov     [rcx], di
0x140064d50  mov     [r15+80h], edi
0x140064d57  mov     [r15+84h], dil
0x140064d5e  lea     rax, [r15+20h]
0x140064d62  mov     [rbp+0E0h+var_F8], rax
0x140064d66  lea     rcx, [rax+10h]
0x140064d6a  mov     [rsp+1E0h+var_198], rcx
0x140064d6f  mov     [rcx], rdi
0x140064d72  cmp     qword ptr [rax+18h], 7
0x140064d77  jbe     short loc_140064D7E
0x140064d79  mov     rcx, [rax]
0x140064d7c  jmp     short loc_140064D81
0x140064d7e  mov     rcx, rax
0x140064d81  mov     [rcx], di
0x140064d84  lea     rax, [r15+40h]
0x140064d88  mov     [rsp+1E0h+var_1A8], rax
0x140064d8d  lea     rcx, [rax+10h]
0x140064d91  mov     [rsp+1E0h+var_190], rcx
0x140064d96  mov     [rcx], rdi
0x140064d99  cmp     qword ptr [rax+18h], 7
0x140064d9e  jbe     short loc_140064DA5
0x140064da0  mov     rcx, [rax]
0x140064da3  jmp     short loc_140064DA8
0x140064da5  mov     rcx, rax
0x140064da8  mov     [rcx], di
0x140064dab  lea     r12, [r15+88h]
0x140064db2  mov     [r12+10h], rdi
0x140064db7  cmp     qword ptr [r12+18h], 7
0x140064dbd  jbe     short loc_140064DC5
0x140064dbf  mov     rcx, [r12]
0x140064dc3  jmp     short loc_140064DC8
0x140064dc5  mov     rcx, r12
0x140064dc8  mov     [rcx], di
0x140064dcb  mov     [r15+0A8h], di
0x140064dd3  lea     r14, [r15+0B0h]
0x140064dda  mov     [r14+10h], rdi
0x140064dde  cmp     qword ptr [r14+18h], 7
0x140064de3  jbe     short loc_140064DEA
0x140064de5  mov     rcx, [r14]
0x140064de8  jmp     short loc_140064DED
0x140064dea  mov     rcx, r14
0x140064ded  mov     [rcx], di
0x140064df0  lea     rax, [r15+0D0h]
0x140064df7  mov     [rax+10h], rdi
0x140064dfb  cmp     qword ptr [rax+18h], 7
0x140064e00  jbe     short loc_140064E07
0x140064e02  mov     rcx, [rax]
0x140064e05  jmp     short loc_140064E0A
0x140064e07  mov     rcx, rax
0x140064e0a  mov     [rcx], di
0x140064e0d  lea     rax, [r15+0F0h]
0x140064e14  mov     [rax+10h], rdi
0x140064e18  cmp     qword ptr [rax+18h], 7
0x140064e1d  jbe     short loc_140064E24
0x140064e1f  mov     rcx, [rax]
0x140064e22  jmp     short loc_140064E27
0x140064e24  mov     rcx, rax
0x140064e27  mov     [rcx], di
0x140064e2a  mov     [r15+130h], edi
0x140064e31  test    r8, r8
0x140064e34  jz      loc_140065870
0x140064e3a  or      r13, 0FFFFFFFFFFFFFFFFh
0x140064e3e  mov     rbx, r13
0x140064e41  inc     rbx
0x140064e44  cmp     [rdx+rbx*2], di
0x140064e48  jnz     short loc_140064E41
0x140064e4a  test    ebx, ebx
0x140064e4c  jz      loc_140065870
0x140064e52  lea     rdx, SubStr; "://"
0x140064e59  mov     rcx, r8; Str
0x140064e5c  call    cs:__imp_wcsstr
0x140064e62  test    rax, rax
0x140064e65  jnz     short loc_140064E77
0x140064e67  mov     dword ptr [r15+130h], 2EE8h
0x140064e72  jmp     loc_14006587B
0x140064e77  lea     eax, [rbx+20h]
0x140064e7a  mov     [rsp+1E0h+dwBufferLength], eax
0x140064e7e  mov     ecx, eax
0x140064e80  mov     eax, 2
0x140064e85  mul     rcx
0x140064e88  mov     rbx, rax
0x140064e8b  cmovb   rbx, r13
0x140064e8f  mov     rcx, rbx; unsigned __int64
0x140064e92  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140064e97  mov     rsi, rax
0x140064e9a  mov     [rsp+1E0h+var_1A0], rax
0x140064e9f  mov     r8, rbx; Size
0x140064ea2  xor     edx, edx; Val
0x140064ea4  mov     rcx, rax; void *
0x140064ea7  call    memset_0
0x140064eac  mov     rdi, rsi
0x140064eaf  mov     [rbp+0E0h+var_E8], rsi
0x140064eb3  xor     r9d, r9d; dwFlags
0x140064eb6  lea     r8, [rsp+1E0h+dwBufferLength]; lpdwBufferLength
0x140064ebb  mov     rdx, rsi; lpszBuffer
0x140064ebe  mov     rbx, [rbp+0E0h+lpszUrl]
0x140064ec2  mov     rcx, rbx; lpszUrl
0x140064ec5  call    cs:__imp_InternetCanonicalizeUrlW
0x140064ecb  test    eax, eax
0x140064ecd  jnz     short loc_140064F3C
0x140064ecf  call    cs:__imp_GetLastError
0x140064ed5  cmp     eax, 7Ah ; 'z'
0x140064ed8  jnz     loc_1400650B1
0x140064ede  mov     ecx, [rsp+1E0h+dwBufferLength]
0x140064ee2  mov     eax, 2
0x140064ee7  mul     rcx
0x140064eea  cmovb   rax, r13
0x140064eee  mov     rcx, rax; unsigned __int64
0x140064ef1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140064ef6  mov     rdi, rax
0x140064ef9  mov     [rbp+0E0h+var_E8], rax
0x140064efd  mov     rcx, rsi; Block
0x140064f00  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140064f05  xor     r9d, r9d; dwFlags
0x140064f08  lea     r8, [rsp+1E0h+dwBufferLength]; lpdwBufferLength
0x140064f0d  mov     rdx, rdi; lpszBuffer
0x140064f10  mov     rcx, rbx; lpszUrl
0x140064f13  call    cs:__imp_InternetCanonicalizeUrlW
0x140064f19  test    eax, eax
0x140064f1b  jnz     short loc_140064F37
0x140064f1d  call    cs:__imp_GetLastError
0x140064f23  mov     [r15+130h], eax
0x140064f2a  mov     rcx, rdi; Block
0x140064f2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140064f32  jmp     loc_14006587B
0x140064f37  mov     [rsp+1E0h+var_1A0], rdi
0x140064f3c  mov     esi, [rsp+1E0h+dwBufferLength]
0x140064f40  inc     esi
0x140064f42  mov     ebx, esi
0x140064f44  mov     edx, esi
0x140064f46  lea     rcx, [rsp+1E0h+String]
0x140064f4b  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064f50  nop
0x140064f51  add     rbx, rbx
0x140064f54  mov     r8, rbx; Size
0x140064f57  xor     edx, edx; Val
0x140064f59  mov     rcx, [rsp+1E0h+String]; void *
0x140064f5e  call    memset_0
0x140064f63  mov     edx, esi
0x140064f65  lea     rcx, [rbp+0E0h+Src]
0x140064f69  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064f6e  nop
0x140064f6f  mov     r8, rbx; Size
0x140064f72  xor     edx, edx; Val
0x140064f74  mov     rcx, [rbp+0E0h+Src]; void *
0x140064f78  call    memset_0
0x140064f7d  mov     edx, esi
0x140064f7f  lea     rcx, [rbp+0E0h+var_128]
0x140064f83  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064f88  nop
0x140064f89  mov     r8, rbx; Size
0x140064f8c  xor     edx, edx; Val
0x140064f8e  mov     rcx, [rbp+0E0h+var_128]; void *
0x140064f92  call    memset_0
0x140064f97  mov     edx, esi
0x140064f99  lea     rcx, [rbp+0E0h+var_140]
0x140064f9d  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064fa2  nop
0x140064fa3  mov     r8, rbx; Size
0x140064fa6  xor     edx, edx; Val
0x140064fa8  mov     rcx, [rbp+0E0h+var_140]; void *
0x140064fac  call    memset_0
0x140064fb1  mov     edx, esi
0x140064fb3  lea     rcx, [rbp+0E0h+var_158]
0x140064fb7  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064fbc  nop
0x140064fbd  mov     r8, rbx; Size
0x140064fc0  xor     edx, edx; Val
0x140064fc2  mov     rcx, [rbp+0E0h+var_158]; void *
0x140064fc6  call    memset_0
0x140064fcb  mov     edx, esi
0x140064fcd  lea     rcx, [rsp+1E0h+var_170]
0x140064fd2  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x140064fd7  nop
0x140064fd8  mov     r8, rbx; Size
0x140064fdb  xor     edx, edx; Val
0x140064fdd  mov     rcx, [rsp+1E0h+var_170]; void *
0x140064fe2  call    memset_0
0x140064fe7  mov     ebx, 68h ; 'h'
0x140064fec  mov     r8d, ebx; Size
0x140064fef  xor     edx, edx; Val
0x140064ff1  lea     rcx, [rbp+0E0h+UrlComponents]; void *
0x140064ff5  call    memset_0
0x140064ffa  mov     [rbp+0E0h+UrlComponents.dwStructSize], ebx
0x140064ffd  mov     rax, [rsp+1E0h+String]
0x140065002  mov     [rbp+0E0h+UrlComponents.lpszScheme], rax
0x140065006  mov     [rbp+0E0h+UrlComponents.dwSchemeLength], esi
0x140065009  mov     rax, [rbp+0E0h+Src]
0x14006500d  mov     [rbp+0E0h+UrlComponents.lpszHostName], rax
0x140065011  mov     [rbp+0E0h+UrlComponents.dwHostNameLength], esi
0x140065014  mov     rax, [rbp+0E0h+var_128]
0x140065018  mov     [rbp+0E0h+UrlComponents.lpszUserName], rax
0x14006501c  mov     [rbp+0E0h+UrlComponents.dwUserNameLength], esi
0x14006501f  mov     rax, [rbp+0E0h+var_140]
0x140065023  mov     [rbp+0E0h+UrlComponents.lpszPassword], rax
0x140065027  mov     [rbp+0E0h+UrlComponents.dwPasswordLength], esi
0x14006502a  mov     rax, [rbp+0E0h+var_158]
0x14006502e  mov     [rbp+0E0h+UrlComponents.lpszUrlPath], rax
0x140065032  mov     [rbp+0E0h+UrlComponents.dwUrlPathLength], esi
0x140065035  mov     rax, [rsp+1E0h+var_170]
0x14006503a  mov     [rbp+0E0h+UrlComponents.lpszExtraInfo], rax
0x14006503e  mov     [rbp+0E0h+UrlComponents.dwExtraInfoLength], esi
0x140065041  lea     r9, [rbp+0E0h+UrlComponents]; lpUrlComponents
0x140065045  mov     r8d, 90000000h; dwFlags
0x14006504b  mov     edx, esi; dwUrlLength
0x14006504d  mov     rcx, rdi; lpszUrl
0x140065050  call    cs:__imp_InternetCrackUrlW
0x140065056  xor     ebx, ebx
0x140065058  test    eax, eax
0x14006505a  jnz     short loc_1400650C6
0x14006505c  call    cs:__imp_GetLastError
0x140065062  mov     [r15+130h], eax
0x140065069  lea     rcx, [rsp+1E0h+var_170]
0x14006506e  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140065073  nop
0x140065074  lea     rcx, [rbp+0E0h+var_158]
0x140065078  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14006507d  nop
0x14006507e  lea     rcx, [rbp+0E0h+var_140]
0x140065082  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140065087  nop
0x140065088  lea     rcx, [rbp+0E0h+var_128]
0x14006508c  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140065091  nop
0x140065092  lea     rcx, [rbp+0E0h+Src]
0x140065096  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14006509b  nop
0x14006509c  lea     rcx, [rsp+1E0h+String]
0x1400650a1  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x1400650a6  nop
0x1400650a7  cmp     [rsp+1E0h+var_1A0], rbx
0x1400650ac  jmp     loc_1400657EB
0x1400650b1  call    cs:__imp_GetLastError
0x1400650b7  mov     [r15+130h], eax
0x1400650be  mov     rcx, rsi
0x1400650c1  jmp     loc_140064F2D
0x1400650c6  mov     edx, esi; SizeInWords
0x1400650c8  mov     rcx, [rsp+1E0h+String]; String
0x1400650cd  call    cs:__imp__wcslwr_s
0x1400650d3  mov     r9, [rsp+1E0h+String]
0x1400650d8  mov     rdx, r13
0x1400650db  inc     rdx
0x1400650de  cmp     [r9+rdx*2], bx
0x1400650e3  jnz     short loc_1400650DB
0x1400650e5  lea     rsi, [r15+60h]
0x1400650e9  mov     rax, [rsi+18h]
0x1400650ed  cmp     rdx, rax
0x1400650f0  ja      short loc_14006512A
0x1400650f2  cmp     rax, 7
0x1400650f6  jbe     short loc_1400650FD
0x1400650f8  mov     rax, [rsi]
0x1400650fb  jmp     short loc_140065100
0x1400650fd  mov     rax, rsi
0x140065100  mov     [rsp+1E0h+var_1A0], rax
0x140065105  mov     [rsi+10h], rdx
0x140065109  lea     rbx, [rdx+rdx]
0x14006510d  mov     r8, rbx; Size
0x140065110  mov     rdx, r9; Src
0x140065113  mov     rcx, rax; void *
0x140065116  call    memmove_0
0x14006511b  xor     eax, eax
0x14006511d  mov     rcx, [rsp+1E0h+var_1A0]
0x140065122  mov     [rbx+rcx], ax
0x140065126  xor     ebx, ebx
0x140065128  jmp     short loc_140065132
0x14006512a  mov     rcx, rsi
0x14006512d  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140065132  mov     eax, [rbp+0E0h+UrlComponents.nScheme]
0x140065135  mov     [r15+80h], eax
0x14006513c  mov     r9, [rbp+0E0h+Src]
  ... truncated ...
```
