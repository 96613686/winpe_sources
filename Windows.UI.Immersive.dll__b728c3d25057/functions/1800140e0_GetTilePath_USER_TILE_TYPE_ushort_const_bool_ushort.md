# _GetTilePath(USER_TILE_TYPE,ushort const *,bool,ushort * *)

- ea: `0x1800140e0`
- end: `0x180014874`
- name: `?_GetTilePath@@YAJW4USER_TILE_TYPE@@PEBG_NPEAPEAG@Z`
- size: `1940`
- prototype: `int __high(enum USER_TILE_TYPE, const unsigned __int16 *, bool, unsigned __int16 **)`
- caller_count: `14`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013cc0`
- `0x180013d00`
- `0x180013fe0`
- `0x1800392fc`
- `0x180043f4c`
- `0x1800448b0`
- `0x1800c2590`
- `0x1800c2610`
- `0x1800c2950`
- `0x1800c4770`
- `0x1800c4e10`
- `0x1800c51c0`
- `0x1800c6a1c`
- `0x1800c87b4`

## callees

- `0x18000d2b8`
- `0x1800140e0`
- `0x180014a10`
- `0x180039d24`
- `0x18003a68c`
- `0x18003aa84`
- `0x180048540`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014689`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014732`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014689`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014732`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014771`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014239`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014357`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014357`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014569`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014569`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001448d`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001448d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001479a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001479a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18001421a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18001421a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001424d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014293`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014455`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800144f5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001424d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014293`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014455`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800144f5`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014132`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014132`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014716`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001432a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001436d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014510`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800141be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001432a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001436d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014510`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001469c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014740`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001469c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014740`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001475e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001475e`

## string_xrefs

- `0x180014793`: `%ProgramData%`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall _GetTilePath(unsigned int a1, const WCHAR *a2, char a3, LPWSTR *a4)
{
  const WCHAR *v5; // rsi
  unsigned __int16 *v7; // r15
  WCHAR *v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rdx
  const wchar_t *v11; // r8
  __int64 v12; // r9
  WCHAR *v13; // r10
  wchar_t v14; // ax
  HRESULT Error; // r14d
  int ValueW; // ebx
  WCHAR *v17; // rdx
  int v18; // eax
  bool v20; // sf
  HRESULT CurrentUsersSidString; // eax
  __int64 v22; // rdx
  WCHAR *v23; // rax
  LPWSTR v24; // rcx
  WCHAR *v25; // r8
  WCHAR v26; // ax
  WCHAR *v27; // rcx
  LPWSTR v28; // rcx
  LSTATUS v29; // eax
  WCHAR *v30; // rcx
  const WCHAR *v31; // rsi
  signed int LastError; // eax
  bool v33; // bl
  unsigned int v34; // edx
  const WCHAR *v35; // rcx
  WCHAR *v36; // rcx
  bool v37; // sf
  const WCHAR *v38; // rsi
  int LargeSizeForTileType; // ebx
  DWORD v40; // eax
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h] BYREF
  char v42; // [rsp+48h] [rbp-B8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR ppwsz; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v45; // [rsp+60h] [rbp-A0h]
  HSTRING string; // [rsp+68h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 pvData[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR psz[260]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v51[528]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v42 = a3;
  v5 = a2;
  v45 = a2;
  *a4 = 0;
  v7 = 0;
  if ( (unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) || a1 == 3 )
  {
    ValueW = -2147467259;
    if ( WindowsCreateStringReference(L"Default user tile forced by group policy.", 0x29u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    RoOriginateError(2147500037LL, string);
    Error = -2147024774;
    v5 = v45;
    goto LABEL_14;
  }
  hKey = 0;
  v8 = 0;
  lpSubKey = 0;
  v9 = 2147483646;
  v10 = 2147483646;
  v11 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
  v12 = 260;
  v13 = psz;
  do
  {
    if ( !v10 )
      break;
    v14 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v13++ = v14;
    --v10;
    --v12;
  }
  while ( v12 );
  Error = -2147024774;
  ValueW = -2147024774;
  if ( v12 )
    ValueW = 0;
  v17 = v13 - 1;
  if ( v12 )
    v17 = v13;
  *v17 = 0;
  if ( !v12 )
    goto LABEL_12;
  ppwsz = 0;
  if ( v5 )
    CurrentUsersSidString = SHStrDupW(v5, &ppwsz);
  else
    CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
  ValueW = CurrentUsersSidString;
  if ( CurrentUsersSidString >= 0 )
  {
    v22 = 260;
    v23 = psz;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    ValueW = -2147024809;
    if ( v22 )
    {
      v24 = ppwsz;
      v25 = (WCHAR *)(v51 - 2 * v22 + 6);
      do
      {
        if ( !v9 )
          break;
        v26 = *v24;
        if ( !*v24 )
          break;
        ++v24;
        *v25++ = v26;
        --v9;
        --v22;
      }
      while ( v22 );
      ValueW = -2147024774;
      if ( v22 )
        ValueW = 0;
      v27 = v25 - 1;
      if ( v22 )
        v27 = v25;
      *v27 = 0;
      if ( v22 )
        ValueW = SHStrDupW(psz, (LPWSTR *)&lpSubKey);
    }
  }
  v28 = ppwsz;
  ppwsz = 0;
  CoTaskMemFree(v28);
  if ( ValueW < 0 )
  {
    v8 = (WCHAR *)lpSubKey;
LABEL_12:
    lpSubKey = 0;
    CoTaskMemFree(v8);
    goto LABEL_13;
  }
  v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  ValueW = v29;
  if ( v29 > 0 )
    ValueW = (unsigned __int16)v29 | 0x80070000;
  v30 = (WCHAR *)lpSubKey;
  lpSubKey = 0;
  CoTaskMemFree(v30);
  if ( ValueW >= 0 )
  {
    if ( a1 )
    {
      if ( a1 != 8 )
      {
        switch ( a1 )
        {
          case 1u:
            v31 = L"Image448";
            goto LABEL_49;
          case 2u:
            v31 = L"Video448";
            goto LABEL_49;
          case 4u:
            v31 = L"Image32";
            goto LABEL_49;
          case 5u:
            v31 = L"Image40";
            goto LABEL_49;
          case 6u:
            v31 = L"Image48";
            goto LABEL_49;
          case 7u:
            v31 = L"Image192";
            goto LABEL_49;
          case 9u:
            v31 = L"Image240";
            goto LABEL_49;
          case 0xAu:
            v31 = L"Video240";
            goto LABEL_49;
          case 0xBu:
            v31 = L"Image64";
            goto LABEL_49;
          case 0xCu:
            v31 = L"Image208";
            goto LABEL_49;
          case 0xDu:
            v31 = L"Image424";
            goto LABEL_49;
          case 0xEu:
            v31 = L"Image1080";
            goto LABEL_49;
          default:
            if ( WindowsCreateStringReference(L"Unexpected UserImageKind.", 0x19u, &hstringHeader, &string) < 0 )
              RaiseException(0xC000000D, 1u, 0, 0);
            RoOriginateError(2147500037LL, string);
            ValueW = -2147467259;
            break;
        }
        goto LABEL_22;
      }
      v31 = L"Video192";
    }
    else
    {
      v31 = L"Image96";
    }
LABEL_49:
    LODWORD(lpSubKey) = 520;
    ValueW = RegGetValueW(hKey, 0, v31, 2u, 0, pvData, (LPDWORD)&lpSubKey);
    if ( ValueW )
    {
      pvData[0] = 0;
      v20 = ValueW < 0;
      if ( ValueW <= 0 )
        goto LABEL_19;
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    v20 = ValueW < 0;
LABEL_19:
    if ( !v20 )
      goto LABEL_20;
    switch ( a1 )
    {
      case 4u:
        v38 = L"Image40";
        break;
      case 6u:
        v38 = L"Image96";
        break;
      case 7u:
        v38 = L"Image200";
        break;
      case 8u:
        v38 = L"Video200";
        break;
      default:
        goto LABEL_22;
    }
    LODWORD(lpSubKey) = 520;
    ValueW = RegGetValueW(hKey, 0, v38, 2u, 0, pvData, (LPDWORD)&lpSubKey);
    if ( ValueW )
    {
      pvData[0] = 0;
      v37 = ValueW < 0;
      if ( ValueW <= 0 )
      {
LABEL_78:
        if ( !v37 )
        {
LABEL_20:
          if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, v51, 260) )
          {
            v7 = (unsigned __int16 *)v51;
          }
          else
          {
            v7 = pvData;
            LastError = GetLastError();
            ValueW = LastError;
            if ( LastError > 0 )
              ValueW = (unsigned __int16)LastError | 0x80070000;
            if ( ValueW >= 0 )
              ValueW = -2147467259;
          }
        }
LABEL_22:
        if ( hKey )
          RegCloseKey(hKey);
        if ( ValueW >= 0 )
          return SHStrDupW(v7, a4);
        v5 = v45;
        goto LABEL_13;
      }
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    }
    v37 = ValueW < 0;
    goto LABEL_78;
  }
LABEL_13:
  if ( !v42 )
    return ValueW;
LABEL_14:
  if ( a1 <= 0xA )
  {
    v18 = 1284;
    if ( _bittest(&v18, a1) )
    {
      if ( ValueW < 0 )
        return ValueW;
      return SHStrDupW(v7, a4);
    }
  }
  v33 = 0;
  hKey = 0;
  if ( !v5 )
  {
    if ( (int)GetCurrentUserSid((void **)&hKey) < 0 )
      goto LABEL_64;
    goto LABEL_63;
  }
  if ( ConvertStringSidToSidW(v5, (PSID *)&hKey) )
LABEL_63:
    v33 = IsWellKnownSid(hKey, WinAccountGuestSid);
LABEL_64:
  if ( hKey )
    LocalFree(hKey);
  if ( !v33 )
  {
    LargeSizeForTileType = _GetLargeSizeForTileType(a1);
    v40 = ExpandEnvironmentStringsW(L"%ProgramData%", psz, 0x104u);
    if ( v40 )
    {
      if ( v40 > 0x104 )
        goto LABEL_68;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_68;
    }
    lpSubKey = 0;
    switch ( LargeSizeForTileType )
    {
      case 32:
        v35 = L"user-32.png";
        break;
      case 40:
        v35 = L"user-40.png";
        break;
      case 48:
        v35 = L"user-48.png";
        break;
      case 192:
        v35 = L"user-192.png";
        break;
      default:
        v35 = L"user.png";
        break;
    }
    Error = SHStrDupW(v35, (LPWSTR *)&lpSubKey);
    if ( Error >= 0 )
      Error = StringCchPrintfW(pvData, 0x104u, L"%s\\%s\\%s", psz, L"Microsoft\\User Account Pictures", lpSubKey);
    v36 = (WCHAR *)lpSubKey;
    lpSubKey = 0;
    CoTaskMemFree(v36);
    goto LABEL_68;
  }
  Error = SHGetDefaultGuestPicturePath(pvData, v34);
LABEL_68:
  if ( Error >= 0 )
  {
    v7 = pvData;
    return SHStrDupW(v7, a4);
  }
  return Error;
}

```

