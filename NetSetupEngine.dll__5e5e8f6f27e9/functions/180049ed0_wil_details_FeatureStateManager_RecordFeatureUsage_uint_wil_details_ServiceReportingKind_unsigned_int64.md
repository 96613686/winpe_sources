# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180049ed0`
- end: `0x180049fa2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800702f0`

## callees

- `0x180043ea4`
- `0x180044324`
- `0x180049ed0`
- `0x18004a078`
- `0x18004a270`
- `0x18004a2d0`
- `0x18004a3e4`
- `0x18004a4cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049f2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049f2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049f59`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180049f59`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        RTL_SRWLOCK *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h]

  v11 = -2;
  if ( LOBYTE(a1->Ptr)
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && (unsigned __int8)wil::details_abi::FeatureStateData::RecordFeatureUsage(a1[3].Ptr, a2, a3, a4)
    && !wil::ProcessShutdownInProgress(v8) )
  {
    AcquireSRWLockExclusive(a1 + 4);
    if ( !BYTE1(a1[8].Ptr) )
    {
      if ( !a1[6].Ptr )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v10);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_,
                            a1,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &a1[6],
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
      }
      wil::details::EnsureCoalescedTimer_SetTimer(&a1[6], (char *)&a1[8].Ptr + 1, 300000);
    }
    if ( a1 != (RTL_SRWLOCK *)-32LL )
      ReleaseSRWLockExclusive(a1 + 4);
  }
}

```

## disassembly

```asm
0x180049ed0  push    rbp
0x180049ed2  push    rsi
0x180049ed3  push    rdi
0x180049ed4  sub     rsp, 30h
0x180049ed8  mov     [rsp+48h+var_20], 0FFFFFFFFFFFFFFFEh
0x180049ee1  mov     [rsp+48h+arg_18], rbx
0x180049ee6  mov     rdi, r9
0x180049ee9  mov     ebp, r8d
0x180049eec  mov     esi, edx
0x180049eee  mov     rbx, rcx
0x180049ef1  cmp     byte ptr [rcx], 0
0x180049ef4  jz      loc_180049F95
0x180049efa  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180049eff  test    al, al
0x180049f01  jz      loc_180049F95
0x180049f07  mov     r9, rdi
0x180049f0a  mov     r8d, ebp
0x180049f0d  mov     edx, esi
0x180049f0f  mov     rcx, [rbx+18h]
0x180049f13  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180049f18  test    al, al
0x180049f1a  jz      short loc_180049F95
0x180049f1c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180049f21  test    al, al
0x180049f23  jnz     short loc_180049F95
0x180049f25  lea     rdi, [rbx+20h]
0x180049f29  mov     rcx, rdi; SRWLock
0x180049f2c  call    cs:__imp_AcquireSRWLockExclusive
0x180049f32  cmp     byte ptr [rbx+41h], 0
0x180049f36  jnz     short loc_180049F86
0x180049f38  lea     rsi, [rbx+30h]
0x180049f3c  cmp     qword ptr [rsi], 0
0x180049f40  jnz     short loc_180049F74
0x180049f42  lea     rcx, [rsp+48h+var_28]; this
0x180049f47  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180049f4c  xor     r8d, r8d; pcbe
0x180049f4f  mov     rdx, rbx; pv
0x180049f52  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180049f59  call    cs:__imp_CreateThreadpoolTimer
0x180049f5f  mov     rdx, rax
0x180049f62  mov     rcx, rsi
0x180049f65  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180049f6a  lea     rcx, [rsp+48h+var_28]; this
0x180049f6f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180049f74  mov     r8d, 493E0h
0x180049f7a  lea     rdx, [rbx+41h]
0x180049f7e  mov     rcx, rsi
0x180049f81  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180049f86  test    rdi, rdi
0x180049f89  jz      short loc_180049F95
0x180049f8b  mov     rcx, rdi; SRWLock
0x180049f8e  call    cs:__imp_ReleaseSRWLockExclusive
0x180049f94  nop
0x180049f95  mov     rbx, [rsp+48h+arg_18]
0x180049f9a  add     rsp, 30h
0x180049f9e  pop     rdi
0x180049f9f  pop     rsi
0x180049fa0  pop     rbp
0x180049fa1  retn
```
