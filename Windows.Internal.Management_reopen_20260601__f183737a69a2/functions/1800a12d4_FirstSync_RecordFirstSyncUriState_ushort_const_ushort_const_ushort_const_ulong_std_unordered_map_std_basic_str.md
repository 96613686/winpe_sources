# FirstSync::RecordFirstSyncUriState(ushort const *,ushort const *,ushort const *,ulong,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,FirstSync::FirstSyncTrackedItemStatus,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,FirstSync::FirstSyncTrackedItemStatus>>> const &)

- ea: `0x1800a12d4`
- end: `0x1800a1832`
- name: `?RecordFirstSyncUriState@FirstSync@@YAJPEBG00KAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@@std@@@Z`
- size: `1374`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a531c`
- `0x1800a55d4`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000a5c4`
- `0x18000ac30`
- `0x18000d50c`
- `0x18000dc18`
- `0x180015e44`
- `0x180016698`
- `0x180017024`
- `0x180017118`
- `0x180033500`
- `0x18007a7e8`
- `0x18007a814`
- `0x18007bb94`
- `0x1800923d0`
- `0x1800a12d4`
- `0x1800a24b4`
- `0x1800a24cc`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a14c8`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a14c8`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1701`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a17a4`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1701`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a17a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a1553`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a1553`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a1460`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a166e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a1460`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a166e`

## string_xrefs

- `0x1800a14ba`: `LastCountOfCompletedUris`
- `0x1800a16f3`: `LastCountOfCompletedUris`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall FirstSync::RecordFirstSyncUriState(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  const WCHAR *v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // ebx
  int DWORD; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rbx
  int v25; // eax
  unsigned int v26; // ebx
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  unsigned int v29; // r9d
  int v30; // eax
  unsigned int v31; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-328h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-328h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-328h]
  HKEY hKey; // [rsp+50h] [rbp-2F8h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-2F0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-2E8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-2E0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-2D8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-2D0h] BYREF
  _BYTE v41[32]; // [rsp+88h] [rbp-2C0h] BYREF
  _BYTE v42[32]; // [rsp+A8h] [rbp-2A0h] BYREF
  _BYTE v43[32]; // [rsp+C8h] [rbp-280h] BYREF
  _BYTE v44[40]; // [rsp+E8h] [rbp-260h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  if ( !*(_QWORD *)(a5 + 16) )
    return 0;
  v9 = DMGetNonVolatileRegPrefix();
  v10 = std::wstring::wstring(v44, v9);
  std::operator+<unsigned short>(
    v41,
    v10,
    L"SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking\\ESPTrackingInfo\\Diagnostics");
  std::wstring::~wstring(v44);
  if ( a2 )
  {
    v11 = std::wstring::wstring(v43, L"\\");
    v12 = std::operator+<unsigned short>(v42, v11, a2);
    std::wstring::append(v41, v12);
    std::wstring::~wstring(v42);
    std::wstring::~wstring(v43);
  }
  v13 = std::wstring::wstring(v42, L"\\");
  v14 = std::operator+<unsigned short>(v43, v13, a3);
  std::wstring::append(v41, v14);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v42);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  v16 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v16 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x45A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
            (const char *)v16,
            dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v41);
    return v17;
  }
  v36 = 0;
  DWORD = OmaDmRegistryGetDWORD(hKey, 0, L"LastCountOfCompletedUris", &v36);
  v19 = DWORD;
  if ( DWORD >= 0 )
  {
    if ( v36 == a4 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(v41);
      return 0;
    }
  }
  else if ( (unsigned int)(DWORD + 2147024894) > 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x464,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)DWORD,
      dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v41);
    return v19;
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  memset_0(SubKey, 0, 0x208u);
  dwOptionsa = SystemTime.wMonth;
  v20 = StringCchPrintfW(SubKey, 0x104u, L"%04d-%02d-%02dT%02d:%02d:%02d.%03dZ", SystemTime.wYear);
  v21 = v20;
  if ( v20 >= 0 )
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v22 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    if ( v22 )
    {
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x482,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
              (const char *)v22,
              dwOptionsb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(v41);
      return v23;
    }
    else
    {
      std::_Hash<std::_Umap_traits<std::wstring,enum FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_begin(
        a5,
        &v38);
      std::_Hash<std::_Umap_traits<std::wstring,enum FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,enum FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_end(
        a5,
        &v39);
      v24 = v39;
      while ( v38 != v24 )
      {
        v27 = std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator*(&v38);
        v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
        v30 = OmaDmRegistrySetDWORD(phkResult, 0, v28, v29);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x486,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
            (const char *)(unsigned int)v30,
            dwOptionsb);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::~wstring(v41);
          return v31;
        }
        std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator++(&v38);
      }
      v25 = OmaDmRegistrySetDWORD(hKey, 0, L"LastCountOfCompletedUris", a4);
      v26 = v25;
      if ( v25 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(v41);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
          (const char *)(unsigned int)v25,
          dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(v41);
        return v26;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x476,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)v20,
      dwOptionsa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::~wstring(v41);
    return v21;
  }
}

