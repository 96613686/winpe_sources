# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001f0d8`
- end: `0x18001f199`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002a9d0`

## callees

- `0x180015a10`
- `0x180016790`
- `0x1800176d4`
- `0x1800178c4`
- `0x18001f0d8`
- `0x18001f344`
- `0x180028bb4`
- `0x180029c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f189`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f189`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f154`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f154`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
    if ( !a1[65] )
    {
      if ( !*((_QWORD *)a1 + 6) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          a1 + 48,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)a1 + 6, a1 + 65, 300000);
    }
    if ( a1 != (_BYTE *)-32LL )
      ReleaseSRWLockExclusive((PSRWLOCK)a1 + 4);
  }
}

```

## disassembly

```asm
0x18001f0d8  push    rbx
0x18001f0da  push    rbp
0x18001f0db  push    rsi
0x18001f0dc  push    rdi
0x18001f0dd  sub     rsp, 28h
0x18001f0e1  mov     rdi, r9
0x18001f0e4  mov     esi, r8d
0x18001f0e7  mov     ebp, edx
0x18001f0e9  mov     rbx, rcx
0x18001f0ec  cmp     byte ptr [rcx], 0
0x18001f0ef  jz      loc_18001F190
0x18001f0f5  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001f0fa  test    al, al
0x18001f0fc  jz      loc_18001F190
0x18001f102  mov     r9, rdi
0x18001f105  mov     r8d, esi
0x18001f108  mov     edx, ebp
0x18001f10a  mov     rcx, [rbx+18h]
0x18001f10e  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001f113  test    al, al
0x18001f115  jz      short loc_18001F190
0x18001f117  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001f11c  test    al, al
0x18001f11e  jnz     short loc_18001F190
0x18001f120  lea     rdi, [rbx+20h]
0x18001f124  mov     rcx, rdi; SRWLock
0x18001f127  call    cs:__imp_AcquireSRWLockExclusive
0x18001f12d  cmp     byte ptr [rbx+41h], 0
0x18001f131  jnz     short loc_18001F181
0x18001f133  lea     rsi, [rbx+30h]
0x18001f137  cmp     qword ptr [rsi], 0
0x18001f13b  jnz     short loc_18001F16F
0x18001f13d  lea     rcx, [rsp+48h+arg_0]; this
0x18001f142  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001f147  xor     r8d, r8d; pcbe
0x18001f14a  mov     rdx, rbx; pv
0x18001f14d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f154  call    cs:__imp_CreateThreadpoolTimer
0x18001f15a  mov     rdx, rax
0x18001f15d  mov     rcx, rsi
0x18001f160  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001f165  lea     rcx, [rsp+48h+arg_0]; this
0x18001f16a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001f16f  mov     r8d, 493E0h
0x18001f175  lea     rdx, [rbx+41h]
0x18001f179  mov     rcx, rsi
0x18001f17c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001f181  test    rdi, rdi
0x18001f184  jz      short loc_18001F190
0x18001f186  mov     rcx, rdi; SRWLock
0x18001f189  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f18f  nop
0x18001f190  add     rsp, 28h
0x18001f194  pop     rdi
0x18001f195  pop     rsi
0x18001f196  pop     rbp
0x18001f197  pop     rbx
0x18001f198  retn
```
