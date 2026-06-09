# PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x1800aff14`
- end: `0x1800b036e`
- name: `?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1114`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800afecc`

## callees

- `0x180002cdc`
- `0x180003884`
- `0x180004eb0`
- `0x1800058ec`
- `0x18000d50c`
- `0x1800131a8`
- `0x180016698`
- `0x180017118`
- `0x18003e5d4`
- `0x1800449f0`
- `0x18006ac14`
- `0x1800a8d98`
- `0x1800ac230`
- `0x1800af838`
- `0x1800af8e4`
- `0x1800afca8`
- `0x1800aff14`
- `0x1800b0374`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b01d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b01d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b00a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b00a2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b00dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b00dc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b001a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b029a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b001a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b029a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aff96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aff96`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b01b5`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b01b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b0180`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b0180`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
  v5 = qword_1800FF590;
  if ( PackageCollector::s_registryCache == qword_1800FF590 )
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
              if ( (unsigned int)dword_1800FE488 > 2 )
              {
                v41 = FileNameW;
                v31 = lpFileName;
                if ( v47 > 7 )
                  v31 = (LPCWSTR *)lpFileName[0];
                v43 = v31;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  v28,
                  (unsigned int)word_1800EE242,
                  v29,
                  v30,
                  (__int64)&v43,
                  (__int64)&v41);
              }
              goto LABEL_42;
            }
          }
          std::vector<std::wstring>::emplace_back<std::wstring &>(&PackageCollector::s_registryCache, lpFileName);
          PackageCollector::AddSearchPath(a1, qword_1800FF590 - 32);
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
      if ( (unsigned int)dword_1800FE488 > 4 )
      {
        v23 = v48;
        if ( v49 > 7 )
          v23 = (unsigned __int16 **)v48[0];
        v41 = v23;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v17,
          (unsigned int)byte_1800EE209,
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
0x1800aff14  mov     [rsp-8+arg_10], rbx
0x1800aff19  mov     [rsp-8+arg_18], rsi
0x1800aff1e  push    rbp
0x1800aff1f  push    rdi
0x1800aff20  push    r12
0x1800aff22  push    r14
0x1800aff24  push    r15
0x1800aff26  lea     rbp, [rsp-37h]
0x1800aff2b  sub     rsp, 100h
0x1800aff32  mov     rax, cs:__security_cookie
0x1800aff39  xor     rax, rsp
0x1800aff3c  mov     [rbp+57h+var_28], rax
0x1800aff40  mov     rsi, rdx
0x1800aff43  mov     r15, rcx
0x1800aff46  mov     [rbp+57h+var_A0], rdx
0x1800aff4a  mov     rbx, cs:?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x1800aff51  mov     rdi, cs:qword_1800FF590
0x1800aff58  cmp     rbx, rdi
0x1800aff5b  jnz     loc_1800B02BD
0x1800aff61  xor     r12d, r12d
0x1800aff64  mov     [rsp+120h+hKey], r12
0x1800aff69  xor     edx, edx
0x1800aff6b  lea     rcx, [rsp+120h+hKey]
0x1800aff70  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800aff75  lea     rax, [rsp+120h+hKey]
0x1800aff7a  mov     [rsp+120h+phkResult], rax; unsigned int
0x1800aff7f  mov     r9d, 20019h; samDesired
0x1800aff85  xor     r8d, r8d; ulOptions
0x1800aff88  lea     rdx, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x1800aff8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aff96  call    cs:__imp_RegOpenKeyExW
0x1800aff9d  nop     dword ptr [rax+rax+00h]
0x1800affa2  mov     rcx, [rbp+5Fh]; this
0x1800affa6  test    eax, eax
0x1800affa8  jnz     loc_1800B0317
0x1800affae  mov     r14d, r12d
0x1800affb1  xor     edx, edx
0x1800affb3  jmp     loc_1800B0266
0x1800affb8  mov     rcx, [rbp+5Fh]; this
0x1800affbc  test    eax, eax
0x1800affbe  jnz     loc_1800B0302
0x1800affc4  cmp     [rsp+120h+cchValueName], 10h
0x1800affc9  setb    al
0x1800affcc  mov     rcx, [rbp+5Fh]; this
0x1800affd0  test    al, al
0x1800affd2  jz      loc_1800B0356
0x1800affd8  mov     ecx, [rsp+120h+cbData]; unsigned __int64
0x1800affdc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800affe1  mov     rbx, rax
0x1800affe4  mov     [rbp+57h+var_D0], rax
0x1800affe8  mov     [rsp+120h+cchValueName], 0Fh
0x1800afff0  lea     rax, [rsp+120h+cbData]
0x1800afff5  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800afffa  mov     [rsp+120h+lpData], rbx; lpData
0x1800affff  mov     [rsp+120h+lpType], r12; lpType
0x1800b0004  mov     [rsp+120h+phkResult], r12; unsigned int
0x1800b0009  lea     r9, [rsp+120h+cchValueName]; lpcchValueName
0x1800b000e  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800b0012  mov     edx, r14d; dwIndex
0x1800b0015  mov     rcx, [rsp+120h+hKey]; hKey
0x1800b001a  call    cs:__imp_RegEnumValueW
0x1800b0021  nop     dword ptr [rax+rax+00h]
0x1800b0026  mov     rcx, [rbp+5Fh]; this
0x1800b002a  test    eax, eax
0x1800b002c  jnz     loc_1800B0341
0x1800b0032  mov     rdx, rbx; unsigned __int16 *
0x1800b0035  lea     rcx, [rbp+57h+var_98]; this
0x1800b0039  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800b003e  nop
0x1800b003f  mov     rdx, [rax]
0x1800b0042  lea     rcx, [rbp+57h+lpFileName]
0x1800b0046  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b004b  nop
0x1800b004c  lea     rcx, [rbp+57h+var_98]
0x1800b0050  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b0055  mov     rbx, [rsi]
0x1800b0058  mov     rdi, [rsi+8]
0x1800b005c  jmp     short loc_1800B00C9
0x1800b005e  mov     rdx, rbx
0x1800b0061  lea     rcx, [rbp+57h+var_68]
0x1800b0065  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b006a  nop
0x1800b006b  lea     rdx, [rbp+57h+var_68]
0x1800b006f  cmp     [rbp+57h+var_50], 7
0x1800b0074  cmova   rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800b0079  lea     rcx, [rbp+57h+var_B0]; this
0x1800b007d  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x1800b0082  mov     rdx, [rbp+57h+var_B0]
0x1800b0086  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b008a  inc     r8
0x1800b008d  cmp     [rdx+r8*2], r12w
0x1800b0092  jnz     short loc_1800B008A
0x1800b0094  lea     rcx, [rbp+57h+lpFileName]
0x1800b0098  cmp     [rbp+57h+var_70], 7
0x1800b009d  cmova   rcx, [rbp+57h+lpFileName]
0x1800b00a2  call    cs:__imp__o__wcsnicmp
0x1800b00a9  nop     dword ptr [rax+rax+00h]
0x1800b00ae  test    eax, eax
0x1800b00b0  jz      short loc_1800B0120
0x1800b00b2  lea     rcx, [rbp+57h+var_B0]
0x1800b00b6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b00bb  nop
0x1800b00bc  lea     rcx, [rbp+57h+var_68]
0x1800b00c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b00c5  add     rbx, 20h ; ' '
0x1800b00c9  cmp     rbx, rdi
0x1800b00cc  jnz     short loc_1800B005E
0x1800b00ce  lea     rcx, [rbp+57h+lpFileName]
0x1800b00d2  cmp     [rbp+57h+var_70], 7
0x1800b00d7  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x1800b00dc  call    cs:__imp_GetFileAttributesW
0x1800b00e3  nop     dword ptr [rax+rax+00h]
0x1800b00e8  cmp     eax, 0FFFFFFFFh
0x1800b00eb  jnz     short loc_1800B016A
0x1800b00ed  test    cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, 4
0x1800b00f4  jz      loc_1800B024D
0x1800b00fa  lea     r8, [rbp+57h+lpFileName]
0x1800b00fe  cmp     [rbp+57h+var_70], 7
0x1800b0103  cmova   r8, [rbp+57h+lpFileName]
0x1800b0108  lea     rdx, ProvisioningSearchPathNotExist
0x1800b010f  lea     rcx, PROVISIONING_DIAGNOSTICS_Context
0x1800b0116  call    McTemplateU0z_EventWriteTransfer
0x1800b011b  jmp     loc_1800B024D
0x1800b0120  mov     eax, cs:dword_1800FE488
0x1800b0126  cmp     eax, 4
0x1800b0129  jbe     short loc_1800B0152
0x1800b012b  lea     rax, [rbp+57h+var_68]
0x1800b012f  cmp     [rbp+57h+var_50], 7
0x1800b0134  cmova   rax, [rbp+57h+var_68]
0x1800b0139  mov     [rbp+57h+var_C8], rax
0x1800b013d  lea     rax, [rbp+57h+var_C8]
0x1800b0141  mov     [rsp+120h+phkResult], rax
0x1800b0146  lea     rdx, byte_1800EE209
0x1800b014d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b0152  lea     rcx, [rbp+57h+var_B0]
0x1800b0156  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b015b  nop
0x1800b015c  lea     rcx, [rbp+57h+var_68]
0x1800b0160  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0165  jmp     loc_1800B024D
0x1800b016a  test    al, 10h
0x1800b016c  jnz     loc_1800B0229
0x1800b0172  lea     rcx, [rbp+57h+lpFileName]
0x1800b0176  cmp     [rbp+57h+var_70], 7
0x1800b017b  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x1800b0180  call    cs:__imp_PathFindFileNameW
0x1800b0187  nop     dword ptr [rax+rax+00h]
0x1800b018c  mov     rbx, rax
0x1800b018f  test    rax, rax
0x1800b0192  jz      loc_1800B024D
0x1800b0198  mov     [rbp+57h+ppszExt], r12
0x1800b019c  mov     rdx, [rbp+57h+var_78]
0x1800b01a0  inc     rdx; cchPath
0x1800b01a3  lea     rcx, [rbp+57h+lpFileName]
0x1800b01a7  cmp     [rbp+57h+var_70], 7
0x1800b01ac  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x1800b01b1  lea     r8, [rbp+57h+ppszExt]; ppszExt
0x1800b01b5  call    cs:__imp_PathCchFindExtension
0x1800b01bc  nop     dword ptr [rax+rax+00h]
0x1800b01c1  mov     rcx, [rbp+5Fh]; this
0x1800b01c5  test    eax, eax
0x1800b01c7  js      loc_1800B032C
0x1800b01cd  lea     rdx, aPpkg_0; ".ppkg"
0x1800b01d4  mov     rcx, [rbp+57h+ppszExt]
0x1800b01d8  call    cs:__imp__o__wcsicmp
0x1800b01df  nop     dword ptr [rax+rax+00h]
0x1800b01e4  test    eax, eax
0x1800b01e6  jz      short loc_1800B0229
0x1800b01e8  mov     eax, cs:dword_1800FE488
0x1800b01ee  cmp     eax, 2
0x1800b01f1  jbe     short loc_1800B024D
0x1800b01f3  mov     [rbp+57h+var_C8], rbx
0x1800b01f7  lea     rax, [rbp+57h+lpFileName]
0x1800b01fb  cmp     [rbp+57h+var_70], 7
0x1800b0200  cmova   rax, [rbp+57h+lpFileName]
0x1800b0205  mov     [rbp+57h+var_B8], rax
0x1800b0209  lea     rax, [rbp+57h+var_C8]
0x1800b020d  mov     [rsp+120h+lpType], rax
0x1800b0212  lea     rax, [rbp+57h+var_B8]
0x1800b0216  mov     [rsp+120h+phkResult], rax
0x1800b021b  lea     rdx, word_1800EE242
0x1800b0222  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800b0227  jmp     short loc_1800B024D
0x1800b0229  lea     rdx, [rbp+57h+lpFileName]
0x1800b022d  lea     rcx, ?s_registryCache@PackageCollector@@0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::vector<std::wstring> PackageCollector::s_registryCache
0x1800b0234  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring &>(std::wstring &)
0x1800b0239  mov     rdx, cs:qword_1800FF590
0x1800b0240  add     rdx, 0FFFFFFFFFFFFFFE0h
0x1800b0244  mov     rcx, r15
0x1800b0247  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x1800b024c  nop
0x1800b024d  lea     rcx, [rbp+57h+lpFileName]
0x1800b0251  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b0256  nop
0x1800b0257  lea     rcx, [rbp+57h+var_D0]
0x1800b025b  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b0260  inc     r14d
0x1800b0263  mov     edx, r14d; dwIndex
0x1800b0266  lea     rax, [rsp+120h+cbData]
0x1800b026b  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800b0270  mov     [rsp+120h+lpData], r12; lpData
0x1800b0275  mov     [rsp+120h+lpType], r12; lpType
0x1800b027a  mov     [rsp+120h+phkResult], r12; int
0x1800b027f  mov     [rsp+120h+cchValueName], 0Fh
0x1800b0287  mov     [rsp+120h+cbData], r12d
0x1800b028c  lea     r9, [rsp+120h+cchValueName]; lpcchValueName
0x1800b0291  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800b0295  mov     rcx, [rsp+120h+hKey]; hKey
0x1800b029a  call    cs:__imp_RegEnumValueW
0x1800b02a1  nop     dword ptr [rax+rax+00h]
0x1800b02a6  cmp     eax, 103h
0x1800b02ab  jnz     loc_1800AFFB8
0x1800b02b1  lea     rcx, [rsp+120h+hKey]
0x1800b02b6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b02bb  jmp     short loc_1800B02D1
0x1800b02bd  mov     rdx, rbx
0x1800b02c0  mov     rcx, r15
0x1800b02c3  call    ?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageCollector::AddSearchPath(std::wstring const &)
0x1800b02c8  add     rbx, 20h ; ' '
0x1800b02cc  cmp     rbx, rdi
0x1800b02cf  jnz     short loc_1800B02BD
0x1800b02d1  mov     rcx, rsi
0x1800b02d4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800b02d9  mov     rcx, [rbp+57h+var_28]
0x1800b02dd  xor     rcx, rsp; StackCookie
0x1800b02e0  call    __security_check_cookie
0x1800b02e5  lea     r11, [rsp+120h+var_20]
0x1800b02ed  mov     rbx, [r11+40h]
0x1800b02f1  mov     rsi, [r11+48h]
0x1800b02f5  mov     rsp, r11
0x1800b02f8  pop     r15
0x1800b02fa  pop     r14
0x1800b02fc  pop     r12
0x1800b02fe  pop     rdi
0x1800b02ff  pop     rbp
0x1800b0300  retn
0x1800b0302  mov     r9d, eax; char *
0x1800b0305  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b030c  mov     edx, 51h ; 'Q'; void *
0x1800b0311  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b0317  mov     r9d, eax; char *
0x1800b031a  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b0321  mov     edx, 3Ch ; '<'; void *
0x1800b0326  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b032c  mov     r9d, eax; char *
0x1800b032f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b0336  mov     edx, 93h; void *
0x1800b033b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b0341  mov     r9d, eax; char *
0x1800b0344  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b034b  mov     edx, 61h ; 'a'; void *
0x1800b0350  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b0356  mov     r9d, 8000FFFFh; char *
0x1800b035c  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b0363  mov     edx, 52h ; 'R'; void *
0x1800b0368  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
