# HWSecurityRegistryManager::SetValue(HWSecurityRegistryManager::RegValues,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x18009b300`
- end: `0x18009b5e3`
- name: `?SetValue@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009b208`

## callees

- `0x180007270`
- `0x180057c6c`
- `0x18005bb6c`
- `0x18005bbf0`
- `0x18005d010`
- `0x18005d508`
- `0x18005d6e0`
- `0x18009a548`
- `0x18009a5a0`
- `0x18009a750`
- `0x18009aa80`
- `0x18009ad68`
- `0x18009b1e0`
- `0x18009b300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b4f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b4f2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b405`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b405`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b57a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b58d`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b5a1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b5b4`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b57a`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b58d`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b5a1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009b5b4`

## string_xrefs

- `0x18009b42c`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`
- `0x18009b529`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

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
  const WCHAR *v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rcx
  unsigned int v12; // ebx
  const BYTE *v14; // rsi
  DWORD v15; // edi
  __int64 v16; // rcx
  __int64 v17; // r10
  DWORD v18; // ebx
  __int64 ValueName; // rax
  const WCHAR *v20; // rax
  LSTATUS v21; // eax
  unsigned int v22; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-148h]
  int dwOptionsa; // [rsp+20h] [rbp-148h]
  unsigned int v25; // [rsp+50h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-110h] BYREF
  _BYTE v27[16]; // [rsp+60h] [rbp-108h] BYREF
  __int64 v28; // [rsp+70h] [rbp-F8h]
  _BYTE v29[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v30[96]; // [rsp+A0h] [rbp-C8h] BYREF
  DWORD v31; // [rsp+100h] [rbp-68h]
  REGSAM v32; // [rsp+104h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = a1;
  hKey = 0;
  v25 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v27,
    &v25);
  if ( *(_BYTE *)(v28 + 25) || v3 < *(_DWORD *)(v28 + 32) )
    goto LABEL_19;
  v25 = *(_DWORD *)(v28 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v4,
    v27,
    &v25);
  if ( *(_BYTE *)(v28 + 25) || v5 < *(_DWORD *)(v28 + 32) )
  {
LABEL_18:
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_19:
    std::_Xout_of_range("invalid map<K, T> key");
    return v25;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v30,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v28 + 40));
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  samDesired = v32;
  v7 = v31;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v30, v27);
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, v7, samDesired, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v27);
  if ( v10 )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x27A,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
            (const char *)v10,
            dwOptions);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v12;
  }
  v14 = *(const BYTE **)a2;
  v15 = *(_DWORD *)(a2 + 8) - *(_QWORD *)a2;
  v25 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v11,
    v27,
    &v25);
  if ( *(_BYTE *)(v28 + 25) || v3 < *(_DWORD *)(v28 + 32) )
  {
LABEL_17:
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_18;
  }
  v25 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v16,
    v27,
    &v25);
  if ( *(_BYTE *)(v28 + 25) || v3 < *(_DWORD *)(v28 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_17;
  }
  v18 = *(_DWORD *)(v17 + 80);
  ValueName = HWSecurityRegistryManager::RegistryValueEntry::GetValueName(v28 + 40, v29);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ValueName);
  v21 = RegSetValueExW(hKey, v20, 0, v18, v14, v15);
  v22 = v21;
  if ( v21 > 0 )
    v22 = (unsigned __int16)v21 | 0x80070000;
  std::wstring::_Tidy_deallocate(v29);
  if ( (v22 & 0x80000000) == 0 )
  {
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v22,
      dwOptionsa);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v22;
  }
}

```

## disassembly

