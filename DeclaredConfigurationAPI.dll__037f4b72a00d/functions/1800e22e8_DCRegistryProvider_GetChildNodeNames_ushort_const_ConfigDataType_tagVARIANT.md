# DCRegistryProvider::GetChildNodeNames(ushort const *,ConfigDataType,tagVARIANT *)

- ea: `0x1800e22e8`
- end: `0x1800e2905`
- name: `?GetChildNodeNames@DCRegistryProvider@@QEBAJPEBGW4ConfigDataType@@PEAUtagVARIANT@@@Z`
- size: `1565`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e72b0`
- `0x1800e8bb8`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x1800143c8`
- `0x18001440c`
- `0x180014adc`
- `0x180018a70`
- `0x180018ac0`
- `0x180018ba4`
- `0x180019270`
- `0x1800192f8`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18001dea8`
- `0x18004babc`
- `0x1800e1d50`
- `0x1800e22e8`
- `0x1800e306c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e27b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e2806`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e2828`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e27b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e2806`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e2828`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e24bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e25de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e24bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e25de`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800e26b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800e26b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e264d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800e264d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e27c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e27c8`

## string_xrefs

- `0x1800e2331`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e23bf`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e24f9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e2719`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e278f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`
- `0x1800e27e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistryprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall DCRegistryProvider::GetChildNodeNames(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v6; // rdx
  int v7; // ebx
  int v9; // edx
  int v10; // ecx
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  const WCHAR *v15; // rdx
  LSTATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  const WCHAR *v20; // rdx
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  DWORD i; // edi
  LSTATUS v24; // eax
  HLOCAL v25; // rcx
  BSTR v26; // rax
  HLOCAL v27; // rcx
  HLOCAL v28; // rcx
  int dwOptions; // [rsp+20h] [rbp-358h]
  int dwOptionsa; // [rsp+20h] [rbp-358h]
  int dwOptionsb; // [rsp+20h] [rbp-358h]
  int dwOptionsc; // [rsp+20h] [rbp-358h]
  int dwOptionsd; // [rsp+20h] [rbp-358h]
  HKEY hKey; // [rsp+60h] [rbp-318h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-310h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-308h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-304h] BYREF
  _QWORD v38[3]; // [rsp+78h] [rbp-300h] BYREF
  void *p_hKey; // [rsp+90h] [rbp-2E8h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-2E0h] BYREF
  char v41; // [rsp+A0h] [rbp-2D8h]
  LPCWSTR lpSubKey[3]; // [rsp+B0h] [rbp-2C8h] BYREF
  unsigned __int64 v43; // [rsp+C8h] [rbp-2B0h]
  _BYTE v44[32]; // [rsp+D0h] [rbp-2A8h] BYREF
  int v45[8]; // [rsp+F0h] [rbp-288h] BYREF
  _BYTE v46[32]; // [rsp+110h] [rbp-268h] BYREF
  WCHAR Name[264]; // [rsp+130h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  if ( !a2 )
  {
    v6 = 729;
LABEL_3:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x80070057LL,
      dwOptionsb);
    return (unsigned int)v7;
  }
  if ( !a4 )
  {
    v6 = 730;
    goto LABEL_3;
  }
  if ( a3 != 8 )
  {
    v6 = 735;
    goto LABEL_3;
  }
  std::wstring::wstring((__int64)v44);
  std::wstring::wstring((__int64)lpSubKey);
  std::wstring::wstring((__int64)v45);
  v11 = DCRegistryProvider::ParseFullRegPathUri(v10, v9, (unsigned int)v44, (unsigned int)lpSubKey, (__int64)v45);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)(unsigned int)v11,
      dwOptionsc);
