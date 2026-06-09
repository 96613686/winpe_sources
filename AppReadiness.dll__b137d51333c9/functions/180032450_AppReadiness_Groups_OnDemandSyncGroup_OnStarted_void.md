# AppReadiness::Groups::OnDemandSyncGroup::OnStarted(void)

- ea: `0x180032450`
- end: `0x1800325ac`
- name: `?OnStarted@OnDemandSyncGroup@Groups@AppReadiness@@MEAAXXZ`
- size: `348`
- prototype: `void __fastcall __noreturn(AppReadiness::Groups::OnDemandSyncGroup *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002958`
- `0x18000e4a0`
- `0x18001870c`
- `0x1800236a4`
- `0x18002910c`
- `0x180029b1c`
- `0x18002a500`
- `0x180032450`
- `0x1800325b4`
- `0x1800327fc`
- `0x18003293c`
- `0x1800399b8`
- `0x18003e210`
- `0x180049310`
- `0x180059fb4`
- `0x18006391c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032588`

## string_xrefs

- `0x1800324ca`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall __noreturn AppReadiness::Groups::OnDemandSyncGroup::OnStarted(
        AppReadiness::Groups::OnDemandSyncGroup *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rax
  const WCHAR *DefaultAccountSid; // rax
  AppReadiness::User *v7; // rax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  HSTRING v9; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v10[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v2 = (char *)this + 320;
  tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::start(
    (char *)this + 320,
    v10);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(
                           v2,
                           v10)
            + 288LL) = 5;
  tip2::test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::~test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>(v10);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 344);
  v4 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
         v3,
         (_QWORD *)this + 43);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  AppReadiness::Groups::OnDemandSyncGroup::RemoveRegionExcludedPackages((AppReadiness::Groups::OnDemandSyncGroup *)((char *)this - 8));
  v5 = (*(__int64 (__fastcall **)(AppReadiness::Groups::OnDemandSyncGroup *))(*(_QWORD *)this + 112LL))(this);
  to_winstring(&v9, (PCNZWCH)(v5 + 64));
  DefaultAccountSid = (const WCHAR *)AppReadiness::User::GetDefaultAccountSid(v10);
  to_winstring(&string, DefaultAccountSid);
  std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(v10);
  v7 = (AppReadiness::User *)(*(__int64 (__fastcall **)(AppReadiness::Groups::OnDemandSyncGroup *))(*(_QWORD *)this
                                                                                                  + 112LL))(this);
  if ( AppReadiness::User::GetStateRepositoryUser(v7) )
    AppReadiness::Groups::OnDemandSyncGroup::SyncRemovedPackages(
      (AppReadiness::Groups::OnDemandSyncGroup *)((char *)this - 8),
      (struct Microsoft::WRL::Wrappers::HString *)&v9,
      (struct Microsoft::WRL::Wrappers::HString *)&string);
  AppReadiness::Groups::OnDemandSyncGroup::OnDemandSyncNewPackages(
    (AppReadiness::Groups::OnDemandSyncGroup *)((char *)this - 8),
    (struct Microsoft::WRL::Wrappers::HString *)&v9,
    (struct Microsoft::WRL::Wrappers::HString *)&string);
}

