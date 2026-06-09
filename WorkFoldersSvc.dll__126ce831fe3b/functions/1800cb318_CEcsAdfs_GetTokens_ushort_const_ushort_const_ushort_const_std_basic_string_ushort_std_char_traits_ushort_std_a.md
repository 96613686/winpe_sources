# CEcsAdfs::GetTokens(ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800cb318`
- end: `0x1800cc771`
- name: `?GetTokens@CEcsAdfs@@SAJPEBG00AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `5209`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pwszUrl@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006f7c0`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008108`
- `0x180008ba8`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180015150`
- `0x1800151c0`
- `0x1800158d4`
- `0x18001db58`
- `0x18001db74`
- `0x180021420`
- `0x180023c90`
- `0x180028490`
- `0x180028984`
- `0x180031910`
- `0x18003510c`
- `0x1800351a0`
- `0x180035564`
- `0x1800612bc`
- `0x18006137c`
- `0x1800675bc`
- `0x180068808`
- `0x18006b3a8`
- `0x18007f178`
- `0x1800c91d8`
- `0x1800c91fc`
- `0x1800c921c`
- `0x1800cb16c`
- `0x1800cb318`
- `0x1800ccc08`
- `0x1800cd140`
- `0x1800cd1c0`
- `0x1800cd21c`
- `0x1800cd324`
- `0x1800cd348`
- `0x1800cd3c0`
- `0x1800d27f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800cbe4e`
- `KERNEL32!GetLastError` at `0x1800cbe4e`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cb799`
- `WINHTTP!WinHttpCrackUrl` at `0x1800cb799`
- `WINHTTP!WinHttpConnect` at `0x1800cbb30`
- `WINHTTP!WinHttpConnect` at `0x1800cbb30`
- `WINHTTP!WinHttpOpen` at `0x1800cbad7`
- `WINHTTP!WinHttpOpen` at `0x1800cbad7`
- `WINHTTP!WinHttpSendRequest` at `0x1800cbc5c`
- `WINHTTP!WinHttpSendRequest` at `0x1800cbc5c`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cbcab`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800cbcab`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800cbefe`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800cbefe`
- `WINHTTP!WinHttpReadData` at `0x1800cbfbf`
- `WINHTTP!WinHttpReadData` at `0x1800cbfbf`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800cbbf3`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800cbbf3`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cbd1c`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cbe44`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cbd1c`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800cbe44`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cbb9e`
- `WINHTTP!WinHttpOpenRequest` at `0x1800cbb9e`

## string_xrefs

