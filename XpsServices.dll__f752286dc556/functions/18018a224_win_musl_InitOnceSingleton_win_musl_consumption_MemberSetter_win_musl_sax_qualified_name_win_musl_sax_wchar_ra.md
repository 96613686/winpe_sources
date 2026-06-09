# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTargets>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTargets>)

- ea: `0x18018a224`
- end: `0x18018a3e4`
- name: `??$Get@V?$SingletonInitializer@VLinkTargets@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTargets@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VLinkTargets@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18018dfc0`

## callees

- `0x180012450`
- `0x1800ad884`
- `0x180115e70`
- `0x180118898`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x18018a224`
- `0x18018c704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18018a349`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18018a349`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18018a26b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18018a26b`

## string_xrefs

- `0x18018a3a2`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTargets>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTargets>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::store'::`2'::s_storage,
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
0x18018a224  mov     [rsp-8+arg_0], rdi
0x18018a229  push    rbp
0x18018a22a  lea     rbp, [rsp-20h]
0x18018a22f  sub     rsp, 120h
0x18018a236  mov     rax, cs:__security_cookie
0x18018a23d  xor     rax, rsp
0x18018a240  mov     [rbp+20h+var_10], rax
0x18018a244  mov     [rsp+120h+fPending], 0
0x18018a24c  mov     [rsp+120h+Context], 0
0x18018a255  lea     r9, [rsp+120h+Context]; lpContext
0x18018a25a  lea     r8, [rsp+120h+fPending]; fPending
0x18018a25f  xor     edx, edx; dwFlags
0x18018a261  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTargets@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTargets>>::store(void)'::`2'::s_storage
0x18018a268  mov     rcx, rdi; lpInitOnce
0x18018a26b  call    cs:__imp_InitOnceBeginInitialize
0x18018a271  test    eax, eax
0x18018a273  jnz     short loc_18018A2BC
0x18018a275  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18018a27a  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18018a281  mov     [rsp+120h+var_F0], rcx; __int64
0x18018a286  mov     [rsp+120h+var_F8], eax; int
0x18018a28a  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18018a292  lea     r9, Src
0x18018a299  lea     r8, aNoFilename; "(no filename)"
0x18018a2a0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18018a2a5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18018a2aa  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18018a2b1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18018a2b6  call    _CxxThrowException_0
0x18018a2bc  cmp     [rsp+120h+fPending], 0
0x18018a2c1  jz      loc_18018A37A
0x18018a2c7  mov     [rsp+120h+var_C8], rdi
0x18018a2cc  mov     [rsp+120h+var_C0], 0
0x18018a2d4  lea     rdx, [rsp+120h+var_D0]
0x18018a2d9  call    ??R?$SingletonInitializer@VLinkTargets@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTargets>::operator()(void)
0x18018a2de  nop
0x18018a2df  mov     rax, [rsp+120h+var_D0]
0x18018a2e4  mov     [rsp+120h+Context], rax
0x18018a2e9  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTargets@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18018a2f0  call    atexit
0x18018a2f5  test    eax, eax
0x18018a2f7  jz      short loc_18018A33F
0x18018a2f9  lea     rax, aAtexitFailed; "atexit() failed"
0x18018a300  mov     [rsp+120h+var_F0], rax; __int64
0x18018a305  mov     [rsp+120h+var_F8], 8007000Eh; int
0x18018a30d  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18018a315  lea     r9, Src
0x18018a31c  lea     r8, aNoFilename; "(no filename)"
0x18018a323  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18018a328  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18018a32d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18018a334  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18018a339  call    _CxxThrowException_0
0x18018a33f  mov     r8, [rsp+120h+Context]; lpContext
0x18018a344  xor     edx, edx; dwFlags
0x18018a346  mov     rcx, rdi; lpInitOnce
0x18018a349  call    cs:__imp_InitOnceComplete
0x18018a34f  test    eax, eax
0x18018a351  jz      short loc_18018A39C
0x18018a353  mov     [rsp+120h+var_D0], 0
0x18018a35c  mov     [rsp+120h+var_C8], 0
0x18018a365  lea     rcx, [rsp+120h+var_D0]
0x18018a36a  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x18018a36f  nop
0x18018a370  lea     rcx, [rsp+120h+var_C8]; this
0x18018a375  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18018a37a  mov     rax, [rsp+120h+Context]
0x18018a37f  mov     rcx, [rbp+20h+var_10]
0x18018a383  xor     rcx, rsp; StackCookie
0x18018a386  call    __security_check_cookie
0x18018a38b  mov     rdi, [rsp+120h+arg_0]
0x18018a393  add     rsp, 120h
0x18018a39a  pop     rbp
0x18018a39b  retn
0x18018a39c  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18018a3a1  nop
0x18018a3a2  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18018a3a9  mov     [rsp+120h+var_F0], rcx; __int64
0x18018a3ae  mov     [rsp+120h+var_F8], eax; int
0x18018a3b2  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18018a3ba  lea     r9, Src
0x18018a3c1  lea     r8, aNoFilename; "(no filename)"
0x18018a3c8  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18018a3cd  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18018a3d2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18018a3d9  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18018a3de  call    _CxxThrowException_0
```
