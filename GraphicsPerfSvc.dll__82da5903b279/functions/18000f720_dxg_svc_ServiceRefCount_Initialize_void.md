# dxg::svc::ServiceRefCount::Initialize(void)

- ea: `0x18000f720`
- end: `0x18000f7a2`
- name: `?Initialize@ServiceRefCount@svc@dxg@@QEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(dxg::svc::ServiceRefCount *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011630`

## callees

- `0x18000919c`
- `0x18000aa74`
- `0x18000f720`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f795`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f795`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f742`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000f742`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000f730`
- `api-ms-win-shcore-thread-l1-1-0!SetProcessReference` at `0x18000f730`

## string_xrefs

- `0x18000f768`: `onecoreuap\windows\DirectX\dxg\common\ServiceHelpers\ServiceRefCount.h`

## pseudocode

```c
__int64 __fastcall dxg::svc::ServiceRefCount::Initialize(dxg::svc::ServiceRefCount *this)
{
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  pftDueTime = (struct _FILETIME)this;
  SetProcessReference(&g::RefCount);
  ThreadpoolTimer = CreateThreadpoolTimer(dxg::svc::ServiceRefCount::s_TimerCallback, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    ThreadpoolTimer);
  if ( !pti )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1D,
             (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\common\\ServiceHelpers\\ServiceRefCount.h",
             v2);
  pftDueTime = (struct _FILETIME)-6000000000LL;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18000f720  mov     qword ptr [rsp+pftDueTime.dwLowDateTime], rcx
0x18000f725  sub     rsp, 28h
0x18000f729  lea     rcx, ?RefCount@g@@3VServiceRefCount@svc@dxg@@A; dxg::svc::ServiceRefCount g::RefCount
0x18000f730  call    cs:__imp_SetProcessReference
0x18000f736  xor     r8d, r8d; pcbe
0x18000f739  lea     rcx, ?s_TimerCallback@ServiceRefCount@svc@dxg@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000f740  xor     edx, edx; pv
0x18000f742  call    cs:__imp_CreateThreadpoolTimer
0x18000f748  mov     rdx, rax
0x18000f74b  lea     rcx, pti
0x18000f752  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000f757  mov     rcx, cs:pti; pti
0x18000f75e  test    rcx, rcx
0x18000f761  jnz     short loc_18000F77B
0x18000f763  mov     rcx, [rsp+28h]; this
0x18000f768  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\DirectX\\dxg\\comm"...
0x18000f76f  mov     edx, 1Dh; void *
0x18000f774  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f779  jmp     short loc_18000F79D
0x18000f77b  mov     rax, 0FFFFFFFE9A5F4400h
0x18000f785  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000f78a  xor     r9d, r9d; msWindowLength
0x18000f78d  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000f792  xor     r8d, r8d; msPeriod
0x18000f795  call    cs:__imp_SetThreadpoolTimer
0x18000f79b  xor     eax, eax
0x18000f79d  add     rsp, 28h
0x18000f7a1  retn
```