LABEL_50:
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v44);
    return (unsigned int)v7;
  }
  try
  {
    v12 = std::operator+<unsigned short>(v46, lpSubKey, L"\\");
    v13 = std::operator+<unsigned short>(&p_hKey, v12, v45);
    std::wstring::operator=(lpSubKey, v13);
    std::wstring::_Tidy_deallocate(&p_hKey);
    std::wstring::_Tidy_deallocate(v46);
    hKey = 0;
    v14 = std::wstring::compare(v44, L"device");
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2ED,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x8007000ELL,
      dwOptionsa);
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(lpSubKey);
    std::wstring::_Tidy_deallocate(v44);
    return 2147942414LL;
  }
  if ( v14 )
  {
    try
    {
      v18 = std::operator+<unsigned short>(&p_hKey, v44, L"\\");
      v19 = std::operator+<unsigned short>(v46, v18, lpSubKey);
      std::wstring::operator=(lpSubKey, v19);
      std::wstring::_Tidy_deallocate(v46);
      std::wstring::_Tidy_deallocate(&p_hKey);
      p_hKey = &hKey;
      phkResult = 0;
      v41 = 1;
      v20 = (const WCHAR *)lpSubKey;
      if ( v43 > 7 )
        v20 = lpSubKey[0];
      v21 = RegCreateKeyExW(HKEY_USERS, v20, 0, 0, 0, 0x20119u, 0, &phkResult, 0);
      v7 = v21;
      if ( v21 > 0 )
        v7 = (unsigned __int16)v21 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    }
    catch ( std::bad_alloc )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x306,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)0x8007000ELL,
        dwOptions);
      goto LABEL_49;
    }
    if ( v7 < 0 )
    {
      v17 = 785;
      goto LABEL_18;
    }
  }
  else
  {
    p_hKey = &hKey;
    phkResult = 0;
    v41 = 1;
    v15 = (const WCHAR *)lpSubKey;
    if ( v43 > 7 )
      v15 = lpSubKey[0];
    v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0, 0, 0x20119u, 0, &phkResult, 0);
    v7 = v16;
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v7 < 0 )
    {
      v17 = 764;
      goto LABEL_18;
    }
  }
  cSubKeys = 0;
  v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v7 = v22;
  if ( v22 > 0 )
    v7 = (unsigned __int16)v22 | 0x80070000;
  if ( v7 < 0 )
  {
    v17 = 790;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)(unsigned int)v7,
      dwOptionsd);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_50;
  }
  std::vector<ConfigDoc>::vector<ConfigDoc>(v38);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 260;
    v24 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    v7 = v24;
    if ( v24 > 0 )
      v7 = (unsigned __int16)v24 | 0x80070000;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x326,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
        (const char *)(unsigned int)v7,
        dwOptionsd);
LABEL_38:
      std::vector<std::wstring>::_Tidy(v38);
      goto LABEL_19;
    }
    std::wstring::wstring((__int64)&p_hKey, (__int64)Name);
    std::vector<std::wstring>::push_back(v38, &p_hKey);
    std::wstring::_Tidy_deallocate(&p_hKey);
  }
  hMem = 0;
  p_hKey = &hMem;
  phkResult = 0;
  v41 = 1;
  v7 = ConvertChildNodesToXML(a2, v38, (HLOCAL *)&phkResult);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hKey);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)(unsigned int)v7,
      dwOptionsd);
    v25 = hMem;
    hMem = 0;
    if ( v25 )
      LocalFree(v25);
    goto LABEL_38;
  }
  *(_WORD *)a4 = 8;
  v26 = SysAllocString((const OLECHAR *)hMem);
  *(_QWORD *)(a4 + 8) = v26;
  if ( !v26 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistryprovider.cpp",
      (const char *)0x8007000ELL,
      dwOptionsd);
    v27 = hMem;
    hMem = 0;
    if ( v27 )
      LocalFree(v27);
    std::vector<std::wstring>::_Tidy(v38);
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v7 = -2147024882;
    goto LABEL_50;
  }
  v28 = hMem;
  hMem = 0;
  if ( v28 )
    LocalFree(v28);
  std::vector<std::wstring>::_Tidy(v38);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v45);
  std::wstring::_Tidy_deallocate(lpSubKey);
  std::wstring::_Tidy_deallocate(v44);
  return 0;
}

