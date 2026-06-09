# Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::Initialize(void)

- ea: `0x180032b34`
- end: `0x180032de9`
- name: `?Initialize@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@SAXXZ`
- size: `693`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ecf8`

## callees

- `0x18000aa04`
- `0x18000b68c`
- `0x18001c330`
- `0x180028320`
- `0x180028414`
- `0x180030c14`
- `0x180031d78`
- `0x180032650`
- `0x180032b34`
- `0x180033078`
- `0x180033228`
- `0x1800333d8`
- `0x1800334b0`
- `0x1800335b0`
- `0x180033884`
- `0x18003395c`
- `0x180033a34`
- `0x180033b34`
- `0x180033c34`
- `0x180033de4`
- `0x180034750`
- `0x1800347d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032b4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032b4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::Initialize(void)
{
  _QWORD *v0; // rax
  __int64 v1; // rcx
  _QWORD *v2; // rax
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rcx
  const char *v8; // r9
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // [rsp+20h] [rbp-20h] BYREF
  std::_Ref_count_base *v39; // [rsp+28h] [rbp-18h]
  _BYTE v40[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  RTL_SRWLOCK *v42; // [rsp+50h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock);
  v42 = &Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock;
  if ( !Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized )
  {
    v0 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::GraphicsCaptureProgrammatic::MintPolicy(&v38);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
      v1,
      (__int64)v40,
      &c_szCapabilityGraphicsCaptureProgrammatic,
      v0);
    if ( v39 )
      std::_Ref_count_base::_Decref(v39);
    v2 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::GraphicsCaptureLegacy::MintPolicy(&v38);
    std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
      v3,
      (__int64)v40,
      &c_szCapabilityGraphicsCaptureLegacy,
      v2);
    if ( v39 )
      std::_Ref_count_base::_Decref(v39);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::GetImpl'::`2'::impl) )
    {
      v4 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::Passkeys::MintPolicy(&v38);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v5,
        (__int64)v40,
        &c_szCapabilityPasskeys,
        v4);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      v6 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PasskeysEnumeration::MintPolicy(&v38);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v7,
        (__int64)v40,
        &c_szCapabilityPasskeysEnumeration,
        v6);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl'::`2'::impl) )
    {
      if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
          v8);
      if ( Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_policyTemplate == 1 )
      {
        v9 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::Microphone::MintPolicy(&v38);
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
          v10,
          (__int64)v40,
          &c_szCapabilityMicrophone,
          v9);
        if ( v39 )
          std::_Ref_count_base::_Decref(v39);
        v11 = (_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::Webcam::MintPolicy(&v38);
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
          v12,
          (__int64)v40,
          &c_szCapabilityWebcam,
          v11);
        if ( v39 )
          std::_Ref_count_base::_Decref(v39);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl'::`2'::impl) )
    {
      v16 = Windows::Internal::CapabilityAccess::Private::ModernPolicy::BackgroundAITasks::MintPolicy(
              &v38,
              v13,
              v14,
              v15);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v17,
        (__int64)v40,
        &c_szCapabilityBackgroundAITasks,
        v16);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      v21 = Windows::Internal::CapabilityAccess::Private::ModernPolicy::CuaAccess::MintPolicy(&v38, v18, v19, v20);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v22,
        (__int64)v40,
        &c_szPolicyCuaAccess,
        v21);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      v26 = Windows::Internal::CapabilityAccess::Private::ModernPolicy::McpAccess::MintPolicy(&v38, v23, v24, v25);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v27,
        (__int64)v40,
        &c_szPolicyMcpAccess,
        v26);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
      v31 = Windows::Internal::CapabilityAccess::Private::ModernPolicy::RemoteMcpAccess::MintPolicy(&v38, v28, v29, v30);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v32,
        (__int64)v40,
        &c_szPolicyRemoteMcpAccess,
        v31);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58761460>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_58761460>::GetImpl'::`2'::impl) )
    {
      v36 = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ForegroundTextAccess::MintPolicy(
              &v38,
              v33,
              v34,
              v35);
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<unsigned short const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(
        v37,
        (__int64)v40,
        &c_szCapabilityForegroundTextAccess,
        v36);
      if ( v39 )
        std::_Ref_count_base::_Decref(v39);
    }
    Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::AddTestPolicies();
    Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v42);
}

