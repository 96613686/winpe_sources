# NgcCtnrCommon::KeyHandleCache::OpenKey(unsigned __int64,ushort const *,ulong,ulong,unsigned __int64 *)

- ea: `0x18006f3cc`
- end: `0x18006f582`
- name: `?OpenKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBGKKPEA_K@Z`
- size: `438`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, NCRYPT_PROV_HANDLE hProvider@<rdx>, LPCWSTR pszKeyName@<r8>, unsigned int@<r9d>, unsigned int, unsigned __int64 *)`
- caller_count: `10`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019120`
- `0x18001f028`
- `0x180020cd0`
- `0x1800214e0`
- `0x180022720`
- `0x180022bd0`
- `0x180024550`
- `0x180025640`
- `0x180025f20`
- `0x18004c148`

## callees

- `0x180007670`
- `0x18000a168`
- `0x18000a188`
- `0x18000d62c`
- `0x1800108e4`
- `0x180011c9c`
- `0x180017d70`
- `0x18001dc68`
- `0x18002bfec`
- `0x18006ef30`
- `0x18006efb4`
- `0x18006f02c`
- `0x18006f1b4`
- `0x18006f3cc`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18006f489`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18006f489`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006f427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f518`
- `ncrypt!NCryptOpenKey` at `0x18006f4d5`
- `ncrypt!NCryptOpenKey` at `0x18006f4d5`

## string_xrefs

- `0x18006f4e8`: `onecore\ds\security\ngc\ctnrsvc\common\keyhandlecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcCtnrCommon::KeyHandleCache::OpenKey(
        PSRWLOCK SRWLock,
        NCRYPT_PROV_HANDLE hProvider,
        LPCWSTR pszKeyName,
        __int64 a4,
        unsigned int a5,
        unsigned __int64 *a6)
{
  __int64 v9; // rax
  PVOID v10; // rbx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  SECURITY_STATUS v15; // eax
  NCRYPT_KEY_HANDLE v17; // rbx
  _QWORD *v18; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-59h]
  PSRWLOCK v20; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-41h] BYREF
  void *v22; // [rsp+48h] [rbp-31h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-21h] BYREF
  NCRYPT_PROV_HANDLE v24; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v25[32]; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v9 = std::wstring::wstring(v21, pszKeyName);
  v24 = hProvider;
  std::wstring::wstring(v25, v9);
  std::wstring::_Tidy_deallocate(v21);
  AcquireSRWLockShared(SRWLock);
  v20 = SRWLock;
  std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(
    &SRWLock[1],
    v21,
    &v24);
  v10 = v22;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::pair<unsigned __int64,std::wstring>>(
                          v11,
                          v22,
                          &v24)
    && v10 != SRWLock[1].Ptr )
  {
    std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(
      &SRWLock[1],
      v21,
      &v24);
    v12 = v22;
    if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::pair<unsigned __int64,std::wstring>>(
                             v13,
                             v22,
                             &v24) )
    {
      std::_Xout_of_range("invalid map<K, T> key");
      __debugbreak();
    }
    *a6 = v12[9];
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
    v14 = 0;
    goto LABEL_8;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v15 = NCryptOpenKey(hProvider, &phKey, pszKeyName, 0, 0);
  v14 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\keyhandlecache.cpp",
      (const char *)(unsigned int)v15,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
LABEL_8:
    std::wstring::_Tidy_deallocate(v25);
    return v14;
  }
  v17 = phKey;
  AcquireSRWLockExclusive(SRWLock);
  v20 = SRWLock;
  v18 = (_QWORD *)std::map<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::_Try_emplace<std::pair<unsigned __int64,std::wstring> const &,>(
                    &SRWLock[1],
                    v21,
                    &v24);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(
    *v18 + 72LL,
    &phKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  *a6 = v17;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  std::wstring::_Tidy_deallocate(v25);
  return 0;
}

