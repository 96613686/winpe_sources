# win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>(win_musl::consumption::ContainerSender::SingletonInitializer)

- ea: `0x180016b48`
- end: `0x180016cec`
- name: `??$Get@VSingletonInitializer@ContainerSender@consumption@win_musl@@@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@SAPEAUContentType@1@VSingletonInitializer@ContainerSender@consumption@1@@Z`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015dc0`
- `0x18003c040`

## callees

- `0x180016b48`
- `0x1800517a0`
- `0x180079ca0`
- `0x180098308`
- `0x1800cd38c`
- `0x1800cd66c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016b99`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016b99`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016c08`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016c08`

## string_xrefs

- `0x180016caa`: `InitOnceComplete() failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPVOID win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Get<win_musl::consumption::ContainerSender::SingletonInitializer>()
{
  win_musl::detail *v0; // rcx
  win_musl::detail *v2; // rcx
  unsigned int v3; // eax
  unsigned int LastErrorAsFailHR; // [rsp+30h] [rbp-D8h]
  BOOL fPending[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID Context; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v7[3]; // [rsp+58h] [rbp-B0h] BYREF
  int v8; // [rsp+70h] [rbp-98h]
  _BYTE pExceptionObject[160]; // [rsp+78h] [rbp-90h] BYREF

  v7[1] = -2;
  fPending[0] = 0;
  Context = 0;
  if ( !InitOnceBeginInitialize(
          &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
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
    v7[2] = &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage;
    v8 = 0;
    win_musl::consumption::ContainerSender::SingletonInitializer::operator()(v0, v7);
    Context = (LPVOID)v7[0];
    if ( atexit(win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::Cleanup) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1EAu,
        0x8007000E,
        (struct win_musl::TStringEllipseBase *)L"atexit() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !InitOnceComplete(
            &`win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store'::`2'::s_storage,
            0,
            Context) )
    {
      v3 = win_musl::detail::GetLastErrorAsFailHR(v2);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1F5u,
        v3,
        (struct win_musl::TStringEllipseBase *)L"InitOnceComplete() failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  return Context;
}

```

## disassembly

```asm
0x180016b48  mov     rax, rsp
0x180016b4b  push    rbp
0x180016b4c  lea     rbp, [rax-28h]
0x180016b50  sub     rsp, 120h
0x180016b57  mov     [rsp+120h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180016b60  mov     [rax+8], rdi
0x180016b64  mov     rax, cs:__security_cookie
0x180016b6b  xor     rax, rsp
0x180016b6e  mov     [rbp+20h+var_10], rax
0x180016b72  mov     [rsp+120h+fPending], 0
0x180016b7a  mov     [rsp+120h+Context], 0
0x180016b83  lea     r9, [rsp+120h+Context]; lpContext
0x180016b88  lea     r8, [rsp+120h+fPending]; fPending
0x180016b8d  xor     edx, edx; dwFlags
0x180016b8f  lea     rdi, ?s_storage@?1??store@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@CAPEAT_RTL_RUN_ONCE@@XZ@4T4@A; _RTL_RUN_ONCE `win_musl::InitOnceSingleton<win_musl::ContentType,win_musl::consumption::ContainerSender::RelationshipsContentTypeSingleton_tag>::store(void)'::`2'::s_storage
0x180016b96  mov     rcx, rdi; lpInitOnce
0x180016b99  call    cs:__imp_InitOnceBeginInitialize
0x180016b9f  test    eax, eax
0x180016ba1  jz      short loc_180016C18
0x180016ba3  cmp     [rsp+120h+fPending], 0
0x180016ba8  jnz     short loc_180016BCC
0x180016baa  mov     rax, [rsp+120h+Context]
0x180016baf  mov     rcx, [rbp+20h+var_10]
0x180016bb3  xor     rcx, rsp; StackCookie
0x180016bb6  call    __security_check_cookie
0x180016bbb  mov     rdi, [rsp+120h+arg_0]
0x180016bc3  add     rsp, 120h
0x180016bca  pop     rbp
0x180016bcb  retn
0x180016bcc  mov     qword ptr [rsp+120h+var_C0], rdi
0x180016bd1  mov     [rsp+120h+var_B8], 0
0x180016bd9  lea     rdx, [rsp+120h+var_D0]
0x180016bde  call    ??RSingletonInitializer@ContainerSender@consumption@win_musl@@QEBA?AV?$auto_ptr@UContentType@win_musl@@@std@@XZ; win_musl::consumption::ContainerSender::SingletonInitializer::operator()(void)
0x180016be3  nop
0x180016be4  mov     rax, [rsp+120h+var_D0]
0x180016be9  mov     [rsp+120h+Context], rax
0x180016bee  lea     rcx, ?Cleanup@?$InitOnceSingleton@UContentType@win_musl@@URelationshipsContentTypeSingleton_tag@ContainerSender@consumption@2@@win_musl@@CAXXZ; void (__cdecl *)()
0x180016bf5  call    atexit
0x180016bfa  test    eax, eax
0x180016bfc  jnz     short loc_180016C5F
0x180016bfe  mov     r8, [rsp+120h+Context]; lpContext
0x180016c03  xor     edx, edx; dwFlags
0x180016c05  mov     rcx, rdi; lpInitOnce
0x180016c08  call    cs:__imp_InitOnceComplete
0x180016c0e  test    eax, eax
0x180016c10  jz      loc_180016CA5
0x180016c16  jmp     short loc_180016BAA
0x180016c18  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180016c1d  lea     rcx, aInitoncebegini; "InitOnceBeginInitialize() failed"
0x180016c24  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180016c29  mov     [rsp+120h+var_F8], eax; unsigned int
0x180016c2d  mov     [rsp+120h+var_100], 1DCh; unsigned int
0x180016c35  lea     r9, word_18013A0B6
0x180016c3c  lea     r8, aNoFilename; "(no filename)"
0x180016c43  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180016c48  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180016c4d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180016c54  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180016c59  call    _CxxThrowException_0
0x180016c5f  lea     rax, aAtexitFailed; "atexit() failed"
0x180016c66  mov     qword ptr [rsp+120h+var_F8+8], rax; struct win_musl::TStringEllipseBase *
0x180016c6b  mov     [rsp+120h+var_F8], 8007000Eh; unsigned int
0x180016c73  mov     [rsp+120h+var_100], 1EAh; unsigned int
0x180016c7b  lea     r9, word_18013A0B6
0x180016c82  lea     r8, aNoFilename; "(no filename)"
0x180016c89  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180016c8e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180016c93  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180016c9a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180016c9f  call    _CxxThrowException_0
0x180016ca5  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180016caa  lea     rcx, aInitoncecomple; "InitOnceComplete() failed"
0x180016cb1  mov     qword ptr [rsp+120h+var_F8+8], rcx; struct win_musl::TStringEllipseBase *
0x180016cb6  mov     [rsp+120h+var_F8], eax; unsigned int
0x180016cba  mov     [rsp+120h+var_100], 1F5h; unsigned int
0x180016cc2  lea     r9, word_18013A0B6
0x180016cc9  lea     r8, aNoFilename; "(no filename)"
0x180016cd0  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180016cd5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180016cda  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180016ce1  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180016ce6  call    _CxxThrowException_0
```