- `0x1800cb3d7`: `CEcsAdfs::GetTokens`
- `0x1800cba1e`: `refresh_token`
- `0x1800cba33`: `refresh_token`
- `0x1800cb917`: `/token`
- `0x1800cba62`: `grant_type=%s&%s=%s&client_id=%s&redirect_uri=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CEcsAdfs::GetTokens(LPCWSTR pwszUrl, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  _BYTE *v9; // rax
  char v10; // al
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // edx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // r10
  __int64 v25; // r14
  __int64 v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rcx
  const char *v30; // rax
  const char *v31; // r10
  const char *v32; // r11
  const char *v33; // r8
  const char *v34; // r9
  int v35; // eax
  HINTERNET v36; // rax
  const WCHAR *v37; // rax
  INTERNET_PORT v38; // r8
  HINTERNET v39; // rax
  const WCHAR *v40; // rax
  HINTERNET v41; // rax
  void *v42; // rbx
  int v43; // edx
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned __int64 v47; // r14
  int v48; // ecx
  DWORD v49; // r8d
  int v50; // ecx
  char *v51; // r9
  _BYTE *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // r10
  int v57; // r9d
  PVOID *v58; // r10
  __int64 v59; // rax
  __int64 v60; // r10
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // r10
  int v67; // r9d
  _BYTE *v68; // rdx
  __int64 v69; // rax
  unsigned int v70; // ebx
  int v72; // [rsp+40h] [rbp-478h] BYREF
  int v73; // [rsp+44h] [rbp-474h]
  char v74; // [rsp+48h] [rbp-470h]
  const char *v75; // [rsp+50h] [rbp-468h]
  __int64 v76; // [rsp+58h] [rbp-460h]
  DWORD dwBufferLength; // [rsp+60h] [rbp-458h] BYREF
  __int64 v78; // [rsp+68h] [rbp-450h]
  unsigned int Buffer; // [rsp+70h] [rbp-448h] BYREF
  __int64 v80; // [rsp+78h] [rbp-440h] BYREF
  LPVOID lpOptional; // [rsp+80h] [rbp-438h] BYREF
  __int64 v82; // [rsp+88h] [rbp-430h]
  __int64 v83; // [rsp+98h] [rbp-420h]
  HINTERNET hConnect; // [rsp+A0h] [rbp-418h] BYREF
  HINTERNET hSession; // [rsp+A8h] [rbp-410h] BYREF
  int v86; // [rsp+B0h] [rbp-408h] BYREF
  int v87; // [rsp+B4h] [rbp-404h] BYREF
  int v88; // [rsp+B8h] [rbp-400h] BYREF
  int v89; // [rsp+BCh] [rbp-3FCh] BYREF
  int v90; // [rsp+C0h] [rbp-3F8h] BYREF
  int v91; // [rsp+C4h] [rbp-3F4h] BYREF
  int v92; // [rsp+C8h] [rbp-3F0h] BYREF
  int v93; // [rsp+CCh] [rbp-3ECh] BYREF
  int v94; // [rsp+D0h] [rbp-3E8h] BYREF
  int v95; // [rsp+D4h] [rbp-3E4h] BYREF
  int v96; // [rsp+D8h] [rbp-3E0h] BYREF
  int v97; // [rsp+DCh] [rbp-3DCh] BYREF
  int v98; // [rsp+E0h] [rbp-3D8h] BYREF
  int LastFailureAsHRESULT; // [rsp+E4h] [rbp-3D4h] BYREF
  int v100; // [rsp+E8h] [rbp-3D0h] BYREF
  int v101; // [rsp+ECh] [rbp-3CCh] BYREF
  int v102; // [rsp+F0h] [rbp-3C8h] BYREF
  int v103; // [rsp+F4h] [rbp-3C4h] BYREF
  int v104; // [rsp+F8h] [rbp-3C0h] BYREF
  int v105; // [rsp+FCh] [rbp-3BCh] BYREF
  _BYTE *v106; // [rsp+100h] [rbp-3B8h]
  int pExceptionObject; // [rsp+108h] [rbp-3B0h] BYREF
  int v108; // [rsp+10Ch] [rbp-3ACh] BYREF
  int v109; // [rsp+110h] [rbp-3A8h] BYREF
  int v110; // [rsp+114h] [rbp-3A4h] BYREF
  HINTERNET hRequest; // [rsp+118h] [rbp-3A0h] BYREF
  int v112; // [rsp+120h] [rbp-398h] BYREF
  int v113; // [rsp+124h] [rbp-394h] BYREF
  __int64 v114; // [rsp+128h] [rbp-390h] BYREF
  int v115; // [rsp+130h] [rbp-388h] BYREF
  int v116; // [rsp+134h] [rbp-384h] BYREF
  _QWORD v117[3]; // [rsp+140h] [rbp-378h] BYREF
  int v118; // [rsp+158h] [rbp-360h]
  int v119; // [rsp+15Ch] [rbp-35Ch]
  __int128 v120; // [rsp+160h] [rbp-358h]
  __int64 v121; // [rsp+170h] [rbp-348h]
  __int64 v122; // [rsp+178h] [rbp-340h]
  __int64 v123; // [rsp+180h] [rbp-338h]
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+190h] [rbp-328h] BYREF
  const ATL::CAtlException *v125; // [rsp+200h] [rbp-2B8h] BYREF
  const ATL::CAtlException *v126; // [rsp+208h] [rbp-2B0h] BYREF
  _QWORD v127[3]; // [rsp+210h] [rbp-2A8h] BYREF
  _BYTE v128[32]; // [rsp+228h] [rbp-290h] BYREF
  _BYTE v129[32]; // [rsp+248h] [rbp-270h] BYREF
  _BYTE v130[16]; // [rsp+268h] [rbp-250h] BYREF
  __int64 v131; // [rsp+278h] [rbp-240h]
  _BYTE v132[16]; // [rsp+288h] [rbp-230h] BYREF
  __int64 v133; // [rsp+298h] [rbp-220h]
  _BYTE v134[16]; // [rsp+2A8h] [rbp-210h] BYREF
  __int64 v135; // [rsp+2B8h] [rbp-200h]
  _BYTE v136[16]; // [rsp+2C8h] [rbp-1F0h] BYREF
  unsigned __int64 v137; // [rsp+2D8h] [rbp-1E0h]
  _BYTE v138[32]; // [rsp+2E8h] [rbp-1D0h] BYREF
  _BYTE v139[16]; // [rsp+308h] [rbp-1B0h] BYREF
  __int64 v140; // [rsp+318h] [rbp-1A0h]
  _BYTE v141[16]; // [rsp+328h] [rbp-190h] BYREF
  __int64 v142; // [rsp+338h] [rbp-180h]
  void **v143; // [rsp+350h] [rbp-168h] BYREF
  _BYTE v144[16]; // [rsp+358h] [rbp-160h] BYREF
  __int64 v145; // [rsp+368h] [rbp-150h]
  _BYTE v146[16]; // [rsp+378h] [rbp-140h] BYREF
  __int64 v147; // [rsp+388h] [rbp-130h]
  _BYTE v148[16]; // [rsp+398h] [rbp-120h] BYREF
  __int64 v149; // [rsp+3A8h] [rbp-110h]
  _BYTE v150[16]; // [rsp+3B8h] [rbp-100h] BYREF
  __int64 v151; // [rsp+3C8h] [rbp-F0h]
  _BYTE v152[16]; // [rsp+3D8h] [rbp-E0h] BYREF
  __int64 v153; // [rsp+3E8h] [rbp-D0h]
  int v154; // [rsp+3F8h] [rbp-C0h]
  int v155; // [rsp+3FCh] [rbp-BCh]
  _BYTE v156[32]; // [rsp+400h] [rbp-B8h] BYREF
  _BYTE v157[32]; // [rsp+420h] [rbp-98h] BYREF
  _BYTE v158[32]; // [rsp+440h] [rbp-78h] BYREF
  _BYTE v159[32]; // [rsp+460h] [rbp-58h] BYREF

  v80 = a4;
  v83 = a6;
  v106 = (_BYTE *)a5;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v11 = 0;
      v10 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids);
      v9 = WPP_GLOBAL_Control;
      a4 = v80;
    }
  }
  if ( (v9[68] & 2) == 0 || v9[65] < 6u )
    goto LABEL_8;
  v10 = 1;
  v11 = 0;
LABEL_9:
  v72 = 0;
  v73 = 284;
  v74 = v10;
  v75 = "CEcsAdfs::GetTokens";
  v76 = 0;
  std::wstring::_Eos(a4, 0);
  std::wstring::_Eos(v13, v12);
  try
  {
    memset_0(&UrlComponents, v14, (unsigned int)(v14 + 104));
    v78 = 0;
    dwBufferLength = 0;
    v15 = *(_QWORD *)(a5 + 16);
    Buffer = 0;
    std::string::string(v136);
    std::wstring::wstring((__int64)v158);
    std::wstring::wstring((__int64)v130);
    std::vector<std::wstring>::vector<std::wstring>(&lpOptional);
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&v114);
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hSession);
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hConnect);
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hRequest);
    v117[0] = &JsonReader::`vftable';
    v117[1] = 0;
    v117[2] = 0;
    v118 = 1;
    v119 = 1;
    v120 = 0;
    v121 = 255;
    v122 = 0x80000;
    v123 = 8;
    v143 = &CEcsAdfs::JsonCallback::`vftable';
    std::wstring::wstring((__int64)v144);
    std::wstring::wstring((__int64)v146);
    std::wstring::wstring((__int64)v148);
    std::wstring::wstring((__int64)v150);
    std::wstring::wstring((__int64)v152);
    v154 = 0;
    v155 = 0;
    std::wstring::wstring((__int64)v134);
    std::wstring::wstring((__int64)v141);
    std::string::string(v157);
    std::wstring::wstring((__int64)v159);
    std::string::string(v132);
    std::wstring::wstring((__int64)v156);
    CEcsAdfs::ResolveAuthRequestParameters(a2, v141, v159);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v141);
    v17 = CEcsStringUtil::Utf16ToUtf8(v129, v16);
    std::string::operator=(v157, v17);
    std::string::~string(v129);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v159);
    v19 = CEcsStringUtil::Utf16ToUtf8(v129, v18);
    std::string::operator=(v132, v19);
    std::string::~string(v129);
    v20 = CEcsUri::UrlEncode(v129, v132);
    std::string::operator=(v132, v20);
    std::string::~string(v129);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, v15 != 0);
    }
    if ( v15 )
    {
      v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
      v22 = CEcsStringUtil::Utf16ToUtf8(v129, v21);
    }
    else
    {
      v22 = CEcsStringUtil::Utf16ToUtf8(v129, a3);
    }
    std::string::operator=(v136, v22);
    std::string::~string(v129);
    if ( v137 > 0x80000 )
    {
      v72 = -2147418113;
      HIWORD(v73) = 341;
      v105 = -2147418113;
      throw (long *)&v105;
    }
    LOWORD(v73) = 341;
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwHostNameLength = 1;
    UrlComponents.dwUrlPathLength = 1;
    UrlComponents.dwExtraInfoLength = 1;
    v72 = 0;
    if ( !WinHttpCrackUrl(pwszUrl, 0, 0x4000u, &UrlComponents) )
    {
      HIWORD(v73) = 355;
      pExceptionObject = EcsGetLastFailureAsHRESULT();
      throw (long *)&pExceptionObject;
    }
    LOWORD(v73) = 355;
    v72 = 0;
    if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER
      || !UrlComponents.lpszHostName
      || !UrlComponents.dwHostNameLength
      || !UrlComponents.lpszUrlPath
      || !UrlComponents.dwUrlPathLength )
    {
      v72 = -2147418113;
      HIWORD(v73) = 360;
      v104 = -2147418113;
      throw (long *)&v104;
    }
    v72 = 0;
    LOWORD(v73) = 360;
    std::wstring::assign(v158, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
    std::wstring::assign(v130, UrlComponents.lpszUrlPath, UrlComponents.dwUrlPathLength);
    v23 = std::wstring::find(v130, L"/authorize", 0);
    v24 = v23;
    v25 = -1;
    if ( v23 == -1 )
    {
      v72 = -2147418113;
      HIWORD(v73) = 368;
      v103 = -2147418113;
      throw (long *)&v103;
    }
    LOWORD(v73) = 368;
    v72 = 0;
    if ( v23 + 10 != v131 )
    {
      if ( v23 + 10 != v131 - 1
        || (v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130), *(_WORD *)(v26 + 2 * v27) != 47) )
      {
        v72 = -2147418113;
        HIWORD(v73) = 374;
        v108 = -2147418113;
        throw (long *)&v108;
      }
    }
    v72 = 0;
    LOWORD(v73) = 374;
    std::wstring::replace(v130, v24, 10, L"/token");
    std::wstring::append(v130, UrlComponents.lpszExtraInfo, UrlComponents.dwExtraInfoLength);
    v78 = 80;
    v28 = v137 + 80;
    if ( v137 >= 0xFFFFFFFFFFFFFFB0uLL )
    {
      v78 = -1;
      v72 = -2147024362;
      HIWORD(v73) = 383;
      v102 = -2147024362;
      throw (long *)&v102;
    }
    v78 = v137 + 80;
    v72 = 0;
    LOWORD(v73) = 383;
    v29 = v28 + v142;
    if ( v28 + v142 < v28 )
    {
      v78 = -1;
      v72 = -2147024362;
      HIWORD(v73) = 384;
      v101 = -2147024362;
      throw (long *)&v101;
    }
    v78 = v28 + v142;
    v72 = 0;
    LOWORD(v73) = 384;
    if ( v29 + v133 < v29 )
    {
      v78 = -1;
      v72 = -2147024362;
      HIWORD(v73) = 385;
      v100 = -2147024362;
      throw (long *)&v100;
    }
    v78 = v29 + v133;
    v72 = 0;
    LOWORD(v73) = 385;
    std::vector<char>::resize(&lpOptional);
    std::_String_val<std::_Simple_types<char>>::_Myptr(v132);
    std::_String_val<std::_Simple_types<char>>::_Myptr(v157);
    v30 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v136);
    v33 = "refresh_token";
    if ( !v15 )
      v33 = "code";
    v34 = "refresh_token";
    if ( !v15 )
      v34 = "authorization_code";
    v35 = StringCchPrintfA(
            (char *)lpOptional,
            v82 - (_QWORD)lpOptional,
            "grant_type=%s&%s=%s&client_id=%s&redirect_uri=%s",
            v34,
            v33,
            v30,
            v31,
            v32);
    v72 = v35;
    if ( v35 < 0 )
    {
      HIWORD(v73) = 396;
      v109 = v35;
      throw (long *)&v109;
    }
    LOWORD(v73) = 396;
    do
      ++v25;
    while ( *((_BYTE *)lpOptional + v25) );
    v78 = v25;
    v36 = WinHttpOpen(L"MS_WorkFoldersClient", 4u, 0, 0, 0);
    std::unique_ptr<void *,WinHttpDeleter>::reset(&hSession, v36);
    if ( !hSession )
    {
      HIWORD(v73) = 409;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v72 = 0;
    LOWORD(v73) = 409;
    v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v158);
    v39 = WinHttpConnect(hSession, v37, v38, 0);
    std::unique_ptr<void *,WinHttpDeleter>::reset(&hConnect, v39);
    if ( !hConnect )
    {
      HIWORD(v73) = 416;
      v98 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v98;
    }
    v72 = 0;
    LOWORD(v73) = 416;
    v40 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130);
    v41 = WinHttpOpenRequest(hConnect, L"POST", v40, 0, 0, 0, 0x800040u);
    std::unique_ptr<void *,WinHttpDeleter>::reset(&hRequest, v41);
    v42 = hRequest;
    if ( !hRequest )
    {
      HIWORD(v73) = 426;
      v97 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v97;
    }
    LOWORD(v73) = 426;
    v72 = 0;
    if ( !WinHttpAddRequestHeaders(hRequest, L"Content-Type: application/x-www-form-urlencoded", 0xFFFFFFFF, 0xA0000000) )
    {
      HIWORD(v73) = 431;
      v110 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v110;
    }
    LOWORD(v73) = 431;
    v72 = 0;
    if ( !WinHttpSendRequest(v42, 0, 0, lpOptional, v25, v25, 0) )
    {
      HIWORD(v73) = 439;
      v112 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v112;
    }
    LOWORD(v73) = 439;
    v72 = 0;
    if ( !WinHttpReceiveResponse(v42, 0) )
    {
      HIWORD(v73) = 441;
      v113 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v113;
    }
    LOWORD(v73) = 441;
    dwBufferLength = 4;
    v72 = 0;
    if ( !WinHttpQueryHeaders(v42, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
    {
      HIWORD(v73) = 450;
      v86 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v86;
    }
    v43 = 0;
    v72 = 0;
    LOWORD(v73) = 450;
    v44 = Buffer;
    if ( Buffer != 200 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, Buffer);
        v43 = v72;
        v44 = Buffer;
      }
      v45 = v44 - 400;
      if ( v45 )
      {
        v46 = v45 - 103;
        if ( v46 )
        {
          v72 = v43;
          if ( v46 != 1 )
          {
            v72 = -2147467259;
            HIWORD(v73) = 498;
            v87 = -2147467259;
            throw (long *)&v87;
          }
          v72 = -2134376375;
          HIWORD(v73) = 493;
          v88 = -2134376375;
          throw (long *)&v88;
        }
        LOWORD(v80) = 0;
        dwBufferLength = 2;
        if ( !WinHttpQueryHeaders(v42, 0x24u, 0, &v80, &dwBufferLength, 0) && GetLastError() == 122 )
        {
          v72 = -2134376375;
          HIWORD(v73) = 483;
          v89 = -2134376375;
          throw (long *)&v89;
        }
        v72 = -2147467259;
        HIWORD(v73) = 486;
        v90 = -2147467259;
        throw (long *)&v90;
      }
    }
    std::vector<char>::resize(&lpOptional);
    v47 = 0;
    v78 = 0;
    v48 = v72;
    while ( 1 )
    {
      dwBufferLength = 0;
      v72 = v48;
      if ( !WinHttpQueryDataAvailable(v42, &dwBufferLength) )
      {
        HIWORD(v73) = 511;
        v91 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v91;
      }
      v72 = 0;
      LOWORD(v73) = 511;
      v49 = dwBufferLength;
      if ( !dwBufferLength )
        break;
      v72 = 0;
      if ( dwBufferLength > 0x100000 || v47 + dwBufferLength > 0x100000 )
      {
        v72 = -2147418113;
        HIWORD(v73) = 520;
        v93 = -2147418113;
        throw (long *)&v93;
      }
      v50 = 0;
      v72 = 0;
      LOWORD(v73) = 520;
      v51 = (char *)lpOptional;
      if ( v47 + dwBufferLength > v82 - (__int64)lpOptional )
      {
        std::vector<char>::resize(&lpOptional);
        v50 = v72;
        v49 = dwBufferLength;
        v51 = (char *)lpOptional;
      }
      v72 = v50;
      if ( !WinHttpReadData(v42, &v51[v47], v49, &dwBufferLength) )
      {
        HIWORD(v73) = 527;
        v92 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v92;
      }
      v48 = 0;
      v72 = 0;
      LOWORD(v73) = 527;
      if ( !dwBufferLength )
        break;
      v47 += dwBufferLength;
      v78 = v47;
    }
    v52 = lpOptional;
    if ( v47 >= v82 - (__int64)lpOptional )
    {
      std::vector<char>::resize(&lpOptional);
      v52 = lpOptional;
    }
    v52[v47] = 0;
    v53 = CEcsStringUtil::Utf8ToUtf16(v129, lpOptional);
    std::wstring::operator=(v134, v53);
    std::wstring::~wstring((__int64)v129);
    if ( Buffer == 200 )
    {
      v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
      if ( (unsigned int)JsonReader::Read(v117, v54, v54 + 2 * v135, &v143, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v55 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
          WPP_SF_dS(*(_QWORD *)(v56 + 56), 16, (unsigned int)WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, v57, v55);
        }
        v72 = -2147418113;
        HIWORD(v73) = 564;
        v94 = -2147418113;
        throw (long *)&v94;
      }
      v58 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
      {
LABEL_93:
        if ( !v145 )
        {
          if ( v58 != &WPP_GLOBAL_Control && (*((_BYTE *)v58 + 68) & 2) != 0 && *((_BYTE *)v58 + 65) >= 2u )
          {
            v59 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
            WPP_SF_S(*(_QWORD *)(v60 + 56), 18, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, v59);
          }
          v72 = -2134376415;
          HIWORD(v73) = 578;
          v95 = -2134376415;
          throw (long *)&v95;
        }
        std::wstring::swap(v80, v144);
        if ( v147 )
          std::wstring::swap(v106, v146);
        if ( !v149 )
          goto LABEL_124;
        std::wstring::swap(v156, v148);
        LODWORD(v80) = v72;
        try
        {
          v106 = v128;
          v61 = std::wstring::wstring((__int64)v128);
          CEcsAdfs::GetTokenBody(v138, v61);
          while ( (v138[16] & 3) != 0 )
          {
            v62 = std::wstring::append(v138, L"=");
            std::wstring::operator=(v138, v62);
          }
          v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v138);
          CEcsEncode::Base64DecodeW(v127, v63);
          CEcsStringUtil::Utf8ToUtf16(v139, v127[0]);
          v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v139);
          if ( (unsigned int)JsonReader::Read(v117, v64, v64 + 2 * v140, &v143, 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
            {
              v65 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v139);
              WPP_SF_dS(
                *(_QWORD *)(v66 + 56),
                19,
                (unsigned int)WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids,
                v67,
                v65);
            }
            v72 = -2147418113;
            HIWORD(v73) = 615;
            v96 = -2147418113;
            throw (long *)&v96;
          }
          if ( v151 )
          {
            v68 = v150;
            v69 = v83;
          }
          else
          {
            v69 = v83;
            if ( !v153 )
              goto LABEL_116;
            v68 = v152;
          }
          v69 = std::wstring::swap(v69, v68);
LABEL_116:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            if ( *(_QWORD *)(v69 + 16) )
              v11 = 1;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, v11);
          }
          std::wstring::~wstring((__int64)v139);
          std::vector<unsigned char>::_Tidy(v127);
          std::wstring::~wstring((__int64)v138);
        }
        catch ( long v116 )
        {
          v72 = v116;
        }
        catch ( std::bad_alloc )
        {
          HIWORD(v73) = 630;
          v72 = -2147024882;
        }
        catch ( std::exception )
        {
          HIWORD(v73) = 630;
          v72 = -2147418113;
        }
        catch ( const ATL::CAtlException *v125 )
        {
          HIWORD(v73) = 630;
          v72 = *(_DWORD *)v125;
        }
        v72 = v80;
LABEL_124:
        std::wstring::~wstring((__int64)v156);
        std::string::~string(v132);
        std::wstring::~wstring((__int64)v159);
        std::string::~string(v157);
        std::wstring::~wstring((__int64)v141);
        std::wstring::~wstring((__int64)v134);
        CEcsAdfs::JsonCallback::~JsonCallback((CEcsAdfs::JsonCallback *)&v143);
        std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hRequest);
        std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hConnect);
        std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hSession);
        std::unique_ptr<char>::~unique_ptr<char>(&v114);
        std::vector<unsigned char>::_Tidy(&lpOptional);
        std::wstring::~wstring((__int64)v130);
        std::wstring::~wstring((__int64)v158);
        std::string::~string(v136);
        goto LABEL_137;
      }
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        17,
        WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids,
        v145 != 0,
        v147 != 0);
    }
    v58 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_93;
  }
  catch ( long v115 )
  {
    v72 = v115;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v73) = 634;
    v72 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v73) = 634;
    v72 = -2147418113;
  }
  catch ( const ATL::CAtlException *v126 )
  {
    HIWORD(v73) = 634;
    v72 = *(_DWORD *)v126;
  }
LABEL_137:
  v70 = v72;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v72);
  return v70;
}

```

