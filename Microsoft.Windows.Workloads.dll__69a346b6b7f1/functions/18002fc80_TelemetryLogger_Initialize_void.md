# TelemetryLogger::Initialize(void)

- ea: `0x18002fc80`
- end: `0x18002fd18`
- name: `?Initialize@TelemetryLogger@@EEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TelemetryLogger *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000f590`
- `0x18002fc80`
- `0x180034ef0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18002fcfa`
- `KERNEL32!SetThreadpoolTimer` at `0x18002fcfa`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002fcc5`
- `KERNEL32!CreateThreadpoolTimer` at `0x18002fcc5`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x18002fcb3`
- `api-ms-win-core-psm-appnotify-l1-1-0!RegisterAppStateChangeNotification` at `0x18002fcb3`

## pseudocode

```c
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
0x18002fc80  mov     [rsp+arg_8], rbx
0x18002fc85  push    rdi
0x18002fc86  sub     rsp, 40h
0x18002fc8a  mov     rax, cs:__security_cookie
0x18002fc91  xor     rax, rsp
0x18002fc94  mov     [rsp+48h+var_18], rax
0x18002fc99  mov     rdi, rcx
0x18002fc9c  mov     [rsp+48h+var_28], 0
0x18002fca5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_63ed9c68e287d6474e78e420a4e8e4a2_@@CA@EPEAX@Z; _lambda_63ed9c68e287d6474e78e420a4e8e4a2_::_lambda_invoker_cdecl_(uchar,void *)
0x18002fcac  xor     edx, edx
0x18002fcae  lea     r8, [rsp+48h+var_28]
0x18002fcb3  call    cs:__imp_RegisterAppStateChangeNotification
0x18002fcb9  xor     r8d, r8d; pcbe
0x18002fcbc  lea     rcx, ?FireEventCallback@TelemetryLogger@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002fcc3  xor     edx, edx; pv
0x18002fcc5  call    cs:__imp_CreateThreadpoolTimer
0x18002fccb  mov     rdx, rax
0x18002fcce  lea     rcx, [rdi+40h]
0x18002fcd2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002fcd7  mov     rcx, [rdi+40h]; pti
0x18002fcdb  test    rcx, rcx
0x18002fcde  jz      short loc_18002FD00
0x18002fce0  mov     eax, [rdi+48h]
0x18002fce3  xor     r9d, r9d; msWindowLength
0x18002fce6  imul    rdx, rax, 0FFFFFFFFFF676980h
0x18002fced  xor     r8d, r8d; msPeriod
0x18002fcf0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x18002fcf5  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18002fcfa  call    cs:__imp_SetThreadpoolTimer
0x18002fd00  mov     rcx, [rsp+48h+var_18]
0x18002fd05  xor     rcx, rsp; StackCookie
0x18002fd08  call    __security_check_cookie
0x18002fd0d  mov     rbx, [rsp+48h+arg_8]
0x18002fd12  add     rsp, 40h
0x18002fd16  pop     rdi
0x18002fd17  retn
```
