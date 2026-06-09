# WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AuthenticationEndpoint,WinStoreAuth::PromptType,Windows::System::IUser *,Windows::Security::Authentication::Web::Core::IWebTokenRequest * *)

- ea: `0x18002d928`
- end: `0x18002e074`
- name: `?CreateTokenRequestHelper@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@W4AuthenticationEndpoint@2@W4PromptType@2@PEAUIUser@System@Windows@@PEAPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@Z`
- size: `1868`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002ce2c`
- `0x1800a6840`

## callees

- `0x180004738`
- `0x18002cce0`
- `0x18002d928`
- `0x18002ecc8`
- `0x180030294`
- `0x1800374f0`
- `0x18003dab0`
- `0x18003ddac`
- `0x180044dcc`
- `0x180061c04`
- `0x180068f9c`
- `0x180075e60`
- `0x1800aba80`
- `0x1800abad4`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002da98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002daa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002da98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002daa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002deee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dfc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dd82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ddf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002de42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dedf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002deee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002df96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dfc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dfd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e01f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e02f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e041`

## string_xrefs

- `0x18002daee`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18002dab6`: `service::%s::%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall WinStoreAuth::AuthenticationInternal::CreateTokenRequestHelper(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  int SlsValue; // eax
  __int64 v11; // rdx
  unsigned int StringRawBuffer; // ebx
  PCWSTR v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, _QWORD, _QWORD, HSTRING); // rdi
  HSTRING v18; // rbx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, __int64, _BYTE *); // rdi
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rsi
  __int64 (__fastcall *v36)(__int64, __int64, HSTRING, _BYTE *); // rdi
  HSTRING v37; // rbx
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, __int64, HSTRING, _BYTE *); // rdi
  HSTRING v42; // rbx
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  int v48; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v50; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v51[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v53; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v55[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v57; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v58; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER v59; // [rsp+90h] [rbp-70h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-58h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-38h]
  WCHAR sourceString[2088]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1158h] [rbp+1058h]

  *a5 = 0;
  v58 = 0;
  LODWORD(v53) = 0;
  v6 = WinStoreAuth::AuthenticationInternal::ExtractProviderType(a1, &v53);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1913;
LABEL_10:
    v9 = (unsigned int)v6;
    goto LABEL_11;
  }
  if ( (_DWORD)v53 == 1 )
  {
    v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v58);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1918;
      goto LABEL_10;
    }
    goto LABEL_12;
  }
  if ( (_DWORD)v53 == 2 )
  {
    v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v58);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 1921;
      goto LABEL_10;
    }
LABEL_12:
    string = 0;
    WindowsDeleteString(0);
    v50 = 0;
    SlsValue = WinStoreAuth::GetSlsValue(0, &v50);
    v7 = SlsValue;
    if ( SlsValue < 0 )
    {
      v11 = 1933;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)SlsValue,
        v48);
