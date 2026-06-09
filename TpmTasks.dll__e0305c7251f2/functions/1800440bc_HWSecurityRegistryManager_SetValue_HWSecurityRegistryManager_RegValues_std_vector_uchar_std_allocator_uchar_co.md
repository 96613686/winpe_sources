# HWSecurityRegistryManager::SetValue(HWSecurityRegistryManager::RegValues,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800440bc`
- end: `0x18004438e`
- name: `?SetValue@HWSecurityRegistryManager@@SAJW4RegValues@1@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043d8c`
- `0x180043e8c`
- `0x180043fc8`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x18001a42c`
- `0x18001a450`
- `0x180023634`
- `0x18002386c`
- `0x180024780`
- `0x180042a14`
- `0x180042a6c`
- `0x180042c20`
- `0x180042f40`
- `0x1800435cc`
- `0x180043d34`
- `0x1800440bc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180044331`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004433e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004434c`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180044359`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180044331`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004433e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004434c`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180044359`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800441c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800441c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800442af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800442af`

## string_xrefs

- `0x1800441e9`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`
- `0x1800442e0`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
__int64 __fastcall HWSecurityRegistryManager::SetValue(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // r10d
  HKEY *phkResult; // rsi
  REGSAM samDesired; // r14d
  DWORD v8; // r15d
  __int64 KeyPath; // rax
  const WCHAR *v10; // rax
  unsigned int Key; // esi
  __int64 v12; // rcx
  unsigned int v13; // ebx
  const BYTE *v15; // rsi
  DWORD v16; // edi
  __int64 v17; // rcx
  __int64 v18; // r10
  DWORD v19; // ebx
  __int64 ValueName; // rax
  const WCHAR *v21; // rax
  LSTATUS v22; // eax
  unsigned int v23; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-138h]
  int dwOptionsa; // [rsp+20h] [rbp-138h]
  unsigned int v26; // [rsp+50h] [rbp-108h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-100h] BYREF
  _BYTE v28[16]; // [rsp+60h] [rbp-F8h] BYREF
  __int64 v29; // [rsp+70h] [rbp-E8h]
  _BYTE v30[32]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v31[96]; // [rsp+A0h] [rbp-B8h] BYREF
  DWORD v32; // [rsp+100h] [rbp-58h]
  REGSAM v33; // [rsp+104h] [rbp-54h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v3 = a1;
  hKey = 0;
  v26 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
    goto LABEL_19;
  v26 = *(_DWORD *)(v29 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v4,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v5 < *(_DWORD *)(v29 + 32) )
  {
LABEL_18:
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_19:
    std::_Xout_of_range("invalid map<K, T> key");
    return v26;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v31,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v29 + 40));
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  samDesired = v33;
  v8 = v32;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v31, v28);
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, v8, samDesired, 0, phkResult, 0);
  std::wstring::_Tidy_deallocate(v28);
  if ( Key )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x27A,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
            (const char *)Key,
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
LABEL_17:
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_18;
  }
  v26 = v3;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    v17,
    v28,
    &v26);
  if ( *(_BYTE *)(v29 + 25) || v3 < *(_DWORD *)(v29 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    goto LABEL_17;
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
0x1800440bc  mov     [rsp+arg_0], rbx
0x1800440c1  mov     [rsp+arg_10], rsi
0x1800440c6  push    rdi
0x1800440c7  push    r14
0x1800440c9  push    r15
0x1800440cb  sub     rsp, 140h
0x1800440d2  mov     rax, cs:__security_cookie
0x1800440d9  xor     rax, rsp
0x1800440dc  mov     [rsp+158h+var_28], rax
0x1800440e4  mov     rdi, rdx
0x1800440e7  mov     ebx, ecx
0x1800440e9  mov     [rsp+158h+hKey], 0
0x1800440f2  mov     [rsp+158h+var_108], ecx
0x1800440f6  lea     r8, [rsp+158h+var_108]
0x1800440fb  lea     rdx, [rsp+158h+var_F8]
0x180044100  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180044105  mov     rdx, [rsp+158h+var_E8]
0x18004410a  cmp     byte ptr [rdx+19h], 0
0x18004410e  jnz     loc_180044352
0x180044114  cmp     ebx, [rdx+20h]
0x180044117  jb      loc_180044352
0x18004411d  mov     r10d, [rdx+28h]
0x180044121  mov     [rsp+158h+var_108], r10d
0x180044126  lea     r8, [rsp+158h+var_108]
0x18004412b  lea     rdx, [rsp+158h+var_F8]
0x180044130  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180044135  mov     rdx, [rsp+158h+var_E8]
0x18004413a  cmp     byte ptr [rdx+19h], 0
0x18004413e  jnz     loc_180044345
0x180044144  cmp     r10d, [rdx+20h]
0x180044148  jb      loc_180044345
0x18004414e  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180044152  lea     rcx, [rsp+158h+var_B8]; this
0x18004415a  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18004415f  nop
0x180044160  lea     rcx, [rsp+158h+hKey]
0x180044165  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18004416a  mov     rsi, rax
0x18004416d  mov     r14d, [rsp+158h+var_54]
0x180044175  mov     r15d, [rsp+158h+var_58]
0x18004417d  lea     rdx, [rsp+158h+var_F8]
0x180044182  lea     rcx, [rsp+158h+var_B8]
0x18004418a  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x18004418f  mov     rcx, rax
0x180044192  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044197  mov     [rsp+158h+lpdwDisposition], 0; lpdwDisposition
0x1800441a0  mov     [rsp+158h+phkResult], rsi; phkResult
0x1800441a5  mov     [rsp+158h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800441ae  mov     [rsp+158h+samDesired], r14d; samDesired
0x1800441b3  mov     [rsp+158h+dwOptions], r15d; unsigned int
0x1800441b8  xor     r9d, r9d; lpClass
0x1800441bb  xor     r8d, r8d; Reserved
0x1800441be  mov     rdx, rax; lpSubKey
0x1800441c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800441c8  call    cs:__imp_RegCreateKeyExW
0x1800441ce  mov     esi, eax
0x1800441d0  lea     rcx, [rsp+158h+var_F8]
0x1800441d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441da  test    esi, esi
0x1800441dc  jz      short loc_18004421B
0x1800441de  mov     rcx, [rsp+158h]; this
0x1800441e6  mov     r9d, esi; char *
0x1800441e9  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x1800441f0  mov     edx, 27Ah; void *
0x1800441f5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800441fa  mov     ebx, eax
0x1800441fc  lea     rcx, [rsp+158h+var_B8]; this
0x180044204  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180044209  nop
0x18004420a  lea     rcx, [rsp+158h+hKey]
0x18004420f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044214  mov     eax, ebx
0x180044216  jmp     loc_180044364
0x18004421b  mov     rsi, [rdi]
0x18004421e  mov     edi, [rdi+8]
0x180044221  sub     edi, esi
0x180044223  mov     [rsp+158h+var_108], ebx
0x180044227  lea     r8, [rsp+158h+var_108]
0x18004422c  lea     rdx, [rsp+158h+var_F8]
0x180044231  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180044236  mov     r10, [rsp+158h+var_E8]
0x18004423b  cmp     byte ptr [r10+19h], 0
0x180044240  jnz     loc_180044337
0x180044246  cmp     ebx, [r10+20h]
0x18004424a  jb      loc_180044337
0x180044250  mov     [rsp+158h+var_108], ebx
0x180044254  lea     r8, [rsp+158h+var_108]
0x180044259  lea     rdx, [rsp+158h+var_F8]
0x18004425e  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x180044263  mov     rcx, [rsp+158h+var_E8]
0x180044268  cmp     byte ptr [rcx+19h], 0
0x18004426c  jnz     loc_18004432A
0x180044272  cmp     ebx, [rcx+20h]
0x180044275  jb      loc_18004432A
0x18004427b  mov     ebx, [r10+50h]
0x18004427f  add     rcx, 28h ; '('
0x180044283  lea     rdx, [rsp+158h+var_D8]
0x18004428b  call    ?GetValueName@RegistryValueEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryValueEntry::GetValueName(void)
0x180044290  mov     rcx, rax
0x180044293  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044298  mov     [rsp+158h+samDesired], edi; cbData
0x18004429c  mov     qword ptr [rsp+158h+dwOptions], rsi; int
0x1800442a1  mov     r9d, ebx; dwType
0x1800442a4  xor     r8d, r8d; Reserved
0x1800442a7  mov     rdx, rax; lpValueName
0x1800442aa  mov     rcx, [rsp+158h+hKey]; hKey
0x1800442af  call    cs:__imp_RegSetValueExW
0x1800442b5  mov     ebx, eax
0x1800442b7  test    eax, eax
0x1800442b9  jle     short loc_1800442C4
0x1800442bb  movzx   ebx, ax
0x1800442be  or      ebx, 80070000h
0x1800442c4  lea     rcx, [rsp+158h+var_D8]
0x1800442cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800442d1  test    ebx, ebx
0x1800442d3  jns     short loc_18004430E
0x1800442d5  mov     rcx, [rsp+158h]; this
0x1800442dd  mov     r9d, ebx; char *
0x1800442e0  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x1800442e7  mov     edx, 283h; void *
0x1800442ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442f1  nop
0x1800442f2  lea     rcx, [rsp+158h+var_B8]; this
0x1800442fa  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1800442ff  nop
0x180044300  lea     rcx, [rsp+158h+hKey]
0x180044305  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004430a  mov     eax, ebx
0x18004430c  jmp     short loc_180044364
0x18004430e  lea     rcx, [rsp+158h+var_B8]; this
0x180044316  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18004431b  nop
0x18004431c  lea     rcx, [rsp+158h+hKey]
0x180044321  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180044326  xor     eax, eax
0x180044328  jmp     short loc_180044364
0x18004432a  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180044331  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180044337  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18004433e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180044344  nop
0x180044345  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18004434c  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180044352  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180044359  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18004435f  nop
0x180044360  mov     eax, [rsp+158h+var_108]
0x180044364  mov     rcx, [rsp+158h+var_28]
0x18004436c  xor     rcx, rsp; StackCookie
0x18004436f  call    __security_check_cookie
0x180044374  lea     r11, [rsp+158h+var_18]
0x18004437c  mov     rbx, [r11+20h]
0x180044380  mov     rsi, [r11+30h]
0x180044384  mov     rsp, r11
0x180044387  pop     r15
0x180044389  pop     r14
0x18004438b  pop     rdi
0x18004438c  retn
```
