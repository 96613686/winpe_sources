# CUserTileStore::GetDynamicPathBySize(ushort const *,uint,ushort * *)

- ea: `0x180013690`
- end: `0x180013c01`
- name: `?GetDynamicPathBySize@CUserTileStore@@UEAAJPEBGIPEAPEAG@Z`
- size: `1393`
- prototype: `int(CUserTileStore *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180013690`
- `0x180013c08`
- `0x180014a10`
- `0x18001527c`
- `0x18003a68c`
- `0x180047a54`
- `0x180048540`
- `0x18004908c`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013994`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013b74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013994`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013876`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013876`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013a18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013aba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013a18`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013aba`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180013aeb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180013aeb`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013774`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001383b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013bcc`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013774`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18001383b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180013bcc`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800136df`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800136df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001397b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001397b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001384d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013895`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001384d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013895`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800139a7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013b82`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800139a7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013b82`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserTileStore::GetDynamicPathBySize(
        CUserTileStore *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  int TileTypeForDynamicSize; // esi
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
  LPWSTR v27; // rcx
  unsigned __int16 *v28; // r14
  const WCHAR *v29; // rdi
  LSTATUS ValueW; // eax
  const WCHAR *v31; // rdi
  LSTATUS v32; // eax
  signed int LastError; // eax
  unsigned int v34; // edx
  int DefaultUserPicturePathBySize; // eax
  unsigned int LargeSizeForTileType; // eax
  bool v37; // cl
  unsigned int v38; // r9d
  LPWSTR ppwsz; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v41; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR psz[264]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v47[528]; // [rsp+4A0h] [rbp+3A0h] BYREF

  TileTypeForDynamicSize = _GetTileTypeForDynamicSize(a3);
  *a4 = 0;
  if ( !(unsigned int)SHWindowsPolicy(POLID_UseDefaultTile) && TileTypeForDynamicSize != 3 )
  {
    hkey = 0;
    v41 = 0;
    v7 = 2147483646;
    v8 = 2147483646;
    v9 = L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture\\Users\\";
    v10 = 260;
    v11 = psz;
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
        v17 = psz;
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
          v22 = &psz[v18];
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
            v13 = SHStrDupW(psz, &v41);
        }
      }
      v25 = ppwsz;
      ppwsz = 0;
      CoTaskMemFree(v25);
      if ( v13 >= 0 )
      {
        v26 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v41, 0, 0x20119u, &hkey);
        v13 = v26;
        if ( v26 > 0 )
          v13 = (unsigned __int16)v26 | 0x80070000;
      }
    }
    v27 = v41;
    v41 = 0;
    CoTaskMemFree(v27);
    if ( v13 < 0 )
      return (unsigned int)v13;
    v28 = 0;
    if ( TileTypeForDynamicSize == 8 )
    {
      v29 = L"Video192";
    }
    else if ( TileTypeForDynamicSize > 8 )
    {
      switch ( TileTypeForDynamicSize )
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
          goto LABEL_53;
      }
    }
    else if ( TileTypeForDynamicSize )
    {
      switch ( TileTypeForDynamicSize )
      {
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
LABEL_53:
          if ( WindowsCreateStringReference(L"Unexpected UserImageKind.", 0x19u, &hstringHeader, &string) < 0 )
            RaiseException(0xC000000D, 1u, 0, 0);
          RoOriginateError(2147500037LL, string);
          v13 = -2147467259;
          goto LABEL_84;
      }
    }
    else
    {
      v29 = L"Image96";
    }
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
      goto LABEL_100;
    switch ( TileTypeForDynamicSize )
    {
      case 4:
        v31 = L"Image40";
        break;
      case 6:
        v31 = L"Image96";
        break;
      case 7:
        v31 = L"Image200";
        break;
      case 8:
        v31 = L"Video200";
        break;
      default:
        goto LABEL_84;
    }
    LODWORD(ppwsz) = 520;
    v32 = RegGetValueW(hkey, 0, v31, 2u, 0, pvData, (LPDWORD)&ppwsz);
    v13 = v32;
    if ( v32 )
    {
      pvData[0] = 0;
      if ( v32 > 0 )
        v13 = (unsigned __int16)v32 | 0x80070000;
    }
    if ( v13 >= 0 )
    {
LABEL_100:
      if ( (unsigned int)SHExpandEnvironmentStringsW(pvData, v47, 260) )
      {
        v28 = (unsigned __int16 *)v47;
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
LABEL_84:
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
  if ( !(unsigned __int8)_IsVideoAccountPictureType((unsigned int)TileTypeForDynamicSize) )
  {
    if ( _IsGuestAccount(a2) )
    {
      DefaultUserPicturePathBySize = SHGetDefaultGuestPicturePath(pvData, v34);
    }
    else
    {
      LargeSizeForTileType = _GetLargeSizeForTileType((unsigned int)TileTypeForDynamicSize);
      DefaultUserPicturePathBySize = _GetDefaultUserPicturePathBySize(v37, LargeSizeForTileType, pvData, v38);
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
0x180013690  mov     [rsp-8+arg_0], rbx
0x180013695  mov     [rsp-8+arg_10], rsi
0x18001369a  push    rbp
0x18001369b  push    rdi
0x18001369c  push    r12
0x18001369e  push    r14
0x1800136a0  push    r15
0x1800136a2  lea     rbp, [rsp-5C0h]
0x1800136aa  sub     rsp, 6C0h
0x1800136b1  mov     rax, cs:__security_cookie
0x1800136b8  xor     rax, rsp
0x1800136bb  mov     [rbp+5E0h+var_30], rax
0x1800136c2  mov     r15, r9
0x1800136c5  mov     r14, rdx
0x1800136c8  mov     ecx, r8d
0x1800136cb  call    ?_GetTileTypeForDynamicSize@@YA?AW4USER_TILE_TYPE@@I@Z; _GetTileTypeForDynamicSize(uint)
0x1800136d0  mov     esi, eax
0x1800136d2  xor     r12d, r12d
0x1800136d5  mov     [r15], r12
0x1800136d8  lea     rcx, POLID_UseDefaultTile
0x1800136df  call    cs:__imp_SHWindowsPolicy
0x1800136e5  test    eax, eax
0x1800136e7  jnz     loc_180013B3E
0x1800136ed  cmp     esi, 3
0x1800136f0  jz      loc_180013B3E
0x1800136f6  mov     [rsp+6E0h+hkey], r12
0x1800136fb  mov     [rsp+6E0h+var_698], r12
0x180013700  mov     edi, 7FFFFFFEh
0x180013705  mov     eax, edi
0x180013707  lea     rcx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001370e  mov     r8d, 104h
0x180013714  lea     r9, [rbp+5E0h+psz]
0x18001371b  test    rax, rax
0x18001371e  jz      short loc_18001373D
0x180013720  movzx   edx, word ptr [rcx]
0x180013723  test    dx, dx
0x180013726  jz      short loc_18001373D
0x180013728  add     rcx, 2
0x18001372c  mov     [r9], dx
0x180013730  add     r9, 2
0x180013734  dec     rax
0x180013737  sub     r8, 1
0x18001373b  jnz     short loc_18001371B
0x18001373d  mov     rax, r8
0x180013740  neg     rax
0x180013743  sbb     ebx, ebx
0x180013745  not     ebx
0x180013747  and     ebx, 8007007Ah
0x18001374d  lea     rdx, [r9-2]
0x180013751  test    r8, r8
0x180013754  cmovnz  rdx, r9
0x180013758  mov     [rdx], r12w
0x18001375c  jz      loc_18001388B
0x180013762  mov     [rsp+6E0h+ppwsz], r12
0x180013767  test    r14, r14
0x18001376a  jz      short loc_18001377C
0x18001376c  lea     rdx, [rsp+6E0h+ppwsz]; ppwsz
0x180013771  mov     rcx, r14; psz
0x180013774  call    cs:__imp_SHStrDupW
0x18001377a  jmp     short loc_180013786
0x18001377c  lea     rcx, [rsp+6E0h+ppwsz]; ppwsz
0x180013781  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x180013786  mov     ebx, eax
0x180013788  test    eax, eax
0x18001378a  js      loc_180013843
0x180013790  mov     r9d, 104h
0x180013796  mov     edx, r9d
0x180013799  lea     rax, [rbp+5E0h+psz]
0x1800137a0  cmp     [rax], r12w
0x1800137a4  jz      short loc_1800137B0
0x1800137a6  add     rax, 2
0x1800137aa  sub     rdx, 1
0x1800137ae  jnz     short loc_1800137A0
0x1800137b0  mov     rax, rdx
0x1800137b3  neg     rax
0x1800137b6  sbb     ebx, ebx
0x1800137b8  not     ebx
0x1800137ba  and     ebx, 80070057h
0x1800137c0  mov     rax, rdx
0x1800137c3  mov     rcx, r9
0x1800137c6  sub     rcx, rdx
0x1800137c9  neg     rax
0x1800137cc  sbb     r8, r8
0x1800137cf  and     r8, rcx
0x1800137d2  test    rdx, rdx
0x1800137d5  jz      short loc_180013843
0x1800137d7  mov     rax, [rsp+6E0h+ppwsz]
0x1800137dc  mov     rdx, r9
0x1800137df  sub     rdx, r8
0x1800137e2  lea     r8, [rbp+r8*2+5E0h+psz]
0x1800137ea  jz      short loc_18001380E
0x1800137ec  test    rdi, rdi
0x1800137ef  jz      short loc_18001380E
0x1800137f1  movzx   ecx, word ptr [rax]
0x1800137f4  test    cx, cx
0x1800137f7  jz      short loc_18001380E
0x1800137f9  add     rax, 2
0x1800137fd  mov     [r8], cx
0x180013801  add     r8, 2
0x180013805  dec     rdi
0x180013808  sub     rdx, 1
0x18001380c  jnz     short loc_1800137EC
0x18001380e  mov     rax, rdx
0x180013811  neg     rax
0x180013814  sbb     ebx, ebx
0x180013816  not     ebx
0x180013818  and     ebx, 8007007Ah
0x18001381e  lea     rcx, [r8-2]
0x180013822  test    rdx, rdx
0x180013825  cmovnz  rcx, r8
0x180013829  mov     [rcx], r12w
0x18001382d  jz      short loc_180013843
0x18001382f  lea     rdx, [rsp+6E0h+var_698]; ppwsz
0x180013834  lea     rcx, [rbp+5E0h+psz]; psz
0x18001383b  call    cs:__imp_SHStrDupW
0x180013841  mov     ebx, eax
0x180013843  mov     rcx, [rsp+6E0h+ppwsz]; pv
0x180013848  mov     [rsp+6E0h+ppwsz], r12
0x18001384d  call    cs:__imp_CoTaskMemFree
0x180013853  test    ebx, ebx
0x180013855  js      short loc_18001388B
0x180013857  lea     rax, [rsp+6E0h+hkey]
0x18001385c  mov     [rsp+6E0h+phkResult], rax; phkResult
0x180013861  mov     r9d, 20119h; samDesired
0x180013867  xor     r8d, r8d; ulOptions
0x18001386a  mov     rdx, [rsp+6E0h+var_698]; lpSubKey
0x18001386f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013876  call    cs:__imp_RegOpenKeyExW
0x18001387c  mov     ebx, eax
0x18001387e  test    eax, eax
0x180013880  jle     short loc_18001388B
0x180013882  movzx   ebx, ax
0x180013885  or      ebx, 80070000h
0x18001388b  mov     rcx, [rsp+6E0h+var_698]; pv
0x180013890  mov     [rsp+6E0h+var_698], r12
0x180013895  call    cs:__imp_CoTaskMemFree
0x18001389b  test    ebx, ebx
0x18001389d  js      loc_180013BD4
0x1800138a3  mov     r14, r12
0x1800138a6  cmp     esi, 8
0x1800138a9  jz      loc_180013931
0x1800138af  jg      loc_18001393D
0x1800138b5  mov     ecx, esi
0x1800138b7  test    esi, esi
0x1800138b9  jz      short loc_180013925
0x1800138bb  sub     ecx, 1
0x1800138be  jz      short loc_180013919
0x1800138c0  sub     ecx, 1
0x1800138c3  jz      short loc_18001390D
0x1800138c5  sub     ecx, 2
0x1800138c8  jz      short loc_180013901
0x1800138ca  sub     ecx, 1
0x1800138cd  jz      short loc_1800138F5
0x1800138cf  sub     ecx, 1
0x1800138d2  jz      short loc_1800138E9
0x1800138d4  cmp     ecx, 1
0x1800138d7  jnz     loc_180013965
0x1800138dd  lea     rdi, aImage192; "Image192"
0x1800138e4  jmp     loc_1800139E8
0x1800138e9  lea     rdi, aImage48; "Image48"
0x1800138f0  jmp     loc_1800139E8
0x1800138f5  lea     rdi, aImage40; "Image40"
0x1800138fc  jmp     loc_1800139E8
0x180013901  lea     rdi, aImage32; "Image32"
0x180013908  jmp     loc_1800139E8
0x18001390d  lea     rdi, aVideo448; "Video448"
0x180013914  jmp     loc_1800139E8
0x180013919  lea     rdi, aImage448; "Image448"
0x180013920  jmp     loc_1800139E8
0x180013925  lea     rdi, aImage96; "Image96"
0x18001392c  jmp     loc_1800139E8
0x180013931  lea     rdi, aVideo192; "Video192"
0x180013938  jmp     loc_1800139E8
0x18001393d  mov     ecx, esi
0x18001393f  sub     ecx, 9
0x180013942  jz      loc_1800139E1
0x180013948  sub     ecx, 1
0x18001394b  jz      loc_1800139D8
0x180013951  sub     ecx, 1
0x180013954  jz      short loc_1800139CF
0x180013956  sub     ecx, 1
0x180013959  jz      short loc_1800139C6
0x18001395b  sub     ecx, 1
0x18001395e  jz      short loc_1800139BD
0x180013960  cmp     ecx, 1
0x180013963  jz      short loc_1800139B4
0x180013965  lea     r9, [rsp+6E0h+string]; string
0x18001396a  lea     r8, [rsp+6E0h+hstringHeader]; hstringHeader
0x18001396f  mov     edx, 19h; length
0x180013974  lea     rcx, aUnexpectedUser; "Unexpected UserImageKind."
0x18001397b  call    cs:__imp_WindowsCreateStringReference
0x180013981  test    eax, eax
0x180013983  jns     short loc_18001399B
0x180013985  xor     r9d, r9d; lpArguments
0x180013988  xor     r8d, r8d; nNumberOfArguments
0x18001398b  lea     edx, [r9+1]; dwExceptionFlags
0x18001398f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180013994  call    cs:__imp_RaiseException
0x18001399a  nop
0x18001399b  mov     rdx, [rsp+6E0h+string]
0x1800139a0  mov     edi, 80004005h
0x1800139a5  mov     ecx, edi
0x1800139a7  call    cs:__imp_RoOriginateError
0x1800139ad  mov     ebx, edi
0x1800139af  jmp     loc_180013B21
0x1800139b4  lea     rdi, aImage1080; "Image1080"
0x1800139bb  jmp     short loc_1800139E8
0x1800139bd  lea     rdi, aImage424; "Image424"
0x1800139c4  jmp     short loc_1800139E8
0x1800139c6  lea     rdi, aImage208; "Image208"
0x1800139cd  jmp     short loc_1800139E8
0x1800139cf  lea     rdi, aImage64; "Image64"
0x1800139d6  jmp     short loc_1800139E8
0x1800139d8  lea     rdi, aVideo240; "Video240"
0x1800139df  jmp     short loc_1800139E8
0x1800139e1  lea     rdi, aImage240; "Image240"
0x1800139e8  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x1800139f0  lea     rax, [rsp+6E0h+ppwsz]
0x1800139f5  mov     [rsp+6E0h+pcbData], rax; pcbData
0x1800139fa  lea     rax, [rbp+5E0h+var_660]
0x1800139fe  mov     [rsp+6E0h+pvData], rax; pvData
0x180013a03  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180013a08  mov     r9d, 2; dwFlags
0x180013a0e  mov     r8, rdi; lpValue
0x180013a11  xor     edx, edx; lpSubKey
0x180013a13  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180013a18  call    cs:__imp_RegGetValueW
0x180013a1e  mov     ebx, eax
0x180013a20  test    eax, eax
0x180013a22  jz      short loc_180013A34
0x180013a24  mov     [rbp+5E0h+var_660], r12w
0x180013a29  jle     short loc_180013A34
0x180013a2b  movzx   ebx, ax
0x180013a2e  or      ebx, 80070000h
0x180013a34  test    ebx, ebx
0x180013a36  jns     loc_180013ADA
0x180013a3c  cmp     esi, 4
0x180013a3f  jz      short loc_180013A83
0x180013a41  cmp     esi, 6
0x180013a44  jz      short loc_180013A7A
0x180013a46  cmp     esi, 7
0x180013a49  jz      short loc_180013A71
0x180013a4b  cmp     esi, 8
0x180013a4e  jnz     loc_180013B21
0x180013a54  sub     esi, 4
0x180013a57  jz      short loc_180013A83
0x180013a59  sub     esi, 2
0x180013a5c  jz      short loc_180013A7A
0x180013a5e  sub     esi, 1
0x180013a61  jz      short loc_180013A71
0x180013a63  cmp     esi, 1
0x180013a66  jnz     short loc_180013A8A
0x180013a68  lea     rdi, aVideo200; "Video200"
0x180013a6f  jmp     short loc_180013A8A
0x180013a71  lea     rdi, aImage200; "Image200"
0x180013a78  jmp     short loc_180013A8A
0x180013a7a  lea     rdi, aImage96; "Image96"
0x180013a81  jmp     short loc_180013A8A
0x180013a83  lea     rdi, aImage40; "Image40"
0x180013a8a  mov     dword ptr [rsp+6E0h+ppwsz], 208h
0x180013a92  lea     rax, [rsp+6E0h+ppwsz]
0x180013a97  mov     [rsp+6E0h+pcbData], rax; pcbData
0x180013a9c  lea     rax, [rbp+5E0h+var_660]
0x180013aa0  mov     [rsp+6E0h+pvData], rax; pvData
0x180013aa5  mov     [rsp+6E0h+phkResult], r12; pdwType
0x180013aaa  mov     r9d, 2; dwFlags
0x180013ab0  mov     r8, rdi; lpValue
0x180013ab3  xor     edx, edx; lpSubKey
0x180013ab5  mov     rcx, [rsp+6E0h+hkey]; hkey
0x180013aba  call    cs:__imp_RegGetValueW
0x180013ac0  mov     ebx, eax
0x180013ac2  test    eax, eax
0x180013ac4  jz      short loc_180013AD6
0x180013ac6  mov     [rbp+5E0h+var_660], r12w
0x180013acb  jle     short loc_180013AD6
0x180013acd  movzx   ebx, ax
0x180013ad0  or      ebx, 80070000h
0x180013ad6  test    ebx, ebx
0x180013ad8  js      short loc_180013B21
0x180013ada  mov     r8d, 104h
0x180013ae0  lea     rdx, [rbp+5E0h+var_240]
0x180013ae7  lea     rcx, [rbp+5E0h+var_660]
0x180013aeb  call    cs:__imp_SHExpandEnvironmentStringsW
0x180013af1  test    eax, eax
0x180013af3  jz      short loc_180013AFE
0x180013af5  lea     r14, [rbp+5E0h+var_240]
0x180013afc  jmp     short loc_180013B21
0x180013afe  lea     r14, [rbp+5E0h+var_660]
0x180013b02  call    cs:__imp_GetLastError
0x180013b08  mov     ebx, eax
0x180013b0a  test    eax, eax
0x180013b0c  jle     short loc_180013B17
0x180013b0e  movzx   ebx, ax
0x180013b11  or      ebx, 80070000h
0x180013b17  mov     edi, 80004005h
0x180013b1c  test    ebx, ebx
0x180013b1e  cmovns  ebx, edi
0x180013b21  mov     rcx, [rsp+6E0h+hkey]; hKey
0x180013b26  test    rcx, rcx
0x180013b29  jz      short loc_180013B31
  ... truncated ...
```