## disassembly

```asm
0x1800cb318  push    rbx
0x1800cb31a  push    rdi
0x1800cb31b  push    r12
0x1800cb31d  push    r13
0x1800cb31f  push    r14
0x1800cb321  sub     rsp, 490h
0x1800cb328  mov     rax, cs:__security_cookie
0x1800cb32f  xor     rax, rsp
0x1800cb332  mov     [rsp+4B8h+var_38], rax
0x1800cb33a  mov     [rsp+4B8h+var_440], r9
0x1800cb33f  mov     r14, r8
0x1800cb342  mov     r13, rdx
0x1800cb345  mov     r12, rcx
0x1800cb348  mov     r8, [rsp+4B8h+arg_28]
0x1800cb350  mov     [rsp+4B8h+var_420], r8
0x1800cb358  mov     rbx, [rsp+4B8h+arg_20]
0x1800cb360  mov     [rsp+4B8h+var_3B8], rbx
0x1800cb368  lea     rcx, WPP_GLOBAL_Control
0x1800cb36f  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb376  cmp     rax, rcx
0x1800cb379  jz      short loc_1800CB3B0
0x1800cb37b  test    byte ptr [rax+44h], 2
0x1800cb37f  jz      short loc_1800CB3C2
0x1800cb381  cmp     byte ptr [rax+41h], 6
0x1800cb385  jb      short loc_1800CB3B0
0x1800cb387  mov     edx, 0Dh
0x1800cb38c  lea     r8, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids
0x1800cb393  mov     rcx, [rax+38h]
0x1800cb397  call    WPP_SF_
0x1800cb39c  mov     rax, cs:WPP_GLOBAL_Control
0x1800cb3a3  mov     r8, [rsp+4B8h+var_420]
0x1800cb3ab  mov     r9, [rsp+4B8h+var_440]
0x1800cb3b0  test    byte ptr [rax+44h], 2
0x1800cb3b4  jz      short loc_1800CB3C2
0x1800cb3b6  cmp     byte ptr [rax+41h], 6
0x1800cb3ba  jb      short loc_1800CB3C2
0x1800cb3bc  mov     al, 1
0x1800cb3be  xor     edi, edi
0x1800cb3c0  jmp     short loc_1800CB3C7
0x1800cb3c2  xor     edi, edi
0x1800cb3c4  mov     al, dil
0x1800cb3c7  mov     [rsp+4B8h+var_478], edi
0x1800cb3cb  mov     [rsp+4B8h+var_474], 11Ch
0x1800cb3d3  mov     [rsp+4B8h+var_470], al
0x1800cb3d7  lea     rax, aCecsadfsGettok; "CEcsAdfs::GetTokens"
0x1800cb3de  mov     [rsp+4B8h+var_468], rax
0x1800cb3e3  mov     [rsp+4B8h+var_460], rdi
0x1800cb3e8  xor     edx, edx
0x1800cb3ea  mov     rcx, r9
0x1800cb3ed  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800cb3f2  mov     rcx, r8
0x1800cb3f5  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800cb3fa  nop
0x1800cb3fb  lea     r8d, [rdx+68h]; Size
0x1800cb3ff  lea     rcx, [rsp+4B8h+UrlComponents]; void *
0x1800cb407  call    memset_0
0x1800cb40c  mov     [rsp+4B8h+var_450], rdi
0x1800cb411  mov     [rsp+4B8h+dwBufferLength], edi
0x1800cb415  mov     rbx, [rbx+10h]
0x1800cb419  mov     [rsp+4B8h+Buffer], edi
0x1800cb41d  lea     rcx, [rsp+4B8h+var_1F0]
0x1800cb425  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800cb42a  nop
0x1800cb42b  lea     rcx, [rsp+4B8h+var_78]
0x1800cb433  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb438  nop
0x1800cb439  lea     rcx, [rsp+4B8h+var_250]
0x1800cb441  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb446  nop
0x1800cb447  lea     rcx, [rsp+4B8h+lpOptional]
0x1800cb44f  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x1800cb454  nop
0x1800cb455  lea     rcx, [rsp+4B8h+var_390]
0x1800cb45d  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800cb462  nop
0x1800cb463  lea     rcx, [rsp+4B8h+hSession]
0x1800cb46b  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800cb470  nop
0x1800cb471  lea     rcx, [rsp+4B8h+hConnect]
0x1800cb479  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800cb47e  nop
0x1800cb47f  lea     rcx, [rsp+4B8h+hRequest]
0x1800cb487  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800cb48c  nop
0x1800cb48d  lea     rax, ??_7IJsonReader@@6B@; const IJsonReader::`vftable'
0x1800cb494  mov     [rsp+4B8h+var_378], rax
0x1800cb49c  lea     rax, ??_7JsonReader@@6B@; const JsonReader::`vftable'
0x1800cb4a3  mov     [rsp+4B8h+var_378], rax
0x1800cb4ab  mov     [rsp+4B8h+var_370], rdi
0x1800cb4b3  mov     [rsp+4B8h+var_368], rdi
0x1800cb4bb  mov     [rsp+4B8h+var_360], 1
0x1800cb4c6  mov     [rsp+4B8h+var_35C], 1
0x1800cb4d1  xorps   xmm0, xmm0
0x1800cb4d4  movdqa  [rsp+4B8h+var_358], xmm0
0x1800cb4dd  mov     [rsp+4B8h+var_348], 0FFh
0x1800cb4e9  mov     [rsp+4B8h+var_340], 80000h
0x1800cb4f5  mov     [rsp+4B8h+var_338], 8
0x1800cb501  lea     rax, ??_7IJsonReaderCallback@@6B@; const IJsonReaderCallback::`vftable'
0x1800cb508  mov     [rsp+4B8h+var_168], rax
0x1800cb510  lea     rax, ??_7JsonCallback@CEcsAdfs@@6B@; const CEcsAdfs::JsonCallback::`vftable'
0x1800cb517  mov     [rsp+4B8h+var_168], rax
0x1800cb51f  lea     rcx, [rsp+4B8h+var_160]
0x1800cb527  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb52c  nop
0x1800cb52d  lea     rcx, [rsp+4B8h+var_140]
0x1800cb535  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb53a  nop
0x1800cb53b  lea     rcx, [rsp+4B8h+var_120]
0x1800cb543  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb548  nop
0x1800cb549  lea     rcx, [rsp+4B8h+var_100]
0x1800cb551  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb556  nop
0x1800cb557  lea     rcx, [rsp+4B8h+var_E0]
0x1800cb55f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb564  nop
0x1800cb565  mov     [rsp+4B8h+var_C0], edi
0x1800cb56c  mov     [rsp+4B8h+var_BC], edi
0x1800cb573  lea     rcx, [rsp+4B8h+var_210]
0x1800cb57b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb580  nop
0x1800cb581  lea     rcx, [rsp+4B8h+var_190]
0x1800cb589  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb58e  nop
0x1800cb58f  lea     rcx, [rsp+4B8h+var_98]
0x1800cb597  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800cb59c  nop
0x1800cb59d  lea     rcx, [rsp+4B8h+var_58]
0x1800cb5a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb5aa  nop
0x1800cb5ab  lea     rcx, [rsp+4B8h+var_230]
0x1800cb5b3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800cb5b8  nop
0x1800cb5b9  lea     rcx, [rsp+4B8h+var_B8]
0x1800cb5c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cb5c6  nop
0x1800cb5c7  lea     r8, [rsp+4B8h+var_58]
0x1800cb5cf  lea     rdx, [rsp+4B8h+var_190]
0x1800cb5d7  mov     rcx, r13
0x1800cb5da  call    ?ResolveAuthRequestParameters@CEcsAdfs@@CAXPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; CEcsAdfs::ResolveAuthRequestParameters(ushort const *,std::wstring *,std::wstring *,std::wstring *)
0x1800cb5df  lea     rcx, [rsp+4B8h+var_190]
0x1800cb5e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb5ec  mov     rdx, rax
0x1800cb5ef  lea     rcx, [rsp+4B8h+var_270]
0x1800cb5f7  call    ?Utf16ToUtf8@CEcsStringUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; CEcsStringUtil::Utf16ToUtf8(ushort const *)
0x1800cb5fc  nop
0x1800cb5fd  mov     rdx, rax
0x1800cb600  lea     rcx, [rsp+4B8h+var_98]
0x1800cb608  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cb60d  nop
0x1800cb60e  lea     rcx, [rsp+4B8h+var_270]
0x1800cb616  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cb61b  lea     rcx, [rsp+4B8h+var_58]
0x1800cb623  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb628  mov     rdx, rax
0x1800cb62b  lea     rcx, [rsp+4B8h+var_270]
0x1800cb633  call    ?Utf16ToUtf8@CEcsStringUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; CEcsStringUtil::Utf16ToUtf8(ushort const *)
0x1800cb638  nop
0x1800cb639  mov     rdx, rax
0x1800cb63c  lea     rcx, [rsp+4B8h+var_230]
0x1800cb644  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cb649  nop
0x1800cb64a  lea     rcx, [rsp+4B8h+var_270]
0x1800cb652  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cb657  lea     rdx, [rsp+4B8h+var_230]
0x1800cb65f  lea     rcx, [rsp+4B8h+var_270]
0x1800cb667  call    ?UrlEncode@CEcsUri@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@@Z; CEcsUri::UrlEncode(std::string const &)
0x1800cb66c  nop
0x1800cb66d  mov     rdx, rax
0x1800cb670  lea     rcx, [rsp+4B8h+var_230]
0x1800cb678  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cb67d  nop
0x1800cb67e  lea     rcx, [rsp+4B8h+var_270]
0x1800cb686  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cb68b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb692  lea     r13, WPP_GLOBAL_Control
0x1800cb699  cmp     rcx, r13
0x1800cb69c  jz      short loc_1800CB6C9
0x1800cb69e  test    byte ptr [rcx+44h], 2
0x1800cb6a2  jz      short loc_1800CB6C9
0x1800cb6a4  cmp     byte ptr [rcx+41h], 4
0x1800cb6a8  jb      short loc_1800CB6C9
0x1800cb6aa  mov     r9d, edi
0x1800cb6ad  test    rbx, rbx
0x1800cb6b0  setnz   r9b
0x1800cb6b4  mov     edx, 0Eh
0x1800cb6b9  lea     r8, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids
0x1800cb6c0  mov     rcx, [rcx+38h]
0x1800cb6c4  call    WPP_SF_d
0x1800cb6c9  test    rbx, rbx
0x1800cb6cc  jz      short loc_1800CB6FF
0x1800cb6ce  mov     rcx, [rsp+4B8h+var_3B8]
0x1800cb6d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb6db  mov     rdx, rax
0x1800cb6de  lea     rcx, [rsp+4B8h+var_270]
0x1800cb6e6  call    ?Utf16ToUtf8@CEcsStringUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; CEcsStringUtil::Utf16ToUtf8(ushort const *)
0x1800cb6eb  nop
0x1800cb6ec  mov     rdx, rax
0x1800cb6ef  lea     rcx, [rsp+4B8h+var_1F0]
0x1800cb6f7  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cb6fc  nop
0x1800cb6fd  jmp     short loc_1800CB721
0x1800cb6ff  mov     rdx, r14
0x1800cb702  lea     rcx, [rsp+4B8h+var_270]
0x1800cb70a  call    ?Utf16ToUtf8@CEcsStringUtil@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBG@Z; CEcsStringUtil::Utf16ToUtf8(ushort const *)
0x1800cb70f  nop
0x1800cb710  mov     rdx, rax
0x1800cb713  lea     rcx, [rsp+4B8h+var_1F0]
0x1800cb71b  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800cb720  nop
0x1800cb721  lea     rcx, [rsp+4B8h+var_270]
0x1800cb729  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800cb72e  mov     eax, [rsp+4B8h+var_478]
0x1800cb732  mov     [rsp+4B8h+var_478], eax
0x1800cb736  mov     edx, 155h
0x1800cb73b  cmp     [rsp+4B8h+var_1E0], 80000h
0x1800cb747  ja      loc_1800CC711
0x1800cb74d  mov     [rsp+4B8h+var_478], edi
0x1800cb751  mov     word ptr [rsp+4B8h+var_474], dx
0x1800cb756  mov     [rsp+4B8h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800cb761  mov     [rsp+4B8h+UrlComponents.dwHostNameLength], 1
0x1800cb76c  mov     [rsp+4B8h+UrlComponents.dwUrlPathLength], 1
0x1800cb777  mov     [rsp+4B8h+UrlComponents.dwExtraInfoLength], 1
0x1800cb782  mov     [rsp+4B8h+var_478], edi
0x1800cb786  lea     r9, [rsp+4B8h+UrlComponents]; lpUrlComponents
0x1800cb78e  xor     edx, edx; dwUrlLength
0x1800cb790  mov     r8d, 4000h; dwFlags
0x1800cb796  mov     rcx, r12; pwszUrl
0x1800cb799  call    cs:__imp_WinHttpCrackUrl
0x1800cb79f  test    eax, eax
0x1800cb7a1  jnz     short loc_1800CB7D1
0x1800cb7a3  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800cb7a8  mov     [rsp+4B8h+var_478], eax
0x1800cb7ac  mov     ecx, 163h
0x1800cb7b1  mov     word ptr [rsp+4B8h+var_474+2], cx
0x1800cb7b6  mov     [rsp+4B8h+pExceptionObject], eax
0x1800cb7bd  lea     rdx, _TI1J; pThrowInfo
0x1800cb7c4  lea     rcx, [rsp+4B8h+pExceptionObject]; pExceptionObject
0x1800cb7cc  call    _CxxThrowException_0
0x1800cb7d1  mov     [rsp+4B8h+var_478], edi
0x1800cb7d5  mov     ecx, 163h
0x1800cb7da  mov     word ptr [rsp+4B8h+var_474], cx
0x1800cb7df  mov     [rsp+4B8h+var_478], edi
0x1800cb7e3  cmp     [rsp+4B8h+UrlComponents.nScheme], 2
0x1800cb7eb  jnz     loc_1800CC6E3
0x1800cb7f1  mov     rdx, [rsp+4B8h+UrlComponents.lpszHostName]
0x1800cb7f9  test    rdx, rdx
0x1800cb7fc  jz      loc_1800CC6E3
0x1800cb802  cmp     [rsp+4B8h+UrlComponents.dwHostNameLength], edi
0x1800cb809  jz      loc_1800CC6E3
0x1800cb80f  cmp     [rsp+4B8h+UrlComponents.lpszUrlPath], rdi
0x1800cb817  jz      loc_1800CC6E3
0x1800cb81d  cmp     [rsp+4B8h+UrlComponents.dwUrlPathLength], edi
0x1800cb824  jz      loc_1800CC6E3
0x1800cb82a  mov     [rsp+4B8h+var_478], edi
0x1800cb82e  mov     ecx, 168h
0x1800cb833  mov     word ptr [rsp+4B8h+var_474], cx
0x1800cb838  mov     r8d, [rsp+4B8h+UrlComponents.dwHostNameLength]
0x1800cb840  lea     rcx, [rsp+4B8h+var_78]
0x1800cb848  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800cb84d  mov     r8d, [rsp+4B8h+UrlComponents.dwUrlPathLength]
0x1800cb855  mov     rdx, [rsp+4B8h+UrlComponents.lpszUrlPath]
0x1800cb85d  lea     rcx, [rsp+4B8h+var_250]
0x1800cb865  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800cb86a  xor     r8d, r8d
0x1800cb86d  lea     rdx, ?s_wszAuthorizationSuffix@CEcsAdfs@@0QBGB; "/authorize"
0x1800cb874  lea     rcx, [rsp+4B8h+var_250]
0x1800cb87c  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800cb881  mov     r10, rax
0x1800cb884  mov     ecx, [rsp+4B8h+var_478]
0x1800cb888  mov     [rsp+4B8h+var_478], ecx
0x1800cb88c  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800cb890  mov     ecx, 170h
0x1800cb895  cmp     rax, r14
0x1800cb898  jz      loc_1800CC6BA
0x1800cb89e  mov     [rsp+4B8h+var_478], edi
0x1800cb8a2  mov     word ptr [rsp+4B8h+var_474], cx
0x1800cb8a7  lea     rdx, [rax+0Ah]
0x1800cb8ab  mov     [rsp+4B8h+var_478], edi
0x1800cb8af  mov     rax, [rsp+4B8h+var_240]
0x1800cb8b7  cmp     rdx, rax
0x1800cb8ba  jz      short loc_1800CB909
0x1800cb8bc  dec     rax
0x1800cb8bf  cmp     rdx, rax
0x1800cb8c2  jnz     short loc_1800CB8DB
0x1800cb8c4  lea     rcx, [rsp+4B8h+var_250]
0x1800cb8cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb8d1  lea     ecx, [r14+30h]
0x1800cb8d5  cmp     cx, [rax+rdx*2]
0x1800cb8d9  jz      short loc_1800CB909
0x1800cb8db  mov     eax, 8000FFFFh
0x1800cb8e0  mov     [rsp+4B8h+var_478], eax
0x1800cb8e4  mov     ecx, 176h
0x1800cb8e9  mov     word ptr [rsp+4B8h+var_474+2], cx
0x1800cb8ee  mov     [rsp+4B8h+var_3AC], eax
0x1800cb8f5  lea     rdx, _TI1J; pThrowInfo
0x1800cb8fc  lea     rcx, [rsp+4B8h+var_3AC]; pExceptionObject
0x1800cb904  call    _CxxThrowException_0
0x1800cb909  mov     [rsp+4B8h+var_478], edi
0x1800cb90d  mov     ecx, 176h
  ... truncated ...
```
