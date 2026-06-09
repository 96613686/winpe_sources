# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::PageContent>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::PageContent>)

- ea: `0x18009ebcc`
- end: `0x18009ed8c`
- name: `??$Get@V?$SingletonInitializer@VPageContent@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VPageContent@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VPageContent@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009eb10`

## callees

- `0x180012450`
- `0x18009ebcc`
- `0x1800ad884`
- `0x180115e70`
- `0x180118898`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x18018c7bc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009ed0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009ed0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009ec13`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009ec13`

## string_xrefs

- `0x18009ed4a`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::PageContent>>()
{
  win_musl::detail *v0; // rcx
  int LastErrorAsFailHR; // eax
  win_musl::detail *v3; // rcx
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::PageContent>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v3);
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
0x18009ebcc  mov     [rsp-8+arg_0], rdi
0x18009ebd1  push    rbp
0x18009ebd2  lea     rbp, [rsp-20h]
0x18009ebd7  sub     rsp, 120h
0x18009ebde  mov     rax, cs:__security_cookie
0x18009ebe5  xor     rax, rsp
0x18009ebe8  mov     [rbp+20h+var_10], rax
0x18009ebec  mov     [rsp+120h+fPending], 0
0x18009ebf4  mov     [rsp+120h+Context], 0
0x18009ebfd  lea     r9, [rsp+120h+Context]; lpContext
0x18009ec02  lea     r8, [rsp+120h+fPending]; fPending
0x18009ec07  xor     edx, edx; dwFlags
0x18009ec09  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VPageContent@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::PageContent>>::store(void)'::`2'::s_storage
0x18009ec10  mov     rcx, rdi; lpInitOnce
0x18009ec13  call    cs:__imp_InitOnceBeginInitialize
0x18009ec19  test    eax, eax
0x18009ec1b  jz      short loc_18009EC46
0x18009ec1d  cmp     [rsp+120h+fPending], 0
0x18009ec22  jnz     short loc_18009EC8D
0x18009ec24  mov     rax, [rsp+120h+Context]
0x18009ec29  mov     rcx, [rbp+20h+var_10]
0x18009ec2d  xor     rcx, rsp; StackCookie
0x18009ec30  call    __security_check_cookie
0x18009ec35  mov     rdi, [rsp+120h+arg_0]
0x18009ec3d  add     rsp, 120h
0x18009ec44  pop     rbp
0x18009ec45  retn
0x18009ec46  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18009ec4b  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18009ec52  mov     [rsp+120h+var_F0], rcx; __int64
0x18009ec57  mov     [rsp+120h+var_F8], eax; int
0x18009ec5b  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18009ec63  lea     r9, Src
0x18009ec6a  lea     r8, aNoFilename; "(no filename)"
0x18009ec71  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009ec76  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ec7b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ec82  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009ec87  call    _CxxThrowException_0
0x18009ec8d  mov     [rsp+120h+var_C8], rdi
0x18009ec92  mov     [rsp+120h+var_C0], 0
0x18009ec9a  lea     rdx, [rsp+120h+var_D0]
0x18009ec9f  call    ??R?$SingletonInitializer@VPageContent@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::PageContent>::operator()(void)
0x18009eca4  nop
0x18009eca5  mov     rax, [rsp+120h+var_D0]
0x18009ecaa  mov     [rsp+120h+Context], rax
0x18009ecaf  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VPageContent@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18009ecb6  call    atexit
0x18009ecbb  test    eax, eax
0x18009ecbd  jz      short loc_18009ED05
0x18009ecbf  lea     rax, aAtexitFailed; "atexit() failed"
0x18009ecc6  mov     [rsp+120h+var_F0], rax; __int64
0x18009eccb  mov     [rsp+120h+var_F8], 8007000Eh; int
0x18009ecd3  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18009ecdb  lea     r9, Src
0x18009ece2  lea     r8, aNoFilename; "(no filename)"
0x18009ece9  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009ecee  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ecf3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ecfa  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009ecff  call    _CxxThrowException_0
0x18009ed05  mov     r8, [rsp+120h+Context]; lpContext
0x18009ed0a  xor     edx, edx; dwFlags
0x18009ed0c  mov     rcx, rdi; lpInitOnce
0x18009ed0f  call    cs:__imp_InitOnceComplete
0x18009ed15  test    eax, eax
0x18009ed17  jz      short loc_18009ED45
0x18009ed19  mov     [rsp+120h+var_D0], 0
0x18009ed22  mov     [rsp+120h+var_C8], 0
0x18009ed2b  lea     rcx, [rsp+120h+var_D0]
0x18009ed30  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x18009ed35  nop
0x18009ed36  lea     rcx, [rsp+120h+var_C8]; this
0x18009ed3b  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18009ed40  jmp     loc_18009EC24
0x18009ed45  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18009ed4a  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18009ed51  mov     [rsp+120h+var_F0], rcx; __int64
0x18009ed56  mov     [rsp+120h+var_F8], eax; int
0x18009ed5a  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18009ed62  lea     r9, Src
0x18009ed69  lea     r8, aNoFilename; "(no filename)"
0x18009ed70  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009ed75  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18009ed7a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009ed81  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18009ed86  call    _CxxThrowException_0
```
