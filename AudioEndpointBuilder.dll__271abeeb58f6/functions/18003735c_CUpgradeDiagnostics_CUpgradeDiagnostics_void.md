# CUpgradeDiagnostics::~CUpgradeDiagnostics(void)

- ea: `0x18003735c`
- end: `0x1800373da`
- name: `??1CUpgradeDiagnostics@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(CUpgradeDiagnostics *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180049010`

## callees

- `0x180012e80`
- `0x180021060`
- `0x180035170`
- `0x18003735c`
- `0x1800373e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037370`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800373c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800373c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037399`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037399`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003738b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003738b`

## pseudocode

```c
void __fastcall CUpgradeDiagnostics::~CUpgradeDiagnostics(struct _TP_TIMER **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  struct _TP_TIMER *v3; // rcx
  struct _RTL_CRITICAL_SECTION *v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
  v3 = *this;
  v4 = v1;
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      this,
      0);
    AudMigLibSetupLog(L"Migration diagnostics shut down\r\n");
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v4);
  DeleteCriticalSection(v1);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(this);
}

```

## disassembly

```asm
0x18003735c  mov     [rsp+arg_8], rbx
0x180037361  push    rdi
0x180037362  sub     rsp, 20h
0x180037366  lea     rdi, [rcx+10h]
0x18003736a  mov     rbx, rcx
0x18003736d  mov     rcx, rdi; lpCriticalSection
0x180037370  call    cs:__imp_EnterCriticalSection
0x180037376  mov     rcx, [rbx]; pti
0x180037379  mov     [rsp+28h+arg_0], rdi
0x18003737e  test    rcx, rcx
0x180037381  jz      short loc_1800373B5
0x180037383  xor     r9d, r9d; msWindowLength
0x180037386  xor     r8d, r8d; msPeriod
0x180037389  xor     edx, edx; pftDueTime
0x18003738b  call    cs:__imp_SetThreadpoolTimer
0x180037391  mov     rcx, [rbx]; pti
0x180037394  mov     edx, 1; fCancelPendingCallbacks
0x180037399  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003739f  xor     edx, edx
0x1800373a1  mov     rcx, rbx
0x1800373a4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800373a9  lea     rcx, aMigrationDiagn_2; "Migration diagnostics shut down\r\n"
0x1800373b0  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x1800373b5  lea     rcx, [rsp+28h+arg_0]
0x1800373ba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800373bf  mov     rcx, rdi; lpCriticalSection
0x1800373c2  call    cs:__imp_DeleteCriticalSection
0x1800373c8  mov     rcx, rbx
0x1800373cb  mov     rbx, [rsp+28h+arg_8]
0x1800373d0  add     rsp, 20h
0x1800373d4  pop     rdi
0x1800373d5  jmp     ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
```