```

## disassembly

```asm
0x1800e22e8  mov     [rsp+arg_0], rbx
0x1800e22ed  push    rsi
0x1800e22ee  push    rdi
0x1800e22ef  push    r12
0x1800e22f1  push    r14
0x1800e22f3  push    r15
0x1800e22f5  sub     rsp, 350h
0x1800e22fc  mov     rax, cs:__security_cookie
0x1800e2303  xor     rax, rsp
0x1800e2306  mov     [rsp+378h+var_38], rax
0x1800e230e  mov     rsi, r9
0x1800e2311  mov     r14, rdx
0x1800e2314  xor     r15d, r15d
0x1800e2317  test    rdx, rdx
0x1800e231a  jnz     short loc_1800E2344
0x1800e231c  mov     edx, 2D9h; void *
0x1800e2321  mov     ebx, 80070057h
0x1800e2326  mov     rcx, [rsp+378h]; this
0x1800e232e  mov     r9d, ebx; char *
0x1800e2331  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e233d  mov     eax, ebx
0x1800e233f  jmp     loc_1800E28DD
0x1800e2344  test    rsi, rsi
0x1800e2347  jnz     short loc_1800E2350
0x1800e2349  mov     edx, 2DAh
0x1800e234e  jmp     short loc_1800E2321
0x1800e2350  mov     r12d, 8
0x1800e2356  cmp     r8d, r12d
0x1800e2359  jz      short loc_1800E2362
0x1800e235b  mov     edx, 2DFh
0x1800e2360  jmp     short loc_1800E2321
0x1800e2362  lea     rcx, [rsp+378h+var_2A8]
0x1800e236a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e236f  nop
0x1800e2370  lea     rcx, [rsp+378h+lpSubKey]
0x1800e2378  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e237d  nop
0x1800e237e  lea     rcx, [rsp+378h+var_288]
0x1800e2386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800e238b  nop
0x1800e238c  lea     rax, [rsp+378h+var_288]
0x1800e2394  mov     qword ptr [rsp+378h+dwOptions], rax; int
0x1800e2399  lea     r9, [rsp+378h+lpSubKey]
0x1800e23a1  lea     r8, [rsp+378h+var_2A8]
0x1800e23a9  call    ?ParseFullRegPathUri@DCRegistryProvider@@AEBAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z; DCRegistryProvider::ParseFullRegPathUri(ushort const *,std::wstring &,std::wstring &,std::wstring &)
0x1800e23ae  mov     ebx, eax
0x1800e23b0  test    eax, eax
0x1800e23b2  jns     short loc_1800E23D5
0x1800e23b4  mov     rcx, [rsp+378h]; this
0x1800e23bc  mov     r9d, eax; char *
0x1800e23bf  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e23c6  mov     edx, 2E5h; void *
0x1800e23cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e23d0  jmp     loc_1800E2881
0x1800e23d5  lea     r8, StringValue; "\\"
0x1800e23dc  lea     rdx, [rsp+378h+lpSubKey]
0x1800e23e4  lea     rcx, [rsp+378h+var_268]
0x1800e23ec  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e23f1  nop
0x1800e23f2  lea     r8, [rsp+378h+var_288]
0x1800e23fa  mov     rdx, rax
0x1800e23fd  lea     rcx, [rsp+378h+var_2E8]
0x1800e2405  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e240a  mov     rdx, rax
0x1800e240d  lea     rcx, [rsp+378h+lpSubKey]
0x1800e2415  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e241a  lea     rcx, [rsp+378h+var_2E8]
0x1800e2422  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2427  nop
0x1800e2428  lea     rcx, [rsp+378h+var_268]
0x1800e2430  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2435  nop
0x1800e2436  mov     [rsp+378h+hKey], r15
0x1800e243b  lea     rdx, aDevice_4; "device"
0x1800e2442  lea     rcx, [rsp+378h+var_2A8]
0x1800e244a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800e244f  test    eax, eax
0x1800e2451  jnz     loc_1800E2515
0x1800e2457  lea     rax, [rsp+378h+hKey]
0x1800e245c  mov     [rsp+378h+var_2E8], rax
0x1800e2464  mov     [rsp+378h+var_2E0], r15
0x1800e246c  mov     [rsp+378h+var_2D8], 1
0x1800e2474  lea     rdx, [rsp+378h+lpSubKey]
0x1800e247c  cmp     [rsp+378h+var_2B0], 7
0x1800e2485  cmova   rdx, [rsp+378h+lpSubKey]; lpSubKey
0x1800e248e  mov     [rsp+378h+lpdwDisposition], r15; lpdwDisposition
0x1800e2493  lea     rax, [rsp+378h+var_2E0]
0x1800e249b  mov     [rsp+378h+phkResult], rax; phkResult
0x1800e24a0  mov     [rsp+378h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800e24a5  mov     [rsp+378h+samDesired], 20119h; samDesired
0x1800e24ad  mov     [rsp+378h+dwOptions], r15d; int
0x1800e24b2  xor     r9d, r9d; lpClass
0x1800e24b5  xor     r8d, r8d; Reserved
0x1800e24b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e24bf  call    cs:__imp_RegCreateKeyExW
0x1800e24c5  mov     ebx, eax
0x1800e24c7  test    eax, eax
0x1800e24c9  jle     short loc_1800E24D4
0x1800e24cb  movzx   ebx, ax
0x1800e24ce  or      ebx, 80070000h
0x1800e24d4  lea     rcx, [rsp+378h+var_2E8]
0x1800e24dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e24e1  test    ebx, ebx
0x1800e24e3  jns     loc_1800E260E
0x1800e24e9  mov     edx, 2FCh; void *
0x1800e24ee  mov     rcx, [rsp+378h]; this
0x1800e24f6  mov     r9d, ebx; char *
0x1800e24f9  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e2505  nop
0x1800e2506  lea     rcx, [rsp+378h+hKey]
0x1800e250b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e2510  jmp     loc_1800E2881
0x1800e2515  lea     r8, StringValue; "\\"
0x1800e251c  lea     rdx, [rsp+378h+var_2A8]
0x1800e2524  lea     rcx, [rsp+378h+var_2E8]
0x1800e252c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e2531  nop
0x1800e2532  lea     r8, [rsp+378h+lpSubKey]
0x1800e253a  mov     rdx, rax
0x1800e253d  lea     rcx, [rsp+378h+var_268]
0x1800e2545  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e254a  mov     rdx, rax
0x1800e254d  lea     rcx, [rsp+378h+lpSubKey]
0x1800e2555  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800e255a  lea     rcx, [rsp+378h+var_268]
0x1800e2562  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2567  nop
0x1800e2568  lea     rcx, [rsp+378h+var_2E8]
0x1800e2570  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2575  nop
0x1800e2576  lea     rax, [rsp+378h+hKey]
0x1800e257b  mov     [rsp+378h+var_2E8], rax
0x1800e2583  mov     [rsp+378h+var_2E0], r15
0x1800e258b  mov     [rsp+378h+var_2D8], 1
0x1800e2593  lea     rdx, [rsp+378h+lpSubKey]
0x1800e259b  cmp     [rsp+378h+var_2B0], 7
0x1800e25a4  cmova   rdx, [rsp+378h+lpSubKey]; lpSubKey
0x1800e25ad  mov     [rsp+378h+lpdwDisposition], r15; lpdwDisposition
0x1800e25b2  lea     rax, [rsp+378h+var_2E0]
0x1800e25ba  mov     [rsp+378h+phkResult], rax; phkResult
0x1800e25bf  mov     [rsp+378h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800e25c4  mov     [rsp+378h+samDesired], 20119h; samDesired
0x1800e25cc  mov     [rsp+378h+dwOptions], r15d; dwOptions
0x1800e25d1  xor     r9d, r9d; lpClass
0x1800e25d4  xor     r8d, r8d; Reserved
0x1800e25d7  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800e25de  call    cs:__imp_RegCreateKeyExW
0x1800e25e4  mov     ebx, eax
0x1800e25e6  test    eax, eax
0x1800e25e8  jle     short loc_1800E25F3
0x1800e25ea  movzx   ebx, ax
0x1800e25ed  or      ebx, 80070000h
0x1800e25f3  lea     rcx, [rsp+378h+var_2E8]
0x1800e25fb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800e2600  test    ebx, ebx
0x1800e2602  jns     short loc_1800E260E
0x1800e2604  mov     edx, 311h
0x1800e2609  jmp     loc_1800E24EE
0x1800e260e  mov     [rsp+378h+cSubKeys], r15d
0x1800e2613  mov     [rsp+378h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800e2618  mov     [rsp+378h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800e261d  mov     [rsp+378h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800e2622  mov     [rsp+378h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x1800e2627  mov     [rsp+378h+phkResult], r15; lpcValues
0x1800e262c  mov     [rsp+378h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x1800e2631  mov     qword ptr [rsp+378h+samDesired], r15; lpcbMaxSubKeyLen
0x1800e2636  lea     rax, [rsp+378h+cSubKeys]
0x1800e263b  mov     qword ptr [rsp+378h+dwOptions], rax; int
0x1800e2640  xor     r9d, r9d; lpReserved
0x1800e2643  xor     r8d, r8d; lpcchClass
0x1800e2646  xor     edx, edx; lpClass
0x1800e2648  mov     rcx, [rsp+378h+hKey]; hKey
0x1800e264d  call    cs:__imp_RegQueryInfoKeyW
0x1800e2653  mov     ebx, eax
0x1800e2655  test    eax, eax
0x1800e2657  jle     short loc_1800E2662
0x1800e2659  movzx   ebx, ax
0x1800e265c  or      ebx, 80070000h
0x1800e2662  test    ebx, ebx
0x1800e2664  jns     short loc_1800E2670
0x1800e2666  mov     edx, 316h
0x1800e266b  jmp     loc_1800E24EE
0x1800e2670  lea     rcx, [rsp+378h+var_300]
0x1800e2675  call    ??0?$vector@VConfigDoc@@V?$allocator@VConfigDoc@@@std@@@std@@QEAA@XZ; std::vector<ConfigDoc>::vector<ConfigDoc>(void)
0x1800e267a  nop
0x1800e267b  mov     edi, r15d
0x1800e267e  cmp     edi, [rsp+378h+cSubKeys]
0x1800e2682  jnb     loc_1800E273A
0x1800e2688  mov     [rsp+378h+cchName], 104h
0x1800e2690  mov     [rsp+378h+phkResult], r15; lpftLastWriteTime
0x1800e2695  mov     [rsp+378h+lpSecurityAttributes], r15; lpcchClass
0x1800e269a  mov     qword ptr [rsp+378h+samDesired], r15; lpClass
0x1800e269f  mov     qword ptr [rsp+378h+dwOptions], r15; int
0x1800e26a4  lea     r9, [rsp+378h+cchName]; lpcchName
0x1800e26a9  lea     r8, [rsp+378h+Name]; lpName
0x1800e26b1  mov     edx, edi; dwIndex
0x1800e26b3  mov     rcx, [rsp+378h+hKey]; hKey
0x1800e26b8  call    cs:__imp_RegEnumKeyExW
0x1800e26be  mov     ebx, eax
0x1800e26c0  test    eax, eax
0x1800e26c2  jle     short loc_1800E26CD
0x1800e26c4  movzx   ebx, ax
0x1800e26c7  or      ebx, 80070000h
0x1800e26cd  test    ebx, ebx
0x1800e26cf  js      short loc_1800E270E
0x1800e26d1  lea     rdx, [rsp+378h+Name]
0x1800e26d9  lea     rcx, [rsp+378h+var_2E8]
0x1800e26e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e26e6  nop
0x1800e26e7  lea     rdx, [rsp+378h+var_2E8]
0x1800e26ef  lea     rcx, [rsp+378h+var_300]
0x1800e26f4  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800e26f9  nop
0x1800e26fa  lea     rcx, [rsp+378h+var_2E8]
0x1800e2702  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2707  inc     edi
0x1800e2709  jmp     loc_1800E267E
0x1800e270e  mov     rcx, [rsp+378h]; this
0x1800e2716  mov     r9d, ebx; char *
0x1800e2719  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2720  mov     edx, 326h; void *
0x1800e2725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e272a  nop
0x1800e272b  lea     rcx, [rsp+378h+var_300]
0x1800e2730  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e2735  jmp     loc_1800E2506
0x1800e273a  mov     [rsp+378h+hMem], r15
0x1800e273f  lea     rax, [rsp+378h+hMem]
0x1800e2744  mov     [rsp+378h+var_2E8], rax
0x1800e274c  mov     [rsp+378h+var_2E0], r15
0x1800e2754  mov     [rsp+378h+var_2D8], 1
0x1800e275c  lea     r8, [rsp+378h+var_2E0]
0x1800e2764  lea     rdx, [rsp+378h+var_300]
0x1800e2769  mov     rcx, r14
0x1800e276c  call    ?ConvertChildNodesToXML@@YAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAPEAG@Z; ConvertChildNodesToXML(ushort const *,std::vector<std::wstring> &,ushort * *)
0x1800e2771  mov     ebx, eax
0x1800e2773  lea     rcx, [rsp+378h+var_2E8]
0x1800e277b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800e2780  test    ebx, ebx
0x1800e2782  jns     short loc_1800E27BF
0x1800e2784  mov     rcx, [rsp+378h]; this
0x1800e278c  mov     r9d, ebx; char *
0x1800e278f  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e2796  mov     edx, 32Bh; void *
0x1800e279b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e27a0  nop
0x1800e27a1  mov     rcx, [rsp+378h+hMem]; hMem
0x1800e27a6  mov     [rsp+378h+hMem], r15
0x1800e27ab  test    rcx, rcx
0x1800e27ae  jz      loc_1800E272B
0x1800e27b4  call    cs:__imp_LocalFree
0x1800e27ba  jmp     loc_1800E272B
0x1800e27bf  mov     [rsi], r12w
0x1800e27c3  mov     rcx, [rsp+378h+hMem]; psz
0x1800e27c8  call    cs:__imp_SysAllocString
0x1800e27ce  mov     [rsi+8], rax
0x1800e27d2  test    rax, rax
0x1800e27d5  jnz     short loc_1800E2819
0x1800e27d7  mov     rcx, [rsp+378h]; this
0x1800e27df  mov     r9d, 8007000Eh; char *
0x1800e27e5  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800e27ec  mov     edx, 32Fh; void *
0x1800e27f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e27f6  nop
0x1800e27f7  mov     rcx, [rsp+378h+hMem]; hMem
0x1800e27fc  mov     [rsp+378h+hMem], r15
0x1800e2801  test    rcx, rcx
0x1800e2804  jz      short loc_1800E280D
0x1800e2806  call    cs:__imp_LocalFree
0x1800e280c  nop
0x1800e280d  lea     rcx, [rsp+378h+var_300]
0x1800e2812  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e2817  jmp     short loc_1800E2872
0x1800e2819  mov     rcx, [rsp+378h+hMem]; hMem
0x1800e281e  mov     [rsp+378h+hMem], r15
0x1800e2823  test    rcx, rcx
0x1800e2826  jz      short loc_1800E282F
0x1800e2828  call    cs:__imp_LocalFree
0x1800e282e  nop
0x1800e282f  lea     rcx, [rsp+378h+var_300]
0x1800e2834  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800e2839  nop
0x1800e283a  lea     rcx, [rsp+378h+hKey]
0x1800e283f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e2844  nop
0x1800e2845  lea     rcx, [rsp+378h+var_288]
0x1800e284d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2852  nop
0x1800e2853  lea     rcx, [rsp+378h+lpSubKey]
0x1800e285b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e2860  nop
0x1800e2861  lea     rcx, [rsp+378h+var_2A8]
0x1800e2869  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e286e  xor     eax, eax
0x1800e2870  jmp     short loc_1800E28DD
0x1800e2872  lea     rcx, [rsp+378h+hKey]
0x1800e2877  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800e287c  mov     ebx, 8007000Eh
  ... truncated ...
```
