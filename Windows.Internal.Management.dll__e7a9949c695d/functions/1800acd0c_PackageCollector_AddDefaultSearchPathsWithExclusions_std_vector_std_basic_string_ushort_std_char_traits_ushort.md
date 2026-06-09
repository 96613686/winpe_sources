# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x1800acd0c`
- end: `0x1800ad135`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1065`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071b50`

## callees

- `0x180002bdc`
- `0x18000377c`
- `0x180004d50`
- `0x18000578c`
- `0x18000cfdc`
- `0x180012ae8`
- `0x180015f70`
- `0x1800169b8`
- `0x18003ec00`
- `0x180044d84`
- `0x1800699d0`
- `0x1800a597c`
- `0x1800a8d18`
- `0x1800ac6a0`
- `0x1800ac740`
- `0x1800acaf0`
- `0x1800acd0c`
- `0x1800ad13c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800acfac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800acfac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800ace8e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800ace8e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800acec2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800acec2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ace0c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ad068`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ace0c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800ad068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acd8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800acd8e`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800acf8f`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800acf8f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800acf60`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800acf60`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall PackageCollector::AddDefaultSearchPathsWithExclusions(__int64 a1, __int64 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned int v6; // eax
  DWORD v7; // r14d
  DWORD i; // edx
  BYTE *lpData; // rbx
  unsigned int v10; // eax
  expanded_wstring *v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdi
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  LPCWSTR *v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const WCHAR *v20; // rcx
  DWORD FileAttributesW; // eax
  LPCWSTR *v22; // r8
  unsigned __int16 **v23; // rax
  const WCHAR *v24; // rcx
  LPWSTR FileNameW; // rbx
  const WCHAR *v26; // rcx
  HRESULT Extension; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  LPCWSTR *v31; // rax
  unsigned int v32; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-A9h]
  unsigned int phkResulta; // [rsp+20h] [rbp-A9h]
  unsigned int phkResultb; // [rsp+20h] [rbp-A9h]
  DWORD cchValueName; // [rsp+40h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-85h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-81h] BYREF
  BYTE *v40; // [rsp+50h] [rbp-79h] BYREF
  void *v41; // [rsp+58h] [rbp-71h] BYREF
  PCWSTR ppszExt; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR *v43; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v44[3]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v45[16]; // [rsp+88h] [rbp-41h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v47; // [rsp+B0h] [rbp-19h]
  unsigned __int16 *v48[3]; // [rsp+B8h] [rbp-11h] BYREF
  unsigned __int64 v49; // [rsp+D0h] [rbp+7h]
  WCHAR ValueName[16]; // [rsp+D8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v44[2] = a2;
  v4 = PackageCollector::s_registryCache;
  v5 = qword_1800FB5D0;
  if ( PackageCollector::s_registryCache == qword_1800FB5D0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Provisioning\\PackageLocations", 0, 0x20019u, &hKey);
    if ( v6 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        (const char *)v6,
        phkResult);
    v7 = 0;
    for ( i = 0; ; i = v7 )
    {
      cchValueName = 15;
      cbData = 0;
      v32 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, &cbData);
      if ( v32 == 259 )
        break;
      if ( v32 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v32,
          phkResultb);
      if ( cchValueName >= 0x10 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x8000FFFFLL,
          phkResultb);
      lpData = (BYTE *)operator new[](cbData);
      v40 = lpData;
      cchValueName = 15;
      v10 = RegEnumValueW(hKey, v7, ValueName, &cchValueName, 0, 0, lpData, &cbData);
      if ( v10 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v10,
          phkResulta);
      v11 = expanded_wstring::expanded_wstring((expanded_wstring *)v45, (const unsigned __int16 *)lpData);
      std::wstring::wstring(lpFileName, *(_QWORD *)v11);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v45);
      v12 = *a2;
      v13 = a2[1];
      while ( 1 )
      {
        if ( v12 == v13 )
        {
          v20 = (const WCHAR *)lpFileName;
          if ( v47 > 7 )
            v20 = lpFileName[0];
          FileAttributesW = GetFileAttributesW(v20);
          if ( FileAttributesW == -1 )
          {
            if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 4) != 0 )
            {
              v22 = lpFileName;
              if ( v47 > 7 )
                v22 = (LPCWSTR *)lpFileName[0];
              McTemplateU0z_EventWriteTransfer(PROVISIONING_DIAGNOSTICS_Context, ProvisioningSearchPathNotExist, v22);
            }
            goto LABEL_42;
          }
          if ( (FileAttributesW & 0x10) == 0 )
          {
            v24 = (const WCHAR *)lpFileName;
            if ( v47 > 7 )
              v24 = lpFileName[0];
            FileNameW = PathFindFileNameW(v24);
            if ( !FileNameW )
              goto LABEL_42;
            ppszExt = 0;
            v26 = (const WCHAR *)lpFileName;
            if ( v47 > 7 )
              v26 = lpFileName[0];
            Extension = PathCchFindExtension(v26, (size_t)lpFileName[2] + 1, &ppszExt);
            if ( Extension < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x93,
                (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
                (const char *)(unsigned int)Extension,
                phkResulta);
            if ( (unsigned int)_o__wcsicmp(ppszExt, L".ppkg") )
            {
              if ( (unsigned int)dword_1800FA480 > 2 )
              {
                v41 = FileNameW;
                v31 = lpFileName;
                if ( v47 > 7 )
                  v31 = (LPCWSTR *)lpFileName[0];
                v43 = v31;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v28,
                  (unsigned int)&dword_1800EA3CC,
                  v29,
                  v30,
                  (__int64)&v43,
                  (__int64)&v41);
              }
              goto LABEL_42;
            }
          }
          std::vector<std::wstring>::emplace_back<std::wstring &>(&PackageCollector::s_registryCache, lpFileName);
          PackageCollector::AddSearchPath(a1, qword_1800FB5D0 - 32);
          goto LABEL_42;
        }
        std::wstring::wstring(v48, v12);
        v14 = (const unsigned __int16 *)v48;
        if ( v49 > 7 )
          v14 = v48[0];
        expanded_wstring::expanded_wstring((expanded_wstring *)v44, v14);
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)(v44[0] + 2 * v15) );
        v16 = lpFileName;
        if ( v47 > 7 )
          v16 = (LPCWSTR *)lpFileName[0];
        if ( !(unsigned int)_o__wcsnicmp(v16, v44[0]) )
          break;
        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v44);
        std::wstring::_Tidy_deallocate(v48);
        v12 += 32;
      }
      if ( (unsigned int)dword_1800FA480 > 4 )
      {
        v23 = v48;
        if ( v49 > 7 )
          v23 = (unsigned __int16 **)v48[0];
        v41 = v23;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v17,
          (unsigned int)byte_1800EA45B,
          v18,
          v19,
          (__int64)&v41);
      }
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v44);
      std::wstring::_Tidy_deallocate(v48);
