# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer(winrt::Windows::System::Threading::ThreadPoolTimer const &)

- ea: `0x180022b40`
- end: `0x180022ceb`
- name: `?RefreshTimer@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUThreadPoolTimer@Threading@System@56@@Z`
- size: `427`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this, const struct winrt::Windows::System::Threading::ThreadPoolTimer *)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020e08`
- `0x180021d80`
- `0x180022da0`
- `0x180022f5c`

## callees

- `0x1800072d8`
- `0x180007924`
- `0x18000dfc0`
- `0x18001a71c`
- `0x18001da2c`
- `0x18001eca0`
- `0x180020974`
- `0x180022b40`
- `0x180022e0c`
- `0x180023d68`
- `0x180024718`
- `0x180024c6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer(
        winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *this,
        const struct winrt::Windows::System::Threading::ThreadPoolTimer *a2)
{
  _QWORD *v3; // rdi
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 **); // rcx
  const char *v5; // r9
  __int64 v6; // [rsp+20h] [rbp-58h] BYREF
  __int64 v7; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v8[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v9; // [rsp+38h] [rbp-40h] BYREF
  int v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+44h] [rbp-34h]
  _BYTE v12[16]; // [rsp+48h] [rbp-30h] BYREF
  __int64 *v13; // [rsp+58h] [rbp-20h] BYREF
  __int64 *v14; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v16; // [rsp+90h] [rbp+18h] BYREF
  __int64 v17; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveExpiredSessions(this);
    winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::TryGetNextExpiringTime(this, v12);
    if ( !v12[8]
      || *(_QWORD *)std::optional<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::value(v12) == 0x7FFFFFFFFFFFFFFFLL )
    {
      v16 = 0;
      winrt::Windows::Foundation::IUnknown::operator=((char *)this + 184, &v16);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v16);
    }
    else
    {
      v3 = (_QWORD *)winrt::clock::now(v8);
      v7 = *(_QWORD *)std::optional<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::value(v12)
         - *v3;
      winrt::impl::root_implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_weak<winrt::Windows::UI::Shell::implementation::FocusSessionManager>(
        this,
        &v6);
      v9 = (__int64 *)winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer;
      v10 = 0;
      v11 = HIDWORD(v14);
      ____0UFocusSessionThemeManager_implementation_Shell_Internal_Windows_winrt__P8012345_EAAXAEBUThreadPoolTimer_Threading_System_45___E_TimerElapsedHandler_Threading_System_Windows_winrt__QEAA___QEAU__weak_ref_UFocusSessionThemeManager_implementation_Shell_Internal_Windows_winrt___4___QEAP8FocusSessionThemeManager_implementation_Shell_Internal_34_EAAXAEBUThreadPoolTimer_1234___E_Z(
        &v17,
        &v6,
        &v9);
      v13 = &v17;
      v14 = &v7;
      v9 = &qword_180046CB8;
      _InterlockedIncrement64(&qword_180046CB8);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> )
      {
        _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(
          &v13,
          &v16,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>);
        _InterlockedDecrement64(&qword_180046CB8);
      }
      else
      {
        _InterlockedDecrement64(&qword_180046CB8);
        winrt::impl::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::call<_lambda_b19cf72fe9674443383aa89d5c22450b_ &>(
          v4,
          (__int64)&v16,
          (__int64)&v13);
      }
      winrt::Windows::Foundation::IUnknown::operator=((char *)this + 184, &v16);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v16);
      if ( v17 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
      if ( v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v6);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussessio"
                    "nthememanager.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180022b40  mov     [rsp+arg_0], rbx
0x180022b45  push    rdi
0x180022b46  sub     rsp, 70h
0x180022b4a  mov     rbx, rcx
0x180022b4d  call    ?RemoveExpiredSessions@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RemoveExpiredSessions(void)
0x180022b52  lea     rdx, [rsp+78h+var_30]
0x180022b57  mov     rcx, rbx
0x180022b5a  call    ?TryGetNextExpiringTime@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAA?AV?$optional@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@XZ; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::TryGetNextExpiringTime(void)
0x180022b5f  cmp     [rsp+78h+var_28], 0
0x180022b64  jz      loc_180022CAD
0x180022b6a  lea     rcx, [rsp+78h+var_30]
0x180022b6f  call    ?value@?$optional@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@QEGBAAEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@2@XZ; std::optional<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::value(void)
0x180022b74  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180022b7e  cmp     [rax], rcx
0x180022b81  jz      loc_180022CAD
0x180022b87  lea     rcx, [rsp+78h+var_48]
0x180022b8c  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180022b91  mov     rdi, rax
0x180022b94  lea     rcx, [rsp+78h+var_30]
0x180022b99  call    ?value@?$optional@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@QEGBAAEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@2@XZ; std::optional<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::value(void)
0x180022b9e  mov     rax, [rax]
0x180022ba1  sub     rax, [rdi]
0x180022ba4  mov     [rsp+78h+var_50], rax
0x180022ba9  lea     rdx, [rsp+78h+var_58]
0x180022bae  mov     rcx, rbx
0x180022bb1  call    ??$get_weak@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@?$root_implements@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@U13456@@impl@winrt@@IEAA?AU?$weak_ref@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@2@XZ; winrt::impl::root_implements<winrt::Windows::UI::Shell::implementation::FocusSessionManager,winrt::Windows::UI::Shell::FocusSessionManager>::get_weak<winrt::Windows::UI::Shell::implementation::FocusSessionManager>(void)
0x180022bb6  nop
0x180022bb7  lea     rax, ?RefreshTimer@FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@AEAAXAEBUThreadPoolTimer@Threading@System@56@@Z; winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer(winrt::Windows::System::Threading::ThreadPoolTimer const &)
0x180022bbe  mov     [rsp+78h+var_40], rax
0x180022bc3  mov     [rsp+78h+var_38], 0
0x180022bcb  mov     eax, [rsp+78h+var_14]
0x180022bcf  mov     [rsp+78h+var_34], eax
0x180022bd3  lea     r8, [rsp+78h+var_40]
0x180022bd8  lea     rdx, [rsp+78h+var_58]
0x180022bdd  lea     rcx, [rsp+78h+arg_18]
0x180022be5  call    ??$?0UFocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@P8012345@EAAXAEBUThreadPoolTimer@Threading@System@45@@_E@TimerElapsedHandler@Threading@System@Windows@winrt@@QEAA@$$QEAU?$weak_ref@UFocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@@4@$$QEAP8FocusSessionThemeManager@implementation@Shell@Internal@34@EAAXAEBUThreadPoolTimer@1234@@_E@Z
0x180022bea  nop
0x180022beb  lea     rax, [rsp+78h+arg_18]
0x180022bf3  mov     [rsp+78h+var_20], rax
0x180022bf8  lea     rax, [rsp+78h+var_50]
0x180022bfd  mov     [rsp+60h], rax
0x180022c02  lea     rax, qword_180046CB8
0x180022c09  mov     [rsp+78h+var_40], rax
0x180022c0e  lock inc cs:qword_180046CB8
0x180022c16  cmp     cs:??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x180022c1e  jz      short loc_180022C44
0x180022c20  lea     r8, ??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x180022c27  lea     rdx, [rsp+78h+arg_10]
0x180022c2f  lea     rcx, [rsp+78h+var_20]
0x180022c34  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x180022c39  nop
0x180022c3a  lock dec cs:qword_180046CB8
0x180022c42  jmp     short loc_180022C5E
0x180022c44  lock dec cs:qword_180046CB8
0x180022c4c  lea     r8, [rsp+78h+var_20]
0x180022c51  lea     rdx, [rsp+78h+arg_10]
0x180022c59  call    ??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z
0x180022c5e  lea     rcx, [rbx+0B8h]
0x180022c65  lea     rdx, [rsp+78h+arg_10]
0x180022c6d  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180022c72  lea     rcx, [rsp+78h+arg_10]
0x180022c7a  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180022c7f  nop
0x180022c80  cmp     [rsp+78h+arg_18], 0
0x180022c89  jz      short loc_180022C99
0x180022c8b  lea     rcx, [rsp+78h+arg_18]
0x180022c93  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180022c98  nop
0x180022c99  cmp     [rsp+78h+var_58], 0
0x180022c9f  jz      short loc_180022CDB
0x180022ca1  lea     rcx, [rsp+78h+var_58]
0x180022ca6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180022cab  jmp     short loc_180022CDB
0x180022cad  mov     [rsp+78h+arg_10], 0
0x180022cb9  lea     rcx, [rbx+0B8h]
0x180022cc0  lea     rdx, [rsp+78h+arg_10]
0x180022cc8  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180022ccd  lea     rcx, [rsp+78h+arg_10]
0x180022cd5  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180022cda  nop
0x180022cdb  jmp     short $+2
0x180022cdd  mov     rbx, [rsp+78h+arg_0]
0x180022ce5  add     rsp, 70h
0x180022ce9  pop     rdi
0x180022cea  retn
```
