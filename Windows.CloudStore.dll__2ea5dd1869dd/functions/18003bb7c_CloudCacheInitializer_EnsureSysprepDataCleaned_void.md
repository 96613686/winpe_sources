# CloudCacheInitializer::EnsureSysprepDataCleaned(void)

- ea: `0x18003bb7c`
- end: `0x18003bd29`
- name: `?EnsureSysprepDataCleaned@CloudCacheInitializer@@CAJXZ`
- size: `429`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003bd30`

## callees

- `0x180014aac`
- `0x18003bb7c`
- `0x18003f6c4`
- `0x1800c8458`
- `0x1800ff298`
- `0x1801a6bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bc8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bbd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003bbd3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bcda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bcda`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18003bcbe`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x18003bcbe`

## string_xrefs

- `0x18003bc00`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003bc41`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003bcf0`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
__int64 CloudCacheInitializer::EnsureSysprepDataCleaned(void)
{
  LSTATUS ValueW; // eax
  unsigned int v1; // ebx
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  HKEY *p_hKey; // [rsp+40h] [rbp-20h] BYREF
  HKEY v11; // [rsp+48h] [rbp-18h] BYREF
  char v12; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  int v14; // [rsp+70h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+18h] BYREF

  v14 = 0;
  LODWORD(hKey) = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore",
             L"IsSysPrepGeneralized",
             0x10u,
             0,
             &v14,
             (LPDWORD)&hKey);
  v1 = ValueW;
  if ( ValueW > 0 )
    v1 = (unsigned __int16)ValueW | 0x80070000;
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147024894 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)v1,
      phkResult);
    return v1;
  }
  if ( v14 )
  {
    v3 = RegDeleteTreeW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore");
    if ( v3 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x2A7,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
        (const char *)v3,
        phkResult);
      hKey = 0;
      p_hKey = &hKey;
      v11 = 0;
      v12 = 1;
      v4 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion", 0, 0xF003Fu, &v11);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
      if ( v4 )
      {
        v5 = (const char *)v4;
        v6 = 682;
LABEL_16:
        v1 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
               v5,
               phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v1;
      }
      v7 = RegRenameKey(hKey, L"CloudStore", L"CloudStore.SysPrepGeneralized");
      if ( v7 )
      {
        v6 = 685;
LABEL_15:
        v5 = (const char *)v7;
        goto LABEL_16;
      }
      v7 = RegDeleteTreeW(hKey, L"CloudStore.SysPrepGeneralized");
      if ( v7 )
      {
        v6 = 686;
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003bb7c  mov     r11, rsp
0x18003bb7f  mov     [r11+18h], rbx
0x18003bb83  mov     [r11+20h], r14
0x18003bb87  push    rbp
0x18003bb88  mov     rbp, rsp
0x18003bb8b  sub     rsp, 60h
0x18003bb8f  lea     rax, [rbp+hKey]
0x18003bb93  mov     [rbp+arg_0], 0
0x18003bb9a  mov     [r11-38h], rax
0x18003bb9e  lea     r8, aIssysprepgener; "IsSysPrepGeneralized"
0x18003bba5  lea     rax, [rbp+arg_0]
0x18003bba9  mov     dword ptr [rbp+hKey], 4
0x18003bbb0  mov     [r11-40h], rax
0x18003bbb4  lea     rdx, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003bbbb  mov     r14, 0FFFFFFFF80000001h
0x18003bbc2  mov     qword ptr [r11-48h], 0
0x18003bbca  mov     r9d, 10h; dwFlags
0x18003bbd0  mov     rcx, r14; hkey
0x18003bbd3  call    cs:__imp_RegGetValueW
0x18003bbd9  mov     ebx, eax
0x18003bbdb  test    eax, eax
0x18003bbdd  jle     short loc_18003BBE8
0x18003bbdf  movzx   ebx, ax
0x18003bbe2  or      ebx, 80070000h
0x18003bbe8  mov     eax, 80000000h
0x18003bbed  lea     ecx, [rbx+rax]
0x18003bbf0  test    eax, ecx
0x18003bbf2  jnz     short loc_18003BC1B
0x18003bbf4  cmp     ebx, 80070002h
0x18003bbfa  jz      short loc_18003BC1B
0x18003bbfc  mov     rcx, [rbp+8]; this
0x18003bc00  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003bc07  mov     r9d, ebx; char *
0x18003bc0a  mov     edx, 2A5h; void *
0x18003bc0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc14  mov     eax, ebx
0x18003bc16  jmp     loc_18003BD17
0x18003bc1b  cmp     [rbp+arg_0], 0
0x18003bc1f  jz      loc_18003BD15
0x18003bc25  lea     rdx, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003bc2c  mov     rcx, r14; hKey
0x18003bc2f  call    cs:__imp_RegDeleteTreeW
0x18003bc35  test    eax, eax
0x18003bc37  jz      loc_18003BD15
0x18003bc3d  mov     rcx, [rbp+8]; this
0x18003bc41  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003bc48  mov     r9d, eax; char *
0x18003bc4b  mov     edx, 2A7h; void *
0x18003bc50  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003bc55  lea     rax, [rbp+hKey]
0x18003bc59  mov     [rbp+hKey], 0
0x18003bc61  mov     [rbp+var_20], rax
0x18003bc65  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003bc6c  lea     rax, [rbp+var_18]
0x18003bc70  mov     [rbp+var_18], 0
0x18003bc78  mov     r9d, 0F003Fh; samDesired
0x18003bc7e  mov     qword ptr [rsp+60h+phkResult], rax; unsigned int
0x18003bc83  xor     r8d, r8d; ulOptions
0x18003bc86  mov     [rbp+var_10], 1
0x18003bc8a  mov     rcx, r14; hKey
0x18003bc8d  call    cs:__imp_RegOpenKeyExW
0x18003bc93  lea     rcx, [rbp+var_20]
0x18003bc97  mov     ebx, eax
0x18003bc99  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18003bc9e  test    ebx, ebx
0x18003bca0  jz      short loc_18003BCAC
0x18003bca2  mov     r9d, ebx
0x18003bca5  mov     edx, 2AAh
0x18003bcaa  jmp     short loc_18003BCEC
0x18003bcac  mov     rcx, [rbp+hKey]; hKey
0x18003bcb0  lea     r8, NewKeyName; "CloudStore.SysPrepGeneralized"
0x18003bcb7  lea     rdx, SubKeyName; "CloudStore"
0x18003bcbe  call    cs:__imp_RegRenameKey
0x18003bcc4  test    eax, eax
0x18003bcc6  jz      short loc_18003BCCF
0x18003bcc8  mov     edx, 2ADh
0x18003bccd  jmp     short loc_18003BCE9
0x18003bccf  mov     rcx, [rbp+hKey]; hKey
0x18003bcd3  lea     rdx, NewKeyName; "CloudStore.SysPrepGeneralized"
0x18003bcda  call    cs:__imp_RegDeleteTreeW
0x18003bce0  test    eax, eax
0x18003bce2  jz      short loc_18003BD0C
0x18003bce4  mov     edx, 2AEh; void *
0x18003bce9  mov     r9d, eax; char *
0x18003bcec  mov     rcx, [rbp+8]; this
0x18003bcf0  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003bcf7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003bcfc  lea     rcx, [rbp+hKey]
0x18003bd00  mov     ebx, eax
0x18003bd02  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003bd07  jmp     loc_18003BC14
0x18003bd0c  lea     rcx, [rbp+hKey]
0x18003bd10  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003bd15  xor     eax, eax
0x18003bd17  lea     r11, [rsp+60h+var_s0]
0x18003bd1c  mov     rbx, [r11+20h]
0x18003bd20  mov     r14, [r11+28h]
0x18003bd24  mov     rsp, r11
0x18003bd27  pop     rbp
0x18003bd28  retn
```
