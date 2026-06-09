# DCRegistryTrackingStore::MigrateAllPoliciesToRegistryProviderAuthorityTracking(void)

- ea: `0x1800d2050`
- end: `0x1800d24dd`
- name: `?MigrateAllPoliciesToRegistryProviderAuthorityTracking@DCRegistryTrackingStore@@SAJXZ`
- size: `1165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800ced20`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x1800192b4`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x1800d2050`
- `0x1800d24e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d217a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d22b1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d23ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d217a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d22b1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d23ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d211d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d225e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d235c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d211d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d225e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d235c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d20b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d21fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d22fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d20b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d21fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d22fc`

## string_xrefs

- `0x1800d2431`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d246e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d2496`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d21a5`: `\vendor\msft\policy\config`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 DCRegistryTrackingStore::MigrateAllPoliciesToRegistryProviderAuthorityTracking(void)
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  LSTATUS v2; // eax
  signed int v3; // ebx
  __int64 v4; // rdx
  DWORD i; // r14d
  LSTATUS v6; // eax
  __int64 v7; // rax
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD v11; // esi
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  DWORD j; // edi
  LSTATUS v16; // eax
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v25; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY v27; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-88h] BYREF
  DWORD v29; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD v30; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY *p_hKey; // [rsp+90h] [rbp-70h] BYREF
  HKEY v33; // [rsp+98h] [rbp-68h] BYREF
  char v34; // [rsp+A0h] [rbp-60h]
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR v38[264]; // [rsp+4F0h] [rbp+3F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+648h]

  hKey = 0;
  p_hKey = &hKey;
  v33 = 0;
  v34 = 1;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, qword_18018A5F8, 0, 0x30119u, &v33);
  v1 = v0;
  if ( v0 > 0 )
    v1 = (unsigned __int16)v0 | 0x80070000;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v1 == -2147024894 )
  {
LABEL_54:
    v3 = 0;
  }
  else
  {
    cSubKeys = 0;
    v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v3 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= cSubKeys )
          goto LABEL_54;
        cchName = 260;
        v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        if ( v3 < 0 )
          break;
        v7 = std::wstring::wstring((__int64)&p_hKey, (__int64)Name);
        std::operator+<unsigned short>(lpSubKey, v7, L"\\vendor\\msft\\policy\\config");
        std::wstring::_Tidy_deallocate(&p_hKey);
        v25 = 0;
        p_hKey = &v25;
        v33 = 0;
        v34 = 1;
        v8 = (const WCHAR *)lpSubKey;
        if ( lpSubKey[3] > (LPCWSTR)7 )
          v8 = lpSubKey[0];
        v9 = RegOpenKeyExW(hKey, v8, 0, 0x20119u, &v33);
        v3 = v9;
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v3 < 0 )
        {
          v20 = 1414;
          goto LABEL_50;
        }
        v29 = 0;
        v10 = RegQueryInfoKeyW(v25, 0, 0, 0, &v29, 0, 0, 0, 0, 0, 0, 0);
        v3 = v10;
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
        if ( v3 < 0 )
        {
          v20 = 1418;
          goto LABEL_50;
        }
        v11 = 0;
LABEL_22:
        if ( v11 < v29 )
        {
          cchName = 260;
          v12 = RegEnumKeyExW(v25, v11, SubKey, &cchName, 0, 0, 0, 0);
          v3 = v12;
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
          if ( v3 >= 0 )
          {
            v27 = 0;
            p_hKey = &v27;
            v33 = 0;
            v34 = 1;
            v13 = RegOpenKeyExW(v25, SubKey, 0, 0x20119u, &v33);
            v3 = v13;
            if ( v13 > 0 )
              v3 = (unsigned __int16)v13 | 0x80070000;
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
            if ( v3 < 0 )
            {
              v19 = 1439;
            }
            else
            {
              v30 = 0;
              v14 = RegQueryInfoKeyW(v27, 0, 0, 0, &v30, 0, 0, 0, 0, 0, 0, 0);
              v3 = v14;
              if ( v14 > 0 )
                v3 = (unsigned __int16)v14 | 0x80070000;
              if ( v3 < 0 )
              {
                v19 = 1443;
              }
              else
              {
                for ( j = 0; ; ++j )
                {
                  if ( j >= v30 )
                  {
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
                    ++v11;
                    goto LABEL_22;
                  }
                  cchName = 260;
                  v16 = RegEnumKeyExW(v27, j, v38, &cchName, 0, 0, 0, 0);
                  v3 = v16;
                  if ( v16 > 0 )
                    v3 = (unsigned __int16)v16 | 0x80070000;
                  if ( v3 < 0 )
                    break;
                  v17 = DCRegistryTrackingStore::MigratePolicyToRegistryProviderAuthorityTracking(Name, SubKey, v38);
                  v3 = v17;
                  if ( v17 < 0 )
                  {
                    v18 = (unsigned int)v17;
                    v19 = 1457;
                    goto LABEL_46;
                  }
                }
                v19 = 1456;
              }
            }
            v18 = (unsigned int)v3;
LABEL_46:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
              (const char *)v18,
              phkResultb);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v27);
            goto LABEL_51;
          }
          v20 = 1431;
