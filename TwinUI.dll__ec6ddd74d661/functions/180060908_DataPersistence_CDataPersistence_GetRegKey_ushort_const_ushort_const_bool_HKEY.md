# DataPersistence::CDataPersistence::GetRegKey(ushort const *,ushort const *,bool,HKEY__ * *)

- ea: `0x180060908`
- end: `0x180061373`
- name: `?GetRegKey@CDataPersistence@DataPersistence@@AEAAJPEBG0_NPEAPEAUHKEY__@@@Z`
- size: `2667`
- prototype: `int(DataPersistence::CDataPersistence *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool, HKEY *)`
- caller_count: `9`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060330`
- `0x1800604d0`
- `0x1800605f0`
- `0x180060754`
- `0x1800607f0`
- `0x180104f10`
- `0x1801e39d8`
- `0x1801e3bb0`
- `0x1801e3db0`

## callees

- `0x18000e498`
- `0x18002fc18`
- `0x1800378dc`
- `0x180060908`
- `0x18008acb0`
- `0x18008f860`
- `0x1800a98c4`
- `0x1800a9d98`
- `0x1800f1a00`
- `0x180108c7c`
- `0x18010df2c`
- `0x180142e10`
- `0x180143a7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800609ab`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800609ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060bbf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060dd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061006`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061289`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006135a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060dd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061006`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061289`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006135a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800610d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800611f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060d56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060f23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061091`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800610d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800611f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061218`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060e9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060c99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060e9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060edf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060a12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180060fb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800610e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060bdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060bdf`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180060b7f`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180060b7f`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180060bab`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180060c1a`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180060bab`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x180060c1a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180060d74`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180060e50`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800610b9`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180060d74`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180060e50`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800610b9`

## pseudocode

```c
__int64 __fastcall DataPersistence::CDataPersistence::GetRegKey(
        DataPersistence::CDataPersistence *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        PHKEY a5)
{
  wchar_t *v5; // rax
  __int64 v7; // rdi
  const unsigned __int16 *v9; // r8
  _WORD *v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rdx
  wchar_t *v13; // rcx
  wchar_t *v14; // rax
  unsigned int LastError; // ebx
  _WORD *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  wchar_t *v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // r10
  _WORD *v23; // rcx
  unsigned __int64 v24; // r14
  unsigned __int64 v25; // rdi
  __int64 v26; // r8
  __int64 v27; // r9
  _WORD *v28; // rcx
  unsigned __int64 v29; // rdx
  _WORD *v30; // rax
  _WORD *v31; // rcx
  __int64 v32; // rax
  const char *v33; // r9
  __int64 v34; // rbx
  __int64 v35; // rdi
  WCHAR *v36; // r14
  const char *v37; // r9
  int v38; // edi
  bool v39; // sf
  LSTATUS v40; // eax
  bool v41; // sf
  LSTATUS v42; // eax
  bool v43; // sf
  char v44; // di
  HKEY v45; // rdi
  unsigned int v46; // eax
  LSTATUS v47; // eax
  bool v48; // sf
  LSTATUS v49; // eax
  bool v50; // sf
  HKEY v51; // rdi
  unsigned int v52; // eax
  unsigned __int64 v53; // rdi
  bool v54; // cf
  __int64 v55; // rdx
  __int64 v56; // r9
  int Error; // eax
  unsigned int Key; // eax
  __int64 v59; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultd; // [rsp+20h] [rbp-E0h]
  HKEY v66; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v67; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v68; // [rsp+68h] [rbp-98h] BYREF
  HKEY v69; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v71; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v72; // [rsp+88h] [rbp-78h] BYREF
  _WORD *v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  _WORD v75[72]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Str[136]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v5 = Str;
  v75[0] = 0;
  v7 = 2147483646;
  v9 = a2;
  *a5 = 0;
  v10 = 0;
  v11 = 2147483646;
  v12 = 130;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v5++ = *v9++;
    --v11;
    --v12;
  }
  while ( v12 );
  v13 = v5 - 1;
  if ( v12 )
    v13 = v5;
  *v13 = 0;
  if ( !v12 || (v14 = wcsrchr(Str, 0x21u), Str[0] == 33) || !v14 || (v17 = v14 + 1, !v14[1]) )
  {
    LastError = -2147024809;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)LastError,
      phkResult);
