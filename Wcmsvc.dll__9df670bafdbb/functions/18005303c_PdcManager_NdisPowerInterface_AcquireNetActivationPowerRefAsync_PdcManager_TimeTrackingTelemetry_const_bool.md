# PdcManager::NdisPowerInterface::AcquireNetActivationPowerRefAsync(PdcManager::TimeTrackingTelemetry const &,bool)

- ea: `0x18005303c`
- end: `0x180053236`
- name: `?AcquireNetActivationPowerRefAsync@NdisPowerInterface@PdcManager@@QEAAXAEBVTimeTrackingTelemetry@2@_N@Z`
- size: `506`
- prototype: `void __fastcall(PdcManager::NdisPowerInterface *__hidden this, const struct PdcManager::TimeTrackingTelemetry *, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800543d4`
- `0x18009e058`

## callees

- `0x180010080`
- `0x180027630`
- `0x18003322c`
- `0x180034d80`
- `0x180035a68`
- `0x180035d3c`
- `0x18003a050`
- `0x18003a540`
- `0x180052d5c`
- `0x18005303c`
- `0x180073f44`
- `0x18007b57c`
- `0x180080cac`
- `0x180095294`
- `0x1800964b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800531d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800531ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800531d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800531ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005307e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005307e`

## string_xrefs

- `0x180053223`: `onecoreuap\net\wcm\service\base\server\pdcasyncpowersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall PdcManager::NdisPowerInterface::AcquireNetActivationPowerRefAsync(
        PdcManager::NdisPowerInterface *this,
        const struct PdcManager::TimeTrackingTelemetry *a2,
        bool a3)
{
  HANDLE FileW; // rax
  PdcManager *v7; // rcx
  const char *v8; // r9
  _QWORD *v9; // rax
  _QWORD *v10; // rdx
  int v11; // esi
  std::_Ref_count_base *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  const char *v15; // r9
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-40h] BYREF
  std::_Ref_count_base *v17; // [rsp+50h] [rbp-38h]
  LPCRITICAL_SECTION v18; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v19[5]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0x40000080u, 0);
  try
  {
    v19[0] = FileW;
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( a3 )
        PdcManager::ReportAsyncCompletionWaiterOneCompleted(v7);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdcasyncpowersession.cpp",
        v8);
    }
    v18 = 0;
    wil::EnterCriticalSection(&v18, this);
    v9 = (_QWORD *)std::make_shared<PdcManager::AsyncPowerSession,_GUID &,_NET_LUID_LH &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
                     &lpCriticalSection,
                     (char *)this + 104,
                     (char *)this + 120,
                     v19);
    v10 = (_QWORD *)*((_QWORD *)this + 6);
    if ( v10 == *((_QWORD **)this + 7) )
    {
      std::vector<std::shared_ptr<ClientContext>>::_Emplace_reallocate<std::shared_ptr<ClientContext>>(
        (char *)this + 40,
        v10,
        v9);
    }
    else
    {
      *v10 = 0;
      v10[1] = 0;
      *v10 = *v9;
      v10[1] = v9[1];
      *v9 = 0;
      v9[1] = 0;
      *((_QWORD *)this + 6) += 16LL;
    }
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    v11 = PdcManager::AsyncPowerSession::Acquire(*(PSRWLOCK *)(*((_QWORD *)this + 6) - 16LL), a2, a3);
    if ( v11 < 0 )
    {
      v12 = *(std::_Ref_count_base **)(*((_QWORD *)this + 6) - 8LL);
      if ( v12 )
        std::_Ref_count_base::_Decref(v12);
      *((_QWORD *)this + 6) -= 16LL;
    }
    if ( *((_QWORD *)this + 18) )
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        (char *)this + 144,
        0);
    v13 = *((_QWORD *)this + 17);
    if ( v13 )
    {
      if ( tip2::details::shared_data<1,0,0>::is_running(v13 + 8) )
      {
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::operator->(
                                 (char *)this + 136,
                                 &lpCriticalSection)
                  + 288LL) = v11;
        tip2::test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::~test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>(&lpCriticalSection);
        v14 = *((_QWORD *)this + 17);
        if ( v14 )
        {
          lpCriticalSection = 0;
          wil::EnterCriticalSection(&lpCriticalSection, v14 + 200);
          tip2::details::shared_data<1,0,0>::complete_helper(v14 + 8);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
        }
      }
    }
    PdcManager::NdisPowerInterface::ScavengeNqmNetActivatorPowerSessions(this);
    if ( v18 )
      LeaveCriticalSection(v18);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdcasyncpowersession.cpp",
      v15);
  }
}

```

