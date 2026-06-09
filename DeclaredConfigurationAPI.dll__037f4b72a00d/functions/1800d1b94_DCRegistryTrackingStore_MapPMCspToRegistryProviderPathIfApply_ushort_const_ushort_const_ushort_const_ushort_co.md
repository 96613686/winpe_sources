# DCRegistryTrackingStore::MapPMCspToRegistryProviderPathIfApply(ushort const *,ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x1800d1b94`
- end: `0x1800d2049`
- name: `?MapPMCspToRegistryProviderPathIfApply@DCRegistryTrackingStore@@AEAAJPEBG000AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1205`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800d32a0`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x1800600bc`
- `0x1800ce974`
- `0x1800cf734`
- `0x1800d1b94`
- `0x1801006c8`
- `0x180100ad8`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1bd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1d14`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1bd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800d1d14`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800d1beb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800d1beb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d1f62`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d1f62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d1d57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d1e18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d1d57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d1e18`

## string_xrefs

- `0x1800d1c48`: `registry`
- `0x1800d1cbb`: `regRedirectPath`
- `0x1800d1fc5`: `regRedirectPath`
- `0x1800d1c88`: `regRedirectPathRefCount`
- `0x1800d1e45`: `regRedirectPathRefCount`
- `0x1800d1f94`: `regRedirectPathRefCount`
- `0x1800d1ce7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d1dcb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d1e64`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d1fef`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d2027`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DCRegistryTrackingStore::MapPMCspToRegistryProviderPathIfApply(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        int a5,
        HKEY *a6)
{
  int PolicyRegistryRedirectedPath; // eax
  signed int RegistryString; // ebx
  unsigned __int16 **v10; // rax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int RegistryDWORD; // eax
  __int64 v14; // rdx
  unsigned __int16 **v15; // rdx
  LSTATUS v16; // eax
  LSTATUS v17; // eax
  int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  LSTATUS v22; // eax
  const unsigned __int16 *v23; // r9
  int phkResult; // [rsp+20h] [rbp-79h]
  int phkResulta; // [rsp+20h] [rbp-79h]
  int phkResultb; // [rsp+20h] [rbp-79h]
  __int64 v27; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  __int64 *p_lpSubKey; // [rsp+60h] [rbp-39h] BYREF
  HKEY v30; // [rsp+68h] [rbp-31h] BYREF
  char v31; // [rsp+70h] [rbp-29h]
  LPCWSTR v32; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v33; // [rsp+80h] [rbp-19h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-11h] BYREF
  __int64 v35; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int16 *v36[3]; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int64 v37; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  if ( (unsigned int)_o__wcsicmp(L"csp", a2) || !wcsstr(a3, L"vendor/msft/policy") )
    return 0;
  std::wstring::wstring((__int64)v36);
  PolicyRegistryRedirectedPath = DCRegistryTrackingStore::FindPolicyRegistryRedirectedPath(a3, a4, v36);
  RegistryString = PolicyRegistryRedirectedPath;
  if ( PolicyRegistryRedirectedPath < 0 )
  {
    if ( PolicyRegistryRedirectedPath != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)PolicyRegistryRedirectedPath,
        phkResult);
      goto LABEL_56;
    }
    goto LABEL_37;
  }
  hKey = 0;
  lpSubKey = 0;
  v10 = v36;
  if ( v37 > 7 )
    v10 = (unsigned __int16 **)v36[0];
  p_lpSubKey = (__int64 *)&lpSubKey;
  v30 = 0;
  v31 = 1;
  RegistryString = DCStringCchPrintfAllStrings(&v30, qword_18018A5F0, 2, L"registry", v10);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    v11 = (unsigned int)RegistryString;
    v12 = 1113;