LABEL_15:
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v50);
LABEL_67:
      v50 = 0;
      goto LABEL_68;
    }
    WindowsDeleteString(string);
    string = 0;
    SlsValue = WinStoreAuth::GetSlsValue(1, &string);
    v7 = SlsValue;
    if ( SlsValue < 0 )
    {
      v11 = 1934;
      goto LABEL_14;
    }
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
    v13 = WindowsGetStringRawBuffer(v50, 0);
    v48 = StringRawBuffer;
    SlsValue = StringCchPrintfW(sourceString, 0x824u, L"service::%s::%s", v13);
    v7 = SlsValue;
    if ( SlsValue < 0 )
    {
      v11 = 1948;
      goto LABEL_14;
    }
    v56 = 0;
    v62 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
      0x39u,
      0x38u);
    v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
            v62,
            &v56);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 1959;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v14,
        v48);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      goto LABEL_15;
    }
    v14 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v56);
    v7 = v14;
    if ( v14 < 0 )
    {
      v15 = 1960;
      goto LABEL_22;
    }
    v54 = 0;
    v16 = v56;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, HSTRING))(*(_QWORD *)v56 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
    v18 = v58;
    v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v59, sourceString);
    v20 = v17(v16, *a1, *(_QWORD *)(v19 + 24), v18);
    v7 = v20;
    if ( v20 >= 0 )
    {
      v20 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v54);
      v7 = v20;
      if ( v20 >= 0 )
      {
        v52 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 80LL))(v54, &v52);
        v7 = v22;
        if ( v22 >= 0 )
        {
          v24 = WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(v52);
          v7 = v24;
          if ( v24 >= 0 )
          {
            if ( (_DWORD)v53 == 1 )
            {
              v55[0] = 0;
              if ( !wcscmp_0(WinStoreAuth::g_msaClientId, L"{f0c62012-2cef-4831-b1f7-930682874c86}") )
              {
                v26 = v52;
                v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64, _BYTE *))(*(_QWORD *)v52 + 80LL);
                v62 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"none", 5u, 4u);
                v28 = v62;
                v60 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v59, L"ssoappgroup", 0xCu, 0xBu);
                v29 = v27(v26, v60, v28, v55);
                v7 = v29;
                if ( v29 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x7C2,
                    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                    (const char *)(unsigned int)v29,
                    0);
                  v30 = v52;
                  if ( v52 )
                  {
                    v52 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                  }
                  goto LABEL_29;
                }
              }
            }
            else if ( (_DWORD)v53 == 2 )
            {
              v53 = 0;
              WindowsDeleteString(0);
              v53 = 0;
              v31 = WinStoreAuth::GetSlsValue(2, &v53);
              v7 = v31;
              if ( v31 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7D2,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v31,
                  0);
                WindowsDeleteString(v53);
                v53 = 0;
                v32 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
                goto LABEL_29;
              }
              v57 = 0;
              WindowsDeleteString(0);
              v57 = 0;
              v33 = WinStoreAuth::GetSlsValue(3, &v57);
              v7 = v33;
              if ( v33 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7D5,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v33,
                  0);
                WindowsDeleteString(v57);
                v57 = 0;
                WindowsDeleteString(v53);
                v53 = 0;
                v34 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
                goto LABEL_29;
              }
              v51[0] = 0;
              v35 = v52;
              v36 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, _BYTE *))(*(_QWORD *)v52 + 80LL);
              v37 = v57;
              v60 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v59, L"resource", 9u, 8u);
              v38 = v36(v35, v60, v37, v51);
              v7 = v38;
              if ( v38 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7DB,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v38,
                  0);
                WindowsDeleteString(v57);
                v57 = 0;
                WindowsDeleteString(v53);
                v53 = 0;
                v39 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                }
                goto LABEL_29;
              }
              v40 = v52;
              v41 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, _BYTE *))(*(_QWORD *)v52 + 80LL);
              v42 = v53;
              v60 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v59, L"authority", 0xAu, 9u);
              v43 = v41(v40, v60, v42, v51);
              v7 = v43;
              if ( v43 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7E0,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
                  (const char *)(unsigned int)v43,
                  0);
                WindowsDeleteString(v57);
                v57 = 0;
                WindowsDeleteString(v53);
                v53 = 0;
                v44 = v52;
                if ( v52 )
                {
                  v52 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
                }
                goto LABEL_29;
              }
              WindowsDeleteString(v57);
              v57 = 0;
              WindowsDeleteString(v53);
            }
            v45 = v54;
            v54 = 0;
            *a5 = v45;
            v46 = v52;
            if ( v52 )
            {
              v52 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
            }
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
            WindowsDeleteString(string);
            string = 0;
            WindowsDeleteString(v50);
            v7 = 0;
            goto LABEL_67;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B5,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v24,
            0);
          v25 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B4,
            (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
            (const char *)(unsigned int)v22,
            0);
          v23 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
        }
LABEL_29:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v54);
        goto LABEL_23;
      }
      v21 = 1969;
    }
    else
    {
      v21 = 1968;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v20,
      0);
    goto LABEL_29;
  }
  v7 = -2147024809;
  v9 = 2147942487LL;
  v8 = 1924;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
    (const char *)v9,
    v48);
LABEL_68:
  WindowsDeleteString(v58);
  return v7;
}

