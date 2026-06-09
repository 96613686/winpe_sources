# UiaManagerImpl::RegisterWindow(uint,IUiaWindowNotifierCallback *,IUiaWindowRegistrationToken * *)

- ea: `0x180013fe0`
- end: `0x180014419`
- name: `?RegisterWindow@UiaManagerImpl@@UEAAJIPEAUIUiaWindowNotifierCallback@@PEAPEAUIUiaWindowRegistrationToken@@@Z`
- size: `1081`
- prototype: `__int64 __fastcall(UiaManagerImpl *__hidden this, unsigned int, struct IUiaWindowNotifierCallback *, struct IUiaWindowRegistrationToken **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006edc`
- `0x1800088e4`
- `0x180009340`
- `0x18000cbe8`
- `0x18000e560`
- `0x180013fe0`
- `0x180043680`
- `0x180043a30`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800142f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014352`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014352`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180014163`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180014163`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001417e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001417e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014273`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014273`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800141ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800141ad`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800140b9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800140b9`

## string_xrefs

- `0x180014026`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180014054`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180014082`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800142b4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180014384`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UiaManagerImpl::RegisterWindow(
        UiaManagerImpl *this,
        WINBOOL a2,
        struct IUiaWindowNotifierCallback *a3,
        struct IUiaWindowRegistrationToken **a4)
{
  ULONGLONG *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 (***v11)(void); // rcx
  _QWORD *v12; // rax
  const char *v13; // r9
  __int64 (*v14)(void); // rax
  int v15; // eax
  unsigned int v16; // ebx
  __int64 (***v17)(void); // rcx
  __int64 (***v18)(void); // rcx
  __int64 (***v19)(void); // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-B8h]
  LPVOID Context; // [rsp+30h] [rbp-A8h] BYREF
  __int64 (***v22)(void); // [rsp+38h] [rbp-A0h] BYREF
  WINBOOL fPending; // [rsp+40h] [rbp-98h] BYREF
  WINBOOL v24; // [rsp+48h] [rbp-90h] BYREF
  struct IUiaWindowNotifierCallback *v25; // [rsp+50h] [rbp-88h] BYREF
  GUID ProviderId; // [rsp+58h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-70h] BYREF
  __int16 *v28; // [rsp+78h] [rbp-60h]
  int v29; // [rsp+80h] [rbp-58h]
  int v30; // [rsp+84h] [rbp-54h]
  WINBOOL *p_fPending; // [rsp+88h] [rbp-50h]
  __int64 v32; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v24 = a2;
  v25 = a3;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  Context = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    Context = &qword_1800C4F30;
    qword_1800C4F38 = 0;
    byte_1800C4F40 = 0;
    dword_1800C4F44 = 0;
    qword_1800C4F30 = (__int64)&UiaManagerTraceLoggingProvider::`vftable';
    CallbackContext = &`UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_::_lambda_invoker_cdecl_);
    v7 = (ULONGLONG *)CallbackContext;
    qword_1800C4F38 = (__int64)CallbackContext;
    byte_1800C4F40 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v7[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v7, v7 + 4) )
      EventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
    dword_1800C4F44 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C4F30 + 8))(&qword_1800C4F30);
    InitOnceComplete(&`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_1800C4F30);
  }
  v8 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)v8 > 4u )
  {
    fPending = v24;
    p_fPending = &fPending;
    v32 = 4;
    ProviderId.Data1 = 184549376;
    *(_DWORD *)&ProviderId.Data2 = 4;
    *(_QWORD *)ProviderId.Data4 = 0;
    UserData.Ptr = *(_QWORD *)(v8 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v28 = &word_1800ADA06;
    v29 = 52;
    v30 = 1;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v8 + 32), (PCEVENT_DESCRIPTOR)&ProviderId, 0, 0, 3u, &UserData);
  }
  *a4 = 0;
  v22 = 0;
  Context = (char *)this - 40;
  v9 = Microsoft::WRL::Details::MakeAndInitialize<UiaManagerWindowRegistration,IUiaWindowRegistration,UiaManagerImpl *,unsigned int &,IUiaWindowNotifierCallback * &>(
         &v22,
         &Context,
         &v24,
         &v25);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v9,
      UserDataCount);
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (***)(void)))(*v11)[2])(v11);
    }
    return v10;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
  v25 = (UiaManagerImpl *)((char *)this + 768);
  try
  {
    wil::com_weak_query<IUiaWindowNotifierCallback * &>(&Context, &v22);
    v12 = (_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Try_emplace<unsigned int const &,>(
                      (char *)this + 64,
                      &ProviderId,
                      &v24);
    wil::com_ptr_t<IWeakReference,wil::err_exception_policy>::operator=(*v12 + 24LL, &Context);
    if ( Context )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)Context + 16LL))(Context);
    if ( this != (UiaManagerImpl *)-768LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
    v14 = **v22;
  }
  catch ( ... )
  {
    LODWORD(Context) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x100,
                         (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                         v13);
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (***)(void)))(*v19)[2])(v19);
    }
    return (unsigned int)Context;
  }
  v15 = v14();
  v16 = v15;
  if ( v15 >= 0 )
  {
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (***)(void)))(*v18)[2])(v18);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v15,
      UserDataCount);
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      ((void (__fastcall *)(__int64 (***)(void)))(*v17)[2])(v17);
    }
    return v16;
  }
}

