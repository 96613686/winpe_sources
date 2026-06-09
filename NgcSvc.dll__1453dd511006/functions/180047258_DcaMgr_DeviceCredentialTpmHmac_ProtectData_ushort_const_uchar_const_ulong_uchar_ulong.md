# DcaMgr::DeviceCredentialTpmHmac::ProtectData(ushort const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180047258`
- end: `0x180047ced`
- name: `?ProtectData@DeviceCredentialTpmHmac@DcaMgr@@SAJPEBGPEBEKPEAPEAEPEAK@Z`
- size: `2709`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180098f9c`

## callees

- `0x18000782c`
- `0x1800281e0`
- `0x180028200`
- `0x180032c20`
- `0x180047258`
- `0x180048304`
- `0x180048434`
- `0x18004ed74`
- `0x18004f1b0`
- `0x180050b30`
- `0x18005bce8`
- `0x18005bef0`
- `0x18005bf44`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x1800a64ec`
- `0x1800a89ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004773f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800477db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004786f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800479ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047a6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047cbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004773f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800477db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004786f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800478fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800479ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047a6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047c7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047cbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800473e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800473e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800472b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004748f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800472b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004748f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800474db`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800474db`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180047454`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180047454`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047358`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180047358`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047762`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800477fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047890`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18004791b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047996`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047a0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047a8b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047af0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047b53`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047c5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047ca2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047762`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800477fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047890`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18004791b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047996`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047a0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047a8b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047af0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047b53`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047c5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180047ca2`

## string_xrefs

- `0x180047301`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047380`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800473bc`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800476e5`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x18004778a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047822`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800478b6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047941`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800479be`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047a35`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047aaa`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047b3f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047bdc`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x180047503`: `UserSid`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialTpmHmac::ProtectData(
        char *a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned __int8 **a5)
{
  unsigned int v5; // r12d
  int v6; // ebx
  bool v7; // sf
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  unsigned int v11; // eax
  const char *v12; // r9
  WCHAR *v13; // rbx
  __int64 v14; // rdx
  SIZE_T v15; // rdi
  char *v16; // rax
  char *v17; // rsi
  char *v18; // rcx
  HLOCAL v19; // rdi
  unsigned int v20; // r14d
  DWORD i; // ecx
  unsigned int v22; // eax
  unsigned int v23; // r12d
  unsigned int v24; // eax
  int RegStringValue; // r13d
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  unsigned __int64 *v29; // r8
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rbx
  SIZE_T v35; // rax
  _BYTE *mm; // rcx
  __int64 v37; // rbx
  SIZE_T v38; // rax
  _BYTE *kk; // rcx
  unsigned int v40; // r12d
  __int64 v41; // rbx
  SIZE_T v42; // rax
  _BYTE *jj; // rcx
  unsigned int v44; // r12d
  __int64 v45; // rbx
  SIZE_T v46; // rax
  _BYTE *ii; // rcx
  __int64 v48; // rbx
  SIZE_T v49; // rax
  _BYTE *n; // rcx
  __int64 v51; // rbx
  SIZE_T v52; // rax
  _BYTE *m; // rcx
  unsigned int v54; // r12d
  __int64 v55; // rbx
  SIZE_T v56; // rax
  _BYTE *k; // rcx
  __int64 v58; // rbx
  SIZE_T v59; // rax
  _BYTE *j; // rcx
  SIZE_T v61; // rax
  char *nn; // rcx
  unsigned int v64; // r13d
  __int64 v65; // rbx
  __int64 v66; // rbx
  SIZE_T v67; // rax
  char *i2; // rcx
  SIZE_T v69; // rax
  char *i1; // rcx
  unsigned int phkResult; // [rsp+28h] [rbp-C1h]
  unsigned int phkResulta; // [rsp+28h] [rbp-C1h]
  unsigned int phkResultb; // [rsp+28h] [rbp-C1h]
  unsigned int phkResultc; // [rsp+28h] [rbp-C1h]
  int phkResultd; // [rsp+28h] [rbp-C1h]
  unsigned int *lpcbMaxSubKeyLen; // [rsp+30h] [rbp-B9h]
  const char *lpcbMaxSubKeyLena; // [rsp+30h] [rbp-B9h]
  unsigned int *lpcbMaxClassLen; // [rsp+38h] [rbp-B1h]
  DWORD v79; // [rsp+68h] [rbp-81h]
  int v80; // [rsp+68h] [rbp-81h]
  _BYTE v81[12]; // [rsp+6Ch] [rbp-7Dh] BYREF
  HKEY hkey; // [rsp+78h] [rbp-71h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp-69h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+84h] [rbp-65h] BYREF
  char *v85; // [rsp+88h] [rbp-61h] BYREF
  __int64 *p_hKey; // [rsp+90h] [rbp-59h] BYREF
  HKEY v87; // [rsp+98h] [rbp-51h] BYREF
  char v88; // [rsp+A0h] [rbp-49h]
  NCRYPT_HANDLE hObject; // [rsp+A8h] [rbp-41h] BYREF
  LPCWSTR pszKeyName; // [rsp+B0h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-31h] BYREF
  BYTE Data[4]; // [rsp+C0h] [rbp-29h] BYREF
  DWORD cbInput; // [rsp+C4h] [rbp-25h] BYREF
  __int64 v94; // [rsp+C8h] [rbp-21h] BYREF
  PBYTE pbInput; // [rsp+D0h] [rbp-19h] BYREF
  DWORD cchName; // [rsp+D8h] [rbp-11h] BYREF
  DWORD cbData; // [rsp+DCh] [rbp-Dh] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+57h]
  unsigned int v101; // [rsp+150h] [rbp+67h]
  unsigned int v103; // [rsp+160h] [rbp+77h]

  v103 = (unsigned int)a4;
  v101 = (unsigned int)a2;
  v88 = 1;
  p_hKey = (__int64 *)&hKey;
  v5 = 0;
  hKey = 0;
  v87 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
         0,
         0x20019u,
         &v87);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      v7 = v6 < 0;
      if ( v6 > 0 )
      {
        v6 = (unsigned __int16)v6 | 0x80070000;
        v7 = v6 < 0;
      }
      if ( !v7 )
        goto LABEL_103;
      v8 = 235;
      goto LABEL_13;
    }
    v9 = 1168;
    v10 = 238;
