# HWSecurityRegistryManager::CreateKey(HWSecurityRegistryManager::RegKeys,HKEY__ * *,bool *)

- ea: `0x180042fd4`
- end: `0x180043192`
- name: `?CreateKey@HWSecurityRegistryManager@@SAJW4RegKeys@1@PEAPEAUHKEY__@@PEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014d38`
- `0x1800451ec`

## callees

- `0x1800078b0`
- `0x18000e48c`
- `0x18001a42c`
- `0x180023634`
- `0x18002386c`
- `0x180024780`
- `0x180042a14`
- `0x180042c20`
- `0x180042f40`
- `0x180042fd4`
- `0x1800435cc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043169`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180043169`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800430af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800430af`

## string_xrefs

- `0x180043102`: `onecore\base\ngscb\tpmhli\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall HWSecurityRegistryManager::CreateKey(__int64 a1, HKEY *a2)
{
  unsigned int v3; // r10d
  HKEY *phkResult; // rbx
  REGSAM samDesired; // esi
  DWORD v6; // r14d
  __int64 KeyPath; // rax
  const WCHAR *v8; // rax
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  HKEY v12; // rax
  DWORD dwOptions; // [rsp+20h] [rbp-138h]
  DWORD dwDisposition; // [rsp+50h] [rbp-108h] BYREF
  HKEY v15; // [rsp+58h] [rbp-100h] BYREF
  int v16; // [rsp+60h] [rbp-F8h] BYREF
  _QWORD v17[2]; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v18; // [rsp+78h] [rbp-E0h]
  _BYTE v19[96]; // [rsp+90h] [rbp-C8h] BYREF
  DWORD v20; // [rsp+F0h] [rbp-68h]
  REGSAM v21; // [rsp+F4h] [rbp-64h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v15 = 0;
  dwDisposition = 0;
  v16 = a1;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<enum HWSecurityRegistryManager::RegKeys>(
    a1,
    v17,
    &v16);
  if ( *(_BYTE *)(v18 + 25) || v3 < *(_DWORD *)(v18 + 32) )
  {
    std::_Xout_of_range("invalid map<K, T> key");
    return dwDisposition;
  }
  else
  {
    HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
      (HWSecurityRegistryManager::RegistryKeyEntry *)v19,
      (const struct HWSecurityRegistryManager::RegistryKeyEntry *)(v18 + 40));
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v15);
    samDesired = v21;
    v6 = v20;
    KeyPath = HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(v19, v17);
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(KeyPath);
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, v6, samDesired, 0, phkResult, &dwDisposition);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    std::wstring::_Tidy_deallocate(v17);
    if ( (v10 & 0x80000000) == 0 )
    {
      if ( a2 )
      {
        v12 = v15;
        v15 = 0;
        *a2 = v12;
      }
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v19);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
      return 0;
    }
    else if ( v10 == -2147024894 )
    {
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v19);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
      return 2147942402LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\registry.cpp",
        (const char *)v10,
        dwOptions);
      HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v19);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
      return v10;
    }
  }
}

```

## disassembly