```

## disassembly

```asm
0x180032b34  mov     [rsp-8+arg_8], rbx
0x180032b39  push    rbp
0x180032b3a  mov     rbp, rsp
0x180032b3d  sub     rsp, 40h
0x180032b41  lea     rbx, ?m_policyLock@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock
0x180032b48  mov     rcx, rbx; SRWLock
0x180032b4b  call    cs:__imp_AcquireSRWLockExclusive
0x180032b51  mov     [rbp+arg_0], rbx
0x180032b55  cmp     cs:?m_isInitialized@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0_NA, 0; bool Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized
0x180032b5c  jnz     loc_180032DC3
0x180032b62  lea     rcx, [rbp+var_20]
0x180032b66  call    ?MintPolicy@GraphicsCaptureProgrammatic@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::GraphicsCaptureProgrammatic::MintPolicy(void)
0x180032b6b  nop
0x180032b6c  mov     r9, rax
0x180032b6f  lea     r8, ?c_szCapabilityGraphicsCaptureProgrammatic@@3QEBGEB; ushort const * const c_szCapabilityGraphicsCaptureProgrammatic
0x180032b76  lea     rdx, [rbp+var_10]
0x180032b7a  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032b7f  nop
0x180032b80  mov     rcx, [rbp+var_18]; this
0x180032b84  test    rcx, rcx
0x180032b87  jz      short loc_180032B8E
0x180032b89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032b8e  lea     rcx, [rbp+var_20]
0x180032b92  call    ?MintPolicy@GraphicsCaptureLegacy@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::GraphicsCaptureLegacy::MintPolicy(void)
0x180032b97  nop
0x180032b98  mov     r9, rax
0x180032b9b  lea     r8, ?c_szCapabilityGraphicsCaptureLegacy@@3QEBGEB; ushort const * const c_szCapabilityGraphicsCaptureLegacy
0x180032ba2  lea     rdx, [rbp+var_10]
0x180032ba6  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032bab  nop
0x180032bac  mov     rcx, [rbp+var_18]; this
0x180032bb0  test    rcx, rcx
0x180032bb3  jz      short loc_180032BBA
0x180032bb5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032bba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl> `wil::Feature<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::GetImpl(void)'::`2'::impl
0x180032bc1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PasskeyPrivacyAppControl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPrivacyAppControl>::__private_IsEnabled(void)
0x180032bc6  test    al, al
0x180032bc8  jz      short loc_180032C22
0x180032bca  lea     rcx, [rbp+var_20]
0x180032bce  call    ?MintPolicy@Passkeys@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::Passkeys::MintPolicy(void)
0x180032bd3  nop
0x180032bd4  mov     r9, rax
0x180032bd7  lea     r8, ?c_szCapabilityPasskeys@@3QEBGEB; ushort const * const c_szCapabilityPasskeys
0x180032bde  lea     rdx, [rbp+var_10]
0x180032be2  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032be7  nop
0x180032be8  mov     rcx, [rbp+var_18]; this
0x180032bec  test    rcx, rcx
0x180032bef  jz      short loc_180032BF6
0x180032bf1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032bf6  lea     rcx, [rbp+var_20]
0x180032bfa  call    ?MintPolicy@PasskeysEnumeration@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::PasskeysEnumeration::MintPolicy(void)
0x180032bff  nop
0x180032c00  mov     r9, rax
0x180032c03  lea     r8, ?c_szCapabilityPasskeysEnumeration@@3QEBGEB; ushort const * const c_szCapabilityPasskeysEnumeration
0x180032c0a  lea     rdx, [rbp+var_10]
0x180032c0e  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032c13  nop
0x180032c14  mov     rcx, [rbp+var_18]; this
0x180032c18  test    rcx, rcx
0x180032c1b  jz      short loc_180032C22
0x180032c1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CM_OneClick@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick> `wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl(void)'::`2'::impl
0x180032c29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(void)
0x180032c2e  test    al, al
0x180032c30  jz      short loc_180032CA7
0x180032c32  mov     eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x180032c38  nop
0x180032c39  mov     rcx, [rbp+8]; this
0x180032c3d  cmp     eax, 1
0x180032c40  jb      loc_180032DD7
0x180032c46  cmp     cs:?m_policyTemplate@RegistryConfig@Globals@Private@CapabilityAccess@Internal@Windows@@0IA, 1; uint Windows::Internal::CapabilityAccess::Private::Globals::RegistryConfig::m_policyTemplate
0x180032c4d  jnz     short loc_180032CA7
0x180032c4f  lea     rcx, [rbp+var_20]
0x180032c53  call    ?MintPolicy@Microphone@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::Microphone::MintPolicy(void)
0x180032c58  nop
0x180032c59  mov     r9, rax
0x180032c5c  lea     r8, ?c_szCapabilityMicrophone@@3QEBGEB; ushort const * const c_szCapabilityMicrophone
0x180032c63  lea     rdx, [rbp+var_10]
0x180032c67  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032c6c  nop
0x180032c6d  mov     rcx, [rbp+var_18]; this
0x180032c71  test    rcx, rcx
0x180032c74  jz      short loc_180032C7B
0x180032c76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032c7b  lea     rcx, [rbp+var_20]
0x180032c7f  call    ?MintPolicy@Webcam@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::Webcam::MintPolicy(void)
0x180032c84  nop
0x180032c85  mov     r9, rax
0x180032c88  lea     r8, ?c_szCapabilityWebcam@@3QEBGEB; ushort const * const c_szCapabilityWebcam
0x180032c8f  lea     rdx, [rbp+var_10]
0x180032c93  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032c98  nop
0x180032c99  mov     rcx, [rbp+var_18]; this
0x180032c9d  test    rcx, rcx
0x180032ca0  jz      short loc_180032CA7
0x180032ca2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032ca7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58336780@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780> `wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl(void)'::`2'::impl
0x180032cae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(void)
0x180032cb3  test    al, al
0x180032cb5  jz      short loc_180032CE3
0x180032cb7  lea     rcx, [rbp+var_20]
0x180032cbb  call    ?MintPolicy@BackgroundAITasks@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::BackgroundAITasks::MintPolicy(void)
0x180032cc0  nop
0x180032cc1  mov     r9, rax
0x180032cc4  lea     r8, ?c_szCapabilityBackgroundAITasks@@3QEBGEB; ushort const * const c_szCapabilityBackgroundAITasks
0x180032ccb  lea     rdx, [rbp+var_10]
0x180032ccf  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032cd4  nop
0x180032cd5  mov     rcx, [rbp+var_18]; this
0x180032cd9  test    rcx, rcx
0x180032cdc  jz      short loc_180032CE3
0x180032cde  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032ce3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x180032cea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x180032cef  test    al, al
0x180032cf1  jz      loc_180032D7B
0x180032cf7  lea     rcx, [rbp+var_20]
0x180032cfb  call    ?MintPolicy@CuaAccess@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::CuaAccess::MintPolicy(void)
0x180032d00  nop
0x180032d01  mov     r9, rax
0x180032d04  lea     r8, ?c_szPolicyCuaAccess@@3QEBGEB; ushort const * const c_szPolicyCuaAccess
0x180032d0b  lea     rdx, [rbp+var_10]
0x180032d0f  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032d14  nop
0x180032d15  mov     rcx, [rbp+var_18]; this
0x180032d19  test    rcx, rcx
0x180032d1c  jz      short loc_180032D23
0x180032d1e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032d23  lea     rcx, [rbp+var_20]
0x180032d27  call    ?MintPolicy@McpAccess@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::McpAccess::MintPolicy(void)
0x180032d2c  nop
0x180032d2d  mov     r9, rax
0x180032d30  lea     r8, ?c_szPolicyMcpAccess@@3QEBGEB; ushort const * const c_szPolicyMcpAccess
0x180032d37  lea     rdx, [rbp+var_10]
0x180032d3b  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032d40  nop
0x180032d41  mov     rcx, [rbp+var_18]; this
0x180032d45  test    rcx, rcx
0x180032d48  jz      short loc_180032D4F
0x180032d4a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032d4f  lea     rcx, [rbp+var_20]
0x180032d53  call    ?MintPolicy@RemoteMcpAccess@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::RemoteMcpAccess::MintPolicy(void)
0x180032d58  nop
0x180032d59  mov     r9, rax
0x180032d5c  lea     r8, ?c_szPolicyRemoteMcpAccess@@3QEBGEB; ushort const * const c_szPolicyRemoteMcpAccess
0x180032d63  lea     rdx, [rbp+var_10]
0x180032d67  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032d6c  nop
0x180032d6d  mov     rcx, [rbp+var_18]; this
0x180032d71  test    rcx, rcx
0x180032d74  jz      short loc_180032D7B
0x180032d76  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032d7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_58761460@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58761460@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58761460> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_58761460>::GetImpl(void)'::`2'::impl
0x180032d82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_58761460@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_58761460>::__private_IsEnabled(void)
0x180032d87  test    al, al
0x180032d89  jz      short loc_180032DB7
0x180032d8b  lea     rcx, [rbp+var_20]
0x180032d8f  call    ?MintPolicy@ForegroundTextAccess@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@YA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::ForegroundTextAccess::MintPolicy(void)
0x180032d94  nop
0x180032d95  mov     r9, rax
0x180032d98  lea     r8, ?c_szCapabilityForegroundTextAccess@@3QEBGEB; ushort const * const c_szCapabilityForegroundTextAccess
0x180032d9f  lea     rdx, [rbp+var_10]
0x180032da3  call    ??$emplace@AEBQEBGV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@@std@@_N@1@AEBQEBG$$QEAV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>,0>>::emplace<ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>(ushort const * const &,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy> &&)
0x180032da8  nop
0x180032da9  mov     rcx, [rbp+var_18]; this
0x180032dad  test    rcx, rcx
0x180032db0  jz      short loc_180032DB7
0x180032db2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032db7  call    ?AddTestPolicies@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@CAXXZ; Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::AddTestPolicies(void)
0x180032dbc  mov     cs:?m_isInitialized@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0_NA, 1; bool Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized
0x180032dc3  lea     rcx, [rbp+arg_0]
0x180032dc7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180032dcc  mov     rbx, [rsp+40h+arg_8]
0x180032dd1  add     rsp, 40h
0x180032dd5  pop     rbp
0x180032dd6  retn
0x180032dd7  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\core\\sync"...
0x180032dde  mov     edx, 265h; void *
0x180032de3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