LABEL_8:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
           (const char *)v9,
           phkResult);
LABEL_103:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v6;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v11 )
  {
    v9 = v11;
    v10 = 255;
    goto LABEL_8;
  }
  if ( !cSubKeys )
  {
    v6 = -2147023728;
    v8 = 257;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    goto LABEL_103;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v81[4],
    0,
    ++cbMaxSubKeyLen,
    v12);
  v13 = *(WCHAR **)&v81[4];
  if ( !*(_QWORD *)&v81[4] )
  {
    v14 = 261;
LABEL_16:
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_102:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81[4]);
    goto LABEL_103;
  }
  v15 = 16LL * cSubKeys;
  v16 = (char *)LocalAlloc(0, v15);
  v17 = v16;
  if ( !v16 || (v18 = &v16[v15], v16 == &v16[v15]) )
  {
    if ( !v16 )
    {
      v14 = 264;
      goto LABEL_16;
    }
  }
  else
  {
    do
    {
      *(_DWORD *)v16 = 0;
      *((_QWORD *)v16 + 1) = 0;
      v16 += 16;
    }
    while ( v16 != v18 );
  }
  v19 = v17;
  hMem = v17;
  v20 = 0;
  for ( i = 0; ; i = v79 + 1 )
  {
    v79 = i;
    if ( i >= cSubKeys )
      break;
    cchName = cbMaxSubKeyLen;
    v22 = RegEnumKeyExW(hKey, i, v13, &cchName, 0, 0, 0, 0);
    if ( v22 )
    {
      RegStringValue = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x11F,
                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
                         (const char *)v22,
                         phkResulta);
      if ( v20 )
      {
        do
        {
          v58 = 2LL * v5;
          LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
          *(_QWORD *)&v17[8 * v58 + 8] = 0;
        }
        while ( v5 < v20 );
      }
      else
      {
        v19 = v17;
      }
      v59 = LocalSize(v19);
      for ( j = v19; v59; --v59 )
        *j++ = 0;
      goto LABEL_97;
    }
    p_hKey = (__int64 *)&hkey;
    hkey = 0;
    v87 = 0;
    v88 = 1;
    v23 = RegOpenKeyExW(hKey, v13, 0, 0x20019u, &v87);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v23 )
    {
      RegStringValue = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x127,
                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
                         (const char *)v23,
                         phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      v54 = 0;
      if ( v20 )
      {
        do
        {
          v55 = 2LL * v54;
          LocalFree(*(HLOCAL *)&v17[16 * v54++ + 8]);
          *(_QWORD *)&v17[8 * v55 + 8] = 0;
        }
        while ( v54 < v20 );
      }
      else
      {
        v19 = v17;
      }
      v56 = LocalSize(v19);
      for ( k = v19; v56; --v56 )
        *k++ = 0;
      goto LABEL_97;
    }
    cbData = 4;
    v5 = 0;
    *(_DWORD *)Data = 0;
    v24 = RegQueryValueExW(hkey, L"State", 0, 0, Data, &cbData);
    if ( v24 )
    {
      RegStringValue = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x131,
                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
                         (const char *)v24,
                         phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      if ( v20 )
      {
        do
        {
          v51 = 2LL * v5;
          LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
          *(_QWORD *)&v17[8 * v51 + 8] = 0;
        }
        while ( v5 < v20 );
      }
      else
      {
        v19 = v17;
      }
      v52 = LocalSize(v19);
      for ( m = v19; v52; --v52 )
        *m++ = 0;
      goto LABEL_97;
    }
    if ( *(_DWORD *)Data <= 1u )
    {
      p_hKey = (__int64 *)&v85;
      v85 = 0;
      v87 = 0;
      v88 = 1;
      RegStringValue = ReadRegStringValue(hkey, 0, L"UserSid");
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
      if ( RegStringValue < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13D,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
          (const char *)(unsigned int)RegStringValue,
          phkResultc);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        if ( v20 )
        {
          do
          {
            v48 = 2LL * v5;
            LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
            *(_QWORD *)&v17[8 * v48 + 8] = 0;
          }
          while ( v5 < v20 );
        }
        else
        {
          v19 = v17;
        }
        v49 = LocalSize(v19);
        for ( n = v19; v49; --v49 )
          *n++ = 0;
        goto LABEL_97;
      }
      v26 = (unsigned __int16 *)v85;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v26 + a1 - v85);
        v28 = *v26 - v27;
        if ( v28 )
          break;
        ++v26;
      }
      while ( v27 );
      if ( v28 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
        v5 = 0;
      }
      else
      {
        pszKeyName = 0;
        v87 = 0;
        p_hKey = (__int64 *)&pszKeyName;
        v88 = 1;
        RegStringValue = ReadRegStringValue(hkey, 0, L"TpmHmacKeyName");
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
        if ( RegStringValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x148,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)RegStringValue,
            phkResultc);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszKeyName);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          v44 = 0;
          if ( v20 )
          {
            do
            {
              v45 = 2LL * v44;
              LocalFree(*(HLOCAL *)&v17[16 * v44++ + 8]);
              *(_QWORD *)&v17[8 * v45 + 8] = 0;
            }
            while ( v44 < v20 );
          }
          else
          {
            v19 = v17;
          }
          v46 = LocalSize(v19);
          for ( ii = v19; v46; --v46 )
            *ii++ = 0;
          goto LABEL_97;
        }
        hObject = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
          &hObject,
          0);
        v30 = TpmPolicySession::OpenHmacKey(pszKeyName, (const unsigned __int16 *)&hObject, v29);
        RegStringValue = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14D,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)v30,
            phkResultc);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszKeyName);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          v40 = 0;
          if ( v20 )
          {
            do
            {
              v41 = 2LL * v40;
              LocalFree(*(HLOCAL *)&v17[16 * v40++ + 8]);
              *(_QWORD *)&v17[8 * v41 + 8] = 0;
            }
            while ( v40 < v20 );
          }
          else
          {
            v19 = v17;
          }
          v42 = LocalSize(v19);
          for ( jj = v19; v42; --v42 )
            *jj++ = 0;
          goto LABEL_97;
        }
        pbInput = 0;
        p_hKey = (__int64 *)&pbInput;
        v31 = -1;
        cbInput = 0;
        v87 = 0;
        v88 = 1;
        do
          ++v31;
        while ( *(_WORD *)&a1[2 * v31] );
        RegStringValue = GenerateHash(0, a1, (unsigned int)(2 * v31), &v87);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
        v5 = 0;
        if ( RegStringValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x156,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)RegStringValue,
            (int)&cbInput);
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszKeyName);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          if ( v20 )
          {
            do
            {
              v37 = 2LL * v5;
              LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
              *(_QWORD *)&v17[8 * v37 + 8] = 0;
            }
            while ( v5 < v20 );
          }
          else
          {
            v19 = v17;
          }
          v38 = LocalSize(v19);
          for ( kk = v19; v38; --v38 )
            *kk++ = 0;
          goto LABEL_97;
        }
        p_hKey = &v94;
        v94 = 0;
        *(_DWORD *)v81 = 0;
        v87 = 0;
        v88 = 1;
        RegStringValue = TpmPolicySession::GetPolicyInfo(
                           hObject,
                           pbInput,
                           cbInput,
                           (unsigned int)&v87,
                           (unsigned __int8 **)v81,
                           lpcbMaxSubKeyLen);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
        if ( RegStringValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x160,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)RegStringValue,
            phkResultd);
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v94);
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszKeyName);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          if ( v20 )
          {
            do
            {
              v34 = 2LL * v5;
              LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
              *(_QWORD *)&v17[8 * v34 + 8] = 0;
            }
            while ( v5 < v20 );
            v19 = hMem;
          }
          else
          {
            v19 = v17;
          }
          v35 = LocalSize(v19);
          for ( mm = v19; v35; --v35 )
            *mm++ = 0;
