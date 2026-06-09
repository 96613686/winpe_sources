# ThemeAppModelWrapper::CleanupOnAppPackageUninstall(ushort const *,ushort const *)

- ea: `0x180269d68`
- end: `0x18026a10e`
- name: `?CleanupOnAppPackageUninstall@ThemeAppModelWrapper@@SAJPEBG0@Z`
- size: `934`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180111fc0`
- `0x18026cd68`

## callees

- `0x18000c840`
- `0x180019a20`
- `0x1800234f8`
- `0x18002373c`
- `0x18002b9f0`
- `0x18002e1f4`
- `0x180041004`
- `0x180228318`
- `0x180269d68`
- `0x18026a938`
- `0x18026b000`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180269ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180269ede`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180269e86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180269ef7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18026a06c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180269e86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180269ef7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18026a06c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180269e2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a000`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180269e2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026a000`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ThemeAppModelWrapper::CleanupOnAppPackageUninstall(LPCWSTR lpValueName, const unsigned __int16 *a2)
{
  int ThemeNameFromAppxName; // eax
  unsigned int v4; // edi
  unsigned int v6; // edi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int ExtensionKey; // eax
  unsigned int v14; // edi
  const WCHAR *v15; // rax
  unsigned int v16; // edi
  unsigned int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-2A8h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-2A8h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-2A8h]
  DWORD dwOptionsc; // [rsp+20h] [rbp-2A8h]
  HKEY hKey; // [rsp+50h] [rbp-278h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-270h] BYREF
  HKEY v26; // [rsp+60h] [rbp-268h] BYREF
  HKEY *p_hKey; // [rsp+68h] [rbp-260h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-258h] BYREF
  char v29; // [rsp+78h] [rbp-250h]
  _BYTE v30[32]; // [rsp+80h] [rbp-248h] BYREF
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  cbData = 260;
  ThemeNameFromAppxName = ThemeAppModelWrapper::GetThemeNameFromAppxName(lpValueName, ValueName, &cbData);
  v4 = ThemeNameFromAppxName;
  if ( ThemeNameFromAppxName >= 0 )
  {
    hKey = 0;
    p_hKey = &hKey;
    phkResult = 0;
    v29 = 1;
    v6 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize\\ThemeAppxMapping",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &phkResult,
           0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x24E,
             (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
             (const char *)v6,
             dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v7;
    }
    else
    {
      v8 = RegDeleteValueW(hKey, ValueName);
      if ( v8 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x24F,
               (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
               (const char *)v8,
               dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v9;
      }
      else if ( CompareStringOrdinal(lpValueName, -1, ValueName, -1, 0) == 2
             || (v10 = RegDeleteValueW(hKey, lpValueName)) == 0 )
      {
        std::wstring::wstring(v30);
        ExtensionKey = GetExtensionKey(v12, lpValueName, v30);
        v14 = ExtensionKey;
        if ( ExtensionKey >= 0 )
        {
          v26 = 0;
          p_hKey = &v26;
          phkResult = 0;
          v29 = 1;
          v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30);
          v16 = RegCreateKeyExW(HKEY_CURRENT_USER, v15, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
          if ( v16 )
          {
            v17 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x25B,
                    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\theme"
                                  "appmodelwrapper.cpp",
                    (const char *)v16,
                    dwOptionsc);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
            std::wstring::_Tidy_deallocate(v30);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            return v17;
          }
          else
          {
            v18 = RegDeleteValueW(v26, lpValueName);
            if ( v18 )
            {
              v19 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x25C,
                      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\the"
                                    "meappmodelwrapper.cpp",
                      (const char *)v18,
                      dwOptionsc);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
              std::wstring::_Tidy_deallocate(v30);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return v19;
            }
            else
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
              std::wstring::_Tidy_deallocate(v30);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
              return 0;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x257,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
            (const char *)(unsigned int)ExtensionKey,
            dwOptionsb);
          std::wstring::_Tidy_deallocate(v30);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v14;
        }
      }
      else
      {
        v11 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x253,
                (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
                (const char *)v10,
                dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v11;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\themeappx\\lib\\themeappmodelwrapper.cpp",
      (const char *)(unsigned int)ThemeNameFromAppxName,
      dwOptions);
    return v4;
  }
}

