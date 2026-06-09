# RouteManagement::DebounceTimer::StartTimer(ushort)

- ea: `0x18005d99c`
- end: `0x18005db53`
- name: `?StartTimer@DebounceTimer@RouteManagement@@QEAAXG@Z`
- size: `439`
- prototype: `void __fastcall(PVOID pv, unsigned __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180059da8`

## callees

- `0x18003322c`
- `0x180034584`
- `0x18005d99c`
- `0x180084f50`
- `0x180085be8`
- `0x180088990`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d9f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005da82`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005d9f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005da82`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18005da1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18005daa9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18005da1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18005daa9`

## string_xrefs

- `0x18005da43`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerdebouncetimers.cpp`
- `0x18005dacc`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerdebouncetimers.cpp`

## pseudocode

```c
void __fastcall RouteManagement::DebounceTimer::StartTimer(struct _TP_TIMER **pv, __int16 a2)
{
  struct _TP_TIMER *v3; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  char *v8; // rdx
  const char **v9; // rax
  struct _TP_TIMER **v10; // rdi
  struct _TP_TIMER *v11; // rcx
  PTP_TIMER v12; // rax
  const char **v13; // [rsp+28h] [rbp-58h]
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  const char *v15; // [rsp+48h] [rbp-38h] BYREF
  const char *v16; // [rsp+50h] [rbp-30h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp-10h] BYREF

  v14 = -12500000;
  pftDueTime = (struct _FILETIME)-12500000LL;
  if ( a2 == 2 )
  {
    v3 = *pv;
    if ( !v3 )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(RouteManagement::DebounceTimer::DebounceTimerCallback4, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        pv,
        ThreadpoolTimer);
      v3 = *pv;
      if ( !*pv )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    SetThreadpoolTimerEx(v3, &pftDueTime, 0, 0);
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v15 = "DebounceTimer IPv4 timer started (ms)";
      v8 = byte_18011DABD;
      v16 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerdebouncetimers.cpp";
      v13 = &v15;
      v9 = &v16;
LABEL_10:
      LODWORD(v14) = 1250;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (_DWORD)v8,
        v6,
        v7,
        (__int64)v9,
        (__int64)v13,
        (__int64)&v14);
    }
  }
  else
  {
    v10 = pv + 1;
    v11 = pv[1];
    if ( !v11 )
    {
      v12 = CreateThreadpoolTimer(RouteManagement::DebounceTimer::DebounceTimerCallback6, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v10,
        v12);
      v11 = *v10;
      if ( !*v10 )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
    SetThreadpoolTimerEx(v11, &pftDueTime, 0, 0);
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v16 = "DebounceTimer IPv6 timer started (ms)";
      v8 = byte_18011DAF9;
      v15 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerdebouncetimers.cpp";
      v13 = &v16;
      v9 = &v15;
      goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x18005d99c  mov     [rsp-8+arg_8], rbx
0x18005d9a1  mov     [rsp-8+arg_10], rdi
0x18005d9a6  push    rbp
0x18005d9a7  mov     rbp, rsp
0x18005d9aa  sub     rsp, 80h
0x18005d9b1  mov     rax, cs:__security_cookie
0x18005d9b8  xor     rax, rsp
0x18005d9bb  mov     [rbp+var_8], rax
0x18005d9bf  mov     [rbp+var_40], 0FFFFFFFFFF4143E0h
0x18005d9c7  mov     rbx, rcx
0x18005d9ca  mov     rax, [rbp+var_40]
0x18005d9ce  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18005d9d2  mov     eax, 2
0x18005d9d7  cmp     ax, dx
0x18005d9da  jnz     loc_18005DA69
0x18005d9e0  mov     rcx, [rcx]
0x18005d9e3  test    rcx, rcx
0x18005d9e6  jnz     short loc_18005DA12
0x18005d9e8  xor     r8d, r8d; pcbe
0x18005d9eb  lea     rcx, ?DebounceTimerCallback4@DebounceTimer@RouteManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005d9f2  mov     rdx, rbx; pv
0x18005d9f5  call    cs:__imp_CreateThreadpoolTimer
0x18005d9fb  mov     rdx, rax
0x18005d9fe  mov     rcx, rbx
0x18005da01  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005da06  mov     rcx, [rbx]; pti
0x18005da09  test    rcx, rcx
0x18005da0c  jz      loc_18005DB39
0x18005da12  xor     r9d, r9d; msWindowLength
0x18005da15  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18005da19  xor     r8d, r8d; msPeriod
0x18005da1c  call    cs:__imp_SetThreadpoolTimerEx
0x18005da22  mov     eax, cs:dword_18013A120
0x18005da28  cmp     eax, 5
0x18005da2b  jbe     loc_18005DAFE
0x18005da31  lea     rax, aDebouncetimerI_0; "DebounceTimer IPv4 timer started (ms)"
0x18005da38  mov     [rbp+var_38], rax
0x18005da3c  lea     rdx, byte_18011DABD
0x18005da43  lea     rax, aOnecoreuapNetW_29; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005da4a  mov     [rbp+var_30], rax
0x18005da4e  lea     rax, [rbp+var_40]
0x18005da52  mov     [rsp+80h+var_50], rax
0x18005da57  lea     rax, [rbp+var_38]
0x18005da5b  mov     [rsp+80h+var_58], rax
0x18005da60  lea     rax, [rbp+var_30]
0x18005da64  jmp     loc_18005DAED
0x18005da69  lea     rdi, [rcx+8]
0x18005da6d  mov     rcx, [rdi]
0x18005da70  test    rcx, rcx
0x18005da73  jnz     short loc_18005DA9F
0x18005da75  xor     r8d, r8d; pcbe
0x18005da78  lea     rcx, ?DebounceTimerCallback6@DebounceTimer@RouteManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005da7f  mov     rdx, rbx; pv
0x18005da82  call    cs:__imp_CreateThreadpoolTimer
0x18005da88  mov     rdx, rax
0x18005da8b  mov     rcx, rdi
0x18005da8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005da93  mov     rcx, [rdi]; pti
0x18005da96  test    rcx, rcx
0x18005da99  jz      loc_18005DB1F
0x18005da9f  xor     r9d, r9d; msWindowLength
0x18005daa2  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18005daa6  xor     r8d, r8d; msPeriod
0x18005daa9  call    cs:__imp_SetThreadpoolTimerEx
0x18005daaf  mov     eax, cs:dword_18013A120
0x18005dab5  cmp     eax, 5
0x18005dab8  jbe     short loc_18005DAFE
0x18005daba  lea     rax, aDebouncetimerI; "DebounceTimer IPv6 timer started (ms)"
0x18005dac1  mov     [rbp+var_30], rax
0x18005dac5  lea     rdx, byte_18011DAF9
0x18005dacc  lea     rax, aOnecoreuapNetW_29; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005dad3  mov     [rbp+var_38], rax
0x18005dad7  lea     rax, [rbp+var_40]
0x18005dadb  mov     [rsp+80h+var_50], rax
0x18005dae0  lea     rax, [rbp+var_30]
0x18005dae4  mov     [rsp+80h+var_58], rax
0x18005dae9  lea     rax, [rbp+var_38]
0x18005daed  mov     [rsp+80h+var_60], rax
0x18005daf2  mov     dword ptr [rbp+var_40], 4E2h
0x18005daf9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005dafe  mov     rcx, [rbp+var_8]
0x18005db02  xor     rcx, rsp; StackCookie
0x18005db05  call    __security_check_cookie
0x18005db0a  lea     r11, [rsp+80h+var_s0]
0x18005db12  mov     rbx, [r11+18h]
0x18005db16  mov     rdi, [r11+20h]
0x18005db1a  mov     rsp, r11
0x18005db1d  pop     rbp
0x18005db1e  retn
0x18005db1f  lea     rcx, [rbp+pExceptionObject]; this
0x18005db23  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18005db28  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18005db2f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005db33  call    _CxxThrowException_0
0x18005db39  lea     rcx, [rbp+pExceptionObject]; this
0x18005db3d  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18005db42  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18005db49  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005db4d  call    _CxxThrowException_0
```