```asm
0x18009b300  push    rbx
0x18009b302  push    rsi
0x18009b303  push    rdi
0x18009b304  push    r14
0x18009b306  sub     rsp, 148h
0x18009b30d  mov     rax, cs:__security_cookie
0x18009b314  xor     rax, rsp
0x18009b317  mov     [rsp+168h+var_38], rax
0x18009b31f  mov     rdi, rdx
0x18009b322  mov     ebx, ecx
0x18009b324  mov     [rsp+168h+hKey], 0
0x18009b32d  mov     [rsp+168h+var_118], ecx
0x18009b331  lea     r8, [rsp+168h+var_118]
0x18009b336  lea     rdx, [rsp+168h+var_108]
0x18009b33b  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x18009b340  mov     rdx, [rsp+168h+var_F8]
0x18009b345  cmp     byte ptr [rdx+19h], 0
0x18009b349  jnz     loc_18009B5AD
0x18009b34f  cmp     ebx, [rdx+20h]
0x18009b352  jb      loc_18009B5AD
0x18009b358  mov     r10d, [rdx+28h]
0x18009b35c  mov     [rsp+168h+var_118], r10d
0x18009b361  lea     r8, [rsp+168h+var_118]
0x18009b366  lea     rdx, [rsp+168h+var_108]
0x18009b36b  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x18009b370  mov     rdx, [rsp+168h+var_F8]
0x18009b375  cmp     byte ptr [rdx+19h], 0
0x18009b379  jnz     loc_18009B59A
0x18009b37f  cmp     r10d, [rdx+20h]
0x18009b383  jb      loc_18009B59A
0x18009b389  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x18009b38d  lea     rcx, [rsp+168h+var_C8]; this
0x18009b395  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18009b39a  nop
0x18009b39b  xor     edx, edx
0x18009b39d  lea     rcx, [rsp+168h+hKey]
0x18009b3a2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009b3a7  mov     esi, [rsp+168h+var_64]
0x18009b3ae  mov     r14d, [rsp+168h+var_68]
0x18009b3b6  lea     rdx, [rsp+168h+var_108]
0x18009b3bb  lea     rcx, [rsp+168h+var_C8]
0x18009b3c3  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x18009b3c8  mov     rcx, rax
0x18009b3cb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009b3d0  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x18009b3d9  lea     rcx, [rsp+168h+hKey]
0x18009b3de  mov     [rsp+168h+phkResult], rcx; phkResult
0x18009b3e3  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009b3ec  mov     [rsp+168h+samDesired], esi; samDesired
0x18009b3f0  mov     [rsp+168h+dwOptions], r14d; unsigned int
0x18009b3f5  xor     r9d, r9d; lpClass
0x18009b3f8  xor     r8d, r8d; Reserved
0x18009b3fb  mov     rdx, rax; lpSubKey
0x18009b3fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009b405  call    cs:__imp_RegCreateKeyExW
0x18009b40c  nop     dword ptr [rax+rax+00h]
0x18009b411  mov     esi, eax
0x18009b413  lea     rcx, [rsp+168h+var_108]
0x18009b418  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b41d  test    esi, esi
0x18009b41f  jz      short loc_18009B45E
0x18009b421  mov     rcx, [rsp+168h]; this
0x18009b429  mov     r9d, esi; char *
0x18009b42c  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x18009b433  mov     edx, 27Ah; void *
0x18009b438  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009b43d  mov     ebx, eax
0x18009b43f  lea     rcx, [rsp+168h+var_C8]; this
0x18009b447  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009b44c  nop
0x18009b44d  lea     rcx, [rsp+168h+hKey]
0x18009b452  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b457  mov     eax, ebx
0x18009b459  jmp     loc_18009B5C5
0x18009b45e  mov     rsi, [rdi]
0x18009b461  mov     edi, [rdi+8]
0x18009b464  sub     edi, esi
0x18009b466  mov     [rsp+168h+var_118], ebx
0x18009b46a  lea     r8, [rsp+168h+var_118]
0x18009b46f  lea     rdx, [rsp+168h+var_108]
0x18009b474  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x18009b479  mov     r10, [rsp+168h+var_F8]
0x18009b47e  cmp     byte ptr [r10+19h], 0
0x18009b483  jnz     loc_18009B586
0x18009b489  cmp     ebx, [r10+20h]
0x18009b48d  jb      loc_18009B586
0x18009b493  mov     [rsp+168h+var_118], ebx
0x18009b497  lea     r8, [rsp+168h+var_118]
0x18009b49c  lea     rdx, [rsp+168h+var_108]
0x18009b4a1  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x18009b4a6  mov     rcx, [rsp+168h+var_F8]
0x18009b4ab  cmp     byte ptr [rcx+19h], 0
0x18009b4af  jnz     loc_18009B573
0x18009b4b5  cmp     ebx, [rcx+20h]
0x18009b4b8  jb      loc_18009B573
0x18009b4be  mov     ebx, [r10+50h]
0x18009b4c2  add     rcx, 28h ; '('
0x18009b4c6  lea     rdx, [rsp+168h+var_E8]
0x18009b4ce  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x18009b4d3  mov     rcx, rax
0x18009b4d6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009b4db  mov     [rsp+168h+samDesired], edi; cbData
0x18009b4df  mov     qword ptr [rsp+168h+dwOptions], rsi; int
0x18009b4e4  mov     r9d, ebx; dwType
0x18009b4e7  xor     r8d, r8d; Reserved
0x18009b4ea  mov     rdx, rax; lpValueName
0x18009b4ed  mov     rcx, [rsp+168h+hKey]; hKey
0x18009b4f2  call    cs:__imp_RegSetValueExW
0x18009b4f9  nop     dword ptr [rax+rax+00h]
0x18009b4fe  mov     ebx, eax
0x18009b500  test    eax, eax
0x18009b502  jle     short loc_18009B50D
0x18009b504  movzx   ebx, ax
0x18009b507  or      ebx, 80070000h
0x18009b50d  lea     rcx, [rsp+168h+var_E8]
0x18009b515  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b51a  test    ebx, ebx
0x18009b51c  jns     short loc_18009B557
0x18009b51e  mov     rcx, [rsp+168h]; this
0x18009b526  mov     r9d, ebx; char *
0x18009b529  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x18009b530  mov     edx, 283h; void *
0x18009b535  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009b53a  nop
0x18009b53b  lea     rcx, [rsp+168h+var_C8]; this
0x18009b543  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009b548  nop
0x18009b549  lea     rcx, [rsp+168h+hKey]
0x18009b54e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b553  mov     eax, ebx
0x18009b555  jmp     short loc_18009B5C5
0x18009b557  lea     rcx, [rsp+168h+var_C8]; this
0x18009b55f  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009b564  nop
0x18009b565  lea     rcx, [rsp+168h+hKey]
0x18009b56a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009b56f  xor     eax, eax
0x18009b571  jmp     short loc_18009B5C5
0x18009b573  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18009b57a  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009b581  nop     dword ptr [rax+rax+00h]
0x18009b586  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18009b58d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009b594  nop     dword ptr [rax+rax+00h]
0x18009b599  nop
0x18009b59a  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18009b5a1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009b5a8  nop     dword ptr [rax+rax+00h]
0x18009b5ad  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18009b5b4  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009b5bb  nop     dword ptr [rax+rax+00h]
0x18009b5c0  nop
0x18009b5c1  mov     eax, [rsp+168h+var_118]
0x18009b5c5  mov     rcx, [rsp+168h+var_38]
0x18009b5cd  xor     rcx, rsp; StackCookie
0x18009b5d0  call    __security_check_cookie
0x18009b5d5  add     rsp, 148h
0x18009b5dc  pop     r14
0x18009b5de  pop     rdi
0x18009b5df  pop     rsi
0x18009b5e0  pop     rbx
0x18009b5e1  retn
```
