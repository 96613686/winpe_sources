# Wns::ConnectionStateMachine::ConnectionStateMachine(Wns::ConnectionMultiplexer *)

- ea: `0x180024830`
- end: `0x1800249de`
- name: `??0ConnectionStateMachine@Wns@@QEAA@PEAVConnectionMultiplexer@1@@Z`
- size: `430`
- prototype: `Wns::ConnectionStateMachine *__fastcall(Wns::ConnectionStateMachine *this, struct Wns::ConnectionMultiplexer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180020ee4`

## callees

- `0x180017b68`
- `0x180021048`
- `0x180021468`
- `0x180024830`
- `0x1800249e4`
- `0x180024a50`
- `0x180024c5c`
- `0x180024c78`
- `0x180025108`
- `0x1800259fc`
- `0x180026200`
- `0x180032034`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002486a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002486a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180024963`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180024963`

## pseudocode

```c
Wns::ConnectionStateMachine *__fastcall Wns::ConnectionStateMachine::ConnectionStateMachine(
        Wns::ConnectionStateMachine *this,
        struct Wns::ConnectionMultiplexer *a2)
{
  PTP_WORK ThreadpoolWork; // rax
  __int64 v5; // rdx
  _QWORD *wnf; // rax
  int v8; // [rsp+20h] [rbp-59h] BYREF
  __int64 v9; // [rsp+28h] [rbp-51h] BYREF
  int v10; // [rsp+30h] [rbp-49h] BYREF
  Wns::ConnectionStateMachine *v11; // [rsp+38h] [rbp-41h]
  _BYTE v12[8]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v13[14]; // [rsp+48h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v11 = this;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this, 0, 0);
  *((_QWORD *)this + 5) = 0;
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)this + 6,
    (int *)&v9);
  LODWORD(v9) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)this + 7,
    (int *)&v9);
  Wns::CPTransactionRequestManager::CPTransactionRequestManager(
    (Wns::ConnectionStateMachine *)((char *)this + 64),
    this);
  *((_QWORD *)this + 45) = a2;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = this;
  *((_QWORD *)this + 52) = 0;
  *((_BYTE *)this + 424) = 0;
  *(_QWORD *)((char *)this + 428) = 0;
  *(_QWORD *)((char *)this + 436) = 0;
  *(_QWORD *)((char *)this + 444) = 0;
  if ( !*((_QWORD *)this + 45) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
      (const char *)0x80070057LL,
      v8);
  v10 = 0;
  LOBYTE(v8) = 0;
  if ( (int)wil::wnf_query_nothrow<int>(retaddr, &v8, &v10) >= 0 && (_BYTE)v8 && v10 )
  {
    Wns::ConnectionStateMachine::LoadConnectionProvider(this);
  }
  else
  {
    ThreadpoolWork = CreateThreadpoolWork(Wns::ConnectionStateMachine::CleanupWnfSubscription, this, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (char *)this + 416,
      ThreadpoolWork);
    v13[0] = off_180038B78;
    v13[1] = this;
    v13[13] = v13;
    wnf = wil::make_wnf_subscription<int>(&v9, v5, (__int64)v12);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
      (char *)this + 376,
      wnf);
    wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v9);
    wistd::function<void (int const &)>::~function<void (int const &)>(v12);
  }
  return this;
}

```

## disassembly

