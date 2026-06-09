# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800087e4`
- end: `0x1800088be`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000a1f0`

## callees

- `0x180004cec`
- `0x180005c8c`
- `0x1800066b8`
- `0x180008430`
- `0x1800087e4`
- `0x1800088c4`
- `0x1800089dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000883f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008885`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000883f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008885`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  RTL_SRWLOCK *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = (RTL_SRWLOCK *)(a1 + 32);
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v11 = v8;
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x1800087e4  mov     [rsp+arg_8], rbx
0x1800087e9  mov     [rsp+arg_10], rbp
0x1800087ee  push    rsi
0x1800087ef  push    rdi
0x1800087f0  push    r14
0x1800087f2  sub     rsp, 20h
0x1800087f6  mov     rbp, r9
0x1800087f9  mov     ebx, r8d
0x1800087fc  mov     r14d, edx
0x1800087ff  mov     rdi, rcx
0x180008802  cmp     byte ptr [rcx], 0
0x180008805  jz      loc_1800088AB
0x18000880b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008810  test    al, al
0x180008812  jz      loc_1800088AB
0x180008818  mov     rsi, [rdi+18h]
0x18000881c  cmp     ebx, 0FEh
0x180008822  jz      short loc_18000886D
0x180008824  cmp     ebx, 0C8h
0x18000882a  jb      short loc_18000883C
0x18000882c  cmp     ebx, 100h
0x180008832  jl      short loc_1800088AB
0x180008834  cmp     ebx, 200h
0x18000883a  jnb     short loc_1800088AB
0x18000883c  mov     rcx, rsi; SRWLock
0x18000883f  call    cs:__imp_AcquireSRWLockExclusive
0x180008845  mov     [rsp+38h+arg_0], rsi
0x18000884a  mov     r9, rbp
0x18000884d  mov     r8d, ebx
0x180008850  mov     edx, r14d
0x180008853  mov     rcx, rsi
0x180008856  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000885b  mov     bl, al
0x18000885d  lea     rcx, [rsp+38h+arg_0]
0x180008862  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008867  test    bl, bl
0x180008869  jz      short loc_1800088AB
0x18000886b  jmp     short loc_180008875
0x18000886d  mov     rcx, rsi; this
0x180008870  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008875  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000887a  test    al, al
0x18000887c  jnz     short loc_1800088AB
0x18000887e  lea     rbx, [rdi+20h]
0x180008882  mov     rcx, rbx; SRWLock
0x180008885  call    cs:__imp_AcquireSRWLockExclusive
0x18000888b  mov     [rsp+38h+arg_0], rbx
0x180008890  lea     rdx, [rdi+41h]
0x180008894  lea     rcx, [rdi+30h]
0x180008898  mov     r8, rdi
0x18000889b  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x1800088a0  lea     rcx, [rsp+38h+arg_0]
0x1800088a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800088aa  nop
0x1800088ab  mov     rbx, [rsp+38h+arg_8]
0x1800088b0  mov     rbp, [rsp+38h+arg_10]
0x1800088b5  add     rsp, 20h
0x1800088b9  pop     r14
0x1800088bb  pop     rdi
0x1800088bc  pop     rsi
0x1800088bd  retn
```
