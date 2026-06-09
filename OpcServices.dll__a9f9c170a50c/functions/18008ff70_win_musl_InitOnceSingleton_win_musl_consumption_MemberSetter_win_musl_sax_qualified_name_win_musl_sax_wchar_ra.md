# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>)

- ea: `0x18008ff70`
- end: `0x18009013a`
- name: `??$Get@V?$SingletonInitializer@VOverrideType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VOverrideType@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003ea80`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x18008ff70`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1800e5f18`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008ffc1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18008ffc1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800900bd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800900bd`

## string_xrefs

- `0x1800900f8`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>>()
{
  win_musl::detail *v0; // rcx
  unsigned int LastErrorAsFailHR; // eax
  win_musl::detail *v3; // rcx
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v4 = win_musl::detail::GetLastErrorAsFailHR(v3);
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
0x18008ff70  mov     rax, rsp
0x18008ff73  push    rbp
0x18008ff74  lea     rbp, [rax-28h]
0x18008ff78  sub     rsp, 120h
0x18008ff7f  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18008ff88  mov     [rax+8], rdi
0x18008ff8c  mov     rax, cs:__security_cookie
0x18008ff93  xor     rax, rsp
0x18008ff96  mov     [rbp+20h+var_10], rax
0x18008ff9a  mov     [rsp+120h+fPending], 0
0x18008ffa2  mov     [rsp+120h+Context], 0
0x18008ffab  lea     r9, [rsp+120h+Context]; lpContext
0x18008ffb0  lea     r8, [rsp+120h+fPending]; fPending
0x18008ffb5  xor     edx, edx; dwFlags
0x18008ffb7  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::OverrideType>>::store(void)'::`2'::s_storage
0x18008ffbe  mov     rcx, rdi; lpInitOnce
0x18008ffc1  call    cs:__imp_InitOnceBeginInitialize
0x18008ffc7  test    eax, eax
0x18008ffc9  jz      short loc_18008FFF4
0x18008ffcb  cmp     [rsp+120h+fPending], 0
0x18008ffd0  jnz     short loc_18009003B
0x18008ffd2  mov     rax, [rsp+120h+Context]
0x18008ffd7  mov     rcx, [rbp+20h+var_10]
0x18008ffdb  xor     rcx, rsp; StackCookie
0x18008ffde  call    __security_check_cookie
0x18008ffe3  mov     rdi, [rsp+120h+arg_0]
0x18008ffeb  add     rsp, 120h
0x18008fff2  pop     rbp
0x18008fff3  retn
0x18008fff4  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18008fff9  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180090000  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180090005  mov     [rsp+120h+var_F8], eax; unsigned int
0x180090009  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180090011  lea     r9, word_18013A0B6
0x180090018  lea     r8, aNoFilename; "(no filename)"
0x18009001f  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180090024  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090029  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180090030  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180090035  call    _CxxThrowException_0
0x18009003b  mov     [rsp+120h+var_C8], rdi
0x180090040  mov     dword ptr [rsp+120h+var_C0], 0
0x180090048  lea     rdx, [rsp+120h+var_D0]
0x18009004d  call    ??R?$SingletonInitializer@VOverrideType@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::OverrideType>::operator()(void)
0x180090052  nop
0x180090053  mov     rax, [rsp+120h+var_D0]
0x180090058  mov     [rsp+120h+Context], rax
0x18009005d  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VOverrideType@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x180090064  call    atexit
0x180090069  test    eax, eax
0x18009006b  jz      short loc_1800900B3
0x18009006d  lea     rax, aAtexitFailed; "atexit() failed"
0x180090074  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x180090079  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180090081  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180090089  lea     r9, word_18013A0B6
0x180090090  lea     r8, aNoFilename; "(no filename)"
0x180090097  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18009009c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800900a1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800900a8  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800900ad  call    _CxxThrowException_0
0x1800900b3  mov     r8, [rsp+120h+Context]; lpContext
0x1800900b8  xor     edx, edx; dwFlags
0x1800900ba  mov     rcx, rdi; lpInitOnce
0x1800900bd  call    cs:__imp_InitOnceComplete
0x1800900c3  test    eax, eax
0x1800900c5  jz      short loc_1800900F3
0x1800900c7  mov     [rsp+120h+var_D0], 0
0x1800900d0  mov     [rsp+120h+var_C8], 0
0x1800900d9  lea     rcx, [rsp+120h+var_D0]
0x1800900de  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x1800900e3  nop
0x1800900e4  lea     rcx, [rsp+120h+var_C8]; this
0x1800900e9  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800900ee  jmp     loc_18008FFD2
0x1800900f3  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800900f8  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800900ff  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180090104  mov     [rsp+120h+var_F8], eax; unsigned int
0x180090108  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180090110  lea     r9, word_18013A0B6
0x180090117  lea     r8, aNoFilename; "(no filename)"
0x18009011e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180090123  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180090128  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18009012f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180090134  call    _CxxThrowException_0
```
