# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTarget>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTarget>)

- ea: `0x18012aaa0`
- end: `0x18012ac60`
- name: `??$Get@V?$SingletonInitializer@VLinkTarget@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTarget@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VLinkTarget@Model@win_musl@@@341@@Z`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18012a9e0`

## callees

- `0x180012450`
- `0x1800ad884`
- `0x180115e70`
- `0x180118898`
- `0x18012aaa0`
- `0x180134b70`
- `0x180134f20`
- `0x1801359ce`
- `0x18018c644`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18012abc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18012abc5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18012aae7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18012aae7`

## string_xrefs

- `0x18012ac1e`: `InitOnceComplete() failed`

## pseudocode

```c
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTarget>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::store'::`2'::s_storage;
    v9 = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTarget>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x1EAu,
        -2147024882,
        (__int64)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::store'::`2'::s_storage,
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
0x18012aaa0  mov     [rsp-8+arg_0], rdi
0x18012aaa5  push    rbp
0x18012aaa6  lea     rbp, [rsp-20h]
0x18012aaab  sub     rsp, 120h
0x18012aab2  mov     rax, cs:__security_cookie
0x18012aab9  xor     rax, rsp
0x18012aabc  mov     [rbp+20h+var_10], rax
0x18012aac0  mov     [rsp+120h+fPending], 0
0x18012aac8  mov     [rsp+120h+Context], 0
0x18012aad1  lea     r9, [rsp+120h+Context]; lpContext
0x18012aad6  lea     r8, [rsp+120h+fPending]; fPending
0x18012aadb  xor     edx, edx; dwFlags
0x18012aadd  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTarget@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::LinkTarget>>::store(void)'::`2'::s_storage
0x18012aae4  mov     rcx, rdi; lpInitOnce
0x18012aae7  call    cs:__imp_InitOnceBeginInitialize
0x18012aaed  test    eax, eax
0x18012aaef  jnz     short loc_18012AB38
0x18012aaf1  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18012aaf6  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18012aafd  mov     [rsp+120h+var_F0], rcx; __int64
0x18012ab02  mov     [rsp+120h+var_F8], eax; int
0x18012ab06  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18012ab0e  lea     r9, Src
0x18012ab15  lea     r8, aNoFilename; "(no filename)"
0x18012ab1c  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18012ab21  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18012ab26  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18012ab2d  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18012ab32  call    _CxxThrowException_0
0x18012ab38  cmp     [rsp+120h+fPending], 0
0x18012ab3d  jz      loc_18012ABF6
0x18012ab43  mov     [rsp+120h+var_C8], rdi
0x18012ab48  mov     [rsp+120h+var_C0], 0
0x18012ab50  lea     rdx, [rsp+120h+var_D0]
0x18012ab55  call    ??R?$SingletonInitializer@VLinkTarget@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$unique_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$default_delete@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::LinkTarget>::operator()(void)
0x18012ab5a  nop
0x18012ab5b  mov     rax, [rsp+120h+var_D0]
0x18012ab60  mov     [rsp+120h+Context], rax
0x18012ab65  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VLinkTarget@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18012ab6c  call    atexit
0x18012ab71  test    eax, eax
0x18012ab73  jz      short loc_18012ABBB
0x18012ab75  lea     rax, aAtexitFailed; "atexit() failed"
0x18012ab7c  mov     [rsp+120h+var_F0], rax; __int64
0x18012ab81  mov     [rsp+120h+var_F8], 8007000Eh; int
0x18012ab89  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18012ab91  lea     r9, Src
0x18012ab98  lea     r8, aNoFilename; "(no filename)"
0x18012ab9f  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18012aba4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18012aba9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18012abb0  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18012abb5  call    _CxxThrowException_0
0x18012abbb  mov     r8, [rsp+120h+Context]; lpContext
0x18012abc0  xor     edx, edx; dwFlags
0x18012abc2  mov     rcx, rdi; lpInitOnce
0x18012abc5  call    cs:__imp_InitOnceComplete
0x18012abcb  test    eax, eax
0x18012abcd  jz      short loc_18012AC18
0x18012abcf  mov     [rsp+120h+var_D0], 0
0x18012abd8  mov     [rsp+120h+var_C8], 0
0x18012abe1  lea     rcx, [rsp+120h+var_D0]
0x18012abe6  call    ??1?$unique_ptr@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@U?$default_delete@$$CBU?$MemberBindings@V?$MemberSetterOnReceiver@UPageBodyReceiverTraitsWithTypeList@?1???$ParsePage@UMsXpsBuilderTraits@xpsom@@@win_musl@@YAXAEBVOpcPartUri@win_dox@@V?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@VFixedPageBodyBuilder@xpsom@@@Z@Uqualified_name@sax@2@Uwchar_range@sax@2@@win_musl@@@win_musl@@@std@@@std@@QEAA@XZ; std::unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>::~unique_ptr<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const,std::default_delete<win_musl::MemberBindings<win_musl::MemberSetterOnReceiver<`win_musl::ParsePage<xpsom::MsXpsBuilderTraits>(win_dox::OpcPartUri const &,win_scope::scope<IStream *,win_scope::const_policies<win_scope::com_policies>>,xpsom::FixedPageBodyBuilder)'::`2'::PageBodyReceiverTraitsWithTypeList,win_musl::sax::qualified_name,win_musl::sax::wchar_range>> const>>(void)
0x18012abeb  nop
0x18012abec  lea     rcx, [rsp+120h+var_C8]; this
0x18012abf1  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18012abf6  mov     rax, [rsp+120h+Context]
0x18012abfb  mov     rcx, [rbp+20h+var_10]
0x18012abff  xor     rcx, rsp; StackCookie
0x18012ac02  call    __security_check_cookie
0x18012ac07  mov     rdi, [rsp+120h+arg_0]
0x18012ac0f  add     rsp, 120h
0x18012ac16  pop     rbp
0x18012ac17  retn
0x18012ac18  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18012ac1d  nop
0x18012ac1e  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18012ac25  mov     [rsp+120h+var_F0], rcx; __int64
0x18012ac2a  mov     [rsp+120h+var_F8], eax; int
0x18012ac2e  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18012ac36  lea     r9, Src
0x18012ac3d  lea     r8, aNoFilename; "(no filename)"
0x18012ac44  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18012ac49  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18012ac4e  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18012ac55  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18012ac5a  call    _CxxThrowException_0
```
