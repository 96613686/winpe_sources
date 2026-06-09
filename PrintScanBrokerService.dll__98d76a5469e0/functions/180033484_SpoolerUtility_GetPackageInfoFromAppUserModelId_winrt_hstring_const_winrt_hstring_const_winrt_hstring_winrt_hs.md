# SpoolerUtility::GetPackageInfoFromAppUserModelId(winrt::hstring const &,winrt::hstring const &,winrt::hstring &,winrt::hstring &,unsigned __int64 &)

- ea: `0x180033484`
- end: `0x18003388d`
- name: `?GetPackageInfoFromAppUserModelId@SpoolerUtility@@SAXAEBUhstring@winrt@@0AEAU23@1AEA_K@Z`
- size: `1033`
- prototype: `void __fastcall(const struct winrt::hstring *, const struct winrt::hstring *, struct winrt::hstring *, __int64 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000a9a0`

## callees

- `0x180002d40`
- `0x18000792c`
- `0x180007a58`
- `0x18000f8a8`
- `0x18000f9e4`
- `0x18000fa2c`
- `0x18000fa48`
- `0x18000fb60`
- `0x1800115c4`
- `0x180012498`
- `0x180012ef4`
- `0x18001cfb4`
- `0x18001d058`
- `0x18002a0e8`
- `0x180032f74`
- `0x1800331e4`
- `0x180033484`
- `0x180033894`
- `0x180048010`

## import_xrefs

- `combase!__imp_RoGetActivationFactoryAsUser` at `0x180033543`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18003359b`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x180033543`
- `combase!__imp_RoGetActivationFactoryAsUser` at `0x18003359b`

## string_xrefs

