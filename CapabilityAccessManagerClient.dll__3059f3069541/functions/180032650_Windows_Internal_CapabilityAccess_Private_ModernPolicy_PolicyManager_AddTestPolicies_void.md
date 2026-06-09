# Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::AddTestPolicies(void)

- ea: `0x180032650`
- end: `0x18003281a`
- name: `?AddTestPolicies@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@CAXXZ`
- size: `458`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180032b34`

## callees

- `0x18000aa04`
- `0x18000b68c`
- `0x18001c330`
- `0x1800316fc`
- `0x180031d44`
- `0x180032650`
- `0x180032df0`
- `0x180032ec8`
- `0x180032fa0`
- `0x180033150`
- `0x180033300`
- `0x1800336b0`
- `0x1800337ac`
- `0x180033d0c`
- `0x180034790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180032667`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180032667`

## string_xrefs

- `0x18003276c`: `ModernTestPolicy_AppLaunchAccessCheckRequired_AppOverride`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::AddTestPolicies(void)
{
  const char *v0; // r9
  _QWORD *v1; // rax
  __int64 v2; // rcx
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rcx
  _BYTE v17[8]; // [rsp+20h] [rbp-20h] BYREF
  std::_Ref_count_base *v18; // [rsp+28h] [rbp-18h]
  _BYTE v19[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  unsigned __int64 v21; // [rsp+50h] [rbp+10h] BYREF

  v21 = (unsigned __int64)&Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock
      & -(__int64)(TryAcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock) != 0);
  if ( v21 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\base\\devices\\cam\\policy\\policymanager.cpp",
      v0);
  v1 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::BaselineFull::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v2,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_BaselineFull",
    v1);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v3 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::SimpleRegionOverride::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v4,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_SimpleRegionOverride",
    v3);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v5 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::EditionOverrides::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v6,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_EditionOverrides",
    v5);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v7 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppOverrides::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v8,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_AppOverrides",
    v7);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v9 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::Handler::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v10,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_Handler",
    v9);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v11 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppLaunchAccessCheckRequired_AppOverride::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v12,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_AppLaunchAccessCheckRequired_AppOverride",
    v11);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  v13 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppCategoryConsentOverride::MintPolicy(v17);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
    v14,
    (__int64)v19,
    (__int64)L"ModernTestPolicy_AppCategoryConsentOverride",
    v13);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl'::`2'::impl) )
  {
    v15 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::LegacyBaseline::MintPolicy(v17);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<unsigned short const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
      v16,
      (__int64)v19,
      (__int64)L"ModernTestPolicy_LegacyBaseline",
      v15);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
}