```

## disassembly

```asm
0x180269d68  mov     [rsp+arg_8], rbx
0x180269d6d  push    rdi
0x180269d6e  sub     rsp, 2C0h
0x180269d75  mov     rax, cs:__security_cookie
0x180269d7c  xor     rax, rsp
0x180269d7f  mov     [rsp+2C8h+var_18], rax
0x180269d87  mov     rbx, rcx
0x180269d8a  mov     [rsp+2C8h+cbData], 104h
0x180269d92  lea     r8, [rsp+2C8h+cbData]; lpcbData
0x180269d97  lea     rdx, [rsp+2C8h+ValueName]; unsigned __int16 *
0x180269d9f  call    ?GetThemeNameFromAppxName@ThemeAppModelWrapper@@SAJPEBGPEAGAEAK@Z; ThemeAppModelWrapper::GetThemeNameFromAppxName(ushort const *,ushort *,ulong &)
0x180269da4  mov     edi, eax
0x180269da6  test    eax, eax
0x180269da8  jns     short loc_180269DCD
0x180269daa  mov     rcx, [rsp+2C8h]; this
0x180269db2  mov     r9d, eax; char *
0x180269db5  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269dbc  mov     edx, 24Bh; void *
0x180269dc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269dc6  mov     eax, edi
0x180269dc8  jmp     loc_18026A0EC
0x180269dcd  mov     [rsp+2C8h+hKey], 0
0x180269dd6  lea     rax, [rsp+2C8h+hKey]
0x180269ddb  mov     [rsp+2C8h+var_260], rax
0x180269de0  mov     [rsp+2C8h+var_258], 0
0x180269de9  mov     [rsp+2C8h+var_250], 1
0x180269dee  mov     [rsp+2C8h+lpdwDisposition], 0; lpdwDisposition
0x180269df7  lea     rax, [rsp+2C8h+var_258]
0x180269dfc  mov     [rsp+2C8h+phkResult], rax; phkResult
0x180269e01  mov     [rsp+2C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180269e0a  mov     [rsp+2C8h+samDesired], 0F003Fh; samDesired
0x180269e12  mov     [rsp+2C8h+dwOptions], 0; unsigned int
0x180269e1a  xor     r9d, r9d; lpClass
0x180269e1d  xor     r8d, r8d; Reserved
0x180269e20  lea     rdx, aSoftwareMicros_71; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180269e27  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180269e2e  call    cs:__imp_RegCreateKeyExW
0x180269e35  nop     dword ptr [rax+rax+00h]
0x180269e3a  mov     edi, eax
0x180269e3c  lea     rcx, [rsp+2C8h+var_260]
0x180269e41  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180269e46  test    edi, edi
0x180269e48  jz      short loc_180269E79
0x180269e4a  mov     rcx, [rsp+2C8h]; this
0x180269e52  mov     r9d, edi; char *
0x180269e55  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269e5c  mov     edx, 24Eh; void *
0x180269e61  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180269e66  mov     ebx, eax
0x180269e68  lea     rcx, [rsp+2C8h+hKey]
0x180269e6d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269e72  mov     eax, ebx
0x180269e74  jmp     loc_18026A0EC
0x180269e79  lea     rdx, [rsp+2C8h+ValueName]; lpValueName
0x180269e81  mov     rcx, [rsp+2C8h+hKey]; hKey
0x180269e86  call    cs:__imp_RegDeleteValueW
0x180269e8d  nop     dword ptr [rax+rax+00h]
0x180269e92  test    eax, eax
0x180269e94  jz      short loc_180269EC5
0x180269e96  mov     rcx, [rsp+2C8h]; this
0x180269e9e  mov     r9d, eax; char *
0x180269ea1  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269ea8  mov     edx, 24Fh; void *
0x180269ead  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180269eb2  mov     ebx, eax
0x180269eb4  lea     rcx, [rsp+2C8h+hKey]
0x180269eb9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269ebe  mov     eax, ebx
0x180269ec0  jmp     loc_18026A0EC
0x180269ec5  mov     [rsp+2C8h+dwOptions], 0; int
0x180269ecd  or      edx, 0FFFFFFFFh; cchCount1
0x180269ed0  mov     r9d, edx; cchCount2
0x180269ed3  lea     r8, [rsp+2C8h+ValueName]; lpString2
0x180269edb  mov     rcx, rbx; lpString1
0x180269ede  call    cs:__imp_CompareStringOrdinal
0x180269ee5  nop     dword ptr [rax+rax+00h]
0x180269eea  cmp     eax, 2
0x180269eed  jz      short loc_180269F36
0x180269eef  mov     rdx, rbx; lpValueName
0x180269ef2  mov     rcx, [rsp+2C8h+hKey]; hKey
0x180269ef7  call    cs:__imp_RegDeleteValueW
0x180269efe  nop     dword ptr [rax+rax+00h]
0x180269f03  test    eax, eax
0x180269f05  jz      short loc_180269F36
0x180269f07  mov     rcx, [rsp+2C8h]; this
0x180269f0f  mov     r9d, eax; char *
0x180269f12  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269f19  mov     edx, 253h; void *
0x180269f1e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180269f23  mov     ebx, eax
0x180269f25  lea     rcx, [rsp+2C8h+hKey]
0x180269f2a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269f2f  mov     eax, ebx
0x180269f31  jmp     loc_18026A0EC
0x180269f36  lea     rcx, [rsp+2C8h+var_248]; void *
0x180269f3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180269f43  nop
0x180269f44  lea     r8, [rsp+2C8h+var_248]
0x180269f4c  mov     rdx, rbx
0x180269f4f  call    ?GetExtensionKey@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetExtensionKey(ushort const *,ushort const *,std::wstring &)
0x180269f54  mov     edi, eax
0x180269f56  test    eax, eax
0x180269f58  jns     short loc_180269F96
0x180269f5a  mov     rcx, [rsp+2C8h]; this
0x180269f62  mov     r9d, eax; char *
0x180269f65  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x180269f6c  mov     edx, 257h; void *
0x180269f71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269f76  nop
0x180269f77  lea     rcx, [rsp+2C8h+var_248]
0x180269f7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180269f84  nop
0x180269f85  lea     rcx, [rsp+2C8h+hKey]
0x180269f8a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180269f8f  mov     eax, edi
0x180269f91  jmp     loc_18026A0EC
0x180269f96  mov     [rsp+2C8h+var_268], 0
0x180269f9f  lea     rax, [rsp+2C8h+var_268]
0x180269fa4  mov     [rsp+2C8h+var_260], rax
0x180269fa9  mov     [rsp+2C8h+var_258], 0
0x180269fb2  mov     [rsp+2C8h+var_250], 1
0x180269fb7  lea     rcx, [rsp+2C8h+var_248]
0x180269fbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180269fc4  mov     rdx, rax; lpSubKey
0x180269fc7  mov     [rsp+2C8h+lpdwDisposition], 0; lpdwDisposition
0x180269fd0  lea     rax, [rsp+2C8h+var_258]
0x180269fd5  mov     [rsp+2C8h+phkResult], rax; phkResult
0x180269fda  mov     [rsp+2C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180269fe3  mov     [rsp+2C8h+samDesired], 0F003Fh; samDesired
0x180269feb  mov     [rsp+2C8h+dwOptions], 0; unsigned int
0x180269ff3  xor     r9d, r9d; lpClass
0x180269ff6  xor     r8d, r8d; Reserved
0x180269ff9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18026a000  call    cs:__imp_RegCreateKeyExW
0x18026a007  nop     dword ptr [rax+rax+00h]
0x18026a00c  mov     edi, eax
0x18026a00e  lea     rcx, [rsp+2C8h+var_260]
0x18026a013  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18026a018  test    edi, edi
0x18026a01a  jz      short loc_18026A064
0x18026a01c  mov     rcx, [rsp+2C8h]; this
0x18026a024  mov     r9d, edi; char *
0x18026a027  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a02e  mov     edx, 25Bh; void *
0x18026a033  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026a038  mov     ebx, eax
0x18026a03a  lea     rcx, [rsp+2C8h+var_268]
0x18026a03f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a044  nop
0x18026a045  lea     rcx, [rsp+2C8h+var_248]
0x18026a04d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a052  nop
0x18026a053  lea     rcx, [rsp+2C8h+hKey]
0x18026a058  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a05d  mov     eax, ebx
0x18026a05f  jmp     loc_18026A0EC
0x18026a064  mov     rdx, rbx; lpValueName
0x18026a067  mov     rcx, [rsp+2C8h+var_268]; hKey
0x18026a06c  call    cs:__imp_RegDeleteValueW
0x18026a073  nop     dword ptr [rax+rax+00h]
0x18026a078  test    eax, eax
0x18026a07a  jz      short loc_18026A0C1
0x18026a07c  mov     rcx, [rsp+2C8h]; this
0x18026a084  mov     r9d, eax; char *
0x18026a087  lea     r8, aShellSystemset_9; "shell\\systemsettingsthreshold\\handler"...
0x18026a08e  mov     edx, 25Ch; void *
0x18026a093  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18026a098  mov     ebx, eax
0x18026a09a  lea     rcx, [rsp+2C8h+var_268]
0x18026a09f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a0a4  nop
0x18026a0a5  lea     rcx, [rsp+2C8h+var_248]
0x18026a0ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a0b2  nop
0x18026a0b3  lea     rcx, [rsp+2C8h+hKey]
0x18026a0b8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a0bd  mov     eax, ebx
0x18026a0bf  jmp     short loc_18026A0EC
0x18026a0c1  lea     rcx, [rsp+2C8h+var_268]
0x18026a0c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a0cb  nop
0x18026a0cc  lea     rcx, [rsp+2C8h+var_248]
0x18026a0d4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18026a0d9  nop
0x18026a0da  lea     rcx, [rsp+2C8h+hKey]
0x18026a0df  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18026a0e4  xor     eax, eax
0x18026a0e6  jmp     short loc_18026A0EC
0x18026a0e8  mov     eax, [rsp+2C8h+cbData]
0x18026a0ec  mov     rcx, [rsp+2C8h+var_18]
0x18026a0f4  xor     rcx, rsp; StackCookie
0x18026a0f7  call    __security_check_cookie
0x18026a0fc  mov     rbx, [rsp+2C8h+arg_8]
0x18026a104  add     rsp, 2C0h
0x18026a10b  pop     rdi
0x18026a10c  retn
```