LABEL_97:
          LocalFree(v19);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81[4]);
          v6 = RegStringValue;
          goto LABEL_103;
        }
        v32 = v20++;
        v32 *= 2;
        *(_DWORD *)&v17[8 * v32] = *(_DWORD *)v81;
        v33 = v94;
        v94 = 0;
        *(_QWORD *)&v17[8 * v32 + 8] = v33;
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v94);
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbInput);
        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszKeyName);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v85);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  if ( !v20 )
  {
    v6 = -2146893802;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x80090016LL,
      (int)"No valid TPM HMAC key name",
      (const char *)lpcbMaxSubKeyLen);
    v61 = LocalSize(v17);
    for ( nn = v17; v61; --v61 )
      *v17++ = 0;
    LocalFree(nn);
    goto LABEL_102;
  }
  v80 = TpmPolicySession::SealWithPolicyInfo(
          (TpmPolicySession *)v17,
          (const struct TpmPolicySession::PolicyInfo *)v20,
          v101,
          (const unsigned __int8 *)a3,
          v103,
          a5,
          lpcbMaxClassLen);
  v64 = v80;
  if ( v80 < 0 )
    goto LABEL_107;
  if ( !*(_DWORD *)a5 )
  {
    v64 = -2146893783;
    v80 = -2146893783;
LABEL_107:
    LODWORD(lpcbMaxSubKeyLena) = v20;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)v64,
      (int)"TpmPolicySession::SealWithPolicyInfo policyCount=%d",
      lpcbMaxSubKeyLena);
    do
    {
      v65 = 2LL * v5;
      LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
      *(_QWORD *)&v17[8 * v65 + 8] = 0;
    }
    while ( v5 < v20 );
    v69 = LocalSize(v17);
    for ( i1 = v17; v69; --v69 )
      *i1++ = 0;
    LocalFree(v17);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81[4]);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)v80;
  }
  do
  {
    v66 = 2LL * v5;
    LocalFree(*(HLOCAL *)&v17[16 * v5++ + 8]);
    *(_QWORD *)&v17[8 * v66 + 8] = 0;
  }
  while ( v5 < v20 );
  v67 = LocalSize(v17);
  for ( i2 = v17; v67; --v67 )
    *i2++ = 0;
  LocalFree(v17);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v81[4]);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180047258  mov     rax, rsp