```

## disassembly

```asm
0x180013fe0  push    rbx
0x180013fe2  push    rsi
0x180013fe3  push    rdi
0x180013fe4  push    r12
0x180013fe6  push    r14
0x180013fe8  push    r15
0x180013fea  sub     rsp, 0A8h
0x180013ff1  mov     rax, cs:__security_cookie
0x180013ff8  xor     rax, rsp
0x180013ffb  mov     [rsp+0D8h+var_40], rax
0x180014003  mov     r15, r9
0x180014006  mov     rsi, rcx
0x180014009  mov     [rsp+0D8h+var_90], edx
0x18001400d  mov     [rsp+0D8h+var_88], r8
0x180014012  xor     edi, edi
0x180014014  test    edx, edx
0x180014016  jnz     short loc_180014041
0x180014018  mov     rcx, [rsp+0D8h]; this
0x180014020  mov     r9d, 80070057h; char *
0x180014026  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18001402d  mov     edx, 0DEh; void *
0x180014032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014037  mov     eax, 80070057h
0x18001403c  jmp     loc_1800143F8
0x180014041  test    r8, r8
0x180014044  jnz     short loc_18001406F
0x180014046  mov     rcx, [rsp+0D8h]; this
0x18001404e  mov     r9d, 80070057h; char *
0x180014054  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18001405b  mov     edx, 0DFh; void *
0x180014060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014065  mov     eax, 80070057h
0x18001406a  jmp     loc_1800143F8
0x18001406f  test    r15, r15
0x180014072  jnz     short loc_18001409D
0x180014074  mov     rcx, [rsp+0D8h]; this
0x18001407c  mov     r9d, 80070057h; char *
0x180014082  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180014089  mov     edx, 0E0h; void *
0x18001408e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014093  mov     eax, 80070057h
0x180014098  jmp     loc_1800143F8
0x18001409d  mov     [rsp+0D8h+Context], rdi
0x1800140a2  mov     [rsp+0D8h+fPending], edi
0x1800140a6  lea     r9, [rsp+0D8h+Context]; lpContext
0x1800140ab  lea     r8, [rsp+0D8h+fPending]; fPending
0x1800140b0  xor     edx, edx; dwFlags
0x1800140b2  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800140b9  call    cs:__imp___std_init_once_begin_initialize
0x1800140bf  test    eax, eax
0x1800140c1  jz      loc_1800141B3
0x1800140c7  cmp     [rsp+0D8h+fPending], edi
0x1800140cb  jz      loc_1800141B3
0x1800140d1  lea     r12, qword_1800C4F30
0x1800140d8  mov     [rsp+0D8h+Context], r12
0x1800140dd  mov     cs:qword_1800C4F38, rdi
0x1800140e4  mov     cs:byte_1800C4F40, dil
0x1800140eb  mov     cs:dword_1800C4F44, edi
0x1800140f1  lea     rax, ??_7UiaManagerTraceLoggingProvider@@6B@; const UiaManagerTraceLoggingProvider::`vftable'
0x1800140f8  mov     cs:qword_1800C4F30, rax
0x1800140ff  lea     rax, ?__hInner@?1???0StaticHandle@UiaManagerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180014106  mov     cs:CallbackContext, rax
0x18001410d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_@@CA@XZ; void (__cdecl *)()
0x180014114  call    atexit
0x180014119  mov     rbx, cs:CallbackContext
0x180014120  mov     cs:qword_1800C4F38, rbx
0x180014127  mov     cs:byte_1800C4F40, 1
0x18001412e  mov     rax, [rbx+8]
0x180014132  movups  xmm0, xmmword ptr [rax-10h]
0x180014136  movups  xmmword ptr [rsp+0D8h+ProviderId.Data1], xmm0
0x18001413b  cmp     [rbx+20h], rdi
0x18001413f  jz      short loc_180014148
0x180014141  mov     ecx, 5
0x180014146  int     29h; Win8: RtlFailFast(ecx)
0x180014148  mov     [rbx+28h], rdi
0x18001414c  mov     [rbx+30h], rdi
0x180014150  lea     r9, [rbx+20h]; RegHandle
0x180014154  mov     r8, rbx; CallbackContext
0x180014157  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001415e  lea     rcx, [rsp+0D8h+ProviderId]; ProviderId
0x180014163  call    cs:__imp_EventRegister
0x180014169  test    eax, eax
0x18001416b  jnz     short loc_180014184
0x18001416d  mov     r8, [rbx+8]
0x180014171  movzx   r9d, word ptr [r8]
0x180014175  mov     edx, 2
0x18001417a  mov     rcx, [rbx+20h]
0x18001417e  call    cs:__imp_EventSetInformation
0x180014184  mov     cs:dword_1800C4F44, 1
0x18001418e  mov     rax, cs:qword_1800C4F30
0x180014195  mov     rcx, r12
0x180014198  mov     rax, [rax+8]
0x18001419c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141a1  mov     r8, r12; lpContext
0x1800141a4  xor     edx, edx; dwFlags
0x1800141a6  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800141ad  call    cs:__imp_InitOnceComplete
0x1800141b3  mov     rax, [rsp+0D8h+Context]
0x1800141b8  mov     rcx, [rax+8]
0x1800141bc  mov     eax, [rcx]
0x1800141be  cmp     eax, 4
0x1800141c1  jbe     loc_180014279
0x1800141c7  mov     eax, [rsp+0D8h+var_90]
0x1800141cb  mov     [rsp+0D8h+fPending], eax
0x1800141cf  lea     rax, [rsp+0D8h+fPending]
0x1800141d4  mov     [rsp+0D8h+var_50], rax
0x1800141dc  mov     [rsp+0D8h+var_48], 4
0x1800141e8  mov     [rsp+0D8h+ProviderId.Data1], 0B000000h
0x1800141f0  movzx   eax, cs:word_1800AD9FC
0x1800141f7  mov     dword ptr [rsp+0D8h+ProviderId.Data2], eax
0x1800141fb  mov     qword ptr [rsp+0D8h+ProviderId.Data4], rdi
0x180014200  mov     rax, [rcx+8]
0x180014204  mov     [rsp+0D8h+var_70.Ptr], rax
0x180014209  movzx   eax, word ptr [rax]
0x18001420c  mov     [rsp+0D8h+var_70.Size], eax
0x180014210  mov     dword ptr [rsp+0D8h+var_70.0Ch], 2
0x180014218  lea     rax, word_1800ADA06
0x18001421f  mov     [rsp+0D8h+var_60], rax
0x180014224  mov     [rsp+0D8h+var_58], 34h ; '4'
0x18001422f  mov     [rsp+0D8h+var_54], 1
0x18001423a  lea     rax, _TraceLoggingMetadataEnd
0x180014241  lea     rdx, _TraceLoggingMetadata
0x180014248  sub     eax, edx
0x18001424a  mov     dword ptr [rsp+0D8h+Context], eax
0x18001424e  mov     eax, dword ptr [rsp+0D8h+Context]
0x180014252  lea     rax, [rsp+0D8h+var_70]
0x180014257  mov     [rsp+0D8h+UserData], rax; UserData
0x18001425c  mov     [rsp+0D8h+UserDataCount], 3; int
0x180014264  xor     r9d, r9d; RelatedActivityId
0x180014267  xor     r8d, r8d; ActivityId
0x18001426a  lea     rdx, [rsp+0D8h+ProviderId]; EventDescriptor
0x18001426f  mov     rcx, [rcx+20h]; RegHandle
0x180014273  call    cs:__imp_EventWriteTransfer
0x180014279  mov     [r15], rdi
0x18001427c  mov     [rsp+0D8h+var_A0], rdi
0x180014281  lea     rax, [rsi-28h]
0x180014285  mov     [rsp+0D8h+Context], rax
0x18001428a  lea     r9, [rsp+0D8h+var_88]
0x18001428f  lea     r8, [rsp+0D8h+var_90]
0x180014294  lea     rdx, [rsp+0D8h+Context]
0x180014299  lea     rcx, [rsp+0D8h+var_A0]
0x18001429e  call    ??$MakeAndInitialize@VUiaManagerWindowRegistration@@UIUiaWindowRegistration@@PEAVUiaManagerImpl@@AEAIAEAPEAUIUiaWindowNotifierCallback@@@Details@WRL@Microsoft@@YAJPEAPEAUIUiaWindowRegistration@@$$QEAPEAVUiaManagerImpl@@AEAIAEAPEAUIUiaWindowNotifierCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UiaManagerWindowRegistration,IUiaWindowRegistration,UiaManagerImpl *,uint &,IUiaWindowNotifierCallback * &>(IUiaWindowRegistration * *,UiaManagerImpl * &&,uint &,IUiaWindowNotifierCallback * &)
0x1800142a3  mov     ebx, eax
0x1800142a5  test    eax, eax
0x1800142a7  jns     short loc_1800142E9
0x1800142a9  mov     rcx, [rsp+0D8h]; this
0x1800142b1  mov     r9d, eax; char *
0x1800142b4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800142bb  mov     edx, 0EDh; void *
0x1800142c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142c5  nop
0x1800142c6  mov     rcx, [rsp+0D8h+var_A0]
0x1800142cb  test    rcx, rcx
0x1800142ce  jz      short loc_1800142E2
0x1800142d0  mov     [rsp+0D8h+var_A0], rdi
0x1800142d5  mov     rax, [rcx]
0x1800142d8  mov     rax, [rax+10h]
0x1800142dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e1  nop
0x1800142e2  mov     eax, ebx
0x1800142e4  jmp     loc_1800143F8
0x1800142e9  lea     rbx, [rsi+300h]
0x1800142f0  mov     rcx, rbx; lpCriticalSection
0x1800142f3  call    cs:__imp_EnterCriticalSection
0x1800142f9  mov     [rsp+0D8h+var_88], rbx
0x1800142fe  lea     rdx, [rsp+0D8h+var_A0]
0x180014303  lea     rcx, [rsp+0D8h+Context]
0x180014308  call    ??$com_weak_query@AEAPEAUIUiaWindowNotifierCallback@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIUiaWindowNotifierCallback@@@Z; wil::com_weak_query<IUiaWindowNotifierCallback * &>(IUiaWindowNotifierCallback * &)
0x18001430d  nop
0x18001430e  lea     rcx, [rsi+40h]
0x180014312  lea     r8, [rsp+0D8h+var_90]
0x180014317  lea     rdx, [rsp+0D8h+ProviderId]
0x18001431c  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x180014321  mov     rcx, [rax]
0x180014324  add     rcx, 18h
0x180014328  lea     rdx, [rsp+0D8h+Context]
0x18001432d  call    ??4?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<IWeakReference,wil::err_exception_policy>::operator=(wil::com_ptr_t<IWeakReference,wil::err_exception_policy> &&)
0x180014332  nop
0x180014333  mov     rcx, [rsp+0D8h+Context]
0x180014338  test    rcx, rcx
0x18001433b  jz      short loc_18001434A
0x18001433d  mov     rax, [rcx]
0x180014340  mov     rax, [rax+10h]
0x180014344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014349  nop
0x18001434a  test    rbx, rbx
0x18001434d  jz      short loc_180014359
0x18001434f  mov     rcx, rbx; lpCriticalSection
0x180014352  call    cs:__imp_LeaveCriticalSection
0x180014358  nop
0x180014359  mov     rcx, [rsp+0D8h+var_A0]
0x18001435e  mov     rax, [rcx]
0x180014361  mov     r8, r15
0x180014364  lea     rdx, _GUID_6dc8c1be_86e5_4eef_8335_72cab53f06c8
0x18001436b  mov     rax, [rax]
0x18001436e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014373  mov     ebx, eax
0x180014375  test    eax, eax
0x180014377  jns     short loc_1800143B6
0x180014379  mov     rcx, [rsp+0D8h]; this
0x180014381  mov     r9d, eax; char *
0x180014384  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18001438b  mov     edx, 102h; void *
0x180014390  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014395  nop
0x180014396  mov     rcx, [rsp+0D8h+var_A0]
0x18001439b  test    rcx, rcx
0x18001439e  jz      short loc_1800143B2
0x1800143a0  mov     [rsp+0D8h+var_A0], rdi
0x1800143a5  mov     rax, [rcx]
0x1800143a8  mov     rax, [rax+10h]
0x1800143ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143b1  nop
0x1800143b2  mov     eax, ebx
0x1800143b4  jmp     short loc_1800143F8
0x1800143b6  mov     rcx, [rsp+0D8h+var_A0]
0x1800143bb  test    rcx, rcx
0x1800143be  jz      short loc_1800143D2
0x1800143c0  mov     [rsp+0D8h+var_A0], rdi
0x1800143c5  mov     rax, [rcx]
0x1800143c8  mov     rax, [rax+10h]
0x1800143cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143d1  nop
0x1800143d2  xor     eax, eax
0x1800143d4  jmp     short loc_1800143F8
0x1800143d6  mov     rcx, [rsp+0D8h+var_A0]
0x1800143db  test    rcx, rcx
0x1800143de  jz      short loc_1800143F4
0x1800143e0  xor     edi, edi
0x1800143e2  mov     [rsp+0D8h+var_A0], rdi
0x1800143e7  mov     rax, [rcx]
0x1800143ea  mov     rax, [rax+10h]
0x1800143ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f3  nop
0x1800143f4  mov     eax, dword ptr [rsp+0D8h+Context]
0x1800143f8  mov     rcx, [rsp+0D8h+var_40]
0x180014400  xor     rcx, rsp; StackCookie
0x180014403  call    __security_check_cookie
0x180014408  add     rsp, 0A8h
0x18001440f  pop     r15
0x180014411  pop     r14
0x180014413  pop     r12
0x180014415  pop     rdi
0x180014416  pop     rsi
0x180014417  pop     rbx
0x180014418  retn
```