```asm
0x180024830  mov     [rsp-8+arg_8], rbx
0x180024835  mov     [rsp-8+arg_10], rsi
0x18002483a  push    rbp
0x18002483b  push    rdi
0x18002483c  push    r14
0x18002483e  lea     rbp, [rsp-47h]
0x180024843  sub     rsp, 0C0h
0x18002484a  mov     rax, cs:__security_cookie
0x180024851  xor     rax, rsp
0x180024854  mov     [rbp+57h+var_18], rax
0x180024858  mov     rbx, rdx
0x18002485b  mov     rdi, rcx
0x18002485e  mov     [rbp+57h+var_98], rcx
0x180024862  xor     r14d, r14d
0x180024865  xor     r8d, r8d; Flags
0x180024868  xor     edx, edx; dwSpinCount
0x18002486a  call    cs:__imp_InitializeCriticalSectionEx
0x180024870  nop
0x180024871  mov     [rdi+28h], r14
0x180024875  lea     esi, [r14+1]
0x180024879  mov     dword ptr [rbp+57h+var_A8], esi
0x18002487c  lea     rcx, [rdi+30h]
0x180024880  lea     rdx, [rbp+57h+var_A8]
0x180024884  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180024889  nop
0x18002488a  mov     dword ptr [rbp+57h+var_A8], esi
0x18002488d  lea     rcx, [rdi+38h]
0x180024891  lea     rdx, [rbp+57h+var_A8]
0x180024895  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18002489a  nop
0x18002489b  lea     rcx, [rdi+40h]; this
0x18002489f  mov     rdx, rdi; struct Wns::ConnectionStateMachine *
0x1800248a2  call    ??0CPTransactionRequestManager@Wns@@QEAA@QEAVConnectionStateMachine@1@@Z; Wns::CPTransactionRequestManager::CPTransactionRequestManager(Wns::ConnectionStateMachine * const)
0x1800248a7  nop
0x1800248a8  mov     [rdi+168h], rbx
0x1800248af  mov     [rdi+170h], r14
0x1800248b6  lea     rbx, [rdi+178h]
0x1800248bd  mov     [rbx], r14
0x1800248c0  xor     eax, eax
0x1800248c2  mov     [rdi+180h], rax
0x1800248c9  mov     [rdi+188h], r14
0x1800248d0  mov     [rdi+190h], r14
0x1800248d7  mov     [rdi+198h], rdi
0x1800248de  lea     rsi, [rdi+1A0h]
0x1800248e5  mov     [rsi], r14
0x1800248e8  mov     [rdi+1A8h], r14b
0x1800248ef  mov     [rdi+1ACh], r14
0x1800248f6  mov     [rdi+1B4h], r14
0x1800248fd  mov     [rdi+1BCh], r14
0x180024904  mov     rcx, [rbp+5Fh]; this
0x180024908  cmp     [rdi+168h], r14
0x18002490f  jnz     short loc_180024927
0x180024911  mov     r9d, 80070057h; char *
0x180024917  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002491e  lea     edx, [rax+37h]; void *
0x180024921  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024927  mov     [rbp+57h+var_A0], r14d
0x18002492b  mov     byte ptr [rbp+57h+var_B0], r14b
0x18002492f  lea     r8, [rbp+57h+var_A0]
0x180024933  lea     rdx, [rbp+57h+var_B0]
0x180024937  call    ??$wnf_query_nothrow@H@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAHPEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<int>(_WNF_STATE_NAME const &,bool *,int *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18002493c  test    eax, eax
0x18002493e  js      short loc_180024956
0x180024940  cmp     byte ptr [rbp+57h+var_B0], r14b
0x180024944  jz      short loc_180024956
0x180024946  cmp     [rbp+57h+var_A0], r14d
0x18002494a  jz      short loc_180024956
0x18002494c  mov     rcx, rdi; this
0x18002494f  call    ?LoadConnectionProvider@ConnectionStateMachine@Wns@@AEAAPEAU_TP_WORK@@XZ; Wns::ConnectionStateMachine::LoadConnectionProvider(void)
0x180024954  jmp     short loc_1800249B7
0x180024956  xor     r8d, r8d; pcbe
0x180024959  mov     rdx, rdi; pv
0x18002495c  lea     rcx, ?CleanupWnfSubscription@ConnectionStateMachine@Wns@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180024963  call    cs:__imp_CreateThreadpoolWork
0x180024969  mov     rdx, rax
0x18002496c  mov     rcx, rsi
0x18002496f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180024974  lea     rax, off_180038B78
0x18002497b  mov     [rbp+57h+var_88], rax
0x18002497f  mov     [rbp+57h+var_80], rdi
0x180024983  lea     rax, [rbp+57h+var_88]
0x180024987  mov     [rbp+57h+var_20], rax
0x18002498b  lea     r8, [rbp+57h+var_90]
0x18002498f  lea     rcx, [rbp+57h+var_A8]
0x180024993  call    ??$make_wnf_subscription@H@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBH@Z@wistd@@K@Z; wil::make_wnf_subscription<int>(_WNF_STATE_NAME const &,wistd::function<void (int const &)> &&,ulong)
0x180024998  mov     rdx, rax
0x18002499b  mov     rcx, rbx
0x18002499e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x1800249a3  lea     rcx, [rbp+57h+var_A8]
0x1800249a7  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800249ac  nop
0x1800249ad  lea     rcx, [rbp+57h+var_90]
0x1800249b1  call    ??1?$function@$$A6AXAEBH@Z@wistd@@QEAA@XZ; wistd::function<void (int const &)>::~function<void (int const &)>(void)
0x1800249b6  nop
0x1800249b7  mov     rax, rdi
0x1800249ba  mov     rcx, [rbp+57h+var_18]
0x1800249be  xor     rcx, rsp; StackCookie
0x1800249c1  call    __security_check_cookie
0x1800249c6  lea     r11, [rsp+0D0h+var_10]
0x1800249ce  mov     rbx, [r11+28h]
0x1800249d2  mov     rsi, [r11+30h]
0x1800249d6  mov     rsp, r11
0x1800249d9  pop     r14
0x1800249db  pop     rdi
0x1800249dc  pop     rbp
0x1800249dd  retn
```