```

## disassembly

```asm
0x18006f3cc  push    rbp
0x18006f3ce  push    rbx
0x18006f3cf  push    rsi
0x18006f3d0  push    rdi
0x18006f3d1  push    r12
0x18006f3d3  push    r14
0x18006f3d5  push    r15
0x18006f3d7  lea     rbp, [rsp-17h]
0x18006f3dc  sub     rsp, 90h
0x18006f3e3  mov     rax, cs:__security_cookie
0x18006f3ea  xor     rax, rsp
0x18006f3ed  mov     [rbp+47h+var_38], rax
0x18006f3f1  mov     r12, r8
0x18006f3f4  mov     r15, rdx
0x18006f3f7  mov     rsi, rcx
0x18006f3fa  mov     r14, [rbp+47h+arg_28]
0x18006f3fe  mov     rdx, r8
0x18006f401  lea     rcx, [rbp+47h+var_88]
0x18006f405  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f40a  mov     [rbp+47h+var_60], r15
0x18006f40e  mov     rdx, rax
0x18006f411  lea     rcx, [rbp+47h+var_58]
0x18006f415  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18006f41a  nop
0x18006f41b  lea     rcx, [rbp+47h+var_88]
0x18006f41f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f424  mov     rcx, rsi; SRWLock
0x18006f427  call    cs:__imp_AcquireSRWLockShared
0x18006f42d  mov     [rbp+47h+var_90], rsi
0x18006f431  lea     rdi, [rsi+8]
0x18006f435  lea     r8, [rbp+47h+var_60]
0x18006f439  lea     rdx, [rbp+47h+var_88]
0x18006f43d  mov     rcx, rdi
0x18006f440  call    ??$_Find_lower_bound@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(std::pair<unsigned __int64,std::wstring> const &)
0x18006f445  lea     r8, [rbp+47h+var_60]
0x18006f449  mov     rbx, [rbp+47h+var_78]
0x18006f44d  mov     rdx, rbx
0x18006f450  call    ??$_Lower_bound_duplicate@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::pair<unsigned __int64,std::wstring>>(std::_Tree_node<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>,void *> * const,std::pair<unsigned __int64,std::wstring> const &)
0x18006f455  test    al, al
0x18006f457  jz      short loc_18006F4A4
0x18006f459  cmp     rbx, [rdi]
0x18006f45c  jz      short loc_18006F4A4
0x18006f45e  lea     r8, [rbp+47h+var_60]
0x18006f462  lea     rdx, [rbp+47h+var_88]
0x18006f466  mov     rcx, rdi
0x18006f469  call    ??$_Find_lower_bound@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Find_lower_bound<std::pair<unsigned __int64,std::wstring>>(std::pair<unsigned __int64,std::wstring> const &)
0x18006f46e  lea     r8, [rbp+47h+var_60]
0x18006f472  mov     rbx, [rbp+47h+var_78]
0x18006f476  mov     rdx, rbx
0x18006f479  call    ??$_Lower_bound_duplicate@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::_Lower_bound_duplicate<std::pair<unsigned __int64,std::wstring>>(std::_Tree_node<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>,void *> * const,std::pair<unsigned __int64,std::wstring> const &)
0x18006f47e  test    al, al
0x18006f480  jnz     short loc_18006F490
0x18006f482  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18006f489  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18006f48f  int     3; Trap to Debugger
0x18006f490  mov     rax, [rbx+48h]
0x18006f494  mov     [r14], rax
0x18006f497  lea     rcx, [rbp+47h+var_90]
0x18006f49b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f4a0  xor     ebx, ebx
0x18006f4a2  jmp     short loc_18006F504
0x18006f4a4  lea     rcx, [rbp+47h+var_90]
0x18006f4a8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f4ad  mov     [rbp+47h+phKey], 0
0x18006f4b5  xor     edx, edx
0x18006f4b7  lea     rcx, [rbp+47h+phKey]
0x18006f4bb  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18006f4c0  mov     [rsp+0C0h+dwFlags], 0; int
0x18006f4c8  xor     r9d, r9d; dwLegacyKeySpec
0x18006f4cb  mov     r8, r12; pszKeyName
0x18006f4ce  lea     rdx, [rbp+47h+phKey]; phKey
0x18006f4d2  mov     rcx, r15; hProvider
0x18006f4d5  call    cs:__imp_NCryptOpenKey
0x18006f4db  mov     ebx, eax
0x18006f4dd  test    eax, eax
0x18006f4df  jns     short loc_18006F511
0x18006f4e1  mov     rcx, [rbp+4Fh]; this
0x18006f4e5  mov     r9d, eax; char *
0x18006f4e8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006f4ef  mov     edx, 4Ah ; 'J'; void *
0x18006f4f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f4f9  nop
0x18006f4fa  lea     rcx, [rbp+47h+phKey]
0x18006f4fe  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18006f503  nop
0x18006f504  lea     rcx, [rbp+47h+var_58]
0x18006f508  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f50d  mov     eax, ebx
0x18006f50f  jmp     short loc_18006F564
0x18006f511  mov     rbx, [rbp+47h+phKey]
0x18006f515  mov     rcx, rsi; SRWLock
0x18006f518  call    cs:__imp_AcquireSRWLockExclusive
0x18006f51e  mov     [rbp+47h+var_90], rsi
0x18006f522  lea     r8, [rbp+47h+var_60]
0x18006f526  lea     rdx, [rbp+47h+var_88]
0x18006f52a  mov     rcx, rdi
0x18006f52d  call    ??$_Try_emplace@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$$V@?$map@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::map<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::_Try_emplace<std::pair<unsigned __int64,std::wstring> const &,>(std::pair<unsigned __int64,std::wstring> const &)
0x18006f532  mov     rcx, [rax]
0x18006f535  add     rcx, 48h ; 'H'
0x18006f539  lea     rdx, [rbp+47h+phKey]
0x18006f53d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>> &&)
0x18006f542  nop
0x18006f543  lea     rcx, [rbp+47h+var_90]
0x18006f547  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f54c  mov     [r14], rbx
0x18006f54f  lea     rcx, [rbp+47h+phKey]
0x18006f553  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18006f558  nop
0x18006f559  lea     rcx, [rbp+47h+var_58]
0x18006f55d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f562  xor     eax, eax
0x18006f564  mov     rcx, [rbp+47h+var_38]
0x18006f568  xor     rcx, rsp; StackCookie
0x18006f56b  call    __security_check_cookie
0x18006f570  add     rsp, 90h
0x18006f577  pop     r15
0x18006f579  pop     r14
0x18006f57b  pop     r12
0x18006f57d  pop     rdi
0x18006f57e  pop     rsi
0x18006f57f  pop     rbx
0x18006f580  pop     rbp
0x18006f581  retn
```
