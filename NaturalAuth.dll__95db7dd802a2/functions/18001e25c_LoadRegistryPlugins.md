# LoadRegistryPlugins

- ea: `0x18001e25c`
- end: `0x18001e724`
- name: `LoadRegistryPlugins`
- size: `1224`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ee00`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000a7f8`
- `0x180012a48`
- `0x180012b74`
- `0x18001d758`
- `0x18001d788`
- `0x18001df8c`
- `0x18001e25c`
- `0x18001f160`
- `0x18001f634`
- `0x18001f738`
- `0x18001f8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e415`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e415`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e4fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e583`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e4fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e583`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001e34e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001e34e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e2c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e480`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e2c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e480`

## string_xrefs

- `0x18001e2b4`: `Software\Microsoft\Windows NT\CurrentVersion\NaAuth\Plugins`
- `0x18001e577`: `DLLName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 LoadRegistryPlugins()
{
  unsigned int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // r9
  unsigned int v4; // eax
  DWORD i; // r14d
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  DWORD v11; // eax
  unsigned int Dll; // eax
  __int64 v13; // rcx
  int v14; // r8d
  unsigned int updated; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  HKEY *p_hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  char v27; // [rsp+98h] [rbp-68h]
  BYTE v28[96]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE Data[4]; // [rsp+100h] [rbp+0h] BYREF
  BYTE v30[140]; // [rsp+104h] [rbp+4h] BYREF
  WCHAR Name[256]; // [rsp+190h] [rbp+90h] BYREF

  hKey = 0;
  cSubKeys = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v27 = 1;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\NaAuth\\Plugins",
         0,
         0x20019u,
         &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 20;
      v3 = v0;
LABEL_5:
      WPP_SF_d(v1[2], v2, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, v3);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v0 = v4;
  if ( !v4 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= cSubKeys )
        goto LABEL_58;
      v22 = 0;
      cbData = 0;
      Type = 0;
      memset_0(v28, 0, 0xE8u);
      cchName = 256;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, i);
      v6 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v0 = v6;
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, v6);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
        goto LABEL_58;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, Name);
      p_hKey = &v22;
      phkResult = 0;
      v27 = 1;
      v0 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( v0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 25;
          v9 = v0;
LABEL_23:
          WPP_SF_d(v7[2], v8, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, v9);
        }
      }
      else
      {
        cbData = 4;
        v0 = RegQueryValueExW(v22, L"SchemaVersion", 0, &Type, Data, &cbData);
        v11 = Type;
        if ( v0 || Type != 4 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 26;
            goto LABEL_52;
          }
        }
        else if ( *(_DWORD *)Data <= 1u )
        {
          cbData = 64;
          v0 = RegQueryValueExW(v22, L"DLLName", 0, &Type, v30, &cbData);
          v11 = Type;
          if ( v0 || Type != 1 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v17 = 28;
LABEL_52:
              WPP_SF_ld(v16[2], v17, v10, v0, v11);
            }
          }
          else
          {
            Dll = LoadDll(v28);
            v0 = Dll;
            if ( Dll )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sl(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v14, (unsigned int)v30, Dll);
            }
            else
            {
              if ( *((_QWORD *)&g_RegistryPlugins + 1) == qword_18005F9A0 )
                std::vector<NA_PLUGIN>::_Emplace_reallocate<NA_PLUGIN const &>(
                  v13,
                  *((_QWORD *)&g_RegistryPlugins + 1),
                  v28);
              else
                std::vector<NA_PLUGIN>::_Emplace_back_with_unused_capacity<NA_PLUGIN const &>(v13, v28);
              updated = UpdateRegistrySignalLookupTable(*((_QWORD *)&g_RegistryPlugins + 1) - 232LL);
              v0 = updated;
              if ( updated )
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v8 = 30;
                  v9 = updated;
                  goto LABEL_23;
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids, v30);
              }
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            Type + 23,
            &WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids,
            *(unsigned int *)Data);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v22);
    }
  }
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v2 = 21;
    v3 = v4;
    goto LABEL_5;
  }
