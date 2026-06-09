# HWSecurityRegistryManager::SetValue(HWSecurityRegistryManager::RegValues,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x180141a34`
- end: `0x180141d17`
- name: `?SetValue@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180141938`

## callees

- `0x180019000`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180104108`
- `0x180140df8`
- `0x180140e50`
- `0x180140ed8`
- `0x1801411d0`
- `0x1801414cc`
- `0x180141914`
- `0x180141a34`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cc6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cd3`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141ce1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cee`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cc6`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cd3`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141ce1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180141cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180141c44`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180141c44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180141ae6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180141ae6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180141b5d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180141b5d`

## string_xrefs

- `0x180141b7e`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`
- `0x180141c75`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::SetValue(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // r10d
  HKEY v6; // rdi
  REGSAM samDesired; // edi
  DWORD v8; // r14d
  __int64 KeyPath; // rax
  const WCHAR *v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rcx
  unsigned int v13; // ebx
  const BYTE *v15; // rdi
  DWORD v16; // esi
  __int64 v17; // rcx
  __int64 v18; // r10
  DWORD v19; // ebx
  __int64 ValueName; // rax
  const WCHAR *v21; // rax
  LSTATUS v22; // eax
  unsigned int v23; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-148h]
  int dwOptionsa; // [rsp+20h] [rbp-148h]
  unsigned int v26; // [rsp+50h] [rbp-118h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-110h] BYREF
  _QWORD v28[2]; // [rsp+60h] [rbp-108h] BYREF
  __int64 v29; // [rsp+70h] [rbp-F8h]
  _BYTE v30[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v31[96]; // [rsp+A0h] [rbp-C8h] BYREF
  DWORD v32; // [rsp+100h] [rbp-68h]
  REGSAM v33; // [rsp+104h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v3 = a1;
  hKey = 0;
  v26 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
    goto LABEL_21;
  v26 = *(_DWORD *)(v29 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v4,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v5 < *(_DWORD *)(v29 + 32) )
  {
LABEL_20:
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_21:
    std::_Xout_of_range("invalid map<K, T> key");
    return v26;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v31,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v29 + 40));
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
  }
  hKey = 0;
  samDesired = v33;
  v8 = v32;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v31, v28);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, v8, samDesired, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v28);
  if ( v11 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x27A,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
            (const char *)v11,
            dwOptions);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v13;
  }
  v15 = *(const BYTE **)a2;
  v16 = *(_DWORD *)(a2 + 8) - *(_QWORD *)a2;
  v26 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v12,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
  {
LABEL_19:
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_20;
  }
  v26 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v17,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_19;
  }
  v19 = *(_DWORD *)(v18 + 80);
  ValueName = HWSecurityRegistryManager::RegistryValueEntry::GetValueName(v29 + 40, v30);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ValueName);
  v22 = RegSetValueExW(hKey, v21, 0, v19, v15, v16);
  v23 = v22;
  if ( v22 > 0 )
    v23 = (unsigned __int16)v22 | 0x80070000;
  std::wstring::_Tidy_deallocate(v30);
  if ( (v23 & 0x80000000) == 0 )
  {
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v23,
      dwOptionsa);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v23;
  }
}

