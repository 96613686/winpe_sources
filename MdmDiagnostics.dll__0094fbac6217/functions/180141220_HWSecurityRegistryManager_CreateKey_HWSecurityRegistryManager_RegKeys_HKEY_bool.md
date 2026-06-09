# HWSecurityRegistryManager::CreateKey(HWSecurityRegistryManager::RegKeys,HKEY__ * *,bool *)

- ea: `0x180141220`
- end: `0x1801413f0`
- name: `?CreateKey@HWSecurityRegistryManager@@SAJW4RegKeys@1@PEAPEAUHKEY__@@PEA_N@Z`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18013f4c4`

## callees

- `0x180019000`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180140df8`
- `0x180140ed8`
- `0x1801411d0`
- `0x180141220`
- `0x1801414cc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1801413c3`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1801413c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801412a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801412a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18014131f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18014131f`

## string_xrefs

- `0x180141372`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::CreateKey(__int64 a1)
{
  REGSAM samDesired; // ebx
  DWORD v2; // edi
  __int64 KeyPath; // rax
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-118h]
  DWORD dwDisposition; // [rsp+50h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-E0h] BYREF
  int v11; // [rsp+60h] [rbp-D8h] BYREF
  _QWORD v12[2]; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+78h] [rbp-C0h]
  _BYTE v14[96]; // [rsp+90h] [rbp-A8h] BYREF
  DWORD v15; // [rsp+F0h] [rbp-48h]
  REGSAM v16; // [rsp+F4h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  hKey = 0;
  dwDisposition = 0;
  v11 = 8;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    a1,
    v12,
    &v11);
  if ( *(_BYTE *)(v13 + 25) || *(_DWORD *)(v13 + 32) > 8u )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    return dwDisposition;
  }
  else
  {
    HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
      (HWSecurityRegistryManager::RegistryKeyEntry *)v14,
      (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v13 + 40));
    hKey = 0;
    samDesired = v16;
    v2 = v15;
    KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v14, v12);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, v2, samDesired, 0, &hKey, &dwDisposition);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    std::wstring::_Tidy_deallocate(v12);
    if ( (v6 & 0x80000000) == 0 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 0;
    }
    else if ( v6 == -2147024894 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return 2147942402LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
        (const char *)v6,
        dwOptions);
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v6;
    }
  }
}

```

## disassembly

```asm
0x180141220  mov     [rsp+arg_0], rbx
0x180141225  push    rdi
0x180141226  sub     rsp, 130h
0x18014122d  mov     rax, cs:__security_cookie
0x180141234  xor     rax, rsp
0x180141237  mov     [rsp+138h+var_18], rax
0x18014123f  mov     [rsp+138h+hKey], 0
0x180141248  mov     [rsp+138h+dwDisposition], 0
0x180141250  mov     [rsp+138h+var_D8], 8
0x180141258  lea     r8, [rsp+138h+var_D8]
0x18014125d  lea     rdx, [rsp+138h+var_D0]
0x180141262  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x180141267  mov     rdx, [rsp+138h+var_C0]
0x18014126c  cmp     byte ptr [rdx+19h], 0
0x180141270  jnz     loc_1801413BC
0x180141276  cmp     dword ptr [rdx+20h], 8
0x18014127a  ja      loc_1801413BC
0x180141280  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180141284  lea     rcx, [rsp+138h+var_A8]; this
0x18014128c  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180141291  nop
0x180141292  mov     rbx, [rsp+138h+hKey]
0x180141297  test    rbx, rbx
0x18014129a  jz      short loc_1801412B9
0x18014129c  lea     rcx, [rsp+138h+var_D8]; this
0x1801412a1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801412a6  mov     rcx, rbx; hKey
0x1801412a9  call    cs:__imp_RegCloseKey
0x1801412af  lea     rcx, [rsp+138h+var_D8]; this
0x1801412b4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801412b9  mov     [rsp+138h+hKey], 0
0x1801412c2  mov     ebx, [rsp+138h+var_44]
0x1801412c9  mov     edi, [rsp+138h+var_48]
0x1801412d0  lea     rdx, [rsp+138h+var_D0]
0x1801412d5  lea     rcx, [rsp+138h+var_A8]
0x1801412dd  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x1801412e2  mov     rcx, rax
0x1801412e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801412ea  lea     rcx, [rsp+138h+dwDisposition]
0x1801412ef  mov     [rsp+138h+lpdwDisposition], rcx; lpdwDisposition
0x1801412f4  lea     rcx, [rsp+138h+hKey]
0x1801412f9  mov     [rsp+138h+phkResult], rcx; phkResult
0x1801412fe  mov     [rsp+138h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180141307  mov     [rsp+138h+samDesired], ebx; samDesired
0x18014130b  mov     [rsp+138h+dwOptions], edi; int
0x18014130f  xor     r9d, r9d; lpClass
0x180141312  xor     r8d, r8d; Reserved
0x180141315  mov     rdx, rax; lpSubKey
0x180141318  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18014131f  call    cs:__imp_RegCreateKeyExW
0x180141325  mov     ebx, eax
0x180141327  test    eax, eax
0x180141329  jle     short loc_180141334
0x18014132b  movzx   ebx, ax
0x18014132e  or      ebx, 80070000h
0x180141334  lea     rcx, [rsp+138h+var_D0]
0x180141339  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014133e  test    ebx, ebx
0x180141340  jns     short loc_1801413A0
0x180141342  mov     edi, 80070002h
0x180141347  cmp     ebx, edi
0x180141349  jnz     short loc_180141367
0x18014134b  lea     rcx, [rsp+138h+var_A8]; this
0x180141353  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180141358  nop
0x180141359  lea     rcx, [rsp+138h+hKey]
0x18014135e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180141363  mov     eax, edi
0x180141365  jmp     short loc_1801413CE
0x180141367  mov     rcx, [rsp+138h]; this
0x18014136f  mov     r9d, ebx; char *
0x180141372  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180141379  mov     edx, 189h; void *
0x18014137e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180141383  nop
0x180141384  lea     rcx, [rsp+138h+var_A8]; this
0x18014138c  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180141391  nop
0x180141392  lea     rcx, [rsp+138h+hKey]
0x180141397  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014139c  mov     eax, ebx
0x18014139e  jmp     short loc_1801413CE
0x1801413a0  lea     rcx, [rsp+138h+var_A8]; this
0x1801413a8  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1801413ad  nop
0x1801413ae  lea     rcx, [rsp+138h+hKey]
0x1801413b3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801413b8  xor     eax, eax
0x1801413ba  jmp     short loc_1801413CE
0x1801413bc  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1801413c3  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1801413c9  nop
0x1801413ca  mov     eax, [rsp+138h+dwDisposition]
0x1801413ce  mov     rcx, [rsp+138h+var_18]
0x1801413d6  xor     rcx, rsp; StackCookie
0x1801413d9  call    __security_check_cookie
0x1801413de  mov     rbx, [rsp+138h+arg_0]
0x1801413e6  add     rsp, 130h
0x1801413ed  pop     rdi
0x1801413ee  retn
```
