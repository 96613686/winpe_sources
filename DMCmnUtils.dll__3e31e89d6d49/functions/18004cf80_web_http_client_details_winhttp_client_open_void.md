# web::http::client::details::winhttp_client::open(void)

- ea: `0x18004cf80`
- end: `0x18004d987`
- name: `?open@winhttp_client@details@client@http@web@@IEAAKXZ`
- size: `2567`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004e950`

## callees

- `0x180007270`
- `0x180007640`
- `0x180009200`
- `0x1800092d0`
- `0x18002a210`
- `0x18003d210`
- `0x180046b20`
- `0x18004cf80`
- `0x180050d77`
- `0x180052296`
- `0x1800522ae`
- `0x18005b348`
- `0x18005b73c`
- `0x18005b8d0`
- `0x18005bc34`
- `0x18005bc54`
- `0x180073bd8`
- `0x180073d1c`
- `0x180095464`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d66e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d1c1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d1d7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d924`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d934`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d944`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d1c1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d1d7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d924`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d934`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18004d944`
- `WINHTTP!WinHttpConnect` at `0x18004d65c`
- `WINHTTP!WinHttpConnect` at `0x18004d65c`
- `WINHTTP!WinHttpSetOption` at `0x18004d583`
- `WINHTTP!WinHttpSetOption` at `0x18004d5b0`
- `WINHTTP!WinHttpSetOption` at `0x18004d583`
- `WINHTTP!WinHttpSetOption` at `0x18004d5b0`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18004d137`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x18004d137`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18004d60c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18004d60c`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18004d14f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x18004d14f`
- `WINHTTP!WinHttpOpen` at `0x18004d506`
- `WINHTTP!WinHttpOpen` at `0x18004d506`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004d54f`
- `WINHTTP!WinHttpSetTimeouts` at `0x18004d54f`

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
      std::wstring::~wstring(&pProxyInfo);
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
0x18004cf80  push    rbp
0x18004cf82  push    rbx
0x18004cf83  push    rsi
0x18004cf84  push    rdi
0x18004cf85  push    r12
0x18004cf87  push    r13
0x18004cf89  push    r14
0x18004cf8b  push    r15
0x18004cf8d  lea     rbp, [rsp-0B8h]
0x18004cf95  sub     rsp, 1B8h
0x18004cf9c  mov     rax, cs:__security_cookie
0x18004cfa3  xor     rax, rsp
0x18004cfa6  mov     [rbp+0F0h+var_50], rax
0x18004cfad  mov     rbx, rcx
0x18004cfb0  xor     esi, esi
0x18004cfb2  movzx   eax, byte ptr [rcx+3C8h]
0x18004cfb9  nop
0x18004cfba  test    al, al
0x18004cfbc  jz      short loc_18004CFC5
0x18004cfbe  xor     eax, eax
0x18004cfc0  jmp     loc_18004D958
0x18004cfc5  lea     rax, [rcx+110h]
0x18004cfcc  mov     [rsp+1F0h+lpCriticalSection], rax
0x18004cfd1  mov     rcx, rax; lpCriticalSection
0x18004cfd4  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18004cfd9  nop
0x18004cfda  movzx   eax, byte ptr [rbx+3C8h]
0x18004cfe1  nop
0x18004cfe2  test    al, al
0x18004cfe4  jz      short loc_18004CFED
0x18004cfe6  mov     ebx, esi
0x18004cfe8  jmp     loc_18004D94B
0x18004cfed  xorps   xmm0, xmm0
0x18004cff0  movups  xmmword ptr [rsp+1F0h+pProxyConfig.fAutoDetect], xmm0
0x18004cff5  movups  xmmword ptr [rsp+1F0h+pProxyConfig.lpszProxy], xmm0
0x18004cffa  mov     rdi, rsi
0x18004cffd  mov     r14, rsi
0x18004d000  mov     [rsp+1F0h+var_1B8], rsi
0x18004d005  mov     [rbx+3E1h], dil
0x18004d00c  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x18004d011  mov     [rsp+1F0h+var_178], rsi
0x18004d016  mov     [rbp+0F0h+var_170], 7
0x18004d01e  mov     word ptr [rsp+1F0h+Src], si
0x18004d023  lea     rdx, S2; "/"
0x18004d02a  lea     rcx, [rbp+0F0h+S1]
0x18004d02e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d033  nop
0x18004d034  lea     rax, [rbp+0F0h+var_140]
0x18004d038  mov     [rsp+1F0h+Buffer], rax
0x18004d03d  xorps   xmm0, xmm0
0x18004d040  movups  xmmword ptr [rbp+0F0h+var_140], xmm0
0x18004d044  mov     [rbp+0F0h+var_130], rsi
0x18004d048  mov     [rbp+0F0h+var_128], 7
0x18004d050  mov     word ptr [rbp+0F0h+var_140], si
0x18004d054  movups  xmmword ptr [rbp+0F0h+var_120], xmm0
0x18004d058  mov     [rbp+0F0h+var_110], rsi
0x18004d05c  mov     [rbp+0F0h+var_108], 7
0x18004d064  mov     word ptr [rbp+0F0h+var_120], si
0x18004d068  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x18004d06c  mov     [rbp+0F0h+var_F0], rsi
0x18004d070  mov     [rbp+0F0h+var_E8], 7
0x18004d078  mov     word ptr [rbp+0F0h+var_100], si
0x18004d07c  lea     rdx, S2; "/"
0x18004d083  lea     rcx, [rbp+0F0h+var_E0]
0x18004d087  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d08c  xorps   xmm0, xmm0
0x18004d08f  movups  xmmword ptr [rbp+0F0h+var_C0], xmm0
0x18004d093  mov     [rbp+0F0h+var_B0], rsi
0x18004d097  mov     [rbp+0F0h+var_A8], 7
0x18004d09f  mov     word ptr [rbp+0F0h+var_C0], si
0x18004d0a3  movups  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x18004d0a7  mov     [rbp+0F0h+var_90], rsi
0x18004d0ab  mov     [rbp+0F0h+var_88], 7
0x18004d0b3  mov     word ptr [rbp+0F0h+var_A0], si
0x18004d0b7  mov     [rbp+0F0h+var_80], 0FFFFFFFFh
0x18004d0be  mov     rcx, rbx; this
0x18004d0c1  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x18004d0c6  mov     r13, rax
0x18004d0c9  mov     [rsp+1F0h+Buffer], rax
0x18004d0ce  lea     rsi, [rax+20h]
0x18004d0d2  mov     eax, [rsi+0E8h]
0x18004d0d8  mov     r15d, 1
0x18004d0de  test    eax, eax
0x18004d0e0  jnz     short loc_18004D0EF
0x18004d0e2  call    web__http__client__details__WinHttpDefaultProxyConstant
0x18004d0e7  mov     r12d, eax
0x18004d0ea  jmp     loc_18004D4F3
0x18004d0ef  cmp     eax, 2
0x18004d0f2  jnz     short loc_18004D0FC
0x18004d0f4  mov     r12d, r15d
0x18004d0f7  jmp     loc_18004D4F3
0x18004d0fc  cmp     eax, r15d
0x18004d0ff  jnz     loc_18004D1E2
0x18004d105  call    web__http__client__details__WinHttpDefaultProxyConstant
0x18004d10a  mov     r12d, eax
0x18004d10d  cmp     eax, 4
0x18004d110  jz      loc_18004D4F3
0x18004d116  mov     [rbx+3E1h], r15b
0x18004d11d  xorps   xmm0, xmm0
0x18004d120  xor     eax, eax
0x18004d122  movups  xmmword ptr [rbp+0F0h+pProxyInfo.dwAccessType], xmm0
0x18004d129  mov     [rbp+0F0h+pProxyInfo.lpszProxyBypass], rax
0x18004d130  lea     rcx, [rbp+0F0h+pProxyInfo]; pProxyInfo
0x18004d137  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x18004d13d  test    eax, eax
0x18004d13f  jz      short loc_18004D14A
0x18004d141  cmp     [rbp+0F0h+pProxyInfo.dwAccessType], 1
0x18004d148  jnz     short loc_18004D1B5
0x18004d14a  lea     rcx, [rsp+1F0h+pProxyConfig]; pProxyConfig
0x18004d14f  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18004d155  test    eax, eax
0x18004d157  jz      short loc_18004D1B5
0x18004d159  cmp     [rsp+1F0h+pProxyConfig.fAutoDetect], 0
0x18004d15e  jz      short loc_18004D169
0x18004d160  mov     byte ptr [rbx+3E1h], 1
0x18004d167  jmp     short loc_18004D1B5
0x18004d169  mov     rsi, [rsp+1F0h+pProxyConfig.lpszAutoConfigUrl]
0x18004d16e  test    rsi, rsi
0x18004d171  jz      short loc_18004D196
0x18004d173  mov     byte ptr [rbx+3E1h], 1
0x18004d17a  mov     rcx, rsi; String
0x18004d17d  call    wcslen_0
0x18004d182  lea     rcx, [rbx+3E8h]
0x18004d189  mov     r8, rax
0x18004d18c  mov     rdx, rsi
0x18004d18f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d194  jmp     short loc_18004D1B5
0x18004d196  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxy]
0x18004d19b  test    rax, rax
0x18004d19e  jz      short loc_18004D1B5
0x18004d1a0  mov     r12d, 3
0x18004d1a6  mov     rdi, rax
0x18004d1a9  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxyBypass]
0x18004d1ae  test    rax, rax
0x18004d1b1  cmovnz  r14, rax
0x18004d1b5  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxy]; hMem
0x18004d1bc  test    rcx, rcx
0x18004d1bf  jz      short loc_18004D1C7
0x18004d1c1  call    cs:__imp_GlobalFree
0x18004d1c7  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxyBypass]; hMem
0x18004d1ce  test    rcx, rcx
0x18004d1d1  jz      loc_18004D4F3
0x18004d1d7  call    cs:__imp_GlobalFree
0x18004d1dd  jmp     loc_18004D4F3
0x18004d1e2  mov     r12d, 3
0x18004d1e8  lea     rax, [rbp+0F0h+S1]
0x18004d1ec  cmp     rax, rsi
0x18004d1ef  jz      short loc_18004D20D
0x18004d1f1  cmp     qword ptr [rsi+18h], 7
0x18004d1f6  jbe     short loc_18004D1FD
0x18004d1f8  mov     rdx, [rsi]
0x18004d1fb  jmp     short loc_18004D200
0x18004d1fd  mov     rdx, rsi
0x18004d200  mov     r8, [rsi+10h]
0x18004d204  lea     rcx, [rbp+0F0h+S1]
0x18004d208  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d20d  lea     rdi, [rsi+20h]
0x18004d211  lea     rax, [rbp+0F0h+var_140]
0x18004d215  cmp     rax, rdi
0x18004d218  jz      short loc_18004D236
0x18004d21a  cmp     qword ptr [rdi+18h], 7
0x18004d21f  jbe     short loc_18004D226
0x18004d221  mov     rdx, [rdi]
0x18004d224  jmp     short loc_18004D229
0x18004d226  mov     rdx, rdi
0x18004d229  mov     r8, [rdi+10h]
0x18004d22d  lea     rcx, [rbp+0F0h+var_140]
0x18004d231  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d236  lea     r8, [rdi+20h]
0x18004d23a  lea     rax, [rbp+0F0h+var_120]
0x18004d23e  cmp     rax, r8
0x18004d241  jz      short loc_18004D25F
0x18004d243  cmp     qword ptr [r8+18h], 7
0x18004d248  jbe     short loc_18004D24F
0x18004d24a  mov     rdx, [r8]
0x18004d24d  jmp     short loc_18004D252
0x18004d24f  mov     rdx, r8
0x18004d252  mov     r8, [r8+10h]
0x18004d256  lea     rcx, [rbp+0F0h+var_120]
0x18004d25a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d25f  lea     r8, [rdi+40h]
0x18004d263  lea     rax, [rbp+0F0h+var_100]
0x18004d267  cmp     rax, r8
0x18004d26a  jz      short loc_18004D288
0x18004d26c  cmp     qword ptr [r8+18h], 7
0x18004d271  jbe     short loc_18004D278
0x18004d273  mov     rdx, [r8]
0x18004d276  jmp     short loc_18004D27B
0x18004d278  mov     rdx, r8
0x18004d27b  mov     r8, [r8+10h]
0x18004d27f  lea     rcx, [rbp+0F0h+var_100]
0x18004d283  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d288  lea     r8, [rdi+60h]
0x18004d28c  lea     rax, [rbp+0F0h+var_E0]
0x18004d290  cmp     rax, r8
0x18004d293  jz      short loc_18004D2B1
0x18004d295  cmp     qword ptr [r8+18h], 7
0x18004d29a  jbe     short loc_18004D2A1
0x18004d29c  mov     rdx, [r8]
0x18004d29f  jmp     short loc_18004D2A4
0x18004d2a1  mov     rdx, r8
0x18004d2a4  mov     r8, [r8+10h]
0x18004d2a8  lea     rcx, [rbp+0F0h+var_E0]
0x18004d2ac  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d2b1  lea     r8, [rdi+80h]
0x18004d2b8  lea     rax, [rbp+0F0h+var_C0]
0x18004d2bc  cmp     rax, r8
0x18004d2bf  jz      short loc_18004D2DD
0x18004d2c1  cmp     qword ptr [r8+18h], 7
0x18004d2c6  jbe     short loc_18004D2CD
0x18004d2c8  mov     rdx, [r8]
0x18004d2cb  jmp     short loc_18004D2D0
0x18004d2cd  mov     rdx, r8
0x18004d2d0  mov     r8, [r8+10h]
0x18004d2d4  lea     rcx, [rbp+0F0h+var_C0]
0x18004d2d8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d2dd  lea     r8, [rdi+0A0h]
0x18004d2e4  lea     rax, [rbp+0F0h+var_A0]
0x18004d2e8  cmp     rax, r8
0x18004d2eb  jz      short loc_18004D309
0x18004d2ed  cmp     qword ptr [r8+18h], 7
0x18004d2f2  jbe     short loc_18004D2F9
0x18004d2f4  mov     rdx, [r8]
0x18004d2f7  jmp     short loc_18004D2FC
0x18004d2f9  mov     rdx, r8
0x18004d2fc  mov     r8, [r8+10h]
0x18004d300  lea     rcx, [rbp+0F0h+var_A0]
0x18004d304  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d309  mov     eax, [rdi+0C0h]
0x18004d30f  mov     [rbp+0F0h+var_80], eax
0x18004d312  mov     r8, [rbp+0F0h+N]; N
0x18004d316  test    r8, r8
0x18004d319  jz      short loc_18004D358
0x18004d31b  lea     rcx, [rbp+0F0h+S1]
0x18004d31f  cmp     [rbp+0F0h+var_148], 7
0x18004d324  cmova   rcx, [rbp+0F0h+S1]; S1
0x18004d329  cmp     r8, r15
0x18004d32c  jnz     short loc_18004D341
0x18004d32e  lea     rdx, S2; "/"
0x18004d335  call    wmemcmp
0x18004d33a  test    eax, eax
0x18004d33c  jz      short loc_18004D358
0x18004d33e  mov     eax, [rbp+0F0h+var_80]
0x18004d341  test    eax, eax
0x18004d343  jnz     short loc_18004D358
0x18004d345  lea     rdi, [rbp+0F0h+var_120]
0x18004d349  cmp     [rbp+0F0h+var_108], 7
0x18004d34e  cmova   rdi, [rbp+0F0h+var_120]
0x18004d353  jmp     loc_18004D4F3
0x18004d358  lea     rdx, [rbp+0F0h+var_120]
0x18004d35c  cmp     [rbp+0F0h+var_108], 7
0x18004d361  cmova   rdx, [rbp+0F0h+var_120]
0x18004d366  mov     r8, [rbp+0F0h+var_110]
0x18004d36a  lea     rcx, [rsp+1F0h+Src]
0x18004d36f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d374  cmp     [rbp+0F0h+var_80], 0
0x18004d378  jle     loc_18004D4E3
0x18004d37e  mov     r14, [rsp+1F0h+var_178]
0x18004d383  mov     rsi, [rbp+0F0h+var_170]
0x18004d387  cmp     r14, rsi
0x18004d38a  jnb     short loc_18004D3B3
0x18004d38c  lea     rax, [r14+1]
0x18004d390  mov     [rsp+1F0h+var_178], rax
0x18004d395  lea     rax, [rsp+1F0h+Src]
0x18004d39a  cmp     rsi, 7
0x18004d39e  cmova   rax, [rsp+1F0h+Src]
0x18004d3a4  lea     rcx, [rax+r14*2]
0x18004d3a8  mov     dword ptr [rcx], 3Ah ; ':'
0x18004d3ae  jmp     loc_18004D499
0x18004d3b3  mov     rdi, 7FFFFFFFFFFFFFFEh
0x18004d3bd  mov     rax, rdi
0x18004d3c0  sub     rax, r14
0x18004d3c3  cmp     rax, r15
0x18004d3c6  jb      loc_18004D981
0x18004d3cc  lea     r13, [r14+1]
0x18004d3d0  mov     rcx, r13
0x18004d3d3  or      rcx, 7
0x18004d3d7  cmp     rcx, rdi
0x18004d3da  ja      short loc_18004D3FB
0x18004d3dc  mov     rdx, rsi
0x18004d3df  shr     rdx, 1
0x18004d3e2  mov     rax, rdi
0x18004d3e5  sub     rax, rdx
0x18004d3e8  cmp     rsi, rax
0x18004d3eb  ja      short loc_18004D3FB
0x18004d3ed  lea     rax, [rsi+rdx]
0x18004d3f1  mov     rdi, rcx
0x18004d3f4  cmp     rcx, rax
0x18004d3f7  cmovb   rdi, rax
0x18004d3fb  lea     rdx, [rdi+1]
0x18004d3ff  lea     rcx, [rsp+1F0h+Src]
0x18004d404  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18004d409  mov     r15, rax
0x18004d40c  mov     [rsp+1F0h+var_178], r13
0x18004d411  mov     [rbp+0F0h+var_170], rdi
0x18004d415  add     r14, r14
0x18004d418  mov     r8, r14; Size
0x18004d41b  mov     rcx, rax; void *
0x18004d41e  cmp     rsi, 7
0x18004d422  jbe     short loc_18004D477
  ... truncated ...
```
