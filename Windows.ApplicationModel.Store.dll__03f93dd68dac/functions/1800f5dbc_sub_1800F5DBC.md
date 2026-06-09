# sub_1800F5DBC

- ea: `0x1800f5dbc`
- end: `0x1800f64aa`
- name: `sub_1800F5DBC`
- size: `1774`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180070280`

## callees

- `0x1800044c0`
- `0x180004f50`
- `0x180010e24`
- `0x18001b940`
- `0x180035374`
- `0x180038a50`
- `0x1800ad1f0`
- `0x1800ad350`
- `0x1800ad3f0`
- `0x1800ad46c`
- `0x1800ba098`
- `0x1800babd4`
- `0x1800c69b8`
- `0x1800f5dbc`
- `0x18014187c`
- `0x1801519b8`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f5e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f5e59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5dfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f6468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f647a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5dfc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f6468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f647a`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800f5e6b`
- `ext-ms-win-kernel32-package-l1-1-0!PackageFamilyNameFromFullName` at `0x1800f5e6b`

## string_xrefs

- `0x1800f5e2e`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f5fc1`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f600d`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f607a`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f6103`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f6177`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f6204`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f62af`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f636d`: `onecoreuap\enduser\winstore\licensing\winrt\lib\windows\catalogserviceproxy.cpp`
- `0x1800f5e23`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f5fb5`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f6001`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f606e`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f60f7`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f616b`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f61f8`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f62a3`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f6361`: `CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType`
- `0x1800f5ffa`: `ChkHr(IAPUtils::GetJsonFromURL(hstrUri.Get(), pCV, &jsonObject))`
- `0x1800f5fae`: `ChkHr(UriHelper::GetUriWithPathAndParameters( UriHelper::MDDisplayCatalog, CSP6Internal::GetSearchSkusByContentIdPath(), rgNameValuePairs, (sizeof(*RtlpNumberOf(rgNameValuePairs))), hstrUri.GetAddressOf()))`
- `0x1800f60f0`: `ChkHr(JsonHelpers::GetNamedInteger(displayProductSearchResult, L"TotalResultCount", (int *)&count))`
- `0x1800f61f1`: `ChkHr(JsonHelpers::GetNamedArray(displayProductSearchResult, L"Products", &products))`
- `0x1800f6067`: `ChkHr(JsonHelpers::GetNamedObject(jsonObject, L"DisplaySkuSearchResult", &displayProductSearchResult))`
- `0x1800f635a`: `ChkHr(JsonHelpers::GetNamedString(firstProduct, L"ProductId", bigCatIdOut))`

## pseudocode

```c
__int64 __fastcall sub_1800F5DBC(HSTRING string, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // edi
  const char *v8; // r9
  int v9; // edx
  HSTRING v10; // rcx
  const WCHAR *StringRawBuffer; // rax
  LONG v12; // eax
  HSTRING v13; // rbx
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  HSTRING stringa; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v50; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v51[6]; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int128 v54; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR sourceString[40]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+110h] [rbp+10h] BYREF

  WindowsDeleteString(0);
  v50 = 0;
  v7 = sub_1800BABD4(&v50);
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = "ChkHr(IAPUtils::GetMarket(market.GetAddressOf()))";
    v9 = 205;