- `0x1800334f9`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`
- `0x18003386a`: `onecoreuap\printscan\print\printscanbroker\class\spoolerutility.cpp`

## pseudocode

```c
void __fastcall SpoolerUtility::GetPackageInfoFromAppUserModelId(
        const struct winrt::hstring *a1,
        const struct winrt::hstring *a2,
        struct winrt::hstring *a3,
        __int64 **a4,
        unsigned __int64 *a5)
{
  const unsigned __int16 *v8; // rax
  unsigned int UserContext; // eax
  __int64 v10; // rbx
  _QWORD *v11; // rax
  unsigned int ActivationFactoryAsUser; // eax
  _QWORD *v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // eax
  struct IUnknown *v18; // rdx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, void **); // rbx
  void **v21; // rax
  int v22; // eax
  unsigned int v23; // eax
  __int64 *v24; // rbx
  struct winrt::hstring *v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // [rsp+20h] [rbp-A1h]
  const char *v30; // [rsp+28h] [rbp-99h]
  const char *v31; // [rsp+28h] [rbp-99h]
  const char *v32; // [rsp+28h] [rbp-99h]
  char v33[8]; // [rsp+30h] [rbp-91h] BYREF
  __int64 v34; // [rsp+38h] [rbp-89h] BYREF
  __int64 v35; // [rsp+40h] [rbp-81h] BYREF
  __int64 *v36; // [rsp+48h] [rbp-79h] BYREF
  __int128 v37; // [rsp+50h] [rbp-71h]
  __int64 v38; // [rsp+60h] [rbp-61h] BYREF
  __int64 v39; // [rsp+68h] [rbp-59h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, __int64 *, __int64 *); // [rsp+70h] [rbp-51h] BYREF
  __int64 *v41; // [rsp+78h] [rbp-49h] BYREF
  __int64 v42; // [rsp+80h] [rbp-41h] BYREF
  __int64 *v43; // [rsp+88h] [rbp-39h] BYREF
  __int64 v44; // [rsp+90h] [rbp-31h] BYREF
  int v45; // [rsp+B0h] [rbp-11h] BYREF
  __int128 v46; // [rsp+B8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  v34 = 0;
  v8 = winrt::hstring::c_str(a2);
  std::wstring::wstring(&v45, v8);
  UserContext = PrintCore::UserContextHelpers::GetUserContext(&v45, &v34);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x121,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)UserContext,
    (int)"Failed to get user context for requesting credentials!",
    v30);
  std::wstring::_Tidy_deallocate(&v45);
  v40 = 0;
  v10 = v34;
  v11 = (_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v35, L"Windows.System.Internal.UserManager");
  ActivationFactoryAsUser = RoGetActivationFactoryAsUser(*v11, v10, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v40);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x127,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)ActivationFactoryAsUser,
    (int)"Failed to get user manager statics from user context!",
    v31);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v35);
  v39 = 0;
  v13 = (_QWORD *)winrt::hstring::hstring((winrt::hstring *)&v35, L"Windows.Internal.StateRepository.User");
  v14 = RoGetActivationFactoryAsUser(*v13, v10, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v39);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
    (const char *)v14,
    (int)"Failed to get user statics from user context!",
    v32);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v35);
  v35 = 0;
  if ( v40 )
  {
    v34 = 0;
    LODWORD(v36) = 0;
    v37 = 0;
    v16 = (**v40)(v40, winrt::impl::guid_v<Windows::System::Internal::ISignInStateManager>, &v34);
    winrt::check_hresult(v33, v16, &v36);
    v15 = v34;
  }
  else
  {
    v15 = 0;
  }
  v35 = v15;
  v38 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 160LL))(v15, v10, &v38);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x133,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
      (const char *)(unsigned int)v17,
      v29);
  v42 = 0;
  v19 = v39;
  v20 = *(__int64 (__fastcall **)(__int64, __int64, void **))(*(_QWORD *)v39 + 168LL);
  v21 = winrt::put_abi((winrt *)&v42, v18);
  v22 = v20(v19, v38, v21);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\spoolerutility.cpp",
      (const char *)(unsigned int)v22,
      v29);
  v44 = *(_QWORD *)a1;
  v36 = &v42;
  *(_QWORD *)&v37 = &v44;
  v43 = &qword_180060DE8;
  _InterlockedIncrement64(&qword_180060DE8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> )
  {
    _lambda_63d16e4a858412ce07219fb242b8ce36_::operator()(
      &v36,
      &v34,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>);
    _InterlockedDecrement64(&qword_180060DE8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180060DE8);
    winrt::impl::factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>::call<_lambda_63d16e4a858412ce07219fb242b8ce36_ &>(
      retaddr,
      &v34,
      &v36);
  }
  v36 = 0;
  v45 = 0;
  v46 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v34 + 72LL))(v34, &v36);
  winrt::check_hresult(v33, v23, &v45);
  v24 = v36;
  v43 = v36;
  v25 = (struct winrt::hstring *)winrt::impl::consume_Windows_Internal_StateRepository_IPackage<winrt::Windows::Internal::StateRepository::IPackage>::PackageFullName(
                                   &v43,
                                   &v36);
  if ( a3 != v25 )
  {
    v26 = *(_QWORD *)v25;
    *(_QWORD *)v25 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(a3, v26);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v36);
  v36 = 0;
  v45 = 0;
  v46 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v24 + 920))(v24, &v36);
  winrt::check_hresult(v33, v27, &v45);
  v41 = v36;
  if ( a4 != &v41 )
  {
    v41 = 0;
    winrt::handle_type<winrt::impl::hstring_traits>::attach(a4, v36);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v41);
  v36 = 0;
  v45 = 0;
  v46 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v24 + 104))(v24, &v36);
  winrt::check_hresult(v33, v28, &v45);
  *a5 = (unsigned __int64)v36;
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v43);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v34);
  winrt::Windows::Internal::StateRepository::IApplication::~IApplication((winrt::Windows::Internal::StateRepository::IApplication *)&v42);
  if ( v38 )
    winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(&v38);
  winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(&v35);
  if ( v39 )
    winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(&v39);
  if ( v40 )
    winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(&v40);
}

