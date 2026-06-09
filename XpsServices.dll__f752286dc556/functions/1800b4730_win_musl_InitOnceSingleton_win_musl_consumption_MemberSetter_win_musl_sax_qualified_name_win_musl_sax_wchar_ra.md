# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DiscardControl>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DiscardControl>)

- ea: `0x1800b4730`
- end: `0x1800b48f0`
- name: `??$Get@V?$SingletonInitializer@VDiscardControl@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDiscardControl@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VDiscardControl@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180009e34`
- `0x180106fb8`

## callees

- `0x180012450`
- `0x1800ad884`
- `0x1800b4730`
- `0x180115e70`
- `0x180118898`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x1801939ec`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800b4855`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800b4855`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800b4777`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800b4777`

## string_xrefs

- `0x1800b48ae`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DiscardControl>>()
{
  win_musl::detail *v0; // rcx
  int LastErrorAsFailHR; // eax
  win_musl::detail *v2; // rcx
  int v4; // eax
  WINBOOL fPending; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+48h] [rbp-B8h] BYREF
  void *v7; // [rsp+50h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+58h] [rbp-A8h] BYREF
  int v9; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF

  fPending = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::store'::`2'::s_storage,
          0,
          &fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (__int64)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending )
  {
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DiscardControl>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v2);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1F5u,
        v4,
        (__int64)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    win_musl::unique_ptr<win_musl::MemberBindings<Z::sax::Uqualified_name::Z::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>'::`2'::PageBodyReceiverTraitsWithTypeList,win_dox::AXAEBVOpcPartUri,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder>,Z::sax::wchar_range> const>::~unique_ptr<win_musl::MemberBindings<Z::sax::Uqualified_name::Z::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>'::`2'::PageBodyReceiverTraitsWithTypeList,win_dox::AXAEBVOpcPartUri,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder>,Z::sax::wchar_range> const>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x1800b4730  mov     [rsp-8+arg_0], rdi
0x1800b4735  push    rbp
0x1800b4736  lea     rbp, [rsp-20h]
0x1800b473b  sub     rsp, 120h
0x1800b4742  mov     rax, cs:__security_cookie
0x1800b4749  xor     rax, rsp
0x1800b474c  mov     [rbp+20h+var_10], rax
0x1800b4750  mov     [rsp+120h+fPending], 0
0x1800b4758  mov     [rsp+120h+Context], 0
0x1800b4761  lea     r9, [rsp+120h+Context]; lpContext
0x1800b4766  lea     r8, [rsp+120h+fPending]; fPending
0x1800b476b  xor     edx, edx; dwFlags
0x1800b476d  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDiscardControl@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::DiscardControl>>::store(void)'::`2'::s_storage
0x1800b4774  mov     rcx, rdi; lpInitOnce
0x1800b4777  call    cs:__imp_InitOnceBeginInitialize
0x1800b477d  test    eax, eax
0x1800b477f  jnz     short loc_1800B47C8
0x1800b4781  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800b4786  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800b478d  mov     [rsp+120h+var_F0], rcx; __int64
0x1800b4792  mov     [rsp+120h+var_F8], eax; int
0x1800b4796  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800b479e  lea     r9, Src
0x1800b47a5  lea     r8, aNoFilename; "(no filename)"
0x1800b47ac  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800b47b1  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800b47b6  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800b47bd  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800b47c2  call    _CxxThrowException_0
0x1800b47c8  cmp     [rsp+120h+fPending], 0
0x1800b47cd  jz      loc_1800B4886
0x1800b47d3  mov     [rsp+120h+var_C8], rdi
0x1800b47d8  mov     [rsp+120h+var_C0], 0
0x1800b47e0  lea     rdx, [rsp+120h+var_D0]
0x1800b47e5  call    ??R?$SingletonInitializer@VDiscardControl@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::DiscardControl>::operator()(void)
0x1800b47ea  nop
0x1800b47eb  mov     rax, [rsp+120h+var_D0]
0x1800b47f0  mov     [rsp+120h+Context], rax
0x1800b47f5  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VDiscardControl@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800b47fc  call    atexit
0x1800b4801  test    eax, eax
0x1800b4803  jz      short loc_1800B484B
0x1800b4805  lea     rax, aAtexitFailed; "atexit() failed"
0x1800b480c  mov     [rsp+120h+var_F0], rax; __int64
0x1800b4811  mov     [rsp+120h+var_F8], 8007000Eh; int
0x1800b4819  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800b4821  lea     r9, Src
0x1800b4828  lea     r8, aNoFilename; "(no filename)"
0x1800b482f  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800b4834  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800b4839  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800b4840  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800b4845  call    _CxxThrowException_0
0x1800b484b  mov     r8, [rsp+120h+Context]; lpContext
0x1800b4850  xor     edx, edx; dwFlags
0x1800b4852  mov     rcx, rdi; lpInitOnce
0x1800b4855  call    cs:__imp_InitOnceComplete
0x1800b485b  test    eax, eax
0x1800b485d  jz      short loc_1800B48A8
0x1800b485f  mov     [rsp+120h+var_D0], 0
0x1800b4868  mov     [rsp+120h+var_C8], 0
0x1800b4871  lea     rcx, [rsp+120h+var_D0]
0x1800b4876  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x1800b487b  nop
0x1800b487c  lea     rcx, [rsp+120h+var_C8]; this
0x1800b4881  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800b4886  mov     rax, [rsp+120h+Context]
0x1800b488b  mov     rcx, [rbp+20h+var_10]
0x1800b488f  xor     rcx, rsp; StackCookie
0x1800b4892  call    __security_check_cookie
0x1800b4897  mov     rdi, [rsp+120h+arg_0]
0x1800b489f  add     rsp, 120h
0x1800b48a6  pop     rbp
0x1800b48a7  retn
0x1800b48a8  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800b48ad  nop
0x1800b48ae  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800b48b5  mov     [rsp+120h+var_F0], rcx; __int64
0x1800b48ba  mov     [rsp+120h+var_F8], eax; int
0x1800b48be  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800b48c6  lea     r9, Src
0x1800b48cd  lea     r8, aNoFilename; "(no filename)"
0x1800b48d4  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800b48d9  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800b48de  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800b48e5  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800b48ea  call    _CxxThrowException_0
```
