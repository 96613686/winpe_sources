# HWSecurityRegistryManager::SetValue(HWSecurityRegistryManager::RegValues,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180051cb4`
- end: `0x180051f77`
- name: `?SetValue@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae160`

## callees

- `0x18000782c`
- `0x18000e960`
- `0x180010030`
- `0x18002459c`
- `0x18002e688`
- `0x18002f414`
- `0x18003031c`
- `0x180032b6c`
- `0x180032c20`
- `0x180048304`
- `0x180051cb4`
- `0x180052134`
- `0x18005cee0`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f26`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f33`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f41`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f4e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f26`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f33`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f41`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180051f4e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051dbb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051dbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180051ea4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180051ea4`

## string_xrefs

- `0x180051ddc`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`
- `0x180051ed5`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::SetValue(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // r10d
  REGSAM samDesired; // esi
  DWORD v7; // r14d
  __int64 KeyPath; // rax
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // ebx
  const BYTE *v13; // rsi
  DWORD v14; // edi
  __int64 v15; // rcx
  __int64 v16; // r10
  DWORD v17; // ebx
  __int64 ValueName; // rax
  LSTATUS v19; // eax
  unsigned int v20; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-148h]
  int dwOptionsa; // [rsp+20h] [rbp-148h]
  unsigned int v23; // [rsp+50h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-110h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-108h] BYREF
  __int64 v26; // [rsp+70h] [rbp-F8h]
  _BYTE v27[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v28[96]; // [rsp+A0h] [rbp-C8h] BYREF
  DWORD v29; // [rsp+100h] [rbp-68h]
  REGSAM v30; // [rsp+104h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = a1;
  hKey = 0;
  v23 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v25,
    &v23);
  if ( *(_BYTE *)(v26 + 25) || v3 < *(_DWORD *)(v26 + 32) )
    goto LABEL_23;
  v23 = *(_DWORD *)(v26 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v4,
    v25,
    &v23);
  if ( *(_BYTE *)(v26 + 25) || v5 < *(_DWORD *)(v26 + 32) )
  {
LABEL_22:
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_23:
    std::_Xout_of_range("invalid map<K, T> key");
    return v23;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v28,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v26 + 40));
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  samDesired = v30;
  v7 = v29;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v28, v25);
  if ( *(_QWORD *)(KeyPath + 24) > 7u )
    KeyPath = *(_QWORD *)KeyPath;
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)KeyPath, 0, 0, v7, samDesired, 0, &hKey, 0);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v25);
  if ( v9 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x27A,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
            (const char *)v9,
            dwOptions);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v11;
  }
  v13 = *(const BYTE **)a2;
  v14 = *(_DWORD *)(a2 + 8) - *(_QWORD *)a2;
  v23 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v10,
    v25,
    &v23);
  if ( *(_BYTE *)(v26 + 25) || v3 < *(_DWORD *)(v26 + 32) )
  {
LABEL_21:
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_22;
  }
  v23 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v15,
    v25,
    &v23);
  if ( *(_BYTE *)(v26 + 25) || v3 < *(_DWORD *)(v26 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_21;
  }
  v17 = *(_DWORD *)(v16 + 80);
  ValueName = HWSecurityRegistryManager::RegistryValueEntry::GetValueName(v26 + 40, v27);
  if ( *(_QWORD *)(ValueName + 24) > 7u )
    ValueName = *(_QWORD *)ValueName;
  v19 = RegSetValueExW(hKey, (LPCWSTR)ValueName, 0, v17, v13, v14);
  v20 = v19;
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v27);
  if ( (v20 & 0x80000000) == 0 )
  {
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v20,
      dwOptionsa);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v28);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v20;
  }
}