```

## disassembly

```asm
0x180033484  mov     [rsp-8+arg_0], rbx
0x180033489  push    rbp
0x18003348a  push    rsi
0x18003348b  push    rdi
0x18003348c  push    r12
0x18003348e  push    r13
0x180033490  push    r14
0x180033492  push    r15
0x180033494  lea     rbp, [rsp-1Fh]
0x180033499  sub     rsp, 0E0h
0x1800334a0  mov     rax, cs:__security_cookie
0x1800334a7  xor     rax, rsp
0x1800334aa  mov     [rbp+4Fh+var_40], rax
0x1800334ae  mov     rsi, r9
0x1800334b1  mov     r14, r8
0x1800334b4  mov     r15, rcx
0x1800334b7  mov     r12, [rbp+4Fh+arg_20]
0x1800334bb  xor     r13d, r13d
0x1800334be  mov     [rsp+110h+var_D8], r13
0x1800334c3  mov     rcx, rdx; this
0x1800334c6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800334cb  mov     rdx, rax
0x1800334ce  lea     rcx, [rbp+4Fh+var_60]
0x1800334d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800334d7  nop
0x1800334d8  lea     rdx, [rsp+110h+var_D8]
0x1800334dd  lea     rcx, [rbp+4Fh+var_60]
0x1800334e1  call    ?GetUserContext@UserContextHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_K@Z; PrintCore::UserContextHelpers::GetUserContext(std::wstring const &,unsigned __int64 *)
0x1800334e6  mov     rcx, [rbp+57h]; this
0x1800334ea  lea     rdx, aFailedToGetUse_2; "Failed to get user context for requesti"...
0x1800334f1  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x1800334f6  mov     r9d, eax; char *
0x1800334f9  lea     rdi, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033500  mov     r8, rdi; unsigned int
0x180033503  mov     edx, 121h; void *
0x180033508  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003350d  nop
0x18003350e  lea     rcx, [rbp+4Fh+var_60]
0x180033512  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180033517  mov     [rbp+4Fh+var_A0], r13
0x18003351b  mov     rbx, [rsp+110h+var_D8]
0x180033520  lea     rdx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x180033527  lea     rcx, [rsp+110h+var_D0]; this
0x18003352c  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180033531  nop
0x180033532  lea     r9, [rbp+4Fh+var_A0]
0x180033536  lea     r8, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18003353d  mov     rdx, rbx
0x180033540  mov     rcx, [rax]
0x180033543  call    cs:__imp_RoGetActivationFactoryAsUser
0x180033549  mov     rcx, [rbp+57h]; this
0x18003354d  lea     rdx, aFailedToGetUse; "Failed to get user manager statics from"...
0x180033554  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x180033559  mov     r9d, eax; char *
0x18003355c  mov     r8, rdi; unsigned int
0x18003355f  mov     edx, 127h; void *
0x180033564  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033569  nop
0x18003356a  lea     rcx, [rsp+110h+var_D0]
0x18003356f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033574  mov     [rbp+4Fh+var_A8], r13
0x180033578  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x18003357f  lea     rcx, [rsp+110h+var_D0]; this
0x180033584  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180033589  nop
0x18003358a  lea     r9, [rbp+4Fh+var_A8]
0x18003358e  lea     r8, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x180033595  mov     rdx, rbx
0x180033598  mov     rcx, [rax]
0x18003359b  call    cs:__imp_RoGetActivationFactoryAsUser
0x1800335a1  mov     rcx, [rbp+57h]; this
0x1800335a5  lea     rdx, aFailedToGetUse_0; "Failed to get user statics from user co"...
0x1800335ac  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x1800335b1  mov     r9d, eax; char *
0x1800335b4  mov     r8, rdi; unsigned int
0x1800335b7  mov     edx, 12Dh; void *
0x1800335bc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800335c1  nop
0x1800335c2  lea     rcx, [rsp+110h+var_D0]
0x1800335c7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800335cc  mov     [rsp+110h+var_D0], r13
0x1800335d1  mov     rcx, [rbp+4Fh+var_A0]
0x1800335d5  test    rcx, rcx
0x1800335d8  jnz     short loc_1800335DF
0x1800335da  mov     ecx, r13d
0x1800335dd  jmp     short loc_18003361C
0x1800335df  mov     [rsp+110h+var_D8], r13
0x1800335e4  mov     dword ptr [rbp+4Fh+var_C8], r13d
0x1800335e8  xorps   xmm0, xmm0
0x1800335eb  movdqu  [rbp+4Fh+var_C0], xmm0
0x1800335f0  mov     rax, [rcx]
0x1800335f3  lea     r8, [rsp+110h+var_D8]
0x1800335f8  lea     rdx, ??$guid_v@UISignInStateManager@Internal@System@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::System::Internal::ISignInStateManager>
0x1800335ff  mov     rax, [rax]
0x180033602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033607  lea     r8, [rbp+4Fh+var_C8]
0x18003360b  mov     edx, eax
0x18003360d  lea     rcx, [rsp+110h+var_E0]
0x180033612  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180033617  mov     rcx, [rsp+110h+var_D8]
0x18003361c  mov     [rsp+110h+var_D0], rcx
0x180033621  mov     [rbp+4Fh+var_B0], r13
0x180033625  mov     rax, [rcx]
0x180033628  lea     r8, [rbp+4Fh+var_B0]
0x18003362c  mov     rdx, rbx
0x18003362f  mov     rax, [rax+0A0h]
0x180033636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003363b  mov     rcx, [rbp+57h]; this
0x18003363f  test    eax, eax
0x180033641  js      loc_18003387C
0x180033647  mov     [rbp+4Fh+var_90], r13
0x18003364b  mov     rdi, [rbp+4Fh+var_A8]
0x18003364f  mov     rax, [rdi]
0x180033652  mov     rbx, [rax+0A8h]
0x180033659  lea     rcx, [rbp+4Fh+var_90]; this
0x18003365d  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x180033662  mov     r8, rax
0x180033665  mov     rdx, [rbp+4Fh+var_B0]
0x180033669  mov     rcx, rdi
0x18003366c  mov     rax, rbx
0x18003366f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033674  mov     rcx, [rbp+57h]; this
0x180033678  test    eax, eax
0x18003367a  js      loc_180033867
0x180033680  mov     rax, [r15]
0x180033683  mov     [rbp+4Fh+var_80], rax
0x180033687  lea     rax, [rbp+4Fh+var_90]
0x18003368b  mov     [rbp+4Fh+var_C8], rax
0x18003368f  lea     rax, [rbp+4Fh+var_80]
0x180033693  mov     qword ptr [rbp+4Fh+var_C0], rax
0x180033697  lea     rax, qword_180060DE8
0x18003369e  mov     [rbp+4Fh+var_88], rax
0x1800336a2  lock inc cs:qword_180060DE8
0x1800336aa  cmp     cs:??$factory_cache_entry_v@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@12@A, r13; factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>
0x1800336b1  jz      short loc_1800336D3
0x1800336b3  lea     r8, ??$factory_cache_entry_v@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>
0x1800336ba  lea     rdx, [rsp+110h+var_D8]
0x1800336bf  lea     rcx, [rbp+4Fh+var_C8]
0x1800336c3  call    ??R_lambda_63d16e4a858412ce07219fb242b8ce36_@@QEBA@AEBUIApplicationStatics@StateRepository@Internal@Windows@winrt@@@Z; _lambda_63d16e4a858412ce07219fb242b8ce36_::operator()(winrt::Windows::Internal::StateRepository::IApplicationStatics const &)
0x1800336c8  nop
0x1800336c9  lock dec cs:qword_180060DE8
0x1800336d1  jmp     short loc_1800336EA
0x1800336d3  lock dec cs:qword_180060DE8
0x1800336db  lea     r8, [rbp+4Fh+var_C8]
0x1800336df  lea     rdx, [rsp+110h+var_D8]
0x1800336e4  call    ??$call@AEAV_lambda_63d16e4a858412ce07219fb242b8ce36_@@@?$factory_cache_entry@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_63d16e4a858412ce07219fb242b8ce36_@@@Z
0x1800336e9  nop
0x1800336ea  mov     [rbp+4Fh+var_C8], r13
0x1800336ee  mov     rcx, [rsp+110h+var_D8]
0x1800336f3  mov     [rbp+4Fh+var_60], r13d
0x1800336f7  xorps   xmm0, xmm0
0x1800336fa  movdqu  [rbp+4Fh+var_58], xmm0
0x1800336ff  mov     rax, [rcx]
0x180033702  lea     rdx, [rbp+4Fh+var_C8]
0x180033706  mov     rax, [rax+48h]
0x18003370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003370f  lea     r8, [rbp+4Fh+var_60]
0x180033713  mov     edx, eax
0x180033715  lea     rcx, [rsp+110h+var_E0]
0x18003371a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003371f  mov     rbx, [rbp+4Fh+var_C8]
0x180033723  mov     [rbp+4Fh+var_88], rbx
0x180033727  lea     rdx, [rbp+4Fh+var_C8]
0x18003372b  lea     rcx, [rbp+4Fh+var_88]
0x18003372f  call    ?PackageFullName@?$consume_Windows_Internal_StateRepository_IPackage@UIPackage@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_StateRepository_IPackage<winrt::Windows::Internal::StateRepository::IPackage>::PackageFullName(void)
0x180033734  cmp     r14, rax
0x180033737  jz      short loc_180033747
0x180033739  mov     rdx, [rax]
0x18003373c  mov     [rax], r13
0x18003373f  mov     rcx, r14
0x180033742  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x180033747  lea     rcx, [rbp+4Fh+var_C8]
0x18003374b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033750  mov     [rbp+4Fh+var_C8], r13
0x180033754  mov     [rbp+4Fh+var_60], r13d
0x180033758  xorps   xmm0, xmm0
0x18003375b  movdqu  [rbp+4Fh+var_58], xmm0
0x180033760  mov     rax, [rbx]
0x180033763  lea     rdx, [rbp+4Fh+var_C8]
0x180033767  mov     rcx, rbx
0x18003376a  mov     rax, [rax+398h]
0x180033771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033776  lea     r8, [rbp+4Fh+var_60]
0x18003377a  mov     edx, eax
0x18003377c  lea     rcx, [rsp+110h+var_E0]
0x180033781  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180033786  mov     rdx, [rbp+4Fh+var_C8]
0x18003378a  mov     [rbp+4Fh+var_98], rdx
0x18003378e  lea     rax, [rbp+4Fh+var_98]
0x180033792  cmp     rsi, rax
0x180033795  jz      short loc_1800337A3
0x180033797  mov     [rbp+4Fh+var_98], r13
0x18003379b  mov     rcx, rsi
0x18003379e  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1800337a3  lea     rcx, [rbp+4Fh+var_98]
0x1800337a7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800337ac  mov     [rbp+4Fh+var_C8], r13
0x1800337b0  mov     [rbp+4Fh+var_60], r13d
0x1800337b4  xorps   xmm0, xmm0
0x1800337b7  movdqu  [rbp+4Fh+var_58], xmm0
0x1800337bc  mov     rax, [rbx]
0x1800337bf  lea     rdx, [rbp+4Fh+var_C8]
0x1800337c3  mov     rcx, rbx
0x1800337c6  mov     rax, [rax+68h]
0x1800337ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337cf  lea     r8, [rbp+4Fh+var_60]
0x1800337d3  mov     edx, eax
0x1800337d5  lea     rcx, [rsp+110h+var_E0]
0x1800337da  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800337df  mov     rax, [rbp+4Fh+var_C8]
0x1800337e3  mov     [r12], rax
0x1800337e7  lea     rcx, [rbp+4Fh+var_88]; this
0x1800337eb  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800337f0  nop
0x1800337f1  lea     rcx, [rsp+110h+var_D8]; this
0x1800337f6  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x1800337fb  nop
0x1800337fc  lea     rcx, [rbp+4Fh+var_90]; this
0x180033800  call    ??1IApplication@StateRepository@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::StateRepository::IApplication::~IApplication(void)
0x180033805  nop
0x180033806  cmp     [rbp+4Fh+var_B0], r13
0x18003380a  jz      short loc_180033816
0x18003380c  lea     rcx, [rbp+4Fh+var_B0]
0x180033810  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180033815  nop
0x180033816  lea     rcx, [rsp+110h+var_D0]
0x18003381b  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180033820  nop
0x180033821  cmp     [rbp+4Fh+var_A8], r13
0x180033825  jz      short loc_180033831
0x180033827  lea     rcx, [rbp+4Fh+var_A8]
0x18003382b  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180033830  nop
0x180033831  cmp     [rbp+4Fh+var_A0], r13
0x180033835  jz      short loc_180033840
0x180033837  lea     rcx, [rbp+4Fh+var_A0]
0x18003383b  call    ?unconditional_release_ref@?$com_ptr@UIUserManagerStatics@Internal@System@Windows@@@winrt@@AEAAXXZ; winrt::com_ptr<Windows::System::Internal::IUserManagerStatics>::unconditional_release_ref(void)
0x180033840  mov     rcx, [rbp+4Fh+var_40]
0x180033844  xor     rcx, rsp; StackCookie
0x180033847  call    __security_check_cookie
0x18003384c  mov     rbx, [rsp+110h+arg_0]
0x180033854  add     rsp, 0E0h
0x18003385b  pop     r15
0x18003385d  pop     r14
0x18003385f  pop     r13
0x180033861  pop     r12
0x180033863  pop     rdi
0x180033864  pop     rsi
0x180033865  pop     rbp
0x180033866  retn
0x180033867  mov     r9d, eax; char *
0x18003386a  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\printscan"...
0x180033871  mov     edx, 136h; void *
0x180033876  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003387c  mov     r9d, eax; char *
0x18003387f  mov     r8, rdi; unsigned int
0x180033882  mov     edx, 133h; void *
0x180033887  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
