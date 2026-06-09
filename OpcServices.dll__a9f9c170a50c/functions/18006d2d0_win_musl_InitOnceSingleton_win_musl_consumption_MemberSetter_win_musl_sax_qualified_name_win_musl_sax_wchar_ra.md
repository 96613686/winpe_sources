# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>)

- ea: `0x18006d2d0`
- end: `0x18006d49a`
- name: `??$Get@V?$SingletonInitializer@VRelationships@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VRelationships@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006d194`
- `0x1800b4348`

## callees

- `0x1800517a0`
- `0x18006d2d0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1800e60f0`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006d321`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006d321`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006d3ff`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006d3ff`

## string_xrefs

- `0x18006d458`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store'::`2'::s_storage,
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
0x18006d2d0  mov     rax, rsp
0x18006d2d3  push    rbp
0x18006d2d4  lea     rbp, [rax-28h]
0x18006d2d8  sub     rsp, 120h
0x18006d2df  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18006d2e8  mov     [rax+8], rdi
0x18006d2ec  mov     rax, cs:__security_cookie
0x18006d2f3  xor     rax, rsp
0x18006d2f6  mov     [rbp+20h+var_10], rax
0x18006d2fa  mov     [rsp+120h+fPending], 0
0x18006d302  mov     [rsp+120h+Context], 0
0x18006d30b  lea     r9, [rsp+120h+Context]; lpContext
0x18006d310  lea     r8, [rsp+120h+fPending]; fPending
0x18006d315  xor     edx, edx; dwFlags
0x18006d317  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationships>>::store(void)'::`2'::s_storage
0x18006d31e  mov     rcx, rdi; lpInitOnce
0x18006d321  call    cs:__imp_InitOnceBeginInitialize
0x18006d327  test    eax, eax
0x18006d329  jnz     short loc_18006D372
0x18006d32b  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18006d330  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18006d337  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18006d33c  mov     [rsp+120h+var_F8], eax; unsigned int
0x18006d340  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18006d348  lea     r9, word_18013A0B6
0x18006d34f  lea     r8, aNoFilename; "(no filename)"
0x18006d356  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006d35b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006d360  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006d367  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006d36c  call    _CxxThrowException_0
0x18006d372  cmp     [rsp+120h+fPending], 0
0x18006d377  jz      loc_18006D430
0x18006d37d  mov     [rsp+120h+var_C8], rdi
0x18006d382  mov     dword ptr [rsp+120h+var_C0], 0
0x18006d38a  lea     rdx, [rsp+120h+var_D0]
0x18006d38f  call    ??R?$SingletonInitializer@VRelationships@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationships>::operator()(void)
0x18006d394  nop
0x18006d395  mov     rax, [rsp+120h+var_D0]
0x18006d39a  mov     [rsp+120h+Context], rax
0x18006d39f  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationships@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18006d3a6  call    atexit
0x18006d3ab  test    eax, eax
0x18006d3ad  jz      short loc_18006D3F5
0x18006d3af  lea     rax, aAtexitFailed; "atexit() failed"
0x18006d3b6  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18006d3bb  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x18006d3c3  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18006d3cb  lea     r9, word_18013A0B6
0x18006d3d2  lea     r8, aNoFilename; "(no filename)"
0x18006d3d9  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006d3de  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006d3e3  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006d3ea  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006d3ef  call    _CxxThrowException_0
0x18006d3f5  mov     r8, [rsp+120h+Context]; lpContext
0x18006d3fa  xor     edx, edx; dwFlags
0x18006d3fc  mov     rcx, rdi; lpInitOnce
0x18006d3ff  call    cs:__imp_InitOnceComplete
0x18006d405  test    eax, eax
0x18006d407  jz      short loc_18006D452
0x18006d409  mov     [rsp+120h+var_D0], 0
0x18006d412  mov     [rsp+120h+var_C8], 0
0x18006d41b  lea     rcx, [rsp+120h+var_D0]
0x18006d420  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x18006d425  nop
0x18006d426  lea     rcx, [rsp+120h+var_C8]; this
0x18006d42b  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18006d430  mov     rax, [rsp+120h+Context]
0x18006d435  mov     rcx, [rbp+20h+var_10]
0x18006d439  xor     rcx, rsp; StackCookie
0x18006d43c  call    __security_check_cookie
0x18006d441  mov     rdi, [rsp+120h+arg_0]
0x18006d449  add     rsp, 120h
0x18006d450  pop     rbp
0x18006d451  retn
0x18006d452  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18006d457  nop
0x18006d458  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18006d45f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18006d464  mov     [rsp+120h+var_F8], eax; unsigned int
0x18006d468  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18006d470  lea     r9, word_18013A0B6
0x18006d477  lea     r8, aNoFilename; "(no filename)"
0x18006d47e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006d483  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006d488  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006d48f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006d494  call    _CxxThrowException_0
```
