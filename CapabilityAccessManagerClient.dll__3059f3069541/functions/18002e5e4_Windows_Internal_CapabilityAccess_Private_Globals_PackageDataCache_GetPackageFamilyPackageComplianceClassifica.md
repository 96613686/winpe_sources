# Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetPackageFamilyPackageComplianceClassification(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002e5e4`
- end: `0x18002e769`
- name: `?GetPackageFamilyPackageComplianceClassification@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@SA?AW4PackageComplianceClassification@3456@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `389`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800222c8`

## callees

- `0x180003c80`
- `0x18000aa04`
- `0x18000f9e4`
- `0x180014754`
- `0x1800214b0`
- `0x1800225a0`
- `0x180022728`
- `0x18002d6b0`
- `0x18002df28`
- `0x18002e5e4`
- `0x18002f1b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e622`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e622`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::GetPackageFamilyPackageComplianceClassification(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 PackageFullNameFromFamilyNameAndUser; // rax
  __int64 *v8; // rdx
  wil *v9; // rcx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // [rsp+20h] [rbp-B8h] BYREF
  _QWORD v13[2]; // [rsp+28h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v14; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-98h] BYREF
  char v16; // [rsp+50h] [rbp-88h] BYREF
  __int128 v17; // [rsp+60h] [rbp-78h] BYREF
  __int64 v18; // [rsp+70h] [rbp-68h]
  __int64 v19; // [rsp+78h] [rbp-60h]
  _BYTE v20[64]; // [rsp+80h] [rbp-58h] BYREF

  v2 = a2;
  v3 = a1;
  v15 = a1;
  v13[0] = a2;
  AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::m_packageFamilyNamePackageComplianceClassificationMapLock);
  v14 = &Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::m_packageFamilyNamePackageComplianceClassificationMapLock;
  std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(v20, v4, v3, v2, v12, v13[0]);
  std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,std::wstring>,enum Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification,std::less<std::tuple<std::wstring,std::wstring>>,std::allocator<std::pair<std::tuple<std::wstring,std::wstring> const,enum Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>>,0>>::find(
    v5,
    &v12,
    v20);
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v20);
  if ( v12 == Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::m_packageFamilyNamePackageComplianceClassificationCache )
  {
    try
    {
      v17 = 0;
      v18 = 0;
      v19 = 7;
      LOWORD(v17) = 0;
      PackageFullNameFromFamilyNameAndUser = Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(
                                               (__int64)v20,
                                               v2,
                                               v3);
      std::wstring::operator=(&v17, PackageFullNameFromFamilyNameAndUser);
      std::wstring::_Tidy_deallocate(v20);
    }
    catch ( wil::ResultException )
    {
      if ( (unsigned int)wil::ResultFromCaughtException(v9) != -2147023728 )
        throw;
      v3 = v15;
      v2 = v13[0];
    }
    if ( v18 )
    {
      if ( (unsigned int)Windows::Internal::CapabilityAccess::Private::GetPackageOriginFromFullName((__int64)&v17, v11) == 2 )
      {
        LODWORD(v12) = 2;
        v8 = (__int64 *)&v16;
      }
      else
      {
        LODWORD(v12) = 3;
        v8 = (__int64 *)v20;
      }
    }
    else
    {
      LODWORD(v12) = 1;
      v8 = &v15;
    }
    v13[0] = v2;
    v13[1] = v3;
    v6 = *(_DWORD *)(*(_QWORD *)std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,std::wstring>,enum Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification,std::less<std::tuple<std::wstring,std::wstring>>,std::allocator<std::pair<std::tuple<std::wstring,std::wstring> const,enum Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>>,0>>::emplace<std::tuple<std::wstring const &,std::wstring const &>,enum Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>(
                                  (__int64)v9,
                                  (__int64)v8,
                                  v13,
                                  (unsigned int *)&v12)
                   + 96LL);
    std::wstring::_Tidy_deallocate(&v17);
  }
  else
  {
    v6 = *(_DWORD *)(v12 + 96);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  return v6;
}

```

## disassembly