LABEL_11:
    if ( v10 )
      CoTaskMemFree(v10);
    return LastError;
  }
  v18 = 65;
  *v14 = 0;
  v19 = 65;
  v20 = Str;
  v21 = 2147483646;
  v22 = v75;
  do
  {
    if ( !v21 )
      break;
    if ( !*v20 )
      break;
    *v22++ = *v20++;
    --v21;
    --v19;
  }
  while ( v19 );
  v23 = v22 - 1;
  LastError = v19 == 0 ? 0x8007007A : 0;
  if ( v19 )
    v23 = v22;
  *v23 = 0;
  if ( v19 )
  {
    do
    {
      if ( !v7 )
        break;
      if ( !*v17 )
        break;
      ++v17;
      --v7;
      --v18;
    }
    while ( v18 );
    LastError = v18 == 0 ? 0x8007007A : 0;
  }
  if ( (LastError & 0x80000000) != 0 )
    goto LABEL_10;
  v24 = -1;
  do
    ++v24;
  while ( v75[v24] );
  v25 = v24 + 1;
  if ( v24 + 1 < v24 || (v73 = 0, !is_mul_ok(v25, 2u)) )
  {
    LastError = -2147024362;
    goto LABEL_10;
  }
  v10 = CoTaskMemAlloc(2 * v25);
  v73 = v10;
  LastError = v10 == 0 ? 0x8007000E : 0;
  if ( !v10 )
    goto LABEL_10;
  if ( v25 > 0x7FFFFFFF )
  {
LABEL_111:
    *v10 = 0;
    goto LABEL_39;
  }
  if ( v24 >= 0x7FFFFFFF )
  {
    if ( v24 == -1 )
      goto LABEL_39;
    goto LABEL_111;
  }
  v28 = v75;
  v29 = v24 + 1;
  v30 = v10;
  v26 = 0;
  do
  {
    if ( !v24 )
      break;
    if ( !*v28 )
      break;
    *v30++ = *v28++;
    --v24;
    ++v26;
    --v29;
  }
  while ( v29 );
  v31 = v30 - 1;
  v27 = v26 - 1;
  if ( v29 )
  {
    v31 = v30;
    v27 = v26;
  }
  *v31 = 0;
  if ( v29 )
  {
    v54 = v25 == v27;
    v53 = v25 - v27;
    if ( !v54 && v53 != 1 )
    {
      v26 = 2 * v53;
      if ( 2 * v53 > 2 )
        memset_0(&v10[v27 + 1], 0, v26 - 2);
    }
  }