```

## disassembly

```asm
0x18002d928  mov     [rsp-8+arg_8], rbx
0x18002d92d  mov     [rsp-8+arg_10], rsi
0x18002d932  push    rbp
0x18002d933  push    rdi
0x18002d934  push    r12
0x18002d936  push    r13
0x18002d938  push    r15
0x18002d93a  lea     rbp, [rsp-1030h]
0x18002d942  mov     eax, 1130h
0x18002d947  call    _alloca_probe
0x18002d94c  sub     rsp, rax
0x18002d94f  mov     rax, cs:__security_cookie
0x18002d956  xor     rax, rsp
0x18002d959  mov     [rbp+1050h+var_30], rax
0x18002d960  mov     r12, rcx
0x18002d963  mov     r15, [rbp+1050h+arg_20]
0x18002d96a  xor     r13d, r13d
0x18002d96d  mov     [r15], r13
0x18002d970  mov     [rbp+1050h+var_10C8], r13
0x18002d974  mov     dword ptr [rsp+1150h+var_10F0], r13d
0x18002d979  lea     rdx, [rsp+1150h+var_10F0]
0x18002d97e  call    ?ExtractProviderType@AuthenticationInternal@WinStoreAuth@@YAJAEBV?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@AEAW4AccountProviderType@2@@Z; WinStoreAuth::AuthenticationInternal::ExtractProviderType(Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider> const &,WinStoreAuth::AccountProviderType &)
0x18002d983  mov     ebx, eax
0x18002d985  test    eax, eax
0x18002d987  jns     short loc_18002D990
0x18002d989  mov     edx, 779h
0x18002d98e  jmp     short loc_18002D9E5
0x18002d990  mov     ecx, dword ptr [rsp+1150h+var_10F0]
0x18002d994  sub     ecx, 1
0x18002d997  jz      short loc_18002D9CA
0x18002d999  cmp     ecx, 1
0x18002d99c  jz      short loc_18002D9AD
0x18002d99e  mov     ebx, 80070057h
0x18002d9a3  mov     r9d, ebx
0x18002d9a6  mov     edx, 784h
0x18002d9ab  jmp     short loc_18002D9E8
0x18002d9ad  lea     rdx, ?g_pszAadClientId@WinStoreAuth@@3PEBGEB; ushort const * const WinStoreAuth::g_pszAadClientId
0x18002d9b4  lea     rcx, [rbp+1050h+var_10C8]; string
0x18002d9b8  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002d9bd  mov     ebx, eax
0x18002d9bf  test    eax, eax
0x18002d9c1  jns     short loc_18002DA00
0x18002d9c3  mov     edx, 781h
0x18002d9c8  jmp     short loc_18002D9E5
0x18002d9ca  lea     rdx, ?g_msaClientId@WinStoreAuth@@3PEBGEB; ushort const * const WinStoreAuth::g_msaClientId
0x18002d9d1  lea     rcx, [rbp+1050h+var_10C8]; string
0x18002d9d5  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002d9da  mov     ebx, eax
0x18002d9dc  test    eax, eax
0x18002d9de  jns     short loc_18002DA00
0x18002d9e0  mov     edx, 77Eh; void *
0x18002d9e5  mov     r9d, eax; char *
0x18002d9e8  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002d9ef  mov     rcx, [rbp+1058h]; this
0x18002d9f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d9fb  jmp     loc_18002E03D
0x18002da00  mov     [rsp+1150h+var_1108], r13
0x18002da05  mov     [rsp+1150h+string], r13
0x18002da0a  xor     ecx, ecx; string
0x18002da0c  call    cs:__imp_WindowsDeleteString
0x18002da12  mov     [rsp+1150h+var_1108], r13
0x18002da17  lea     rdx, [rsp+1150h+var_1108]
0x18002da1c  xor     ecx, ecx
0x18002da1e  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18002da23  mov     ebx, eax
0x18002da25  test    eax, eax
0x18002da27  jns     short loc_18002DA65
0x18002da29  mov     edx, 78Dh; void *
0x18002da2e  mov     rcx, [rbp+1058h]; this
0x18002da35  mov     r9d, eax; char *
0x18002da38  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002da3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da44  nop
0x18002da45  mov     rcx, [rsp+1150h+string]; string
0x18002da4a  call    cs:__imp_WindowsDeleteString
0x18002da50  mov     [rsp+1150h+string], r13
0x18002da55  mov     rcx, [rsp+1150h+var_1108]; string
0x18002da5a  call    cs:__imp_WindowsDeleteString
0x18002da60  jmp     loc_18002E038
0x18002da65  mov     rcx, [rsp+1150h+string]; string
0x18002da6a  call    cs:__imp_WindowsDeleteString
0x18002da70  mov     [rsp+1150h+string], r13
0x18002da75  lea     rdx, [rsp+1150h+string]
0x18002da7a  mov     ecx, 1
0x18002da7f  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18002da84  mov     ebx, eax
0x18002da86  test    eax, eax
0x18002da88  jns     short loc_18002DA91
0x18002da8a  mov     edx, 78Eh
0x18002da8f  jmp     short loc_18002DA2E
0x18002da91  xor     edx, edx; length
0x18002da93  mov     rcx, [rsp+1150h+string]; string
0x18002da98  call    cs:__imp_WindowsGetStringRawBuffer
0x18002da9e  mov     rbx, rax
0x18002daa1  xor     edx, edx; length
0x18002daa3  mov     rcx, [rsp+1150h+var_1108]; string
0x18002daa8  call    cs:__imp_WindowsGetStringRawBuffer
0x18002daae  mov     qword ptr [rsp+1150h+var_1130], rbx; int
0x18002dab3  mov     r9, rax
0x18002dab6  lea     r8, aServiceSS; "service::%s::%s"
0x18002dabd  mov     edx, 824h; unsigned __int64
0x18002dac2  lea     rcx, [rbp+1050h+sourceString]; unsigned __int16 *
0x18002dac6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dacb  mov     ebx, eax
0x18002dacd  test    eax, eax
0x18002dacf  jns     short loc_18002DADB
0x18002dad1  mov     edx, 79Ch
0x18002dad6  jmp     loc_18002DA2E
0x18002dadb  mov     [rsp+1150h+var_10D8], r13
0x18002dae0  mov     [rbp+1050h+var_1088], r13
0x18002dae4  mov     r9d, 38h ; '8'; unsigned int
0x18002daea  lea     r8d, [r9+1]; unsigned int
0x18002daee  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18002daf5  lea     rcx, [rbp+1050h+hstringHeader]; hstringHeader
0x18002daf9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dafe  lea     rdx, [rsp+1150h+var_10D8]
0x18002db03  mov     rcx, [rbp+1050h+var_1088]
0x18002db07  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x18002db0c  mov     ebx, eax
0x18002db0e  test    eax, eax
0x18002db10  jns     short loc_18002DB3D
0x18002db12  mov     edx, 7A7h; void *
0x18002db17  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002db1e  mov     r9d, eax; char *
0x18002db21  mov     rcx, [rbp+1058h]; this
0x18002db28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db2d  nop
0x18002db2e  lea     rcx, [rsp+1150h+var_10D8]
0x18002db33  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002db38  jmp     loc_18002DA45
0x18002db3d  mov     rcx, [rsp+1150h+var_10D8]
0x18002db42  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18002db47  mov     ebx, eax
0x18002db49  test    eax, eax
0x18002db4b  jns     short loc_18002DB54
0x18002db4d  mov     edx, 7A8h
0x18002db52  jmp     short loc_18002DB17
0x18002db54  mov     [rsp+1150h+var_10E8], r13
0x18002db59  mov     rsi, [rsp+1150h+var_10D8]
0x18002db5e  mov     rax, [rsi]
0x18002db61  mov     rdi, [rax+38h]
0x18002db65  lea     rcx, [rsp+1150h+var_10E8]
0x18002db6a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002db6f  mov     rbx, [rbp+1050h+var_10C8]
0x18002db73  lea     rdx, [rbp+1050h+sourceString]; sourceString
0x18002db77  lea     rcx, [rbp+1050h+var_10C0]; hstringHeader
0x18002db7b  call    ??$?0$0ICE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0ICE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[2084])
0x18002db80  nop
0x18002db81  lea     rcx, [rsp+1150h+var_10E8]
0x18002db86  mov     [rsp+1150h+var_1128], rcx
0x18002db8b  mov     [rsp+1150h+var_1130], r13d; int
0x18002db90  mov     r9, rbx
0x18002db93  mov     r8, [rax+18h]
0x18002db97  mov     rdx, [r12]
0x18002db9b  mov     rcx, rsi
0x18002db9e  mov     rax, rdi
0x18002dba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dba6  mov     ebx, eax
0x18002dba8  test    eax, eax
0x18002dbaa  jns     short loc_18002DBD7
0x18002dbac  mov     edx, 7B0h; void *
0x18002dbb1  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002dbb8  mov     r9d, eax; char *
0x18002dbbb  mov     rcx, [rbp+1058h]; this
0x18002dbc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dbc7  nop
0x18002dbc8  lea     rcx, [rsp+1150h+var_10E8]
0x18002dbcd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002dbd2  jmp     loc_18002DB2E
0x18002dbd7  mov     rcx, [rsp+1150h+var_10E8]
0x18002dbdc  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18002dbe1  mov     ebx, eax
0x18002dbe3  test    eax, eax
0x18002dbe5  jns     short loc_18002DBEE
0x18002dbe7  mov     edx, 7B1h
0x18002dbec  jmp     short loc_18002DBB1
0x18002dbee  mov     [rsp+1150h+var_10F8], r13
0x18002dbf3  mov     rcx, [rsp+1150h+var_10E8]
0x18002dbf8  mov     rax, [rcx]
0x18002dbfb  lea     rdx, [rsp+1150h+var_10F8]
0x18002dc00  mov     rax, [rax+50h]
0x18002dc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc09  mov     ebx, eax
0x18002dc0b  test    eax, eax
0x18002dc0d  jns     short loc_18002DC4C
0x18002dc0f  mov     rcx, [rbp+1058h]; this
0x18002dc16  mov     r9d, eax; char *
0x18002dc19  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002dc20  mov     edx, 7B4h; void *
0x18002dc25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc2a  nop
0x18002dc2b  mov     rcx, [rsp+1150h+var_10F8]
0x18002dc30  test    rcx, rcx
0x18002dc33  jz      short loc_18002DC47
0x18002dc35  mov     [rsp+1150h+var_10F8], r13
0x18002dc3a  mov     rax, [rcx]
0x18002dc3d  mov     rax, [rax+10h]
0x18002dc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc46  nop
0x18002dc47  jmp     loc_18002DBC8
0x18002dc4c  mov     rcx, [rsp+1150h+var_10F8]
0x18002dc51  call    ??$SetProxyBlanket@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@WinStoreAuth@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@Z; WinStoreAuth::SetProxyBlanket<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)
0x18002dc56  mov     ebx, eax
0x18002dc58  test    eax, eax
0x18002dc5a  jns     short loc_18002DC99
0x18002dc5c  mov     rcx, [rbp+1058h]; this
0x18002dc63  mov     r9d, eax; char *
0x18002dc66  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002dc6d  mov     edx, 7B5h; void *
0x18002dc72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dc77  nop
0x18002dc78  mov     rcx, [rsp+1150h+var_10F8]
0x18002dc7d  test    rcx, rcx
0x18002dc80  jz      short loc_18002DC94
0x18002dc82  mov     [rsp+1150h+var_10F8], r13
0x18002dc87  mov     rax, [rcx]
0x18002dc8a  mov     rax, [rax+10h]
0x18002dc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc93  nop
0x18002dc94  jmp     loc_18002DBC8
0x18002dc99  cmp     dword ptr [rsp+1150h+var_10F0], 1
0x18002dc9e  jnz     loc_18002DD70
0x18002dca4  mov     [rsp+1150h+var_10E0], r13b
0x18002dca9  lea     rdx, aF0c620122cef48; "{f0c62012-2cef-4831-b1f7-930682874c86}"
0x18002dcb0  mov     rcx, cs:?g_msaClientId@WinStoreAuth@@3PEBGEB; String1
0x18002dcb7  call    wcscmp_0
0x18002dcbc  test    eax, eax
0x18002dcbe  jnz     loc_18002DFDB
0x18002dcc4  mov     rsi, [rsp+1150h+var_10F8]
0x18002dcc9  mov     rax, [rsi]
0x18002dccc  mov     rdi, [rax+50h]
0x18002dcd0  mov     [rbp+1050h+var_1088], r13
0x18002dcd4  mov     r9d, 4; unsigned int
0x18002dcda  lea     r8d, [r9+1]; unsigned int
0x18002dcde  lea     rdx, aNone; "none"
0x18002dce5  lea     rcx, [rbp+1050h+hstringHeader]; hstringHeader
0x18002dce9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dcee  nop
0x18002dcef  mov     rbx, [rbp+1050h+var_1088]
0x18002dcf3  mov     [rbp+1050h+var_10A8], r13
0x18002dcf7  mov     r9d, 0Bh; unsigned int
0x18002dcfd  lea     r8d, [r9+1]; unsigned int
0x18002dd01  lea     rdx, aSsoappgroup; "ssoappgroup"
0x18002dd08  lea     rcx, [rbp+1050h+var_10C0]; hstringHeader
0x18002dd0c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dd11  nop
0x18002dd12  lea     r9, [rsp+1150h+var_10E0]
0x18002dd17  mov     r8, rbx
0x18002dd1a  mov     rdx, [rbp+1050h+var_10A8]
0x18002dd1e  mov     rcx, rsi
0x18002dd21  mov     rax, rdi
0x18002dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd29  mov     ebx, eax
0x18002dd2b  test    eax, eax
0x18002dd2d  jns     loc_18002DFDB
0x18002dd33  mov     rcx, [rbp+1058h]; this
0x18002dd3a  mov     r9d, eax; char *
0x18002dd3d  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002dd44  mov     edx, 7C2h; void *
0x18002dd49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dd4e  nop
0x18002dd4f  mov     rcx, [rsp+1150h+var_10F8]
0x18002dd54  test    rcx, rcx
0x18002dd57  jz      short loc_18002DD6B
0x18002dd59  mov     [rsp+1150h+var_10F8], r13
0x18002dd5e  mov     rax, [rcx]
0x18002dd61  mov     rax, [rax+10h]
0x18002dd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd6a  nop
0x18002dd6b  jmp     loc_18002DBC8
0x18002dd70  cmp     dword ptr [rsp+1150h+var_10F0], 2
0x18002dd75  jnz     loc_18002DFDB
0x18002dd7b  mov     [rsp+1150h+var_10F0], r13
0x18002dd80  xor     ecx, ecx; string
0x18002dd82  call    cs:__imp_WindowsDeleteString
0x18002dd88  mov     [rsp+1150h+var_10F0], r13
0x18002dd8d  lea     rdx, [rsp+1150h+var_10F0]
0x18002dd92  mov     ecx, 2
0x18002dd97  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18002dd9c  mov     ebx, eax
0x18002dd9e  test    eax, eax
0x18002dda0  jns     short loc_18002DDEF
0x18002dda2  mov     rcx, [rbp+1058h]; this
0x18002dda9  mov     r9d, eax; char *
0x18002ddac  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18002ddb3  mov     edx, 7D2h; void *
0x18002ddb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ddbd  nop
0x18002ddbe  mov     rcx, [rsp+1150h+var_10F0]; string
0x18002ddc3  call    cs:__imp_WindowsDeleteString
0x18002ddc9  mov     [rsp+1150h+var_10F0], r13
0x18002ddce  mov     rcx, [rsp+1150h+var_10F8]
0x18002ddd3  test    rcx, rcx
0x18002ddd6  jz      short loc_18002DDEA
0x18002ddd8  mov     [rsp+1150h+var_10F8], r13
0x18002dddd  mov     rax, [rcx]
0x18002dde0  mov     rax, [rax+10h]
0x18002dde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dde9  nop
0x18002ddea  jmp     loc_18002DBC8
  ... truncated ...
```
