# FirstSync::RecordFirstSyncUriState(ushort const *,ushort const *,ushort const *,ulong,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,FirstSync::FirstSyncTrackedItemStatus,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,FirstSync::FirstSyncTrackedItemStatus>>> const &)

- ea: `0x18009e300`
- end: `0x18009e83a`
- name: `?RecordFirstSyncUriState@FirstSync@@YAJPEBG00KAEBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@@std@@@Z`
- size: `1338`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2030`
- `0x1800a22d8`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000a2a4`
- `0x18000a8e8`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015720`
- `0x180015f70`
- `0x1800168d0`
- `0x1800169b8`
- `0x18003446c`
- `0x180078fe0`
- `0x18007900c`
- `0x18007a328`
- `0x18008fdcc`
- `0x18009e300`
- `0x18009f428`
- `0x18009f43c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009e4ee`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009e4ee`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e715`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e7b2`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e715`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e7b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009e573`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18009e573`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e48c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e688`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e48c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009e688`

## string_xrefs

- `0x18009e4e0`: `LastCountOfCompletedUris`
- `0x18009e707`: `LastCountOfCompletedUris`

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
0x18009e300  mov     [rsp+arg_0], rbx
0x18009e305  push    rsi
0x18009e306  push    rdi
0x18009e307  push    r14
0x18009e309  sub     rsp, 330h
0x18009e310  mov     rax, cs:__security_cookie
0x18009e317  xor     rax, rsp
0x18009e31a  mov     [rsp+348h+var_28], rax
0x18009e322  mov     esi, r9d
0x18009e325  mov     r14, r8
0x18009e328  mov     rbx, rdx
0x18009e32b  mov     rdi, [rsp+348h+arg_20]
0x18009e333  cmp     qword ptr [rdi+10h], 0
0x18009e338  jnz     short loc_18009E341
0x18009e33a  xor     eax, eax
0x18009e33c  jmp     loc_18009E815
0x18009e341  call    ?DMGetNonVolatileRegPrefix@@YAPEBGXZ; DMGetNonVolatileRegPrefix(void)
0x18009e346  mov     rdx, rax
0x18009e349  lea     rcx, [rsp+348h+var_260]
0x18009e351  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009e356  nop
0x18009e357  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x18009e35e  mov     rdx, rax
0x18009e361  lea     rcx, [rsp+348h+var_2C0]
0x18009e369  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009e36e  nop
0x18009e36f  lea     rcx, [rsp+348h+var_260]
0x18009e377  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e37c  test    rbx, rbx
0x18009e37f  jz      short loc_18009E3D6
0x18009e381  lea     rdx, asc_1800D9938; "\\"
0x18009e388  lea     rcx, [rsp+348h+var_280]
0x18009e390  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009e395  nop
0x18009e396  mov     r8, rbx
0x18009e399  mov     rdx, rax
0x18009e39c  lea     rcx, [rsp+348h+var_2A0]
0x18009e3a4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009e3a9  nop
0x18009e3aa  mov     rdx, rax
0x18009e3ad  lea     rcx, [rsp+348h+var_2C0]
0x18009e3b5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18009e3ba  nop
0x18009e3bb  lea     rcx, [rsp+348h+var_2A0]
0x18009e3c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e3c8  nop
0x18009e3c9  lea     rcx, [rsp+348h+var_280]
0x18009e3d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e3d6  lea     rdx, asc_1800D9938; "\\"
0x18009e3dd  lea     rcx, [rsp+348h+var_2A0]
0x18009e3e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009e3ea  nop
0x18009e3eb  mov     r8, r14
0x18009e3ee  mov     rdx, rax
0x18009e3f1  lea     rcx, [rsp+348h+var_280]
0x18009e3f9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18009e3fe  nop
0x18009e3ff  mov     rdx, rax
0x18009e402  lea     rcx, [rsp+348h+var_2C0]
0x18009e40a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18009e40f  nop
0x18009e410  lea     rcx, [rsp+348h+var_280]
0x18009e418  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e41d  nop
0x18009e41e  lea     rcx, [rsp+348h+var_2A0]
0x18009e426  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e42b  mov     [rsp+348h+hKey], 0
0x18009e434  xor     edx, edx
0x18009e436  lea     rcx, [rsp+348h+hKey]
0x18009e43b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009e440  lea     rcx, [rsp+348h+var_2C0]
0x18009e448  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e44d  mov     rdx, rax; lpSubKey
0x18009e450  mov     [rsp+348h+lpdwDisposition], 0; lpdwDisposition
0x18009e459  lea     rax, [rsp+348h+hKey]
0x18009e45e  mov     [rsp+348h+phkResult], rax; phkResult
0x18009e463  mov     [rsp+348h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009e46c  mov     r14d, 0F003Fh
0x18009e472  mov     [rsp+348h+samDesired], r14d; samDesired
0x18009e477  mov     [rsp+348h+dwOptions], 0; int
0x18009e47f  xor     r9d, r9d; lpClass
0x18009e482  xor     r8d, r8d; Reserved
0x18009e485  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009e48c  call    cs:__imp_RegCreateKeyExW
0x18009e492  test    eax, eax
0x18009e494  jz      short loc_18009E4D3
0x18009e496  mov     rcx, [rsp+348h]; this
0x18009e49e  mov     r9d, eax; char *
0x18009e4a1  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e4a8  mov     edx, 45Ah; void *
0x18009e4ad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009e4b2  mov     ebx, eax
0x18009e4b4  lea     rcx, [rsp+348h+hKey]
0x18009e4b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e4be  nop
0x18009e4bf  lea     rcx, [rsp+348h+var_2C0]
0x18009e4c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e4cc  mov     eax, ebx
0x18009e4ce  jmp     loc_18009E815
0x18009e4d3  mov     [rsp+348h+var_2F0], 0
0x18009e4db  lea     r9, [rsp+348h+var_2F0]
0x18009e4e0  lea     r8, aLastcountofcom; "LastCountOfCompletedUris"
0x18009e4e7  xor     edx, edx
0x18009e4e9  mov     rcx, [rsp+348h+hKey]
0x18009e4ee  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18009e4f4  mov     ebx, eax
0x18009e4f6  test    eax, eax
0x18009e4f8  jns     short loc_18009E541
0x18009e4fa  lea     ecx, [rax+7FF8FFFEh]
0x18009e500  cmp     ecx, 1
0x18009e503  jbe     short loc_18009E566
0x18009e505  mov     rcx, [rsp+348h]; this
0x18009e50d  mov     r9d, eax; char *
0x18009e510  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e517  mov     edx, 464h; void *
0x18009e51c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e521  nop
0x18009e522  lea     rcx, [rsp+348h+hKey]
0x18009e527  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e52c  nop
0x18009e52d  lea     rcx, [rsp+348h+var_2C0]
0x18009e535  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e53a  mov     eax, ebx
0x18009e53c  jmp     loc_18009E815
0x18009e541  cmp     [rsp+348h+var_2F0], esi
0x18009e545  jnz     short loc_18009E566
0x18009e547  lea     rcx, [rsp+348h+hKey]
0x18009e54c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e551  nop
0x18009e552  lea     rcx, [rsp+348h+var_2C0]
0x18009e55a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e55f  xor     eax, eax
0x18009e561  jmp     loc_18009E815
0x18009e566  xorps   xmm0, xmm0
0x18009e569  movups  xmmword ptr [rsp+348h+SystemTime.wYear], xmm0
0x18009e56e  lea     rcx, [rsp+348h+SystemTime]; lpSystemTime
0x18009e573  call    cs:__imp_GetSystemTime
0x18009e579  xor     edx, edx; Val
0x18009e57b  mov     r8d, 208h; Size
0x18009e581  lea     rcx, [rsp+348h+SubKey]; void *
0x18009e589  call    memset_0
0x18009e58e  movzx   eax, [rsp+348h+SystemTime.wMilliseconds]
0x18009e596  movzx   ecx, [rsp+348h+SystemTime.wSecond]
0x18009e59e  movzx   edx, [rsp+348h+SystemTime.wMinute]
0x18009e5a6  movzx   r8d, [rsp+348h+SystemTime.wHour]
0x18009e5af  movzx   r10d, [rsp+348h+SystemTime.wDay]
0x18009e5b5  movzx   r11d, [rsp+348h+SystemTime.wMonth]
0x18009e5bb  movzx   r9d, [rsp+348h+SystemTime.wYear]
0x18009e5c1  mov     [rsp+348h+var_300], eax
0x18009e5c5  mov     dword ptr [rsp+348h+lpdwDisposition], ecx
0x18009e5c9  mov     dword ptr [rsp+348h+phkResult], edx
0x18009e5cd  mov     dword ptr [rsp+348h+lpSecurityAttributes], r8d
0x18009e5d2  mov     [rsp+348h+samDesired], r10d
0x18009e5d7  mov     [rsp+348h+dwOptions], r11d; int
0x18009e5dc  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x18009e5e3  mov     edx, 104h; unsigned __int64
0x18009e5e8  lea     rcx, [rsp+348h+SubKey]; unsigned __int16 *
0x18009e5f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009e5f5  mov     ebx, eax
0x18009e5f7  test    eax, eax
0x18009e5f9  jns     short loc_18009E637
0x18009e5fb  mov     rcx, [rsp+348h]; this
0x18009e603  mov     r9d, eax; char *
0x18009e606  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e60d  mov     edx, 476h; void *
0x18009e612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e617  nop
0x18009e618  lea     rcx, [rsp+348h+hKey]
0x18009e61d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e622  nop
0x18009e623  lea     rcx, [rsp+348h+var_2C0]
0x18009e62b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e630  mov     eax, ebx
0x18009e632  jmp     loc_18009E815
0x18009e637  mov     [rsp+348h+var_2E8], 0
0x18009e640  xor     edx, edx
0x18009e642  lea     rcx, [rsp+348h+var_2E8]
0x18009e647  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009e64c  mov     [rsp+348h+lpdwDisposition], 0; lpdwDisposition
0x18009e655  lea     rax, [rsp+348h+var_2E8]
0x18009e65a  mov     [rsp+348h+phkResult], rax; phkResult
0x18009e65f  mov     [rsp+348h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009e668  mov     [rsp+348h+samDesired], r14d; samDesired
0x18009e66d  mov     [rsp+348h+dwOptions], 0; int
0x18009e675  xor     r9d, r9d; lpClass
0x18009e678  xor     r8d, r8d; Reserved
0x18009e67b  lea     rdx, [rsp+348h+SubKey]; lpSubKey
0x18009e683  mov     rcx, [rsp+348h+hKey]; hKey
0x18009e688  call    cs:__imp_RegCreateKeyExW
0x18009e68e  test    eax, eax
0x18009e690  jz      short loc_18009E6DA
0x18009e692  mov     rcx, [rsp+348h]; this
0x18009e69a  mov     r9d, eax; char *
0x18009e69d  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e6a4  mov     edx, 482h; void *
0x18009e6a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009e6ae  mov     ebx, eax
0x18009e6b0  lea     rcx, [rsp+348h+var_2E8]
0x18009e6b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e6ba  nop
0x18009e6bb  lea     rcx, [rsp+348h+hKey]
0x18009e6c0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e6c5  nop
0x18009e6c6  lea     rcx, [rsp+348h+var_2C0]
0x18009e6ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e6d3  mov     eax, ebx
0x18009e6d5  jmp     loc_18009E815
0x18009e6da  lea     rdx, [rsp+348h+var_2E0]
0x18009e6df  mov     rcx, rdi
0x18009e6e2  call    ?_Unchecked_begin@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Hash<std::_Umap_traits<std::wstring,FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_begin(void)
0x18009e6e7  lea     rdx, [rsp+348h+var_2D8]
0x18009e6ec  mov     rcx, rdi
0x18009e6ef  call    ?_Unchecked_end@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4FirstSyncTrackedItemStatus@FirstSync@@@std@@@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Hash<std::_Umap_traits<std::wstring,FirstSync::FirstSyncTrackedItemStatus,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,FirstSync::FirstSyncTrackedItemStatus>>,0>>::_Unchecked_end(void)
0x18009e6f4  mov     rbx, [rsp+348h+var_2D8]
0x18009e6f9  cmp     [rsp+348h+var_2E0], rbx
0x18009e6fe  jnz     loc_18009E792
0x18009e704  mov     r9d, esi
0x18009e707  lea     r8, aLastcountofcom; "LastCountOfCompletedUris"
0x18009e70e  xor     edx, edx
0x18009e710  mov     rcx, [rsp+348h+hKey]
0x18009e715  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009e71b  mov     ebx, eax
0x18009e71d  test    eax, eax
0x18009e71f  jns     short loc_18009E768
0x18009e721  mov     rcx, [rsp+348h]; this
0x18009e729  mov     r9d, eax; char *
0x18009e72c  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e733  mov     edx, 48Ah; void *
0x18009e738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e73d  nop
0x18009e73e  lea     rcx, [rsp+348h+var_2E8]
0x18009e743  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e748  nop
0x18009e749  lea     rcx, [rsp+348h+hKey]
0x18009e74e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e753  nop
0x18009e754  lea     rcx, [rsp+348h+var_2C0]
0x18009e75c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e761  mov     eax, ebx
0x18009e763  jmp     loc_18009E815
0x18009e768  lea     rcx, [rsp+348h+var_2E8]
0x18009e76d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e772  nop
0x18009e773  lea     rcx, [rsp+348h+hKey]
0x18009e778  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e77d  nop
0x18009e77e  lea     rcx, [rsp+348h+var_2C0]
0x18009e786  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e78b  xor     eax, eax
0x18009e78d  jmp     loc_18009E815
0x18009e792  lea     rcx, [rsp+348h+var_2E0]
0x18009e797  call    ??D?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@U_Iterator_base0@2@@std@@QEBAAEBUCommandResult@@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator*(void)
0x18009e79c  mov     r9d, [rax+20h]
0x18009e7a0  mov     rcx, rax
0x18009e7a3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009e7a8  mov     r8, rax
0x18009e7ab  xor     edx, edx
0x18009e7ad  mov     rcx, [rsp+348h+var_2E8]
0x18009e7b2  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009e7b8  mov     edi, eax
0x18009e7ba  test    eax, eax
0x18009e7bc  jns     short loc_18009E802
0x18009e7be  mov     rcx, [rsp+348h]; this
0x18009e7c6  mov     r9d, eax; char *
0x18009e7c9  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e7d0  mov     edx, 486h; void *
0x18009e7d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e7da  nop
0x18009e7db  lea     rcx, [rsp+348h+var_2E8]
0x18009e7e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e7e5  nop
0x18009e7e6  lea     rcx, [rsp+348h+hKey]
0x18009e7eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e7f0  nop
0x18009e7f1  lea     rcx, [rsp+348h+var_2C0]
0x18009e7f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009e7fe  mov     eax, edi
0x18009e800  jmp     short loc_18009E815
0x18009e802  lea     rcx, [rsp+348h+var_2E0]
0x18009e807  call    ??E?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<CommandResult>>,std::_Iterator_base0>::operator++(void)
0x18009e80c  jmp     loc_18009E6F9
0x18009e811  mov     eax, [rsp+348h+var_2F0]
0x18009e815  mov     rcx, [rsp+348h+var_28]
0x18009e81d  xor     rcx, rsp; StackCookie
0x18009e820  call    __security_check_cookie
0x18009e825  mov     rbx, [rsp+348h+arg_0]
0x18009e82d  add     rsp, 330h
0x18009e834  pop     r14
0x18009e836  pop     rdi
0x18009e837  pop     rsi
0x18009e838  retn
```