LABEL_42:
      std::wstring::_Tidy_deallocate(lpFileName);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v40);
      ++v7;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    do
    {
      PackageCollector::AddSearchPath(a1, v4);
      v4 += 32;
    }
    while ( v4 != v5 );
  }
  return std::vector<std::wstring>::_Tidy(a2);
}

```

## disassembly

```asm
0x1800acd0c  mov     [rsp-8+arg_10], rbx
0x1800acd11  mov     [rsp-8+arg_18], rsi
0x1800acd16  push    rbp
0x1800acd17  push    rdi
0x1800acd18  push    r12
0x1800acd1a  push    r14
0x1800acd1c  push    r15
0x1800acd1e  lea     rbp, [rsp-37h]
0x1800acd23  sub     rsp, 100h
0x1800acd2a  mov     rax, cs:__security_cookie
0x1800acd31  xor     rax, rsp
0x1800acd34  mov     [rbp+57h+var_28], rax
0x1800acd38  mov     rsi, rdx
0x1800acd3b  mov     r15, rcx
0x1800acd3e  mov     [rbp+57h+var_A0], rdx
0x1800acd42  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x1800acd49  mov     rdi, cs:qword_1800FB5D0
0x1800acd50  cmp     rbx, rdi
0x1800acd53  jnz     loc_1800AD085
0x1800acd59  xor     r12d, r12d
0x1800acd5c  mov     [rsp+120h+hKey], r12
0x1800acd61  xor     edx, edx
0x1800acd63  lea     rcx, [rsp+120h+hKey]
0x1800acd68  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800acd6d  lea     rax, [rsp+120h+hKey]
0x1800acd72  mov     [rsp+120h+phkResult], rax; unsigned int
0x1800acd77  mov     r9d, 20019h; samDesired
0x1800acd7d  xor     r8d, r8d; ulOptions
0x1800acd80  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x1800acd87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800acd8e  call    cs:__imp_RegOpenKeyExW
0x1800acd94  mov     rcx, [rbp+5Fh]; this
0x1800acd98  test    eax, eax
0x1800acd9a  jnz     loc_1800AD0DE
0x1800acda0  mov     r14d, r12d
0x1800acda3  xor     edx, edx
0x1800acda5  jmp     loc_1800AD034
0x1800acdaa  mov     rcx, [rbp+5Fh]; this
0x1800acdae  test    eax, eax
0x1800acdb0  jnz     loc_1800AD0C9
0x1800acdb6  cmp     [rsp+120h+cchValueName], 10h
0x1800acdbb  setb    al
0x1800acdbe  mov     rcx, [rbp+5Fh]; this
0x1800acdc2  test    al, al
0x1800acdc4  jz      loc_1800AD11D
0x1800acdca  mov     ecx, [rsp+120h+cbData]; unsigned __int64
0x1800acdce  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800acdd3  mov     rbx, rax
0x1800acdd6  mov     [rbp+57h+var_D0], rax
0x1800acdda  mov     [rsp+120h+cchValueName], 0Fh
0x1800acde2  lea     rax, [rsp+120h+cbData]
0x1800acde7  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800acdec  mov     [rsp+120h+lpData], rbx; lpData
0x1800acdf1  mov     [rsp+120h+lpType], r12; lpType
0x1800acdf6  mov     [rsp+120h+phkResult], r12; unsigned int
0x1800acdfb  lea     r9, [rsp+120h+cchValueName]; lpcchValueName
0x1800ace00  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800ace04  mov     edx, r14d; dwIndex
0x1800ace07  mov     rcx, [rsp+120h+hKey]; hKey
0x1800ace0c  call    cs:__imp_RegEnumValueW
0x1800ace12  mov     rcx, [rbp+5Fh]; this
0x1800ace16  test    eax, eax
0x1800ace18  jnz     loc_1800AD108
0x1800ace1e  mov     rdx, rbx; unsigned __int16 *
0x1800ace21  lea     rcx, [rbp+57h+var_98]; this
0x1800ace25  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800ace2a  nop
0x1800ace2b  mov     rdx, [rax]
0x1800ace2e  lea     rcx, [rbp+57h+lpFileName]
0x1800ace32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ace37  nop
0x1800ace38  lea     rcx, [rbp+57h+var_98]
0x1800ace3c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800ace41  mov     rbx, [rsi]
0x1800ace44  mov     rdi, [rsi+8]
0x1800ace48  jmp     short loc_1800ACEAF
0x1800ace4a  mov     rdx, rbx
0x1800ace4d  lea     rcx, [rbp+57h+var_68]
0x1800ace51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800ace56  nop
0x1800ace57  lea     rdx, [rbp+57h+var_68]
0x1800ace5b  cmp     [rbp+57h+var_50], 7
0x1800ace60  cmova   rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800ace65  lea     rcx, [rbp+57h+var_B0]; this
0x1800ace69  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800ace6e  mov     rdx, [rbp+57h+var_B0]
0x1800ace72  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ace76  inc     r8
0x1800ace79  cmp     [rdx+r8*2], r12w
0x1800ace7e  jnz     short loc_1800ACE76
0x1800ace80  lea     rcx, [rbp+57h+lpFileName]
0x1800ace84  cmp     [rbp+57h+var_70], 7
0x1800ace89  cmova   rcx, [rbp+57h+lpFileName]
0x1800ace8e  call    cs:__imp__o__wcsnicmp
0x1800ace94  test    eax, eax
0x1800ace96  jz      short loc_1800ACF00
0x1800ace98  lea     rcx, [rbp+57h+var_B0]
0x1800ace9c  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800acea1  nop
0x1800acea2  lea     rcx, [rbp+57h+var_68]
0x1800acea6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aceab  add     rbx, 20h ; ' '
0x1800aceaf  cmp     rbx, rdi
0x1800aceb2  jnz     short loc_1800ACE4A
0x1800aceb4  lea     rcx, [rbp+57h+lpFileName]
0x1800aceb8  cmp     [rbp+57h+var_70], 7
0x1800acebd  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800acec2  call    cs:__imp_GetFileAttributesW
0x1800acec8  cmp     eax, 0FFFFFFFFh
0x1800acecb  jnz     short loc_1800ACF4A
0x1800acecd  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x1800aced4  jz      loc_1800AD01B
0x1800aceda  lea     r8, [rbp+57h+lpFileName]
0x1800acede  cmp     [rbp+57h+var_70], 7
0x1800acee3  cmova   r8, [rbp+57h+lpFileName]
0x1800acee8  lea     rdx, ProvisioningSearchPathNotExist
0x1800aceef  lea     rcx, PROVISIONING_DIAGNOSTICS_Context
0x1800acef6  call    McTemplateU0z_EventWriteTransfer
0x1800acefb  jmp     loc_1800AD01B
0x1800acf00  mov     eax, cs:dword_1800FA480
0x1800acf06  cmp     eax, 4
0x1800acf09  jbe     short loc_1800ACF32
0x1800acf0b  lea     rax, [rbp+57h+var_68]
0x1800acf0f  cmp     [rbp+57h+var_50], 7
0x1800acf14  cmova   rax, [rbp+57h+var_68]
0x1800acf19  mov     [rbp+57h+var_C8], rax
0x1800acf1d  lea     rax, [rbp+57h+var_C8]
0x1800acf21  mov     [rsp+120h+phkResult], rax
0x1800acf26  lea     rdx, byte_1800EA45B
0x1800acf2d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800acf32  lea     rcx, [rbp+57h+var_B0]
0x1800acf36  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800acf3b  nop
0x1800acf3c  lea     rcx, [rbp+57h+var_68]
0x1800acf40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800acf45  jmp     loc_1800AD01B
0x1800acf4a  test    al, 10h
0x1800acf4c  jnz     loc_1800ACFF7
0x1800acf52  lea     rcx, [rbp+57h+lpFileName]
0x1800acf56  cmp     [rbp+57h+var_70], 7
0x1800acf5b  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x1800acf60  call    cs:__imp_PathFindFileNameW
0x1800acf66  mov     rbx, rax
0x1800acf69  test    rax, rax
0x1800acf6c  jz      loc_1800AD01B
0x1800acf72  mov     [rbp+57h+ppszExt], r12
0x1800acf76  mov     rdx, [rbp+57h+var_78]
0x1800acf7a  inc     rdx; cchPath
0x1800acf7d  lea     rcx, [rbp+57h+lpFileName]
0x1800acf81  cmp     [rbp+57h+var_70], 7
0x1800acf86  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x1800acf8b  lea     r8, [rbp+57h+ppszExt]; ppszExt
0x1800acf8f  call    cs:__imp_PathCchFindExtension
0x1800acf95  mov     rcx, [rbp+5Fh]; this
0x1800acf99  test    eax, eax
0x1800acf9b  js      loc_1800AD0F3
0x1800acfa1  lea     rdx, aPpkg_0; ".ppkg"
0x1800acfa8  mov     rcx, [rbp+57h+ppszExt]
0x1800acfac  call    cs:__imp__o__wcsicmp
0x1800acfb2  test    eax, eax
0x1800acfb4  jz      short loc_1800ACFF7
0x1800acfb6  mov     eax, cs:dword_1800FA480
0x1800acfbc  cmp     eax, 2
0x1800acfbf  jbe     short loc_1800AD01B
0x1800acfc1  mov     [rbp+57h+var_C8], rbx
0x1800acfc5  lea     rax, [rbp+57h+lpFileName]
0x1800acfc9  cmp     [rbp+57h+var_70], 7
0x1800acfce  cmova   rax, [rbp+57h+lpFileName]
0x1800acfd3  mov     [rbp+57h+var_B8], rax
0x1800acfd7  lea     rax, [rbp+57h+var_C8]
0x1800acfdb  mov     [rsp+120h+lpType], rax
0x1800acfe0  lea     rax, [rbp+57h+var_B8]
0x1800acfe4  mov     [rsp+120h+phkResult], rax
0x1800acfe9  lea     rdx, dword_1800EA3CC
0x1800acff0  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800acff5  jmp     short loc_1800AD01B
0x1800acff7  lea     rdx, [rbp+57h+lpFileName]
0x1800acffb  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x1800ad002  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring &>(std::wstring &)
0x1800ad007  mov     rdx, cs:qword_1800FB5D0
0x1800ad00e  add     rdx, 0FFFFFFFFFFFFFFE0h
0x1800ad012  mov     rcx, r15
0x1800ad015  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x1800ad01a  nop
0x1800ad01b  lea     rcx, [rbp+57h+lpFileName]
0x1800ad01f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad024  nop
0x1800ad025  lea     rcx, [rbp+57h+var_D0]
0x1800ad029  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800ad02e  inc     r14d
0x1800ad031  mov     edx, r14d; dwIndex
0x1800ad034  lea     rax, [rsp+120h+cbData]
0x1800ad039  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800ad03e  mov     [rsp+120h+lpData], r12; lpData
0x1800ad043  mov     [rsp+120h+lpType], r12; lpType
0x1800ad048  mov     [rsp+120h+phkResult], r12; int
0x1800ad04d  mov     [rsp+120h+cchValueName], 0Fh
0x1800ad055  mov     [rsp+120h+cbData], r12d
0x1800ad05a  lea     r9, [rsp+120h+cchValueName]; lpcchValueName
0x1800ad05f  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800ad063  mov     rcx, [rsp+120h+hKey]; hKey
0x1800ad068  call    cs:__imp_RegEnumValueW
0x1800ad06e  cmp     eax, 103h
0x1800ad073  jnz     loc_1800ACDAA
0x1800ad079  lea     rcx, [rsp+120h+hKey]
0x1800ad07e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ad083  jmp     short loc_1800AD099
0x1800ad085  mov     rdx, rbx
0x1800ad088  mov     rcx, r15
0x1800ad08b  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x1800ad090  add     rbx, 20h ; ' '
0x1800ad094  cmp     rbx, rdi
0x1800ad097  jnz     short loc_1800AD085
0x1800ad099  mov     rcx, rsi
0x1800ad09c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ad0a1  mov     rcx, [rbp+57h+var_28]
0x1800ad0a5  xor     rcx, rsp; StackCookie
0x1800ad0a8  call    __security_check_cookie
0x1800ad0ad  lea     r11, [rsp+120h+var_20]
0x1800ad0b5  mov     rbx, [r11+40h]
0x1800ad0b9  mov     rsi, [r11+48h]
0x1800ad0bd  mov     rsp, r11
0x1800ad0c0  pop     r15
0x1800ad0c2  pop     r14
0x1800ad0c4  pop     r12
0x1800ad0c6  pop     rdi
0x1800ad0c7  pop     rbp
0x1800ad0c8  retn
0x1800ad0c9  mov     r9d, eax; char *
0x1800ad0cc  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad0d3  mov     edx, 51h ; 'Q'; void *
0x1800ad0d8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ad0de  mov     r9d, eax; char *
0x1800ad0e1  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad0e8  mov     edx, 3Ch ; '<'; void *
0x1800ad0ed  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ad0f3  mov     r9d, eax; char *
0x1800ad0f6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad0fd  mov     edx, 93h; void *
0x1800ad102  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad108  mov     r9d, eax; char *
0x1800ad10b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad112  mov     edx, 61h ; 'a'; void *
0x1800ad117  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800ad11d  mov     r9d, 8000FFFFh; char *
0x1800ad123  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad12a  mov     edx, 52h ; 'R'; void *
0x1800ad12f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