LABEL_39:
  v32 = OpenStateExplicit(-4, v10, v26, v27);
  v74 = v32;
  v34 = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xE0,
                  (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                  v33);
    goto LABEL_11;
  }
  v71 = 0;
  if ( (unsigned int)GetSystemAppDataKey(v32, 0, 0, &v71) )
  {
    v38 = -2147418113;
    v55 = 228;
    v56 = 2147549183LL;
LABEL_115:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)v56,
      phkResult);
    goto LABEL_88;
  }
  if ( GetLastError() != 122 )
  {
    Error = ResultFromKnownLastError();
    v38 = Error;
    if ( Error < 0 )
    {
      v56 = (unsigned int)Error;
      v55 = 231;
      goto LABEL_115;
    }
  }
  v35 = v71;
  v36 = (WCHAR *)CoTaskMemAlloc(2LL * v71 + 2);
  v72 = v36;
  if ( !v36 )
  {
    v38 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_87:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
LABEL_88:
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v74);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v73);
    return (unsigned int)v38;
  }
  *v36 = 0;
  v36[v35] = 0;
  hKey = 0;
  if ( !(unsigned int)GetSystemAppDataKey(v34, &hKey, v36, &v71) )
  {
    v38 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xF0,
            (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
            v37);
LABEL_119:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_87;
  }
  v69 = 0;
  v38 = RegOpenKeyExW(hKey, v36, 0, 0xF003Fu, &v69);
  v39 = v38 < 0;
  if ( v38 > 0 )
  {
    v38 = (unsigned __int16)v38 | 0x80070000;
    v39 = v38 < 0;
  }
  if ( !v39 )
  {
    v68 = 0;
    v40 = RegOpenKeyExW(v69, L"ApplicationFrame", 0, 0xF003Fu, &v68);
    v41 = v40 < 0;
    if ( v40 > 0 )
      v41 = 1;
    if ( v41 )
    {
      v45 = v68;
      if ( v68 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
        RegCloseKey(v45);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
      }
      v68 = 0;
      v46 = RegCreateKeyExW(v69, L"ApplicationFrame", 0, 0, 0, 0xF003Fu, 0, &v68, 0);
      if ( v46 )
      {
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x100,
                (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                (const char *)v46,
                phkResultb);
LABEL_67:
        if ( v68 )
          RegCloseKey(v68);
        if ( v69 )
          RegCloseKey(v69);
        if ( hKey )
          RegCloseKey(hKey);
        CoTaskMemFree(v36);
        CloseState(v34);
        CoTaskMemFree(v10);
        return (unsigned int)v38;
      }
    }
    v67 = 0;
    v42 = RegOpenKeyExW(v68, a2, 0, 0xF003Fu, &v67);
    v43 = v42 < 0;
    if ( v42 > 0 )
      v43 = 1;
    if ( v43 )
    {
      v51 = v67;
      if ( v67 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
        RegCloseKey(v51);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
      }
      v67 = 0;
      v52 = RegCreateKeyExW(v68, a2, 0, 0, 0, 0xF003Fu, 0, &v67, 0);
      if ( v52 )
      {
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x106,
                (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                (const char *)v52,
                phkResultc);
        if ( v67 )
          RegCloseKey(v67);
        goto LABEL_67;
      }
    }
    if ( a3 && *a3 )
    {
      v44 = a4;
    }
    else
    {
      v44 = a4;
      if ( !a4 )
      {
        *a5 = v67;
        v67 = 0;
LABEL_56:
        if ( v68 )
          RegCloseKey(v68);
        if ( v69 )
          RegCloseKey(v69);
        if ( hKey )
          RegCloseKey(hKey);
        CoTaskMemFree(v36);
        CloseState(v34);
        CoTaskMemFree(v10);
        return 0;
      }
    }
    v66 = 0;
    v47 = RegOpenKeyExW(v67, L"ApplicationWindows", 0, 0xF003Fu, &v66);
    v48 = v47 < 0;
    if ( v47 > 0 )
      v48 = 1;
    if ( v48 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v66,
        0);
      Key = RegCreateKeyExW(v67, L"ApplicationWindows", 0, 0, 0, 0xF003Fu, 0, &v66, 0);
      if ( Key )
      {
        v59 = 276;
LABEL_124:
        v38 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)v59,
                (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
                (const char *)Key,
                phkResultd);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
        goto LABEL_118;
      }
    }
    if ( v44 )
    {
      *a5 = v66;
      v66 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v66);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v68);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v72);
      v38 = 0;
      goto LABEL_88;
    }
    v49 = RegOpenKeyExW(v66, a3, 0, 0xF003Fu, a5);
    v50 = v49 < 0;
    if ( v49 > 0 )
      v50 = 1;
    if ( v50 )
    {
      Key = RegCreateKeyExW(v66, a3, 0, 0, 0, 0xF003Fu, 0, a5, 0);
      if ( Key )
      {
        v59 = 287;
        goto LABEL_124;
      }
    }
    if ( v66 )
      RegCloseKey(v66);
    if ( v67 )
      RegCloseKey(v67);
    goto LABEL_56;
  }
  if ( v38 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"shell\\twinui\\datapersistence\\lib\\datapersistence.cpp",
      (const char *)(unsigned int)v38,
      phkResulta);
