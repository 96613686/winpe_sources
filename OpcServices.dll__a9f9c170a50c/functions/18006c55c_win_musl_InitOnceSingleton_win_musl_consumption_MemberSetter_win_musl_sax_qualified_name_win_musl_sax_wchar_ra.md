# win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>>(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>)

- ea: `0x18006c55c`
- end: `0x18006c726`
- name: `??$Get@V?$SingletonInitializer@VRelationship@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@SAPEBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@1@V?$SingletonInitializer@VRelationship@Model@win_musl@@@341@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006b600`

## callees

- `0x1800517a0`
- `0x18006c55c`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800ad628`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1800e603c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006c5ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006c5ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006c68b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006c68b`

## string_xrefs

- `0x18006c6e4`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Get<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>>()
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
          &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>::operator()(
      v0,
      &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store'::`2'::s_storage,
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
0x18006c55c  mov     rax, rsp
0x18006c55f  push    rbp
0x18006c560  lea     rbp, [rax-28h]
0x18006c564  sub     rsp, 120h
0x18006c56b  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18006c574  mov     [rax+8], rdi
0x18006c578  mov     rax, cs:__security_cookie
0x18006c57f  xor     rax, rsp
0x18006c582  mov     [rbp+20h+var_10], rax
0x18006c586  mov     [rsp+120h+fPending], 0
0x18006c58e  mov     [rsp+120h+Context], 0
0x18006c597  lea     r9, [rsp+120h+Context]; lpContext
0x18006c59c  lea     r8, [rsp+120h+fPending]; fPending
0x18006c5a1  xor     edx, edx; dwFlags
0x18006c5a3  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t const,win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindingsSingleton_tag<win_musl::Model::Relationship>>::store(void)'::`2'::s_storage
0x18006c5aa  mov     rcx, rdi; lpInitOnce
0x18006c5ad  call    cs:__imp_InitOnceBeginInitialize
0x18006c5b3  test    eax, eax
0x18006c5b5  jnz     short loc_18006C5FE
0x18006c5b7  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18006c5bc  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x18006c5c3  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18006c5c8  mov     [rsp+120h+var_F8], eax; unsigned int
0x18006c5cc  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x18006c5d4  lea     r9, word_18013A0B6
0x18006c5db  lea     r8, aNoFilename; "(no filename)"
0x18006c5e2  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006c5e7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c5ec  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c5f3  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006c5f8  call    _CxxThrowException_0
0x18006c5fe  cmp     [rsp+120h+fPending], 0
0x18006c603  jz      loc_18006C6BC
0x18006c609  mov     [rsp+120h+var_C8], rdi
0x18006c60e  mov     dword ptr [rsp+120h+var_C0], 0
0x18006c616  lea     rdx, [rsp+120h+var_D0]
0x18006c61b  call    ??R?$SingletonInitializer@VRelationship@Model@win_musl@@@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@QEBA?AV?$auto_ptr@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@XZ; win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::SingletonInitializer<win_musl::Model::Relationship>::operator()(void)
0x18006c620  nop
0x18006c621  mov     rax, [rsp+120h+var_D0]
0x18006c626  mov     [rsp+120h+Context], rax
0x18006c62b  lea     rcx, ?Cleanup@?$InitOnceSingleton@$$CBUMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@U?$MemberBindingsSingleton_tag@VRelationship@Model@win_musl@@@234@@win_musl@@CAXXZ; void (__cdecl *)()
0x18006c632  call    atexit
0x18006c637  test    eax, eax
0x18006c639  jz      short loc_18006C681
0x18006c63b  lea     rax, aAtexitFailed; "atexit() failed"
0x18006c642  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x18006c647  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x18006c64f  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x18006c657  lea     r9, word_18013A0B6
0x18006c65e  lea     r8, aNoFilename; "(no filename)"
0x18006c665  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006c66a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c66f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c676  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006c67b  call    _CxxThrowException_0
0x18006c681  mov     r8, [rsp+120h+Context]; lpContext
0x18006c686  xor     edx, edx; dwFlags
0x18006c688  mov     rcx, rdi; lpInitOnce
0x18006c68b  call    cs:__imp_InitOnceComplete
0x18006c691  test    eax, eax
0x18006c693  jz      short loc_18006C6DE
0x18006c695  mov     [rsp+120h+var_D0], 0
0x18006c69e  mov     [rsp+120h+var_C8], 0
0x18006c6a7  lea     rcx, [rsp+120h+var_D0]
0x18006c6ac  call    ??1?$auto_ptr@UMemberBindings_t@?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>::~auto_ptr<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>::MemberBindings_t>(void)
0x18006c6b1  nop
0x18006c6b2  lea     rcx, [rsp+120h+var_C8]; this
0x18006c6b7  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x18006c6bc  mov     rax, [rsp+120h+Context]
0x18006c6c1  mov     rcx, [rbp+20h+var_10]
0x18006c6c5  xor     rcx, rsp; StackCookie
0x18006c6c8  call    __security_check_cookie
0x18006c6cd  mov     rdi, [rsp+120h+arg_0]
0x18006c6d5  add     rsp, 120h
0x18006c6dc  pop     rbp
0x18006c6dd  retn
0x18006c6de  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18006c6e3  nop
0x18006c6e4  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x18006c6eb  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x18006c6f0  mov     [rsp+120h+var_F8], eax; unsigned int
0x18006c6f4  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x18006c6fc  lea     r9, word_18013A0B6
0x18006c703  lea     r8, aNoFilename; "(no filename)"
0x18006c70a  lea     rcx, [rsp+120h+pExceptionObject]; this
0x18006c70f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18006c714  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006c71b  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18006c720  call    _CxxThrowException_0
```