LABEL_50:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
            (const char *)(unsigned int)v3,
            phkResulta);
LABEL_51:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
          std::wstring::_Tidy_deallocate(lpSubKey);
          goto LABEL_55;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
        std::wstring::_Tidy_deallocate(lpSubKey);
      }
      v4 = 1404;
    }
    else
    {
      v4 = 1391;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
  }
LABEL_55:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800d2050  push    rbp
0x1800d2052  push    rbx
0x1800d2053  push    rsi
0x1800d2054  push    rdi
0x1800d2055  push    r12
0x1800d2057  push    r14
0x1800d2059  push    r15
0x1800d205b  lea     rbp, [rsp-610h]
0x1800d2063  sub     rsp, 710h
0x1800d206a  mov     rax, cs:__security_cookie
0x1800d2071  xor     rax, rsp
0x1800d2074  mov     [rbp+640h+var_40], rax
0x1800d207b  xor     r15d, r15d
0x1800d207e  mov     [rbp+640h+hKey], r15
0x1800d2082  lea     rax, [rbp+640h+hKey]
0x1800d2086  mov     [rbp+640h+var_6B0], rax
0x1800d208a  mov     [rbp+640h+var_6A8], r15
0x1800d208e  mov     [rbp+640h+var_6A0], 1
0x1800d2092  lea     rax, [rbp+640h+var_6A8]
0x1800d2096  mov     [rsp+740h+phkResult], rax; phkResult
0x1800d209b  mov     r9d, 30119h; samDesired
0x1800d20a1  xor     r8d, r8d; ulOptions
0x1800d20a4  mov     rdx, cs:qword_18018A5F8; lpSubKey
0x1800d20ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d20b2  call    cs:__imp_RegOpenKeyExW
0x1800d20b8  mov     ebx, eax
0x1800d20ba  mov     r12d, 80070000h
0x1800d20c0  test    eax, eax
0x1800d20c2  jle     short loc_1800D20CA
0x1800d20c4  movzx   ebx, ax
0x1800d20c7  or      ebx, r12d
0x1800d20ca  lea     rcx, [rbp+640h+var_6B0]
0x1800d20ce  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d20d3  cmp     ebx, 80070002h
0x1800d20d9  jz      loc_1800D24AE
0x1800d20df  mov     [rsp+740h+cSubKeys], r15d
0x1800d20e4  mov     [rsp+740h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d20e9  mov     [rsp+740h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d20ee  mov     [rsp+740h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d20f3  mov     [rsp+740h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d20f8  mov     [rsp+740h+lpcValues], r15; lpcValues
0x1800d20fd  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d2102  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d2107  lea     rax, [rsp+740h+cSubKeys]
0x1800d210c  mov     [rsp+740h+phkResult], rax; lpcSubKeys
0x1800d2111  xor     r9d, r9d; lpReserved
0x1800d2114  xor     r8d, r8d; lpcchClass
0x1800d2117  xor     edx, edx; lpClass
0x1800d2119  mov     rcx, [rbp+640h+hKey]; hKey
0x1800d211d  call    cs:__imp_RegQueryInfoKeyW
0x1800d2123  mov     ebx, eax
0x1800d2125  test    eax, eax
0x1800d2127  jle     short loc_1800D212F
0x1800d2129  movzx   ebx, ax
0x1800d212c  or      ebx, r12d
0x1800d212f  test    ebx, ebx
0x1800d2131  jns     short loc_1800D213D
0x1800d2133  mov     edx, 56Fh
0x1800d2138  jmp     loc_1800D2496
0x1800d213d  mov     r14d, r15d
0x1800d2140  cmp     r14d, [rsp+740h+cSubKeys]
0x1800d2145  jnb     loc_1800D24AE
0x1800d214b  mov     [rsp+740h+cchName], 104h
0x1800d2153  mov     [rsp+740h+lpcValues], r15; lpftLastWriteTime
0x1800d2158  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcchClass
0x1800d215d  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpClass
0x1800d2162  mov     [rsp+740h+phkResult], r15; int
0x1800d2167  lea     r9, [rsp+740h+cchName]; lpcchName
0x1800d216c  lea     r8, [rbp+640h+Name]; lpName
0x1800d2173  mov     edx, r14d; dwIndex
0x1800d2176  mov     rcx, [rbp+640h+hKey]; hKey
0x1800d217a  call    cs:__imp_RegEnumKeyExW
0x1800d2180  mov     ebx, eax
0x1800d2182  test    eax, eax
0x1800d2184  jle     short loc_1800D218C
0x1800d2186  movzx   ebx, ax
0x1800d2189  or      ebx, r12d
0x1800d218c  test    ebx, ebx
0x1800d218e  js      loc_1800D2491
0x1800d2194  lea     rdx, [rbp+640h+Name]
0x1800d219b  lea     rcx, [rbp+640h+var_6B0]
0x1800d219f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d21a4  nop
0x1800d21a5  lea     r8, aVendorMsftPoli_3; "\\vendor\\msft\\policy\\config"
0x1800d21ac  mov     rdx, rax
0x1800d21af  lea     rcx, [rbp+640h+lpSubKey]
0x1800d21b3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800d21b8  nop
0x1800d21b9  lea     rcx, [rbp+640h+var_6B0]
0x1800d21bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d21c2  mov     [rsp+740h+var_6E0], r15
0x1800d21c7  lea     rax, [rsp+740h+var_6E0]
0x1800d21cc  mov     [rbp+640h+var_6B0], rax
0x1800d21d0  mov     [rbp+640h+var_6A8], r15
0x1800d21d4  mov     [rbp+640h+var_6A0], 1
0x1800d21d8  lea     rdx, [rbp+640h+lpSubKey]
0x1800d21dc  cmp     [rbp+640h+var_678], 7
0x1800d21e1  cmova   rdx, [rbp+640h+lpSubKey]; lpSubKey
0x1800d21e6  lea     rax, [rbp+640h+var_6A8]
0x1800d21ea  mov     [rsp+740h+phkResult], rax; int
0x1800d21ef  mov     r9d, 20119h; samDesired
0x1800d21f5  xor     r8d, r8d; ulOptions
0x1800d21f8  mov     rcx, [rbp+640h+hKey]; hKey
0x1800d21fc  call    cs:__imp_RegOpenKeyExW
0x1800d2202  mov     ebx, eax
0x1800d2204  test    eax, eax
0x1800d2206  jle     short loc_1800D220E
0x1800d2208  movzx   ebx, ax
0x1800d220b  or      ebx, r12d
0x1800d220e  lea     rcx, [rbp+640h+var_6B0]
0x1800d2212  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d2217  test    ebx, ebx
0x1800d2219  js      loc_1800D245F
0x1800d221f  mov     [rsp+740h+var_6C4], r15d
0x1800d2224  mov     [rsp+740h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d2229  mov     [rsp+740h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d222e  mov     [rsp+740h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d2233  mov     [rsp+740h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d2238  mov     [rsp+740h+lpcValues], r15; lpcValues
0x1800d223d  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d2242  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d2247  lea     rax, [rsp+740h+var_6C4]
0x1800d224c  mov     [rsp+740h+phkResult], rax; lpcSubKeys
0x1800d2251  xor     r9d, r9d; lpReserved
0x1800d2254  xor     r8d, r8d; lpcchClass
0x1800d2257  xor     edx, edx; lpClass
0x1800d2259  mov     rcx, [rsp+740h+var_6E0]; hKey
0x1800d225e  call    cs:__imp_RegQueryInfoKeyW
0x1800d2264  mov     ebx, eax
0x1800d2266  test    eax, eax
0x1800d2268  jle     short loc_1800D2270
0x1800d226a  movzx   ebx, ax
0x1800d226d  or      ebx, r12d
0x1800d2270  test    ebx, ebx
0x1800d2272  js      loc_1800D2458
0x1800d2278  mov     esi, r15d
0x1800d227b  cmp     esi, [rsp+740h+var_6C4]
0x1800d227f  jnb     loc_1800D23F5
0x1800d2285  mov     [rsp+740h+cchName], 104h
0x1800d228d  mov     [rsp+740h+lpcValues], r15; lpftLastWriteTime
0x1800d2292  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcchClass
0x1800d2297  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpClass
0x1800d229c  mov     [rsp+740h+phkResult], r15; lpReserved
0x1800d22a1  lea     r9, [rsp+740h+cchName]; lpcchName
0x1800d22a6  lea     r8, [rbp+640h+SubKey]; lpName
0x1800d22aa  mov     edx, esi; dwIndex
0x1800d22ac  mov     rcx, [rsp+740h+var_6E0]; hKey
0x1800d22b1  call    cs:__imp_RegEnumKeyExW
0x1800d22b7  mov     ebx, eax
0x1800d22b9  test    eax, eax
0x1800d22bb  jle     short loc_1800D22C3
0x1800d22bd  movzx   ebx, ax
0x1800d22c0  or      ebx, r12d
0x1800d22c3  test    ebx, ebx
0x1800d22c5  js      loc_1800D2451
0x1800d22cb  mov     [rsp+740h+var_6D0], r15
0x1800d22d0  lea     rax, [rsp+740h+var_6D0]
0x1800d22d5  mov     [rbp+640h+var_6B0], rax
0x1800d22d9  mov     [rbp+640h+var_6A8], r15
0x1800d22dd  mov     [rbp+640h+var_6A0], 1
0x1800d22e1  lea     rax, [rbp+640h+var_6A8]
0x1800d22e5  mov     [rsp+740h+phkResult], rax; int
0x1800d22ea  mov     r9d, 20119h; samDesired
0x1800d22f0  xor     r8d, r8d; ulOptions
0x1800d22f3  lea     rdx, [rbp+640h+SubKey]; lpSubKey
0x1800d22f7  mov     rcx, [rsp+740h+var_6E0]; hKey
0x1800d22fc  call    cs:__imp_RegOpenKeyExW
0x1800d2302  mov     ebx, eax
0x1800d2304  test    eax, eax
0x1800d2306  jle     short loc_1800D230E
0x1800d2308  movzx   ebx, ax
0x1800d230b  or      ebx, r12d
0x1800d230e  lea     rcx, [rbp+640h+var_6B0]
0x1800d2312  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d2317  test    ebx, ebx
0x1800d2319  js      loc_1800D2429
0x1800d231f  mov     [rbp+640h+var_6C0], r15d
0x1800d2323  mov     [rsp+740h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d2328  mov     [rsp+740h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d232d  mov     [rsp+740h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d2332  mov     [rsp+740h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d2337  mov     [rsp+740h+lpcValues], r15; lpcValues
0x1800d233c  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d2341  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d2346  lea     rax, [rbp+640h+var_6C0]
0x1800d234a  mov     [rsp+740h+phkResult], rax; lpcSubKeys
0x1800d234f  xor     r9d, r9d; lpReserved
0x1800d2352  xor     r8d, r8d; lpcchClass
0x1800d2355  xor     edx, edx; lpClass
0x1800d2357  mov     rcx, [rsp+740h+var_6D0]; hKey
0x1800d235c  call    cs:__imp_RegQueryInfoKeyW
0x1800d2362  mov     ebx, eax
0x1800d2364  test    eax, eax
0x1800d2366  jle     short loc_1800D236E
0x1800d2368  movzx   ebx, ax
0x1800d236b  or      ebx, r12d
0x1800d236e  test    ebx, ebx
0x1800d2370  js      loc_1800D2422
0x1800d2376  mov     edi, r15d
0x1800d2379  cmp     edi, [rbp+640h+var_6C0]
0x1800d237c  jnb     short loc_1800D23E4
0x1800d237e  mov     [rsp+740h+cchName], 104h
0x1800d2386  mov     [rsp+740h+lpcValues], r15; lpftLastWriteTime
0x1800d238b  mov     [rsp+740h+lpcbMaxClassLen], r15; lpcchClass
0x1800d2390  mov     [rsp+740h+lpcbMaxSubKeyLen], r15; lpClass
0x1800d2395  mov     [rsp+740h+phkResult], r15; lpReserved
0x1800d239a  lea     r9, [rsp+740h+cchName]; lpcchName
0x1800d239f  lea     r8, [rbp+640h+var_250]; lpName
0x1800d23a6  mov     edx, edi; dwIndex
0x1800d23a8  mov     rcx, [rsp+740h+var_6D0]; hKey
0x1800d23ad  call    cs:__imp_RegEnumKeyExW
0x1800d23b3  mov     ebx, eax
0x1800d23b5  test    eax, eax
0x1800d23b7  jle     short loc_1800D23BF
0x1800d23b9  movzx   ebx, ax
0x1800d23bc  or      ebx, r12d
0x1800d23bf  test    ebx, ebx
0x1800d23c1  js      short loc_1800D241B
0x1800d23c3  lea     r8, [rbp+640h+var_250]; unsigned __int16 *
0x1800d23ca  lea     rdx, [rbp+640h+SubKey]; unsigned __int16 *
0x1800d23ce  lea     rcx, [rbp+640h+Name]; unsigned __int16 *
0x1800d23d5  call    ?MigratePolicyToRegistryProviderAuthorityTracking@DCRegistryTrackingStore@@CAJPEBG00@Z; DCRegistryTrackingStore::MigratePolicyToRegistryProviderAuthorityTracking(ushort const *,ushort const *,ushort const *)
0x1800d23da  mov     ebx, eax
0x1800d23dc  test    eax, eax
0x1800d23de  js      short loc_1800D2411
0x1800d23e0  inc     edi
0x1800d23e2  jmp     short loc_1800D2379
0x1800d23e4  lea     rcx, [rsp+740h+var_6D0]
0x1800d23e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d23ee  inc     esi
0x1800d23f0  jmp     loc_1800D227B
0x1800d23f5  lea     rcx, [rsp+740h+var_6E0]
0x1800d23fa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d23ff  nop
0x1800d2400  lea     rcx, [rbp+640h+lpSubKey]
0x1800d2404  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d2409  inc     r14d
0x1800d240c  jmp     loc_1800D2140
0x1800d2411  mov     r9d, eax
0x1800d2414  mov     edx, 5B1h
0x1800d2419  jmp     short loc_1800D2431
0x1800d241b  mov     edx, 5B0h
0x1800d2420  jmp     short loc_1800D242E
0x1800d2422  mov     edx, 5A3h
0x1800d2427  jmp     short loc_1800D242E
0x1800d2429  mov     edx, 59Fh; void *
0x1800d242e  mov     r9d, ebx; char *
0x1800d2431  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d2438  mov     rcx, [rbp+648h]; this
0x1800d243f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2444  nop
0x1800d2445  lea     rcx, [rsp+740h+var_6D0]
0x1800d244a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d244f  jmp     short loc_1800D247B
0x1800d2451  mov     edx, 597h
0x1800d2456  jmp     short loc_1800D2464
0x1800d2458  mov     edx, 58Ah
0x1800d245d  jmp     short loc_1800D2464
0x1800d245f  mov     edx, 586h; void *
0x1800d2464  mov     rcx, [rbp+648h]; this
0x1800d246b  mov     r9d, ebx; char *
0x1800d246e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d2475  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d247a  nop
0x1800d247b  lea     rcx, [rsp+740h+var_6E0]
0x1800d2480  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2485  nop
0x1800d2486  lea     rcx, [rbp+640h+lpSubKey]
0x1800d248a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d248f  jmp     short loc_1800D24B1
0x1800d2491  mov     edx, 57Ch; void *
0x1800d2496  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d249d  mov     r9d, ebx; char *
0x1800d24a0  mov     rcx, [rbp+648h]; this
0x1800d24a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d24ac  jmp     short loc_1800D24B1
0x1800d24ae  mov     ebx, r15d
0x1800d24b1  lea     rcx, [rbp+640h+hKey]
0x1800d24b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d24ba  mov     eax, ebx
0x1800d24bc  mov     rcx, [rbp+640h+var_40]
0x1800d24c3  xor     rcx, rsp; StackCookie
0x1800d24c6  call    __security_check_cookie
0x1800d24cb  add     rsp, 710h
0x1800d24d2  pop     r15
0x1800d24d4  pop     r14
0x1800d24d6  pop     r12
0x1800d24d8  pop     rdi
0x1800d24d9  pop     rsi
0x1800d24da  pop     rbx
0x1800d24db  pop     rbp
0x1800d24dc  retn
```