```asm
0x18002e5e4  mov     [rsp+arg_10], rbx
0x18002e5e9  mov     [rsp+arg_18], rsi
0x18002e5ee  push    rdi
0x18002e5ef  sub     rsp, 0D0h
0x18002e5f6  mov     rax, cs:__security_cookie
0x18002e5fd  xor     rax, rsp
0x18002e600  mov     [rsp+0D8h+var_18], rax
0x18002e608  mov     rsi, rdx
0x18002e60b  mov     rdi, rcx
0x18002e60e  mov     [rsp+0D8h+var_98], rcx
0x18002e613  mov     [rsp+0D8h+var_B0], rdx
0x18002e618  lea     rbx, ?m_packageFamilyNamePackageComplianceClassificationMapLock@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::m_packageFamilyNamePackageComplianceClassificationMapLock
0x18002e61f  mov     rcx, rbx; SRWLock
0x18002e622  call    cs:__imp_AcquireSRWLockExclusive
0x18002e628  mov     [rsp+0D8h+var_A0], rbx
0x18002e62d  mov     r9, rsi
0x18002e630  mov     r8, rdi
0x18002e633  lea     rcx, [rsp+0D8h+var_58]
0x18002e63b  call    ??$?0U_Exact_args_t@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@$0A@@?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@U_Exact_args_t@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@1@Z; std::tuple<std::wstring,std::wstring>::tuple<std::wstring,std::wstring>(std::_Exact_args_t,std::wstring const &,std::wstring const &)
0x18002e640  lea     r8, [rsp+0D8h+var_58]
0x18002e648  lea     rdx, [rsp+0D8h+var_B8]
0x18002e64d  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@2@AEBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,std::wstring>,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification,std::less<std::tuple<std::wstring,std::wstring>>,std::allocator<std::pair<std::tuple<std::wstring,std::wstring> const,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>>,0>>::find(std::tuple<std::wstring,std::wstring> const &)
0x18002e652  lea     rcx, [rsp+0D8h+var_58]
0x18002e65a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18002e65f  mov     rax, [rsp+0D8h+var_B8]
0x18002e664  cmp     rax, cs:?m_packageFamilyNamePackageComplianceClassificationCache@PackageDataCache@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$map@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@std@@@2@@std@@A; std::map<std::tuple<std::wstring,std::wstring>,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification> Windows::Internal::CapabilityAccess::Private::Globals::PackageDataCache::m_packageFamilyNamePackageComplianceClassificationCache
0x18002e66b  jz      short loc_18002E675
0x18002e66d  mov     ebx, [rax+60h]
0x18002e670  jmp     loc_18002E738
0x18002e675  xorps   xmm0, xmm0
0x18002e678  movups  [rsp+0D8h+var_78], xmm0
0x18002e67d  xor     ebx, ebx
0x18002e67f  mov     [rsp+0D8h+var_68], rbx
0x18002e684  mov     [rsp+0D8h+var_60], 7
0x18002e68d  mov     word ptr [rsp+0D8h+var_78], bx
0x18002e692  mov     r8, rdi
0x18002e695  mov     rdx, rsi
0x18002e698  lea     rcx, [rsp+0D8h+var_58]
0x18002e6a0  call    ?GetPackageFullNameFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFullNameFromFamilyNameAndUser(std::wstring const &,std::wstring const &)
0x18002e6a5  mov     rdx, rax
0x18002e6a8  lea     rcx, [rsp+0D8h+var_78]
0x18002e6ad  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002e6b2  lea     rcx, [rsp+0D8h+var_58]
0x18002e6ba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6bf  nop
0x18002e6c0  jmp     short loc_18002E6CE
0x18002e6c2  xor     ebx, ebx
0x18002e6c4  mov     rdi, [rsp+0D8h+var_98]
0x18002e6c9  mov     rsi, [rsp+0D8h+var_B0]
0x18002e6ce  cmp     [rsp+0D8h+var_68], rbx
0x18002e6d3  jnz     short loc_18002E6E4
0x18002e6d5  mov     dword ptr [rsp+0D8h+var_B8], 1
0x18002e6dd  lea     rdx, [rsp+0D8h+var_98]
0x18002e6e2  jmp     short loc_18002E70E
0x18002e6e4  lea     rcx, [rsp+0D8h+var_78]
0x18002e6e9  call    ?GetPackageOriginFromFullName@Private@CapabilityAccess@Internal@Windows@@YA?AW4PackageOrigin@StateRepository@34@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageOriginFromFullName(std::wstring const &)
0x18002e6ee  cmp     eax, 2
0x18002e6f1  jnz     short loc_18002E6FE
0x18002e6f3  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18002e6f7  lea     rdx, [rsp+0D8h+var_88]
0x18002e6fc  jmp     short loc_18002E70E
0x18002e6fe  mov     dword ptr [rsp+0D8h+var_B8], 3
0x18002e706  lea     rdx, [rsp+0D8h+var_58]
0x18002e70e  mov     [rsp+0D8h+var_B0], rsi
0x18002e713  mov     [rsp+0D8h+var_A8], rdi
0x18002e718  lea     r9, [rsp+0D8h+var_B8]
0x18002e71d  lea     r8, [rsp+0D8h+var_B0]
0x18002e722  call    ??$emplace@V?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@U?$less@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@W4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$tuple@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@1@$$QEAW4PackageComplianceClassification@Private@CapabilityAccess@Internal@Windows@@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::wstring,std::wstring>,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification,std::less<std::tuple<std::wstring,std::wstring>>,std::allocator<std::pair<std::tuple<std::wstring,std::wstring> const,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>>,0>>::emplace<std::tuple<std::wstring const &,std::wstring const &>,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification>(std::tuple<std::wstring const &,std::wstring const &> &&,Windows::Internal::CapabilityAccess::Private::PackageComplianceClassification &&)
0x18002e727  mov     rcx, [rax]
0x18002e72a  mov     ebx, [rcx+60h]
0x18002e72d  lea     rcx, [rsp+0D8h+var_78]
0x18002e732  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e737  nop
0x18002e738  lea     rcx, [rsp+0D8h+var_A0]
0x18002e73d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e742  mov     eax, ebx
0x18002e744  mov     rcx, [rsp+0D8h+var_18]
0x18002e74c  xor     rcx, rsp; StackCookie
0x18002e74f  call    __security_check_cookie
0x18002e754  lea     r11, [rsp+0D8h+var_8]
0x18002e75c  mov     rbx, [r11+20h]
0x18002e760  mov     rsi, [r11+28h]
0x18002e764  mov     rsp, r11
0x18002e767  pop     rdi
0x18002e768  retn
```
