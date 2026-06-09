# PdcManager::NdisPowerInterface::ReleaseNetActivationPowerRefAsync(PdcManager::TimeTrackingTelemetry const &,bool)

- ea: `0x18005323c`
- end: `0x1800533a7`
- name: `?ReleaseNetActivationPowerRefAsync@NdisPowerInterface@PdcManager@@QEAAXAEBVTimeTrackingTelemetry@2@_N@Z`
- size: `363`
- prototype: `void __fastcall(PdcManager::NdisPowerInterface *__hidden this, const struct PdcManager::TimeTrackingTelemetry *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009e058`

## callees

- `0x18002706c`
- `0x180027630`
- `0x18003322c`
- `0x180035a68`
- `0x180037484`
- `0x18003a050`
- `0x180041544`
- `0x180052d30`
- `0x18005323c`
- `0x180073f44`
- `0x180075418`
- `0x180095294`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053326`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800532ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800532ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800532d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800532d3`

## string_xrefs

- `0x180053394`: `onecoreuap\net\wcm\service\base\server\pdcasyncpowersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PdcManager::NdisPowerInterface::ReleaseNetActivationPowerRefAsync(
        PdcManager::NdisPowerInterface *this,
        const struct PdcManager::TimeTrackingTelemetry *a2,
        bool a3)
{
  PdcManager *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  PTP_TIMER *v9; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  __int128 v11; // xmm6
  int v13; // r8d
  int v14; // r9d
  const char *v15; // r9
  unsigned int v16[4]; // [rsp+20h] [rbp-48h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v18[2]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, this);
  v8 = *((_QWORD *)this + 6);
  if ( *((_QWORD *)this + 5) == v8 )
  {
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18013A120, 0, v7) )
      {
        *(_QWORD *)v18 = (char *)this + 104;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
          (_DWORD)v6,
          (unsigned int)&byte_180114AFF,
          v13,
          v14,
          (__int64)v18);
      }
    }
    if ( a3 )
      PdcManager::ReportAsyncCompletionWaiterOneCompleted(v6);
    try
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdcasyncpowersession.cpp",
        (const char *)0x490,
        v16[0]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x12B,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\server\\pdcasyncpowersession.cpp",
        v15);
      return;
    }
  }
  if ( PdcManager::AsyncPowerSession::Release(*(PdcManager::AsyncPowerSession **)(v8 - 16), a2, a3) >= 0 )
  {
    v9 = (PTP_TIMER *)((char *)this + 144);
    if ( !*((_QWORD *)this + 18) )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(PdcManager::NdisPowerInterface::TimerCallback, this, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        (char *)this + 144,
        ThreadpoolTimer);
    }
    if ( *v9 )
      SetThreadpoolTimer(*v9, (PFILETIME)&PdcManager::NdisPowerInterface::c_timerPeriod, 0, 0);
    tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::start(
      (char *)this + 136,
      v18);
    v11 = *(_OWORD *)((char *)this + 104);
    *(_OWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::operator->(
                             (char *)this + 136,
                             v18)
              + 272LL) = v11;
    tip2::test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::~test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>(v18);
  }
  PdcManager::NdisPowerInterface::ScavengeNqmNetActivatorPowerSessions(this);
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18005323c  mov     rax, rsp
0x18005323f  mov     [rax+10h], rbx
0x180053243  mov     [rax+20h], rsi
0x180053247  push    rdi
0x180053248  sub     rsp, 60h
0x18005324c  movaps  xmmword ptr [rax-18h], xmm6
0x180053250  mov     bl, r8b
0x180053253  mov     rsi, rdx
0x180053256  mov     rdi, rcx
0x180053259  mov     qword ptr [rax-38h], 0
0x180053261  mov     rdx, rcx
0x180053264  lea     rcx, [rax-38h]
0x180053268  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005326d  nop
0x18005326e  mov     rax, [rdi+30h]
0x180053272  cmp     [rdi+28h], rax
0x180053276  jz      loc_180053344
0x18005327c  mov     r8b, bl; bool
0x18005327f  mov     rdx, rsi; struct PdcManager::TimeTrackingTelemetry *
0x180053282  mov     rcx, [rax-10h]; this
0x180053286  call    ?Release@AsyncPowerSession@PdcManager@@QEAAJAEBVTimeTrackingTelemetry@2@_N@Z; PdcManager::AsyncPowerSession::Release(PdcManager::TimeTrackingTelemetry const &,bool)
0x18005328b  test    eax, eax
0x18005328d  js      loc_180053313
0x180053293  lea     rbx, [rdi+90h]
0x18005329a  cmp     qword ptr [rbx], 0
0x18005329e  jnz     short loc_1800532BE
0x1800532a0  xor     r8d, r8d; pcbe
0x1800532a3  mov     rdx, rdi; pv
0x1800532a6  lea     rcx, ?TimerCallback@NdisPowerInterface@PdcManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800532ad  call    cs:__imp_CreateThreadpoolTimer
0x1800532b3  mov     rdx, rax
0x1800532b6  mov     rcx, rbx
0x1800532b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800532be  mov     rcx, [rbx]; pti
0x1800532c1  test    rcx, rcx
0x1800532c4  jz      short loc_1800532D9
0x1800532c6  xor     r9d, r9d; msWindowLength
0x1800532c9  xor     r8d, r8d; msPeriod
0x1800532cc  lea     rdx, ?c_timerPeriod@NdisPowerInterface@PdcManager@@0U_FILETIME@@B; pftDueTime
0x1800532d3  call    cs:__imp_SetThreadpoolTimer
0x1800532d9  lea     rbx, [rdi+88h]
0x1800532e0  lea     rdx, [rsp+68h+var_30]
0x1800532e5  mov     rcx, rbx
0x1800532e8  call    ?start@?$tip_test@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::start(void)
0x1800532ed  movups  xmm6, xmmword ptr [rdi+68h]
0x1800532f1  lea     rdx, [rsp+68h+var_30]
0x1800532f6  mov     rcx, rbx
0x1800532f9  call    ??C?$tip_test@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::operator->(void)
0x1800532fe  mov     rdx, [rax]
0x180053301  movdqu  xmmword ptr [rdx+110h], xmm6
0x180053309  lea     rcx, [rsp+68h+var_30]
0x18005330e  call    ??1?$test_data_control@V?$merged_data@U_tip_ReturnedToFullPowerTest@NdisPowerInterface@PdcManager@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>::~test_data_control<tip2::details::merged_data<PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest,PdcManager::NdisPowerInterface::_tip_ReturnedToFullPowerTest>>(void)
0x180053313  mov     rcx, rdi; this
0x180053316  call    ?ScavengeNqmNetActivatorPowerSessions@NdisPowerInterface@PdcManager@@AEAAXXZ; PdcManager::NdisPowerInterface::ScavengeNqmNetActivatorPowerSessions(void)
0x18005331b  nop
0x18005331c  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180053321  test    rcx, rcx
0x180053324  jz      short loc_18005332D
0x180053326  call    cs:__imp_LeaveCriticalSection
0x18005332c  nop
0x18005332d  lea     r11, [rsp+68h+var_8]
0x180053332  mov     rbx, [r11+18h]
0x180053336  mov     rsi, [r11+28h]
0x18005333a  movaps  xmm6, [rsp+68h+var_18]
0x18005333f  mov     rsp, r11
0x180053342  pop     rdi
0x180053343  retn
0x180053344  mov     eax, cs:dword_18013A120
0x18005334a  cmp     eax, 5
0x18005334d  jbe     short loc_180053380
0x18005334f  xor     edx, edx
0x180053351  lea     rcx, dword_18013A120
0x180053358  call    _tlgKeywordOn
0x18005335d  test    al, al
0x18005335f  jz      short loc_180053380
0x180053361  lea     rax, [rdi+68h]
0x180053365  mov     qword ptr [rsp+68h+var_30], rax
0x18005336a  lea     rax, [rsp+68h+var_30]
0x18005336f  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x180053374  lea     rdx, byte_180114AFF
0x18005337b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180053380  test    bl, bl
0x180053382  jz      short loc_180053389
0x180053384  call    ?ReportAsyncCompletionWaiterOneCompleted@PdcManager@@YAXXZ; PdcManager::ReportAsyncCompletionWaiterOneCompleted(void)
0x180053389  mov     rcx, [rsp+68h]; this
0x18005338e  mov     r9d, 490h; char *
0x180053394  lea     r8, aOnecoreuapNetW_20; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18005339b  mov     edx, 115h; void *
0x1800533a0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
