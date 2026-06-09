# win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Get<win_dox::OpcPartSetImplementation::SingletonInitializer>(win_dox::OpcPartSetImplementation::SingletonInitializer)

- ea: `0x1800f3980`
- end: `0x1800f3b4a`
- name: `??$Get@VSingletonInitializer@OpcPartSetImplementation@win_dox@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@OpcPartSetImplementation@win_dox@@@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800f3e9c`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180098e2c`
- `0x1800b69cc`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x1800f3980`
- `0x1800f3c34`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f39d1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800f39d1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f3aaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800f3aaf`

## string_xrefs

- `0x1800f3b08`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Get<win_dox::OpcPartSetImplementation::SingletonInitializer>()
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
          &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
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
    v8 = &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage;
    LODWORD(v9) = 0;
    win_dox::OpcPartSetImplementation::SingletonInitializer::operator()(v0, &v7);
    Context = v7;
    if ( atexit(win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
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
    std::auto_ptr<win_musl::ContentType>::~auto_ptr<win_musl::ContentType>(&v7);
    win_musl::InitOnceGuard::~InitOnceGuard((win_musl::InitOnceGuard *)&v8);
  }
  return Context;
}

```

## disassembly

```asm
0x1800f3980  mov     rax, rsp
0x1800f3983  push    rbp
0x1800f3984  lea     rbp, [rax-28h]
0x1800f3988  sub     rsp, 120h
0x1800f398f  mov     [rsp+120h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800f3998  mov     [rax+8], rdi
0x1800f399c  mov     rax, cs:__security_cookie
0x1800f39a3  xor     rax, rsp
0x1800f39a6  mov     [rbp+20h+var_10], rax
0x1800f39aa  mov     [rsp+120h+fPending], 0
0x1800f39b2  mov     [rsp+120h+Context], 0
0x1800f39bb  lea     r9, [rsp+120h+Context]; lpContext
0x1800f39c0  lea     r8, [rsp+120h+fPending]; fPending
0x1800f39c5  xor     edx, edx; dwFlags
0x1800f39c7  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::ContentType,win_dox::OpcPartSetImplementation::RelationshipsContentTypeSingleton_tag>::store(void)'::`2'::s_storage
0x1800f39ce  mov     rcx, rdi; lpInitOnce
0x1800f39d1  call    cs:__imp_InitOnceBeginInitialize
0x1800f39d7  test    eax, eax
0x1800f39d9  jnz     short loc_1800F3A22
0x1800f39db  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800f39e0  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x1800f39e7  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800f39ec  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800f39f0  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x1800f39f8  lea     r9, word_18013A0B6
0x1800f39ff  lea     r8, aNoFilename; "(no filename)"
0x1800f3a06  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3a0b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3a10  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3a17  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3a1c  call    _CxxThrowException_0
0x1800f3a22  cmp     [rsp+120h+fPending], 0
0x1800f3a27  jz      loc_1800F3AE0
0x1800f3a2d  mov     [rsp+120h+var_C8], rdi
0x1800f3a32  mov     dword ptr [rsp+120h+var_C0], 0
0x1800f3a3a  lea     rdx, [rsp+120h+var_D0]
0x1800f3a3f  call    ??RSingletonInitializer@OpcPartSetImplementation@win_dox@@QEBA?AV?$auto_ptr@UContentType@win_musl@@@std@@XZ; win_dox::OpcPartSetImplementation::SingletonInitializer::operator()(void)
0x1800f3a44  nop
0x1800f3a45  mov     rax, [rsp+120h+var_D0]
0x1800f3a4a  mov     [rsp+120h+Context], rax
0x1800f3a4f  lea     rcx, ?Cleanup@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@OpcPartSetImplementation@win_dox@@@win_musl@@CAXXZ; void (__cdecl *)()
0x1800f3a56  call    atexit
0x1800f3a5b  test    eax, eax
0x1800f3a5d  jz      short loc_1800F3AA5
0x1800f3a5f  lea     rax, aAtexitFailed; "atexit() failed"
0x1800f3a66  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x1800f3a6b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x1800f3a73  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x1800f3a7b  lea     r9, word_18013A0B6
0x1800f3a82  lea     r8, aNoFilename; "(no filename)"
0x1800f3a89  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3a8e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3a93  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3a9a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3a9f  call    _CxxThrowException_0
0x1800f3aa5  mov     r8, [rsp+120h+Context]; lpContext
0x1800f3aaa  xor     edx, edx; dwFlags
0x1800f3aac  mov     rcx, rdi; lpInitOnce
0x1800f3aaf  call    cs:__imp_InitOnceComplete
0x1800f3ab5  test    eax, eax
0x1800f3ab7  jz      short loc_1800F3B02
0x1800f3ab9  mov     [rsp+120h+var_D0], 0
0x1800f3ac2  mov     [rsp+120h+var_C8], 0
0x1800f3acb  lea     rcx, [rsp+120h+var_D0]
0x1800f3ad0  call    ??1?$auto_ptr@UContentType@win_musl@@@std@@QEAA@XZ; std::auto_ptr<win_musl::ContentType>::~auto_ptr<win_musl::ContentType>(void)
0x1800f3ad5  nop
0x1800f3ad6  lea     rcx, [rsp+120h+var_C8]; this
0x1800f3adb  call    ??1InitOnceGuard@win_musl@@QEAA@XZ; win_musl::InitOnceGuard::~InitOnceGuard(void)
0x1800f3ae0  mov     rax, [rsp+120h+Context]
0x1800f3ae5  mov     rcx, [rbp+20h+var_10]
0x1800f3ae9  xor     rcx, rsp; StackCookie
0x1800f3aec  call    __security_check_cookie
0x1800f3af1  mov     rdi, [rsp+120h+arg_0]
0x1800f3af9  add     rsp, 120h
0x1800f3b00  pop     rbp
0x1800f3b01  retn
0x1800f3b02  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800f3b07  nop
0x1800f3b08  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x1800f3b0f  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x1800f3b14  mov     [rsp+120h+var_F8], eax; unsigned int
0x1800f3b18  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x1800f3b20  lea     r9, word_18013A0B6
0x1800f3b27  lea     r8, aNoFilename; "(no filename)"
0x1800f3b2e  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800f3b33  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800f3b38  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800f3b3f  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800f3b44  call    _CxxThrowException_0
```
