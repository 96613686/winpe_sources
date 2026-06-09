# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>)

- ea: `0x18007095c`
- end: `0x180070b26`
- name: `??$Get@V?$SingletonInitializer@VContentTypes@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VContentTypes@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006fa68`

## callees

- `0x1800517a0`
- `0x18007095c`
- `0x180071094`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800709ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800709ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180070a8b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180070a8b`

## string_xrefs

- `0x180070ae4`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store'::`2'::s_storage,
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
0x18007095c  mov     rax, rsp
0x18007095f  push    rbp
0x180070960  lea     rbp, [rax-28h]
0x180070964  sub     rsp, 120h
0x18007096b  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180070974  mov     [rax+8], rdi
0x180070978  mov     rax, cs:__security_cookie
0x18007097f  xor     rax, rsp
0x180070982  mov     [rbp+20h+var_10], rax
0x180070986  mov     [rsp+120h+fPending], 0
0x18007098e  mov     [rsp+120h+Context], 0
0x180070997  lea     r9, [rsp+120h+Context]; lpContext
0x18007099c  lea     r8, [rsp+120h+fPending]; fPending
0x1800709a1  xor     edx, edx; dwFlags
0x1800709a3  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::ContentTypes>>::store(void)'::`2'::s_storage
0x1800709aa  mov     rcx, rdi; lpInitOnce
0x1800709ad  call    cs:__imp_InitOnceBeginInitialize
0x1800709b3  test    eax, eax
0x1800709b5  jnz     short loc_1800709FE
0x1800709b7  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800709bc  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800709c3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800709c8  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800709cc  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800709d4  lea     r9, word_18013A0B6
0x1800709db  lea     r8, aNoFilename; "(no filename)"
0x1800709e2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800709e7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800709ec  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800709f3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800709f8  call    _CxxThrowException_0
0x1800709fe  cmp     [rsp+120h+fPending], 0
0x180070a03  jz      loc_180070ABC
0x180070a09  mov     [rsp+120h+var_C8], rdi
0x180070a0e  mov     dword ptr [rsp+120h+var_C0], 0
0x180070a16  lea     rdx, [rsp+120h+var_D0]
0x180070a1b  call    ??R?$SingletonInitializer@VContentTypes@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::ContentTypes>::operator()(void)
0x180070a20  nop
0x180070a21  mov     rax, [rsp+120h+var_D0]
0x180070a26  mov     [rsp+120h+Context], rax
0x180070a2b  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VContentTypes@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180070a32  call    atexit
0x180070a37  test    eax, eax
0x180070a39  jz      short loc_180070A81
0x180070a3b  lea     rax, aAtexitFailed; "atexit() failed"
0x180070a42  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x180070a47  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180070a4f  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180070a57  lea     r9, word_18013A0B6
0x180070a5e  lea     r8, aNoFilename; "(no filename)"
0x180070a65  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180070a6a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180070a6f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180070a76  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180070a7b  call    _CxxThrowException_0
0x180070a81  mov     r8, [rsp+120h+Context]; lpContext
0x180070a86  xor     edx, edx; dwFlags
0x180070a88  mov     rcx, rdi; lpInitOnce
0x180070a8b  call    cs:__imp_InitOnceComplete
0x180070a91  test    eax, eax
0x180070a93  jz      short loc_180070ADE
0x180070a95  mov     [rsp+120h+var_D0], 0
0x180070a9e  mov     [rsp+120h+var_C8], 0
0x180070aa7  lea     rcx, [rsp+120h+var_D0]
0x180070aac  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x180070ab1  nop
0x180070ab2  lea     rcx, [rsp+120h+var_C8]; this
0x180070ab7  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x180070abc  mov     rax, [rsp+120h+Context]
0x180070ac1  mov     rcx, [rbp+20h+var_10]
0x180070ac5  xor     rcx, rsp; StackCookie
0x180070ac8  call    __security_check_cookie
0x180070acd  mov     rdi, [rsp+120h+arg_0]
0x180070ad5  add     rsp, 120h
0x180070adc  pop     rbp
0x180070add  retn
0x180070ade  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180070ae3  nop
0x180070ae4  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180070aeb  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180070af0  mov     [rsp+120h+var_F8], eax; unsigned int
0x180070af4  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180070afc  lea     r9, word_18013A0B6
0x180070b03  lea     r8, aNoFilename; "(no filename)"
0x180070b0a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180070b0f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180070b14  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180070b1b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180070b20  call    _CxxThrowException_0
```