```

## disassembly

```asm
0x1800a12d4  mov     [rsp+arg_0], rbx
0x1800a12d9  push    rsi
0x1800a12da  push    rdi
0x1800a12db  push    r14
0x1800a12dd  sub     rsp, 330h
0x1800a12e4  mov     rax, cs:__security_cookie
0x1800a12eb  xor     rax, rsp
0x1800a12ee  mov     [rsp+348h+var_28], rax
0x1800a12f6  mov     esi, r9d
0x1800a12f9  mov     r14, r8
0x1800a12fc  mov     rbx, rdx
0x1800a12ff  mov     rdi, [rsp+348h+arg_20]
0x1800a1307  cmp     qword ptr [rdi+10h], 0
0x1800a130c  jnz     short loc_1800A1315
0x1800a130e  xor     eax, eax
0x1800a1310  jmp     loc_1800A180D
0x1800a1315  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x1800a131a  mov     rdx, rax
0x1800a131d  lea     rcx, [rsp+348h+var_260]
0x1800a1325  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a132a  nop
0x1800a132b  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x1800a1332  mov     rdx, rax
0x1800a1335  lea     rcx, [rsp+348h+var_2C0]
0x1800a133d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a1342  nop
0x1800a1343  lea     rcx, [rsp+348h+var_260]
0x1800a134b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1350  test    rbx, rbx
0x1800a1353  jz      short loc_1800A13AA
0x1800a1355  lea     rdx, asc_1800DD8B8; "\\"
0x1800a135c  lea     rcx, [rsp+348h+var_280]
0x1800a1364  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a1369  nop
0x1800a136a  mov     r8, rbx
0x1800a136d  mov     rdx, rax
0x1800a1370  lea     rcx, [rsp+348h+var_2A0]
0x1800a1378  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a137d  nop
0x1800a137e  mov     rdx, rax
0x1800a1381  lea     rcx, [rsp+348h+var_2C0]
0x1800a1389  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800a138e  nop
0x1800a138f  lea     rcx, [rsp+348h+var_2A0]
0x1800a1397  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a139c  nop
0x1800a139d  lea     rcx, [rsp+348h+var_280]
0x1800a13a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a13aa  lea     rdx, asc_1800DD8B8; "\\"
0x1800a13b1  lea     rcx, [rsp+348h+var_2A0]
0x1800a13b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a13be  nop
0x1800a13bf  mov     r8, r14
0x1800a13c2  mov     rdx, rax
0x1800a13c5  lea     rcx, [rsp+348h+var_280]
0x1800a13cd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a13d2  nop
0x1800a13d3  mov     rdx, rax
0x1800a13d6  lea     rcx, [rsp+348h+var_2C0]
0x1800a13de  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800a13e3  nop
0x1800a13e4  lea     rcx, [rsp+348h+var_280]
0x1800a13ec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a13f1  nop
0x1800a13f2  lea     rcx, [rsp+348h+var_2A0]
0x1800a13fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a13ff  mov     [rsp+348h+hKey], 0
0x1800a1408  xor     edx, edx
0x1800a140a  lea     rcx, [rsp+348h+hKey]
0x1800a140f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a1414  lea     rcx, [rsp+348h+var_2C0]
0x1800a141c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a1421  mov     rdx, rax; lpSubKey
0x1800a1424  mov     [rsp+348h+lpdwDisposition], 0; lpdwDisposition
0x1800a142d  lea     rax, [rsp+348h+hKey]
0x1800a1432  mov     [rsp+348h+phkResult], rax; phkResult
0x1800a1437  mov     [rsp+348h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a1440  mov     r14d, 0F003Fh
0x1800a1446  mov     [rsp+348h+samDesired], r14d; samDesired
0x1800a144b  mov     [rsp+348h+dwOptions], 0; int
0x1800a1453  xor     r9d, r9d; lpClass
0x1800a1456  xor     r8d, r8d; Reserved
0x1800a1459  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a1460  call    cs:__imp_RegCreateKeyExW
0x1800a1467  nop     dword ptr [rax+rax+00h]
0x1800a146c  test    eax, eax
0x1800a146e  jz      short loc_1800A14AD
0x1800a1470  mov     rcx, [rsp+348h]; this
0x1800a1478  mov     r9d, eax; char *
0x1800a147b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1482  mov     edx, 45Ah; void *
0x1800a1487  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a148c  mov     ebx, eax
0x1800a148e  lea     rcx, [rsp+348h+hKey]
0x1800a1493  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1498  nop
0x1800a1499  lea     rcx, [rsp+348h+var_2C0]
0x1800a14a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a14a6  mov     eax, ebx
0x1800a14a8  jmp     loc_1800A180D
0x1800a14ad  mov     [rsp+348h+var_2F0], 0
0x1800a14b5  lea     r9, [rsp+348h+var_2F0]
0x1800a14ba  lea     r8, aLastcountofcom; "LastCountOfCompletedUris"
0x1800a14c1  xor     edx, edx
0x1800a14c3  mov     rcx, [rsp+348h+hKey]
0x1800a14c8  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800a14cf  nop     dword ptr [rax+rax+00h]
0x1800a14d4  mov     ebx, eax
0x1800a14d6  test    eax, eax
0x1800a14d8  jns     short loc_1800A1521
0x1800a14da  lea     ecx, [rax+7FF8FFFEh]
0x1800a14e0  cmp     ecx, 1
0x1800a14e3  jbe     short loc_1800A1546
0x1800a14e5  mov     rcx, [rsp+348h]; this
0x1800a14ed  mov     r9d, eax; char *
0x1800a14f0  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a14f7  mov     edx, 464h; void *
0x1800a14fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1501  nop
0x1800a1502  lea     rcx, [rsp+348h+hKey]
0x1800a1507  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a150c  nop
0x1800a150d  lea     rcx, [rsp+348h+var_2C0]
0x1800a1515  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a151a  mov     eax, ebx
0x1800a151c  jmp     loc_1800A180D
0x1800a1521  cmp     [rsp+348h+var_2F0], esi
0x1800a1525  jnz     short loc_1800A1546
0x1800a1527  lea     rcx, [rsp+348h+hKey]
0x1800a152c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1531  nop
0x1800a1532  lea     rcx, [rsp+348h+var_2C0]
0x1800a153a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a153f  xor     eax, eax
0x1800a1541  jmp     loc_1800A180D
0x1800a1546  xorps   xmm0, xmm0
0x1800a1549  movups  xmmword ptr [rsp+348h+SystemTime.wYear], xmm0
0x1800a154e  lea     rcx, [rsp+348h+SystemTime]; lpSystemTime
0x1800a1553  call    cs:__imp_GetSystemTime
0x1800a155a  nop     dword ptr [rax+rax+00h]
0x1800a155f  xor     edx, edx; Val
0x1800a1561  mov     r8d, 208h; Size
0x1800a1567  lea     rcx, [rsp+348h+SubKey]; void *
0x1800a156f  call    memset_0
0x1800a1574  movzx   eax, [rsp+348h+SystemTime.wMilliseconds]
0x1800a157c  movzx   ecx, [rsp+348h+SystemTime.wSecond]
0x1800a1584  movzx   edx, [rsp+348h+SystemTime.wMinute]
0x1800a158c  movzx   r8d, [rsp+348h+SystemTime.wHour]
0x1800a1595  movzx   r10d, [rsp+348h+SystemTime.wDay]
0x1800a159b  movzx   r11d, [rsp+348h+SystemTime.wMonth]
0x1800a15a1  movzx   r9d, [rsp+348h+SystemTime.wYear]
0x1800a15a7  mov     [rsp+348h+var_300], eax
0x1800a15ab  mov     dword ptr [rsp+348h+lpdwDisposition], ecx
0x1800a15af  mov     dword ptr [rsp+348h+phkResult], edx
0x1800a15b3  mov     dword ptr [rsp+348h+lpSecurityAttributes], r8d
0x1800a15b8  mov     [rsp+348h+samDesired], r10d
0x1800a15bd  mov     [rsp+348h+dwOptions], r11d; int
0x1800a15c2  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1800a15c9  mov     edx, 104h; unsigned __int64
0x1800a15ce  lea     rcx, [rsp+348h+SubKey]; unsigned __int16 *
0x1800a15d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a15db  mov     ebx, eax
0x1800a15dd  test    eax, eax
0x1800a15df  jns     short loc_1800A161D
0x1800a15e1  mov     rcx, [rsp+348h]; this
0x1800a15e9  mov     r9d, eax; char *
0x1800a15ec  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a15f3  mov     edx, 476h; void *
0x1800a15f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a15fd  nop
0x1800a15fe  lea     rcx, [rsp+348h+hKey]
0x1800a1603  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1608  nop
0x1800a1609  lea     rcx, [rsp+348h+var_2C0]
0x1800a1611  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1616  mov     eax, ebx
0x1800a1618  jmp     loc_1800A180D
0x1800a161d  mov     [rsp+348h+var_2E8], 0
0x1800a1626  xor     edx, edx
0x1800a1628  lea     rcx, [rsp+348h+var_2E8]
0x1800a162d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a1632  mov     [rsp+348h+lpdwDisposition], 0; lpdwDisposition
0x1800a163b  lea     rax, [rsp+348h+var_2E8]
0x1800a1640  mov     [rsp+348h+phkResult], rax; phkResult
0x1800a1645  mov     [rsp+348h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a164e  mov     [rsp+348h+samDesired], r14d; samDesired
0x1800a1653  mov     [rsp+348h+dwOptions], 0; int
0x1800a165b  xor     r9d, r9d; lpClass
0x1800a165e  xor     r8d, r8d; Reserved
0x1800a1661  lea     rdx, [rsp+348h+SubKey]; lpSubKey
0x1800a1669  mov     rcx, [rsp+348h+hKey]; hKey
0x1800a166e  call    cs:__imp_RegCreateKeyExW
0x1800a1675  nop     dword ptr [rax+rax+00h]
0x1800a167a  test    eax, eax
0x1800a167c  jz      short loc_1800A16C6
0x1800a167e  mov     rcx, [rsp+348h]; this
0x1800a1686  mov     r9d, eax; char *
0x1800a1689  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1690  mov     edx, 482h; void *
0x1800a1695  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a169a  mov     ebx, eax
0x1800a169c  lea     rcx, [rsp+348h+var_2E8]
0x1800a16a1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a16a6  nop
0x1800a16a7  lea     rcx, [rsp+348h+hKey]
0x1800a16ac  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a16b1  nop
0x1800a16b2  lea     rcx, [rsp+348h+var_2C0]
0x1800a16ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a16bf  mov     eax, ebx
0x1800a16c1  jmp     loc_1800A180D
0x1800a16c6  lea     rdx, [rsp+348h+var_2E0]
0x1800a16cb  mov     rcx, rdi
0x1800a16ce  call    ?_Unchecked_begin@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Hash<std::_Umap_traits<std::wstring,FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_begin(void)
0x1800a16d3  lea     rdx, [rsp+348h+var_2D8]
0x1800a16d8  mov     rcx, rdi
0x1800a16db  call    ?_Unchecked_end@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Hash<std::_Umap_traits<std::wstring,FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_end(void)
0x1800a16e0  mov     rbx, [rsp+348h+var_2D8]
0x1800a16e5  cmp     [rsp+348h+var_2E0], rbx
0x1800a16ea  jnz     loc_1800A1784
0x1800a16f0  mov     r9d, esi
0x1800a16f3  lea     r8, aLastcountofcom; "LastCountOfCompletedUris"
0x1800a16fa  xor     edx, edx
0x1800a16fc  mov     rcx, [rsp+348h+hKey]
0x1800a1701  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a1708  nop     dword ptr [rax+rax+00h]
0x1800a170d  mov     ebx, eax
0x1800a170f  test    eax, eax
0x1800a1711  jns     short loc_1800A175A
0x1800a1713  mov     rcx, [rsp+348h]; this
0x1800a171b  mov     r9d, eax; char *
0x1800a171e  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1725  mov     edx, 48Ah; void *
0x1800a172a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a172f  nop
0x1800a1730  lea     rcx, [rsp+348h+var_2E8]
0x1800a1735  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a173a  nop
0x1800a173b  lea     rcx, [rsp+348h+hKey]
0x1800a1740  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1745  nop
0x1800a1746  lea     rcx, [rsp+348h+var_2C0]
0x1800a174e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a1753  mov     eax, ebx
0x1800a1755  jmp     loc_1800A180D
0x1800a175a  lea     rcx, [rsp+348h+var_2E8]
0x1800a175f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1764  nop
0x1800a1765  lea     rcx, [rsp+348h+hKey]
0x1800a176a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a176f  nop
0x1800a1770  lea     rcx, [rsp+348h+var_2C0]
0x1800a1778  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a177d  xor     eax, eax
0x1800a177f  jmp     loc_1800A180D
0x1800a1784  lea     rcx, [rsp+348h+var_2E0]
0x1800a1789  call    ??D?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@U_Iterator_base0@2@@std@@QEBAAEBUCommandResult@@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator*(void)
0x1800a178e  mov     r9d, [rax+20h]
0x1800a1792  mov     rcx, rax
0x1800a1795  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a179a  mov     r8, rax
0x1800a179d  xor     edx, edx
0x1800a179f  mov     rcx, [rsp+348h+var_2E8]
0x1800a17a4  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a17ab  nop     dword ptr [rax+rax+00h]
0x1800a17b0  mov     edi, eax
0x1800a17b2  test    eax, eax
0x1800a17b4  jns     short loc_1800A17FA
0x1800a17b6  mov     rcx, [rsp+348h]; this
0x1800a17be  mov     r9d, eax; char *
0x1800a17c1  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a17c8  mov     edx, 486h; void *
0x1800a17cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a17d2  nop
0x1800a17d3  lea     rcx, [rsp+348h+var_2E8]
0x1800a17d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a17dd  nop
0x1800a17de  lea     rcx, [rsp+348h+hKey]
0x1800a17e3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a17e8  nop
0x1800a17e9  lea     rcx, [rsp+348h+var_2C0]
0x1800a17f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a17f6  mov     eax, edi
0x1800a17f8  jmp     short loc_1800A180D
0x1800a17fa  lea     rcx, [rsp+348h+var_2E0]
0x1800a17ff  call    ??E?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator++(void)
0x1800a1804  jmp     loc_1800A16E5
0x1800a1809  mov     eax, [rsp+348h+var_2F0]
0x1800a180d  mov     rcx, [rsp+348h+var_28]
0x1800a1815  xor     rcx, rsp; StackCookie
0x1800a1818  call    __security_check_cookie
0x1800a181d  mov     rbx, [rsp+348h+arg_0]
0x1800a1825  add     rsp, 330h
0x1800a182c  pop     r14
0x1800a182e  pop     rdi
0x1800a182f  pop     rsi
0x1800a1830  retn
```
