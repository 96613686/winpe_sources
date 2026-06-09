# ADPService::AdpServiceTraits::try_stop_service<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)

- ea: `0x180010a40`
- end: `0x180010b63`
- name: `??$try_stop_service@UAggregatedDataPlatform@1Internal@Windows@winrt@@@AdpServiceTraits@ADPService@@SA_NXZ`
- size: `291`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ff90`

## callees

- `0x180001008`
- `0x18000e1d0`
- `0x18000f148`
- `0x180010824`
- `0x180010a40`
- `0x180025ac8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ae2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ae2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010a6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010a6c`

## string_xrefs

- `0x180010a52`: `Service stopping.`

## pseudocode

```c
__int64 ADPService::AdpServiceTraits::try_stop_service<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>()
{
  __int64 v0; // rbp
  RTL_SRWLOCK *v1; // rsi
  __int64 **v2; // rdi
  __int64 **i; // rbx
  _QWORD *v4; // r14
  _DWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  volatile signed __int32 *v8; // rbx
  _QWORD *v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+58h] [rbp+10h]

  ADPTraceLoggingProvider::TraceLoggingInfo("Service stopping.");
  v0 = ADPService::g_databaseManager;
  v1 = (RTL_SRWLOCK *)(ADPService::g_databaseManager + 64);
  AcquireSRWLockExclusive((PSRWLOCK)(ADPService::g_databaseManager + 64));
  v11 = v1;
  v2 = *(__int64 ***)(v0 + 8);
  for ( i = (__int64 **)*v2; i != v2; i = (__int64 **)*i )
  {
    v4 = i + 2;
    if ( (unsigned __int64)i[5] > 7 )
      v4 = (_QWORD *)*v4;
    v5 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
    if ( *v5 > 5u )
    {
      v10 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (_DWORD)v5,
        (unsigned int)byte_18010042B,
        v6,
        v7,
        (__int64)&v10);
    }
    (*(void (__fastcall **)(__int64 *))(*i[6] + 8))(i[6]);
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::clear(v0);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  ADPService::g_databaseManager = 0;
  v8 = (volatile signed __int32 *)qword_18010F9B0;
  qword_18010F9B0 = 0;
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  ADPTraceLoggingProvider::TraceLoggingInfo("Database manager has been shut down.");
  return wil::svchost_service_traits__ADPService::c_serviceName__wil::defaultShutdownDelay_::try_stop_service_winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform_();
}

```

## disassembly

```asm
0x180010a40  mov     [rsp+arg_10], rbx
0x180010a45  mov     [rsp+arg_18], rbp
0x180010a4a  push    rsi
0x180010a4b  push    rdi
0x180010a4c  push    r14
0x180010a4e  sub     rsp, 30h
0x180010a52  lea     rcx, aServiceStoppin; "Service stopping."
0x180010a59  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180010a5e  mov     rbp, cs:?g_databaseManager@ADPService@@3V?$shared_ptr@VDatabaseManager@@@std@@A; std::shared_ptr<DatabaseManager> ADPService::g_databaseManager
0x180010a65  lea     rsi, [rbp+40h]
0x180010a69  mov     rcx, rsi; SRWLock
0x180010a6c  call    cs:__imp_AcquireSRWLockExclusive
0x180010a72  mov     [rsp+48h+arg_8], rsi
0x180010a77  mov     rdi, [rbp+8]
0x180010a7b  mov     rbx, [rdi]
0x180010a7e  cmp     rbx, rdi
0x180010a81  jz      short loc_180010AD1
0x180010a83  lea     r14, [rbx+10h]
0x180010a87  cmp     qword ptr [rbx+28h], 7
0x180010a8c  jbe     short loc_180010A91
0x180010a8e  mov     r14, [r14]
0x180010a91  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180010a96  mov     rcx, [rax+8]
0x180010a9a  mov     eax, [rcx]
0x180010a9c  cmp     eax, 5
0x180010a9f  jbe     short loc_180010ABC
0x180010aa1  mov     [rsp+48h+arg_0], r14
0x180010aa6  lea     rax, [rsp+48h+arg_0]
0x180010aab  mov     [rsp+48h+var_28], rax
0x180010ab0  lea     rdx, byte_18010042B
0x180010ab7  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180010abc  mov     rcx, [rbx+30h]
0x180010ac0  mov     rax, [rcx]
0x180010ac3  mov     rax, [rax+8]
0x180010ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010acc  mov     rbx, [rbx]
0x180010acf  jmp     short loc_180010A7E
0x180010ad1  mov     rcx, rbp
0x180010ad4  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VADPDatabase@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<ADPDatabase>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ADPDatabase>>>,0>>::clear(void)
0x180010ad9  nop
0x180010ada  test    rsi, rsi
0x180010add  jz      short loc_180010AE8
0x180010adf  mov     rcx, rsi; SRWLock
0x180010ae2  call    cs:__imp_ReleaseSRWLockExclusive
0x180010ae8  mov     cs:?g_databaseManager@ADPService@@3V?$shared_ptr@VDatabaseManager@@@std@@A, 0; std::shared_ptr<DatabaseManager> ADPService::g_databaseManager
0x180010af3  mov     rbx, cs:qword_18010F9B0
0x180010afa  mov     cs:qword_18010F9B0, 0
0x180010b05  test    rbx, rbx
0x180010b08  jz      short loc_180010B40
0x180010b0a  or      edi, 0FFFFFFFFh
0x180010b0d  mov     eax, edi
0x180010b0f  lock xadd [rbx+8], eax
0x180010b14  add     eax, edi
0x180010b16  jnz     short loc_180010B40
0x180010b18  mov     rax, [rbx]
0x180010b1b  mov     rcx, rbx
0x180010b1e  mov     rax, [rax]
0x180010b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b26  mov     eax, edi
0x180010b28  lock xadd [rbx+0Ch], eax
0x180010b2d  add     eax, edi
0x180010b2f  jnz     short loc_180010B40
0x180010b31  mov     rax, [rbx]
0x180010b34  mov     rcx, rbx
0x180010b37  mov     rax, [rax+8]
0x180010b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b40  lea     rcx, aDatabaseManage; "Database manager has been shut down."
0x180010b47  call    ?TraceLoggingInfo@ADPTraceLoggingProvider@@SAXPEBDZZ; ADPTraceLoggingProvider::TraceLoggingInfo(char const *,...)
0x180010b4c  mov     rbx, [rsp+48h+arg_10]
0x180010b51  mov     rbp, [rsp+48h+arg_18]
0x180010b56  add     rsp, 30h
0x180010b5a  pop     r14
0x180010b5c  pop     rdi
0x180010b5d  pop     rsi
0x180010b5e  jmp     wil__svchost_service_traits__ADPService__c_serviceName__wil__defaultShutdownDelay___try_stop_service_winrt__Windows__Internal__AggregatedDataPlatform__AggregatedDataPlatform_
```