```asm
0x180042fd4  push    rbx
0x180042fd6  push    rsi
0x180042fd7  push    rdi
0x180042fd8  push    r14
0x180042fda  sub     rsp, 138h
0x180042fe1  mov     rax, cs:__security_cookie
0x180042fe8  xor     rax, rsp
0x180042feb  mov     [rsp+158h+var_38], rax
0x180042ff3  mov     rdi, rdx
0x180042ff6  mov     r10d, ecx
0x180042ff9  mov     [rsp+158h+var_100], 0
0x180043002  mov     [rsp+158h+dwDisposition], 0
0x18004300a  mov     [rsp+158h+var_F8], ecx
0x18004300e  lea     r8, [rsp+158h+var_F8]
0x180043013  lea     rdx, [rsp+158h+var_F0]
0x180043018  call    ??$_Find_lower_bound@W4RegKeys@HWSecurityRegistryManager@@@?$_Tree@V?$_Tmap_traits@W4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@U?$less@W4RegKeys@HWSecurityRegistryManager@@@std@@V?$allocator@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@PEAX@std@@@1@AEBW4RegKeys@HWSecurityRegistryManager@@@Z; std::_Tree<std::_Tmap_traits<HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Find_lower_bound<HWSecurityRegistryManager::RegKeys>(HWSecurityRegistryManager::RegKeys const &)
0x18004301d  mov     rdx, [rsp+158h+var_E0]
0x180043022  cmp     byte ptr [rdx+19h], 0
0x180043026  jnz     loc_180043162
0x18004302c  cmp     r10d, [rdx+20h]
0x180043030  jb      loc_180043162
0x180043036  add     rdx, 28h ; '('; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x18004303a  lea     rcx, [rsp+158h+var_C8]; this
0x180043042  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180043047  nop
0x180043048  lea     rcx, [rsp+158h+var_100]
0x18004304d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180043052  mov     rbx, rax
0x180043055  mov     esi, [rsp+158h+var_64]
0x18004305c  mov     r14d, [rsp+158h+var_68]
0x180043064  lea     rdx, [rsp+158h+var_F0]
0x180043069  lea     rcx, [rsp+158h+var_C8]
0x180043071  call    ?GetKeyPath@RegistryKeyEntry@HWSecurityRegistryManager@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HWSecurityRegistryManager::RegistryKeyEntry::GetKeyPath(void)
0x180043076  mov     rcx, rax
0x180043079  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004307e  lea     rcx, [rsp+158h+dwDisposition]
0x180043083  mov     [rsp+158h+lpdwDisposition], rcx; lpdwDisposition
0x180043088  mov     [rsp+158h+phkResult], rbx; phkResult
0x18004308d  mov     [rsp+158h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180043096  mov     [rsp+158h+samDesired], esi; samDesired
0x18004309a  mov     [rsp+158h+dwOptions], r14d; int
0x18004309f  xor     r9d, r9d; lpClass
0x1800430a2  xor     r8d, r8d; Reserved
0x1800430a5  mov     rdx, rax; lpSubKey
0x1800430a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800430af  call    cs:__imp_RegCreateKeyExW
0x1800430b5  mov     ebx, eax
0x1800430b7  test    eax, eax
0x1800430b9  jle     short loc_1800430C4
0x1800430bb  movzx   ebx, ax
0x1800430be  or      ebx, 80070000h
0x1800430c4  lea     rcx, [rsp+158h+var_F0]
0x1800430c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800430ce  test    ebx, ebx
0x1800430d0  jns     short loc_180043130
0x1800430d2  mov     edi, 80070002h
0x1800430d7  cmp     ebx, edi
0x1800430d9  jnz     short loc_1800430F7
0x1800430db  lea     rcx, [rsp+158h+var_C8]; this
0x1800430e3  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x1800430e8  nop
0x1800430e9  lea     rcx, [rsp+158h+var_100]
0x1800430ee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800430f3  mov     eax, edi
0x1800430f5  jmp     short loc_180043174
0x1800430f7  mov     rcx, [rsp+158h]; this
0x1800430ff  mov     r9d, ebx; char *
0x180043102  lea     r8, aOnecoreBaseNgs_0; "onecore\\base\\ngscb\\tpmhli\\lib\\regi"...
0x180043109  mov     edx, 189h; void *
0x18004310e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043113  nop
0x180043114  lea     rcx, [rsp+158h+var_C8]; this
0x18004311c  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180043121  nop
0x180043122  lea     rcx, [rsp+158h+var_100]
0x180043127  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004312c  mov     eax, ebx
0x18004312e  jmp     short loc_180043174
0x180043130  test    rdi, rdi
0x180043133  jz      short loc_180043146
0x180043135  mov     rax, [rsp+158h+var_100]
0x18004313a  mov     [rsp+158h+var_100], 0
0x180043143  mov     [rdi], rax
0x180043146  lea     rcx, [rsp+158h+var_C8]; this
0x18004314e  call    ??1RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@XZ; HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry(void)
0x180043153  nop
0x180043154  lea     rcx, [rsp+158h+var_100]
0x180043159  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004315e  xor     eax, eax
0x180043160  jmp     short loc_180043174
0x180043162  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180043169  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18004316f  nop
0x180043170  mov     eax, [rsp+158h+dwDisposition]
0x180043174  mov     rcx, [rsp+158h+var_38]
0x18004317c  xor     rcx, rsp; StackCookie
0x18004317f  call    __security_check_cookie
0x180043184  add     rsp, 138h
0x18004318b  pop     r14
0x18004318d  pop     rdi
0x18004318e  pop     rsi
0x18004318f  pop     rbx
0x180043190  retn
```