```

## disassembly

```asm
0x180032650  mov     [rsp-8+arg_8], rbx
0x180032655  push    rbp
0x180032656  mov     rbp, rsp
0x180032659  sub     rsp, 40h
0x18003265d  lea     rbx, ?m_policyLock@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock
0x180032664  mov     rcx, rbx; SRWLock
0x180032667  call    cs:__imp_TryAcquireSRWLockExclusive
0x18003266d  neg     al
0x18003266f  sbb     rcx, rcx
0x180032672  and     rcx, rbx
0x180032675  mov     [rbp+arg_0], rcx
0x180032679  mov     rcx, [rbp+8]; this
0x18003267d  jnz     loc_180032808
0x180032683  lea     rcx, [rbp+var_20]
0x180032687  call    ?MintPolicy@BaselineFull@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::BaselineFull::MintPolicy(void)
0x18003268c  nop
0x18003268d  mov     r9, rax
0x180032690  lea     r8, aModerntestpoli_1; "ModernTestPolicy_BaselineFull"
0x180032697  lea     rdx, [rbp+var_10]
0x18003269b  call    ??$emplace@AEAY0BO@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEAY0BO@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x1800326a0  nop
0x1800326a1  mov     rcx, [rbp+var_18]; this
0x1800326a5  test    rcx, rcx
0x1800326a8  jz      short loc_1800326AF
0x1800326aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800326af  lea     rcx, [rbp+var_20]
0x1800326b3  call    ?MintPolicy@SimpleRegionOverride@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::SimpleRegionOverride::MintPolicy(void)
0x1800326b8  nop
0x1800326b9  mov     r9, rax
0x1800326bc  lea     r8, aModerntestpoli; "ModernTestPolicy_SimpleRegionOverride"
0x1800326c3  lea     rdx, [rbp+var_10]
0x1800326c7  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x1800326cc  nop
0x1800326cd  mov     rcx, [rbp+var_18]; this
0x1800326d1  test    rcx, rcx
0x1800326d4  jz      short loc_1800326DB
0x1800326d6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800326db  lea     rcx, [rbp+var_20]
0x1800326df  call    ?MintPolicy@EditionOverrides@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::EditionOverrides::MintPolicy(void)
0x1800326e4  nop
0x1800326e5  mov     r9, rax
0x1800326e8  lea     r8, aModerntestpoli_5; "ModernTestPolicy_EditionOverrides"
0x1800326ef  lea     rdx, [rbp+var_10]
0x1800326f3  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x1800326f8  nop
0x1800326f9  mov     rcx, [rbp+var_18]; this
0x1800326fd  test    rcx, rcx
0x180032700  jz      short loc_180032707
0x180032702  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032707  lea     rcx, [rbp+var_20]
0x18003270b  call    ?MintPolicy@AppOverrides@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppOverrides::MintPolicy(void)
0x180032710  nop
0x180032711  mov     r9, rax
0x180032714  lea     r8, aModerntestpoli_6; "ModernTestPolicy_AppOverrides"
0x18003271b  lea     rdx, [rbp+var_10]
0x18003271f  call    ??$emplace@AEAY0BO@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEAY0BO@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[30],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032724  nop
0x180032725  mov     rcx, [rbp+var_18]; this
0x180032729  test    rcx, rcx
0x18003272c  jz      short loc_180032733
0x18003272e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032733  lea     rcx, [rbp+var_20]
0x180032737  call    ?MintPolicy@Handler@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::Handler::MintPolicy(void)
0x18003273c  nop
0x18003273d  mov     r9, rax
0x180032740  lea     r8, aModerntestpoli_2; "ModernTestPolicy_Handler"
0x180032747  lea     rdx, [rbp+var_10]
0x18003274b  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032750  nop
0x180032751  mov     rcx, [rbp+var_18]; this
0x180032755  test    rcx, rcx
0x180032758  jz      short loc_18003275F
0x18003275a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003275f  lea     rcx, [rbp+var_20]
0x180032763  call    ?MintPolicy@AppLaunchAccessCheckRequired_AppOverride@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppLaunchAccessCheckRequired_AppOverride::MintPolicy(void)
0x180032768  nop
0x180032769  mov     r9, rax
0x18003276c  lea     r8, aModerntestpoli_4; "ModernTestPolicy_AppLaunchAccessCheckRe"...
0x180032773  lea     rdx, [rbp+var_10]
0x180032777  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x18003277c  nop
0x18003277d  mov     rcx, [rbp+var_18]; this
0x180032781  test    rcx, rcx
0x180032784  jz      short loc_18003278B
0x180032786  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003278b  lea     rcx, [rbp+var_20]
0x18003278f  call    ?MintPolicy@AppCategoryConsentOverride@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::AppCategoryConsentOverride::MintPolicy(void)
0x180032794  nop
0x180032795  mov     r9, rax
0x180032798  lea     r8, aModerntestpoli_0; "ModernTestPolicy_AppCategoryConsentOver"...
0x18003279f  lea     rdx, [rbp+var_10]
0x1800327a3  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x1800327a8  nop
0x1800327a9  mov     rcx, [rbp+var_18]; this
0x1800327ad  test    rcx, rcx
0x1800327b0  jz      short loc_1800327B7
0x1800327b2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LegacyBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline> `wil::Feature<__WilFeatureTraits_Feature_LegacyBaseline>::GetImpl(void)'::`2'::impl
0x1800327be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::__private_IsEnabled(void)
0x1800327c3  test    al, al
0x1800327c5  jz      short loc_1800327F4
0x1800327c7  lea     rcx, [rbp+var_20]
0x1800327cb  call    ?MintPolicy@LegacyBaseline@TestPolicies@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::TestPolicies::LegacyBaseline::MintPolicy(void)
0x1800327d0  nop
0x1800327d1  mov     r9, rax
0x1800327d4  lea     r8, aModerntestpoli_3; "ModernTestPolicy_LegacyBaseline"
0x1800327db  lea     rdx, [rbp+var_10]
0x1800327df  call    ??$_Emplace@AEAY0CG@$$CBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@PEAX@std@@_N@1@AEAY0CG@$$CBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::_Emplace<ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const (&)[38],std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x1800327e4  nop
0x1800327e5  mov     rcx, [rbp+var_18]; this
0x1800327e9  test    rcx, rcx
0x1800327ec  jz      short loc_1800327F4
0x1800327ee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327f3  nop
0x1800327f4  lea     rcx, [rbp+arg_0]
0x1800327f8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800327fd  mov     rbx, [rsp+40h+arg_8]
0x180032802  add     rsp, 40h
0x180032806  pop     rbp
0x180032807  retn
0x180032808  lea     r8, aOnecoreBaseDev_12; "onecore\\base\\devices\\cam\\policy\\po"...
0x18003280f  mov     edx, 139h; void *
0x180032814  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