LABEL_118:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v69);
    goto LABEL_119;
  }
  if ( v69 )
    RegCloseKey(v69);
  if ( hKey )
    RegCloseKey(hKey);
  CoTaskMemFree(v36);
  CloseState(v34);
  CoTaskMemFree(v10);
  return 2147942402LL;
}

```

## disassembly

```asm
0x180060908  mov     [rsp-8+arg_0], rbx
0x18006090d  push    rbp
0x18006090e  push    rsi
0x18006090f  push    rdi
0x180060910  push    r12
0x180060912  push    r13
0x180060914  push    r14
0x180060916  push    r15
0x180060918  lea     rbp, [rsp-150h]
0x180060920  sub     rsp, 250h
0x180060927  mov     rax, cs:__security_cookie
0x18006092e  xor     rax, rsp
0x180060931  mov     [rbp+180h+var_40], rax
0x180060938  mov     r15, [rbp+180h+arg_20]
0x18006093f  lea     rax, [rbp+180h+Str]
0x180060943  xor     r14d, r14d
0x180060946  mov     [rsp+280h+var_230], r9b
0x18006094b  mov     r12, r8
0x18006094e  mov     [rbp+180h+var_1E0], r14w
0x180060953  mov     edi, 7FFFFFFEh
0x180060958  mov     r13, rdx
0x18006095b  mov     r8, rdx
0x18006095e  mov     [r15], r14
0x180060961  mov     esi, r14d
0x180060964  mov     ecx, edi
0x180060966  mov     edx, 82h
0x18006096b  test    rcx, rcx
0x18006096e  jz      short loc_18006098F
0x180060970  movzx   r9d, word ptr [r8]
0x180060974  test    r9w, r9w
0x180060978  jz      short loc_18006098F
0x18006097a  mov     [rax], r9w
0x18006097e  add     r8, 2
0x180060982  add     rax, 2
0x180060986  dec     rcx
0x180060989  sub     rdx, 1
0x18006098d  jnz     short loc_18006096B
0x18006098f  test    rdx, rdx
0x180060992  lea     rcx, [rax-2]
0x180060996  cmovnz  rcx, rax
0x18006099a  mov     [rcx], r14w
0x18006099e  jz      short loc_1800609BD
0x1800609a0  mov     ebx, 21h ; '!'
0x1800609a5  lea     rcx, [rbp+180h+Str]; Str
0x1800609a9  mov     edx, ebx; Ch
0x1800609ab  call    cs:__imp_wcsrchr
0x1800609b2  nop     dword ptr [rax+rax+00h]
0x1800609b7  cmp     bx, [rbp+180h+Str]
0x1800609bb  jnz     short loc_180060A20
0x1800609bd  mov     ebx, 80070057h
0x1800609c2  mov     rcx, [rbp+188h]; this
0x1800609c9  lea     r8, aShellTwinuiDat; "shell\\twinui\\datapersistence\\lib\\da"...
0x1800609d0  mov     r9d, ebx; char *
0x1800609d3  mov     edx, 0DDh; void *
0x1800609d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800609dd  test    rsi, rsi
0x1800609e0  jnz     short loc_180060A0F
0x1800609e2  mov     eax, ebx
0x1800609e4  mov     rcx, [rbp+180h+var_40]
0x1800609eb  xor     rcx, rsp; StackCookie
0x1800609ee  call    __security_check_cookie
0x1800609f3  mov     rbx, [rsp+280h+arg_0]
0x1800609fb  add     rsp, 250h
0x180060a02  pop     r15
0x180060a04  pop     r14
0x180060a06  pop     r13
0x180060a08  pop     r12
0x180060a0a  pop     rdi
0x180060a0b  pop     rsi
0x180060a0c  pop     rbp
0x180060a0d  retn
0x180060a0f  mov     rcx, rsi; pv
0x180060a12  call    cs:__imp_CoTaskMemFree
0x180060a19  nop     dword ptr [rax+rax+00h]
0x180060a1e  jmp     short loc_1800609E2
0x180060a20  test    rax, rax
0x180060a23  jz      short loc_1800609BD
0x180060a25  lea     r8, [rax+2]
0x180060a29  cmp     r14w, [r8]
0x180060a2d  jz      short loc_1800609BD
0x180060a2f  mov     edx, 41h ; 'A'
0x180060a34  mov     [rax], r14w
0x180060a38  mov     r9d, edx
0x180060a3b  lea     rcx, [rbp+180h+Str]
0x180060a3f  mov     rax, rdi
0x180060a42  lea     r10, [rbp+180h+var_1E0]
0x180060a46  test    rax, rax
0x180060a49  jz      short loc_180060A6A
0x180060a4b  movzx   r11d, word ptr [rcx]
0x180060a4f  test    r11w, r11w
0x180060a53  jz      short loc_180060A6A
0x180060a55  mov     [r10], r11w
0x180060a59  add     rcx, 2
0x180060a5d  add     r10, 2
0x180060a61  dec     rax
0x180060a64  sub     r9, 1
0x180060a68  jnz     short loc_180060A46
0x180060a6a  mov     rax, r9
0x180060a6d  lea     rcx, [r10-2]
0x180060a71  neg     rax
0x180060a74  mov     r11d, 8007007Ah
0x180060a7a  sbb     ebx, ebx
0x180060a7c  not     ebx
0x180060a7e  and     ebx, r11d
0x180060a81  test    r9, r9
0x180060a84  cmovnz  rcx, r10
0x180060a88  mov     [rcx], r14w
0x180060a8c  jnz     loc_180060F88
0x180060a92  test    ebx, ebx
0x180060a94  js      loc_1800609C2
0x180060a9a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180060a9e  lea     rax, [rbp+180h+var_1E0]
0x180060aa2  xor     ecx, ecx
0x180060aa4  inc     r14
0x180060aa7  cmp     [rax+r14*2], cx
0x180060aac  jnz     short loc_180060AA4
0x180060aae  lea     rdi, [r14+1]
0x180060ab2  cmp     rdi, r14
0x180060ab5  jb      short loc_180060AC8
0x180060ab7  mov     eax, 2
0x180060abc  mov     [rbp+180h+var_1F0], rcx
0x180060ac0  mul     rdi
0x180060ac3  test    rdx, rdx
0x180060ac6  jz      short loc_180060AD2
0x180060ac8  mov     ebx, 80070216h
0x180060acd  jmp     loc_1800609C2
0x180060ad2  mov     rcx, rax; cb
0x180060ad5  call    cs:__imp_CoTaskMemAlloc
0x180060adc  nop     dword ptr [rax+rax+00h]
0x180060ae1  mov     rsi, rax
0x180060ae4  mov     [rbp+180h+var_1F0], rax
0x180060ae8  neg     rax
0x180060aeb  sbb     ebx, ebx
0x180060aed  xor     r10d, r10d
0x180060af0  not     ebx
0x180060af2  and     ebx, 8007000Eh
0x180060af8  test    rsi, rsi
0x180060afb  jz      loc_1800610F1
0x180060b01  mov     eax, 7FFFFFFFh
0x180060b06  cmp     rdi, rax
0x180060b09  ja      loc_180061101
0x180060b0f  cmp     r14, rax
0x180060b12  jnb     loc_180061138
0x180060b18  test    rdi, rdi
0x180060b1b  jz      loc_18006114D
0x180060b21  lea     rcx, [rbp+180h+var_1E0]
0x180060b25  mov     rdx, rdi
0x180060b28  mov     rax, rsi
0x180060b2b  mov     r8d, r10d
0x180060b2e  test    r14, r14
0x180060b31  jz      short loc_180060B55
0x180060b33  movzx   r9d, word ptr [rcx]
0x180060b37  test    r9w, r9w
0x180060b3b  jz      short loc_180060B55
0x180060b3d  mov     [rax], r9w
0x180060b41  add     rcx, 2
0x180060b45  add     rax, 2
0x180060b49  dec     r14
0x180060b4c  inc     r8
0x180060b4f  sub     rdx, 1
0x180060b53  jnz     short loc_180060B2E
0x180060b55  xor     r14d, r14d
0x180060b58  lea     rcx, [rax-2]
0x180060b5c  test    rdx, rdx
0x180060b5f  lea     r9, [r8-1]
0x180060b63  cmovnz  rcx, rax
0x180060b67  cmovnz  r9, r8
0x180060b6b  mov     [rcx], r14w
0x180060b6f  jnz     loc_180061106
0x180060b75  mov     rdx, rsi
0x180060b78  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x180060b7f  call    cs:__imp_OpenStateExplicit
0x180060b86  nop     dword ptr [rax+rax+00h]
0x180060b8b  mov     [rbp+180h+var_1E8], rax
0x180060b8f  mov     rbx, rax
0x180060b92  test    rax, rax
0x180060b95  jz      loc_180061059
0x180060b9b  lea     r9, [rbp+180h+var_200]
0x180060b9f  mov     [rbp+180h+var_200], r14d
0x180060ba3  xor     r8d, r8d
0x180060ba6  xor     edx, edx
0x180060ba8  mov     rcx, rax
0x180060bab  call    cs:__imp_GetSystemAppDataKey
0x180060bb2  nop     dword ptr [rax+rax+00h]
0x180060bb7  test    eax, eax
0x180060bb9  jnz     loc_180061155
0x180060bbf  call    cs:__imp_GetLastError
0x180060bc6  nop     dword ptr [rax+rax+00h]
0x180060bcb  cmp     eax, 7Ah ; 'z'
0x180060bce  jnz     loc_180061164
0x180060bd4  mov     edi, [rbp+180h+var_200]
0x180060bd7  lea     rcx, ds:2[rdi*2]; cb
0x180060bdf  call    cs:__imp_CoTaskMemAlloc
0x180060be6  nop     dword ptr [rax+rax+00h]
0x180060beb  mov     r14, rax
0x180060bee  xor     eax, eax
0x180060bf0  mov     [rbp+180h+var_1F8], r14
0x180060bf4  test    r14, r14
0x180060bf7  jz      loc_180060F34
0x180060bfd  mov     [r14], ax
0x180060c01  lea     r9, [rbp+180h+var_200]
0x180060c05  mov     [r14+rdi*2], ax
0x180060c0a  lea     rdx, [rsp+280h+hKey]
0x180060c0f  mov     r8, r14
0x180060c12  mov     [rsp+280h+hKey], rax
0x180060c17  mov     rcx, rbx
0x180060c1a  call    cs:__imp_GetSystemAppDataKey
0x180060c21  nop     dword ptr [rax+rax+00h]
0x180060c26  xor     ecx, ecx
0x180060c28  test    eax, eax
0x180060c2a  jz      loc_180061193
0x180060c30  mov     [rsp+280h+var_210], rcx
0x180060c35  lea     rax, [rsp+280h+var_210]
0x180060c3a  mov     rcx, [rsp+280h+hKey]; hKey
0x180060c3f  mov     r9d, 0F003Fh; samDesired
0x180060c45  xor     r8d, r8d; ulOptions
0x180060c48  mov     [rsp+280h+phkResult], rax; int
0x180060c4d  mov     rdx, r14; lpSubKey
0x180060c50  call    cs:__imp_RegOpenKeyExW
0x180060c57  nop     dword ptr [rax+rax+00h]
0x180060c5c  mov     edi, eax
0x180060c5e  test    eax, eax
0x180060c60  jle     short loc_180060C6D
0x180060c62  movzx   edi, di
0x180060c65  or      edi, 80070000h
0x180060c6b  test    edi, edi
0x180060c6d  js      loc_180061078
0x180060c73  mov     rcx, [rsp+280h+var_210]; hKey
0x180060c78  lea     rax, [rsp+280h+var_218]
0x180060c7d  xor     edi, edi
0x180060c7f  mov     [rsp+280h+phkResult], rax; phkResult
0x180060c84  mov     r9d, 0F003Fh; samDesired
0x180060c8a  mov     [rsp+280h+var_218], rdi
0x180060c8f  xor     r8d, r8d; ulOptions
0x180060c92  lea     rdx, aApplicationfra; "ApplicationFrame"
0x180060c99  call    cs:__imp_RegOpenKeyExW
0x180060ca0  nop     dword ptr [rax+rax+00h]
0x180060ca5  test    eax, eax
0x180060ca7  jle     short loc_180060CB3
0x180060ca9  movzx   eax, ax
0x180060cac  or      eax, 80070000h
0x180060cb1  test    eax, eax
0x180060cb3  js      loc_180060D90
0x180060cb9  mov     rcx, [rsp+280h+var_218]; hKey
0x180060cbe  lea     rax, [rsp+280h+var_220]
0x180060cc3  mov     r9d, 0F003Fh; samDesired
0x180060cc9  mov     [rsp+280h+phkResult], rax; phkResult
0x180060cce  xor     r8d, r8d; ulOptions
0x180060cd1  mov     [rsp+280h+var_220], rdi
0x180060cd6  mov     rdx, r13; lpSubKey
0x180060cd9  call    cs:__imp_RegOpenKeyExW
0x180060ce0  nop     dword ptr [rax+rax+00h]
0x180060ce5  test    eax, eax
0x180060ce7  jle     short loc_180060CF3
0x180060ce9  movzx   eax, ax
0x180060cec  or      eax, 80070000h
0x180060cf1  test    eax, eax
0x180060cf3  js      loc_180060FC3
0x180060cf9  xor     r13d, r13d
0x180060cfc  test    r12, r12
0x180060cff  jnz     loc_180061235
0x180060d05  mov     dil, [rsp+280h+var_230]
0x180060d0a  test    dil, dil
0x180060d0d  jnz     loc_180060E7A
0x180060d13  mov     rax, [rsp+280h+var_220]
0x180060d18  mov     [r15], rax
0x180060d1b  mov     [rsp+280h+var_220], r13
0x180060d20  mov     rcx, [rsp+280h+var_218]; hKey
0x180060d25  test    rcx, rcx
0x180060d28  jz      short loc_180060D36
0x180060d2a  call    cs:__imp_RegCloseKey
0x180060d31  nop     dword ptr [rax+rax+00h]
0x180060d36  mov     rcx, [rsp+280h+var_210]; hKey
0x180060d3b  test    rcx, rcx
0x180060d3e  jz      short loc_180060D4C
0x180060d40  call    cs:__imp_RegCloseKey
0x180060d47  nop     dword ptr [rax+rax+00h]
0x180060d4c  mov     rcx, [rsp+280h+hKey]; hKey
0x180060d51  test    rcx, rcx
0x180060d54  jz      short loc_180060D62
0x180060d56  call    cs:__imp_RegCloseKey
0x180060d5d  nop     dword ptr [rax+rax+00h]
0x180060d62  mov     rcx, r14; pv
0x180060d65  call    cs:__imp_CoTaskMemFree
0x180060d6c  nop     dword ptr [rax+rax+00h]
0x180060d71  mov     rcx, rbx
0x180060d74  call    cs:__imp_CloseState
0x180060d7b  nop     dword ptr [rax+rax+00h]
0x180060d80  test    rsi, rsi
0x180060d83  jnz     loc_180060F74
0x180060d89  xor     eax, eax
0x180060d8b  jmp     loc_1800609E4
0x180060d90  mov     rdi, [rsp+280h+var_218]
0x180060d95  test    rdi, rdi
0x180060d98  jnz     loc_1800611E3
0x180060d9e  mov     rcx, [rsp+280h+var_210]; hKey
0x180060da3  lea     rax, [rsp+280h+var_218]
0x180060da8  xor     edi, edi
0x180060daa  lea     rdx, aApplicationfra; "ApplicationFrame"
0x180060db1  mov     [rsp+280h+lpdwDisposition], rdi; lpdwDisposition
  ... truncated ...
```