LABEL_58:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x18001e25c  push    rbp
0x18001e25e  push    rbx
0x18001e25f  push    rdi
0x18001e260  push    r14
0x18001e262  push    r15
0x18001e264  lea     rbp, [rsp-2A0h]
0x18001e26c  sub     rsp, 3A0h
0x18001e273  mov     rax, cs:__security_cookie
0x18001e27a  xor     rax, rsp
0x18001e27d  mov     [rbp+2C0h+var_30], rax
0x18001e284  xor     r15d, r15d
0x18001e287  mov     [rsp+3C0h+hKey], r15
0x18001e28c  mov     [rsp+3C0h+cSubKeys], r15d
0x18001e291  lea     rax, [rsp+3C0h+hKey]
0x18001e296  mov     [rbp+2C0h+var_338], rax
0x18001e29a  mov     [rbp+2C0h+var_330], r15
0x18001e29e  mov     [rbp+2C0h+var_328], 1
0x18001e2a2  lea     rax, [rbp+2C0h+var_330]
0x18001e2a6  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18001e2ab  mov     r9d, 20019h; samDesired
0x18001e2b1  xor     r8d, r8d; ulOptions
0x18001e2b4  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001e2bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e2c2  call    cs:__imp_RegOpenKeyExW
0x18001e2c8  mov     ebx, eax
0x18001e2ca  lea     rcx, [rbp+2C0h+var_338]
0x18001e2ce  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001e2d3  test    ebx, ebx
0x18001e2d5  jz      short loc_18001E314
0x18001e2d7  lea     rdi, WPP_GLOBAL_Control
0x18001e2de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e2e5  cmp     rcx, rdi
0x18001e2e8  jz      loc_18001E6FA
0x18001e2ee  test    byte ptr [rcx+1Ch], 1
0x18001e2f2  jz      loc_18001E6FA
0x18001e2f8  lea     edx, [r15+14h]
0x18001e2fc  mov     r9d, ebx
0x18001e2ff  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e306  mov     rcx, [rcx+10h]
0x18001e30a  call    WPP_SF_d
0x18001e30f  jmp     loc_18001E6FA
0x18001e314  mov     [rsp+3C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001e319  mov     [rsp+3C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001e31e  mov     [rsp+3C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001e323  mov     [rsp+3C0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18001e328  mov     [rsp+3C0h+lpcValues], r15; lpcValues
0x18001e32d  mov     [rsp+3C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001e332  mov     [rsp+3C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001e337  lea     rax, [rsp+3C0h+cSubKeys]
0x18001e33c  mov     [rsp+3C0h+phkResult], rax; lpcSubKeys
0x18001e341  xor     r9d, r9d; lpReserved
0x18001e344  xor     r8d, r8d; lpcchClass
0x18001e347  xor     edx, edx; lpClass
0x18001e349  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18001e34e  call    cs:__imp_RegQueryInfoKeyW
0x18001e354  mov     ebx, eax
0x18001e356  test    eax, eax
0x18001e358  jz      short loc_18001E388
0x18001e35a  lea     rdi, WPP_GLOBAL_Control
0x18001e361  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e368  cmp     rcx, rdi
0x18001e36b  jz      loc_18001E6FA
0x18001e371  test    byte ptr [rcx+1Ch], 1
0x18001e375  jz      loc_18001E6FA
0x18001e37b  mov     edx, 15h
0x18001e380  mov     r9d, eax
0x18001e383  jmp     loc_18001E2FF
0x18001e388  mov     r14d, r15d
0x18001e38b  lea     rdi, WPP_GLOBAL_Control
0x18001e392  cmp     r14d, [rsp+3C0h+cSubKeys]
0x18001e397  jnb     loc_18001E6FA
0x18001e39d  mov     [rsp+3C0h+var_350], r15
0x18001e3a2  mov     [rsp+3C0h+cbData], r15d
0x18001e3a7  mov     [rsp+3C0h+Type], r15d
0x18001e3ac  xor     edx, edx; Val
0x18001e3ae  mov     r8d, 0E8h; Size
0x18001e3b4  lea     rcx, [rbp+2C0h+var_320]; void *
0x18001e3b8  call    memset_0
0x18001e3bd  mov     [rbp+2C0h+cchName], 100h
0x18001e3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3cb  cmp     rcx, rdi
0x18001e3ce  jz      short loc_18001E3EE
0x18001e3d0  test    byte ptr [rcx+1Ch], 4
0x18001e3d4  jz      short loc_18001E3EE
0x18001e3d6  mov     edx, 16h
0x18001e3db  mov     r9d, r14d
0x18001e3de  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e3e5  mov     rcx, [rcx+10h]
0x18001e3e9  call    WPP_SF_d
0x18001e3ee  mov     [rsp+3C0h+lpcValues], r15; lpftLastWriteTime
0x18001e3f3  mov     [rsp+3C0h+lpcbMaxClassLen], r15; lpcchClass
0x18001e3f8  mov     [rsp+3C0h+lpcbMaxSubKeyLen], r15; lpClass
0x18001e3fd  mov     [rsp+3C0h+phkResult], r15; lpReserved
0x18001e402  lea     r9, [rbp+2C0h+cchName]; lpcchName
0x18001e406  lea     r8, [rbp+2C0h+Name]; lpName
0x18001e40d  mov     edx, r14d; dwIndex
0x18001e410  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18001e415  call    cs:__imp_RegEnumKeyExW
0x18001e41b  mov     ebx, eax
0x18001e41d  test    eax, eax
0x18001e41f  jnz     loc_18001E6C4
0x18001e425  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e42c  cmp     rcx, rdi
0x18001e42f  jz      short loc_18001E451
0x18001e431  test    byte ptr [rcx+1Ch], 4
0x18001e435  jz      short loc_18001E451
0x18001e437  lea     edx, [rax+18h]
0x18001e43a  lea     r9, [rbp+2C0h+Name]
0x18001e441  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e448  mov     rcx, [rcx+10h]
0x18001e44c  call    WPP_SF_S
0x18001e451  lea     rax, [rsp+3C0h+var_350]
0x18001e456  mov     [rbp+2C0h+var_338], rax
0x18001e45a  mov     [rbp+2C0h+var_330], r15
0x18001e45e  mov     [rbp+2C0h+var_328], 1
0x18001e462  lea     rax, [rbp+2C0h+var_330]
0x18001e466  mov     [rsp+3C0h+phkResult], rax; phkResult
0x18001e46b  mov     r9d, 20019h; samDesired
0x18001e471  xor     r8d, r8d; ulOptions
0x18001e474  lea     rdx, [rbp+2C0h+Name]; lpSubKey
0x18001e47b  mov     rcx, [rsp+3C0h+hKey]; hKey
0x18001e480  call    cs:__imp_RegOpenKeyExW
0x18001e486  mov     ebx, eax
0x18001e488  lea     rcx, [rbp+2C0h+var_338]
0x18001e48c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001e491  test    ebx, ebx
0x18001e493  jz      short loc_18001E4CC
0x18001e495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e49c  cmp     rcx, rdi
0x18001e49f  jz      loc_18001E6B2
0x18001e4a5  test    byte ptr [rcx+1Ch], 1
0x18001e4a9  jz      loc_18001E6B2
0x18001e4af  mov     edx, 19h
0x18001e4b4  mov     r9d, ebx
0x18001e4b7  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e4be  mov     rcx, [rcx+10h]
0x18001e4c2  call    WPP_SF_d
0x18001e4c7  jmp     loc_18001E6B2
0x18001e4cc  mov     [rsp+3C0h+cbData], 4
0x18001e4d4  lea     rax, [rsp+3C0h+cbData]
0x18001e4d9  mov     [rsp+3C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18001e4de  lea     rax, [rbp+2C0h+Data]
0x18001e4e2  mov     [rsp+3C0h+phkResult], rax; lpData
0x18001e4e7  lea     r9, [rsp+3C0h+Type]; lpType
0x18001e4ec  xor     r8d, r8d; lpReserved
0x18001e4ef  lea     rdx, aSchemaversion; "SchemaVersion"
0x18001e4f6  mov     rcx, [rsp+3C0h+var_350]; hKey
0x18001e4fb  call    cs:__imp_RegQueryValueExW
0x18001e501  mov     ebx, eax
0x18001e503  mov     eax, [rsp+3C0h+Type]
0x18001e507  test    ebx, ebx
0x18001e509  jnz     loc_18001E68A
0x18001e50f  cmp     eax, 4
0x18001e512  jnz     loc_18001E68A
0x18001e518  mov     r9d, dword ptr [rbp+2C0h+Data]
0x18001e51c  cmp     r9d, 1
0x18001e520  jbe     short loc_18001E554
0x18001e522  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e529  cmp     rcx, rdi
0x18001e52c  jz      loc_18001E6B2
0x18001e532  test    byte ptr [rcx+1Ch], 1
0x18001e536  jz      loc_18001E6B2
0x18001e53c  lea     edx, [rax+17h]
0x18001e53f  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e546  mov     rcx, [rcx+10h]
0x18001e54a  call    WPP_SF_d
0x18001e54f  jmp     loc_18001E6B2
0x18001e554  mov     [rsp+3C0h+cbData], 40h ; '@'
0x18001e55c  lea     rax, [rsp+3C0h+cbData]
0x18001e561  mov     [rsp+3C0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18001e566  lea     rax, [rbp+2C0h+var_2BC]
0x18001e56a  mov     [rsp+3C0h+phkResult], rax; lpData
0x18001e56f  lea     r9, [rsp+3C0h+Type]; lpType
0x18001e574  xor     r8d, r8d; lpReserved
0x18001e577  lea     rdx, aDllname; "DLLName"
0x18001e57e  mov     rcx, [rsp+3C0h+var_350]; hKey
0x18001e583  call    cs:__imp_RegQueryValueExW
0x18001e589  mov     ebx, eax
0x18001e58b  mov     eax, [rsp+3C0h+Type]
0x18001e58f  test    ebx, ebx
0x18001e591  jnz     loc_18001E671
0x18001e597  cmp     eax, 1
0x18001e59a  jnz     loc_18001E671
0x18001e5a0  lea     rcx, [rbp+2C0h+var_320]
0x18001e5a4  call    LoadDll
0x18001e5a9  mov     ebx, eax
0x18001e5ab  test    eax, eax
0x18001e5ad  jz      short loc_18001E5E4
0x18001e5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5b6  cmp     rcx, rdi
0x18001e5b9  jz      loc_18001E6B2
0x18001e5bf  test    byte ptr [rcx+1Ch], 1
0x18001e5c3  jz      loc_18001E6B2
0x18001e5c9  mov     edx, 1Dh
0x18001e5ce  mov     dword ptr [rsp+3C0h+phkResult], eax
0x18001e5d2  lea     r9, [rbp+2C0h+var_2BC]
0x18001e5d6  mov     rcx, [rcx+10h]
0x18001e5da  call    WPP_SF_Sl
0x18001e5df  jmp     loc_18001E6B2
0x18001e5e4  mov     rdx, qword ptr cs:?g_RegistryPlugins@@3V?$vector@UNA_PLUGIN@@V?$allocator@UNA_PLUGIN@@@std@@@std@@A+8; std::vector<NA_PLUGIN> g_RegistryPlugins
0x18001e5eb  cmp     rdx, cs:qword_18005F9A0
0x18001e5f2  jz      short loc_18001E5FF
0x18001e5f4  lea     rdx, [rbp+2C0h+var_320]
0x18001e5f8  call    ??$_Emplace_back_with_unused_capacity@AEBUNA_PLUGIN@@@?$vector@UNA_PLUGIN@@V?$allocator@UNA_PLUGIN@@@std@@@std@@AEAAAEAUNA_PLUGIN@@AEBU2@@Z; std::vector<NA_PLUGIN>::_Emplace_back_with_unused_capacity<NA_PLUGIN const &>(NA_PLUGIN const &)
0x18001e5fd  jmp     short loc_18001E608
0x18001e5ff  lea     r8, [rbp+2C0h+var_320]
0x18001e603  call    ??$_Emplace_reallocate@AEBUNA_PLUGIN@@@?$vector@UNA_PLUGIN@@V?$allocator@UNA_PLUGIN@@@std@@@std@@AEAAPEAUNA_PLUGIN@@QEAU2@AEBU2@@Z; std::vector<NA_PLUGIN>::_Emplace_reallocate<NA_PLUGIN const &>(NA_PLUGIN * const,NA_PLUGIN const &)
0x18001e608  mov     rcx, qword ptr cs:?g_RegistryPlugins@@3V?$vector@UNA_PLUGIN@@V?$allocator@UNA_PLUGIN@@@std@@@std@@A+8; std::vector<NA_PLUGIN> g_RegistryPlugins
0x18001e60f  add     rcx, 0FFFFFFFFFFFFFF18h
0x18001e616  call    UpdateRegistrySignalLookupTable
0x18001e61b  mov     ebx, eax
0x18001e61d  test    eax, eax
0x18001e61f  jz      short loc_18001E644
0x18001e621  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e628  cmp     rcx, rdi
0x18001e62b  jz      loc_18001E6B2
0x18001e631  test    byte ptr [rcx+1Ch], 1
0x18001e635  jz      short loc_18001E6B2
0x18001e637  mov     edx, 1Eh
0x18001e63c  mov     r9d, eax
0x18001e63f  jmp     loc_18001E4B7
0x18001e644  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e64b  cmp     rcx, rdi
0x18001e64e  jz      short loc_18001E6B2
0x18001e650  test    byte ptr [rcx+1Ch], 4
0x18001e654  jz      short loc_18001E6B2
0x18001e656  mov     edx, 1Fh
0x18001e65b  lea     r9, [rbp+2C0h+var_2BC]
0x18001e65f  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e666  mov     rcx, [rcx+10h]
0x18001e66a  call    WPP_SF_S
0x18001e66f  jmp     short loc_18001E6B2
0x18001e671  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e678  cmp     rcx, rdi
0x18001e67b  jz      short loc_18001E6B2
0x18001e67d  test    byte ptr [rcx+1Ch], 1
0x18001e681  jz      short loc_18001E6B2
0x18001e683  mov     edx, 1Ch
0x18001e688  jmp     short loc_18001E6A1
0x18001e68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e691  cmp     rcx, rdi
0x18001e694  jz      short loc_18001E6B2
0x18001e696  test    byte ptr [rcx+1Ch], 1
0x18001e69a  jz      short loc_18001E6B2
0x18001e69c  mov     edx, 1Ah
0x18001e6a1  mov     dword ptr [rsp+3C0h+phkResult], eax
0x18001e6a5  mov     r9d, ebx
0x18001e6a8  mov     rcx, [rcx+10h]
0x18001e6ac  call    WPP_SF_ld
0x18001e6b1  nop
0x18001e6b2  lea     rcx, [rsp+3C0h+var_350]
0x18001e6b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e6bc  inc     r14d
0x18001e6bf  jmp     loc_18001E392
0x18001e6c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6cb  cmp     rcx, rdi
0x18001e6ce  jz      short loc_18001E6EF
0x18001e6d0  test    byte ptr [rcx+1Ch], 1
0x18001e6d4  jz      short loc_18001E6EF
0x18001e6d6  mov     edx, 17h
0x18001e6db  mov     r9d, eax
0x18001e6de  lea     r8, WPP_fb4b6c20289c37c1f24720aba8866156_Traceguids
0x18001e6e5  mov     rcx, [rcx+10h]
0x18001e6e9  call    WPP_SF_d
0x18001e6ee  nop
0x18001e6ef  lea     rcx, [rsp+3C0h+var_350]
0x18001e6f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e6f9  nop
0x18001e6fa  lea     rcx, [rsp+3C0h+hKey]
0x18001e6ff  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e704  mov     eax, ebx
0x18001e706  mov     rcx, [rbp+2C0h+var_30]
0x18001e70d  xor     rcx, rsp; StackCookie
0x18001e710  call    __security_check_cookie
0x18001e715  add     rsp, 3A0h
0x18001e71c  pop     r15
0x18001e71e  pop     r14
0x18001e720  pop     rdi
0x18001e721  pop     rbx
0x18001e722  pop     rbp
0x18001e723  retn
```
