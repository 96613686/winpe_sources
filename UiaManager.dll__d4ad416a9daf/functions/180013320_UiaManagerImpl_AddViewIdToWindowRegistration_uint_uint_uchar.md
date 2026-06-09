# UiaManagerImpl::AddViewIdToWindowRegistration(uint,uint,uchar)

- ea: `0x180013320`
- end: `0x1800136e6`
- name: `?AddViewIdToWindowRegistration@UiaManagerImpl@@UEAAJIIE@Z`
- size: `966`
- prototype: `__int64 __fastcall(UiaManagerImpl *__hidden this, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006edc`
- `0x180009340`
- `0x18000d2c8`
- `0x18000d474`
- `0x18000e448`
- `0x180013320`
- `0x180031540`
- `0x180043680`
- `0x180043a30`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013519`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001367e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001367e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013482`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013482`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001349d`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001349d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800134cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800134cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800133d6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800133d6`

## string_xrefs

- `0x180013362`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800133a8`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800136a4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800136bc`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800136d3`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UiaManagerImpl::AddViewIdToWindowRegistration(
        UiaManagerImpl *this,
        int a2,
        unsigned int a3,
        char a4)
{
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rdx
  __int64 result; // rax
  int v10; // r8d
  int v11; // r9d
  ULONGLONG *v12; // rbx
  _DWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  const char *v23; // r9
  int v24; // [rsp+20h] [rbp-78h]
  LPVOID Context; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-60h] BYREF
  WINBOOL fPending[2]; // [rsp+40h] [rbp-58h] BYREF
  GUID ProviderId; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v26 = a3;
  if ( !a2 )
  {
    v7 = retaddr;
    v8 = 271;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      v7,
      (void *)v8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      v24);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v7 = retaddr;
    v8 = 272;
    goto LABEL_3;
  }
  Context = 0;
  fPending[0] = 0;
  if ( __std_init_once_begin_initialize(
         &`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         fPending,
         &Context)
    && fPending[0] )
  {
    Context = &qword_1800C4F30;
    qword_1800C4F38 = 0;
    byte_1800C4F40 = 0;
    dword_1800C4F44 = 0;
    qword_1800C4F30 = (__int64)&UiaManagerTraceLoggingProvider::`vftable';
    CallbackContext = &`UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_::_lambda_invoker_cdecl_);
    v12 = (ULONGLONG *)CallbackContext;
    qword_1800C4F38 = (__int64)CallbackContext;
    byte_1800C4F40 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v12[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v12, v12 + 4) )
      EventSetInformation(v12[4], 2, v12[1], *(unsigned __int16 *)v12[1]);
    dword_1800C4F44 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C4F30 + 8))(&qword_1800C4F30);
    InitOnceComplete(&`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_1800C4F30);
  }
  v13 = (_DWORD *)*((_QWORD *)Context + 1);
  if ( *v13 > 4u )
  {
    fPending[0] = v26;
    LODWORD(Context) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&word_1800AD956,
      v10,
      v11,
      (__int64)&Context,
      (__int64)fPending);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
  try
  {
    *(_QWORD *)fPending = (char *)this + 768;
    _mm_lfence();
    v14 = *((_QWORD *)this + 11);
    v15 = *(_QWORD *)(v14
                    + 16
                    * (*((_QWORD *)this + 14)
                     & (0x100000001B3LL
                      * (HIBYTE(a2)
                       ^ (0x100000001B3LL
                        * (BYTE2(a2)
                         ^ (0x100000001B3LL
                          * (BYTE1(a2) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL)))))))))
                    + 8);
    if ( v15 == *((_QWORD *)this + 9) )
    {
LABEL_21:
      v15 = 0;
    }
    else
    {
      v16 = *(_QWORD *)(v14
                      + 16
                      * (*((_QWORD *)this + 14)
                       & (0x100000001B3LL
                        * (HIBYTE(a2)
                         ^ (0x100000001B3LL
                          * (BYTE2(a2)
                           ^ (0x100000001B3LL
                            * (BYTE1(a2) ^ (0x100000001B3LL * ((unsigned __int8)a2 ^ 0xCBF29CE484222325uLL))))))))));
      while ( a2 != *(_DWORD *)(v15 + 16) )
      {
        if ( v15 == v16 )
          goto LABEL_21;
        v15 = *(_QWORD *)(v15 + 8);
      }
    }
    if ( !v15 )
      v15 = *((_QWORD *)this + 9);
    if ( v15 == *((_QWORD *)this + 9) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80004005LL,
        v24);
    v17 = *(_QWORD *)(v15 + 24);
    Context = 0;
    wil::details::weak_query_policy::query<IUiaWindowRegistration>(v17, &Context);
    if ( !Context )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80004005LL,
        v24);
    LOBYTE(v18) = a4 != 0;
    v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)Context + 32LL))(Context, v26, v18);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)(unsigned int)v19,
        v24);
    v20 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Try_emplace<unsigned int const &,>(
                       (char *)this + 128,
                       &ProviderId,
                       &v26);
    v21 = *(_QWORD *)(v15 + 24);
    *(_QWORD *)(v15 + 24) = 0;
    v22 = *(_QWORD *)(v20 + 24);
    *(_QWORD *)(v20 + 24) = v21;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    std::_Hash<std::_Umap_traits<unsigned int,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>>>,0>(
      (char *)this + 64,
      &ProviderId,
      v15);
    if ( Context )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)Context + 16LL))(Context);
    if ( this != (UiaManagerImpl *)-768LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 768));
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x125,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                           v23);
  }
  return result;
}