LABEL_52:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)v11,
      phkResulta);
    goto LABEL_53;
  }
  v33 = 0;
  RegistryDWORD = DCCDNUtil_GetRegistryDWORD(*a6, 0, L"regRedirectPathRefCount", &v33);
  RegistryString = RegistryDWORD;
  if ( RegistryDWORD < 0 )
  {
    if ( RegistryDWORD == -2147024894 )
    {
      p_lpSubKey = (__int64 *)&hKey;
      v30 = 0;
      v31 = 1;
      v22 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2011Fu, 0, &v30, 0);
      RegistryString = v22;
      if ( v22 > 0 )
        RegistryString = (unsigned __int16)v22 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        v11 = (unsigned int)RegistryString;
        v12 = 1170;
        goto LABEL_52;
      }
      RegistryDWORD = DCCDNUtil_SetRegistryDWORD(*a6, 0, L"regRedirectPathRefCount", 1u);
      RegistryString = RegistryDWORD;
      if ( RegistryDWORD >= 0 )
      {
        v23 = (const unsigned __int16 *)v36;
        if ( v37 > 7 )
          v23 = v36[0];
        RegistryDWORD = DCCDNUtil_SetRegistryString(*a6, 0, L"regRedirectPath", v23, 0);
        RegistryString = RegistryDWORD;
        if ( RegistryDWORD >= 0 )
        {
LABEL_33:
          if ( hKey )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(a6);
            if ( a6 != &hKey )
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                a6,
                hKey);
              hKey = 0;
            }
          }
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_37:
          std::wstring::_Tidy_deallocate(v36);
          return 0;
        }
        v12 = 1173;
      }
      else
      {
        v12 = 1172;
      }
    }
    else
    {
      v12 = 1177;
    }
    v11 = (unsigned int)RegistryDWORD;
    goto LABEL_52;
  }
  v27 = 0;
  p_lpSubKey = &v27;
  v30 = 0;
  v31 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(*a6, 0, L"regRedirectPath", (unsigned __int16 **)&v30);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString >= 0 )
  {
    v15 = v36;
    if ( v37 > 7 )
      v15 = (unsigned __int16 **)v36[0];
    if ( (unsigned int)_o__wcsicmp(v27, v15) )
    {
      RegistryString = -2147418113;
      v14 = 1124;
      goto LABEL_11;
    }
    p_lpSubKey = (__int64 *)&hKey;
    v30 = 0;
    v31 = 1;
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x3011Fu, &v30);
    RegistryString = v16;
    if ( v16 > 0 )
      RegistryString = (unsigned __int16)v16 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v14 = 1134;
      goto LABEL_11;
    }
    v32 = 0;
    p_lpSubKey = (__int64 *)&v32;
    v30 = 0;
    v31 = 1;
    RegistryString = DCStringCchPrintfAllStrings(&v30, L"%s\\%s", 2, a4);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x476,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        a5);
LABEL_23:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
      goto LABEL_12;
    }
    v35 = 0;
    p_lpSubKey = &v35;
    v30 = 0;
    v31 = 1;
    v17 = RegOpenKeyExW(hKey, v32, 0, 0x20119u, &v30);
    RegistryString = v17;
    if ( v17 > 0 )
      RegistryString = (unsigned __int16)v17 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString == -2147024894 )
    {
      v18 = DCCDNUtil_SetRegistryDWORD(*a6, 0, L"regRedirectPathRefCount", v33 + 1);
      RegistryString = v18;
      if ( v18 < 0 )
      {
        v19 = (unsigned int)v18;
        v20 = 1154;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
          (const char *)v19,
          phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
        goto LABEL_23;
      }
    }
    else if ( RegistryString < 0 )
    {
      v19 = (unsigned int)RegistryString;
      v20 = 1157;
      goto LABEL_29;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v32);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v27);
    goto LABEL_33;
  }
  v14 = 1121;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
    (const char *)(unsigned int)RegistryString,
    phkResulta);
LABEL_12:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v27);
LABEL_53:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_56:
  std::wstring::_Tidy_deallocate(v36);
  return (unsigned int)RegistryString;
}

