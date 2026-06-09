# CEcsAdfs::GetAuthorizationCode(ushort const *,ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800c9c08`
- end: `0x1800caa3c`
- name: `?GetAuthorizationCode@CEcsAdfs@@SAJPEBG0KAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3636`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18006f7c0`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x1800084ac`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180015150`
- `0x18001db74`
- `0x180028490`
- `0x180028984`
- `0x180035564`
- `0x180067658`
- `0x18006770c`
- `0x1800678ac`
- `0x1800c91b8`
- `0x1800c91fc`
- `0x1800c938c`
- `0x1800c9888`
- `0x1800c9c08`
- `0x1800caa44`
- `0x1800cd324`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ca1d2`
- `KERNEL32!GetLastError` at `0x1800ca666`
- `KERNEL32!GetLastError` at `0x1800ca1d2`
- `KERNEL32!GetLastError` at `0x1800ca666`
- `WINHTTP!WinHttpCrackUrl` at `0x1800c9f44`
- `WINHTTP!WinHttpCrackUrl` at `0x1800c9f44`
- `WINHTTP!WinHttpConnect` at `0x1800ca00a`
- `WINHTTP!WinHttpConnect` at `0x1800ca00a`
- `WINHTTP!WinHttpOpen` at `0x1800c9d7f`
- `WINHTTP!WinHttpOpen` at `0x1800c9d7f`
- `WINHTTP!WinHttpSetCredentials` at `0x1800ca117`
- `WINHTTP!WinHttpSetCredentials` at `0x1800ca390`
- `WINHTTP!WinHttpSetCredentials` at `0x1800ca117`
- `WINHTTP!WinHttpSetCredentials` at `0x1800ca390`
- `WINHTTP!WinHttpSendRequest` at `0x1800ca179`
- `WINHTTP!WinHttpSendRequest` at `0x1800ca440`
- `WINHTTP!WinHttpSendRequest` at `0x1800ca179`
- `WINHTTP!WinHttpSendRequest` at `0x1800ca440`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800ca1c4`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800ca48f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800ca1c4`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800ca48f`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca546`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca658`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca736`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca546`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca658`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800ca736`
- `WINHTTP!WinHttpOpenRequest` at `0x1800ca067`
- `WINHTTP!WinHttpOpenRequest` at `0x1800ca270`
- `WINHTTP!WinHttpOpenRequest` at `0x1800ca067`
- `WINHTTP!WinHttpOpenRequest` at `0x1800ca270`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800c9dd2`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800c9dd2`
- `WINHTTP!WinHttpSetOption` at `0x1800c9e30`
- `WINHTTP!WinHttpSetOption` at `0x1800ca0b6`
- `WINHTTP!WinHttpSetOption` at `0x1800ca2d1`
- `WINHTTP!WinHttpSetOption` at `0x1800ca32f`
- `WINHTTP!WinHttpSetOption` at `0x1800c9e30`
- `WINHTTP!WinHttpSetOption` at `0x1800ca0b6`
- `WINHTTP!WinHttpSetOption` at `0x1800ca2d1`
- `WINHTTP!WinHttpSetOption` at `0x1800ca32f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CEcsAdfs::GetAuthorizationCode(__int64 a1, __int64 a2, DWORD a3, __int64 a4)
{
  _BYTE *v8; // rax
  char v9; // al
  int v10; // edx
  int FullAuthorizationUri; // eax
  HINTERNET v12; // rax
  void *v13; // rdi
  int v14; // r15d
  __int64 v15; // rax
  __int64 v16; // r10
  const WCHAR *v17; // rax
  const WCHAR *v18; // rax
  INTERNET_PORT v19; // r8
  HINTERNET v20; // rax
  HINTERNET v21; // rax
  void *v22; // rbx
  signed int LastError; // ecx
  HINTERNET v24; // rax
  bool v25; // al
  int v26; // eax
  int v27; // eax
  void *Pointer; // rax
  signed int v29; // eax
  int v30; // ecx
  void *v31; // rax
  __int64 v32; // rax
  int AuthorizationCode; // eax
  __int64 v34; // rax
  __int64 v35; // r8
  unsigned int v36; // ebx
  int v38; // [rsp+40h] [rbp-3E8h] BYREF
  int v39; // [rsp+44h] [rbp-3E4h]
  char v40; // [rsp+48h] [rbp-3E0h]
  const char *v41; // [rsp+50h] [rbp-3D8h]
  __int64 v42; // [rsp+58h] [rbp-3D0h]
  DWORD dwBufferLength; // [rsp+60h] [rbp-3C8h] BYREF
  unsigned int Buffer; // [rsp+64h] [rbp-3C4h] BYREF
  HINTERNET hRequest; // [rsp+68h] [rbp-3C0h] BYREF
  HINTERNET hConnect; // [rsp+70h] [rbp-3B8h] BYREF
  int v47; // [rsp+78h] [rbp-3B0h]
  LPVOID lpBuffer; // [rsp+80h] [rbp-3A8h] BYREF
  int v49; // [rsp+88h] [rbp-3A0h] BYREF
  int v50; // [rsp+8Ch] [rbp-39Ch] BYREF
  int v51; // [rsp+90h] [rbp-398h] BYREF
  int v52; // [rsp+94h] [rbp-394h] BYREF
  int v53; // [rsp+98h] [rbp-390h] BYREF
  int v54; // [rsp+9Ch] [rbp-38Ch] BYREF
  int v55; // [rsp+A0h] [rbp-388h] BYREF
  int v56; // [rsp+A4h] [rbp-384h] BYREF
  int v57; // [rsp+A8h] [rbp-380h] BYREF
  signed int v58; // [rsp+ACh] [rbp-37Ch] BYREF
  int v59; // [rsp+B0h] [rbp-378h] BYREF
  int v60; // [rsp+B4h] [rbp-374h] BYREF
  signed int v61; // [rsp+B8h] [rbp-370h] BYREF
  int v62; // [rsp+BCh] [rbp-36Ch] BYREF
  int v63; // [rsp+C0h] [rbp-368h] BYREF
  int v64; // [rsp+C4h] [rbp-364h] BYREF
  int v65; // [rsp+C8h] [rbp-360h] BYREF
  int v66; // [rsp+CCh] [rbp-35Ch] BYREF
  int v67; // [rsp+D0h] [rbp-358h] BYREF
  int v68; // [rsp+D4h] [rbp-354h] BYREF
  int LastFailureAsHRESULT; // [rsp+D8h] [rbp-350h] BYREF
  int pExceptionObject; // [rsp+DCh] [rbp-34Ch] BYREF
  int v71; // [rsp+E0h] [rbp-348h] BYREF
  int v72; // [rsp+E4h] [rbp-344h] BYREF
  HINTERNET hInternet; // [rsp+E8h] [rbp-340h] BYREF
  int v74; // [rsp+F0h] [rbp-338h] BYREF
  int v75; // [rsp+F4h] [rbp-334h] BYREF
  const ATL::CAtlException *v76; // [rsp+F8h] [rbp-330h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+100h] [rbp-328h] BYREF
  _BYTE v78[32]; // [rsp+170h] [rbp-2B8h] BYREF
  _BYTE v79[16]; // [rsp+190h] [rbp-298h] BYREF
  __int64 v80; // [rsp+1A0h] [rbp-288h]
  _BYTE v81[32]; // [rsp+1B0h] [rbp-278h] BYREF
  _QWORD v82[2]; // [rsp+1D0h] [rbp-258h] BYREF
  _BYTE v83[512]; // [rsp+1E0h] [rbp-248h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v9 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( (v8[68] & 2) == 0 || v8[65] < 6u )
    goto LABEL_8;
  v9 = 1;
LABEL_9:
  v38 = 0;
  v39 = 687;
  v40 = v9;
  v41 = "CEcsAdfs::GetAuthorizationCode";
  v42 = 0;
  std::wstring::_Eos(a4, 0);
  try
  {
    v47 = 0;
    Buffer = 0;
    dwBufferLength = 0;
    v82[0] = 256;
    v82[1] = 0;
    memset_0(v83, v10, sizeof(v83));
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hInternet);
    std::wstring::wstring((__int64)v78);
    std::wstring::wstring((__int64)v81);
    std::wstring::wstring((__int64)v79);
    FullAuthorizationUri = CEcsAdfs::GetFullAuthorizationUri(a1, a2, v78);
    v38 = FullAuthorizationUri;
    if ( FullAuthorizationUri < 0 )
    {
      HIWORD(v39) = 709;
      pExceptionObject = FullAuthorizationUri;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v39) = 709;
    v12 = WinHttpOpen(L"MS_WorkFoldersClient", 4u, 0, 0, 0);
    std::unique_ptr<void *,WinHttpDeleter>::reset(&hInternet, v12);
    v13 = hInternet;
    if ( !hInternet )
    {
      HIWORD(v39) = 717;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    LOWORD(v39) = 717;
    v38 = 0;
    if ( !WinHttpSetTimeouts(hInternet, 6000, 6000, 6000, 6000) )
    {
      HIWORD(v39) = 721;
      v71 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v71;
    }
    LOWORD(v39) = 721;
    v38 = 0;
    if ( !WinHttpSetOption(v13, 0x58u, &dword_18015ECDC, 4u) )
    {
      HIWORD(v39) = 727;
      v72 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v72;
    }
    v38 = 0;
    LOWORD(v39) = 727;
    v14 = 0;
    v47 = 0;
    while ( v14 < 10 )
    {
      memset_0(&UrlComponents, 0, sizeof(UrlComponents));
      ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hConnect);
      ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&hRequest);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78);
        WPP_SF_S(*(_QWORD *)(v16 + 56), 24, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, v15);
      }
      UrlComponents.dwStructSize = 104;
      UrlComponents.dwHostNameLength = 1;
      UrlComponents.dwUrlPathLength = 1;
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78);
      if ( !WinHttpCrackUrl(v17, 0, 0x4000u, &UrlComponents) )
      {
        HIWORD(v39) = 744;
        v74 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v74;
      }
      LOWORD(v39) = 744;
      v38 = 0;
      if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER
        || !UrlComponents.lpszHostName
        || !UrlComponents.dwHostNameLength
        || !UrlComponents.lpszUrlPath
        || !UrlComponents.dwUrlPathLength )
      {
        v38 = -2147418113;
        HIWORD(v39) = 749;
        v67 = -2147418113;
        throw (long *)&v67;
      }
      v38 = 0;
      LOWORD(v39) = 749;
      std::wstring::assign(v81, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v81);
      v20 = WinHttpConnect(v13, v18, v19, 0);
      std::unique_ptr<void *,WinHttpDeleter>::reset(&hConnect, v20);
      if ( !hConnect )
      {
        HIWORD(v39) = 758;
        v66 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v66;
      }
      v38 = 0;
      LOWORD(v39) = 758;
      v21 = WinHttpOpenRequest(hConnect, L"GET", (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, 0x800100u);
      std::unique_ptr<void *,WinHttpDeleter>::reset(&hRequest, v21);
      v22 = hRequest;
      if ( !hRequest )
      {
        HIWORD(v39) = 768;
        v65 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v65;
      }
      LOWORD(v39) = 768;
      v38 = 0;
      if ( !WinHttpSetOption(hRequest, 0x4Du, byte_18015ECD8, 4u) )
      {
        HIWORD(v39) = 773;
        v49 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v49;
      }
      LOWORD(v39) = 773;
      v38 = 0;
      if ( !WinHttpSetCredentials(v22, a3, 0x10u, 0, 0, 0) )
      {
        HIWORD(v39) = 782;
        v50 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v50;
      }
      LOWORD(v39) = 782;
      v38 = 0;
      if ( !WinHttpSendRequest(v22, 0, 0, 0, 0, 0, 0) )
      {
        HIWORD(v39) = 790;
        v51 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v51;
      }
      v38 = 0;
      LOWORD(v39) = 790;
      if ( WinHttpReceiveResponse(v22, 0) )
      {
        v26 = v38;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 12044 )
        {
          FindClientCertificate(&lpBuffer, v22);
          if ( !std::operator!=<CFileDownloadTask>(&lpBuffer)
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids);
          }
          std::unique_ptr<void *,WinHttpDeleter>::reset(&hRequest, 0);
          v24 = WinHttpOpenRequest(hConnect, L"GET", (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, 0, 0x800100u);
          std::unique_ptr<void *,WinHttpDeleter>::reset(&hRequest, v24);
          v22 = hRequest;
          if ( !hRequest )
          {
            HIWORD(v39) = 818;
            v55 = EcsGetLastFailureAsHRESULT();
            throw (long *)&v55;
          }
          LOWORD(v39) = 818;
          v38 = 0;
          v25 = std::operator!=<CFileDownloadTask>(&lpBuffer);
          if ( !WinHttpSetOption(v22, 0x2Fu, lpBuffer, v25 ? 0x28 : 0) )
          {
            HIWORD(v39) = 823;
            v52 = EcsGetLastFailureAsHRESULT();
            throw (long *)&v52;
          }
          LOWORD(v39) = 823;
          v38 = 0;
          if ( !WinHttpSetOption(v22, 0x4Du, byte_18015ECD8, 4u) )
          {
            HIWORD(v39) = 828;
            v53 = EcsGetLastFailureAsHRESULT();
            throw (long *)&v53;
          }
          LOWORD(v39) = 828;
          v38 = 0;
          if ( !WinHttpSetCredentials(v22, a3, 0x10u, 0, 0, 0) )
          {
            HIWORD(v39) = 835;
            v54 = EcsGetLastFailureAsHRESULT();
            throw (long *)&v54;
          }
          v38 = 0;
          LOWORD(v39) = 835;
          std::unique_ptr<_CERT_CONTEXT const,CertContextDeleter>::~unique_ptr<_CERT_CONTEXT const,CertContextDeleter>(&lpBuffer);
        }
        else if ( LastError != 12032 )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v38 = LastError;
          HIWORD(v39) = 843;
          v58 = LastError;
          throw (long *)&v58;
        }
        if ( !WinHttpSendRequest(v22, 0, 0, 0, 0, 0, 0) )
        {
          HIWORD(v39) = 854;
          v56 = EcsGetLastFailureAsHRESULT();
          throw (long *)&v56;
        }
        LOWORD(v39) = 854;
        v38 = 0;
        if ( !WinHttpReceiveResponse(v22, 0) )
        {
          HIWORD(v39) = 856;
          v57 = EcsGetLastFailureAsHRESULT();
          throw (long *)&v57;
        }
        v26 = 0;
        v38 = 0;
        LOWORD(v39) = 856;
      }
      dwBufferLength = 4;
      v38 = v26;
      if ( !WinHttpQueryHeaders(v22, 0x20000013u, 0, &Buffer, &dwBufferLength, 0) )
      {
        HIWORD(v39) = 866;
        v59 = EcsGetLastFailureAsHRESULT();
        throw (long *)&v59;
      }
      v27 = 0;
      v38 = 0;
      LOWORD(v39) = 866;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids, Buffer);
        v27 = v38;
      }
      v38 = v27;
      if ( Buffer - 301 > 2 && Buffer != 307 )
      {
        v38 = -2134376415;
        HIWORD(v39) = 876;
        v60 = -2134376415;
        throw (long *)&v60;
      }
      v38 = 0;
      LOWORD(v39) = 876;
      dwBufferLength = 2 * LODWORD(v82[0]);
      Pointer = (void *)CEcsPreallocArray<unsigned short,256>::GetPointer(v82);
      if ( !WinHttpQueryHeaders(v22, 0x21u, 0, Pointer, &dwBufferLength, 0) )
      {
        v29 = GetLastError();
        if ( v29 != 122 )
        {
          if ( v29 > 0 )
            v29 = (unsigned __int16)v29 | 0x80070000;
          v38 = v29;
          HIWORD(v39) = 893;
          v61 = v29;
          throw (long *)&v61;
        }
        dwBufferLength >>= 1;
        v30 = CEcsPreallocArray<unsigned short,256>::Alloc(v82, dwBufferLength);
        v38 = v30;
        if ( v30 < 0 )
        {
          HIWORD(v39) = 899;
          v62 = v30;
          throw (long *)&v62;
        }
        LOWORD(v39) = 899;
        dwBufferLength *= 2;
        v38 = v30;
        v31 = (void *)CEcsPreallocArray<unsigned short,256>::GetPointer(v82);
        if ( !WinHttpQueryHeaders(v22, 0x21u, 0, v31, &dwBufferLength, 0) )
        {
          HIWORD(v39) = 907;
          v63 = EcsGetLastFailureAsHRESULT();
          throw (long *)&v63;
        }
        v38 = 0;
        LOWORD(v39) = 907;
      }
      v32 = CEcsPreallocArray<unsigned short,256>::GetPointer(v82);
      AuthorizationCode = CEcsAdfs::ExtractAuthorizationCode(v32, v79);
      v38 = AuthorizationCode;
      if ( AuthorizationCode < 0 )
      {
        HIWORD(v39) = 914;
        v64 = AuthorizationCode;
        throw (long *)&v64;
      }
      LOWORD(v39) = 914;
      if ( v80 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids);
        }
        std::wstring::swap(a4, v79);
        std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hRequest);
        std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hConnect);
        break;
      }
      v34 = CEcsPreallocArray<unsigned short,256>::GetPointer(v82);
      std::wstring::assign(v78, v34, v35);
      std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hRequest);
      std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hConnect);
      v47 = ++v14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        28,
        WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids,
        (unsigned int)v14);
    }
    if ( v14 == 10 )
    {
      v38 = -2147418113;
      HIWORD(v39) = 930;
      v68 = -2147418113;
      throw (long *)&v68;
    }
    v38 = 0;
    LOWORD(v39) = 930;
    std::wstring::~wstring((__int64)v79);
    std::wstring::~wstring((__int64)v81);
    std::wstring::~wstring((__int64)v78);
    std::unique_ptr<void *,WinHttpDeleter>::~unique_ptr<void *,WinHttpDeleter>(&hInternet);
    CEcsPreallocArray<unsigned short,256>::Clear(v82);
  }
  catch ( long v75 )
  {
    v38 = v75;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v39) = 932;
    v38 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v39) = 932;
    v38 = -2147418113;
  }
  catch ( const ATL::CAtlException *v76 )
  {
    HIWORD(v39) = 932;
    v38 = *(_DWORD *)v76;
  }
  v36 = v38;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v38);
  return v36;
}

