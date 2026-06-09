# CloudCacheInvalidatorServiceImpl::ProcessInactiveInvalidator(void)

- ea: `0x180014384`
- end: `0x180014769`
- name: `?ProcessInactiveInvalidator@CloudCacheInvalidatorServiceImpl@@AEAAXXZ`
- size: `997`
- prototype: `void __fastcall(CloudCacheInvalidatorServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013acc`

## callees

- `0x1800135a4`
- `0x1800135e0`
- `0x180014384`
- `0x180014770`
- `0x18001486c`
- `0x18001489c`
- `0x180014a00`
- `0x180014aac`
- `0x180016cf4`
- `0x1800238d0`
- `0x180024020`
- `0x180024fd0`
- `0x18002570c`
- `0x180026688`
- `0x18002e010`
- `0x18003e904`
- `0x18007e800`
- `0x1800d1d50`
- `0x1801201a0`
- `0x1801a581c`
- `0x1801a58f0`
- `0x1801a63b0`
- `0x1801a69bc`
- `0x1801a6bd4`
- `0x1801a6d48`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001454d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001454d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800145d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800145d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001445b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001445b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014489`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014489`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x180014674`
- `api-ms-win-core-registry-private-l1-1-0!RegRenameKey` at `0x180014674`

## string_xrefs

- `0x180014517`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinvalidatorsso.cpp`
- `0x180014689`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinvalidatorsso.cpp`
- `0x18001471f`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinvalidatorsso.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CloudCacheInvalidatorServiceImpl::ProcessInactiveInvalidator(CloudCacheInvalidatorServiceImpl *this)
{
  __int64 **v2; // rax
  __int64 ***v3; // rsi
  LPCWSTR v4; // r13
  __int64 v5; // rax
  HKEY *v6; // r9
  CloudStoreUtilities *v7; // rcx
  int RegistryRootKey; // eax
  void *v9; // rdx
  __int64 **v10; // rdi
  __int64 **i; // rbx
  const char *v12; // r9
  __int64 v13; // rax
  const WCHAR *p_lpString2; // r8
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rax
  const WCHAR *p_lpNewKeyName; // r8
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  const char *v23; // r9
  __int64 **v24; // rdi
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-118h]
  int *bIgnoreCasea; // [rsp+20h] [rbp-118h]
  _BYTE v27[8]; // [rsp+30h] [rbp-108h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-100h] BYREF
  int v29[2]; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-F0h] BYREF
  std::_Ref_count_base *v31; // [rsp+50h] [rbp-E8h]
  HANDLE hObject[3]; // [rsp+58h] [rbp-E0h] BYREF
  int v33; // [rsp+70h] [rbp-C8h] BYREF
  __int64 **v34; // [rsp+78h] [rbp-C0h]
  __int64 v35; // [rsp+80h] [rbp-B8h]
  __int64 v36; // [rsp+88h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+90h] [rbp-A8h]
  __int64 v38; // [rsp+A0h] [rbp-98h]
  __int64 v39; // [rsp+A8h] [rbp-90h]
  LPCWCH lpString2; // [rsp+B0h] [rbp-88h] BYREF
  struct _SECURITY_ATTRIBUTES v41; // [rsp+B8h] [rbp-80h] BYREF
  LPCWSTR lpNewKeyName; // [rsp+D0h] [rbp-68h] BYREF
  std::_Ref_count_base *v43; // [rsp+D8h] [rbp-60h]
  unsigned __int64 v44; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v33 = 0;
  v34 = 0;
  v35 = 0;
  try
  {
    v2 = (__int64 **)std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<CloudCacheInvalidatorHolder>>,void *>>::allocate();
    *v2 = (__int64 *)v2;
    v2[1] = (__int64 *)v2;
    v34 = v2;
    v36 = 0;
    v37 = 0;
    v38 = 7;
    v39 = 8;
    v33 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>>>>>::_Assign_grow(
      &v36,
      16,
      v2);
    v27[0] = 0;
    *(_QWORD *)v29 = this;
    bIgnoreCasea = v29;
    EnsureMemberWithReturnType<std::shared_ptr<std::unordered_map<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo> const>,std::shared_ptr<std::unordered_map<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo> const>,_lambda_81df0d98de88f0676f97e53c360cde0e_>(
      &lpNewKeyName,
      (char *)this + 48,
      (char *)this + 120,
      v27);
    AcquireSRWLockExclusive((PSRWLOCK)this + 6);
    hObject[1] = (char *)this + 48;
    v3 = (__int64 ***)*((_QWORD *)this + 18);
    v24 = *v3;
    v4 = lpNewKeyName;
    while ( v24 != (__int64 **)v3 )
    {
      std::_Hash<std::_Umap_traits<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo>>,0>>::find(
        v4,
        v29,
        v24 + 2);
      if ( *(_QWORD *)v29 == *((_QWORD *)v4 + 1) )
      {
        CloudCacheInvalidatorHolder::Stop((CloudCacheInvalidatorHolder *)v24[6]);
        std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>(
          v30,
          v24[6] + 2,
          v21,
          v22);
        if ( !*(_BYTE *)(std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>::emplace<std::wstring const &,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const &>(
                           &v33,
                           &lpString2,
                           v24 + 2,
                           v30,
                           bIgnoreCasea)
                       + 8) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x122,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinvalidatorsso.cpp",
            v23);
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
      }
      v24 = (__int64 **)*v24;
    }
    if ( this != (CloudCacheInvalidatorServiceImpl *)-48LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
    EffectiveUserContext::Impersonate((void ***)this + 2, hObject);
    hKey = 0;
    lpString2 = (LPCWCH)&hKey;
    *(_QWORD *)&v41.nLength = 0;
    LOBYTE(v41.lpSecurityDescriptor) = 1;
    v5 = CloudCacheInvalidatorServiceImpl::EnsurePersistenceContext(this);
    v7 = (CloudStoreUtilities *)(*(_QWORD *)v5 + 40LL);
    if ( *(_QWORD *)(*(_QWORD *)v5 + 64LL) > 7u )
      v7 = *(CloudStoreUtilities **)v7;
    RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(v7, L"Store", &v41, v6);
    if ( RegistryRootKey < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x12A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinvalidatorsso.cpp",
        (const char *)(unsigned int)RegistryRootKey,
        (int)bIgnoreCasea);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&lpString2);
    v10 = v34;
    for ( i = (__int64 **)*v34; i != v10; i = (__int64 **)*i )
    {
      std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<CloudCacheInvalidatorHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CloudCacheInvalidatorHolder>>>,0>>::_Erase<std::wstring>(
        (_QWORD *)this + 17,
        i + 2);
      v13 = (*(__int64 (__fastcall **)(__int64 *))(*i[6] + 16))(i[6]);
      std::wstring::wstring(&lpString2, v13);
      p_lpString2 = (const WCHAR *)&lpString2;
      if ( *(_QWORD *)&v41.bInheritHandle > 7u )
        p_lpString2 = lpString2;
      if ( CompareStringOrdinal(L"DefaultAccount", -1, p_lpString2, -1, 1) == 2 )
      {
        v17 = std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>(
                v30,
                i + 6,
                v15,
                v16);
        CloudCacheInvalidatorServiceImpl::InvalidateAccountCacheData(this, v17);
      }
      else
      {
        std::wstring::wstring(&lpNewKeyName);
        std::wstring::append(&lpNewKeyName, L".Stale");
        p_lpNewKeyName = (const WCHAR *)&lpNewKeyName;
        if ( v44 > 7 )
          p_lpNewKeyName = lpNewKeyName;
        v19 = (const WCHAR *)&lpString2;
        if ( *(_QWORD *)&v41.bInheritHandle > 7u )
          v19 = lpString2;
        v20 = RegRenameKey(hKey, v19, p_lpNewKeyName);
        if ( v20 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinvalidatorsso.cpp",
            (const char *)v20,
            bIgnoreCase);
        std::wstring::~wstring(&lpNewKeyName);
      }
      std::wstring::~wstring(&lpString2);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( hObject[0] != (HANDLE)-1LL )
      wil::details::RevertImpersonateToken(hObject[0], v9);
    std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>(&v33);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinvalidatorsso.cpp",
      v12);
  }
}

```

