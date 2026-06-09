# TelemetryLogger::Initialize(void)

- ea: `0x1800148e0`
- end: `0x180014978`
- name: `?Initialize@TelemetryLogger@@EEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800067c0`
- `0x1800148e0`
- `0x18004c070`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001495a`
- `KERNEL32!SetThreadpoolTimer` at `0x18001495a`
- `KERNEL32!CreateThreadpoolTimer` at `0x180014925`
- `KERNEL32!CreateThreadpoolTimer` at `0x180014925`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x180014913`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x180014913`

## pseudocode

```c
void __fastcall TelemetryLogger::Initialize(struct _TP_TIMER **this)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  RegisterAppStateChangeNotification(`TelemetryLogger::Initialize'::`2'::_lambda_1_::_lambda_invoker_cdecl_, 0, &v4);
  ThreadpoolTimer = CreateThreadpoolTimer(TelemetryLogger::FireEventCallback, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    this + 8,
    ThreadpoolTimer);
  v3 = this[8];
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000000LL * *((unsigned int *)this + 18));
    SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x1800148e0  mov     [rsp+arg_8], rbx
0x1800148e5  push    rdi
0x1800148e6  sub     rsp, 40h
0x1800148ea  mov     rax, cs:__security_cookie
0x1800148f1  xor     rax, rsp
0x1800148f4  mov     [rsp+48h+var_18], rax
0x1800148f9  mov     rdi, rcx
0x1800148fc  mov     [rsp+48h+var_28], 0
0x180014905  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Initialize@TelemetryLogger@@EEAAXXZ@SA@EPEAX@Z; `TelemetryLogger::Initialize(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(uchar,void *)
0x18001490c  xor     edx, edx
0x18001490e  lea     r8, [rsp+48h+var_28]
0x180014913  call    cs:__imp_RegisterAppStateChangeNotification
0x180014919  xor     r8d, r8d; pcbe
0x18001491c  lea     rcx, ?FireEventCallback@TelemetryLogger@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014923  xor     edx, edx; pv
0x180014925  call    cs:__imp_CreateThreadpoolTimer
0x18001492b  mov     rdx, rax
0x18001492e  lea     rcx, [rdi+40h]
0x180014932  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180014937  mov     rcx, [rdi+40h]; pti
0x18001493b  test    rcx, rcx
0x18001493e  jz      short loc_180014960
0x180014940  mov     eax, [rdi+48h]
0x180014943  xor     r9d, r9d; msWindowLength
0x180014946  imul    rdx, rax, 0FFFFFFFFFF676980h
0x18001494d  xor     r8d, r8d; msPeriod
0x180014950  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x180014955  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001495a  call    cs:__imp_SetThreadpoolTimer
0x180014960  mov     rcx, [rsp+48h+var_18]
0x180014965  xor     rcx, rsp; StackCookie
0x180014968  call    __security_check_cookie
0x18001496d  mov     rbx, [rsp+48h+arg_8]
0x180014972  add     rsp, 40h
0x180014976  pop     rdi
0x180014977  retn
```