```

## disassembly

```asm
0x180013320  mov     [rsp+arg_8], edx
0x180013324  push    rbx
0x180013325  push    rsi
0x180013326  push    rdi
0x180013327  push    r12
0x180013329  push    r13
0x18001332b  push    r14
0x18001332d  push    r15
0x18001332f  sub     rsp, 60h
0x180013333  mov     rax, cs:__security_cookie
0x18001333a  xor     rax, rsp
0x18001333d  mov     [rsp+98h+var_40], rax
0x180013342  movzx   r12d, r9b
0x180013346  mov     esi, edx
0x180013348  mov     r14, rcx
0x18001334b  mov     [rsp+98h+var_60], r8d
0x180013350  test    edx, edx
0x180013352  jnz     short loc_180013395
0x180013354  mov     rcx, [rsp+98h]; this
0x18001335c  mov     r9d, 80070057h; char *
0x180013362  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013369  mov     edx, 10Fh; void *
0x18001336e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013373  mov     eax, 80070057h
0x180013378  mov     rcx, [rsp+98h+var_40]
0x18001337d  xor     rcx, rsp; StackCookie
0x180013380  call    __security_check_cookie
0x180013385  add     rsp, 60h
0x180013389  pop     r15
0x18001338b  pop     r14
0x18001338d  pop     r13
0x18001338f  pop     r12
0x180013391  pop     rdi
0x180013392  pop     rsi
0x180013393  pop     rbx
0x180013394  retn
0x180013395  test    r8d, r8d
0x180013398  jnz     short loc_1800133B6
0x18001339a  mov     rcx, [rsp+98h]
0x1800133a2  mov     r9d, 80070057h
0x1800133a8  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800133af  mov     edx, 110h
0x1800133b4  jmp     short loc_18001336E
0x1800133b6  xor     r13d, r13d
0x1800133b9  mov     [rsp+98h+Context], r13
0x1800133be  mov     [rsp+98h+fPending], r13d
0x1800133c3  lea     r9, [rsp+98h+Context]; lpContext
0x1800133c8  lea     r8, [rsp+98h+fPending]; fPending
0x1800133cd  xor     edx, edx; dwFlags
0x1800133cf  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800133d6  call    cs:__imp___std_init_once_begin_initialize
0x1800133dc  test    eax, eax
0x1800133de  jz      loc_1800134D2
0x1800133e4  cmp     [rsp+98h+fPending], r13d
0x1800133e9  jz      loc_1800134D2
0x1800133ef  lea     r15, qword_1800C4F30
0x1800133f6  mov     [rsp+98h+Context], r15
0x1800133fb  mov     cs:qword_1800C4F38, r13
0x180013402  mov     cs:byte_1800C4F40, r13b
0x180013409  mov     cs:dword_1800C4F44, r13d
0x180013410  lea     rax, ??_7UiaManagerTraceLoggingProvider@@6B@; const UiaManagerTraceLoggingProvider::`vftable'
0x180013417  mov     cs:qword_1800C4F30, rax
0x18001341e  lea     rax, ?__hInner@?1???0StaticHandle@UiaManagerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180013425  mov     cs:CallbackContext, rax
0x18001342c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_@@CA@XZ; void (__cdecl *)()
0x180013433  call    atexit
0x180013438  mov     rbx, cs:CallbackContext
0x18001343f  mov     cs:qword_1800C4F38, rbx
0x180013446  mov     cs:byte_1800C4F40, 1
0x18001344d  mov     rax, [rbx+8]
0x180013451  movups  xmm0, xmmword ptr [rax-10h]
0x180013455  movups  xmmword ptr [rsp+98h+ProviderId.Data1], xmm0
0x18001345a  cmp     [rbx+20h], r13
0x18001345e  jz      short loc_180013467
0x180013460  mov     ecx, 5
0x180013465  int     29h; Win8: RtlFailFast(ecx)
0x180013467  mov     [rbx+28h], r13
0x18001346b  mov     [rbx+30h], r13
0x18001346f  lea     r9, [rbx+20h]; RegHandle
0x180013473  mov     r8, rbx; CallbackContext
0x180013476  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001347d  lea     rcx, [rsp+98h+ProviderId]; ProviderId
0x180013482  call    cs:__imp_EventRegister
0x180013488  test    eax, eax
0x18001348a  jnz     short loc_1800134A3
0x18001348c  mov     r8, [rbx+8]
0x180013490  movzx   r9d, word ptr [r8]
0x180013494  mov     edx, 2
0x180013499  mov     rcx, [rbx+20h]
0x18001349d  call    cs:__imp_EventSetInformation
0x1800134a3  mov     cs:dword_1800C4F44, 1
0x1800134ad  mov     rax, cs:qword_1800C4F30
0x1800134b4  mov     rcx, r15
0x1800134b7  mov     rax, [rax+8]
0x1800134bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c0  mov     r8, r15; lpContext
0x1800134c3  xor     edx, edx; dwFlags
0x1800134c5  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800134cc  call    cs:__imp_InitOnceComplete
0x1800134d2  mov     rax, [rsp+98h+Context]
0x1800134d7  mov     rcx, [rax+8]
0x1800134db  mov     eax, [rcx]
0x1800134dd  cmp     eax, 4
0x1800134e0  jbe     short loc_18001350F
0x1800134e2  mov     eax, [rsp+98h+var_60]
0x1800134e6  mov     [rsp+98h+fPending], eax
0x1800134ea  mov     dword ptr [rsp+98h+Context], esi
0x1800134ee  lea     rax, [rsp+98h+fPending]
0x1800134f3  mov     [rsp+98h+var_70], rax
0x1800134f8  lea     rax, [rsp+98h+Context]
0x1800134fd  mov     qword ptr [rsp+98h+var_78], rax; int
0x180013502  lea     rdx, word_1800AD956
0x180013509  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001350e  nop
0x18001350f  lea     rbx, [r14+300h]
0x180013516  mov     rcx, rbx; lpCriticalSection
0x180013519  call    cs:__imp_EnterCriticalSection
0x18001351f  mov     qword ptr [rsp+98h+fPending], rbx
0x180013524  lfence
0x180013527  movzx   ecx, sil
0x18001352b  mov     rax, 0CBF29CE484222325h
0x180013535  xor     rcx, rax
0x180013538  mov     rdx, 100000001B3h
0x180013542  imul    rcx, rdx
0x180013546  movzx   eax, byte ptr [rsp+98h+arg_8+1]
0x18001354e  xor     rcx, rax
0x180013551  imul    rcx, rdx
0x180013555  movzx   eax, byte ptr [rsp+98h+arg_8+2]
0x18001355d  xor     rcx, rax
0x180013560  imul    rcx, rdx
0x180013564  movzx   eax, byte ptr [rsp+98h+arg_8+3]
0x18001356c  xor     rcx, rax
0x18001356f  imul    rcx, rdx
0x180013573  and     rcx, [r14+70h]
0x180013577  add     rcx, rcx
0x18001357a  mov     rax, [r14+58h]
0x18001357e  mov     rdi, [rax+rcx*8+8]
0x180013583  cmp     rdi, [r14+48h]
0x180013587  jz      short loc_18001359E
0x180013589  mov     rax, [rax+rcx*8]
0x18001358d  nop     dword ptr [rax]
0x180013590  cmp     esi, [rdi+10h]
0x180013593  jz      short loc_1800135A1
0x180013595  cmp     rdi, rax
0x180013598  jnz     loc_180013695
0x18001359e  mov     rdi, r13
0x1800135a1  test    rdi, rdi
0x1800135a4  jnz     short loc_1800135AA
0x1800135a6  mov     rdi, [r14+48h]
0x1800135aa  mov     rcx, [rsp+98h]; this
0x1800135b2  cmp     rdi, [r14+48h]
0x1800135b6  jz      loc_18001369E
0x1800135bc  mov     rcx, [rdi+18h]
0x1800135c0  mov     [rsp+98h+Context], r13
0x1800135c5  lea     rdx, [rsp+98h+Context]
0x1800135ca  call    ??$query@UIUiaWindowRegistration@@@weak_query_policy@details@wil@@SAJPEAUIWeakReference@@PEAPEAUIUiaWindowRegistration@@@Z; wil::details::weak_query_policy::query<IUiaWindowRegistration>(IWeakReference *,IUiaWindowRegistration * *)
0x1800135cf  nop
0x1800135d0  mov     rcx, [rsp+98h+Context]
0x1800135d5  test    rcx, rcx
0x1800135d8  setz    al
0x1800135db  mov     r10, [rsp+98h]
0x1800135e3  test    al, al
0x1800135e5  jnz     loc_1800136B6
0x1800135eb  mov     rax, [rcx]
0x1800135ee  test    r12b, r12b
0x1800135f1  setnz   r8b
0x1800135f5  mov     edx, [rsp+98h+var_60]
0x1800135f9  mov     rax, [rax+20h]
0x1800135fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013602  mov     rcx, [rsp+98h]; this
0x18001360a  test    eax, eax
0x18001360c  js      loc_1800136D0
0x180013612  lea     rcx, [r14+80h]
0x180013619  lea     r8, [rsp+98h+var_60]
0x18001361e  lea     rdx, [rsp+98h+ProviderId]
0x180013623  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x180013628  mov     rdx, [rax]
0x18001362b  mov     rax, [rdi+18h]
0x18001362f  mov     [rdi+18h], r13
0x180013633  mov     rcx, [rdx+18h]
0x180013637  mov     [rdx+18h], rax
0x18001363b  test    rcx, rcx
0x18001363e  jz      short loc_18001364D
0x180013640  mov     rax, [rcx]
0x180013643  mov     rax, [rax+10h]
0x180013647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001364c  nop
0x18001364d  mov     r8, rdi
0x180013650  lea     rdx, [rsp+98h+ProviderId]
0x180013655  lea     rcx, [r14+40h]
0x180013659  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@IV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<uint,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>>>)
0x18001365e  nop
0x18001365f  mov     rcx, [rsp+98h+Context]
0x180013664  test    rcx, rcx
0x180013667  jz      short loc_180013676
0x180013669  mov     rax, [rcx]
0x18001366c  mov     rax, [rax+10h]
0x180013670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013675  nop
0x180013676  test    rbx, rbx
0x180013679  jz      short loc_180013685
0x18001367b  mov     rcx, rbx; lpCriticalSection
0x18001367e  call    cs:__imp_LeaveCriticalSection
0x180013684  nop
0x180013685  xor     eax, eax
0x180013687  jmp     loc_180013378
0x18001368c  mov     eax, dword ptr [rsp+98h+Context]
0x180013690  jmp     loc_180013378
0x180013695  mov     rdi, [rdi+8]
0x180013699  jmp     loc_180013590
0x18001369e  mov     r9d, 80004005h; char *
0x1800136a4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800136ab  mov     edx, 11Bh; void *
0x1800136b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800136b6  mov     r9d, 80004005h; char *
0x1800136bc  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800136c3  mov     edx, 11Fh; void *
0x1800136c8  mov     rcx, r10; this
0x1800136cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800136d0  mov     r9d, eax; char *
0x1800136d3  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800136da  mov     edx, 121h; void *
0x1800136df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