```

## disassembly

```asm
0x180032450  mov     [rsp-8+arg_8], rbx
0x180032455  mov     [rsp-8+arg_10], rdi
0x18003245a  push    rbp
0x18003245b  mov     rbp, rsp
0x18003245e  sub     rsp, 60h
0x180032462  mov     rax, cs:__security_cookie
0x180032469  xor     rax, rsp
0x18003246c  mov     [rbp+var_10], rax
0x180032470  mov     rdi, rcx
0x180032473  lea     rbx, [rcx+140h]
0x18003247a  lea     rdx, [rbp+var_30]
0x18003247e  mov     rcx, rbx
0x180032481  call    ?start@?$tip_test@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::start(void)
0x180032486  lea     rdx, [rbp+var_30]
0x18003248a  mov     rcx, rbx
0x18003248d  call    ??C?$tip_test@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::operator->(void)
0x180032492  mov     rcx, [rax]
0x180032495  mov     dword ptr [rcx+120h], 5
0x18003249f  lea     rcx, [rbp+var_30]
0x1800324a3  call    ??1?$test_data_control@V?$merged_data@U_tip_UserLogonTasksTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>::~test_data_control<tip2::details::merged_data<_tip_UserLogonTasksTest,_tip_UserLogonTasksTest>>(void)
0x1800324a8  lea     rbx, [rdi+158h]
0x1800324af  mov     rcx, rbx
0x1800324b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800324b7  mov     rdx, rbx
0x1800324ba  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1800324bf  mov     rcx, [rbp+8]; this
0x1800324c3  test    eax, eax
0x1800324c5  jns     short loc_1800324DC
0x1800324c7  mov     r9d, eax; char *
0x1800324ca  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800324d1  mov     edx, 88h; void *
0x1800324d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800324dc  lea     rbx, [rdi-8]
0x1800324e0  mov     rcx, rbx; this
0x1800324e3  call    ?RemoveRegionExcludedPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXXZ; AppReadiness::Groups::OnDemandSyncGroup::RemoveRegionExcludedPackages(void)
0x1800324e8  mov     rax, [rdi]
0x1800324eb  mov     rcx, rdi
0x1800324ee  mov     rax, [rax+70h]
0x1800324f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324f7  lea     rdx, [rax+40h]; sourceString
0x1800324fb  lea     rcx, [rbp+var_38]; string
0x1800324ff  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180032504  nop
0x180032505  lea     rcx, [rbp+var_30]
0x180032509  call    ?GetDefaultAccountSid@User@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; AppReadiness::User::GetDefaultAccountSid(void)
0x18003250e  nop
0x18003250f  mov     rdx, rax; sourceString
0x180032512  lea     rcx, [rbp+string]; string
0x180032516  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18003251b  nop
0x18003251c  lea     rcx, [rbp+var_30]
0x180032520  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180032525  mov     rax, [rdi]
0x180032528  mov     rcx, rdi
0x18003252b  mov     rax, [rax+70h]
0x18003252f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032534  mov     rcx, rax; this
0x180032537  call    ?GetStateRepositoryUser@User@AppReadiness@@QEAAPEAUIUser@StateRepository@Internal@Windows@@XZ; AppReadiness::User::GetStateRepositoryUser(void)
0x18003253c  test    rax, rax
0x18003253f  jz      short loc_180032551
0x180032541  lea     r8, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x180032545  lea     rdx, [rbp+var_38]; struct Microsoft::WRL::Wrappers::HString *
0x180032549  mov     rcx, rbx; this
0x18003254c  call    ?SyncRemovedPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXAEAVHString@Wrappers@WRL@Microsoft@@0@Z; AppReadiness::Groups::OnDemandSyncGroup::SyncRemovedPackages(Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::Wrappers::HString &)
0x180032551  lea     r8, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x180032555  lea     rdx, [rbp+var_38]; struct Microsoft::WRL::Wrappers::HString *
0x180032559  mov     rcx, rbx; this
0x18003255c  call    ?OnDemandSyncNewPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXAEAVHString@Wrappers@WRL@Microsoft@@0@Z; AppReadiness::Groups::OnDemandSyncGroup::OnDemandSyncNewPackages(Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::Wrappers::HString &)
0x180032561  lea     r8, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x180032565  lea     rdx, [rbp+var_38]; struct Microsoft::WRL::Wrappers::HString *
0x180032569  mov     rcx, rbx; this
0x18003256c  call    ?SyncFrameworkPackages@OnDemandSyncGroup@Groups@AppReadiness@@AEAAXAEAVHString@Wrappers@WRL@Microsoft@@0@Z; AppReadiness::Groups::OnDemandSyncGroup::SyncFrameworkPackages(Microsoft::WRL::Wrappers::HString &,Microsoft::WRL::Wrappers::HString &)
0x180032571  nop
0x180032572  mov     rcx, [rbp+string]; string
0x180032576  call    cs:__imp_WindowsDeleteString
0x18003257c  mov     [rbp+string], 0
0x180032584  mov     rcx, [rbp+var_38]; string
0x180032588  call    cs:__imp_WindowsDeleteString
0x18003258e  mov     rcx, [rbp+var_10]
0x180032592  xor     rcx, rsp; StackCookie
0x180032595  call    __security_check_cookie
0x18003259a  lea     r11, [rsp+60h+var_s0]
0x18003259f  mov     rbx, [r11+18h]
0x1800325a3  mov     rdi, [r11+20h]
0x1800325a7  mov     rsp, r11
0x1800325aa  pop     rbp
0x1800325ab  retn
```
