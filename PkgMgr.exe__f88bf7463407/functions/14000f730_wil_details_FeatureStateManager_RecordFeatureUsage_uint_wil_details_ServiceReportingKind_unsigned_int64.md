# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000f730`
- end: `0x14000f7fa`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140010430`

## callees

- `0x140005560`
- `0x14000e29c`
- `0x14000e5f8`
- `0x14000ebdc`
- `0x14000f730`
- `0x14000f800`
- `0x14000f908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f784`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f7ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f784`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000f7ca`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  _QWORD v11[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = *((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11[0] = a1 + 32;
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      AcquireSRWLockExclusive(*((PSRWLOCK *)a1 + 3));
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4, v8);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x14000f730  push    rbx
0x14000f732  push    rbp
0x14000f733  push    rsi
0x14000f734  push    rdi
0x14000f735  push    r14
0x14000f737  sub     rsp, 30h
0x14000f73b  cmp     byte ptr [rcx], 0
0x14000f73e  mov     rbp, r9
0x14000f741  mov     ebx, r8d
0x14000f744  mov     r14d, edx
0x14000f747  mov     rdi, rcx
0x14000f74a  jz      loc_14000F7EF
0x14000f750  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000f755  test    al, al
0x14000f757  jz      loc_14000F7EF
0x14000f75d  mov     rsi, [rdi+18h]
0x14000f761  cmp     ebx, 0FEh
0x14000f767  jz      short loc_14000F7B2
0x14000f769  cmp     ebx, 0C8h
0x14000f76f  jb      short loc_14000F781
0x14000f771  cmp     ebx, 100h
0x14000f777  jl      short loc_14000F7EF
0x14000f779  cmp     ebx, 200h
0x14000f77f  jnb     short loc_14000F7EF
0x14000f781  mov     rcx, rsi; SRWLock
0x14000f784  call    cs:__imp_AcquireSRWLockExclusive
0x14000f78a  mov     r9, rbp
0x14000f78d  mov     [rsp+58h+var_38], rsi
0x14000f792  mov     r8d, ebx
0x14000f795  mov     edx, r14d
0x14000f798  mov     rcx, rsi
0x14000f79b  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000f7a0  lea     rcx, [rsp+58h+var_38]
0x14000f7a5  mov     bl, al
0x14000f7a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f7ac  test    bl, bl
0x14000f7ae  jz      short loc_14000F7EF
0x14000f7b0  jmp     short loc_14000F7BA
0x14000f7b2  mov     rcx, rsi; this
0x14000f7b5  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000f7ba  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000f7bf  test    al, al
0x14000f7c1  jnz     short loc_14000F7EF
0x14000f7c3  lea     rbx, [rdi+20h]
0x14000f7c7  mov     rcx, rbx; SRWLock
0x14000f7ca  call    cs:__imp_AcquireSRWLockExclusive
0x14000f7d0  lea     rdx, [rdi+41h]
0x14000f7d4  mov     [rsp+58h+var_38], rbx
0x14000f7d9  lea     rcx, [rdi+30h]
0x14000f7dd  mov     r8, rdi
0x14000f7e0  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x14000f7e5  lea     rcx, [rsp+58h+var_38]
0x14000f7ea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f7ef  add     rsp, 30h
0x14000f7f3  pop     r14
0x14000f7f5  pop     rdi
0x14000f7f6  pop     rsi
0x14000f7f7  pop     rbp
0x14000f7f8  pop     rbx
0x14000f7f9  retn
```
