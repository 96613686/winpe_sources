# Windows::Globalization::Spelling::PublishWnfWithEnsureIntervalFromLastPublish(SpellerDictionaryRequest const &)

- ea: `0x18004473c`
- end: `0x1800448d6`
- name: `?PublishWnfWithEnsureIntervalFromLastPublish@Spelling@Globalization@Windows@@YAXAEBUSpellerDictionaryRequest@@@Z`
- size: `410`
- prototype: `void __fastcall(Windows::Globalization::Spelling *__hidden this, const struct SpellerDictionaryRequest *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005bdf4`
- `0x180088210`
- `0x1800884f4`

## callees

- `0x180043b58`
- `0x18004473c`
- `0x1800448dc`
- `0x180044c28`
- `0x180044cf4`
- `0x18006181c`
- `0x180061b0c`
- `0x180061b74`
- `0x1800875cc`
- `0x1800881d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800447f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800447f2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044866`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180044866`
- `ntdll!RtlPublishWnfStateData` at `0x1800448c0`
- `ntdll!RtlPublishWnfStateData` at `0x1800448c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800447dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800447dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Globalization::Spelling::PublishWnfWithEnsureIntervalFromLastPublish(
        Windows::Globalization::Spelling *this,
        const struct SpellerDictionaryRequest *a2)
{
  __int64 v3; // rbx
  ULONGLONG TickCount64; // rsi
  __int64 v5; // rbx
  __int64 v6; // rcx
  char v7; // di
  __int64 v8; // rcx
  PVOID v9; // rdx
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+10h] BYREF

  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180140850 > *(_DWORD *)(v3 + 8) )
  {
    Init_thread_header(&dword_180140850);
    if ( dword_180140850 == -1 )
    {
      atexit(Windows::Globalization::Spelling::PublishWnfWithEnsureIntervalFromLastPublish_::_2_::_dynamic_atexit_destructor_for__delayedWnfTimer__);
      Init_thread_footer(&dword_180140850);
    }
  }
  if ( dword_180140854 > *(_DWORD *)(v3 + 8) )
  {
    Init_thread_header(&dword_180140854);
    if ( dword_180140854 == -1 )
    {
      std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&qword_180140820);
      atexit(Windows::Globalization::Spelling::PublishWnfWithEnsureIntervalFromLastPublish_::_2_::_dynamic_atexit_destructor_for__requestQueue__);
      Init_thread_footer(&dword_180140854);
    }
  }
  TickCount64 = GetTickCount64();
  v5 = 0;
  AcquireSRWLockExclusive(&stru_1801405F8);
  v11 = &stru_1801405F8;
  if ( qword_180140840 )
  {
    std::queue<SpellerDictionaryRequest>::emplace<SpellerDictionaryRequest const &>(v6, this);
  }
  else
  {
    v7 = 0;
    if ( TickCount64 >= qword_180140600 + 300 )
      goto LABEL_12;
    std::queue<SpellerDictionaryRequest>::emplace<SpellerDictionaryRequest const &>(v6, this);
    v5 = qword_180140600 - TickCount64 + 300;
  }
  v7 = 1;
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v7 )
  {
    v9 = pti;
    if ( !pti )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(lambda_1d54173519b73f8b562e569f727d80f8_::_lambda_invoker_cdecl_, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        &pti,
        ThreadpoolTimer);
      v9 = pti;
    }
    if ( v5 )
      lambda_470d511cdce4992e1f4e48efb5fa4862_::operator()(v8, v9, v5);
    LODWORD(v11) = qword_180140840;
    SpellingTelemetry::PublishWnfIsDelayed<unsigned int>(&v11);
  }
  else
  {
    RtlPublishWnfStateData(WNF_DICT_CONTENT_ADDED, 0, this, 528, 0);
    qword_180140600 = TickCount64;
  }
}

