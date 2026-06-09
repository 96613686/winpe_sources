# FlightSettingsActionManager::ScheduleAsyncValidation(int)

- ea: `0x18008e320`
- end: `0x18008e45f`
- name: `?ScheduleAsyncValidation@FlightSettingsActionManager@@UEAAJH@Z`
- size: `319`
- prototype: `int(FlightSettingsActionManager *__hidden this, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008e9a0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x18000e4d4`
- `0x180013da0`
- `0x1800177bc`
- `0x1800179c4`
- `0x18008cb1c`
- `0x18008e320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e3dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e44a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e3dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e44a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e35f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e35f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008e39d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18008e39d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008e419`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008e419`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18008e3e7`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18008e3e7`

## string_xrefs

- `0x18008e340`: `onecore\base\flighting\flightsettings\broker\lib\actionmanager.cpp`
- `0x18008e3c3`: `onecore\base\flighting\flightsettings\broker\lib\actionmanager.cpp`

## pseudocode

```c
__int64 __fastcall FlightSettingsActionManager::ScheduleAsyncValidation(FlightSettingsActionManager *this, int a2)
{
  __int64 v2; // rbx
  struct _TP_TIMER *v4; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  __int64 v10; // rcx
  FlightSettingsAPITelemetryClass *v11; // rax
  int v12; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+18h] BYREF

  v2 = a2;
  if ( (unsigned int)(a2 - 1) <= 0x1517F )
  {
    EnterCriticalSection(&stru_18011D828);
    if ( byte_18011D7A8 )
    {
      v4 = g_WebRequestTimer;
      if ( g_WebRequestTimer
        || (ThreadpoolTimer = CreateThreadpoolTimer(FlightSettingsActionManager::TimerCallback, 0, 0),
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &g_WebRequestTimer,
              ThreadpoolTimer),
            (v4 = g_WebRequestTimer) != 0) )
      {
        if ( !IsThreadpoolTimerSet(v4) )
        {
          pftDueTime = (struct _FILETIME)(-10000000 * v2);
          SetThreadpoolTimer(g_WebRequestTimer, &pftDueTime, 0, 0x3E8u);
          SvcAddRef();
          if ( FlightSettingsAPITelemetryClass::IsEnabled(v9, v8) )
          {
            v11 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                       v10,
                                                       _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
            FlightSettingsAPITelemetryClass::AsyncServiceCallScheduled_(v11, v2);
          }
        }
        LeaveCriticalSection(&stru_18011D828);
        return 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x259,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\actionmanager.cpp",
                      v6);
        LeaveCriticalSection(&stru_18011D828);
        return LastError;
      }
    }
    else
    {
      LeaveCriticalSection(&stru_18011D828);
      return 2147483674LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\actionmanager.cpp",
      (const char *)0x80070057LL,
      v12);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18008e320  push    rbx; int
0x18008e322  sub     rsp, 20h
0x18008e326  movsxd  rbx, edx
0x18008e329  lea     eax, [rbx-1]
0x18008e32c  cmp     eax, 1517Fh
0x18008e331  jbe     short loc_18008E358
0x18008e333  mov     rcx, [rsp+28h]; this
0x18008e338  mov     ebx, 80070057h
0x18008e33d  mov     r9d, ebx; char *
0x18008e340  lea     r8, aOnecoreBaseFli_6; "onecore\\base\\flighting\\flightsetting"...
0x18008e347  mov     edx, 250h; void *
0x18008e34c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e351  mov     eax, ebx
0x18008e353  jmp     loc_18008E458
0x18008e358  lea     rcx, stru_18011D828; lpCriticalSection
0x18008e35f  call    cs:__imp_EnterCriticalSection
0x18008e365  cmp     cs:byte_18011D7A8, 0
0x18008e36c  jnz     short loc_18008E385
0x18008e36e  lea     rcx, stru_18011D828; lpCriticalSection
0x18008e375  call    cs:__imp_LeaveCriticalSection
0x18008e37b  mov     eax, 8000001Ah
0x18008e380  jmp     loc_18008E458
0x18008e385  mov     rcx, cs:?g_WebRequestTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18008e38c  test    rcx, rcx
0x18008e38f  jnz     short loc_18008E3E7
0x18008e391  xor     r8d, r8d; pcbe
0x18008e394  xor     edx, edx; pv
0x18008e396  lea     rcx, ?TimerCallback@FlightSettingsActionManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18008e39d  call    cs:__imp_CreateThreadpoolTimer
0x18008e3a3  mov     rdx, rax
0x18008e3a6  lea     rcx, ?g_WebRequestTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> g_WebRequestTimer
0x18008e3ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18008e3b2  mov     rcx, cs:?g_WebRequestTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> g_WebRequestTimer
0x18008e3b9  test    rcx, rcx
0x18008e3bc  jnz     short loc_18008E3E7
0x18008e3be  mov     rcx, [rsp+28h]; this
0x18008e3c3  lea     r8, aOnecoreBaseFli_6; "onecore\\base\\flighting\\flightsetting"...
0x18008e3ca  mov     edx, 259h; void *
0x18008e3cf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008e3d4  mov     ebx, eax
0x18008e3d6  lea     rcx, stru_18011D828; lpCriticalSection
0x18008e3dd  call    cs:__imp_LeaveCriticalSection
0x18008e3e3  mov     eax, ebx
0x18008e3e5  jmp     short loc_18008E458
0x18008e3e7  call    cs:__imp_IsThreadpoolTimerSet
0x18008e3ed  test    eax, eax
0x18008e3ef  jnz     short loc_18008E443
0x18008e3f1  imul    rax, rbx, 0FFFFFFFFFF676980h
0x18008e3f8  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18008e3fc  shr     rax, 20h
0x18008e400  mov     [rsp+28h+pftDueTime.dwHighDateTime], eax
0x18008e404  mov     r9d, 3E8h; msWindowLength
0x18008e40a  xor     r8d, r8d; msPeriod
0x18008e40d  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18008e412  mov     rcx, cs:?g_WebRequestTimer@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18008e419  call    cs:__imp_SetThreadpoolTimer
0x18008e41f  call    SvcAddRef
0x18008e424  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18008e429  test    al, al
0x18008e42b  jz      short loc_18008E443
0x18008e42d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x18008e434  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18008e439  mov     edx, ebx; int
0x18008e43b  mov     rcx, rax; this
0x18008e43e  call    ?AsyncServiceCallScheduled_@FlightSettingsAPITelemetryClass@@QEAAXH@Z; FlightSettingsAPITelemetryClass::AsyncServiceCallScheduled_(int)
0x18008e443  lea     rcx, stru_18011D828; lpCriticalSection
0x18008e44a  call    cs:__imp_LeaveCriticalSection
0x18008e450  xor     eax, eax
0x18008e452  jmp     short loc_18008E458
0x18008e454  mov     eax, [rsp+28h+arg_8]
0x18008e458  add     rsp, 20h
0x18008e45c  pop     rbx
0x18008e45d  retn
```
