# HcfDetector::~HcfDetector(void)

- ea: `0x18001ff84`
- end: `0x180020034`
- name: `??1HcfDetector@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(wchar_t *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180022800`

## callees

- `0x18000c478`
- `0x18001fdc0`
- `0x18001fe30`
- `0x18001fea0`
- `0x18001ff84`
- `0x180021290`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fff8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fff8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020001`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020001`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ffea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ffea`

## string_xrefs

- `0x18001ffa0`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`

## pseudocode

```c
void __fastcall HcfDetector::~HcfDetector(wchar_t *this)
{
  struct _TP_TIMER *v2; // rdi
  volatile signed __int32 *v3; // rcx

  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
    (const wchar_t *)0xB4,
    (unsigned int)L"[WSAIFabricHost][HcfDetection] Stopping detector. detector=%p",
    this);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BGI_AA_impl_winrt__QEAA_XZ((__int64 *)this + 8);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BHI_AA_impl_winrt__QEAA_XZ((__int64 *)this + 6);
  __1__event_revoker_UIPackageCatalog_ApplicationModel_Windows_winrt___MP8type___abi_UIPackageCatalog_ApplicationModel_Windows_winrt__X_impl_4_EAAHUevent_token_4___E1___95674__BEI_AA_impl_winrt__QEAA_XZ((__int64 *)this + 4);
  if ( *((_QWORD *)this + 3) )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(this + 12);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x18001ff84  mov     [rsp+arg_0], rbx
0x18001ff89  push    rdi
0x18001ff8a  sub     rsp, 20h
0x18001ff8e  mov     rbx, rcx
0x18001ff91  lea     r8, aWsaifabrichost_8; "[WSAIFabricHost][HcfDetection] Stopping"...
0x18001ff98  mov     r9, rcx; wchar_t *
0x18001ff9b  mov     edx, 0B4h; wchar_t *
0x18001ffa0  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18001ffa7  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18001ffac  lea     rcx, [rbx+40h]
0x18001ffb0  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BGI@AA@impl@winrt@@QEAA@XZ
0x18001ffb5  lea     rcx, [rbx+30h]
0x18001ffb9  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BHI@AA@impl@winrt@@QEAA@XZ
0x18001ffbe  lea     rcx, [rbx+20h]
0x18001ffc2  call    ??1?$event_revoker@UIPackageCatalog@ApplicationModel@Windows@winrt@@$MP8type@?$abi@UIPackageCatalog@ApplicationModel@Windows@winrt@@X@impl@4@EAAHUevent_token@4@@_E1??_95674@$BEI@AA@impl@winrt@@QEAA@XZ
0x18001ffc7  lea     rcx, [rbx+18h]
0x18001ffcb  cmp     qword ptr [rcx], 0
0x18001ffcf  jz      short loc_18001FFD6
0x18001ffd1  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001ffd6  mov     rdi, [rbx+10h]
0x18001ffda  test    rdi, rdi
0x18001ffdd  jz      short loc_180020007
0x18001ffdf  xor     r9d, r9d; msWindowLength
0x18001ffe2  xor     r8d, r8d; msPeriod
0x18001ffe5  xor     edx, edx; pftDueTime
0x18001ffe7  mov     rcx, rdi; pti
0x18001ffea  call    cs:__imp_SetThreadpoolTimer
0x18001fff0  mov     edx, 1; fCancelPendingCallbacks
0x18001fff5  mov     rcx, rdi; pti
0x18001fff8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fffe  mov     rcx, rdi; pti
0x180020001  call    cs:__imp_CloseThreadpoolTimer
0x180020007  mov     rcx, [rbx+8]
0x18002000b  test    rcx, rcx
0x18002000e  jz      short loc_180020029
0x180020010  or      eax, 0FFFFFFFFh
0x180020013  lock xadd [rcx+0Ch], eax
0x180020018  cmp     eax, 1
0x18002001b  jnz     short loc_180020029
0x18002001d  mov     rax, [rcx]
0x180020020  mov     rax, [rax+8]
0x180020024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020029  mov     rbx, [rsp+28h+arg_0]
0x18002002e  add     rsp, 20h
0x180020032  pop     rdi
0x180020033  retn
```
