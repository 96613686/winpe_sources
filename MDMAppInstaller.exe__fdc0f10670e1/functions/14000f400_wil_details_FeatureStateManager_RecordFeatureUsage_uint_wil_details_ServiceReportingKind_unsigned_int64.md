# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000f400`
- end: `0x14000f4da`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1400112c0`

## callees

- `0x14000552c`
- `0x140007e1c`
- `0x1400092f0`
- `0x14000b2e0`
- `0x14000f400`
- `0x14000f4e0`
- `0x14000f5bc`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f45b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f4a1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f45b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f4a1`

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
0x14000f400  mov     [rsp+arg_8], rbx
0x14000f405  mov     [rsp+arg_10], rbp
0x14000f40a  push    rsi
0x14000f40b  push    rdi
0x14000f40c  push    r14
0x14000f40e  sub     rsp, 20h
0x14000f412  mov     rbp, r9
0x14000f415  mov     ebx, r8d
0x14000f418  mov     r14d, edx
0x14000f41b  mov     rdi, rcx
0x14000f41e  cmp     byte ptr [rcx], 0
0x14000f421  jz      loc_14000F4C7
0x14000f427  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000f42c  test    al, al
0x14000f42e  jz      loc_14000F4C7
0x14000f434  mov     rsi, [rdi+18h]
0x14000f438  cmp     ebx, 0FEh
0x14000f43e  jz      short loc_14000F489
0x14000f440  cmp     ebx, 0C8h
0x14000f446  jb      short loc_14000F458
0x14000f448  cmp     ebx, 100h
0x14000f44e  jl      short loc_14000F4C7
0x14000f450  cmp     ebx, 200h
0x14000f456  jnb     short loc_14000F4C7
0x14000f458  mov     rcx, rsi; SRWLock
0x14000f45b  call    cs:__imp_AcquireSRWLockExclusive
0x14000f461  mov     [rsp+38h+arg_0], rsi
0x14000f466  mov     r9, rbp
0x14000f469  mov     r8d, ebx
0x14000f46c  mov     edx, r14d
0x14000f46f  mov     rcx, rsi
0x14000f472  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000f477  mov     bl, al
0x14000f479  lea     rcx, [rsp+38h+arg_0]
0x14000f47e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f483  test    bl, bl
0x14000f485  jz      short loc_14000F4C7
0x14000f487  jmp     short loc_14000F491
0x14000f489  mov     rcx, rsi; this
0x14000f48c  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000f491  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000f496  test    al, al
0x14000f498  jnz     short loc_14000F4C7
0x14000f49a  lea     rbx, [rdi+20h]
0x14000f49e  mov     rcx, rbx; SRWLock
0x14000f4a1  call    cs:__imp_AcquireSRWLockExclusive
0x14000f4a7  mov     [rsp+38h+arg_0], rbx
0x14000f4ac  lea     rdx, [rdi+41h]
0x14000f4b0  lea     rcx, [rdi+30h]
0x14000f4b4  mov     r8, rdi
0x14000f4b7  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x14000f4bc  lea     rcx, [rsp+38h+arg_0]
0x14000f4c1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f4c6  nop
0x14000f4c7  mov     rbx, [rsp+38h+arg_8]
0x14000f4cc  mov     rbp, [rsp+38h+arg_10]
0x14000f4d1  add     rsp, 20h
0x14000f4d5  pop     r14
0x14000f4d7  pop     rdi
0x14000f4d8  pop     rsi
0x14000f4d9  retn
```