```

## disassembly

```asm
0x180051cb4  push    rbx
0x180051cb6  push    rsi
0x180051cb7  push    rdi
0x180051cb8  push    r14
0x180051cba  sub     rsp, 148h
0x180051cc1  mov     rax, cs:__security_cookie
0x180051cc8  xor     rax, rsp
0x180051ccb  mov     [rsp+168h+var_38], rax
0x180051cd3  mov     rdi, rdx
0x180051cd6  mov     ebx, ecx
0x180051cd8  mov     [rsp+168h+hKey], 0
0x180051ce1  mov     [rsp+168h+var_118], ecx
0x180051ce5  lea     r8, [rsp+168h+var_118]
0x180051cea  lea     rdx, [rsp+168h+var_108]
0x180051cef  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180051cf4  mov     rdx, [rsp+168h+var_F8]
0x180051cf9  cmp     byte ptr [rdx+19h], 0
0x180051cfd  jnz     loc_180051F47
0x180051d03  cmp     ebx, [rdx+20h]
0x180051d06  jb      loc_180051F47
0x180051d0c  mov     r10d, [rdx+28h]
0x180051d10  mov     [rsp+168h+var_118], r10d
0x180051d15  lea     r8, [rsp+168h+var_118]
0x180051d1a  lea     rdx, [rsp+168h+var_108]
0x180051d1f  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180051d24  mov     rdx, [rsp+168h+var_F8]
0x180051d29  cmp     byte ptr [rdx+19h], 0
0x180051d2d  jnz     loc_180051F3A
0x180051d33  cmp     r10d, [rdx+20h]
0x180051d37  jb      loc_180051F3A
0x180051d3d  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180051d41  lea     rcx, [rsp+168h+var_C8]; this
0x180051d49  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180051d4e  nop
0x180051d4f  xor     edx, edx
0x180051d51  lea     rcx, [rsp+168h+hKey]
0x180051d56  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180051d5b  mov     esi, [rsp+168h+var_64]
0x180051d62  mov     r14d, [rsp+168h+var_68]
0x180051d6a  lea     rdx, [rsp+168h+var_108]
0x180051d6f  lea     rcx, [rsp+168h+var_C8]
0x180051d77  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x180051d7c  cmp     qword ptr [rax+18h], 7
0x180051d81  jbe     short loc_180051D86
0x180051d83  mov     rax, [rax]
0x180051d86  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x180051d8f  lea     rcx, [rsp+168h+hKey]
0x180051d94  mov     [rsp+168h+phkResult], rcx; phkResult
0x180051d99  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180051da2  mov     [rsp+168h+samDesired], esi; samDesired
0x180051da6  mov     [rsp+168h+dwOptions], r14d; unsigned int
0x180051dab  xor     r9d, r9d; lpClass
0x180051dae  xor     r8d, r8d; Reserved
0x180051db1  mov     rdx, rax; lpSubKey
0x180051db4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051dbb  call    cs:__imp_RegCreateKeyExW
0x180051dc1  mov     esi, eax
0x180051dc3  lea     rcx, [rsp+168h+var_108]
0x180051dc8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180051dcd  test    esi, esi
0x180051dcf  jz      short loc_180051E0E
0x180051dd1  mov     rcx, [rsp+168h]; this
0x180051dd9  mov     r9d, esi; char *
0x180051ddc  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180051de3  mov     edx, 27Ah; void *
0x180051de8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051ded  mov     ebx, eax
0x180051def  lea     rcx, [rsp+168h+var_C8]; this
0x180051df7  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180051dfc  nop
0x180051dfd  lea     rcx, [rsp+168h+hKey]
0x180051e02  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051e07  mov     eax, ebx
0x180051e09  jmp     loc_180051F59
0x180051e0e  mov     rsi, [rdi]
0x180051e11  mov     edi, [rdi+8]
0x180051e14  sub     edi, esi
0x180051e16  mov     [rsp+168h+var_118], ebx
0x180051e1a  lea     r8, [rsp+168h+var_118]
0x180051e1f  lea     rdx, [rsp+168h+var_108]
0x180051e24  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180051e29  mov     r10, [rsp+168h+var_F8]
0x180051e2e  cmp     byte ptr [r10+19h], 0
0x180051e33  jnz     loc_180051F2C
0x180051e39  cmp     ebx, [r10+20h]
0x180051e3d  jb      loc_180051F2C
0x180051e43  mov     [rsp+168h+var_118], ebx
0x180051e47  lea     r8, [rsp+168h+var_118]
0x180051e4c  lea     rdx, [rsp+168h+var_108]
0x180051e51  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180051e56  mov     rcx, [rsp+168h+var_F8]
0x180051e5b  cmp     byte ptr [rcx+19h], 0
0x180051e5f  jnz     loc_180051F1F
0x180051e65  cmp     ebx, [rcx+20h]
0x180051e68  jb      loc_180051F1F
0x180051e6e  mov     ebx, [r10+50h]
0x180051e72  add     rcx, 28h ; '('
0x180051e76  lea     rdx, [rsp+168h+var_E8]
0x180051e7e  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x180051e83  cmp     qword ptr [rax+18h], 7
0x180051e88  jbe     short loc_180051E8D
0x180051e8a  mov     rax, [rax]
0x180051e8d  mov     [rsp+168h+samDesired], edi; cbData
0x180051e91  mov     qword ptr [rsp+168h+dwOptions], rsi; int
0x180051e96  mov     r9d, ebx; dwType
0x180051e99  xor     r8d, r8d; Reserved
0x180051e9c  mov     rdx, rax; lpValueName
0x180051e9f  mov     rcx, [rsp+168h+hKey]; hKey
0x180051ea4  call    cs:__imp_RegSetValueExW
0x180051eaa  mov     ebx, eax
0x180051eac  test    eax, eax
0x180051eae  jle     short loc_180051EB9
0x180051eb0  movzx   ebx, ax
0x180051eb3  or      ebx, 80070000h
0x180051eb9  lea     rcx, [rsp+168h+var_E8]
0x180051ec1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180051ec6  test    ebx, ebx
0x180051ec8  jns     short loc_180051F03
0x180051eca  mov     rcx, [rsp+168h]; this
0x180051ed2  mov     r9d, ebx; char *
0x180051ed5  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180051edc  mov     edx, 283h; void *
0x180051ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051ee6  nop
0x180051ee7  lea     rcx, [rsp+168h+var_C8]; this
0x180051eef  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180051ef4  nop
0x180051ef5  lea     rcx, [rsp+168h+hKey]
0x180051efa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051eff  mov     eax, ebx
0x180051f01  jmp     short loc_180051F59
0x180051f03  lea     rcx, [rsp+168h+var_C8]; this
0x180051f0b  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180051f10  nop
0x180051f11  lea     rcx, [rsp+168h+hKey]
0x180051f16  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051f1b  xor     eax, eax
0x180051f1d  jmp     short loc_180051F59
0x180051f1f  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180051f26  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180051f2c  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180051f33  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180051f39  nop
0x180051f3a  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180051f41  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180051f47  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180051f4e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180051f54  nop
0x180051f55  mov     eax, [rsp+168h+var_118]
0x180051f59  mov     rcx, [rsp+168h+var_38]
0x180051f61  xor     rcx, rsp; StackCookie
0x180051f64  call    __security_check_cookie
0x180051f69  add     rsp, 148h
0x180051f70  pop     r14
0x180051f72  pop     rdi
0x180051f73  pop     rsi
0x180051f74  pop     rbx
0x180051f75  retn
```
