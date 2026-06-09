# HWSecurityRegistryManager::CreateKey(HWSecurityRegistryManager::RegValues)

- ea: `0x180043198`
- end: `0x180043359`
- name: `?CreateKey@HWSecurityRegistryManager@@SAJW4RegValues@1@@Z`
- size: `449`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a474`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x18001a42c`
- `0x180023634`
- `0x18002386c`
- `0x180024780`
- `0x180042a14`
- `0x180042a6c`
- `0x180042c20`
- `0x180042f40`
- `0x180043198`
- `0x1800435cc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004331b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043328`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18004331b`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043328`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004329c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004329c`

## string_xrefs

- `0x1800432ca`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::CreateKey(__int64 a1)
{
  __int64 v1; // rcx
  unsigned int v2; // r10d
  HKEY *phkResult; // rbx
  REGSAM samDesired; // edi
  DWORD v5; // esi
  __int64 KeyPath; // rax
  const WCHAR *v7; // rax
  LSTATUS Key; // eax
  unsigned int v9; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-108h]
  unsigned int v12; // [rsp+50h] [rbp-D8h] BYREF
  HKEY v13; // [rsp+58h] [rbp-D0h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+70h] [rbp-B8h]
  _BYTE v16[96]; // [rsp+80h] [rbp-A8h] BYREF
  DWORD v17; // [rsp+E0h] [rbp-48h]
  REGSAM v18; // [rsp+E4h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v13 = 0;
  v12 = 36;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<enum HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegValues>(
    a1,
    v14,
    &v12);
  if ( *(_BYTE *)(v15 + 25) || *(_DWORD *)(v15 + 32) > 0x24u )
    goto LABEL_11;
  v12 = *(_DWORD *)(v15 + 40);
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    v1,
    v14,
    &v12);
  if ( *(_BYTE *)(v15 + 25) || v2 < *(_DWORD *)(v15 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
LABEL_11:
    std::_Xout_of_range("invalid map<K, T> key");
    return v12;
  }
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v16,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v15 + 40));
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
  samDesired = v18;
  v5 = v17;
  KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v16, v14);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, v5, samDesired, 0, phkResult, 0);
  v9 = Key;
  if ( Key > 0 )
    v9 = (unsigned __int16)Key | 0x80070000;
  std::wstring::_Tidy_deallocate(v14);
  if ( (v9 & 0x80000000) == 0 )
  {
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v16);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
      (const char *)v9,
      dwOptions);
    HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v16);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
    return v9;
  }
}

```

## disassembly

```asm
0x180043198  mov     [rsp+arg_0], rbx
0x18004319d  mov     [rsp+arg_8], rsi
0x1800431a2  push    rdi
0x1800431a3  sub     rsp, 120h
0x1800431aa  mov     rax, cs:__security_cookie
0x1800431b1  xor     rax, rsp
0x1800431b4  mov     [rsp+128h+var_18], rax
0x1800431bc  mov     [rsp+128h+var_D0], 0
0x1800431c5  mov     [rsp+128h+var_D8], 24h ; '$'
0x1800431cd  lea     r8, [rsp+128h+var_D8]
0x1800431d2  lea     rdx, [rsp+128h+var_C8]
0x1800431d7  call    ??$_Find_lower_bound@W4RegValues@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@U?$less@W4RegValues@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegValues@HWSecurityRegistryManager@@VRegistryValueEntry@2@@std@@PEAX@std@@@1@AEBW4RegValues@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegValues,HWSecurityRegistryManager::RegistryValueEntry,std::less<HWSecurityRegistryManager::RegValues>,std::allocator<std::pair<HWSecurityRegistryManager::RegValues const,HWSecurityRegistryManager::RegistryValueEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegValues>(HWSecurityRegistryManager::RegValues const &)
0x1800431dc  mov     rdx, [rsp+128h+var_B8]
0x1800431e1  cmp     byte ptr [rdx+19h], 0
0x1800431e5  jnz     loc_180043321
0x1800431eb  cmp     dword ptr [rdx+20h], 24h ; '$'
0x1800431ef  ja      loc_180043321
0x1800431f5  mov     r10d, [rdx+28h]
0x1800431f9  mov     [rsp+128h+var_D8], r10d
0x1800431fe  lea     r8, [rsp+128h+var_D8]
0x180043203  lea     rdx, [rsp+128h+var_C8]
0x180043208  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x18004320d  mov     rdx, [rsp+128h+var_B8]
0x180043212  cmp     byte ptr [rdx+19h], 0
0x180043216  jnz     loc_180043314
0x18004321c  cmp     r10d, [rdx+20h]
0x180043220  jb      loc_180043314
0x180043226  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x18004322a  lea     rcx, [rsp+128h+var_A8]; this
0x180043232  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180043237  nop
0x180043238  lea     rcx, [rsp+128h+var_D0]
0x18004323d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180043242  mov     rbx, rax
0x180043245  mov     edi, [rsp+128h+var_44]
0x18004324c  mov     esi, [rsp+128h+var_48]
0x180043253  lea     rdx, [rsp+128h+var_C8]
0x180043258  lea     rcx, [rsp+128h+var_A8]
0x180043260  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x180043265  mov     rcx, rax
0x180043268  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004326d  mov     [rsp+128h+lpdwDisposition], 0; lpdwDisposition
0x180043276  mov     [rsp+128h+phkResult], rbx; phkResult
0x18004327b  mov     [rsp+128h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180043284  mov     [rsp+128h+samDesired], edi; samDesired
0x180043288  mov     [rsp+128h+dwOptions], esi; int
0x18004328c  xor     r9d, r9d; lpClass
0x18004328f  xor     r8d, r8d; Reserved
0x180043292  mov     rdx, rax; lpSubKey
0x180043295  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004329c  call    cs:__imp_RegCreateKeyExW
0x1800432a2  mov     ebx, eax
0x1800432a4  test    eax, eax
0x1800432a6  jle     short loc_1800432B1
0x1800432a8  movzx   ebx, ax
0x1800432ab  or      ebx, 80070000h
0x1800432b1  lea     rcx, [rsp+128h+var_C8]
0x1800432b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800432bb  test    ebx, ebx
0x1800432bd  jns     short loc_1800432F8
0x1800432bf  mov     rcx, [rsp+128h]; this
0x1800432c7  mov     r9d, ebx; char *
0x1800432ca  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x1800432d1  mov     edx, 165h; void *
0x1800432d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800432db  nop
0x1800432dc  lea     rcx, [rsp+128h+var_A8]; this
0x1800432e4  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1800432e9  nop
0x1800432ea  lea     rcx, [rsp+128h+var_D0]
0x1800432ef  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800432f4  mov     eax, ebx
0x1800432f6  jmp     short loc_180043333
0x1800432f8  lea     rcx, [rsp+128h+var_A8]; this
0x180043300  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180043305  nop
0x180043306  lea     rcx, [rsp+128h+var_D0]
0x18004330b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043310  xor     eax, eax
0x180043312  jmp     short loc_180043333
0x180043314  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18004331b  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180043321  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180043328  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18004332e  nop
0x18004332f  mov     eax, [rsp+128h+var_D8]
0x180043333  mov     rcx, [rsp+128h+var_18]
0x18004333b  xor     rcx, rsp; StackCookie
0x18004333e  call    __security_check_cookie
0x180043343  lea     r11, [rsp+128h+var_8]
0x18004334b  mov     rbx, [r11+10h]
0x18004334f  mov     rsi, [r11+18h]
0x180043353  mov     rsp, r11
0x180043356  pop     rdi
0x180043357  retn
```