LABEL_3:
    sub_1801519B8(
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
      v9,
      (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
      (_DWORD)v8,
      v7);
    sub_18001B940(v7);
    v10 = v50;
    goto LABEL_74;
  }
  packageFamilyNameLength[0] = 65;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = PackageFamilyNameFromFullName(StringRawBuffer, packageFamilyNameLength, packageFamilyName);
  v7 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( (v7 & 0x80000000) != 0 )
    {
      v8 = "ChkHr(HRESULT_FROM_WIN32(rc))";
      v9 = 215;
      goto LABEL_3;
    }
  }
  v54 = 0;
  v7 = sub_18014187C(packageFamilyName);
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = "ChkHr(GetContentId(szPackageFamilyName, cpt, &guidContentId))";
    v9 = 222;
    goto LABEL_3;
  }
  memset(sourceString, 0, 0x4Au);
  v7 = sub_180035374(&v54, sourceString);
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = "ChkHr(GuidToStringWithoutBraces(&guidContentId, szContentId))";
    v9 = 225;
    goto LABEL_3;
  }
  sub_180010E24(&hstringHeader, sourceString);
  v51[0] = qword_180243410;
  v51[1] = v53;
  v51[2] = qword_180243430;
  v13 = v50;
  v51[3] = v50;
  v51[4] = qword_180243450;
  v51[5] = qword_180243530;
  WindowsDeleteString(0);
  stringa = 0;
  v15 = sub_1800C69B8(v14, (_DWORD)qword_180243510, (unsigned int)v51, 3, (__int64)&stringa);
  v7 = v15;
  if ( v15 >= 0 )
  {
    v46 = 0;
    v16 = sub_1800BA098(stringa, a3, &v46);
    v7 = v16;
    if ( v16 >= 0 )
    {
      v47 = 0;
      v18 = sub_1800AD3F0(v46, L"DisplaySkuSearchResult", &v47);
      v7 = v18;
      if ( v18 >= 0 )
      {
        packageFamilyNameLength[0] = 0;
        v21 = sub_1800AD350(v47, L"TotalResultCount", packageFamilyNameLength);
        v7 = v21;
        if ( v21 >= 0 )
        {
          if ( packageFamilyNameLength[0] )
          {
            *(_QWORD *)packageFamilyNameLength = 0;
            v26 = sub_1800AD1F0(v47, L"Products", packageFamilyNameLength);
            v7 = v26;
            if ( v26 >= 0 )
            {
              v49 = 0;
              v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)packageFamilyNameLength + 48LL))(
                      *(_QWORD *)packageFamilyNameLength,
                      0,
                      &v49);
              v7 = v30;
              if ( v30 >= 0 )
              {
                v35 = sub_1800AD46C(v49, L"ProductId", a4);
                v7 = v35;
                if ( v35 >= 0 )
                {
                  v40 = v49;
                  if ( v49 )
                  {
                    v49 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                  }
                  v41 = *(_QWORD *)packageFamilyNameLength;
                  if ( *(_QWORD *)packageFamilyNameLength )
                  {
                    *(_QWORD *)packageFamilyNameLength = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  }
                  v42 = v47;
                  if ( v47 )
                  {
                    v47 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                  }
                  v43 = v46;
                  if ( v46 )
                  {
                    v46 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                  }
                }
                else
                {
                  sub_1801519B8(
                    (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
                    268,
                    (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
                    (unsigned int)"ChkHr(JsonHelpers::GetNamedString(firstProduct, L\"ProductId\", bigCatIdOut))",
                    v35);
                  sub_18001B940(v7);
                  v36 = v49;
                  if ( v49 )
                  {
                    v49 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                  }
                  v37 = *(_QWORD *)packageFamilyNameLength;
                  if ( *(_QWORD *)packageFamilyNameLength )
                  {
                    *(_QWORD *)packageFamilyNameLength = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  }
                  v38 = v47;
                  if ( v47 )
                  {
                    v47 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                  }
                  v39 = v46;
                  if ( v46 )
                  {
                    v46 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                  }
                }
              }
              else
              {
                sub_1801519B8(
                  (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
                  265,
                  (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
                  (unsigned int)"ChkHr(products->GetObjectAt(0, &firstProduct))",
                  v30);
                sub_18001B940(v7);
                v31 = v49;
                if ( v49 )
                {
                  v49 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                }
                v32 = *(_QWORD *)packageFamilyNameLength;
                if ( *(_QWORD *)packageFamilyNameLength )
                {
                  *(_QWORD *)packageFamilyNameLength = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                }
                v33 = v47;
                if ( v47 )
                {
                  v47 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                }
                v34 = v46;
                if ( v46 )
                {
                  v46 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                }
              }
            }
            else
            {
              sub_1801519B8(
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
                262,
                (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
                (unsigned int)"ChkHr(JsonHelpers::GetNamedArray(displayProductSearchResult, L\"Products\", &products))",
                v26);
              sub_18001B940(v7);
              v27 = *(_QWORD *)packageFamilyNameLength;
              if ( *(_QWORD *)packageFamilyNameLength )
              {
                *(_QWORD *)packageFamilyNameLength = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              }
              v28 = v47;
              if ( v47 )
              {
                v47 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
              }
              v29 = v46;
              if ( v46 )
              {
                v46 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              }
            }
          }
          else
          {
            v7 = -2147023728;
            sub_1801519B8(
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
              255,
              (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
              (unsigned int)"ChkHr(HRESULT_FROM_WIN32(1168L))",
              -2147023728);
            sub_18001B940(2147943568LL);
            v24 = v47;
            if ( v47 )
            {
              v47 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
            v25 = v46;
            if ( v46 )
            {
              v46 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
          }
        }
        else
        {
          sub_1801519B8(
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
            252,
            (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
            (unsigned int)"ChkHr(JsonHelpers::GetNamedInteger(displayProductSearchResult, L\"TotalResultCount\", (int *)&count))",
            v21);
          sub_18001B940(v7);
          v22 = v47;
          if ( v47 )
          {
            v47 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
          v23 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
        }
      }
      else
      {
        sub_1801519B8(
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
          248,
          (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
          (unsigned int)"ChkHr(JsonHelpers::GetNamedObject(jsonObject, L\"DisplaySkuSearchResult\", &displayProductSearchResult))",
          v18);
        sub_18001B940(v7);
        v19 = v47;
        if ( v47 )
        {
          v47 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = v46;
        if ( v46 )
        {
          v46 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
    }
    else
    {
      sub_1801519B8(
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
        244,
        (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
        (unsigned int)"ChkHr(IAPUtils::GetJsonFromURL(hstrUri.Get(), pCV, &jsonObject))",
        v16);
      sub_18001B940(v7);
      v17 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
  }
  else
  {
    sub_1801519B8(
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensing\\winrt\\lib\\windows\\catalogserviceproxy.cpp",
      241,
      (unsigned int)"CatalogServiceProxyV6::QueryCatalogForBigCatIdByPackageFullNameAndType",
      (unsigned int)"ChkHr(UriHelper::GetUriWithPathAndParameters( UriHelper::MDDisplayCatalog, CSP6Internal::GetSearchSk"
                    "usByContentIdPath(), rgNameValuePairs, (sizeof(*RtlpNumberOf(rgNameValuePairs))), hstrUri.GetAddressOf()))",
      v15);
    sub_18001B940(v7);
  }
  WindowsDeleteString(stringa);
  stringa = 0;
  v53 = 0;
  v10 = v13;
LABEL_74:
  WindowsDeleteString(v10);
  sub_180038A50(v7);
  return v7;
}

```

## disassembly

```asm
0x1800f5dbc  push    rbp
0x1800f5dbe  push    rbx
0x1800f5dbf  push    rsi
0x1800f5dc0  push    rdi
0x1800f5dc1  push    r12
0x1800f5dc3  push    r14
0x1800f5dc5  push    r15
0x1800f5dc7  lea     rbp, [rsp-0B0h]
0x1800f5dcf  sub     rsp, 1B0h
0x1800f5dd6  mov     rax, cs:__security_cookie
0x1800f5ddd  xor     rax, rsp
0x1800f5de0  mov     [rbp+0E0h+var_40], rax
0x1800f5de7  mov     r15, r9
0x1800f5dea  mov     r14, r8
0x1800f5ded  mov     ebx, edx
0x1800f5def  mov     rsi, rcx
0x1800f5df2  xor     r12d, r12d
0x1800f5df5  mov     [rsp+1E0h+var_188], r12
0x1800f5dfa  xor     ecx, ecx; string
0x1800f5dfc  call    cs:WindowsDeleteString
0x1800f5e02  mov     [rsp+1E0h+var_188], r12
0x1800f5e07  lea     rcx, [rsp+1E0h+var_188]
0x1800f5e0c  call    sub_1800BABD4
0x1800f5e11  mov     edi, eax
0x1800f5e13  test    eax, eax
0x1800f5e15  jns     short loc_1800F5E4C
0x1800f5e17  lea     r9, aChkhrIaputilsG; "ChkHr(IAPUtils::GetMarket(market.GetAdd"...
0x1800f5e1e  mov     edx, 0CDh
0x1800f5e23  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f5e2a  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x1800f5e2e  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f5e35  call    sub_1801519B8
0x1800f5e3a  mov     ecx, edi
0x1800f5e3c  call    sub_18001B940
0x1800f5e41  nop
0x1800f5e42  mov     rcx, [rsp+1E0h+var_188]
0x1800f5e47  jmp     loc_1800F647A
0x1800f5e4c  mov     [rsp+1E0h+packageFamilyNameLength], 41h ; 'A'
0x1800f5e54  xor     edx, edx; length
0x1800f5e56  mov     rcx, rsi; string
0x1800f5e59  call    cs:WindowsGetStringRawBuffer
0x1800f5e5f  mov     rcx, rax; packageFullName
0x1800f5e62  lea     r8, [rbp+0E0h+packageFamilyName]; packageFamilyName
0x1800f5e66  lea     rdx, [rsp+1E0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800f5e6b  call    cs:PackageFamilyNameFromFullName
0x1800f5e71  mov     edi, eax
0x1800f5e73  test    eax, eax
0x1800f5e75  jz      short loc_1800F5E94
0x1800f5e77  jle     short loc_1800F5E82
0x1800f5e79  movzx   edi, ax
0x1800f5e7c  or      edi, 80070000h
0x1800f5e82  test    edi, edi
0x1800f5e84  jns     short loc_1800F5E94
0x1800f5e86  lea     r9, aChkhrHresultFr_18; "ChkHr(HRESULT_FROM_WIN32(rc))"
0x1800f5e8d  mov     edx, 0D7h
0x1800f5e92  jmp     short loc_1800F5E23
0x1800f5e94  mov     esi, 3
0x1800f5e99  sub     ebx, 1
0x1800f5e9c  jz      short loc_1800F5EC4
0x1800f5e9e  sub     ebx, 1
0x1800f5ea1  jz      short loc_1800F5EBD
0x1800f5ea3  sub     ebx, 1
0x1800f5ea6  jz      short loc_1800F5EB6
0x1800f5ea8  sub     ebx, 1
0x1800f5eab  jz      short loc_1800F5EB2
0x1800f5ead  lea     edx, [rsi+1]
0x1800f5eb0  jmp     short loc_1800F5EC7
0x1800f5eb2  mov     edx, esi
0x1800f5eb4  jmp     short loc_1800F5EC7
0x1800f5eb6  mov     edx, 2
0x1800f5ebb  jmp     short loc_1800F5EC7
0x1800f5ebd  mov     edx, 1
0x1800f5ec2  jmp     short loc_1800F5EC7
0x1800f5ec4  mov     edx, r12d
0x1800f5ec7  xorps   xmm0, xmm0
0x1800f5eca  movups  [rbp+0E0h+var_130], xmm0
0x1800f5ece  lea     r8, [rbp+0E0h+var_130]
0x1800f5ed2  lea     rcx, [rbp+0E0h+packageFamilyName]; packageFamilyName
0x1800f5ed6  call    sub_18014187C
0x1800f5edb  mov     edi, eax
0x1800f5edd  test    eax, eax
0x1800f5edf  jns     short loc_1800F5EF2
0x1800f5ee1  lea     r9, aChkhrGetconten_3; "ChkHr(GetContentId(szPackageFamilyName,"...
0x1800f5ee8  mov     edx, 0DEh
0x1800f5eed  jmp     loc_1800F5E23
0x1800f5ef2  xor     edx, edx; Val
0x1800f5ef4  lea     r8d, [rdx+4Ah]; Size
0x1800f5ef8  lea     rcx, [rbp+0E0h+sourceString]; void *
0x1800f5efc  call    memset
0x1800f5f01  lea     rdx, [rbp+0E0h+sourceString]
0x1800f5f05  lea     rcx, [rbp+0E0h+var_130]
0x1800f5f09  call    sub_180035374
0x1800f5f0e  mov     edi, eax
0x1800f5f10  test    eax, eax
0x1800f5f12  jns     short loc_1800F5F25
0x1800f5f14  lea     r9, aChkhrGuidtostr_0; "ChkHr(GuidToStringWithoutBraces(&guidCo"...
0x1800f5f1b  mov     edx, 0E1h
0x1800f5f20  jmp     loc_1800F5E23
0x1800f5f25  lea     rdx, [rbp+0E0h+sourceString]; sourceString
0x1800f5f29  lea     rcx, [rbp+0E0h+hstringHeader]; hstringHeader
0x1800f5f2d  call    sub_180010E24
0x1800f5f32  nop
0x1800f5f33  mov     rax, cs:qword_180243410
0x1800f5f3a  mov     [rsp+1E0h+var_180], rax
0x1800f5f3f  mov     rax, [rbp+0E0h+var_138]
0x1800f5f43  mov     [rsp+1E0h+var_178], rax
0x1800f5f48  mov     rax, cs:qword_180243430
0x1800f5f4f  mov     [rsp+1E0h+var_170], rax
0x1800f5f54  mov     rbx, [rsp+1E0h+var_188]
0x1800f5f59  mov     [rsp+1E0h+var_168], rbx
0x1800f5f5e  mov     rax, cs:qword_180243450
0x1800f5f65  mov     [rbp+0E0h+var_160], rax
0x1800f5f69  mov     rax, cs:qword_180243530
0x1800f5f70  mov     [rbp+0E0h+var_158], rax
0x1800f5f74  mov     [rsp+1E0h+string], r12
0x1800f5f79  xor     ecx, ecx; string
0x1800f5f7b  call    cs:WindowsDeleteString
0x1800f5f81  mov     [rsp+1E0h+string], r12
0x1800f5f86  lea     rax, [rsp+1E0h+string]
0x1800f5f8b  mov     [rsp+1E0h+var_1C0], rax
0x1800f5f90  mov     r9d, esi
0x1800f5f93  lea     r8, [rsp+1E0h+var_180]
0x1800f5f98  mov     rdx, cs:qword_180243510
0x1800f5f9f  call    sub_1800C69B8
0x1800f5fa4  mov     edi, eax
0x1800f5fa6  test    eax, eax
0x1800f5fa8  jns     short loc_1800F5FD9
0x1800f5faa  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800f5fae  lea     r9, aChkhrUrihelper_17; "ChkHr(UriHelper::GetUriWithPathAndParam"...
0x1800f5fb5  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f5fbc  mov     edx, 0F1h
0x1800f5fc1  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f5fc8  call    sub_1801519B8
0x1800f5fcd  mov     ecx, edi
0x1800f5fcf  call    sub_18001B940
0x1800f5fd4  jmp     loc_1800F6463
0x1800f5fd9  mov     [rsp+1E0h+var_1A8], r12
0x1800f5fde  lea     r8, [rsp+1E0h+var_1A8]
0x1800f5fe3  mov     rdx, r14
0x1800f5fe6  mov     rcx, [rsp+1E0h+string]
0x1800f5feb  call    sub_1800BA098
0x1800f5ff0  mov     edi, eax
0x1800f5ff2  test    eax, eax
0x1800f5ff4  jns     short loc_1800F6042
0x1800f5ff6  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800f5ffa  lea     r9, aChkhrIaputilsG_13; "ChkHr(IAPUtils::GetJsonFromURL(hstrUri."...
0x1800f6001  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f6008  mov     edx, 0F4h
0x1800f600d  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f6014  call    sub_1801519B8
0x1800f6019  mov     ecx, edi
0x1800f601b  call    sub_18001B940
0x1800f6020  nop
0x1800f6021  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f6026  test    rcx, rcx
0x1800f6029  jz      short loc_1800F603D
0x1800f602b  mov     [rsp+1E0h+var_1A8], r12
0x1800f6030  mov     rax, [rcx]
0x1800f6033  mov     rax, [rax+10h]
0x1800f6037  call    j__guard_dispatch_icall
0x1800f603c  nop
0x1800f603d  jmp     loc_1800F6463
0x1800f6042  mov     [rsp+1E0h+var_1A0], r12
0x1800f6047  lea     r8, [rsp+1E0h+var_1A0]
0x1800f604c  lea     rdx, aDisplayskusear; "DisplaySkuSearchResult"
0x1800f6053  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f6058  call    sub_1800AD3F0
0x1800f605d  mov     edi, eax
0x1800f605f  test    eax, eax
0x1800f6061  jns     short loc_1800F60CB
0x1800f6063  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800f6067  lea     r9, aChkhrJsonhelpe_232; "ChkHr(JsonHelpers::GetNamedObject(jsonO"...
0x1800f606e  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f6075  mov     edx, 0F8h
0x1800f607a  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f6081  call    sub_1801519B8
0x1800f6086  mov     ecx, edi
0x1800f6088  call    sub_18001B940
0x1800f608d  nop
0x1800f608e  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f6093  test    rcx, rcx
0x1800f6096  jz      short loc_1800F60AA
0x1800f6098  mov     [rsp+1E0h+var_1A0], r12
0x1800f609d  mov     rax, [rcx]
0x1800f60a0  mov     rax, [rax+10h]
0x1800f60a4  call    j__guard_dispatch_icall
0x1800f60a9  nop
0x1800f60aa  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f60af  test    rcx, rcx
0x1800f60b2  jz      short loc_1800F60C6
0x1800f60b4  mov     [rsp+1E0h+var_1A8], r12
0x1800f60b9  mov     rax, [rcx]
0x1800f60bc  mov     rax, [rax+10h]
0x1800f60c0  call    j__guard_dispatch_icall
0x1800f60c5  nop
0x1800f60c6  jmp     loc_1800F6463
0x1800f60cb  mov     [rsp+1E0h+packageFamilyNameLength], r12d
0x1800f60d0  lea     r8, [rsp+1E0h+packageFamilyNameLength]
0x1800f60d5  lea     rdx, aTotalresultcou; "TotalResultCount"
0x1800f60dc  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f60e1  call    sub_1800AD350
0x1800f60e6  mov     edi, eax
0x1800f60e8  test    eax, eax
0x1800f60ea  jns     short loc_1800F6154
0x1800f60ec  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800f60f0  lea     r9, aChkhrJsonhelpe_229; "ChkHr(JsonHelpers::GetNamedInteger(disp"...
0x1800f60f7  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f60fe  mov     edx, 0FCh
0x1800f6103  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f610a  call    sub_1801519B8
0x1800f610f  mov     ecx, edi
0x1800f6111  call    sub_18001B940
0x1800f6116  nop
0x1800f6117  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f611c  test    rcx, rcx
0x1800f611f  jz      short loc_1800F6133
0x1800f6121  mov     [rsp+1E0h+var_1A0], r12
0x1800f6126  mov     rax, [rcx]
0x1800f6129  mov     rax, [rax+10h]
0x1800f612d  call    j__guard_dispatch_icall
0x1800f6132  nop
0x1800f6133  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f6138  test    rcx, rcx
0x1800f613b  jz      short loc_1800F614F
0x1800f613d  mov     [rsp+1E0h+var_1A8], r12
0x1800f6142  mov     rax, [rcx]
0x1800f6145  mov     rax, [rax+10h]
0x1800f6149  call    j__guard_dispatch_icall
0x1800f614e  nop
0x1800f614f  jmp     loc_1800F6463
0x1800f6154  cmp     [rsp+1E0h+packageFamilyNameLength], r12d
0x1800f6159  jnz     short loc_1800F61C8
0x1800f615b  mov     edi, 80070490h
0x1800f6160  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x1800f6164  lea     r9, aChkhrHresultFr_0; "ChkHr(HRESULT_FROM_WIN32(1168L))"
0x1800f616b  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f6172  mov     edx, 0FFh
0x1800f6177  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f617e  call    sub_1801519B8
0x1800f6183  mov     ecx, edi
0x1800f6185  call    sub_18001B940
0x1800f618a  nop
0x1800f618b  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f6190  test    rcx, rcx
0x1800f6193  jz      short loc_1800F61A7
0x1800f6195  mov     [rsp+1E0h+var_1A0], r12
0x1800f619a  mov     rax, [rcx]
0x1800f619d  mov     rax, [rax+10h]
0x1800f61a1  call    j__guard_dispatch_icall
0x1800f61a6  nop
0x1800f61a7  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f61ac  test    rcx, rcx
0x1800f61af  jz      short loc_1800F61C3
0x1800f61b1  mov     [rsp+1E0h+var_1A8], r12
0x1800f61b6  mov     rax, [rcx]
0x1800f61b9  mov     rax, [rax+10h]
0x1800f61bd  call    j__guard_dispatch_icall
0x1800f61c2  nop
0x1800f61c3  jmp     loc_1800F6463
0x1800f61c8  mov     qword ptr [rsp+1E0h+packageFamilyNameLength], r12
0x1800f61cd  lea     r8, [rsp+1E0h+packageFamilyNameLength]
0x1800f61d2  lea     rdx, aProducts; "Products"
0x1800f61d9  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f61de  call    sub_1800AD1F0
0x1800f61e3  mov     edi, eax
0x1800f61e5  test    eax, eax
0x1800f61e7  jns     loc_1800F6271
0x1800f61ed  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800f61f1  lea     r9, aChkhrJsonhelpe_230; "ChkHr(JsonHelpers::GetNamedArray(displa"...
0x1800f61f8  lea     r8, aCatalogservice_7; "CatalogServiceProxyV6::QueryCatalogForB"...
0x1800f61ff  mov     edx, 106h
0x1800f6204  lea     rcx, aOnecoreuapEndu_15; "onecoreuap\\enduser\\winstore\\licensin"...
0x1800f620b  call    sub_1801519B8
0x1800f6210  mov     ecx, edi
0x1800f6212  call    sub_18001B940
0x1800f6217  nop
0x1800f6218  mov     rcx, qword ptr [rsp+1E0h+packageFamilyNameLength]
0x1800f621d  test    rcx, rcx
0x1800f6220  jz      short loc_1800F6234
0x1800f6222  mov     qword ptr [rsp+1E0h+packageFamilyNameLength], r12
0x1800f6227  mov     rax, [rcx]
0x1800f622a  mov     rax, [rax+10h]
0x1800f622e  call    j__guard_dispatch_icall
0x1800f6233  nop
0x1800f6234  mov     rcx, [rsp+1E0h+var_1A0]
0x1800f6239  test    rcx, rcx
0x1800f623c  jz      short loc_1800F6250
0x1800f623e  mov     [rsp+1E0h+var_1A0], r12
0x1800f6243  mov     rax, [rcx]
0x1800f6246  mov     rax, [rax+10h]
0x1800f624a  call    j__guard_dispatch_icall
0x1800f624f  nop
0x1800f6250  mov     rcx, [rsp+1E0h+var_1A8]
0x1800f6255  test    rcx, rcx
0x1800f6258  jz      short loc_1800F626C
0x1800f625a  mov     [rsp+1E0h+var_1A8], r12
0x1800f625f  mov     rax, [rcx]
0x1800f6262  mov     rax, [rax+10h]
0x1800f6266  call    j__guard_dispatch_icall
0x1800f626b  nop
  ... truncated ...
```
