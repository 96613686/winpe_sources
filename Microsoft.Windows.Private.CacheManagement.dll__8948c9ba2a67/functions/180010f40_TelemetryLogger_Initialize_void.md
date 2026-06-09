# TelemetryLogger::Initialize(void)

- ea: `0x180010f40`
- end: `0x180010fd8`
- name: `?Initialize@TelemetryLogger@@EEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180010f40`
- `0x180012de0`
- `0x1800181b0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180010fba`
- `KERNEL32!SetThreadpoolTimer` at `0x180010fba`
- `KERNEL32!CreateThreadpoolTimer` at `0x180010f85`
- `KERNEL32!CreateThreadpoolTimer` at `0x180010f85`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x180010f73`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x180010f73`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TelemetryLogger::Initialize(TelemetryLogger *this)
{
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  RegisterAppStateChangeNotification(_lambda_63ed9c68e287d6474e78e420a4e8e4a2_::_lambda_invoker_cdecl_, 0, &v4);
  ThreadpoolTimer = CreateThreadpoolTimer(TelemetryLogger::FireEventCallback, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 64,
    ThreadpoolTimer);
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000000LL * *((unsigned int *)this + 18));
    SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x180010f40  mov     [rsp+arg_8], rbx
0x180010f45  push    rdi
0x180010f46  sub     rsp, 40h
0x180010f4a  mov     rax, cs:__security_cookie
0x180010f51  xor     rax, rsp
0x180010f54  mov     [rsp+48h+var_18], rax
0x180010f59  mov     rdi, rcx
0x180010f5c  mov     [rsp+48h+var_28], 0
0x180010f65  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_63ed9c68e287d6474e78e420a4e8e4a2_@@CA@EPEAX@Z; _lambda_63ed9c68e287d6474e78e420a4e8e4a2_::_lambda_invoker_cdecl_(uchar,void *)
0x180010f6c  xor     edx, edx
0x180010f6e  lea     r8, [rsp+48h+var_28]
0x180010f73  call    cs:__imp_RegisterAppStateChangeNotification
0x180010f79  xor     r8d, r8d; pcbe
0x180010f7c  lea     rcx, ?FireEventCallback@TelemetryLogger@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180010f83  xor     edx, edx; pv
0x180010f85  call    cs:__imp_CreateThreadpoolTimer
0x180010f8b  mov     rdx, rax
0x180010f8e  lea     rcx, [rdi+40h]
0x180010f92  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180010f97  mov     rcx, [rdi+40h]; pti
0x180010f9b  test    rcx, rcx
0x180010f9e  jz      short loc_180010FC0
0x180010fa0  mov     eax, [rdi+48h]
0x180010fa3  xor     r9d, r9d; msWindowLength
0x180010fa6  imul    rdx, rax, 0FFFFFFFFFF676980h
0x180010fad  xor     r8d, r8d; msPeriod
0x180010fb0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x180010fb5  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180010fba  call    cs:__imp_SetThreadpoolTimer
0x180010fc0  mov     rcx, [rsp+48h+var_18]
0x180010fc5  xor     rcx, rsp; StackCookie
0x180010fc8  call    __security_check_cookie
0x180010fcd  mov     rbx, [rsp+48h+arg_8]
0x180010fd2  add     rsp, 40h
0x180010fd6  pop     rdi
0x180010fd7  retn
```