```

## disassembly

```asm
0x1800d1b94  mov     [rsp-8+arg_0], rbx
0x1800d1b99  push    rbp
0x1800d1b9a  push    rdi
0x1800d1b9b  push    r12
0x1800d1b9d  push    r14
0x1800d1b9f  push    r15
0x1800d1ba1  lea     rbp, [rsp-27h]
0x1800d1ba6  sub     rsp, 0C0h
0x1800d1bad  mov     rax, cs:__security_cookie
0x1800d1bb4  xor     rax, rsp
0x1800d1bb7  mov     [rbp+47h+var_28], rax
0x1800d1bbb  mov     r14, r9
0x1800d1bbe  mov     rbx, r8
0x1800d1bc1  mov     r15, qword ptr [rbp+47h+arg_20]
0x1800d1bc5  mov     rdi, [rbp+47h+arg_28]
0x1800d1bc9  lea     rcx, aCsp_0; "csp"
0x1800d1bd0  call    cs:__imp__o__wcsicmp
0x1800d1bd6  xor     r12d, r12d
0x1800d1bd9  test    eax, eax
0x1800d1bdb  jnz     loc_1800D1EF0
0x1800d1be1  lea     rdx, aVendorMsftPoli_2; "vendor/msft/policy"
0x1800d1be8  mov     rcx, rbx; Str
0x1800d1beb  call    cs:__imp_wcsstr
0x1800d1bf1  test    rax, rax
0x1800d1bf4  jz      loc_1800D1EF0
0x1800d1bfa  lea     rcx, [rbp+47h+var_48]
0x1800d1bfe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d1c03  nop
0x1800d1c04  lea     r8, [rbp+47h+var_48]
0x1800d1c08  mov     rdx, r14
0x1800d1c0b  mov     rcx, rbx
0x1800d1c0e  call    ?FindPolicyRegistryRedirectedPath@DCRegistryTrackingStore@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DCRegistryTrackingStore::FindPolicyRegistryRedirectedPath(ushort const *,ushort const *,std::wstring &)
0x1800d1c13  mov     ebx, eax
0x1800d1c15  test    eax, eax
0x1800d1c17  js      loc_1800D2015
0x1800d1c1d  mov     [rbp+47h+hKey], r12
0x1800d1c21  mov     [rbp+47h+lpSubKey], r12
0x1800d1c25  lea     rax, [rbp+47h+var_48]
0x1800d1c29  cmp     [rbp+47h+var_30], 7
0x1800d1c2e  cmova   rax, [rbp+47h+var_48]
0x1800d1c33  lea     rcx, [rbp+47h+lpSubKey]
0x1800d1c37  mov     [rbp+47h+var_80], rcx
0x1800d1c3b  mov     [rbp+47h+var_78], r12
0x1800d1c3f  mov     [rbp+47h+var_70], 1
0x1800d1c43  mov     [rsp+0E0h+phkResult], rax; int
0x1800d1c48  lea     r9, aRegistry_0; "registry"
0x1800d1c4f  lea     r8d, [r12+2]
0x1800d1c54  mov     rdx, cs:qword_18018A5F0
0x1800d1c5b  lea     rcx, [rbp+47h+var_78]
0x1800d1c5f  call    DCStringCchPrintfAllStrings
0x1800d1c64  mov     ebx, eax
0x1800d1c66  lea     rcx, [rbp+47h+var_80]
0x1800d1c6a  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d1c6f  test    ebx, ebx
0x1800d1c71  jns     short loc_1800D1C80
0x1800d1c73  mov     r9d, ebx
0x1800d1c76  mov     edx, 459h
0x1800d1c7b  jmp     loc_1800D1FEF
0x1800d1c80  mov     [rbp+47h+var_60], r12d
0x1800d1c84  lea     r9, [rbp+47h+var_60]; unsigned int *
0x1800d1c88  lea     r8, aRegredirectpat_0; "regRedirectPathRefCount"
0x1800d1c8f  xor     edx, edx; unsigned __int16 *
0x1800d1c91  mov     rcx, [rdi]; HKEY
0x1800d1c94  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800d1c99  mov     ebx, eax
0x1800d1c9b  test    eax, eax
0x1800d1c9d  js      loc_1800D1F16
0x1800d1ca3  mov     [rbp+47h+var_90], r12
0x1800d1ca7  lea     rax, [rbp+47h+var_90]
0x1800d1cab  mov     [rbp+47h+var_80], rax
0x1800d1caf  mov     [rbp+47h+var_78], r12
0x1800d1cb3  mov     [rbp+47h+var_70], 1
0x1800d1cb7  lea     r9, [rbp+47h+var_78]; unsigned __int16 **
0x1800d1cbb  lea     r8, aRegredirectpat; "regRedirectPath"
0x1800d1cc2  xor     edx, edx; unsigned __int16 *
0x1800d1cc4  mov     rcx, [rdi]; HKEY
0x1800d1cc7  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800d1ccc  mov     ebx, eax
0x1800d1cce  lea     rcx, [rbp+47h+var_80]
0x1800d1cd2  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d1cd7  test    ebx, ebx
0x1800d1cd9  jns     short loc_1800D1D02
0x1800d1cdb  mov     edx, 461h; void *
0x1800d1ce0  mov     rcx, [rbp+4Fh]; this
0x1800d1ce4  mov     r9d, ebx; char *
0x1800d1ce7  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d1cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1cf3  nop
0x1800d1cf4  lea     rcx, [rbp+47h+var_90]
0x1800d1cf8  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d1cfd  jmp     loc_1800D2000
0x1800d1d02  lea     rdx, [rbp+47h+var_48]
0x1800d1d06  cmp     [rbp+47h+var_30], 7
0x1800d1d0b  cmova   rdx, [rbp+47h+var_48]
0x1800d1d10  mov     rcx, [rbp+47h+var_90]
0x1800d1d14  call    cs:__imp__o__wcsicmp
0x1800d1d1a  test    eax, eax
0x1800d1d1c  jz      short loc_1800D1D2A
0x1800d1d1e  mov     ebx, 8000FFFFh
0x1800d1d23  mov     edx, 464h
0x1800d1d28  jmp     short loc_1800D1CE0
0x1800d1d2a  lea     rax, [rbp+47h+hKey]
0x1800d1d2e  mov     [rbp+47h+var_80], rax
0x1800d1d32  mov     [rbp+47h+var_78], r12
0x1800d1d36  mov     [rbp+47h+var_70], 1
0x1800d1d3a  lea     rax, [rbp+47h+var_78]
0x1800d1d3e  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800d1d43  mov     r9d, 3011Fh; samDesired
0x1800d1d49  xor     r8d, r8d; ulOptions
0x1800d1d4c  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800d1d50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d1d57  call    cs:__imp_RegOpenKeyExW
0x1800d1d5d  mov     ebx, eax
0x1800d1d5f  test    eax, eax
0x1800d1d61  jle     short loc_1800D1D6C
0x1800d1d63  movzx   ebx, ax
0x1800d1d66  or      ebx, 80070000h
0x1800d1d6c  lea     rcx, [rbp+47h+var_80]
0x1800d1d70  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d1d75  test    ebx, ebx
0x1800d1d77  jns     short loc_1800D1D83
0x1800d1d79  mov     edx, 46Eh
0x1800d1d7e  jmp     loc_1800D1CE0
0x1800d1d83  mov     [rbp+47h+var_68], r12
0x1800d1d87  lea     rax, [rbp+47h+var_68]
0x1800d1d8b  mov     [rbp+47h+var_80], rax
0x1800d1d8f  mov     [rbp+47h+var_78], r12
0x1800d1d93  mov     [rbp+47h+var_70], 1
0x1800d1d97  mov     [rsp+0E0h+phkResult], r15; int
0x1800d1d9c  mov     r9, r14
0x1800d1d9f  mov     r8d, 2
0x1800d1da5  lea     rdx, aSS; "%s\\%s"
0x1800d1dac  lea     rcx, [rbp+47h+var_78]
0x1800d1db0  call    DCStringCchPrintfAllStrings
0x1800d1db5  mov     ebx, eax
0x1800d1db7  lea     rcx, [rbp+47h+var_80]
0x1800d1dbb  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d1dc0  test    ebx, ebx
0x1800d1dc2  jns     short loc_1800D1DEA
0x1800d1dc4  mov     rcx, [rbp+4Fh]; this
0x1800d1dc8  mov     r9d, ebx; char *
0x1800d1dcb  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d1dd2  mov     edx, 476h; void *
0x1800d1dd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1ddc  lea     rcx, [rbp+47h+var_68]
0x1800d1de0  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d1de5  jmp     loc_1800D1CF4
0x1800d1dea  mov     [rbp+47h+var_50], r12
0x1800d1dee  lea     rax, [rbp+47h+var_50]
0x1800d1df2  mov     [rbp+47h+var_80], rax
0x1800d1df6  mov     [rbp+47h+var_78], r12
0x1800d1dfa  mov     [rbp+47h+var_70], 1
0x1800d1dfe  lea     rax, [rbp+47h+var_78]
0x1800d1e02  mov     [rsp+0E0h+phkResult], rax; int
0x1800d1e07  mov     r9d, 20119h; samDesired
0x1800d1e0d  xor     r8d, r8d; ulOptions
0x1800d1e10  mov     rdx, [rbp+47h+var_68]; lpSubKey
0x1800d1e14  mov     rcx, [rbp+47h+hKey]; hKey
0x1800d1e18  call    cs:__imp_RegOpenKeyExW
0x1800d1e1e  mov     ebx, eax
0x1800d1e20  test    eax, eax
0x1800d1e22  jle     short loc_1800D1E2D
0x1800d1e24  movzx   ebx, ax
0x1800d1e27  or      ebx, 80070000h
0x1800d1e2d  lea     rcx, [rbp+47h+var_80]
0x1800d1e31  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d1e36  cmp     ebx, 80070002h
0x1800d1e3c  jnz     short loc_1800D1E82
0x1800d1e3e  mov     r9d, [rbp+47h+var_60]
0x1800d1e42  inc     r9d; unsigned int
0x1800d1e45  lea     r8, aRegredirectpat_0; "regRedirectPathRefCount"
0x1800d1e4c  xor     edx, edx; unsigned __int16 *
0x1800d1e4e  mov     rcx, [rdi]; HKEY
0x1800d1e51  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800d1e56  mov     ebx, eax
0x1800d1e58  test    eax, eax
0x1800d1e5a  jns     short loc_1800D1E90
0x1800d1e5c  mov     r9d, eax; char *
0x1800d1e5f  mov     edx, 482h; void *
0x1800d1e64  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d1e6b  mov     rcx, [rbp+4Fh]; this
0x1800d1e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1e74  lea     rcx, [rbp+47h+var_50]
0x1800d1e78  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d1e7d  jmp     loc_1800D1DDC
0x1800d1e82  test    ebx, ebx
0x1800d1e84  jns     short loc_1800D1E90
0x1800d1e86  mov     r9d, ebx
0x1800d1e89  mov     edx, 485h
0x1800d1e8e  jmp     short loc_1800D1E64
0x1800d1e90  lea     rcx, [rbp+47h+var_50]
0x1800d1e94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d1e99  lea     rcx, [rbp+47h+var_68]
0x1800d1e9d  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d1ea2  nop
0x1800d1ea3  lea     rcx, [rbp+47h+var_90]
0x1800d1ea7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d1eac  cmp     [rbp+47h+hKey], r12
0x1800d1eb0  jz      short loc_1800D1ED3
0x1800d1eb2  mov     rcx, rdi
0x1800d1eb5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1800d1eba  lea     rax, [rbp+47h+hKey]
0x1800d1ebe  cmp     rdi, rax
0x1800d1ec1  jz      short loc_1800D1ED3
0x1800d1ec3  mov     rdx, [rbp+47h+hKey]
0x1800d1ec7  mov     rcx, rdi
0x1800d1eca  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d1ecf  mov     [rbp+47h+hKey], r12
0x1800d1ed3  lea     rcx, [rbp+47h+lpSubKey]
0x1800d1ed7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d1edc  nop
0x1800d1edd  lea     rcx, [rbp+47h+hKey]
0x1800d1ee1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d1ee6  nop
0x1800d1ee7  lea     rcx, [rbp+47h+var_48]
0x1800d1eeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d1ef0  xor     eax, eax
0x1800d1ef2  mov     rcx, [rbp+47h+var_28]
0x1800d1ef6  xor     rcx, rsp; StackCookie
0x1800d1ef9  call    __security_check_cookie
0x1800d1efe  mov     rbx, [rsp+0E0h+arg_0]
0x1800d1f06  add     rsp, 0C0h
0x1800d1f0d  pop     r15
0x1800d1f0f  pop     r14
0x1800d1f11  pop     r12
0x1800d1f13  pop     rdi
0x1800d1f14  pop     rbp
0x1800d1f15  retn
0x1800d1f16  cmp     eax, 80070002h
0x1800d1f1b  jnz     loc_1800D1FE7
0x1800d1f21  lea     rax, [rbp+47h+hKey]
0x1800d1f25  mov     [rbp+47h+var_80], rax
0x1800d1f29  mov     [rbp+47h+var_78], r12
0x1800d1f2d  mov     [rbp+47h+var_70], 1
0x1800d1f31  mov     [rsp+0E0h+lpdwDisposition], r12; lpdwDisposition
0x1800d1f36  lea     rax, [rbp+47h+var_78]
0x1800d1f3a  mov     [rsp+0E0h+var_A8], rax; phkResult
0x1800d1f3f  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800d1f44  mov     [rsp+0E0h+samDesired], 2011Fh; samDesired
0x1800d1f4c  mov     dword ptr [rsp+0E0h+phkResult], r12d; dwOptions
0x1800d1f51  xor     r9d, r9d; lpClass
0x1800d1f54  xor     r8d, r8d; Reserved
0x1800d1f57  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800d1f5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d1f62  call    cs:__imp_RegCreateKeyExW
0x1800d1f68  mov     ebx, eax
0x1800d1f6a  test    eax, eax
0x1800d1f6c  jle     short loc_1800D1F77
0x1800d1f6e  movzx   ebx, ax
0x1800d1f71  or      ebx, 80070000h
0x1800d1f77  lea     rcx, [rbp+47h+var_80]
0x1800d1f7b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d1f80  test    ebx, ebx
0x1800d1f82  jns     short loc_1800D1F8E
0x1800d1f84  mov     r9d, ebx
0x1800d1f87  mov     edx, 492h
0x1800d1f8c  jmp     short loc_1800D1FEF
0x1800d1f8e  mov     r9d, 1; unsigned int
0x1800d1f94  lea     r8, aRegredirectpat_0; "regRedirectPathRefCount"
0x1800d1f9b  xor     edx, edx; unsigned __int16 *
0x1800d1f9d  mov     rcx, [rdi]; HKEY
0x1800d1fa0  call    ?DCCDNUtil_SetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; DCCDNUtil_SetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800d1fa5  mov     ebx, eax
0x1800d1fa7  test    eax, eax
0x1800d1fa9  jns     short loc_1800D1FB2
0x1800d1fab  mov     edx, 494h
0x1800d1fb0  jmp     short loc_1800D1FEC
0x1800d1fb2  lea     r9, [rbp+47h+var_48]
0x1800d1fb6  cmp     [rbp+47h+var_30], 7
0x1800d1fbb  cmova   r9, [rbp+47h+var_48]; unsigned __int16 *
0x1800d1fc0  mov     byte ptr [rsp+0E0h+phkResult], r12b; bool
0x1800d1fc5  lea     r8, aRegredirectpat; "regRedirectPath"
0x1800d1fcc  xor     edx, edx; unsigned __int16 *
0x1800d1fce  mov     rcx, [rdi]; HKEY
0x1800d1fd1  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1800d1fd6  mov     ebx, eax
0x1800d1fd8  test    eax, eax
0x1800d1fda  jns     loc_1800D1EAC
0x1800d1fe0  mov     edx, 495h
0x1800d1fe5  jmp     short loc_1800D1FEC
0x1800d1fe7  mov     edx, 499h; void *
0x1800d1fec  mov     r9d, eax; char *
0x1800d1fef  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d1ff6  mov     rcx, [rbp+4Fh]; this
0x1800d1ffa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d1fff  nop
0x1800d2000  lea     rcx, [rbp+47h+lpSubKey]
0x1800d2004  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d2009  nop
0x1800d200a  lea     rcx, [rbp+47h+hKey]
0x1800d200e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2013  jmp     short loc_1800D2039
0x1800d2015  cmp     eax, 80070002h
0x1800d201a  jz      loc_1800D1EE7
0x1800d2020  mov     rcx, [rbp+4Fh]; this
0x1800d2024  mov     r9d, eax; char *
0x1800d2027  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d202e  mov     edx, 4A5h; void *
0x1800d2033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2038  nop
  ... truncated ...
```