## disassembly

```asm
0x18005303c  mov     rax, rsp
0x18005303f  mov     [rax+10h], rbx
0x180053043  push    rsi
0x180053044  push    rdi
0x180053045  push    r14
0x180053047  sub     rsp, 70h
0x18005304b  mov     sil, r8b
0x18005304e  mov     r14, rdx
0x180053051  mov     rdi, rcx
0x180053054  mov     [rsp+88h+var_48], r8b
0x180053059  mov     qword ptr [rax-58h], 0
0x180053061  mov     dword ptr [rax-60h], 40000080h
0x180053068  mov     dword ptr [rax-68h], 3
0x18005306f  xor     r9d, r9d; lpSecurityAttributes
0x180053072  xor     r8d, r8d; dwShareMode
0x180053075  xor     edx, edx; dwDesiredAccess
0x180053077  lea     rcx, FileName; "\\\\.\\NDIS"
0x18005307e  call    cs:__imp_CreateFileW
0x180053084  mov     [rsp+88h+var_28], rax
0x180053089  inc     rax
0x18005308c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180053092  jz      loc_180053211
0x180053098  mov     [rsp+88h+var_30], 0
0x1800530a1  mov     rdx, rdi
0x1800530a4  lea     rcx, [rsp+88h+var_30]
0x1800530a9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800530ae  nop
0x1800530af  lea     r8, [rdi+78h]
0x1800530b3  lea     rdx, [rdi+68h]
0x1800530b7  lea     r9, [rsp+88h+var_28]
0x1800530bc  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800530c1  call    ??$make_shared@VAsyncPowerSession@PdcManager@@AEAU_GUID@@AEAT_NET_LUID_LH@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@YA?AV?$shared_ptr@VAsyncPowerSession@PdcManager@@@0@AEAU_GUID@@AEAT_NET_LUID_LH@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::make_shared<PdcManager::AsyncPowerSession,_GUID &,_NET_LUID_LH &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(_GUID &,_NET_LUID_LH &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800530c6  mov     r8, rax
0x1800530c9  mov     rdx, [rdi+30h]
0x1800530cd  cmp     rdx, [rdi+38h]
0x1800530d1  jz      short loc_180053106
0x1800530d3  mov     qword ptr [rdx], 0
0x1800530da  mov     qword ptr [rdx+8], 0
0x1800530e2  mov     rax, [rax]
0x1800530e5  mov     [rdx], rax
0x1800530e8  mov     rax, [r8+8]
0x1800530ec  mov     [rdx+8], rax
0x1800530f0  mov     qword ptr [r8], 0
0x1800530f7  mov     qword ptr [r8+8], 0
0x1800530ff  add     qword ptr [rdi+30h], 10h
0x180053104  jmp     short loc_180053110
0x180053106  lea     rcx, [rdi+28h]
0x18005310a  call    ??$_Emplace_reallocate@V?$shared_ptr@VClientContext@@@std@@@?$vector@V?$shared_ptr@VClientContext@@@std@@V?$allocator@V?$shared_ptr@VClientContext@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VClientContext@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<ClientContext>>::_Emplace_reallocate<std::shared_ptr<ClientContext>>(std::shared_ptr<ClientContext> * const,std::shared_ptr<ClientContext> &&)
0x18005310f  nop
0x180053110  mov     rcx, [rsp+88h+var_38]; this
0x180053115  test    rcx, rcx
0x180053118  jz      short loc_180053120
0x18005311a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005311f  nop
0x180053120  mov     rcx, [rdi+30h]
0x180053124  mov     r8b, sil; bool
0x180053127  mov     rdx, r14; struct PdcManager::TimeTrackingTelemetry *
0x18005312a  mov     rcx, [rcx-10h]; SRWLock
0x18005312e  call    ?Acquire@AsyncPowerSession@PdcManager@@QEAAJAEBVTimeTrackingTelemetry@2@_N@Z; PdcManager::AsyncPowerSession::Acquire(PdcManager::TimeTrackingTelemetry const &,bool)
0x180053133  mov     esi, eax
0x180053135  test    eax, eax
0x180053137  jns     short loc_180053150
0x180053139  mov     rcx, [rdi+30h]
0x18005313d  mov     rcx, [rcx-8]; this
0x180053141  test    rcx, rcx
0x180053144  jz      short loc_18005314B
0x180053146  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005314b  add     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFF0h
0x180053150  lea     rcx, [rdi+90h]
0x180053157  cmp     qword ptr [rcx], 0
0x18005315b  jz      short loc_180053164
0x18005315d  xor     edx, edx
0x18005315f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180053164  lea     rbx, [rdi+88h]
0x18005316b  mov     rcx, [rbx]
0x18005316e  test    rcx, rcx
0x180053171  jz      short loc_1800531DB
0x180053173  add     rcx, 8
0x180053177  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18005317c  test    al, al
0x18005317e  jz      short loc_1800531DB
0x180053180  lea     rdx, [rsp+88h+lpCriticalSection]
0x180053185  mov     rcx, rbx
0x180053188  call    ??C?$tip_test@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::operator->(void)
0x18005318d  mov     rcx, [rax]
0x180053190  mov     [rcx+120h], esi
0x180053196  lea     rcx, [rsp+88h+lpCriticalSection]
0x18005319b  call    ??1?$test_data_control@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::~test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>(void)
0x1800531a0  mov     rbx, [rbx]
0x1800531a3  test    rbx, rbx
0x1800531a6  jz      short loc_1800531DB
0x1800531a8  mov     [rsp+88h+lpCriticalSection], 0
0x1800531b1  lea     rdx, [rbx+0C8h]
0x1800531b8  lea     rcx, [rsp+88h+lpCriticalSection]
0x1800531bd  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800531c2  lea     rcx, [rbx+8]
0x1800531c6  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestFlags@@W4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestFlags,TestQueryOptions)
0x1800531cb  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x1800531d0  test    rcx, rcx
0x1800531d3  jz      short loc_1800531DB
0x1800531d5  call    cs:__imp_LeaveCriticalSection
0x1800531db  mov     rcx, rdi; this
0x1800531de  call    ?ScavengeNqmNetActivatorPowerSessions@NdisPowerInterface@PdcManager@@AEAAXXZ; PdcManager::NdisPowerInterface::ScavengeNqmNetActivatorPowerSessions(void)
0x1800531e3  nop
0x1800531e4  mov     rcx, [rsp+88h+var_30]; lpCriticalSection
0x1800531e9  test    rcx, rcx
0x1800531ec  jz      short loc_1800531F5
0x1800531ee  call    cs:__imp_LeaveCriticalSection
0x1800531f4  nop
0x1800531f5  lea     rcx, [rsp+88h+var_28]
0x1800531fa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800531ff  nop
0x180053200  mov     rbx, [rsp+88h+arg_8]
0x180053208  add     rsp, 70h
0x18005320c  pop     r14
0x18005320e  pop     rdi
0x18005320f  pop     rsi
0x180053210  retn
0x180053211  test    sil, sil
0x180053214  jz      short loc_18005321B
0x180053216  call    ?ReportAsyncCompletionWaiterOneCompleted@PdcManager@@YAXXZ; PdcManager::ReportAsyncCompletionWaiterOneCompleted(void)
0x18005321b  mov     rcx, [rsp+88h]; this
0x180053223  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18005322a  mov     edx, 0DEh; void *
0x18005322f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