## disassembly

```asm
0x1800140e0  mov     [rsp-8+arg_0], rbx
0x1800140e5  push    rbp
0x1800140e6  push    rsi
0x1800140e7  push    rdi
0x1800140e8  push    r12
0x1800140ea  push    r13
0x1800140ec  push    r14
0x1800140ee  push    r15
0x1800140f0  lea     rbp, [rsp-5D0h]
0x1800140f8  sub     rsp, 6D0h
0x1800140ff  mov     rax, cs:__security_cookie
0x180014106  xor     rax, rsp
0x180014109  mov     [rbp+600h+var_40], rax
0x180014110  mov     r12, r9
0x180014113  mov     [rsp+700h+var_6B8], r8b
0x180014118  mov     rsi, rdx
0x18001411b  mov     [rsp+700h+var_6A0], rdx
0x180014120  mov     r13d, ecx
0x180014123  xor     ebx, ebx
0x180014125  mov     [r9], rbx
0x180014128  mov     r15d, ebx
0x18001412b  lea     rcx, POLID_UseDefaultTile
0x180014132  call    cs:__imp_SHWindowsPolicy
0x180014138  test    eax, eax
0x18001413a  jnz     loc_1800146F9
0x180014140  cmp     r13d, 3
0x180014144  jz      loc_1800146F9
0x18001414a  mov     [rsp+700h+hKey], rbx
0x18001414f  mov     ecx, ebx; pv
0x180014151  mov     [rsp+700h+lpSubKey], rbx
0x180014156  mov     edi, 7FFFFFFEh
0x18001415b  mov     edx, edi
0x18001415d  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014164  mov     r9d, 104h
0x18001416a  lea     r10, [rbp+600h+psz]
0x180014171  test    rdx, rdx
0x180014174  jz      short loc_180014194
0x180014176  movzx   eax, word ptr [r8]
0x18001417a  test    ax, ax
0x18001417d  jz      short loc_180014194
0x18001417f  add     r8, 2
0x180014183  mov     [r10], ax
0x180014187  add     r10, 2
0x18001418b  dec     rdx
0x18001418e  sub     r9, 1
0x180014192  jnz     short loc_180014171
0x180014194  mov     r14d, 8007007Ah
0x18001419a  mov     ebx, r14d
0x18001419d  xor     r8d, r8d
0x1800141a0  test    r9, r9
0x1800141a3  cmovnz  ebx, r8d
0x1800141a7  lea     rdx, [r10-2]
0x1800141ab  cmovnz  rdx, r10
0x1800141af  mov     [rdx], r8w
0x1800141b3  jnz     loc_18001427D
0x1800141b9  mov     [rsp+700h+lpSubKey], r8
0x1800141be  call    cs:__imp_CoTaskMemFree
0x1800141c4  mov     edi, 1
0x1800141c9  cmp     [rsp+700h+var_6B8], 0
0x1800141ce  jz      loc_1800146F2
0x1800141d4  cmp     r13d, 0Ah
0x1800141d8  ja      loc_180014462
0x1800141de  mov     eax, 504h
0x1800141e3  bt      eax, r13d
0x1800141e7  jnb     loc_180014462
0x1800141ed  test    ebx, ebx
0x1800141ef  jns     short loc_180014247
0x1800141f1  mov     eax, ebx
0x1800141f3  jmp     short loc_180014253
0x1800141f5  xor     eax, eax
0x1800141f7  mov     [rbp+600h+var_670], ax
0x1800141fb  test    ebx, ebx
0x1800141fd  jg      loc_180014424
0x180014203  js      loc_180014582
0x180014209  mov     r8d, 104h
0x18001420f  lea     rdx, [rbp+600h+var_250]
0x180014216  lea     rcx, [rbp+600h+var_670]
0x18001421a  call    cs:__imp_SHExpandEnvironmentStringsW
0x180014220  test    eax, eax
0x180014222  jz      loc_1800143EF
0x180014228  lea     r15, [rbp+600h+var_250]
0x18001422f  mov     rcx, [rsp+700h+hKey]; hKey
0x180014234  test    rcx, rcx
0x180014237  jz      short loc_18001423F
0x180014239  call    cs:__imp_RegCloseKey
0x18001423f  test    ebx, ebx
0x180014241  js      loc_1800146E8
0x180014247  mov     rdx, r12; ppwsz
0x18001424a  mov     rcx, r15; psz
0x18001424d  call    cs:__imp_SHStrDupW
0x180014253  mov     rcx, [rbp+600h+var_40]
0x18001425a  xor     rcx, rsp; StackCookie
0x18001425d  call    __security_check_cookie
0x180014262  mov     rbx, [rsp+700h+arg_0]
0x18001426a  add     rsp, 6D0h
0x180014271  pop     r15
0x180014273  pop     r14
0x180014275  pop     r13
0x180014277  pop     r12
0x180014279  pop     rdi
0x18001427a  pop     rsi
0x18001427b  pop     rbp
0x18001427c  retn
0x18001427d  mov     [rsp+700h+ppwsz], r8
0x180014282  test    rsi, rsi
0x180014285  jz      loc_18001442F
0x18001428b  lea     rdx, [rsp+700h+ppwsz]; ppwsz
0x180014290  mov     rcx, rsi; psz
0x180014293  call    cs:__imp_SHStrDupW
0x180014299  mov     ebx, eax
0x18001429b  test    eax, eax
0x18001429d  js      loc_180014320
0x1800142a3  mov     edx, 104h
0x1800142a8  lea     rax, [rbp+600h+psz]
0x1800142af  nop
0x1800142b0  cmp     [rax], r15w
0x1800142b4  jz      short loc_1800142C0
0x1800142b6  add     rax, 2
0x1800142ba  sub     rdx, 1
0x1800142be  jnz     short loc_1800142B0
0x1800142c0  mov     ebx, 80070057h
0x1800142c5  xor     eax, eax
0x1800142c7  test    rdx, rdx
0x1800142ca  cmovnz  ebx, eax
0x1800142cd  jz      short loc_180014320
0x1800142cf  mov     rcx, [rsp+700h+ppwsz]
0x1800142d4  lea     rax, [rdx+rdx]
0x1800142d8  lea     r8, [rbp+600h+var_258]
0x1800142df  sub     r8, rax
0x1800142e2  test    rdi, rdi
0x1800142e5  jz      short loc_180014304
0x1800142e7  movzx   eax, word ptr [rcx]
0x1800142ea  test    ax, ax
0x1800142ed  jz      short loc_180014304
0x1800142ef  add     rcx, 2
0x1800142f3  mov     [r8], ax
0x1800142f7  add     r8, 2
0x1800142fb  dec     rdi
0x1800142fe  sub     rdx, 1
0x180014302  jnz     short loc_1800142E2
0x180014304  mov     ebx, r14d
0x180014307  xor     eax, eax
0x180014309  test    rdx, rdx
0x18001430c  cmovnz  ebx, eax
0x18001430f  lea     rcx, [r8-2]
0x180014313  cmovnz  rcx, r8
0x180014317  mov     [rcx], ax
0x18001431a  jnz     loc_180014449
0x180014320  mov     rcx, [rsp+700h+ppwsz]; pv
0x180014325  mov     [rsp+700h+ppwsz], r15
0x18001432a  call    cs:__imp_CoTaskMemFree
0x180014330  test    ebx, ebx
0x180014332  js      loc_1800143E2
0x180014338  lea     rax, [rsp+700h+hKey]
0x18001433d  mov     [rsp+700h+phkResult], rax; phkResult
0x180014342  mov     r9d, 20119h; samDesired
0x180014348  xor     r8d, r8d; ulOptions
0x18001434b  mov     rdx, [rsp+700h+lpSubKey]; lpSubKey
0x180014350  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014357  call    cs:__imp_RegOpenKeyExW
0x18001435d  mov     ebx, eax
0x18001435f  test    eax, eax
0x180014361  jg      short loc_1800143D7
0x180014363  mov     rcx, [rsp+700h+lpSubKey]; pv
0x180014368  mov     [rsp+700h+lpSubKey], r15
0x18001436d  call    cs:__imp_CoTaskMemFree
0x180014373  test    ebx, ebx
0x180014375  js      loc_1800141C4
0x18001437b  mov     edi, 1
0x180014380  test    r13d, r13d
0x180014383  jnz     loc_18001440E
0x180014389  lea     rsi, aImage96; "Image96"
0x180014390  mov     dword ptr [rsp+700h+lpSubKey], 208h
0x180014398  lea     rax, [rsp+700h+lpSubKey]
0x18001439d  mov     [rsp+700h+pcbData], rax; pcbData
0x1800143a2  lea     rax, [rbp+600h+var_670]
0x1800143a6  mov     [rsp+700h+pvData], rax; pvData
0x1800143ab  mov     [rsp+700h+phkResult], r15; pdwType
0x1800143b0  mov     r9d, 2; dwFlags
0x1800143b6  mov     r8, rsi; lpValue
0x1800143b9  xor     edx, edx; lpSubKey
0x1800143bb  mov     rcx, [rsp+700h+hKey]; hkey
0x1800143c0  call    cs:__imp_RegGetValueW
0x1800143c6  mov     ebx, eax
0x1800143c8  test    eax, eax
0x1800143ca  jnz     loc_1800141F5
0x1800143d0  test    ebx, ebx
0x1800143d2  jmp     loc_180014203
0x1800143d7  movzx   ebx, ax
0x1800143da  or      ebx, 80070000h
0x1800143e0  jmp     short loc_180014363
0x1800143e2  mov     rcx, [rsp+700h+lpSubKey]
0x1800143e7  xor     r8d, r8d
0x1800143ea  jmp     loc_1800141B9
0x1800143ef  lea     r15, [rbp+600h+var_670]
0x1800143f3  call    cs:__imp_GetLastError
0x1800143f9  mov     ebx, eax
0x1800143fb  test    eax, eax
0x1800143fd  jg      short loc_18001443E
0x1800143ff  mov     esi, 80004005h
0x180014404  test    ebx, ebx
0x180014406  cmovns  ebx, esi
0x180014409  jmp     loc_18001422F
0x18001440e  cmp     r13d, 8
0x180014412  jnz     loc_1800145AA
0x180014418  lea     rsi, aVideo192; "Video192"
0x18001441f  jmp     loc_180014390
0x180014424  movzx   ebx, bx
0x180014427  or      ebx, 80070000h
0x18001442d  jmp     short loc_1800143D0
0x18001442f  lea     rcx, [rsp+700h+ppwsz]; ppwsz
0x180014434  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180014439  jmp     loc_180014299
0x18001443e  movzx   ebx, ax
0x180014441  or      ebx, 80070000h
0x180014447  jmp     short loc_1800143FF
0x180014449  lea     rdx, [rsp+700h+lpSubKey]; ppwsz
0x18001444e  lea     rcx, [rbp+600h+psz]; psz
0x180014455  call    cs:__imp_SHStrDupW
0x18001445b  mov     ebx, eax
0x18001445d  jmp     loc_180014320
0x180014462  xor     bl, bl
0x180014464  xor     r15d, r15d
0x180014467  mov     [rsp+700h+hKey], r15
0x18001446c  test    rsi, rsi
0x18001446f  jnz     loc_180014756
0x180014475  lea     rcx, [rsp+700h+hKey]; void **
0x18001447a  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18001447f  test    eax, eax
0x180014481  js      short loc_18001449B
0x180014483  mov     edx, 27h ; '''; WellKnownSidType
0x180014488  mov     rcx, [rsp+700h+hKey]; pSid
0x18001448d  call    cs:__imp_IsWellKnownSid
0x180014493  movzx   ebx, bl
0x180014496  test    eax, eax
0x180014498  cmovnz  ebx, edi
0x18001449b  mov     rcx, [rsp+700h+hKey]; hMem
0x1800144a0  test    rcx, rcx
0x1800144a3  jnz     loc_180014771
0x1800144a9  test    bl, bl
0x1800144ab  jz      loc_18001477C
0x1800144b1  lea     rcx, [rbp+600h+var_670]; unsigned __int16 *
0x1800144b5  call    ?SHGetDefaultGuestPicturePath@@YAJPEAGK@Z; SHGetDefaultGuestPicturePath(ushort *,ulong)
0x1800144ba  mov     r14d, eax
0x1800144bd  test    r14d, r14d
0x1800144c0  js      loc_180014834
0x1800144c6  lea     r15, [rbp+600h+var_670]
0x1800144ca  jmp     loc_180014247
0x1800144cf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800144d4  mov     r14d, eax
0x1800144d7  test    eax, eax
0x1800144d9  js      short loc_1800144BD
0x1800144db  mov     [rsp+700h+lpSubKey], r15
0x1800144e0  lea     rdx, [rsp+700h+lpSubKey]; ppwsz
0x1800144e5  cmp     ebx, 20h ; ' '
0x1800144e8  jnz     loc_1800147B8
0x1800144ee  lea     rcx, psz; "user-32.png"
0x1800144f5  call    cs:__imp_SHStrDupW
0x1800144fb  mov     r14d, eax
0x1800144fe  test    eax, eax
0x180014500  jns     loc_1800147FA
0x180014506  mov     rcx, [rsp+700h+lpSubKey]; pv
0x18001450b  mov     [rsp+700h+lpSubKey], r15
0x180014510  call    cs:__imp_CoTaskMemFree
0x180014516  jmp     short loc_1800144BD
0x180014518  mov     ecx, r13d
0x18001451b  sub     ecx, 4
0x18001451e  jz      short loc_18001458C
0x180014520  sub     ecx, 2
0x180014523  jz      loc_1800146DC
0x180014529  sub     ecx, edi
0x18001452b  jz      loc_1800146D0
0x180014531  cmp     ecx, edi
0x180014533  jz      loc_1800146C4
0x180014539  mov     dword ptr [rsp+700h+lpSubKey], 208h
0x180014541  lea     rax, [rsp+700h+lpSubKey]
0x180014546  mov     [rsp+700h+pcbData], rax; pcbData
0x18001454b  lea     rax, [rbp+600h+var_670]
0x18001454f  mov     [rsp+700h+pvData], rax; pvData
0x180014554  mov     [rsp+700h+phkResult], r15; pdwType
0x180014559  mov     r9d, 2; dwFlags
0x18001455f  mov     r8, rsi; lpValue
0x180014562  xor     edx, edx; lpSubKey
0x180014564  mov     rcx, [rsp+700h+hKey]; hkey
0x180014569  call    cs:__imp_RegGetValueW
0x18001456f  mov     ebx, eax
0x180014571  test    eax, eax
0x180014573  jnz     short loc_180014595
0x180014575  test    ebx, ebx
0x180014577  js      loc_18001422F
0x18001457d  jmp     loc_180014209
0x180014582  cmp     r13d, 4
0x180014586  jnz     loc_1800146A9
0x18001458c  lea     rsi, aImage40; "Image40"
0x180014593  jmp     short loc_180014539
0x180014595  xor     eax, eax
0x180014597  mov     [rbp+600h+var_670], ax
0x18001459b  test    ebx, ebx
0x18001459d  jle     short loc_180014577
0x18001459f  movzx   ebx, bx
  ... truncated ...
```
