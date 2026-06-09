# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>)

- ea: `0x1801074e4`
- end: `0x1801076ae`
- name: `??$Get@V?$SingletonInitializer@VStringElement@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VStringElement@Model@win_dox@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180108a30`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad534`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1801074e4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107535`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180107535`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107613`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180107613`

## string_xrefs

- `0x18010766c`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v1; // rcx
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  unsigned int v4; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  void *v7; // [rsp+58h] [rbp-B0h] BYREF
  union _RTL_RUN_ONCE *v8; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+68h] [rbp-A0h]
  __int64 v10; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v10 = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage,
          0,
          fPending,
          &Context) )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1DCu,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"InitOnceBeginInitialize() failed");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( fPending[0] )
  {
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v1);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v4,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = 0;
    v8 = 0;
    std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x1801074e4  mov     rax, rsp
0x1801074e7  push    rbp
0x1801074e8  lea     rbp, [rax-28h]
0x1801074ec  sub     rsp, 120h
0x1801074f3  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801074fc  mov     [rax+8], rdi
0x180107500  mov     rax, cs:__security_cookie
0x180107507  xor     rax, rsp
0x18010750a  mov     [rbp+20h+var_10], rax
0x18010750e  mov     [rsp+120h+fPending], 0
0x180107516  mov     [rsp+120h+Context], 0
0x18010751f  lea     r9, [rsp+120h+Context]; lpContext
0x180107524  lea     r8, [rsp+120h+fPending]; fPending
0x180107529  xor     edx, edx; dwFlags
0x18010752b  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_dox::Model::StringElement>>::store(void)'::`2'::s_storage
0x180107532  mov     rcx, rdi; lpInitOnce
0x180107535  call    cs:__imp_InitOnceBeginInitialize
0x18010753b  test    eax, eax
0x18010753d  jnz     short loc_180107586
0x18010753f  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180107544  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18010754b  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107550  mov     [rsp+120h+var_F8], eax; unsigned int
0x180107554  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18010755c  lea     r9, word_18013A0B6
0x180107563  lea     r8, aNoFilename; "(no filename)"
0x18010756a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18010756f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180107574  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18010757b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107580  call    _CxxThrowException_0
0x180107586  cmp     [rsp+120h+fPending], 0
0x18010758b  jz      loc_180107644
0x180107591  mov     [rsp+120h+var_C8], rdi
0x180107596  mov     dword ptr [rsp+120h+var_C0], 0
0x18010759e  lea     rdx, [rsp+120h+var_D0]
0x1801075a3  call    ??R?$SingletonInitializer@VStringElement@Model@win_dox@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_dox::Model::StringElement>::operator()(void)
0x1801075a8  nop
0x1801075a9  mov     rax, [rsp+120h+var_D0]
0x1801075ae  mov     [rsp+120h+Context], rax
0x1801075b3  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VStringElement@Model@win_dox@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x1801075ba  call    atexit
0x1801075bf  test    eax, eax
0x1801075c1  jz      short loc_180107609
0x1801075c3  lea     rax, aAtexitFailed; "atexit() failed"
0x1801075ca  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1801075cf  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1801075d7  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1801075df  lea     r9, word_18013A0B6
0x1801075e6  lea     r8, aNoFilename; "(no filename)"
0x1801075ed  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1801075f2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801075f7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801075fe  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180107603  call    _CxxThrowException_0
0x180107609  mov     r8, [rsp+120h+Context]; lpContext
0x18010760e  xor     edx, edx; dwFlags
0x180107610  mov     rcx, rdi; lpInitOnce
0x180107613  call    cs:__imp_InitOnceComplete
0x180107619  test    eax, eax
0x18010761b  jz      short loc_180107666
0x18010761d  mov     [rsp+120h+var_D0], 0
0x180107626  mov     [rsp+120h+var_C8], 0
0x18010762f  lea     rcx, [rsp+120h+var_D0]
0x180107634  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180107639  nop
0x18010763a  lea     rcx, [rsp+120h+var_C8]; this
0x18010763f  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180107644  mov     rax, [rsp+120h+Context]
0x180107649  mov     rcx, [rbp+20h+var_10]
0x18010764d  xor     rcx, rsp; StackCookie
0x180107650  call    __security_check_cookie
0x180107655  mov     rdi, [rsp+120h+arg_0]
0x18010765d  add     rsp, 120h
0x180107664  pop     rbp
0x180107665  retn
0x180107666  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18010766b  nop
0x18010766c  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180107673  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180107678  mov     [rsp+120h+var_F8], eax; unsigned int
0x18010767c  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180107684  lea     r9, word_18013A0B6
0x18010768b  lea     r8, aNoFilename; "(no filename)"
0x180107692  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180107697  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18010769c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801076a3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1801076a8  call    _CxxThrowException_0
```