## disassembly

```asm
0x180014384  push    rbx
0x180014386  push    rsi
0x180014387  push    rdi
0x180014388  push    r13
0x18001438a  push    r14
0x18001438c  push    r15
0x18001438e  sub     rsp, 108h
0x180014395  mov     rax, cs:__security_cookie
0x18001439c  xor     rax, rsp
0x18001439f  mov     [rsp+138h+var_48], rax
0x1800143a7  mov     r14, rcx
0x1800143aa  mov     [rsp+138h+var_C8], 0
0x1800143b2  mov     [rsp+138h+var_C0], 0
0x1800143bb  mov     [rsp+138h+var_B8], 0
0x1800143c7  call    ?allocate@?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCloudCacheInvalidatorHolder@@@2@@std@@PEAX@std@@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCloudCacheInvalidatorHolder@@@2@@std@@PEAX@2@_K@Z; std::allocator<std::_List_node<std::pair<std::wstring const,std::shared_ptr<CloudCacheInvalidatorHolder>>,void *>>::allocate(unsigned __int64)
0x1800143cc  mov     [rax], rax
0x1800143cf  mov     [rax+8], rax
0x1800143d3  mov     [rsp+138h+var_C0], rax
0x1800143d8  mov     [rsp+138h+var_B0], 0
0x1800143e4  xorps   xmm0, xmm0
0x1800143e7  movdqa  [rsp+138h+var_A8], xmm0
0x1800143f0  mov     [rsp+138h+var_98], 7
0x1800143fc  mov     [rsp+138h+var_90], 8
0x180014408  mov     [rsp+138h+var_C8], 3F800000h
0x180014410  mov     r8, rax
0x180014413  mov     edx, 10h
0x180014418  lea     rcx, [rsp+138h+var_B0]
0x180014420  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>>>)
0x180014425  nop
0x180014426  mov     [rsp+138h+var_108], 0
0x18001442b  mov     qword ptr [rsp+138h+var_F8], r14
0x180014430  lea     rbx, [r14+30h]
0x180014434  lea     r8, [r14+78h]
0x180014438  lea     rax, [rsp+138h+var_F8]
0x18001443d  mov     qword ptr [rsp+138h+bIgnoreCase], rax; int
0x180014442  lea     r9, [rsp+138h+var_108]
0x180014447  mov     rdx, rbx
0x18001444a  lea     rcx, [rsp+138h+lpNewKeyName]
0x180014452  call    ??$EnsureMemberWithReturnType@V?$shared_ptr@$$CBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@@std@@@2@@std@@@std@@V12@V_lambda_81df0d98de88f0676f97e53c360cde0e_@@@@YA?AV?$shared_ptr@$$CBV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@@std@@@2@@std@@@std@@AEAVsrwlock@wil@@AEAV01@PEA_NAEBV_lambda_81df0d98de88f0676f97e53c360cde0e_@@@Z; EnsureMemberWithReturnType<std::shared_ptr<std::unordered_map<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo> const>,std::shared_ptr<std::unordered_map<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo> const>,_lambda_81df0d98de88f0676f97e53c360cde0e_>(wil::srwlock &,std::shared_ptr<std::unordered_map<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo> const> &,bool *,_lambda_81df0d98de88f0676f97e53c360cde0e_ const &)
0x180014457  nop
0x180014458  mov     rcx, rbx; SRWLock
0x18001445b  call    cs:__imp_AcquireSRWLockExclusive
0x180014461  mov     [rsp+138h+var_D8], rbx
0x180014466  mov     rsi, [r14+90h]
0x18001446d  mov     rdi, [rsi]
0x180014470  mov     r13, [rsp+138h+lpNewKeyName]
0x180014478  cmp     rdi, rsi
0x18001447b  jnz     loc_1800146BE
0x180014481  test    rbx, rbx
0x180014484  jz      short loc_180014490
0x180014486  mov     rcx, rbx; SRWLock
0x180014489  call    cs:__imp_ReleaseSRWLockExclusive
0x18001448f  nop
0x180014490  mov     rcx, [rsp+138h+var_60]; this
0x180014498  test    rcx, rcx
0x18001449b  jz      short loc_1800144A2
0x18001449d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800144a2  lea     rcx, [r14+10h]
0x1800144a6  lea     rdx, [rsp+138h+hObject]
0x1800144ab  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x1800144b0  nop
0x1800144b1  mov     [rsp+138h+hKey], 0
0x1800144ba  lea     rax, [rsp+138h+hKey]
0x1800144bf  mov     [rsp+138h+lpString2], rax
0x1800144c7  mov     qword ptr [rsp+138h+var_80], 0
0x1800144d3  mov     [rsp+138h+var_78], 1
0x1800144db  mov     rcx, r14
0x1800144de  call    ?EnsurePersistenceContext@CloudCacheInvalidatorServiceImpl@@AEAAAEBV?$shared_ptr@VWindowsPersistenceContext@@@std@@XZ; CloudCacheInvalidatorServiceImpl::EnsurePersistenceContext(void)
0x1800144e3  mov     rcx, [rax]
0x1800144e6  add     rcx, 28h ; '('
0x1800144ea  cmp     qword ptr [rcx+18h], 7
0x1800144ef  jbe     short loc_1800144F4
0x1800144f1  mov     rcx, [rcx]; this
0x1800144f4  lea     r8, [rsp+138h+var_80]; unsigned __int16 *
0x1800144fc  lea     rdx, aStore_1; "Store"
0x180014503  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x180014508  mov     rcx, [rsp+138h]; this
0x180014510  test    eax, eax
0x180014512  jns     short loc_180014529
0x180014514  mov     r9d, eax; char *
0x180014517  lea     r8, aOnecoreuapShel_69; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18001451e  mov     edx, 12Ah; void *
0x180014523  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014529  lea     rcx, [rsp+138h+lpString2]
0x180014531  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180014536  mov     rdi, [rsp+138h+var_C0]
0x18001453b  mov     rbx, [rdi]
0x18001453e  cmp     rbx, rdi
0x180014541  jnz     short loc_180014575
0x180014543  mov     rcx, [rsp+138h+hKey]; hKey
0x180014548  test    rcx, rcx
0x18001454b  jz      short loc_180014554
0x18001454d  call    cs:__imp_RegCloseKey
0x180014553  nop
0x180014554  mov     rcx, [rsp+138h+hObject]; hObject
0x180014559  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001455d  jz      short loc_180014565
0x18001455f  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180014564  nop
0x180014565  lea     rcx, [rsp+138h+var_C8]
0x18001456a  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>::~_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>(void)
0x18001456f  nop
0x180014570  jmp     loc_180014748
0x180014575  lea     rcx, [r14+88h]
0x18001457c  lea     rdx, [rbx+10h]
0x180014580  call    ??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCloudCacheInvalidatorHolder@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCloudCacheInvalidatorHolder@@@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<CloudCacheInvalidatorHolder>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CloudCacheInvalidatorHolder>>>,0>>::_Erase<std::wstring>(std::wstring const &)
0x180014585  mov     rcx, [rbx+30h]
0x180014589  mov     rax, [rcx]
0x18001458c  mov     rax, [rax+10h]
0x180014590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014595  mov     rdx, rax
0x180014598  lea     rcx, [rsp+138h+lpString2]
0x1800145a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800145a5  nop
0x1800145a6  lea     r8, [rsp+138h+lpString2]
0x1800145ae  cmp     [rsp+138h+var_70], 7
0x1800145b7  cmova   r8, [rsp+138h+lpString2]; lpString2
0x1800145c0  mov     [rsp+138h+bIgnoreCase], 1; unsigned int
0x1800145c8  or      r9d, 0FFFFFFFFh; cchCount2
0x1800145cc  or      edx, r9d; cchCount1
0x1800145cf  lea     rcx, String1; "DefaultAccount"
0x1800145d6  call    cs:__imp_CompareStringOrdinal
0x1800145dc  cmp     eax, 2
0x1800145df  jnz     short loc_1800145FF
0x1800145e1  lea     rdx, [rbx+30h]
0x1800145e5  lea     rcx, [rsp+138h+var_F0]
0x1800145ea  call    ??0?$shared_ptr@VICloudStoreHomeCloudMgr@Cloud@Storage@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>(std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr> const &)
0x1800145ef  mov     rdx, rax
0x1800145f2  mov     rcx, r14
0x1800145f5  call    ?InvalidateAccountCacheData@CloudCacheInvalidatorServiceImpl@@AEAAXV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@std@@@Z; CloudCacheInvalidatorServiceImpl::InvalidateAccountCacheData(std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount>)
0x1800145fa  jmp     loc_1800146A9
0x1800145ff  lea     rdx, [rsp+138h+lpString2]
0x180014607  cmp     [rsp+138h+var_70], 7
0x180014610  cmova   rdx, [rsp+138h+lpString2]
0x180014619  lea     rcx, [rsp+138h+lpNewKeyName]
0x180014621  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014626  nop
0x180014627  lea     rdx, aStale; ".Stale"
0x18001462e  lea     rcx, [rsp+138h+lpNewKeyName]; Src
0x180014636  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001463b  lea     r8, [rsp+138h+lpNewKeyName]
0x180014643  cmp     [rsp+138h+var_50], 7
0x18001464c  cmova   r8, [rsp+138h+lpNewKeyName]; lpNewKeyName
0x180014655  lea     rdx, [rsp+138h+lpString2]
0x18001465d  cmp     [rsp+138h+var_70], 7
0x180014666  cmova   rdx, [rsp+138h+lpString2]; lpSubKeyName
0x18001466f  mov     rcx, [rsp+138h+hKey]; hKey
0x180014674  call    cs:__imp_RegRenameKey
0x18001467a  mov     rcx, [rsp+138h]; this
0x180014682  test    eax, eax
0x180014684  jz      short loc_18001469B
0x180014686  mov     r9d, eax; char *
0x180014689  lea     r8, aOnecoreuapShel_69; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180014690  mov     edx, 13Eh; void *
0x180014695  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18001469a  nop
0x18001469b  lea     rcx, [rsp+138h+lpNewKeyName]
0x1800146a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800146a8  nop
0x1800146a9  lea     rcx, [rsp+138h+lpString2]
0x1800146b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800146b6  mov     rbx, [rbx]
0x1800146b9  jmp     loc_18001453E
0x1800146be  lea     r8, [rdi+10h]
0x1800146c2  lea     rdx, [rsp+138h+var_F8]
0x1800146c7  mov     rcx, r13
0x1800146ca  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UActiveActivityStoreInfo@CloudCacheInvalidatorServiceImpl@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CloudCacheInvalidatorServiceImpl::ActiveActivityStoreInfo>>,0>>::find(std::wstring const &)
0x1800146cf  mov     rax, [r13+8]
0x1800146d3  cmp     qword ptr [rsp+138h+var_F8], rax
0x1800146d8  jnz     short loc_180014740
0x1800146da  mov     rcx, [rdi+30h]; this
0x1800146de  call    ?Stop@CloudCacheInvalidatorHolder@@QEAAXXZ; CloudCacheInvalidatorHolder::Stop(void)
0x1800146e3  mov     rdx, [rdi+30h]
0x1800146e7  add     rdx, 10h
0x1800146eb  lea     rcx, [rsp+138h+var_F0]
0x1800146f0  call    ??0?$shared_ptr@VICloudStoreHomeCloudMgr@Cloud@Storage@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr>(std::shared_ptr<Windows::Internal::Storage::Cloud::ICloudStoreHomeCloudMgr> const &)
0x1800146f5  nop
0x1800146f6  lea     r9, [rsp+138h+var_F0]
0x1800146fb  lea     r8, [rdi+10h]
0x1800146ff  lea     rdx, [rsp+138h+lpString2]
0x180014707  lea     rcx, [rsp+138h+var_C8]
0x18001470c  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$CBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const>>,0>>::emplace<std::wstring const &,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const &>(std::wstring const &,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const &)
0x180014711  mov     rcx, [rsp+138h]; this
0x180014719  cmp     byte ptr [rax+8], 0
0x18001471d  jnz     short loc_180014731
0x18001471f  lea     r8, aOnecoreuapShel_69; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180014726  mov     edx, 122h; void *
0x18001472b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180014731  mov     rcx, [rsp+138h+var_E8]; this
0x180014736  test    rcx, rcx
0x180014739  jz      short loc_180014740
0x18001473b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014740  mov     rdi, [rdi]
0x180014743  jmp     loc_180014478
0x180014748  mov     rcx, [rsp+138h+var_48]
0x180014750  xor     rcx, rsp; StackCookie
0x180014753  call    __security_check_cookie
0x180014758  add     rsp, 108h
0x18001475f  pop     r15
0x180014761  pop     r14
0x180014763  pop     r13
0x180014765  pop     rdi
0x180014766  pop     rsi
0x180014767  pop     rbx
0x180014768  retn
```
