# HWSecurityRegistryManager::CreateKey(HWSecurityRegistryManager::RegKeys,HKEY__ * *,bool *)

- ea: `0x18009aad0`
- end: `0x18009ac88`
- name: `?CreateKey@HWSecurityRegistryManager@@SAJW4RegKeys@1@PEAPEAUHKEY__@@PEA_N@Z`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098c64`

## callees

- `0x180007270`
- `0x180057c6c`
- `0x18005bb6c`
- `0x18005bbf0`
- `0x18005d010`
- `0x18005d6e0`
- `0x18009a548`
- `0x18009a750`
- `0x18009aa80`
- `0x18009aad0`
- `0x18009ad68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009abab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009abab`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009ac55`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18009ac55`

## string_xrefs

- `0x18009ac04`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

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
  HKEY phkResult; // [rsp+58h] [rbp-E0h] BYREF
  int v11; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE v12[16]; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+78h] [rbp-C0h]
  _BYTE v14[96]; // [rsp+90h] [rbp-A8h] BYREF
  DWORD v15; // [rsp+F0h] [rbp-48h]
  REGSAM v16; // [rsp+F4h] [rbp-44h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  phkResult = 0;
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
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    samDesired = v16;
    v2 = v15;
    KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v14, v12);
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, v2, samDesired, 0, &phkResult, &dwDisposition);
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    std::wstring::_Tidy_deallocate(v12);
    if ( (v6 & 0x80000000) == 0 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return 0;
    }
    else if ( v6 == -2147024894 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v14);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
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
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return v6;
    }
  }
}

```

## disassembly

```asm
0x18009aad0  mov     [rsp+arg_0], rbx
0x18009aad5  push    rdi
0x18009aad6  sub     rsp, 130h
0x18009aadd  mov     rax, cs:__security_cookie
0x18009aae4  xor     rax, rsp
0x18009aae7  mov     [rsp+138h+var_18], rax
0x18009aaef  mov     [rsp+138h+var_E0], 0
0x18009aaf8  mov     [rsp+138h+dwDisposition], 0
0x18009ab00  mov     [rsp+138h+var_D8], 8
0x18009ab08  lea     r8, [rsp+138h+var_D8]
0x18009ab0d  lea     rdx, [rsp+138h+var_D0]
0x18009ab12  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x18009ab17  mov     rdx, [rsp+138h+var_C0]
0x18009ab1c  cmp     byte ptr [rdx+19h], 0
0x18009ab20  jnz     loc_18009AC4E
0x18009ab26  cmp     dword ptr [rdx+20h], 8
0x18009ab2a  ja      loc_18009AC4E
0x18009ab30  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x18009ab34  lea     rcx, [rsp+138h+var_A8]; this
0x18009ab3c  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18009ab41  nop
0x18009ab42  xor     edx, edx
0x18009ab44  lea     rcx, [rsp+138h+var_E0]
0x18009ab49  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009ab4e  mov     ebx, [rsp+138h+var_44]
0x18009ab55  mov     edi, [rsp+138h+var_48]
0x18009ab5c  lea     rdx, [rsp+138h+var_D0]
0x18009ab61  lea     rcx, [rsp+138h+var_A8]
0x18009ab69  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x18009ab6e  mov     rcx, rax
0x18009ab71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009ab76  lea     rcx, [rsp+138h+dwDisposition]
0x18009ab7b  mov     [rsp+138h+lpdwDisposition], rcx; lpdwDisposition
0x18009ab80  lea     rcx, [rsp+138h+var_E0]
0x18009ab85  mov     [rsp+138h+phkResult], rcx; phkResult
0x18009ab8a  mov     [rsp+138h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18009ab93  mov     [rsp+138h+samDesired], ebx; samDesired
0x18009ab97  mov     [rsp+138h+dwOptions], edi; int
0x18009ab9b  xor     r9d, r9d; lpClass
0x18009ab9e  xor     r8d, r8d; Reserved
0x18009aba1  mov     rdx, rax; lpSubKey
0x18009aba4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009abab  call    cs:__imp_RegCreateKeyExW
0x18009abb2  nop     dword ptr [rax+rax+00h]
0x18009abb7  mov     ebx, eax
0x18009abb9  test    eax, eax
0x18009abbb  jle     short loc_18009ABC6
0x18009abbd  movzx   ebx, ax
0x18009abc0  or      ebx, 80070000h
0x18009abc6  lea     rcx, [rsp+138h+var_D0]
0x18009abcb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009abd0  test    ebx, ebx
0x18009abd2  jns     short loc_18009AC32
0x18009abd4  mov     edi, 80070002h
0x18009abd9  cmp     ebx, edi
0x18009abdb  jnz     short loc_18009ABF9
0x18009abdd  lea     rcx, [rsp+138h+var_A8]; this
0x18009abe5  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009abea  nop
0x18009abeb  lea     rcx, [rsp+138h+var_E0]
0x18009abf0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009abf5  mov     eax, edi
0x18009abf7  jmp     short loc_18009AC66
0x18009abf9  mov     rcx, [rsp+138h]; this
0x18009ac01  mov     r9d, ebx; char *
0x18009ac04  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x18009ac0b  mov     edx, 189h; void *
0x18009ac10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ac15  nop
0x18009ac16  lea     rcx, [rsp+138h+var_A8]; this
0x18009ac1e  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009ac23  nop
0x18009ac24  lea     rcx, [rsp+138h+var_E0]
0x18009ac29  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ac2e  mov     eax, ebx
0x18009ac30  jmp     short loc_18009AC66
0x18009ac32  lea     rcx, [rsp+138h+var_A8]; this
0x18009ac3a  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x18009ac3f  nop
0x18009ac40  lea     rcx, [rsp+138h+var_E0]
0x18009ac45  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ac4a  xor     eax, eax
0x18009ac4c  jmp     short loc_18009AC66
0x18009ac4e  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18009ac55  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18009ac5c  nop     dword ptr [rax+rax+00h]
0x18009ac61  nop
0x18009ac62  mov     eax, [rsp+138h+dwDisposition]
0x18009ac66  mov     rcx, [rsp+138h+var_18]
0x18009ac6e  xor     rcx, rsp; StackCookie
0x18009ac71  call    __security_check_cookie
0x18009ac76  mov     rbx, [rsp+138h+arg_0]
0x18009ac7e  add     rsp, 130h
0x18009ac85  pop     rdi
0x18009ac86  retn
```
