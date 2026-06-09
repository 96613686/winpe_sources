# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b9b0`
- end: `0x18000ba71`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `193`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180011de0`

## callees

- `0x180007160`
- `0x18000991c`
- `0x18000b49c`
- `0x18000b9b0`
- `0x18000ba78`
- `0x18000bb00`
- `0x18000bb20`
- `0x18000bb44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b9ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b9ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ba2c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ba2c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  wil *v8; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  char v10; // [rsp+50h] [rbp+8h] BYREF

  if ( *a1
    && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1)
    && wil::details_abi::FeatureStateData::RecordFeatureUsage(*((_QWORD *)a1 + 3), a2, a3, a4)
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
0x18000b9b0  push    rbx
0x18000b9b2  push    rbp
0x18000b9b3  push    rsi
0x18000b9b4  push    rdi
0x18000b9b5  sub     rsp, 28h
0x18000b9b9  mov     rdi, r9
0x18000b9bc  mov     esi, r8d
0x18000b9bf  mov     ebp, edx
0x18000b9c1  mov     rbx, rcx
0x18000b9c4  cmp     byte ptr [rcx], 0
0x18000b9c7  jz      loc_18000BA68
0x18000b9cd  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b9d2  test    al, al
0x18000b9d4  jz      loc_18000BA68
0x18000b9da  mov     r9, rdi
0x18000b9dd  mov     r8d, esi
0x18000b9e0  mov     edx, ebp
0x18000b9e2  mov     rcx, [rbx+18h]
0x18000b9e6  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b9eb  test    al, al
0x18000b9ed  jz      short loc_18000BA68
0x18000b9ef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000b9f4  test    al, al
0x18000b9f6  jnz     short loc_18000BA68
0x18000b9f8  lea     rdi, [rbx+20h]
0x18000b9fc  mov     rcx, rdi; SRWLock
0x18000b9ff  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba05  cmp     byte ptr [rbx+41h], 0
0x18000ba09  jnz     short loc_18000BA59
0x18000ba0b  lea     rsi, [rbx+30h]
0x18000ba0f  cmp     qword ptr [rsi], 0
0x18000ba13  jnz     short loc_18000BA47
0x18000ba15  lea     rcx, [rsp+48h+arg_0]; this
0x18000ba1a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000ba1f  xor     r8d, r8d; pcbe
0x18000ba22  mov     rdx, rbx; pv
0x18000ba25  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ba2c  call    cs:__imp_CreateThreadpoolTimer
0x18000ba32  mov     rdx, rax
0x18000ba35  mov     rcx, rsi
0x18000ba38  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ba3d  lea     rcx, [rsp+48h+arg_0]; this
0x18000ba42  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000ba47  mov     r8d, 493E0h
0x18000ba4d  lea     rdx, [rbx+41h]
0x18000ba51  mov     rcx, rsi
0x18000ba54  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000ba59  test    rdi, rdi
0x18000ba5c  jz      short loc_18000BA68
0x18000ba5e  mov     rcx, rdi; SRWLock
0x18000ba61  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba67  nop
0x18000ba68  add     rsp, 28h
0x18000ba6c  pop     rdi
0x18000ba6d  pop     rsi
0x18000ba6e  pop     rbp
0x18000ba6f  pop     rbx
0x18000ba70  retn
```
