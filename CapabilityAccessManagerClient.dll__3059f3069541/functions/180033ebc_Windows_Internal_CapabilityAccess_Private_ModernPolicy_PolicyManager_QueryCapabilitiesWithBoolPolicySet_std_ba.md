# Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::QueryCapabilitiesWithBoolPolicySet(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180033ebc`
- end: `0x180034132`
- name: `?QueryCapabilitiesWithBoolPolicySet@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@8@_N@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029960`

## callees

- `0x18000aa24`
- `0x18000b68c`
- `0x180028580`
- `0x18002f280`
- `0x180032348`
- `0x180032820`
- `0x180033ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033f16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033f16`

## string_xrefs

- `0x180033fd9`: `AppLaunchAccessCheckRequired`
- `0x18003408f`: `PublishAccessWNFOnSessionChange`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::QueryCapabilitiesWithBoolPolicySet(
        _QWORD *a1,
        __int64 a2,
        char a3,
        const char *a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v18; // [rsp+20h] [rbp-10h]
  RTL_SRWLOCK *v19; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v21; // [rsp+78h] [rbp+48h] BYREF

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  LODWORD(v18) = 1;
  if ( !Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\base\\devices\\cam\\policy\\policymanager.cpp",
      a4);
  AcquireSRWLockShared(&Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock);
  v19 = &Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock;
  if ( (unsigned int)std::wstring::compare(a2, L"PerAppConsentForFullTrustApps") )
  {
    if ( (unsigned int)std::wstring::compare(a2, L"RecordUsageData") )
    {
      if ( (unsigned int)std::wstring::compare(a2, L"AppLaunchAccessCheckRequired") )
      {
        if ( (unsigned int)std::wstring::compare(a2, L"UserConsentRequired") )
        {
          if ( (unsigned int)std::wstring::compare(a2, L"PublishAccessWNFOnSessionChange") )
            wil::details::in1diag3::FailFast_UnexpectedMsg(
              retaddr,
              (void *)0xCC,
              (unsigned int)"onecore\\base\\devices\\cam\\policy\\policymanager.cpp",
              "GetCapabilitiesSupportingBoolPolicy called with un-mapped policy string",
              v18,
              v19);
          v15 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
          v21 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
          while ( !*(_BYTE *)(v15 + 25) )
          {
            v16 = *(_QWORD *)(v15 + 64);
            if ( *(_BYTE *)(v16 + 57) && (a3 || !*(_BYTE *)(v16 + 63)) )
              std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(a1);
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(&v21);
            v15 = v21;
          }
        }
        else
        {
          v13 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
          v21 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
          while ( !*(_BYTE *)(v13 + 25) )
          {
            v14 = *(_QWORD *)(v13 + 64);
            if ( *(_BYTE *)(v14 + 65) && (a3 || !*(_BYTE *)(v14 + 63)) )
              std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(a1);
            std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(&v21);
            v13 = v21;
          }
        }
      }
      else
      {
        v11 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
        v21 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
        while ( !*(_BYTE *)(v11 + 25) )
        {
          v12 = *(_QWORD *)(v11 + 64);
          if ( *(_BYTE *)(v12 + 47) && (a3 || !*(_BYTE *)(v12 + 63)) )
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(a1);
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(&v21);
          v11 = v21;
        }
      }
    }
    else
    {
      v9 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
      v21 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
      while ( !*(_BYTE *)(v9 + 25) )
      {
        v10 = *(_QWORD *)(v9 + 64);
        if ( *(_BYTE *)(v10 + 58) && (a3 || !*(_BYTE *)(v10 + 63)) )
          std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(a1);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(&v21);
        v9 = v21;
      }
    }
  }
  else
  {
    v7 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
    v21 = *(_QWORD *)Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache;
    while ( !*(_BYTE *)(v7 + 25) )
    {
      v8 = *(_QWORD *)(v7 + 64);
      if ( *(_BYTE *)(v8 + 489) && (a3 || !*(_BYTE *)(v8 + 63)) )
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(a1);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(&v21);
      v7 = v21;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  return a1;
}

```

## disassembly

```asm
0x180033ebc  mov     [rsp-28h+arg_8], rbx
0x180033ec1  mov     [rsp-28h+arg_0], rcx
0x180033ec6  push    rbp
0x180033ec7  push    rsi
0x180033ec8  push    rdi
0x180033ec9  push    r14
0x180033ecb  push    r15
0x180033ecd  mov     rbp, rsp
0x180033ed0  sub     rsp, 30h
0x180033ed4  mov     sil, r8b
0x180033ed7  mov     rdi, rdx
0x180033eda  mov     rbx, rcx
0x180033edd  xor     r15d, r15d
0x180033ee0  mov     dword ptr [rbp+var_10], r15d
0x180033ee4  mov     [rcx], r15
0x180033ee7  mov     [rcx+8], r15
0x180033eeb  mov     [rcx+10h], r15
0x180033eef  mov     dword ptr [rbp+var_10], 1
0x180033ef6  cmp     cs:?m_isInitialized@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0_NA, r15b; bool Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_isInitialized
0x180033efd  setz    al
0x180033f00  mov     rcx, [rbp+28h]; this
0x180033f04  test    al, al
0x180033f06  jnz     loc_180034103
0x180033f0c  lea     r14, ?m_policyLock@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyLock
0x180033f13  mov     rcx, r14; SRWLock
0x180033f16  call    cs:__imp_AcquireSRWLockShared
0x180033f1c  mov     [rbp+var_8], r14
0x180033f20  lea     rdx, aPerappconsentf; "PerAppConsentForFullTrustApps"
0x180033f27  mov     rcx, rdi
0x180033f2a  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180033f2f  test    eax, eax
0x180033f31  jnz     short loc_180033F7E
0x180033f33  mov     rax, cs:?m_policyCache@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>> Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache
0x180033f3a  mov     rax, [rax]
0x180033f3d  mov     [rbp+arg_18], rax
0x180033f41  cmp     [rax+19h], r15b
0x180033f45  jnz     loc_1800340E6
0x180033f4b  lea     rdx, [rax+20h]
0x180033f4f  mov     rax, [rdx+20h]
0x180033f53  cmp     [rax+1E9h], r15b
0x180033f5a  jz      short loc_180033F6F
0x180033f5c  test    sil, sil
0x180033f5f  jnz     short loc_180033F67
0x180033f61  cmp     [rax+3Fh], r15b
0x180033f65  jnz     short loc_180033F6F
0x180033f67  mov     rcx, rbx
0x180033f6a  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x180033f6f  lea     rcx, [rbp+arg_18]
0x180033f73  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(void)
0x180033f78  mov     rax, [rbp+arg_18]
0x180033f7c  jmp     short loc_180033F41
0x180033f7e  lea     rdx, aRecordusagedat; "RecordUsageData"
0x180033f85  mov     rcx, rdi
0x180033f88  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180033f8d  test    eax, eax
0x180033f8f  jnz     short loc_180033FD9
0x180033f91  mov     rax, cs:?m_policyCache@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>> Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache
0x180033f98  mov     rax, [rax]
0x180033f9b  mov     [rbp+arg_18], rax
0x180033f9f  cmp     [rax+19h], r15b
0x180033fa3  jnz     loc_1800340E6
0x180033fa9  lea     rdx, [rax+20h]
0x180033fad  mov     rax, [rdx+20h]
0x180033fb1  cmp     [rax+3Ah], r15b
0x180033fb5  jz      short loc_180033FCA
0x180033fb7  test    sil, sil
0x180033fba  jnz     short loc_180033FC2
0x180033fbc  cmp     [rax+3Fh], r15b
0x180033fc0  jnz     short loc_180033FCA
0x180033fc2  mov     rcx, rbx
0x180033fc5  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x180033fca  lea     rcx, [rbp+arg_18]
0x180033fce  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(void)
0x180033fd3  mov     rax, [rbp+arg_18]
0x180033fd7  jmp     short loc_180033F9F
0x180033fd9  lea     rdx, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x180033fe0  mov     rcx, rdi
0x180033fe3  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180033fe8  test    eax, eax
0x180033fea  jnz     short loc_180034034
0x180033fec  mov     rax, cs:?m_policyCache@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>> Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache
0x180033ff3  mov     rax, [rax]
0x180033ff6  mov     [rbp+arg_18], rax
0x180033ffa  cmp     [rax+19h], r15b
0x180033ffe  jnz     loc_1800340E6
0x180034004  lea     rdx, [rax+20h]
0x180034008  mov     rax, [rdx+20h]
0x18003400c  cmp     [rax+2Fh], r15b
0x180034010  jz      short loc_180034025
0x180034012  test    sil, sil
0x180034015  jnz     short loc_18003401D
0x180034017  cmp     [rax+3Fh], r15b
0x18003401b  jnz     short loc_180034025
0x18003401d  mov     rcx, rbx
0x180034020  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x180034025  lea     rcx, [rbp+arg_18]
0x180034029  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(void)
0x18003402e  mov     rax, [rbp+arg_18]
0x180034032  jmp     short loc_180033FFA
0x180034034  lea     rdx, aUserconsentreq; "UserConsentRequired"
0x18003403b  mov     rcx, rdi
0x18003403e  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x180034043  test    eax, eax
0x180034045  jnz     short loc_18003408F
0x180034047  mov     rax, cs:?m_policyCache@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>> Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache
0x18003404e  mov     rax, [rax]
0x180034051  mov     [rbp+arg_18], rax
0x180034055  cmp     [rax+19h], r15b
0x180034059  jnz     loc_1800340E6
0x18003405f  lea     rdx, [rax+20h]
0x180034063  mov     rax, [rdx+20h]
0x180034067  cmp     [rax+41h], r15b
0x18003406b  jz      short loc_180034080
0x18003406d  test    sil, sil
0x180034070  jnz     short loc_180034078
0x180034072  cmp     [rax+3Fh], r15b
0x180034076  jnz     short loc_180034080
0x180034078  mov     rcx, rbx
0x18003407b  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x180034080  lea     rcx, [rbp+arg_18]
0x180034084  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(void)
0x180034089  mov     rax, [rbp+arg_18]
0x18003408d  jmp     short loc_180034055
0x18003408f  lea     rdx, aPublishaccessw; "PublishAccessWNFOnSessionChange"
0x180034096  mov     rcx, rdi
0x180034099  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x18003409e  test    eax, eax
0x1800340a0  jnz     short loc_180034115
0x1800340a2  mov     rax, cs:?m_policyCache@PolicyManager@ModernPolicy@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@2@@std@@A; std::map<std::wstring,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>> Windows::Internal::CapabilityAccess::Private::ModernPolicy::PolicyManager::m_policyCache
0x1800340a9  mov     rax, [rax]
0x1800340ac  mov     [rbp+arg_18], rax
0x1800340b0  cmp     [rax+19h], r15b
0x1800340b4  jnz     short loc_1800340E6
0x1800340b6  lea     rdx, [rax+20h]
0x1800340ba  mov     rax, [rdx+20h]
0x1800340be  cmp     [rax+39h], r15b
0x1800340c2  jz      short loc_1800340D7
0x1800340c4  test    sil, sil
0x1800340c7  jnz     short loc_1800340CF
0x1800340c9  cmp     [rax+3Fh], r15b
0x1800340cd  jnz     short loc_1800340D7
0x1800340cf  mov     rcx, rbx
0x1800340d2  call    ??$_Emplace_one_at_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(std::wstring const &)
0x1800340d7  lea     rcx, [rbp+arg_18]
0x1800340db  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityPolicy>>>>,std::_Iterator_base0>::operator++(void)
0x1800340e0  mov     rax, [rbp+arg_18]
0x1800340e4  jmp     short loc_1800340B0
0x1800340e6  lea     rcx, [rbp+var_8]
0x1800340ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800340ef  mov     rax, rbx
0x1800340f2  mov     rbx, [rsp+30h+arg_8]
0x1800340f7  add     rsp, 30h
0x1800340fb  pop     r15
0x1800340fd  pop     r14
0x1800340ff  pop     rdi
0x180034100  pop     rsi
0x180034101  pop     rbp
0x180034102  retn
0x180034103  lea     r8, aOnecoreBaseDev_12; "onecore\\base\\devices\\cam\\policy\\po"...
0x18003410a  mov     edx, 83h; void *
0x18003410f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034115  mov     rcx, [rbp+28h]; this
0x180034119  lea     r9, aGetcapabilitie; "GetCapabilitiesSupportingBoolPolicy cal"...
0x180034120  lea     r8, aOnecoreBaseDev_12; "onecore\\base\\devices\\cam\\policy\\po"...
0x180034127  mov     edx, 0CCh; void *
0x18003412c  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
```