0x18004725b  mov     [rax+20h], r9
0x18004725f  mov     [rax+18h], r8d
0x180047263  mov     [rax+10h], rdx
0x180047267  mov     [rax+8], rcx
0x18004726b  push    rbp
0x18004726c  push    rbx
0x18004726d  push    rsi
0x18004726e  push    rdi
0x18004726f  push    r12
0x180047271  push    r13
0x180047273  push    r14
0x180047275  push    r15
0x180047277  lea     rbp, [rax-57h]
0x18004727b  sub     rsp, 0F8h
0x180047282  lea     rax, [rbp+4Fh+hKey]
0x180047286  mov     [rbp+4Fh+var_98], 1
0x18004728a  mov     [rbp+4Fh+var_A8], rax
0x18004728e  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180047295  lea     rax, [rbp+4Fh+var_A0]
0x180047299  xor     r12d, r12d
0x18004729c  mov     r9d, 20019h; samDesired
0x1800472a2  mov     [rsp+130h+phkResult], rax; unsigned int
0x1800472a7  xor     r8d, r8d; ulOptions
0x1800472aa  mov     [rbp+4Fh+hKey], r12
0x1800472ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800472b5  mov     [rbp+4Fh+var_A0], r12
0x1800472b9  call    cs:__imp_RegOpenKeyExW
0x1800472bf  lea     rcx, [rbp+4Fh+var_A8]
0x1800472c3  mov     ebx, eax
0x1800472c5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800472ca  test    ebx, ebx
0x1800472cc  jz      short loc_180047314
0x1800472ce  cmp     ebx, 2
0x1800472d1  jz      short loc_1800472F2
0x1800472d3  test    ebx, ebx
0x1800472d5  jle     short loc_1800472E2
0x1800472d7  movzx   ebx, bx
0x1800472da  or      ebx, 80070000h
0x1800472e0  test    ebx, ebx
0x1800472e2  jns     loc_180047B7C
0x1800472e8  mov     edx, 0EBh
0x1800472ed  jmp     loc_18004737C
0x1800472f2  mov     r9d, 490h; char *
0x1800472f8  mov     edx, 0EEh; void *
0x1800472fd  mov     rcx, [rbp+57h]; this
0x180047301  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x180047308  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004730d  mov     ebx, eax
0x18004730f  jmp     loc_180047B7C
0x180047314  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180047318  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x18004731c  mov     [rsp+130h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180047321  xor     r9d, r9d; lpReserved
0x180047324  mov     [rsp+130h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180047329  xor     r8d, r8d; lpcchClass
0x18004732c  mov     [rsp+130h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180047331  xor     edx, edx; lpClass
0x180047333  mov     [rsp+130h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180047338  mov     [rsp+130h+lpcValues], r12; lpcValues
0x18004733d  mov     [rsp+130h+lpcbMaxClassLen], r12; unsigned int *
0x180047342  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; char *
0x180047347  lea     rax, [rbp+4Fh+cSubKeys]
0x18004734b  mov     [rsp+130h+phkResult], rax; int
0x180047350  mov     [rbp+4Fh+cSubKeys], r12d
0x180047354  mov     [rbp+4Fh+cbMaxSubKeyLen], r12d
0x180047358  call    cs:__imp_RegQueryInfoKeyW
0x18004735e  test    eax, eax
0x180047360  jz      short loc_18004736C
0x180047362  mov     r9d, eax
0x180047365  mov     edx, 0FFh
0x18004736a  jmp     short loc_1800472FD
0x18004736c  cmp     [rbp+4Fh+cSubKeys], r12d
0x180047370  jnz     short loc_180047394
0x180047372  mov     ebx, 80070490h
0x180047377  mov     edx, 101h; void *
0x18004737c  mov     rcx, [rbp+57h]; this
0x180047380  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x180047387  mov     r9d, ebx; char *
0x18004738a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004738f  jmp     loc_180047B7C
0x180047394  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x180047397  lea     rcx, [rbp+4Fh+var_CC+4]
0x18004739b  inc     eax
0x18004739d  xor     edx, edx
0x18004739f  mov     r8d, eax
0x1800473a2  mov     [rbp+4Fh+cbMaxSubKeyLen], eax
0x1800473a5  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800473aa  mov     rbx, qword ptr [rbp+4Fh+var_CC+4]
0x1800473ae  test    rbx, rbx
0x1800473b1  jnz     short loc_1800473D5
0x1800473b3  mov     edx, 105h; void *
0x1800473b8  mov     rcx, [rbp+57h]; this
0x1800473bc  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800473c3  mov     ebx, 8007000Eh
0x1800473c8  mov     r9d, ebx; char *
0x1800473cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800473d0  jmp     loc_180047B73
0x1800473d5  mov     edi, [rbp+4Fh+cSubKeys]
0x1800473d8  xor     ecx, ecx; uFlags
0x1800473da  shl     rdi, 4
0x1800473de  mov     rdx, rdi; uBytes
0x1800473e1  call    cs:__imp_LocalAlloc
0x1800473e7  mov     rsi, rax
0x1800473ea  test    rax, rax
0x1800473ed  jz      loc_18004756B
0x1800473f3  lea     rcx, [rax+rdi]
0x1800473f7  cmp     rax, rcx
0x1800473fa  jz      loc_18004756B
0x180047400  mov     [rax], r12d
0x180047403  mov     [rax+8], r12
0x180047407  add     rax, 10h
0x18004740b  cmp     rax, rcx
0x18004740e  jnz     short loc_180047400
0x180047410  mov     rdi, rsi
0x180047413  mov     [rbp+4Fh+hMem], rsi
0x180047417  mov     r15, rsi
0x18004741a  mov     r14d, r12d
0x18004741d  mov     ecx, r12d
0x180047420  mov     [rsp+60h], ecx
0x180047424  cmp     ecx, [rbp+4Fh+cSubKeys]
0x180047427  jnb     loc_180047B22
0x18004742d  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x180047430  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x180047434  mov     [rsp+130h+lpcValues], r12; lpftLastWriteTime
0x180047439  mov     edx, ecx; dwIndex
0x18004743b  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004743f  mov     r8, rbx; lpName
0x180047442  mov     [rsp+130h+lpcbMaxClassLen], r12; lpcchClass
0x180047447  mov     [rsp+130h+lpcbMaxSubKeyLen], r12; lpClass
0x18004744c  mov     [rsp+130h+phkResult], r12; unsigned int
0x180047451  mov     [rbp+4Fh+cchName], eax
0x180047454  call    cs:__imp_RegEnumKeyExW
0x18004745a  test    eax, eax
0x18004745c  jnz     loc_180047AA6
0x180047462  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180047466  lea     rax, [rbp+4Fh+hkey]
0x18004746a  mov     [rbp+4Fh+var_A8], rax
0x18004746e  mov     r9d, 20019h; samDesired
0x180047474  lea     rax, [rbp+4Fh+var_A0]
0x180047478  mov     [rbp+4Fh+hkey], r12
0x18004747c  xor     r8d, r8d; ulOptions
0x18004747f  mov     [rsp+130h+phkResult], rax; unsigned int
0x180047484  mov     rdx, rbx; lpSubKey
0x180047487  mov     [rbp+4Fh+var_A0], r12
0x18004748b  mov     [rbp+4Fh+var_98], 1
0x18004748f  call    cs:__imp_RegOpenKeyExW
0x180047495  lea     rcx, [rbp+4Fh+var_A8]
0x180047499  mov     r12d, eax
0x18004749c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800474a1  test    r12d, r12d
0x1800474a4  jnz     loc_180047A31
0x1800474aa  mov     rcx, [rbp+4Fh+hkey]; hKey
0x1800474ae  lea     rax, [rbp+4Fh+cbData]
0x1800474b2  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; unsigned int *
0x1800474b7  lea     rdx, aState; "State"
0x1800474be  lea     rax, [rbp+4Fh+Data]
0x1800474c2  mov     [rbp+4Fh+cbData], 4
0x1800474c9  xor     r12d, r12d
0x1800474cc  mov     [rsp+130h+phkResult], rax; unsigned int
0x1800474d1  xor     r9d, r9d; lpType
0x1800474d4  mov     dword ptr [rbp+4Fh+Data], r12d
0x1800474d8  xor     r8d, r8d; lpReserved
0x1800474db  call    cs:__imp_RegQueryValueExW
0x1800474e1  test    eax, eax
0x1800474e3  jnz     loc_1800479BA
0x1800474e9  cmp     dword ptr [rbp+4Fh+Data], 1
0x1800474ed  ja      loc_1800476CD
0x1800474f3  mov     rcx, [rbp+4Fh+hkey]; hkey
0x1800474f7  lea     rax, [rbp+4Fh+var_B0]
0x1800474fb  lea     r9, [rbp+4Fh+var_A0]
0x1800474ff  mov     [rbp+4Fh+var_A8], rax
0x180047503  lea     r8, aUsersid; "UserSid"
0x18004750a  mov     [rbp+4Fh+var_B0], r12
0x18004750e  xor     edx, edx; lpSubKey
0x180047510  mov     [rbp+4Fh+var_A0], r12
0x180047514  mov     [rbp+4Fh+var_98], 1
0x180047518  call    ReadRegStringValue
0x18004751d  lea     rcx, [rbp+4Fh+var_A8]
0x180047521  mov     r13d, eax
0x180047524  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180047529  test    r13d, r13d
0x18004752c  js      loc_18004793D
0x180047532  mov     r12, [rbp+4Fh+arg_0]
0x180047536  mov     rax, [rbp+4Fh+var_B0]
0x18004753a  mov     r8, r12
0x18004753d  sub     r8, rax
0x180047540  movzx   edx, word ptr [rax]
0x180047543  movzx   ecx, word ptr [rax+r8]
0x180047548  sub     edx, ecx
0x18004754a  jnz     short loc_180047554
0x18004754c  add     rax, 2
0x180047550  test    ecx, ecx
0x180047552  jnz     short loc_180047540
0x180047554  xor     ecx, ecx
0x180047556  test    edx, edx
0x180047558  jz      short loc_18004757E
0x18004755a  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18004755e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180047563  xor     r12d, r12d
0x180047566  jmp     loc_1800476CD
0x18004756b  test    rsi, rsi
0x18004756e  jnz     loc_180047410
0x180047574  mov     edx, 108h
0x180047579  jmp     loc_1800473B8
0x18004757e  mov     [rbp+4Fh+pszKeyName], rcx
0x180047582  lea     rax, [rbp+4Fh+pszKeyName]
0x180047586  mov     [rbp+4Fh+var_A0], rcx
0x18004758a  lea     r9, [rbp+4Fh+var_A0]
0x18004758e  mov     rcx, [rbp+4Fh+hkey]; hkey
0x180047592  lea     r8, aTpmhmackeyname; "TpmHmacKeyName"
0x180047599  xor     edx, edx; lpSubKey
0x18004759b  mov     [rbp+4Fh+var_A8], rax
0x18004759f  mov     [rbp+4Fh+var_98], 1
0x1800475a3  call    ReadRegStringValue
0x1800475a8  lea     rcx, [rbp+4Fh+var_A8]
0x1800475ac  mov     r13d, eax
0x1800475af  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800475b4  xor     eax, eax
0x1800475b6  test    r13d, r13d
0x1800475b9  js      loc_1800478B2
0x1800475bf  xor     edx, edx
0x1800475c1  mov     [rbp+4Fh+hObject], rax
0x1800475c5  lea     rcx, [rbp+4Fh+hObject]
0x1800475c9  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800475ce  mov     rcx, [rbp+4Fh+pszKeyName]; pszKeyName
0x1800475d2  lea     rdx, [rbp+4Fh+hObject]; unsigned __int16 *
0x1800475d6  call    ?OpenHmacKey@TpmPolicySession@@YAJPEBGPEA_K@Z; TpmPolicySession::OpenHmacKey(ushort const *,unsigned __int64 *)
0x1800475db  xor     ecx, ecx
0x1800475dd  mov     r13d, eax
0x1800475e0  test    eax, eax
0x1800475e2  js      loc_18004781E
0x1800475e8  lea     rax, [rbp+4Fh+pbInput]
0x1800475ec  mov     [rbp+4Fh+pbInput], rcx
0x1800475f0  mov     [rbp+4Fh+var_A8], rax
0x1800475f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800475f8  mov     [rbp+4Fh+cbInput], ecx
0x1800475fb  mov     [rbp+4Fh+var_A0], rcx
0x1800475ff  mov     [rbp+4Fh+var_98], 1
0x180047603  inc     r8
0x180047606  cmp     [r12+r8*2], cx
0x18004760b  jnz     short loc_180047603
0x18004760d  lea     rax, [rbp+4Fh+cbInput]
0x180047611  add     r8d, r8d
0x180047614  lea     r9, [rbp+4Fh+var_A0]
0x180047618  mov     [rsp+130h+phkResult], rax; int
0x18004761d  mov     rdx, r12
0x180047620  call    GenerateHash
0x180047625  lea     rcx, [rbp+4Fh+var_A8]
0x180047629  mov     r13d, eax
0x18004762c  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180047631  xor     r12d, r12d
0x180047634  test    r13d, r13d
0x180047637  js      loc_180047786
0x18004763d  mov     r8d, [rbp+4Fh+cbInput]; cbInput
0x180047641  lea     rax, [rbp+4Fh+var_70]
0x180047645  mov     rdx, [rbp+4Fh+pbInput]; pbInput
0x180047649  lea     r9, [rbp+4Fh+var_A0]; unsigned int
0x18004764d  mov     rcx, [rbp+4Fh+hObject]; hObject
0x180047651  mov     [rbp+4Fh+var_A8], rax
0x180047655  lea     rax, [rbp+4Fh+var_CC]
0x180047659  mov     [rsp+130h+phkResult], rax; int
0x18004765e  mov     [rbp+4Fh+var_70], r12
0x180047662  mov     dword ptr [rbp+4Fh+var_CC], r12d
0x180047666  mov     [rbp+4Fh+var_A0], r12
0x18004766a  mov     [rbp+4Fh+var_98], 1
0x18004766e  call    ?GetPolicyInfo@TpmPolicySession@@YAJ_KPEBEKPEAPEAEPEAK@Z; TpmPolicySession::GetPolicyInfo(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)
0x180047673  lea     rcx, [rbp+4Fh+var_A8]
0x180047677  mov     r13d, eax
0x18004767a  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x18004767f  test    r13d, r13d
0x180047682  js      short loc_1800476E1
0x180047684  mov     eax, dword ptr [rbp+4Fh+var_CC]
0x180047687  mov     ecx, r14d
0x18004768a  inc     r14d
0x18004768d  add     rcx, rcx
0x180047690  mov     [rsi+rcx*8], eax
0x180047693  mov     rax, [rbp+4Fh+var_70]
0x180047697  mov     [rbp+4Fh+var_70], r12
0x18004769b  mov     [rsi+rcx*8+8], rax
0x1800476a0  lea     rcx, [rbp+4Fh+var_70]
0x1800476a4  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800476a9  lea     rcx, [rbp+4Fh+pbInput]
0x1800476ad  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800476b2  lea     rcx, [rbp+4Fh+hObject]
0x1800476b6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800476bb  lea     rcx, [rbp+4Fh+pszKeyName]; void *
0x1800476bf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800476c4  lea     rcx, [rbp+4Fh+var_B0]; void *
0x1800476c8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800476cd  lea     rcx, [rbp+4Fh+hkey]
0x1800476d1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800476d6  mov     ecx, [rsp+60h]
0x1800476da  inc     ecx
0x1800476dc  jmp     loc_180047420
0x1800476e1  mov     rcx, [rbp+57h]; this
0x1800476e5  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800476ec  mov     r9d, r13d; char *
0x1800476ef  mov     edx, 160h; void *
0x1800476f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
