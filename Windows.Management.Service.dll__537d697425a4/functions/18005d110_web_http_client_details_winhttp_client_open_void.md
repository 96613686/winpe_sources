# web::http::client::details::winhttp_client::open(void)

- ea: `0x18005d110`
- end: `0x18005db17`
- name: `?open@winhttp_client@details@client@http@web@@IEAAKXZ`
- size: `2567`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005e9c0`

## callees

- `0x18000b8f0`
- `0x18000bd9c`
- `0x18001b6b0`
- `0x18001b780`
- `0x18003dff0`
- `0x18004d3a0`
- `0x180056cb0`
- `0x18005d110`
- `0x180063865`
- `0x180063f73`
- `0x180063f8b`
- `0x18006e430`
- `0x1800816d4`
- `0x1800826c0`
- `0x1800826e0`
- `0x180082850`
- `0x180083544`
- `0x180084574`
- `0x180178ed8`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d7fe`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d351`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d367`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dab4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dac4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dad4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d351`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d367`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dab4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dac4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005dad4`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18005d79c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18005d79c`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18005d2c7`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18005d2c7`
- `WINHTTP!WinHttpSetTimeouts` at `0x18005d6df`
- `WINHTTP!WinHttpSetTimeouts` at `0x18005d6df`
- `WINHTTP!WinHttpConnect` at `0x18005d7ec`
- `WINHTTP!WinHttpConnect` at `0x18005d7ec`
- `WINHTTP!WinHttpOpen` at `0x18005d696`
- `WINHTTP!WinHttpOpen` at `0x18005d696`
- `WINHTTP!WinHttpSetOption` at `0x18005d713`
- `WINHTTP!WinHttpSetOption` at `0x18005d740`
- `WINHTTP!WinHttpSetOption` at `0x18005d713`
- `WINHTTP!WinHttpSetOption` at `0x18005d740`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18005d2df`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18005d2df`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall web::http::client::details::winhttp_client::open(web::http::client::details::winhttp_client *this)
{
  DWORD LastError; // ebx
  const WCHAR *lpszProxy; // rdi
  const WCHAR *lpszProxyBypass; // r14
  const struct web::http::client::http_client_config *v6; // r13
  wchar_t **v7; // rsi
  int v8; // eax
  DWORD v9; // r12d
  const wchar_t *lpszAutoConfigUrl; // rsi
  size_t v11; // rax
  wchar_t *v12; // rdx
  char *v13; // rdx
  char *v14; // rdx
  char *v15; // rdx
  char *v16; // rdx
  char *v17; // rdx
  char *v18; // rdx
  int v19; // eax
  const wchar_t *v20; // rcx
  void **v21; // rdx
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rsi
  void **v24; // rax
  __int64 v25; // rdi
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  char *v28; // r15
  size_t v29; // r14
  void *v30; // rdi
  const struct std::nothrow_t *v31; // rdx
  _BYTE *v32; // rcx
  WINHTTP_PROXY_INFO *p_pProxyInfo; // rdx
  void *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // r8d
  const WCHAR *v38; // rdx
  HINTERNET v39; // rax
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  const struct std::nothrow_t *v46; // rdx
  void *v47; // rcx
  const struct std::nothrow_t *v48; // rdx
  void *v49; // rcx
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  const struct std::nothrow_t *v52; // rdx
  wchar_t *v53; // rcx
  const struct std::nothrow_t *v54; // rdx
  void *v55; // rcx
  const struct web::http::client::http_client_config *Buffer; // [rsp+30h] [rbp-D0h] BYREF
  const WCHAR *v57; // [rsp+38h] [rbp-C8h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  void *Src[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v61; // [rsp+78h] [rbp-88h]
  unsigned __int64 v62; // [rsp+80h] [rbp-80h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-70h] BYREF
  size_t N; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v65; // [rsp+A8h] [rbp-58h]
  void *v66[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-38h]
  void *v69[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v70; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v71; // [rsp+E8h] [rbp-18h]
  void *v72[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v73; // [rsp+100h] [rbp+0h]
  unsigned __int64 v74; // [rsp+108h] [rbp+8h]
  void *v75[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v76; // [rsp+128h] [rbp+28h]
  void *v77[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v78; // [rsp+140h] [rbp+40h]
  unsigned __int64 v79; // [rsp+148h] [rbp+48h]
  void *v80[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v81; // [rsp+160h] [rbp+60h]
  unsigned __int64 v82; // [rsp+168h] [rbp+68h]
  int v83; // [rsp+170h] [rbp+70h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v85; // [rsp+198h] [rbp+98h]

  if ( *((_BYTE *)this + 968) )
    return 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 272);
  pplx::details::critical_section_impl::lock((LPCRITICAL_SECTION)((char *)this + 272));
  if ( !*((_BYTE *)this + 968) )
  {
    memset(&pProxyConfig, 0, sizeof(pProxyConfig));
    lpszProxy = 0;
    lpszProxyBypass = 0;
    v57 = 0;
    *((_BYTE *)this + 993) = 0;
    *(_OWORD *)Src = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(Src[0]) = 0;
    std::wstring::wstring(S1, L"/");
    *(_OWORD *)v66 = 0;
    v67 = 0;
    v68 = 7;
    LOWORD(v66[0]) = 0;
    *(_OWORD *)v69 = 0;
    v70 = 0;
    v71 = 7;
    LOWORD(v69[0]) = 0;
    *(_OWORD *)v72 = 0;
    v73 = 0;
    v74 = 7;
    LOWORD(v72[0]) = 0;
    std::wstring::wstring(v75, L"/");
    *(_OWORD *)v77 = 0;
    v78 = 0;
    v79 = 7;
    LOWORD(v77[0]) = 0;
    *(_OWORD *)v80 = 0;
    v81 = 0;
    v82 = 7;
    LOWORD(v80[0]) = 0;
    v83 = -1;
    v6 = web::http::client::details::_http_client_communicator::client_config(this);
    Buffer = v6;
    v7 = (wchar_t **)((char *)v6 + 32);
    v8 = *((_DWORD *)v6 + 66);
    switch ( v8 )
    {
      case 0:
        v9 = web::http::client::details::WinHttpDefaultProxyConstant();
        goto LABEL_95;
      case 2:
        v9 = 1;
        goto LABEL_95;
      case 1:
        v9 = web::http::client::details::WinHttpDefaultProxyConstant();
        if ( v9 != 4 )
        {
          *((_BYTE *)this + 993) = 1;
          memset(&pProxyInfo, 0, sizeof(pProxyInfo));
          if ( (!WinHttpGetDefaultProxyConfiguration(&pProxyInfo) || pProxyInfo.dwAccessType == 1)
            && WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
          {
            if ( pProxyConfig.fAutoDetect )
            {
              *((_BYTE *)this + 993) = 1;
            }
            else
            {
              lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
              if ( pProxyConfig.lpszAutoConfigUrl )
              {
                *((_BYTE *)this + 993) = 1;
                v11 = wcslen_0(lpszAutoConfigUrl);
                std::wstring::_Assign<unsigned short>((char *)this + 1000, lpszAutoConfigUrl, v11);
              }
              else if ( pProxyConfig.lpszProxy )
              {
                v9 = 3;
                lpszProxy = pProxyConfig.lpszProxy;
                if ( pProxyConfig.lpszProxyBypass )
                  lpszProxyBypass = pProxyConfig.lpszProxyBypass;
              }
            }
          }
          if ( pProxyInfo.lpszProxy )
            GlobalFree(pProxyInfo.lpszProxy);
          if ( pProxyInfo.lpszProxyBypass )
            GlobalFree(pProxyInfo.lpszProxyBypass);
        }
        goto LABEL_95;
    }
    v9 = 3;
    if ( S1 != v7 )
    {
      if ( *((_QWORD *)v6 + 7) <= 7u )
        v12 = (wchar_t *)((char *)v6 + 32);
      else
        v12 = *v7;
      std::wstring::_Assign<unsigned short>(S1, v12, *((_QWORD *)v6 + 6));
    }
    if ( v66 != (void **)((char *)v6 + 64) )
    {
      if ( *((_QWORD *)v6 + 11) <= 7u )
        v13 = (char *)v6 + 64;
      else
        v13 = (char *)*((_QWORD *)v6 + 8);
      std::wstring::_Assign<unsigned short>(v66, v13, *((_QWORD *)v6 + 10));
    }
    if ( v69 != (void **)((char *)v6 + 96) )
    {
      if ( *((_QWORD *)v6 + 15) <= 7u )
        v14 = (char *)v6 + 96;
      else
        v14 = (char *)*((_QWORD *)v6 + 12);
      std::wstring::_Assign<unsigned short>(v69, v14, *((_QWORD *)v6 + 14));
    }
    if ( v72 != (void **)((char *)v6 + 128) )
    {
      if ( *((_QWORD *)v6 + 19) <= 7u )
        v15 = (char *)v6 + 128;
      else
        v15 = (char *)*((_QWORD *)v6 + 16);
      std::wstring::_Assign<unsigned short>(v72, v15, *((_QWORD *)v6 + 18));
    }
    if ( v75 != (void **)((char *)v6 + 160) )
    {
      if ( *((_QWORD *)v6 + 23) <= 7u )
        v16 = (char *)v6 + 160;
      else
        v16 = (char *)*((_QWORD *)v6 + 20);
      std::wstring::_Assign<unsigned short>(v75, v16, *((_QWORD *)v6 + 22));
    }
    if ( v77 != (void **)((char *)v6 + 192) )
    {
      if ( *((_QWORD *)v6 + 27) <= 7u )
        v17 = (char *)v6 + 192;
      else
        v17 = (char *)*((_QWORD *)v6 + 24);
      std::wstring::_Assign<unsigned short>(v77, v17, *((_QWORD *)v6 + 26));
    }
    if ( v80 != (void **)((char *)v6 + 224) )
    {
      if ( *((_QWORD *)v6 + 31) <= 7u )
        v18 = (char *)v6 + 224;
      else
        v18 = (char *)*((_QWORD *)v6 + 28);
      std::wstring::_Assign<unsigned short>(v80, v18, *((_QWORD *)v6 + 30));
    }
    v19 = *((_DWORD *)v6 + 64);
    v83 = v19;
    if ( N )
    {
      v20 = (const wchar_t *)S1;
      if ( v65 > 7 )
        v20 = S1[0];
      if ( N != 1 )
      {
LABEL_66:
        if ( !v19 )
        {
          lpszProxy = (const WCHAR *)v69;
          if ( v71 > 7 )
            lpszProxy = (const WCHAR *)v69[0];
          goto LABEL_95;
        }
        goto LABEL_70;
      }
      if ( wmemcmp(v20, L"/", 1u) )
      {
        v19 = v83;
        goto LABEL_66;
      }
    }
LABEL_70:
    v21 = v69;
    if ( v71 > 7 )
      v21 = (void **)v69[0];
    std::wstring::_Assign<unsigned short>(Src, v21, v70);
    if ( v83 > 0 )
    {
      v22 = v61;
      v23 = v62;
      if ( v61 >= v62 )
      {
        v25 = 0x7FFFFFFFFFFFFFFELL;
        if ( 0x7FFFFFFFFFFFFFFELL == v61 )
          goto LABEL_174;
        v26 = (v61 + 1) | 7;
        if ( v26 <= 0x7FFFFFFFFFFFFFFELL )
        {
          v27 = v62 >> 1;
          if ( v62 <= 0x7FFFFFFFFFFFFFFELL - (v62 >> 1) )
          {
            v25 = (v61 + 1) | 7;
            if ( v26 < v62 + v27 )
              v25 = v62 + v27;
          }
        }
        v28 = (char *)std::allocator<unsigned short>::allocate(Src, v25 + 1);
        v61 = v22 + 1;
        v62 = v25;
        v29 = 2 * v22;
        if ( v23 <= 7 )
        {
          memcpy_0(v28, Src, v29);
          *(_DWORD *)&v28[v29] = 58;
        }
        else
        {
          v30 = Src[0];
          memcpy_0(v28, Src[0], v29);
          *(_DWORD *)&v28[v29] = 58;
          v31 = (const struct std::nothrow_t *)(2 * v23 + 2);
          if ( (unsigned __int64)v31 < 0x1000 )
          {
            operator delete(v30, v31);
          }
          else
          {
            v32 = (_BYTE *)*((_QWORD *)v30 - 1);
            if ( (unsigned __int64)((_BYTE *)v30 - v32 - 8) > 0x1F )
              __fastfail(5u);
            operator delete(v32, (const struct std::nothrow_t *)(2 * v23 + 41));
          }
        }
        Src[0] = v28;
        v6 = Buffer;
      }
      else
      {
        ++v61;
        v24 = Src;
        if ( v62 > 7 )
          v24 = (void **)Src[0];
        *(_DWORD *)((char *)v24 + 2 * v22) = 58;
      }
      std::_Integral_to_string<unsigned short,int>(&pProxyInfo, (unsigned int)v83);
      p_pProxyInfo = &pProxyInfo;
      if ( v85 > 7 )
        p_pProxyInfo = *(WINHTTP_PROXY_INFO **)&pProxyInfo.dwAccessType;
      std::wstring::_Append<unsigned short>(Src, p_pProxyInfo, pProxyInfo.lpszProxyBypass);
      Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<std::wstring,enum Microsoft::Windows::Autopilot::Diagnostics::JsonOutputBuilder::ApiScenario>::GenericMapping::~GenericMapping(&pProxyInfo);
      lpszProxyBypass = v57;
    }
    lpszProxy = (const WCHAR *)Src;
    if ( v62 > 7 )
      lpszProxy = (const WCHAR *)Src[0];
LABEL_95:
    v34 = WinHttpOpen(0, v9, lpszProxy, lpszProxyBypass, 0x10000000u);
    *((_QWORD *)this + 122) = v34;
    if ( !v34 )
      goto LABEL_114;
    v35 = *((_QWORD *)v6 + 51) / 1000LL;
    if ( (int)v35 < 1 )
      LODWORD(v35) = 1;
    if ( !WinHttpSetTimeouts(v34, v35, v35, v35, v35) )
      goto LABEL_114;
    if ( *((_BYTE *)v6 + 400) )
    {
      LODWORD(Buffer) = 1;
      if ( !WinHttpSetOption(*((HINTERNET *)this + 122), 0x49u, &Buffer, 4u) )
        goto LABEL_114;
    }
    LODWORD(Buffer) = 2720;
    if ( !WinHttpSetOption(*((HINTERNET *)this + 122), 0x54u, &Buffer, 4u) )
      goto LABEL_114;
    if ( !*((_QWORD *)v6 + 69) )
    {
LABEL_105:
      if ( WinHttpSetStatusCallback(
             *((HINTERNET *)this + 122),
             web::http::client::details::winhttp_client::completion_callback,
             0x97F4C30u,
             0) != (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        if ( web::uri::is_port_default((web::http::client::details::winhttp_client *)((char *)this + 40)) )
        {
          LOWORD(v37) = 80;
          if ( *((_BYTE *)this + 992) )
            LOWORD(v37) = 443;
        }
        else
        {
          v37 = *((_DWORD *)this + 66);
        }
        v38 = (const WCHAR *)((char *)this + 104);
        if ( *((_QWORD *)this + 16) > 7u )
          v38 = *(const WCHAR **)v38;
        v39 = WinHttpConnect(*((HINTERNET *)this + 122), v38, v37, 0);
        *((_QWORD *)this + 123) = v39;
        if ( v39 )
        {
          *((_BYTE *)this + 968) = 1;
          LastError = 0;
LABEL_116:
          if ( v82 > 7 )
          {
            v40 = (const struct std::nothrow_t *)(2 * v82 + 2);
            if ( (unsigned __int64)v40 < 0x1000 )
            {
              v41 = v80[0];
            }
            else
            {
              v41 = (void *)*((_QWORD *)v80[0] - 1);
              if ( (unsigned __int64)((char *)v80[0] - (char *)v41 - 8) > 0x1F )
                goto LABEL_156;
              v40 = (const struct std::nothrow_t *)(2 * v82 + 41);
            }
            operator delete(v41, v40);
          }
          v81 = 0;
          v82 = 7;
          LOWORD(v80[0]) = 0;
          if ( v79 > 7 )
          {
            v42 = (const struct std::nothrow_t *)(2 * v79 + 2);
            if ( (unsigned __int64)v42 < 0x1000 )
            {
              v43 = v77[0];
            }
            else
            {
              v43 = (void *)*((_QWORD *)v77[0] - 1);
              if ( (unsigned __int64)((char *)v77[0] - (char *)v43 - 8) > 0x1F )
                goto LABEL_156;
              v42 = (const struct std::nothrow_t *)(2 * v79 + 41);
            }
            operator delete(v43, v42);
          }
          v78 = 0;
          v79 = 7;
          LOWORD(v77[0]) = 0;
          if ( v76 > 7 )
          {
            v44 = (const struct std::nothrow_t *)(2 * v76 + 2);
            if ( (unsigned __int64)v44 < 0x1000 )
            {
              v45 = v75[0];
            }
            else
            {
              v45 = (void *)*((_QWORD *)v75[0] - 1);
              if ( (unsigned __int64)((char *)v75[0] - (char *)v45 - 8) > 0x1F )
                goto LABEL_156;
              v44 = (const struct std::nothrow_t *)(2 * v76 + 41);
            }
            operator delete(v45, v44);
          }
          v75[2] = 0;
          v76 = 7;
          LOWORD(v75[0]) = 0;
          if ( v74 > 7 )
          {
            v46 = (const struct std::nothrow_t *)(2 * v74 + 2);
            if ( (unsigned __int64)v46 < 0x1000 )
            {
              v47 = v72[0];
            }
            else
            {
              v47 = (void *)*((_QWORD *)v72[0] - 1);
              if ( (unsigned __int64)((char *)v72[0] - (char *)v47 - 8) > 0x1F )
                goto LABEL_156;
              v46 = (const struct std::nothrow_t *)(2 * v74 + 41);
            }
            operator delete(v47, v46);
          }
          v73 = 0;
          v74 = 7;
          LOWORD(v72[0]) = 0;
          if ( v71 > 7 )
          {
            v48 = (const struct std::nothrow_t *)(2 * v71 + 2);
            if ( (unsigned __int64)v48 < 0x1000 )
            {
              v49 = v69[0];
            }
            else
            {
              v49 = (void *)*((_QWORD *)v69[0] - 1);
              if ( (unsigned __int64)((char *)v69[0] - (char *)v49 - 8) > 0x1F )
                goto LABEL_156;
              v48 = (const struct std::nothrow_t *)(2 * v71 + 41);
            }
            operator delete(v49, v48);
          }
          v70 = 0;
          v71 = 7;
          LOWORD(v69[0]) = 0;
          if ( v68 > 7 )
          {
            v50 = (const struct std::nothrow_t *)(2 * v68 + 2);
            if ( (unsigned __int64)v50 < 0x1000 )
            {
              v51 = v66[0];
            }
            else
            {
              v51 = (void *)*((_QWORD *)v66[0] - 1);
              if ( (unsigned __int64)((char *)v66[0] - (char *)v51 - 8) > 0x1F )
                goto LABEL_156;
              v50 = (const struct std::nothrow_t *)(2 * v68 + 41);
            }
            operator delete(v51, v50);
          }
          v67 = 0;
          v68 = 7;
          LOWORD(v66[0]) = 0;
          if ( v65 <= 7 )
          {
LABEL_159:
            N = 0;
            v65 = 7;
            LOWORD(S1[0]) = 0;
            if ( v62 > 7 )
            {
              v54 = (const struct std::nothrow_t *)(2 * v62 + 2);
              if ( (unsigned __int64)v54 < 0x1000 )
              {
                v55 = Src[0];
              }
              else
              {
                v55 = (void *)*((_QWORD *)Src[0] - 1);
                if ( (unsigned __int64)((char *)Src[0] - (char *)v55 - 8) > 0x1F )
                  __fastfail(5u);
                v54 = (const struct std::nothrow_t *)(2 * v62 + 41);
              }
              operator delete(v55, v54);
            }
            v61 = 0;
            v62 = 7;
            LOWORD(Src[0]) = 0;
            if ( pProxyConfig.lpszAutoConfigUrl )
              GlobalFree(pProxyConfig.lpszAutoConfigUrl);
            if ( pProxyConfig.lpszProxy )
              GlobalFree(pProxyConfig.lpszProxy);
            if ( pProxyConfig.lpszProxyBypass )
              GlobalFree(pProxyConfig.lpszProxyBypass);
            goto LABEL_172;
          }
          v52 = (const struct std::nothrow_t *)(2 * v65 + 2);
          if ( (unsigned __int64)v52 < 0x1000 )
          {
            v53 = S1[0];
            goto LABEL_158;
          }
          v53 = (wchar_t *)*((_QWORD *)S1[0] - 1);
          if ( (unsigned __int64)((char *)S1[0] - (char *)v53 - 8) <= 0x1F )
          {
            v52 = (const struct std::nothrow_t *)(2 * v65 + 41);
LABEL_158:
            operator delete(v53, v52);
            goto LABEL_159;
          }
LABEL_156:
          __fastfail(5u);
        }
      }
LABEL_114:
      LastError = GetLastError();
      goto LABEL_116;
    }
    v57 = (const WCHAR *)*((_QWORD *)this + 122);
    v36 = *((_QWORD *)v6 + 69);
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v36 + 16LL))(v36, &v57);
      goto LABEL_105;
    }
    std::_Xbad_function_call();
LABEL_174:
    std::_Xlen_string();
  }
  LastError = 0;
LABEL_172:
  pplx::details::critical_section_impl::unlock(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x18005d110  push    rbp
0x18005d112  push    rbx
0x18005d113  push    rsi
0x18005d114  push    rdi
0x18005d115  push    r12
0x18005d117  push    r13
0x18005d119  push    r14
0x18005d11b  push    r15
0x18005d11d  lea     rbp, [rsp-0B8h]
0x18005d125  sub     rsp, 1B8h
0x18005d12c  mov     rax, cs:__security_cookie
0x18005d133  xor     rax, rsp
0x18005d136  mov     [rbp+0F0h+var_50], rax
0x18005d13d  mov     rbx, rcx
0x18005d140  xor     esi, esi
0x18005d142  movzx   eax, byte ptr [rcx+3C8h]
0x18005d149  nop
0x18005d14a  test    al, al
0x18005d14c  jz      short loc_18005D155
0x18005d14e  xor     eax, eax
0x18005d150  jmp     loc_18005DAE8
0x18005d155  lea     rax, [rcx+110h]
0x18005d15c  mov     [rsp+1F0h+lpCriticalSection], rax
0x18005d161  mov     rcx, rax; lpCriticalSection
0x18005d164  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18005d169  nop
0x18005d16a  movzx   eax, byte ptr [rbx+3C8h]
0x18005d171  nop
0x18005d172  test    al, al
0x18005d174  jz      short loc_18005D17D
0x18005d176  mov     ebx, esi
0x18005d178  jmp     loc_18005DADB
0x18005d17d  xorps   xmm0, xmm0
0x18005d180  movups  xmmword ptr [rsp+1F0h+pProxyConfig.fAutoDetect], xmm0
0x18005d185  movups  xmmword ptr [rsp+1F0h+pProxyConfig.lpszProxy], xmm0
0x18005d18a  mov     rdi, rsi
0x18005d18d  mov     r14, rsi
0x18005d190  mov     [rsp+1F0h+var_1B8], rsi
0x18005d195  mov     [rbx+3E1h], dil
0x18005d19c  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x18005d1a1  mov     [rsp+1F0h+var_178], rsi
0x18005d1a6  mov     [rbp+0F0h+var_170], 7
0x18005d1ae  mov     word ptr [rsp+1F0h+Src], si
0x18005d1b3  lea     rdx, S2; "/"
0x18005d1ba  lea     rcx, [rbp+0F0h+S1]
0x18005d1be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d1c3  nop
0x18005d1c4  lea     rax, [rbp+0F0h+var_140]
0x18005d1c8  mov     [rsp+1F0h+Buffer], rax
0x18005d1cd  xorps   xmm0, xmm0
0x18005d1d0  movups  xmmword ptr [rbp+0F0h+var_140], xmm0
0x18005d1d4  mov     [rbp+0F0h+var_130], rsi
0x18005d1d8  mov     [rbp+0F0h+var_128], 7
0x18005d1e0  mov     word ptr [rbp+0F0h+var_140], si
0x18005d1e4  movups  xmmword ptr [rbp+0F0h+var_120], xmm0
0x18005d1e8  mov     [rbp+0F0h+var_110], rsi
0x18005d1ec  mov     [rbp+0F0h+var_108], 7
0x18005d1f4  mov     word ptr [rbp+0F0h+var_120], si
0x18005d1f8  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x18005d1fc  mov     [rbp+0F0h+var_F0], rsi
0x18005d200  mov     [rbp+0F0h+var_E8], 7
0x18005d208  mov     word ptr [rbp+0F0h+var_100], si
0x18005d20c  lea     rdx, S2; "/"
0x18005d213  lea     rcx, [rbp+0F0h+var_E0]
0x18005d217  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d21c  xorps   xmm0, xmm0
0x18005d21f  movups  xmmword ptr [rbp+0F0h+var_C0], xmm0
0x18005d223  mov     [rbp+0F0h+var_B0], rsi
0x18005d227  mov     [rbp+0F0h+var_A8], 7
0x18005d22f  mov     word ptr [rbp+0F0h+var_C0], si
0x18005d233  movups  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x18005d237  mov     [rbp+0F0h+var_90], rsi
0x18005d23b  mov     [rbp+0F0h+var_88], 7
0x18005d243  mov     word ptr [rbp+0F0h+var_A0], si
0x18005d247  mov     [rbp+0F0h+var_80], 0FFFFFFFFh
0x18005d24e  mov     rcx, rbx; this
0x18005d251  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x18005d256  mov     r13, rax
0x18005d259  mov     [rsp+1F0h+Buffer], rax
0x18005d25e  lea     rsi, [rax+20h]
0x18005d262  mov     eax, [rsi+0E8h]
0x18005d268  mov     r15d, 1
0x18005d26e  test    eax, eax
0x18005d270  jnz     short loc_18005D27F
0x18005d272  call    web__http__client__details__WinHttpDefaultProxyConstant
0x18005d277  mov     r12d, eax
0x18005d27a  jmp     loc_18005D683
0x18005d27f  cmp     eax, 2
0x18005d282  jnz     short loc_18005D28C
0x18005d284  mov     r12d, r15d
0x18005d287  jmp     loc_18005D683
0x18005d28c  cmp     eax, r15d
0x18005d28f  jnz     loc_18005D372
0x18005d295  call    web__http__client__details__WinHttpDefaultProxyConstant
0x18005d29a  mov     r12d, eax
0x18005d29d  cmp     eax, 4
0x18005d2a0  jz      loc_18005D683
0x18005d2a6  mov     [rbx+3E1h], r15b
0x18005d2ad  xorps   xmm0, xmm0
0x18005d2b0  xor     eax, eax
0x18005d2b2  movups  xmmword ptr [rbp+0F0h+pProxyInfo.dwAccessType], xmm0
0x18005d2b9  mov     [rbp+0F0h+pProxyInfo.lpszProxyBypass], rax
0x18005d2c0  lea     rcx, [rbp+0F0h+pProxyInfo]; pProxyInfo
0x18005d2c7  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18005d2cd  test    eax, eax
0x18005d2cf  jz      short loc_18005D2DA
0x18005d2d1  cmp     [rbp+0F0h+pProxyInfo.dwAccessType], 1
0x18005d2d8  jnz     short loc_18005D345
0x18005d2da  lea     rcx, [rsp+1F0h+pProxyConfig]; pProxyConfig
0x18005d2df  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18005d2e5  test    eax, eax
0x18005d2e7  jz      short loc_18005D345
0x18005d2e9  cmp     [rsp+1F0h+pProxyConfig.fAutoDetect], 0
0x18005d2ee  jz      short loc_18005D2F9
0x18005d2f0  mov     byte ptr [rbx+3E1h], 1
0x18005d2f7  jmp     short loc_18005D345
0x18005d2f9  mov     rsi, [rsp+1F0h+pProxyConfig.lpszAutoConfigUrl]
0x18005d2fe  test    rsi, rsi
0x18005d301  jz      short loc_18005D326
0x18005d303  mov     byte ptr [rbx+3E1h], 1
0x18005d30a  mov     rcx, rsi; String
0x18005d30d  call    wcslen_0
0x18005d312  lea     rcx, [rbx+3E8h]
0x18005d319  mov     r8, rax
0x18005d31c  mov     rdx, rsi
0x18005d31f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d324  jmp     short loc_18005D345
0x18005d326  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxy]
0x18005d32b  test    rax, rax
0x18005d32e  jz      short loc_18005D345
0x18005d330  mov     r12d, 3
0x18005d336  mov     rdi, rax
0x18005d339  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxyBypass]
0x18005d33e  test    rax, rax
0x18005d341  cmovnz  r14, rax
0x18005d345  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxy]; hMem
0x18005d34c  test    rcx, rcx
0x18005d34f  jz      short loc_18005D357
0x18005d351  call    cs:__imp_GlobalFree
0x18005d357  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxyBypass]; hMem
0x18005d35e  test    rcx, rcx
0x18005d361  jz      loc_18005D683
0x18005d367  call    cs:__imp_GlobalFree
0x18005d36d  jmp     loc_18005D683
0x18005d372  mov     r12d, 3
0x18005d378  lea     rax, [rbp+0F0h+S1]
0x18005d37c  cmp     rax, rsi
0x18005d37f  jz      short loc_18005D39D
0x18005d381  cmp     qword ptr [rsi+18h], 7
0x18005d386  jbe     short loc_18005D38D
0x18005d388  mov     rdx, [rsi]
0x18005d38b  jmp     short loc_18005D390
0x18005d38d  mov     rdx, rsi
0x18005d390  mov     r8, [rsi+10h]
0x18005d394  lea     rcx, [rbp+0F0h+S1]
0x18005d398  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d39d  lea     rdi, [rsi+20h]
0x18005d3a1  lea     rax, [rbp+0F0h+var_140]
0x18005d3a5  cmp     rax, rdi
0x18005d3a8  jz      short loc_18005D3C6
0x18005d3aa  cmp     qword ptr [rdi+18h], 7
0x18005d3af  jbe     short loc_18005D3B6
0x18005d3b1  mov     rdx, [rdi]
0x18005d3b4  jmp     short loc_18005D3B9
0x18005d3b6  mov     rdx, rdi
0x18005d3b9  mov     r8, [rdi+10h]
0x18005d3bd  lea     rcx, [rbp+0F0h+var_140]
0x18005d3c1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d3c6  lea     r8, [rdi+20h]
0x18005d3ca  lea     rax, [rbp+0F0h+var_120]
0x18005d3ce  cmp     rax, r8
0x18005d3d1  jz      short loc_18005D3EF
0x18005d3d3  cmp     qword ptr [r8+18h], 7
0x18005d3d8  jbe     short loc_18005D3DF
0x18005d3da  mov     rdx, [r8]
0x18005d3dd  jmp     short loc_18005D3E2
0x18005d3df  mov     rdx, r8
0x18005d3e2  mov     r8, [r8+10h]
0x18005d3e6  lea     rcx, [rbp+0F0h+var_120]
0x18005d3ea  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d3ef  lea     r8, [rdi+40h]
0x18005d3f3  lea     rax, [rbp+0F0h+var_100]
0x18005d3f7  cmp     rax, r8
0x18005d3fa  jz      short loc_18005D418
0x18005d3fc  cmp     qword ptr [r8+18h], 7
0x18005d401  jbe     short loc_18005D408
0x18005d403  mov     rdx, [r8]
0x18005d406  jmp     short loc_18005D40B
0x18005d408  mov     rdx, r8
0x18005d40b  mov     r8, [r8+10h]
0x18005d40f  lea     rcx, [rbp+0F0h+var_100]
0x18005d413  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d418  lea     r8, [rdi+60h]
0x18005d41c  lea     rax, [rbp+0F0h+var_E0]
0x18005d420  cmp     rax, r8
0x18005d423  jz      short loc_18005D441
0x18005d425  cmp     qword ptr [r8+18h], 7
0x18005d42a  jbe     short loc_18005D431
0x18005d42c  mov     rdx, [r8]
0x18005d42f  jmp     short loc_18005D434
0x18005d431  mov     rdx, r8
0x18005d434  mov     r8, [r8+10h]
0x18005d438  lea     rcx, [rbp+0F0h+var_E0]
0x18005d43c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d441  lea     r8, [rdi+80h]
0x18005d448  lea     rax, [rbp+0F0h+var_C0]
0x18005d44c  cmp     rax, r8
0x18005d44f  jz      short loc_18005D46D
0x18005d451  cmp     qword ptr [r8+18h], 7
0x18005d456  jbe     short loc_18005D45D
0x18005d458  mov     rdx, [r8]
0x18005d45b  jmp     short loc_18005D460
0x18005d45d  mov     rdx, r8
0x18005d460  mov     r8, [r8+10h]
0x18005d464  lea     rcx, [rbp+0F0h+var_C0]
0x18005d468  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d46d  lea     r8, [rdi+0A0h]
0x18005d474  lea     rax, [rbp+0F0h+var_A0]
0x18005d478  cmp     rax, r8
0x18005d47b  jz      short loc_18005D499
0x18005d47d  cmp     qword ptr [r8+18h], 7
0x18005d482  jbe     short loc_18005D489
0x18005d484  mov     rdx, [r8]
0x18005d487  jmp     short loc_18005D48C
0x18005d489  mov     rdx, r8
0x18005d48c  mov     r8, [r8+10h]
0x18005d490  lea     rcx, [rbp+0F0h+var_A0]
0x18005d494  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d499  mov     eax, [rdi+0C0h]
0x18005d49f  mov     [rbp+0F0h+var_80], eax
0x18005d4a2  mov     r8, [rbp+0F0h+N]; N
0x18005d4a6  test    r8, r8
0x18005d4a9  jz      short loc_18005D4E8
0x18005d4ab  lea     rcx, [rbp+0F0h+S1]
0x18005d4af  cmp     [rbp+0F0h+var_148], 7
0x18005d4b4  cmova   rcx, [rbp+0F0h+S1]; S1
0x18005d4b9  cmp     r8, r15
0x18005d4bc  jnz     short loc_18005D4D1
0x18005d4be  lea     rdx, S2; "/"
0x18005d4c5  call    wmemcmp
0x18005d4ca  test    eax, eax
0x18005d4cc  jz      short loc_18005D4E8
0x18005d4ce  mov     eax, [rbp+0F0h+var_80]
0x18005d4d1  test    eax, eax
0x18005d4d3  jnz     short loc_18005D4E8
0x18005d4d5  lea     rdi, [rbp+0F0h+var_120]
0x18005d4d9  cmp     [rbp+0F0h+var_108], 7
0x18005d4de  cmova   rdi, [rbp+0F0h+var_120]
0x18005d4e3  jmp     loc_18005D683
0x18005d4e8  lea     rdx, [rbp+0F0h+var_120]
0x18005d4ec  cmp     [rbp+0F0h+var_108], 7
0x18005d4f1  cmova   rdx, [rbp+0F0h+var_120]
0x18005d4f6  mov     r8, [rbp+0F0h+var_110]
0x18005d4fa  lea     rcx, [rsp+1F0h+Src]
0x18005d4ff  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005d504  cmp     [rbp+0F0h+var_80], 0
0x18005d508  jle     loc_18005D673
0x18005d50e  mov     r14, [rsp+1F0h+var_178]
0x18005d513  mov     rsi, [rbp+0F0h+var_170]
0x18005d517  cmp     r14, rsi
0x18005d51a  jnb     short loc_18005D543
0x18005d51c  lea     rax, [r14+1]
0x18005d520  mov     [rsp+1F0h+var_178], rax
0x18005d525  lea     rax, [rsp+1F0h+Src]
0x18005d52a  cmp     rsi, 7
0x18005d52e  cmova   rax, [rsp+1F0h+Src]
0x18005d534  lea     rcx, [rax+r14*2]
0x18005d538  mov     dword ptr [rcx], 3Ah ; ':'
0x18005d53e  jmp     loc_18005D629
0x18005d543  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18005d54d  mov     rax, rdi
0x18005d550  sub     rax, r14
0x18005d553  cmp     rax, r15
0x18005d556  jb      loc_18005DB11
0x18005d55c  lea     r13, [r14+1]
0x18005d560  mov     rcx, r13
0x18005d563  or      rcx, 7
0x18005d567  cmp     rcx, rdi
0x18005d56a  ja      short loc_18005D58B
0x18005d56c  mov     rdx, rsi
0x18005d56f  shr     rdx, 1
0x18005d572  mov     rax, rdi
0x18005d575  sub     rax, rdx
0x18005d578  cmp     rsi, rax
0x18005d57b  ja      short loc_18005D58B
0x18005d57d  lea     rax, [rsi+rdx]
0x18005d581  mov     rdi, rcx
0x18005d584  cmp     rcx, rax
0x18005d587  cmovb   rdi, rax
0x18005d58b  lea     rdx, [rdi+1]
0x18005d58f  lea     rcx, [rsp+1F0h+Src]
0x18005d594  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18005d599  mov     r15, rax
0x18005d59c  mov     [rsp+1F0h+var_178], r13
0x18005d5a1  mov     [rbp+0F0h+var_170], rdi
0x18005d5a5  add     r14, r14
0x18005d5a8  mov     r8, r14; Size
0x18005d5ab  mov     rcx, rax; void *
0x18005d5ae  cmp     rsi, 7
0x18005d5b2  jbe     short loc_18005D607
  ... truncated ...
```