```

## disassembly

```asm
0x18004473c  push    rbx
0x18004473e  push    rbp
0x18004473f  push    rsi
0x180044740  push    rdi
0x180044741  sub     rsp, 38h
0x180044745  mov     rbp, rcx
0x180044748  mov     edx, cs:_tls_index
0x18004474e  mov     rax, gs:58h
0x180044757  mov     edi, 8
0x18004475c  mov     rbx, [rax+rdx*8]
0x180044760  mov     eax, [rbx+rdi]
0x180044763  cmp     cs:dword_180140850, eax
0x180044769  jle     short loc_180044798
0x18004476b  lea     rcx, dword_180140850
0x180044772  call    _Init_thread_header
0x180044777  cmp     cs:dword_180140850, 0FFFFFFFFh
0x18004477e  jnz     short loc_180044798
0x180044780  lea     rcx, _Windows__Globalization__Spelling__PublishWnfWithEnsureIntervalFromLastPublish____2____dynamic_atexit_destructor_for__delayedWnfTimer__; void (__cdecl *)()
0x180044787  call    atexit
0x18004478c  lea     rcx, dword_180140850
0x180044793  call    _Init_thread_footer
0x180044798  mov     eax, [rbx+rdi]
0x18004479b  cmp     cs:dword_180140854, eax
0x1800447a1  jle     short loc_1800447DD
0x1800447a3  lea     rcx, dword_180140854
0x1800447aa  call    _Init_thread_header
0x1800447af  cmp     cs:dword_180140854, 0FFFFFFFFh
0x1800447b6  jnz     short loc_1800447DD
0x1800447b8  lea     rcx, qword_180140820
0x1800447bf  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800447c4  lea     rcx, _Windows__Globalization__Spelling__PublishWnfWithEnsureIntervalFromLastPublish____2____dynamic_atexit_destructor_for__requestQueue__; void (__cdecl *)()
0x1800447cb  call    atexit
0x1800447d0  nop
0x1800447d1  lea     rcx, dword_180140854
0x1800447d8  call    _Init_thread_footer
0x1800447dd  call    cs:__imp_GetTickCount64
0x1800447e3  mov     rsi, rax
0x1800447e6  xor     ebx, ebx
0x1800447e8  lea     rdi, stru_1801405F8
0x1800447ef  mov     rcx, rdi; SRWLock
0x1800447f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800447f8  mov     [rsp+58h+arg_8], rdi
0x1800447fd  cmp     cs:qword_180140840, rbx
0x180044804  jz      short loc_180044810
0x180044806  mov     rdx, rbp
0x180044809  call    ??$emplace@AEBUSpellerDictionaryRequest@@@?$queue@USpellerDictionaryRequest@@V?$deque@USpellerDictionaryRequest@@V?$allocator@USpellerDictionaryRequest@@@std@@@std@@@std@@QEAA?A_TAEBUSpellerDictionaryRequest@@@Z
0x18004480e  jmp     short loc_18004483E
0x180044810  xor     dil, dil
0x180044813  mov     rax, cs:qword_180140600
0x18004481a  add     rax, 12Ch
0x180044820  cmp     rsi, rax
0x180044823  jnb     short loc_180044841
0x180044825  mov     rdx, rbp
0x180044828  call    ??$emplace@AEBUSpellerDictionaryRequest@@@?$queue@USpellerDictionaryRequest@@V?$deque@USpellerDictionaryRequest@@V?$allocator@USpellerDictionaryRequest@@@std@@@std@@@std@@QEAA?A_TAEBUSpellerDictionaryRequest@@@Z
0x18004482d  mov     rbx, cs:qword_180140600
0x180044834  sub     rbx, rsi
0x180044837  add     rbx, 12Ch
0x18004483e  mov     dil, 1
0x180044841  lea     rcx, [rsp+58h+arg_8]
0x180044846  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004484b  test    dil, dil
0x18004484e  jz      short loc_1800448A5
0x180044850  mov     rdx, cs:pti; pv
0x180044857  test    rdx, rdx
0x18004485a  jnz     short loc_180044882
0x18004485c  xor     r8d, r8d; pcbe
0x18004485f  lea     rcx, _lambda_1d54173519b73f8b562e569f727d80f8____lambda_invoker_cdecl_; pfnti
0x180044866  call    cs:__imp_CreateThreadpoolTimer
0x18004486c  mov     rdx, rax
0x18004486f  lea     rcx, pti
0x180044876  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18004487b  mov     rdx, cs:pti
0x180044882  test    rbx, rbx
0x180044885  jz      short loc_18004488F
0x180044887  mov     r8, rbx
0x18004488a  call    _lambda_470d511cdce4992e1f4e48efb5fa4862___operator__
0x18004488f  mov     eax, dword ptr cs:qword_180140840
0x180044895  mov     dword ptr [rsp+58h+arg_8], eax
0x180044899  lea     rcx, [rsp+58h+arg_8]
0x18004489e  call    ??$PublishWnfIsDelayed@I@SpellingTelemetry@@SAX$$QEAI@Z; SpellingTelemetry::PublishWnfIsDelayed<uint>(uint &&)
0x1800448a3  jmp     short loc_1800448CD
0x1800448a5  mov     [rsp+58h+var_38], 0
0x1800448ae  mov     r9d, 210h
0x1800448b4  mov     r8, rbp
0x1800448b7  xor     edx, edx
0x1800448b9  mov     rcx, cs:WNF_DICT_CONTENT_ADDED
0x1800448c0  call    cs:__imp_RtlPublishWnfStateData
0x1800448c6  mov     cs:qword_180140600, rsi
0x1800448cd  add     rsp, 38h
0x1800448d1  pop     rdi
0x1800448d2  pop     rsi
0x1800448d3  pop     rbp
0x1800448d4  pop     rbx
0x1800448d5  retn
```
