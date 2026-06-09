# CUserTileStore::GetUserTilePathBySizeNoDefault(ushort const *,uint,ushort * *)

- ea: `0x180014bd0`
- end: `0x1800151bb`
- name: `?GetUserTilePathBySizeNoDefault@CUserTileStore@@UEAAJPEBGIPEAPEAG@Z`
- size: `1515`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180014a10`
- `0x180014bd0`
- `0x1800151c4`
- `0x18001527c`
- `0x18003a68c`
- `0x180047a54`
- `0x180048540`
- `0x18004908c`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014eb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800151af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014e60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014da1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014da1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014e1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014fcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014e1c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014fcf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180014e45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180014e45`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014cbb`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014e70`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014f01`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014cbb`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014e70`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180014f01`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014c22`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180014c22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800150c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015192`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800150c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015192`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014dbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014dbb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014f2e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800150f0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014f2e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800150f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserTileStore::GetUserTilePathBySizeNoDefault(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  int TileTypeForLargeSize; // esi
  __int64 v7; // rdi
  __int64 v8; // rax
  const wchar_t *v9; // rcx
  __int64 v10; // r8
  WCHAR *v11; // r9
  wchar_t v12; // dx
  signed int v13; // ebx
  WCHAR *v14; // rdx
  HRESULT CurrentUsersSidString; // eax
  __int64 v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // r8
  LPWSTR v19; // rax
  bool v20; // zf
  __int64 v21; // rdx
  WCHAR *v22; // r8
  WCHAR v23; // cx
  WCHAR *v24; // rcx
  LPWSTR v25; // rcx
  LSTATUS v26; // eax
  WCHAR *v27; // rcx
  WCHAR *v28; // r14
  const WCHAR *v29; // rdi
  LSTATUS ValueW; // eax
  signed int LastError; // eax
  unsigned int v33; // edx
  int DefaultUserPicturePathBySize; // eax
  unsigned int LargeSizeForTileType; // eax
  bool v36; // cl
  unsigned int v37; // r9d
  LSTATUS v38; // eax
  const WCHAR *v39; // rdi
  LPWSTR ppwsz; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v46[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR psz[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  *a4 = 0;
  TileTypeForLargeSize = _GetTileTypeForLargeSize(a3);
  *a4 = 0;
  if ( !(unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) && TileTypeForLargeSize != 3 )
  {
    hkey = 0;
    lpSubKey = 0;
    v7 = 2147483646;
    v8 = 2147483646;
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
    v10 = 260;
    v11 = v46;
    do
    {
      if ( !v8 )
        break;
      v12 = *v9;
      if ( !*v9 )
        break;
      ++v9;
      *v11++ = v12;
      --v8;
      --v10;
    }
    while ( v10 );
    v13 = v10 == 0 ? 0x8007007A : 0;
    v14 = v11 - 1;
    if ( v10 )
      v14 = v11;
    *v14 = 0;
    if ( v10 )
    {
      ppwsz = 0;
      if ( a2 )
        CurrentUsersSidString = SHStrDupW(a2, &ppwsz);
      else
        CurrentUsersSidString = GetCurrentUsersSidString(&ppwsz);
      v13 = CurrentUsersSidString;
      if ( CurrentUsersSidString >= 0 )
      {
        v16 = 260;
        v17 = v46;
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v16;
        }
        while ( v16 );
        v13 = v16 == 0 ? 0x80070057 : 0;
        v18 = (260 - v16) & -(__int64)(v16 != 0);
        if ( v16 )
        {
          v19 = ppwsz;
          v21 = 260 - v18;
          v20 = v18 == 260;
          v22 = &v46[v18];
          if ( !v20 )
          {
            do
            {
              if ( !v7 )
                break;
              v23 = *v19;
              if ( !*v19 )
                break;
              ++v19;
              *v22++ = v23;
              --v7;
              --v21;
            }
            while ( v21 );
          }
          v13 = v21 == 0 ? 0x8007007A : 0;
          v24 = v22 - 1;
          if ( v21 )
            v24 = v22;
          *v24 = 0;
          if ( v21 )
            v13 = SHStrDupW(v46, (LPWSTR *)&lpSubKey);
        }
      }
      v25 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v25);
      if ( v13 >= 0 )
      {
        v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hkey);
        v13 = v26;
        if ( v26 > 0 )
          v13 = (unsigned __int16)v26 | 0x80070000;
      }
    }
    v27 = (WCHAR *)lpSubKey;
    lpSubKey = 0;
    CoTaskMemFree(v27);
    if ( v13 < 0 )
      return (unsigned int)v13;
    v28 = 0;
    if ( TileTypeForLargeSize == 8 )
    {
      v29 = L"Video192";
      goto LABEL_33;
    }
    if ( TileTypeForLargeSize > 8 )
    {
      switch ( TileTypeForLargeSize )
      {
        case 9:
          v29 = L"Image240";
          break;
        case 10:
          v29 = L"Video240";
          break;
        case 11:
          v29 = L"Image64";
          break;
        case 12:
          v29 = L"Image208";
          break;
        case 13:
          v29 = L"Image424";
          break;
        case 14:
          v29 = L"Image1080";
          break;
        default:
          goto LABEL_83;
      }
    }
    else
    {
      switch ( TileTypeForLargeSize )
      {
        case 0:
          v29 = L"Image96";
          break;
        case 1:
          v29 = L"Image448";
          break;
        case 2:
          v29 = L"Video448";
          break;
        case 4:
          v29 = L"Image32";
          break;
        case 5:
          v29 = L"Image40";
          break;
        case 6:
          v29 = L"Image48";
          break;
        case 7:
          v29 = L"Image192";
          break;
        default:
LABEL_83:
          if ( WindowsCreateStringReference(L"Unexpected UserImageKind.", 0x19u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          RoOriginateError(2147500037LL, string);
          v13 = -2147467259;
          goto LABEL_37;
      }
    }
LABEL_33:
    LODWORD(ppwsz) = 520;
    ValueW = RegGetValueW(hkey, 0, v29, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v13 = ValueW;
    if ( ValueW )
    {
      pvData[0] = 0;
      if ( ValueW > 0 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
    }
    if ( v13 >= 0 )
      goto LABEL_101;
    switch ( TileTypeForLargeSize )
    {
      case 4:
        v39 = L"Image40";
        break;
      case 6:
        v39 = L"Image96";
        break;
      case 7:
        v39 = L"Image200";
        break;
      case 8:
        v39 = L"Video200";
        break;
      default:
        goto LABEL_37;
    }
    LODWORD(ppwsz) = 520;
    v38 = RegGetValueW(hkey, 0, v39, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v13 = v38;
    if ( v38 )
    {
      pvData[0] = 0;
      if ( v38 > 0 )
        v13 = (unsigned __int16)v38 | 0x80070000;
    }
    if ( v13 >= 0 )
    {
LABEL_101:
      if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, psz, 260) )
      {
        v28 = psz;
      }
      else
      {
        v28 = pvData;
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        if ( v13 >= 0 )
          v13 = -2147467259;
      }
    }
LABEL_37:
    if ( hkey )
      RegCloseKey(hkey);
    if ( v13 >= 0 )
      return (unsigned int)SHStrDupW(v28, a4);
    return (unsigned int)v13;
  }
  v13 = -2147467259;
  if ( WindowsCreateStringReference(L"Default user tile forced by group policy.", 0x29u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  RoOriginateError(2147500037LL, string);
  if ( !(unsigned __int8)_IsVideoAccountPictureType((unsigned int)TileTypeForLargeSize) )
  {
    if ( _IsGuestAccount(a2) )
    {
      DefaultUserPicturePathBySize = SHGetDefaultGuestPicturePath(pvData, v33);
    }
    else
    {
      LargeSizeForTileType = _GetLargeSizeForTileType((unsigned int)TileTypeForLargeSize);
      DefaultUserPicturePathBySize = _GetDefaultUserPicturePathBySize(v36, LargeSizeForTileType, pvData, v37);
    }
    v13 = DefaultUserPicturePathBySize;
    if ( DefaultUserPicturePathBySize >= 0 )
    {
      v28 = pvData;
      return (unsigned int)SHStrDupW(v28, a4);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp-8+arg_0], rbx
0x180014bd5  mov     [rsp-8+arg_10], rsi
0x180014bda  push    rbp
0x180014bdb  push    rdi
0x180014bdc  push    r12
0x180014bde  push    r14
0x180014be0  push    r15
0x180014be2  lea     rbp, [rsp-5C0h]
0x180014bea  sub     rsp, 6C0h
0x180014bf1  mov     rax, cs:__security_cookie
0x180014bf8  xor     rax, rsp
0x180014bfb  mov     [rbp+5E0h+var_30], rax
0x180014c02  mov     r15, r9
0x180014c05  mov     r14, rdx
0x180014c08  xor     r12d, r12d
0x180014c0b  mov     [r9], r12
0x180014c0e  mov     ecx, r8d
0x180014c11  call    ?_GetTileTypeForLargeSize@@YA?AW4USER_TILE_TYPE@@I@Z; _GetTileTypeForLargeSize(uint)
0x180014c16  mov     esi, eax
0x180014c18  mov     [r15], r12
0x180014c1b  lea     rcx, POLID_UseDefaultTile
0x180014c22  call    cs:__imp_SHWindowsPolicy
0x180014c28  test    eax, eax
0x180014c2a  jnz     loc_180015175
0x180014c30  cmp     esi, 3
0x180014c33  jz      loc_180015175
0x180014c39  mov     [rsp+6E0h+hkey], r12
0x180014c3e  mov     [rsp+6E0h+lpSubKey], r12
0x180014c43  mov     edi, 7FFFFFFEh
0x180014c48  mov     eax, edi
0x180014c4a  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180014c51  mov     r8d, 104h
0x180014c57  lea     r9, [rbp+5E0h+var_450]
0x180014c5e  test    rax, rax
0x180014c61  jz      short loc_180014C80
0x180014c63  movzx   edx, word ptr [rcx]
0x180014c66  test    dx, dx
0x180014c69  jz      short loc_180014C80
0x180014c6b  add     rcx, 2
0x180014c6f  mov     [r9], dx
0x180014c73  add     r9, 2
0x180014c77  dec     rax
0x180014c7a  sub     r8, 1
0x180014c7e  jnz     short loc_180014C5E
0x180014c80  mov     rax, r8
0x180014c83  neg     rax
0x180014c86  sbb     ebx, ebx
0x180014c88  not     ebx
0x180014c8a  and     ebx, 8007007Ah
0x180014c90  lea     rdx, [r9-2]
0x180014c94  test    r8, r8
0x180014c97  cmovnz  rdx, r9
0x180014c9b  mov     [rdx], r12w
0x180014c9f  jz      loc_180014DB1
0x180014ca5  mov     [rsp+6E0h+ppwsz], r12
0x180014caa  test    r14, r14
0x180014cad  jz      loc_180014EDB
0x180014cb3  lea     rdx, [rsp+6E0h+ppwsz]; ppwsz
0x180014cb8  mov     rcx, r14; psz
0x180014cbb  call    cs:__imp_SHStrDupW
0x180014cc1  mov     ebx, eax
0x180014cc3  test    eax, eax
0x180014cc5  js      loc_180014D6E
0x180014ccb  mov     r9d, 104h
0x180014cd1  mov     edx, r9d
0x180014cd4  lea     rax, [rbp+5E0h+var_450]
0x180014cdb  cmp     [rax], r12w
0x180014cdf  jz      short loc_180014CEB
0x180014ce1  add     rax, 2
0x180014ce5  sub     rdx, 1
0x180014ce9  jnz     short loc_180014CDB
0x180014ceb  mov     rax, rdx
0x180014cee  neg     rax
0x180014cf1  sbb     ebx, ebx
0x180014cf3  not     ebx
0x180014cf5  and     ebx, 80070057h
0x180014cfb  mov     rax, rdx
0x180014cfe  mov     rcx, r9
0x180014d01  sub     rcx, rdx
0x180014d04  neg     rax
0x180014d07  sbb     r8, r8
0x180014d0a  and     r8, rcx
0x180014d0d  test    rdx, rdx
0x180014d10  jz      short loc_180014D6E
0x180014d12  mov     rax, [rsp+6E0h+ppwsz]
0x180014d17  mov     rdx, r9
0x180014d1a  sub     rdx, r8
0x180014d1d  lea     r8, [rbp+r8*2+5E0h+var_450]
0x180014d25  jz      short loc_180014D49
0x180014d27  test    rdi, rdi
0x180014d2a  jz      short loc_180014D49
0x180014d2c  movzx   ecx, word ptr [rax]
0x180014d2f  test    cx, cx
0x180014d32  jz      short loc_180014D49
0x180014d34  add     rax, 2
0x180014d38  mov     [r8], cx
0x180014d3c  add     r8, 2
0x180014d40  dec     rdi
0x180014d43  sub     rdx, 1
0x180014d47  jnz     short loc_180014D27
0x180014d49  mov     rax, rdx
0x180014d4c  neg     rax
0x180014d4f  sbb     ebx, ebx
0x180014d51  not     ebx
0x180014d53  and     ebx, 8007007Ah
0x180014d59  lea     rcx, [r8-2]
0x180014d5d  test    rdx, rdx
0x180014d60  cmovnz  rcx, r8
0x180014d64  mov     [rcx], r12w
0x180014d68  jnz     loc_180014EF5
0x180014d6e  mov     rcx, [rsp+6E0h+ppwsz]; pv
0x180014d73  mov     [rsp+6E0h+ppwsz], r12
0x180014d78  call    cs:__imp_CoTaskMemFree
0x180014d7e  test    ebx, ebx
0x180014d80  js      short loc_180014DB1
0x180014d82  lea     rax, [rsp+6E0h+hkey]
0x180014d87  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180014d8c  mov     r9d, 20119h; samDesired
0x180014d92  xor     r8d, r8d; ulOptions
0x180014d95  mov     rdx, [rsp+6E0h+lpSubKey]; lpSubKey
0x180014d9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014da1  call    cs:__imp_RegOpenKeyExW
0x180014da7  mov     ebx, eax
0x180014da9  test    eax, eax
0x180014dab  jg      loc_180014EA5
0x180014db1  mov     rcx, [rsp+6E0h+lpSubKey]; pv
0x180014db6  mov     [rsp+6E0h+lpSubKey], r12
0x180014dbb  call    cs:__imp_CoTaskMemFree
0x180014dc1  test    ebx, ebx
0x180014dc3  js      loc_180014E78
0x180014dc9  mov     r14, r12
0x180014dcc  cmp     esi, 8
0x180014dcf  jz      loc_180014ECF
0x180014dd5  jg      loc_180015076
0x180014ddb  mov     ecx, esi
0x180014ddd  test    esi, esi
0x180014ddf  jnz     loc_18001500C
0x180014de5  lea     rdi, aImage96; "Image96"
0x180014dec  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x180014df4  lea     rax, [rsp+6E0h+ppwsz]
0x180014df9  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180014dfe  lea     rax, [rbp+5E0h+var_660]
0x180014e02  mov     [rsp+6E0h+pvData], rax; pvData
0x180014e07  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180014e0c  mov     r9d, 2; dwFlags
0x180014e12  mov     r8, rdi; lpValue
0x180014e15  xor     edx, edx; lpSubKey
0x180014e17  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180014e1c  call    cs:__imp_RegGetValueW
0x180014e22  mov     ebx, eax
0x180014e24  test    eax, eax
0x180014e26  jnz     loc_180014F0E
0x180014e2c  test    ebx, ebx
0x180014e2e  js      loc_180014FE8
0x180014e34  mov     r8d, 104h
0x180014e3a  lea     rdx, [rbp+5E0h+psz]
0x180014e41  lea     rcx, [rbp+5E0h+var_660]
0x180014e45  call    cs:__imp_SHExpandEnvironmentStringsW
0x180014e4b  test    eax, eax
0x180014e4d  jz      short loc_180014EB3
0x180014e4f  lea     r14, [rbp+5E0h+psz]
0x180014e56  mov     rcx, [rsp+6E0h+hkey]; hKey
0x180014e5b  test    rcx, rcx
0x180014e5e  jz      short loc_180014E66
0x180014e60  call    cs:__imp_RegCloseKey
0x180014e66  test    ebx, ebx
0x180014e68  js      short loc_180014E78
0x180014e6a  mov     rdx, r15; ppwsz
0x180014e6d  mov     rcx, r14; psz
0x180014e70  call    cs:__imp_SHStrDupW
0x180014e76  mov     ebx, eax
0x180014e78  mov     eax, ebx
0x180014e7a  mov     rcx, [rbp+5E0h+var_30]
0x180014e81  xor     rcx, rsp; StackCookie
0x180014e84  call    __security_check_cookie
0x180014e89  lea     r11, [rsp+6E0h+var_20]
0x180014e91  mov     rbx, [r11+30h]
0x180014e95  mov     rsi, [r11+40h]
0x180014e99  mov     rsp, r11
0x180014e9c  pop     r15
0x180014e9e  pop     r14
0x180014ea0  pop     r12
0x180014ea2  pop     rdi
0x180014ea3  pop     rbp
0x180014ea4  retn
0x180014ea5  movzx   ebx, ax
0x180014ea8  or      ebx, 80070000h
0x180014eae  jmp     loc_180014DB1
0x180014eb3  lea     r14, [rbp+5E0h+var_660]
0x180014eb7  call    cs:__imp_GetLastError
0x180014ebd  mov     ebx, eax
0x180014ebf  test    eax, eax
0x180014ec1  jg      short loc_180014EEA
0x180014ec3  mov     edi, 80004005h
0x180014ec8  test    ebx, ebx
0x180014eca  cmovns  ebx, edi
0x180014ecd  jmp     short loc_180014E56
0x180014ecf  lea     rdi, aVideo192; "Video192"
0x180014ed6  jmp     loc_180014DEC
0x180014edb  lea     rcx, [rsp+6E0h+ppwsz]; ppwsz
0x180014ee0  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180014ee5  jmp     loc_180014CC1
0x180014eea  movzx   ebx, ax
0x180014eed  or      ebx, 80070000h
0x180014ef3  jmp     short loc_180014EC3
0x180014ef5  lea     rdx, [rsp+6E0h+lpSubKey]; ppwsz
0x180014efa  lea     rcx, [rbp+5E0h+var_450]; psz
0x180014f01  call    cs:__imp_SHStrDupW
0x180014f07  mov     ebx, eax
0x180014f09  jmp     loc_180014D6E
0x180014f0e  mov     [rbp+5E0h+var_660], r12w
0x180014f13  jle     loc_180014E2C
0x180014f19  movzx   ebx, ax
0x180014f1c  or      ebx, 80070000h
0x180014f22  jmp     loc_180014E2C
0x180014f27  mov     rdx, [rsp+6E0h+string]
0x180014f2c  mov     ecx, edi
0x180014f2e  call    cs:__imp_RoOriginateError
0x180014f34  mov     ecx, esi
0x180014f36  call    ?_IsVideoAccountPictureType@@YA_NW4USER_TILE_TYPE@@@Z; _IsVideoAccountPictureType(USER_TILE_TYPE)
0x180014f3b  test    al, al
0x180014f3d  jnz     loc_180014E78
0x180014f43  mov     rcx, r14; unsigned __int16 *
0x180014f46  call    ?_IsGuestAccount@@YA_NPEBG@Z; _IsGuestAccount(ushort const *)
0x180014f4b  test    al, al
0x180014f4d  jz      short loc_180014F6B
0x180014f4f  lea     rcx, [rbp+5E0h+var_660]; unsigned __int16 *
0x180014f53  call    ?SHGetDefaultGuestPicturePath@@YAJPEAGK@Z; SHGetDefaultGuestPicturePath(ushort *,ulong)
0x180014f58  mov     ebx, eax
0x180014f5a  test    eax, eax
0x180014f5c  js      loc_180014E78
0x180014f62  lea     r14, [rbp+5E0h+var_660]
0x180014f66  jmp     loc_180014E6A
0x180014f6b  mov     ecx, esi
0x180014f6d  call    ?_GetLargeSizeForTileType@@YAIW4USER_TILE_TYPE@@@Z; _GetLargeSizeForTileType(USER_TILE_TYPE)
0x180014f72  lea     r8, [rbp+5E0h+var_660]; unsigned __int16 *
0x180014f76  mov     edx, eax; unsigned int
0x180014f78  call    ?_GetDefaultUserPicturePathBySize@@YAJ_NIPEAGK@Z; _GetDefaultUserPicturePathBySize(bool,uint,ushort *,ulong)
0x180014f7d  jmp     short loc_180014F58
0x180014f7f  sub     esi, 4
0x180014f82  jz      short loc_180014FF1
0x180014f84  sub     esi, 2
0x180014f87  jz      loc_180015169
0x180014f8d  sub     esi, 1
0x180014f90  jz      loc_18001515D
0x180014f96  cmp     esi, 1
0x180014f99  jz      loc_180015151
0x180014f9f  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x180014fa7  lea     rax, [rsp+6E0h+ppwsz]
0x180014fac  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180014fb1  lea     rax, [rbp+5E0h+var_660]
0x180014fb5  mov     [rsp+6E0h+pvData], rax; pvData
0x180014fba  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180014fbf  mov     r9d, 2; dwFlags
0x180014fc5  mov     r8, rdi; lpValue
0x180014fc8  xor     edx, edx; lpSubKey
0x180014fca  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180014fcf  call    cs:__imp_RegGetValueW
0x180014fd5  mov     ebx, eax
0x180014fd7  test    eax, eax
0x180014fd9  jnz     short loc_180014FFA
0x180014fdb  test    ebx, ebx
0x180014fdd  js      loc_180014E56
0x180014fe3  jmp     loc_180014E34
0x180014fe8  cmp     esi, 4
0x180014feb  jnz     loc_180015139
0x180014ff1  lea     rdi, aImage40; "Image40"
0x180014ff8  jmp     short loc_180014F9F
0x180014ffa  mov     [rbp+5E0h+var_660], r12w
0x180014fff  jle     short loc_180014FDB
0x180015001  movzx   ebx, ax
0x180015004  or      ebx, 80070000h
0x18001500a  jmp     short loc_180014FDB
0x18001500c  sub     ecx, 1
0x18001500f  jz      short loc_18001506A
0x180015011  sub     ecx, 1
0x180015014  jz      short loc_18001505E
0x180015016  sub     ecx, 2
0x180015019  jz      short loc_180015052
0x18001501b  sub     ecx, 1
0x18001501e  jz      short loc_180015046
0x180015020  sub     ecx, 1
0x180015023  jz      short loc_18001503A
0x180015025  cmp     ecx, 1
0x180015028  jnz     loc_1800150AE
0x18001502e  lea     rdi, aImage192; "Image192"
0x180015035  jmp     loc_180014DEC
0x18001503a  lea     rdi, aImage48; "Image48"
0x180015041  jmp     loc_180014DEC
0x180015046  lea     rdi, aImage40; "Image40"
0x18001504d  jmp     loc_180014DEC
0x180015052  lea     rdi, aImage32; "Image32"
0x180015059  jmp     loc_180014DEC
0x18001505e  lea     rdi, aVideo448; "Video448"
0x180015065  jmp     loc_180014DEC
0x18001506a  lea     rdi, aImage448; "Image448"
0x180015071  jmp     loc_180014DEC
0x180015076  mov     ecx, esi
0x180015078  sub     ecx, 9
0x18001507b  jz      loc_18001512D
  ... truncated ...
```