```

## disassembly

```asm
0x1800c9c08  push    rbx
0x1800c9c0a  push    rsi
0x1800c9c0b  push    rdi
0x1800c9c0c  push    r12
0x1800c9c0e  push    r13
0x1800c9c10  push    r15
0x1800c9c12  sub     rsp, 3F8h
0x1800c9c19  mov     rax, cs:__security_cookie
0x1800c9c20  xor     rax, rsp
0x1800c9c23  mov     [rsp+428h+var_48], rax
0x1800c9c2b  mov     r12, r9
0x1800c9c2e  mov     r13d, r8d
0x1800c9c31  mov     rdi, rdx
0x1800c9c34  mov     rbx, rcx
0x1800c9c37  lea     rcx, WPP_GLOBAL_Control
0x1800c9c3e  mov     rax, cs:WPP_GLOBAL_Control
0x1800c9c45  cmp     rax, rcx
0x1800c9c48  jz      short loc_1800C9C72
0x1800c9c4a  test    byte ptr [rax+44h], 2
0x1800c9c4e  jz      short loc_1800C9C84
0x1800c9c50  cmp     byte ptr [rax+41h], 6
0x1800c9c54  jb      short loc_1800C9C72
0x1800c9c56  mov     edx, 17h
0x1800c9c5b  lea     r8, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids
0x1800c9c62  mov     rcx, [rax+38h]
0x1800c9c66  call    WPP_SF_
0x1800c9c6b  mov     rax, cs:WPP_GLOBAL_Control
0x1800c9c72  test    byte ptr [rax+44h], 2
0x1800c9c76  jz      short loc_1800C9C84
0x1800c9c78  cmp     byte ptr [rax+41h], 6
0x1800c9c7c  jb      short loc_1800C9C84
0x1800c9c7e  mov     al, 1
0x1800c9c80  xor     esi, esi
0x1800c9c82  jmp     short loc_1800C9C89
0x1800c9c84  xor     esi, esi
0x1800c9c86  mov     al, sil
0x1800c9c89  mov     [rsp+428h+var_3E8], esi
0x1800c9c8d  mov     [rsp+428h+var_3E4], 2AFh
0x1800c9c95  mov     [rsp+428h+var_3E0], al
0x1800c9c99  lea     rax, aCecsadfsGetaut; "CEcsAdfs::GetAuthorizationCode"
0x1800c9ca0  mov     [rsp+428h+var_3D8], rax
0x1800c9ca5  mov     [rsp+428h+var_3D0], rsi
0x1800c9caa  xor     edx, edx
0x1800c9cac  mov     rcx, r12
0x1800c9caf  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800c9cb4  nop
0x1800c9cb5  mov     [rsp+428h+var_3B0], esi
0x1800c9cb9  mov     [rsp+428h+Buffer], esi
0x1800c9cbd  mov     [rsp+428h+dwBufferLength], esi
0x1800c9cc1  mov     [rsp+428h+var_258], 100h
0x1800c9ccd  mov     [rsp+428h+var_250], rsi
0x1800c9cd5  mov     r8d, 200h; Size
0x1800c9cdb  lea     rcx, [rsp+428h+var_248]; void *
0x1800c9ce3  call    memset_0
0x1800c9ce8  nop
0x1800c9ce9  lea     rcx, [rsp+428h+hInternet]
0x1800c9cf1  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c9cf6  nop
0x1800c9cf7  lea     rcx, [rsp+428h+var_2B8]
0x1800c9cff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c9d04  nop
0x1800c9d05  lea     rcx, [rsp+428h+var_278]
0x1800c9d0d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c9d12  nop
0x1800c9d13  lea     rcx, [rsp+428h+var_298]
0x1800c9d1b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c9d20  nop
0x1800c9d21  lea     r8, [rsp+428h+var_2B8]
0x1800c9d29  mov     rdx, rdi
0x1800c9d2c  mov     rcx, rbx
0x1800c9d2f  call    ?GetFullAuthorizationUri@CEcsAdfs@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CEcsAdfs::GetFullAuthorizationUri(ushort const *,ushort const *,std::wstring &)
0x1800c9d34  mov     [rsp+428h+var_3E8], eax
0x1800c9d38  mov     [rsp+428h+var_3E8], eax
0x1800c9d3c  mov     ecx, 2C5h
0x1800c9d41  test    eax, eax
0x1800c9d43  jns     short loc_1800C9D65
0x1800c9d45  mov     word ptr [rsp+428h+var_3E4+2], cx
0x1800c9d4a  mov     [rsp+428h+pExceptionObject], eax
0x1800c9d51  lea     rdx, _TI1J; pThrowInfo
0x1800c9d58  lea     rcx, [rsp+428h+pExceptionObject]; pExceptionObject
0x1800c9d60  call    _CxxThrowException_0
0x1800c9d65  mov     word ptr [rsp+428h+var_3E4], cx
0x1800c9d6a  mov     [rsp+428h+dwFlags], esi; dwFlags
0x1800c9d6e  xor     r9d, r9d; pszProxyBypassW
0x1800c9d71  xor     r8d, r8d; pszProxyW
0x1800c9d74  lea     edx, [r9+4]; dwAccessType
0x1800c9d78  lea     rcx, aMsWorkfoldersc_0; "MS_WorkFoldersClient"
0x1800c9d7f  call    cs:__imp_WinHttpOpen
0x1800c9d85  mov     rdx, rax
0x1800c9d88  lea     rcx, [rsp+428h+hInternet]
0x1800c9d90  call    ?reset@?$unique_ptr@PEAXUWinHttpDeleter@@@std@@QEAAXPEAX@Z; std::unique_ptr<void *,WinHttpDeleter>::reset(void *)
0x1800c9d95  mov     eax, [rsp+428h+var_3E8]
0x1800c9d99  mov     [rsp+428h+var_3E8], eax
0x1800c9d9d  mov     rdi, [rsp+428h+hInternet]
0x1800c9da5  test    rdi, rdi
0x1800c9da8  jz      loc_1800CA9D6
0x1800c9dae  mov     [rsp+428h+var_3E8], esi
0x1800c9db2  mov     ecx, 2CDh
0x1800c9db7  mov     word ptr [rsp+428h+var_3E4], cx
0x1800c9dbc  mov     [rsp+428h+var_3E8], esi
0x1800c9dc0  mov     edx, 1770h; nResolveTimeout
0x1800c9dc5  mov     [rsp+428h+dwFlags], edx; nReceiveTimeout
0x1800c9dc9  mov     r9d, edx; nSendTimeout
0x1800c9dcc  mov     r8d, edx; nConnectTimeout
0x1800c9dcf  mov     rcx, rdi; hInternet
0x1800c9dd2  call    cs:__imp_WinHttpSetTimeouts
0x1800c9dd8  test    eax, eax
0x1800c9dda  jnz     short loc_1800C9E0A
0x1800c9ddc  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c9de1  mov     [rsp+428h+var_3E8], eax
0x1800c9de5  mov     ecx, 2D1h
0x1800c9dea  mov     word ptr [rsp+428h+var_3E4+2], cx
0x1800c9def  mov     [rsp+428h+var_348], eax
0x1800c9df6  lea     rdx, _TI1J; pThrowInfo
0x1800c9dfd  lea     rcx, [rsp+428h+var_348]; pExceptionObject
0x1800c9e05  call    _CxxThrowException_0
0x1800c9e0a  mov     [rsp+428h+var_3E8], esi
0x1800c9e0e  mov     ecx, 2D1h
0x1800c9e13  mov     word ptr [rsp+428h+var_3E4], cx
0x1800c9e18  mov     [rsp+428h+var_3E8], esi
0x1800c9e1c  mov     r9d, 4; dwBufferLength
0x1800c9e22  lea     r8, dword_18015ECDC; lpBuffer
0x1800c9e29  lea     edx, [r9+54h]; dwOption
0x1800c9e2d  mov     rcx, rdi; hInternet
0x1800c9e30  call    cs:__imp_WinHttpSetOption
0x1800c9e36  test    eax, eax
0x1800c9e38  jnz     short loc_1800C9E68
0x1800c9e3a  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c9e3f  mov     [rsp+428h+var_3E8], eax
0x1800c9e43  mov     ecx, 2D7h
0x1800c9e48  mov     word ptr [rsp+428h+var_3E4+2], cx
0x1800c9e4d  mov     [rsp+428h+var_344], eax
0x1800c9e54  lea     rdx, _TI1J; pThrowInfo
0x1800c9e5b  lea     rcx, [rsp+428h+var_344]; pExceptionObject
0x1800c9e63  call    _CxxThrowException_0
0x1800c9e68  mov     [rsp+428h+var_3E8], esi
0x1800c9e6c  mov     ecx, 2D7h
0x1800c9e71  mov     word ptr [rsp+428h+var_3E4], cx
0x1800c9e76  mov     r15d, esi
0x1800c9e79  mov     [rsp+428h+var_3B0], esi
0x1800c9e7d  mov     ebx, 2E8h
0x1800c9e82  cmp     r15d, 0Ah
0x1800c9e86  jge     loc_1800CA880
0x1800c9e8c  xor     edx, edx; Val
0x1800c9e8e  lea     r8d, [rdx+68h]; Size
0x1800c9e92  lea     rcx, [rsp+428h+UrlComponents]; void *
0x1800c9e9a  call    memset_0
0x1800c9e9f  lea     rcx, [rsp+428h+hConnect]
0x1800c9ea4  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c9ea9  nop
0x1800c9eaa  lea     rcx, [rsp+428h+hRequest]
0x1800c9eaf  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c9eb4  nop
0x1800c9eb5  mov     r10, cs:WPP_GLOBAL_Control
0x1800c9ebc  lea     rax, WPP_GLOBAL_Control
0x1800c9ec3  cmp     r10, rax
0x1800c9ec6  jz      short loc_1800C9EFB
0x1800c9ec8  test    byte ptr [r10+44h], 2
0x1800c9ecd  jz      short loc_1800C9EFB
0x1800c9ecf  cmp     byte ptr [r10+41h], 4
0x1800c9ed4  jb      short loc_1800C9EFB
0x1800c9ed6  lea     rcx, [rsp+428h+var_2B8]
0x1800c9ede  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c9ee3  mov     r9, rax
0x1800c9ee6  mov     edx, 18h
0x1800c9eeb  lea     r8, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids
0x1800c9ef2  mov     rcx, [r10+38h]
0x1800c9ef6  call    WPP_SF_S
0x1800c9efb  mov     [rsp+428h+UrlComponents.dwStructSize], 68h ; 'h'
0x1800c9f06  mov     [rsp+428h+UrlComponents.dwHostNameLength], 1
0x1800c9f11  mov     [rsp+428h+UrlComponents.dwUrlPathLength], 1
0x1800c9f1c  mov     eax, [rsp+428h+var_3E8]
0x1800c9f20  mov     [rsp+428h+var_3E8], eax
0x1800c9f24  lea     rcx, [rsp+428h+var_2B8]
0x1800c9f2c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c9f31  mov     rcx, rax; pwszUrl
0x1800c9f34  lea     r9, [rsp+428h+UrlComponents]; lpUrlComponents
0x1800c9f3c  xor     edx, edx; dwUrlLength
0x1800c9f3e  mov     r8d, 4000h; dwFlags
0x1800c9f44  call    cs:__imp_WinHttpCrackUrl
0x1800c9f4a  test    eax, eax
0x1800c9f4c  jnz     short loc_1800C9F77
0x1800c9f4e  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c9f53  mov     [rsp+428h+var_3E8], eax
0x1800c9f57  mov     word ptr [rsp+428h+var_3E4+2], bx
0x1800c9f5c  mov     [rsp+428h+var_338], eax
0x1800c9f63  lea     rdx, _TI1J; pThrowInfo
0x1800c9f6a  lea     rcx, [rsp+428h+var_338]; pExceptionObject
0x1800c9f72  call    _CxxThrowException_0
0x1800c9f77  mov     [rsp+428h+var_3E8], esi
0x1800c9f7b  mov     word ptr [rsp+428h+var_3E4], bx
0x1800c9f80  mov     [rsp+428h+var_3E8], esi
0x1800c9f84  cmp     [rsp+428h+UrlComponents.nScheme], 2
0x1800c9f8c  jnz     loc_1800CA97E
0x1800c9f92  mov     rdx, [rsp+428h+UrlComponents.lpszHostName]
0x1800c9f9a  test    rdx, rdx
0x1800c9f9d  jz      loc_1800CA97E
0x1800c9fa3  cmp     [rsp+428h+UrlComponents.dwHostNameLength], esi
0x1800c9faa  jz      loc_1800CA97E
0x1800c9fb0  cmp     [rsp+428h+UrlComponents.lpszUrlPath], rsi
0x1800c9fb8  jz      loc_1800CA97E
0x1800c9fbe  cmp     [rsp+428h+UrlComponents.dwUrlPathLength], esi
0x1800c9fc5  jz      loc_1800CA97E
0x1800c9fcb  mov     [rsp+428h+var_3E8], esi
0x1800c9fcf  mov     eax, 2EDh
0x1800c9fd4  mov     word ptr [rsp+428h+var_3E4], ax
0x1800c9fd9  mov     r8d, [rsp+428h+UrlComponents.dwHostNameLength]
0x1800c9fe1  lea     rcx, [rsp+428h+var_278]
0x1800c9fe9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x1800c9fee  mov     r8d, 1BBh
0x1800c9ff4  lea     rcx, [rsp+428h+var_278]
0x1800c9ffc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ca001  mov     rdx, rax; pswzServerName
0x1800ca004  xor     r9d, r9d; dwReserved
0x1800ca007  mov     rcx, rdi; hSession
0x1800ca00a  call    cs:__imp_WinHttpConnect
0x1800ca010  mov     rdx, rax
0x1800ca013  lea     rcx, [rsp+428h+hConnect]
0x1800ca018  call    ?reset@?$unique_ptr@PEAXUWinHttpDeleter@@@std@@QEAAXPEAX@Z; std::unique_ptr<void *,WinHttpDeleter>::reset(void *)
0x1800ca01d  mov     eax, [rsp+428h+var_3E8]
0x1800ca021  mov     [rsp+428h+var_3E8], eax
0x1800ca025  cmp     [rsp+428h+hConnect], rsi
0x1800ca02a  jz      loc_1800CA950
0x1800ca030  mov     [rsp+428h+var_3E8], esi
0x1800ca034  mov     eax, 2F6h
0x1800ca039  mov     word ptr [rsp+428h+var_3E4], ax
0x1800ca03e  mov     [rsp+428h+var_3F8], 800100h; dwFlags
0x1800ca046  mov     [rsp+428h+ppwszAcceptTypes], rsi; ppwszAcceptTypes
0x1800ca04b  mov     qword ptr [rsp+428h+dwFlags], rsi; pwszReferrer
0x1800ca050  xor     r9d, r9d; pwszVersion
0x1800ca053  mov     r8, [rsp+428h+UrlComponents.lpszUrlPath]; pwszObjectName
0x1800ca05b  lea     rdx, pwszVerb; "GET"
0x1800ca062  mov     rcx, [rsp+428h+hConnect]; hConnect
0x1800ca067  call    cs:__imp_WinHttpOpenRequest
0x1800ca06d  mov     rdx, rax
0x1800ca070  lea     rcx, [rsp+428h+hRequest]
0x1800ca075  call    ?reset@?$unique_ptr@PEAXUWinHttpDeleter@@@std@@QEAAXPEAX@Z; std::unique_ptr<void *,WinHttpDeleter>::reset(void *)
0x1800ca07a  mov     eax, [rsp+428h+var_3E8]
0x1800ca07e  mov     [rsp+428h+var_3E8], eax
0x1800ca082  mov     rbx, [rsp+428h+hRequest]
0x1800ca087  test    rbx, rbx
0x1800ca08a  jz      loc_1800CA922
0x1800ca090  mov     [rsp+428h+var_3E8], esi
0x1800ca094  mov     eax, 300h
0x1800ca099  mov     word ptr [rsp+428h+var_3E4], ax
0x1800ca09e  mov     [rsp+428h+var_3E8], esi
0x1800ca0a2  mov     r9d, 4; dwBufferLength
0x1800ca0a8  lea     r8, byte_18015ECD8; lpBuffer
0x1800ca0af  lea     edx, [r9+49h]; dwOption
0x1800ca0b3  mov     rcx, rbx; hInternet
0x1800ca0b6  call    cs:__imp_WinHttpSetOption
0x1800ca0bc  test    eax, eax
0x1800ca0be  jnz     short loc_1800CA0EE
0x1800ca0c0  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800ca0c5  mov     [rsp+428h+var_3E8], eax
0x1800ca0c9  mov     ecx, 305h
0x1800ca0ce  mov     word ptr [rsp+428h+var_3E4+2], cx
0x1800ca0d3  mov     [rsp+428h+var_3A0], eax
0x1800ca0da  lea     rdx, _TI1J; pThrowInfo
0x1800ca0e1  lea     rcx, [rsp+428h+var_3A0]; pExceptionObject
0x1800ca0e9  call    _CxxThrowException_0
0x1800ca0ee  mov     [rsp+428h+var_3E8], esi
0x1800ca0f2  mov     eax, 305h
0x1800ca0f7  mov     word ptr [rsp+428h+var_3E4], ax
0x1800ca0fc  mov     [rsp+428h+var_3E8], esi
0x1800ca100  mov     [rsp+428h+ppwszAcceptTypes], rsi; pAuthParams
0x1800ca105  mov     qword ptr [rsp+428h+dwFlags], rsi; pwszPassword
0x1800ca10a  xor     r9d, r9d; pwszUserName
0x1800ca10d  lea     r8d, [r9+10h]; AuthScheme
0x1800ca111  mov     edx, r13d; AuthTargets
0x1800ca114  mov     rcx, rbx; hRequest
0x1800ca117  call    cs:__imp_WinHttpSetCredentials
0x1800ca11d  test    eax, eax
0x1800ca11f  jnz     short loc_1800CA14F
0x1800ca121  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800ca126  mov     [rsp+428h+var_3E8], eax
0x1800ca12a  mov     ecx, 30Eh
0x1800ca12f  mov     word ptr [rsp+428h+var_3E4+2], cx
0x1800ca134  mov     [rsp+428h+var_39C], eax
0x1800ca13b  lea     rdx, _TI1J; pThrowInfo
0x1800ca142  lea     rcx, [rsp+428h+var_39C]; pExceptionObject
0x1800ca14a  call    _CxxThrowException_0
0x1800ca14f  mov     [rsp+428h+var_3E8], esi
0x1800ca153  mov     eax, 30Eh
0x1800ca158  mov     word ptr [rsp+428h+var_3E4], ax
0x1800ca15d  mov     [rsp+428h+var_3E8], esi
0x1800ca161  mov     qword ptr [rsp+428h+var_3F8], rsi; dwContext
0x1800ca166  mov     dword ptr [rsp+428h+ppwszAcceptTypes], esi; dwTotalLength
0x1800ca16a  mov     [rsp+428h+dwFlags], esi; dwOptionalLength
0x1800ca16e  xor     r9d, r9d; lpOptional
0x1800ca171  xor     r8d, r8d; dwHeadersLength
0x1800ca174  xor     edx, edx; lpszHeaders
0x1800ca176  mov     rcx, rbx; hRequest
0x1800ca179  call    cs:__imp_WinHttpSendRequest
0x1800ca17f  test    eax, eax
0x1800ca181  jnz     short loc_1800CA1B1
0x1800ca183  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800ca188  mov     [rsp+428h+var_3E8], eax
0x1800ca18c  mov     ecx, 316h
0x1800ca191  mov     word ptr [rsp+428h+var_3E4+2], cx
  ... truncated ...
```
