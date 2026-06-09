# GetTypeInfoOfIIDFwd(_GUID const &,ITypeInfo * *,int)

- ea: `0x180012020`
- end: `0x18001274a`
- name: `?GetTypeInfoOfIIDFwd@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@H@Z`
- size: `1834`
- prototype: `__int64 __fastcall(const struct _GUID *, struct ITypeInfo **, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011cd4`
- `0x180011d30`
- `0x180012020`

## callees

- `0x180012020`
- `0x180012750`
- `0x1800128fc`
- `0x180012ac8`
- `0x180012b70`
- `0x180014f04`
- `0x1800161b8`
- `0x18004d900`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180012101`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800121c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180012101`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800121c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800120d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012178`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800121a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012567`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800120d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012178`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800121a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180012567`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012280`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001229c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001251d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012539`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012280`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001229c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001251d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180012539`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012265`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180012265`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012385`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800125ae`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001230a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180012385`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800125ae`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001214f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012227`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012426`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001214f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012227`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180012426`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001215c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001215c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800124d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012337`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800123e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800125d4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800120ed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800121b3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800120ed`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800121b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001261a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001261a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800126e2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800126e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001263a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800124dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001263a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001273c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001273c`

## string_xrefs

- `0x180012687`: `mincore\com\oleaut32\dispatch\ups.cpp`
- `0x180012717`: `mincore\com\oleaut32\dispatch\ups.cpp`

## pseudocode

```c
__int64 __fastcall GetTypeInfoOfIIDFwd(const struct _GUID *a1, struct ITypeInfo **a2, int a3)
{
  struct ITypeInfo **v4; // r14
  unsigned __int16 v6; // si
  int v7; // eax
  int v8; // ebx
  LSTATUS ValueW; // ebx
  int v10; // r13d
  unsigned __int16 v11; // r15
  int v12; // edi
  unsigned __int16 v13; // ax
  DWORD v14; // r14d
  DWORD i; // edx
  HKEY v16; // rcx
  DWORD j; // edi
  int v18; // eax
  const OLECHAR *StringRawBuffer; // rcx
  HRESULT v20; // eax
  ITypeLib *v21; // rdi
  unsigned __int16 v23; // di
  unsigned __int16 v24; // ax
  HRESULT Instance; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, const struct _GUID *, HSTRING *); // rbx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v33; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h]
  HKEY hkey; // [rsp+60h] [rbp-A0h]
  DWORD v38; // [rsp+68h] [rbp-98h] BYREF
  HKEY v39; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY v41; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  ITypeLib *pptlib; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *EndPtr; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v45; // [rsp+A0h] [rbp-60h] BYREF
  struct ITypeInfo *v46; // [rsp+A8h] [rbp-58h] BYREF
  struct ITypeInfo **v47; // [rsp+B0h] [rbp-50h]
  GUID rguid; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name[16]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SubKey[20]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR v51[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE pvData[4]; // [rsp+120h] [rbp+20h] BYREF
  OLECHAR sz[62]; // [rsp+124h] [rbp+24h] BYREF
  wchar_t Data[24]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR v55[10]; // [rsp+1D0h] [rbp+D0h] BYREF
  OLECHAR v56[54]; // [rsp+1E4h] [rbp+E4h] BYREF
  OLECHAR szFile[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v47 = a2;
  v4 = a2;
  if ( a3 < 16 )
  {
    v6 = 0;
    pcbData = 0;
    v45 = 0;
    v33 = 0;
    cchName = 0;
    v46 = 0;
    hKey = 0;
    phkResult = 0;
    v39 = 0;
    v41 = 0;
    string = 0;
    v7 = MapIIDToFusionTypeInfo(a1, a2);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( v7 != 1 )
        goto LABEL_61;
      pptlib = 0;
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v39 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v41 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      _o_wcscpy_s(v51, 71, L"Interface\\");
      StringFromGUID2(a1, sz, 39);
      _o_wcscat_s(v51, 71, L"\\Forward");
      pcbData = 520;
      hkey = 0;
      if ( (unsigned int)OpenClassesRootKeyExW(v51)
        || (ValueW = RegGetValueW(hkey, 0, 0, 6u, 0, szFile, &pcbData), RegCloseKey(hkey), ValueW)
        || (rguid = 0, CLSIDFromString(szFile, &rguid))
        || (unsigned int)GetTypeInfoOfIIDFwd(&rguid, v4, a3 + 1) )
      {
        _o_wcscpy_s(v51, 71, L"TypeLib\\");
        v38 = 40;
        hkey = 0;
        _o_wcscpy_s(v55, 58, L"Interface\\");
        StringFromGUID2(a1, v56, 39);
        _o_wcscat_s(v55, 58, L"\\TypeLib");
        if ( (unsigned int)OpenClassesRootKeyExW(v55) )
          goto LABEL_54;
        v8 = -2147319779;
        v38 *= 2;
        v10 = 0;
        v11 = 0;
        v12 = -2147319779;
        if ( !RegGetValueW(hkey, 0, 0, 6u, 0, pvData, &v38) )
        {
          EndPtr = 0;
          cbData[0] = 40;
          if ( !RegQueryValueExW(hkey, L"Version", 0, 0, (LPBYTE)Data, cbData) )
          {
            v13 = wcstoul(Data, &EndPtr, 16);
            if ( *EndPtr == 46 )
            {
              v6 = v13;
              v11 = wcstoul(EndPtr + 1, 0, 16);
              v10 = 1;
            }
          }
          v12 = 0;
        }
        RegCloseKey(hkey);
        if ( v12 == -2147319779 )
        {
LABEL_54:
          *(_QWORD *)cbData = 0;
          Instance = CoCreateInstance(
                       &GUID_00000346_0000_0000_c000_000000000046,
                       0,
                       1u,
                       &GUID_419c4e35_36bc_4780_845d_a05c51d9f770,
                       (LPVOID *)cbData);
          v8 = Instance;
          if ( Instance >= 0 )
          {
            v26 = *(_QWORD *)cbData;
            v27 = *(__int64 (__fastcall **)(__int64, const struct _GUID *, HSTRING *))(**(_QWORD **)cbData + 40LL);
            WindowsDeleteString(string);
            string = 0;
            v28 = v27(v26, a1, &string);
            v8 = v28;
            if ( v28 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x84E,
                (unsigned int)"mincore\\com\\oleaut32\\dispatch\\ups.cpp",
                (const char *)(unsigned int)v28,
                pdwType);
              v30 = *(_QWORD *)cbData;
              if ( *(_QWORD *)cbData )
              {
                *(_QWORD *)cbData = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
              goto LABEL_41;
            }
            v29 = *(_QWORD *)cbData;
            if ( *(_QWORD *)cbData )
            {
              *(_QWORD *)cbData = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
LABEL_26:
            if ( string )
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            else
              StringRawBuffer = szFile;
            v20 = LoadTypeLibEx(StringRawBuffer, REGKIND_DEFAULT, &pptlib);
            v21 = pptlib;
            v8 = v20;
            if ( v20 >= 0 )
            {
              v8 = ((__int64 (__fastcall *)(ITypeLib *, const struct _GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                     pptlib,
                     a1,
                     &v46);
              if ( v8 >= 0 )
              {
                v8 = 0;
                *v4 = v46;
              }
            }
            if ( v21 )
              ((void (__fastcall *)(ITypeLib *))v21->lpVtbl->Release)(v21);
            goto LABEL_33;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x84C,
            (unsigned int)"mincore\\com\\oleaut32\\dispatch\\ups.cpp",
            (const char *)(unsigned int)Instance,
            pdwType);
          Microsoft::WRL::ComPtr<ITypeInfo>::InternalRelease(cbData);
        }
        else if ( !(unsigned int)OpenClassesRootKeyExW(v51) )
        {
          SubKey[0] = 0;
          v14 = 0;
          cchName = 13;
          for ( i = 0; !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0); i = v14 )
          {
            v23 = wcstoul(Name, &v45, 16);
            if ( *v45 == 46 )
            {
              v24 = wcstoul(v45 + 1, 0, 16);
              if ( !v10 && v23 > v6 || v24 >= v11 && v23 == v6 )
              {
                v6 = v23;
                v11 = v24;
                _o_wcscpy_s(SubKey, 13, Name);
              }
              cchName = 13;
            }
            ++v14;
          }
          if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x2000000u, &phkResult) )
          {
            v16 = phkResult;
            if ( phkResult == hKey )
              hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
            for ( j = 0; ; ++j )
            {
              v33 = 16;
              if ( RegEnumKeyExW(v16, j, v51, &v33, 0, 0, 0, 0) )
                break;
              v18 = FIsLCID(v51);
              v16 = phkResult;
              if ( v18 )
              {
                if ( !RegOpenKeyExW(phkResult, v51, 0, 0x2000000u, &v39) )
                {
                  if ( !RegOpenKeyExW(v39, L"win64", 0, 0x2000000u, &v41)
                    || (v33 = 6, !RegEnumKeyExW(v39, 0, v51, &v33, 0, 0, 0, 0))
                    && !RegOpenKeyExW(v39, v51, 0, 0x2000000u, &v41) )
                  {
                    pcbData = 520;
                    if ( !RegGetValueW(v41, 0, 0, 6u, 0, szFile, &pcbData) )
                    {
                      v4 = v47;
                      goto LABEL_26;
                    }
                  }
                }
                break;
              }
            }
          }
LABEL_33:
          if ( v41 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            RegCloseKey(v41);
          if ( v39 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            RegCloseKey(v39);
          if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            RegCloseKey(phkResult);
          if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            RegCloseKey(hKey);
        }
      }
      else
      {
LABEL_61:
        v8 = 0;
      }
    }
LABEL_41:
    WindowsDeleteString(string);
    return (unsigned int)v8;
  }
  return 2147647517LL;
}

```

## disassembly

```asm
0x180012020  mov     [rsp-8+arg_18], rbx
0x180012025  push    rbp
0x180012026  push    rsi
0x180012027  push    rdi
0x180012028  push    r12
0x18001202a  push    r13
0x18001202c  push    r14
0x18001202e  push    r15
0x180012030  lea     rbp, [rsp-370h]
0x180012038  sub     rsp, 470h
0x18001203f  mov     rax, cs:__security_cookie
0x180012046  xor     rax, rsp
0x180012049  mov     [rbp+3A0h+var_40], rax
0x180012050  mov     [rbp+3A0h+var_3F0], rdx
0x180012054  mov     edi, r8d
0x180012057  mov     r14, rdx
0x18001205a  mov     r12, rcx
0x18001205d  cmp     r8d, 10h
0x180012061  jge     loc_1800126BF
0x180012067  xor     esi, esi
0x180012069  mov     [rsp+4A0h+var_458], esi
0x18001206d  mov     [rbp+3A0h+var_400], rsi
0x180012071  mov     [rsp+4A0h+var_45C], esi
0x180012075  mov     [rsp+4A0h+cchName], esi
0x180012079  mov     [rbp+3A0h+var_3F8], rsi
0x18001207d  mov     [rsp+4A0h+hKey], rsi
0x180012082  mov     [rsp+4A0h+phkResult], rsi
0x180012087  mov     [rsp+4A0h+var_430], rsi
0x18001208c  mov     [rbp+3A0h+var_420], rsi
0x180012090  mov     [rbp+3A0h+string], rsi
0x180012094  call    ?MapIIDToFusionTypeInfo@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@@Z; MapIIDToFusionTypeInfo(_GUID const &,ITypeInfo * *)
0x180012099  mov     ebx, eax
0x18001209b  test    eax, eax
0x18001209d  js      loc_1800124D9
0x1800120a3  cmp     eax, 1
0x1800120a6  jnz     loc_1800126C9
0x1800120ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800120b0  mov     [rbp+3A0h+pptlib], rsi
0x1800120b4  lea     r15d, [rsi+47h]
0x1800120b8  mov     [rsp+4A0h+hKey], rax
0x1800120bd  mov     edx, r15d
0x1800120c0  mov     [rsp+4A0h+phkResult], rax
0x1800120c5  lea     r8, aInterface; "Interface\\"
0x1800120cc  mov     [rsp+4A0h+var_430], rax
0x1800120d1  lea     rcx, [rbp+3A0h+var_390]
0x1800120d5  mov     [rbp+3A0h+var_420], rax
0x1800120d9  call    cs:__imp__o_wcscpy_s
0x1800120df  lea     r13d, [rsi+27h]
0x1800120e3  mov     rcx, r12; rguid
0x1800120e6  mov     r8d, r13d; cchMax
0x1800120e9  lea     rdx, [rbp+3A0h+sz]; lpsz
0x1800120ed  call    cs:__imp_StringFromGUID2
0x1800120f3  lea     r8, aForward; "\\Forward"
0x1800120fa  mov     edx, r15d
0x1800120fd  lea     rcx, [rbp+3A0h+var_390]
0x180012101  call    cs:__imp__o_wcscat_s
0x180012107  lea     r8, [rsp+4A0h+hkey]
0x18001210c  mov     [rsp+4A0h+var_458], 208h
0x180012114  lea     rcx, [rbp+3A0h+var_390]; lpSubKey
0x180012118  mov     [rsp+4A0h+hkey], rsi
0x18001211d  call    OpenClassesRootKeyExW
0x180012122  test    eax, eax
0x180012124  jnz     short loc_18001216A
0x180012126  mov     rcx, [rsp+4A0h+hkey]; hkey
0x18001212b  lea     rax, [rsp+4A0h+var_458]
0x180012130  mov     [rsp+4A0h+pcbData], rax; pcbData
0x180012135  lea     r9d, [rsi+6]; dwFlags
0x180012139  lea     rax, [rbp+3A0h+szFile]
0x180012140  xor     r8d, r8d; lpValue
0x180012143  mov     [rsp+4A0h+pvData], rax; pvData
0x180012148  xor     edx, edx; lpSubKey
0x18001214a  mov     [rsp+4A0h+pdwType], rsi; pdwType
0x18001214f  call    cs:__imp_RegGetValueW
0x180012155  mov     rcx, [rsp+4A0h+hkey]; hKey
0x18001215a  mov     ebx, eax
0x18001215c  call    cs:__imp_RegCloseKey
0x180012162  test    ebx, ebx
0x180012164  jz      loc_1800126D0
0x18001216a  lea     r8, aTypelib_1; "TypeLib\\"
0x180012171  mov     rdx, r15
0x180012174  lea     rcx, [rbp+3A0h+var_390]
0x180012178  call    cs:__imp__o_wcscpy_s
0x18001217e  mov     ebx, 3Ah ; ':'
0x180012183  mov     [rsp+4A0h+var_438], 28h ; '('
0x18001218b  mov     edx, ebx
0x18001218d  mov     [rsp+4A0h+hkey], rsi
0x180012192  lea     r8, aInterface; "Interface\\"
0x180012199  lea     rcx, [rbp+3A0h+var_2D0]
0x1800121a0  call    cs:__imp__o_wcscpy_s
0x1800121a6  mov     r8d, r13d; cchMax
0x1800121a9  lea     rdx, [rbp+3A0h+var_2BC]; lpsz
0x1800121b0  mov     rcx, r12; rguid
0x1800121b3  call    cs:__imp_StringFromGUID2
0x1800121b9  lea     r8, aTypelib_3; "\\TypeLib"
0x1800121c0  mov     edx, ebx
0x1800121c2  lea     rcx, [rbp+3A0h+var_2D0]
0x1800121c9  call    cs:__imp__o_wcscat_s
0x1800121cf  lea     r8, [rsp+4A0h+hkey]
0x1800121d4  lea     rcx, [rbp+3A0h+var_2D0]; lpSubKey
0x1800121db  call    OpenClassesRootKeyExW
0x1800121e0  test    eax, eax
0x1800121e2  jnz     loc_1800125F7
0x1800121e8  mov     eax, [rsp+4A0h+var_438]
0x1800121ec  mov     ebx, 8002801Dh
0x1800121f1  mov     rcx, [rsp+4A0h+hkey]; hkey
0x1800121f6  add     eax, eax
0x1800121f8  mov     [rsp+4A0h+var_438], eax
0x1800121fc  mov     r9d, 6; dwFlags
0x180012202  lea     rax, [rsp+4A0h+var_438]
0x180012207  xor     r8d, r8d; lpValue
0x18001220a  mov     [rsp+4A0h+pcbData], rax; pcbData
0x18001220f  xor     edx, edx; lpSubKey
0x180012211  lea     rax, [rbp+3A0h+var_380]
0x180012215  mov     r13d, esi
0x180012218  mov     [rsp+4A0h+pvData], rax; pvData
0x18001221d  mov     r15d, esi
0x180012220  mov     [rsp+4A0h+pdwType], rsi; pdwType
0x180012225  mov     edi, ebx
0x180012227  call    cs:__imp_RegGetValueW
0x18001222d  test    eax, eax
0x18001222f  jnz     short loc_1800122AC
0x180012231  mov     rcx, [rsp+4A0h+hkey]; hKey
0x180012236  lea     rax, [rsp+4A0h+cbData]
0x18001223b  mov     [rsp+4A0h+pvData], rax; lpcbData
0x180012240  lea     rdx, ?Version@Constants@Catalog@Com@@3QBGB; "Version"
0x180012247  lea     rax, [rbp+3A0h+Data]
0x18001224e  mov     [rbp+3A0h+EndPtr], rsi
0x180012252  xor     r9d, r9d; lpType
0x180012255  mov     [rsp+4A0h+pdwType], rax; lpData
0x18001225a  xor     r8d, r8d; lpReserved
0x18001225d  mov     [rsp+4A0h+cbData], 28h ; '('
0x180012265  call    cs:__imp_RegQueryValueExW
0x18001226b  test    eax, eax
0x18001226d  jnz     short loc_1800122AA
0x18001226f  lea     edi, [rax+10h]
0x180012272  mov     r8d, edi; Radix
0x180012275  lea     rdx, [rbp+3A0h+EndPtr]; EndPtr
0x180012279  lea     rcx, [rbp+3A0h+Data]; String
0x180012280  call    cs:__imp_wcstoul
0x180012286  mov     rcx, [rbp+3A0h+EndPtr]
0x18001228a  cmp     word ptr [rcx], 2Eh ; '.'
0x18001228e  jnz     short loc_1800122AA
0x180012290  add     rcx, 2; String
0x180012294  mov     r8d, edi; Radix
0x180012297  xor     edx, edx; EndPtr
0x180012299  movzx   esi, ax
0x18001229c  call    cs:__imp_wcstoul
0x1800122a2  movzx   r15d, ax
0x1800122a6  lea     r13d, [rdi-0Fh]
0x1800122aa  xor     edi, edi
0x1800122ac  mov     rcx, [rsp+4A0h+hkey]; hKey
0x1800122b1  call    cs:__imp_RegCloseKey
0x1800122b7  cmp     edi, ebx
0x1800122b9  jz      loc_1800125F5
0x1800122bf  lea     r8, [rsp+4A0h+hKey]
0x1800122c4  lea     rcx, [rbp+3A0h+var_390]; lpSubKey
0x1800122c8  call    OpenClassesRootKeyExW
0x1800122cd  xor     edi, edi
0x1800122cf  test    eax, eax
0x1800122d1  jnz     loc_1800124D9
0x1800122d7  mov     [rbp+3A0h+SubKey], di
0x1800122db  mov     r14d, edi
0x1800122de  mov     [rsp+4A0h+cchName], 0Dh
0x1800122e6  xor     edx, edx; dwIndex
0x1800122e8  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800122ed  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x1800122f2  mov     [rsp+4A0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800122f7  lea     r8, [rbp+3A0h+Name]; lpName
0x1800122fb  mov     [rsp+4A0h+pcbData], rdi; lpcchClass
0x180012300  mov     [rsp+4A0h+pvData], rdi; lpClass
0x180012305  mov     [rsp+4A0h+pdwType], rdi; lpReserved
0x18001230a  call    cs:__imp_RegEnumKeyExW
0x180012310  test    eax, eax
0x180012312  jz      loc_18001250F
0x180012318  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001231d  lea     rax, [rsp+4A0h+phkResult]
0x180012322  mov     r14d, 2000000h
0x180012328  mov     [rsp+4A0h+pdwType], rax; phkResult
0x18001232d  mov     r9d, r14d; samDesired
0x180012330  lea     rdx, [rbp+3A0h+SubKey]; lpSubKey
0x180012334  xor     r8d, r8d; ulOptions
0x180012337  call    cs:__imp_RegOpenKeyExW
0x18001233d  xor     esi, esi
0x18001233f  test    eax, eax
0x180012341  jnz     loc_180012496
0x180012347  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x18001234c  cmp     rcx, [rsp+4A0h+hKey]
0x180012351  jnz     short loc_18001235C
0x180012353  mov     [rsp+4A0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18001235c  mov     edi, esi
0x18001235e  mov     [rsp+4A0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180012363  lea     r9, [rsp+4A0h+var_45C]; lpcchName
0x180012368  mov     [rsp+4A0h+pcbData], rsi; lpcchClass
0x18001236d  lea     r8, [rbp+3A0h+var_390]; lpName
0x180012371  mov     [rsp+4A0h+pvData], rsi; lpClass
0x180012376  mov     edx, edi; dwIndex
0x180012378  mov     [rsp+4A0h+pdwType], rsi; lpReserved
0x18001237d  mov     [rsp+4A0h+var_45C], 10h
0x180012385  call    cs:__imp_RegEnumKeyExW
0x18001238b  test    eax, eax
0x18001238d  jnz     loc_180012496
0x180012393  lea     rcx, [rbp+3A0h+var_390]; unsigned __int16 *
0x180012397  call    ?FIsLCID@@YAHPEBG@Z; FIsLCID(ushort const *)
0x18001239c  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x1800123a1  test    eax, eax
0x1800123a3  jz      loc_180012709
0x1800123a9  lea     rax, [rsp+4A0h+var_430]
0x1800123ae  mov     r9d, r14d; samDesired
0x1800123b1  xor     r8d, r8d; ulOptions
0x1800123b4  mov     [rsp+4A0h+pdwType], rax; phkResult
0x1800123b9  lea     rdx, [rbp+3A0h+var_390]; lpSubKey
0x1800123bd  call    cs:__imp_RegOpenKeyExW
0x1800123c3  test    eax, eax
0x1800123c5  jnz     loc_180012496
0x1800123cb  mov     rcx, [rsp+4A0h+var_430]; hKey
0x1800123d0  lea     rax, [rbp+3A0h+var_420]
0x1800123d4  mov     r9d, r14d; samDesired
0x1800123d7  mov     [rsp+4A0h+pdwType], rax; phkResult
0x1800123dc  xor     r8d, r8d; ulOptions
0x1800123df  lea     rdx, aWin64; "win64"
0x1800123e6  call    cs:__imp_RegOpenKeyExW
0x1800123ec  test    eax, eax
0x1800123ee  jnz     loc_180012582
0x1800123f4  mov     rcx, [rbp+3A0h+var_420]; hkey
0x1800123f8  lea     rax, [rsp+4A0h+var_458]
0x1800123fd  mov     [rsp+4A0h+pcbData], rax; pcbData
0x180012402  mov     r9d, 6; dwFlags
0x180012408  lea     rax, [rbp+3A0h+szFile]
0x18001240f  mov     [rsp+4A0h+var_458], 208h
0x180012417  mov     [rsp+4A0h+pvData], rax; pvData
0x18001241c  xor     r8d, r8d; lpValue
0x18001241f  xor     edx, edx; lpSubKey
0x180012421  mov     [rsp+4A0h+pdwType], rsi; pdwType
0x180012426  call    cs:__imp_RegGetValueW
0x18001242c  test    eax, eax
0x18001242e  jnz     short loc_180012496
0x180012430  mov     r14, [rbp+3A0h+var_3F0]
0x180012434  mov     rcx, [rbp+3A0h+string]; string
0x180012438  test    rcx, rcx
0x18001243b  jnz     loc_18001273A
0x180012441  lea     rcx, [rbp+3A0h+szFile]; szFile
0x180012448  lea     r8, [rbp+3A0h+pptlib]; pptlib
0x18001244c  xor     edx, edx; regkind
0x18001244e  call    LoadTypeLibEx
0x180012453  mov     rdi, [rbp+3A0h+pptlib]
0x180012457  mov     ebx, eax
0x180012459  test    eax, eax
0x18001245b  js      short loc_180012482
0x18001245d  mov     rax, [rdi]
0x180012460  lea     r8, [rbp+3A0h+var_3F8]
0x180012464  mov     rdx, r12
0x180012467  mov     rcx, rdi
0x18001246a  mov     rax, [rax+30h]
0x18001246e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012473  mov     ebx, eax
0x180012475  test    eax, eax
0x180012477  js      short loc_180012482
0x180012479  mov     rax, [rbp+3A0h+var_3F8]
0x18001247d  mov     ebx, esi
0x18001247f  mov     [r14], rax
0x180012482  test    rdi, rdi
0x180012485  jz      short loc_180012496
0x180012487  mov     rax, [rdi]
0x18001248a  mov     rcx, rdi
0x18001248d  mov     rax, [rax+10h]
0x180012491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012496  mov     rcx, [rbp+3A0h+var_420]; hKey
0x18001249a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001249e  jz      short loc_1800124A6
0x1800124a0  call    cs:__imp_RegCloseKey
0x1800124a6  mov     rcx, [rsp+4A0h+var_430]; hKey
0x1800124ab  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800124af  jz      short loc_1800124B7
0x1800124b1  call    cs:__imp_RegCloseKey
0x1800124b7  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x1800124bc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800124c0  jz      short loc_1800124C8
0x1800124c2  call    cs:__imp_RegCloseKey
0x1800124c8  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800124cd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800124d1  jz      short loc_1800124D9
0x1800124d3  call    cs:__imp_RegCloseKey
0x1800124d9  mov     rcx, [rbp+3A0h+string]; string
0x1800124dd  call    cs:__imp_WindowsDeleteString
0x1800124e3  mov     eax, ebx
0x1800124e5  mov     rcx, [rbp+3A0h+var_40]
0x1800124ec  xor     rcx, rsp; StackCookie
0x1800124ef  call    __security_check_cookie
0x1800124f4  mov     rbx, [rsp+4A0h+arg_18]
0x1800124fc  add     rsp, 470h
0x180012503  pop     r15
0x180012505  pop     r14
0x180012507  pop     r13
0x180012509  pop     r12
0x18001250b  pop     rdi
0x18001250c  pop     rsi
0x18001250d  pop     rbp
0x18001250e  retn
0x18001250f  mov     r8d, 10h; Radix
0x180012515  lea     rdx, [rbp+3A0h+var_400]; EndPtr
  ... truncated ...
```