```

## disassembly

```asm
0x180141a34  push    rbx
0x180141a36  push    rsi
0x180141a37  push    rdi
0x180141a38  push    r14
0x180141a3a  sub     rsp, 148h
0x180141a41  mov     rax, cs:__security_cookie
0x180141a48  xor     rax, rsp
0x180141a4b  mov     [rsp+168h+var_38], rax
0x180141a53  mov     rsi, rdx
0x180141a56  mov     ebx, ecx
0x180141a58  mov     [rsp+168h+hKey], 0
0x180141a61  mov     [rsp+168h+var_118], ecx
0x180141a65  lea     r8, [rsp+168h+var_118]
0x180141a6a  lea     rdx, [rsp+168h+var_108]
0x180141a6f  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180141a74  mov     rdx, [rsp+168h+var_F8]
0x180141a79  cmp     byte ptr [rdx+19h], 0
0x180141a7d  jnz     loc_180141CE7
0x180141a83  cmp     ebx, [rdx+20h]
0x180141a86  jb      loc_180141CE7
0x180141a8c  mov     r10d, [rdx+28h]
0x180141a90  mov     [rsp+168h+var_118], r10d
0x180141a95  lea     r8, [rsp+168h+var_118]
0x180141a9a  lea     rdx, [rsp+168h+var_108]
0x180141a9f  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180141aa4  mov     rdx, [rsp+168h+var_F8]
0x180141aa9  cmp     byte ptr [rdx+19h], 0
0x180141aad  jnz     loc_180141CDA
0x180141ab3  cmp     r10d, [rdx+20h]
0x180141ab7  jb      loc_180141CDA
0x180141abd  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180141ac1  lea     rcx, [rsp+168h+var_C8]; this
0x180141ac9  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180141ace  nop
0x180141acf  mov     rdi, [rsp+168h+hKey]
0x180141ad4  test    rdi, rdi
0x180141ad7  jz      short loc_180141AF6
0x180141ad9  lea     rcx, [rsp+168h+var_118]; this
0x180141ade  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180141ae3  mov     rcx, rdi; hKey
0x180141ae6  call    cs:__imp_RegCloseKey
0x180141aec  lea     rcx, [rsp+168h+var_118]; this
0x180141af1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180141af6  mov     [rsp+168h+hKey], 0
0x180141aff  mov     edi, [rsp+168h+var_64]
0x180141b06  mov     r14d, [rsp+168h+var_68]
0x180141b0e  lea     rdx, [rsp+168h+var_108]
0x180141b13  lea     rcx, [rsp+168h+var_C8]
0x180141b1b  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x180141b20  mov     rcx, rax
0x180141b23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180141b28  mov     [rsp+168h+lpdwDisposition], 0; lpdwDisposition
0x180141b31  lea     rcx, [rsp+168h+hKey]
0x180141b36  mov     [rsp+168h+phkResult], rcx; phkResult
0x180141b3b  mov     [rsp+168h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180141b44  mov     [rsp+168h+samDesired], edi; samDesired
0x180141b48  mov     [rsp+168h+dwOptions], r14d; unsigned int
0x180141b4d  xor     r9d, r9d; lpClass
0x180141b50  xor     r8d, r8d; Reserved
0x180141b53  mov     rdx, rax; lpSubKey
0x180141b56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180141b5d  call    cs:__imp_RegCreateKeyExW
0x180141b63  mov     edi, eax
0x180141b65  lea     rcx, [rsp+168h+var_108]
0x180141b6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141b6f  test    edi, edi
0x180141b71  jz      short loc_180141BB0
0x180141b73  mov     rcx, [rsp+168h]; this
0x180141b7b  mov     r9d, edi; char *
0x180141b7e  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180141b85  mov     edx, 27Ah; void *
0x180141b8a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180141b8f  mov     ebx, eax
0x180141b91  lea     rcx, [rsp+168h+var_C8]; this
0x180141b99  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180141b9e  nop
0x180141b9f  lea     rcx, [rsp+168h+hKey]
0x180141ba4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180141ba9  mov     eax, ebx
0x180141bab  jmp     loc_180141CF9
0x180141bb0  mov     rdi, [rsi]
0x180141bb3  mov     esi, [rsi+8]
0x180141bb6  sub     esi, edi
0x180141bb8  mov     [rsp+168h+var_118], ebx
0x180141bbc  lea     r8, [rsp+168h+var_118]
0x180141bc1  lea     rdx, [rsp+168h+var_108]
0x180141bc6  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180141bcb  mov     r10, [rsp+168h+var_F8]
0x180141bd0  cmp     byte ptr [r10+19h], 0
0x180141bd5  jnz     loc_180141CCC
0x180141bdb  cmp     ebx, [r10+20h]
0x180141bdf  jb      loc_180141CCC
0x180141be5  mov     [rsp+168h+var_118], ebx
0x180141be9  lea     r8, [rsp+168h+var_118]
0x180141bee  lea     rdx, [rsp+168h+var_108]
0x180141bf3  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180141bf8  mov     rcx, [rsp+168h+var_F8]
0x180141bfd  cmp     byte ptr [rcx+19h], 0
0x180141c01  jnz     loc_180141CBF
0x180141c07  cmp     ebx, [rcx+20h]
0x180141c0a  jb      loc_180141CBF
0x180141c10  mov     ebx, [r10+50h]
0x180141c14  add     rcx, 28h ; '('
0x180141c18  lea     rdx, [rsp+168h+var_E8]
0x180141c20  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x180141c25  mov     rcx, rax
0x180141c28  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180141c2d  mov     [rsp+168h+samDesired], esi; cbData
0x180141c31  mov     qword ptr [rsp+168h+dwOptions], rdi; int
0x180141c36  mov     r9d, ebx; dwType
0x180141c39  xor     r8d, r8d; Reserved
0x180141c3c  mov     rdx, rax; lpValueName
0x180141c3f  mov     rcx, [rsp+168h+hKey]; hKey
0x180141c44  call    cs:__imp_RegSetValueExW
0x180141c4a  mov     ebx, eax
0x180141c4c  test    eax, eax
0x180141c4e  jle     short loc_180141C59
0x180141c50  movzx   ebx, ax
0x180141c53  or      ebx, 80070000h
0x180141c59  lea     rcx, [rsp+168h+var_E8]
0x180141c61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180141c66  test    ebx, ebx
0x180141c68  jns     short loc_180141CA3
0x180141c6a  mov     rcx, [rsp+168h]; this
0x180141c72  mov     r9d, ebx; char *
0x180141c75  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180141c7c  mov     edx, 283h; void *
0x180141c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141c86  nop
0x180141c87  lea     rcx, [rsp+168h+var_C8]; this
0x180141c8f  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180141c94  nop
0x180141c95  lea     rcx, [rsp+168h+hKey]
0x180141c9a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180141c9f  mov     eax, ebx
0x180141ca1  jmp     short loc_180141CF9
0x180141ca3  lea     rcx, [rsp+168h+var_C8]; this
0x180141cab  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180141cb0  nop
0x180141cb1  lea     rcx, [rsp+168h+hKey]
0x180141cb6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180141cbb  xor     eax, eax
0x180141cbd  jmp     short loc_180141CF9
0x180141cbf  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180141cc6  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180141ccc  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180141cd3  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180141cd9  nop
0x180141cda  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180141ce1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180141ce7  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180141cee  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180141cf4  nop
0x180141cf5  mov     eax, [rsp+168h+var_118]
0x180141cf9  mov     rcx, [rsp+168h+var_38]
0x180141d01  xor     rcx, rsp; StackCookie
0x180141d04  call    __security_check_cookie
0x180141d09  add     rsp, 148h
0x180141d10  pop     r14
0x180141d12  pop     rdi
0x180141d13  pop     rsi
0x180141d14  pop     rbx
0x180141d15  retn
```
