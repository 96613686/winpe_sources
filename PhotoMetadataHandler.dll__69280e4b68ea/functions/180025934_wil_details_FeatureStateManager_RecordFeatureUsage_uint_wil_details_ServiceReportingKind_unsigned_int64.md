# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180025934`
- end: `0x180025a1e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180026930`

## callees

- `0x18000f828`
- `0x1800161d8`
- `0x180022f44`
- `0x180024170`
- `0x180025934`
- `0x180025a24`
- `0x180025b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025993`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800259df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025993`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800259df`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        _BYTE *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  _BYTE *v8; // rsi
  char v9; // bl
  wil *v10; // rcx
  _BYTE *v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = (_BYTE *)*((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
        v11 = a1 + 32;
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
0x180025934  mov     [rsp+arg_8], rbx
0x180025939  mov     [rsp+arg_10], rbp
0x18002593e  push    rsi
0x18002593f  push    rdi
0x180025940  push    r14
0x180025942  sub     rsp, 20h
0x180025946  cmp     byte ptr [rcx], 0
0x180025949  mov     rbp, r9
0x18002594c  mov     ebx, r8d
0x18002594f  mov     r14d, edx
0x180025952  mov     rdi, rcx
0x180025955  jz      loc_180025A0A
0x18002595b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180025960  test    al, al
0x180025962  jz      loc_180025A0A
0x180025968  mov     rsi, [rdi+18h]
0x18002596c  cmp     ebx, 0FEh
0x180025972  jz      short loc_1800259C7
0x180025974  cmp     ebx, 0C8h
0x18002597a  jb      short loc_180025990
0x18002597c  cmp     ebx, 100h
0x180025982  jl      loc_180025A0A
0x180025988  cmp     ebx, 200h
0x18002598e  jnb     short loc_180025A0A
0x180025990  mov     rcx, rsi; SRWLock
0x180025993  call    cs:__imp_AcquireSRWLockExclusive
0x18002599a  nop     dword ptr [rax+rax+00h]
0x18002599f  mov     r9, rbp
0x1800259a2  mov     [rsp+38h+arg_0], rsi
0x1800259a7  mov     r8d, ebx
0x1800259aa  mov     edx, r14d
0x1800259ad  mov     rcx, rsi
0x1800259b0  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800259b5  lea     rcx, [rsp+38h+arg_0]
0x1800259ba  mov     bl, al
0x1800259bc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800259c1  test    bl, bl
0x1800259c3  jz      short loc_180025A0A
0x1800259c5  jmp     short loc_1800259CF
0x1800259c7  mov     rcx, rsi; this
0x1800259ca  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800259cf  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800259d4  test    al, al
0x1800259d6  jnz     short loc_180025A0A
0x1800259d8  lea     rbx, [rdi+20h]
0x1800259dc  mov     rcx, rbx; SRWLock
0x1800259df  call    cs:__imp_AcquireSRWLockExclusive
0x1800259e6  nop     dword ptr [rax+rax+00h]
0x1800259eb  lea     rdx, [rdi+41h]
0x1800259ef  mov     [rsp+38h+arg_0], rbx
0x1800259f4  lea     rcx, [rdi+30h]
0x1800259f8  mov     r8, rdi
0x1800259fb  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x180025a00  lea     rcx, [rsp+38h+arg_0]
0x180025a05  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025a0a  mov     rbx, [rsp+38h+arg_8]
0x180025a0f  mov     rbp, [rsp+38h+arg_10]
0x180025a14  add     rsp, 20h
0x180025a18  pop     r14
0x180025a1a  pop     rdi
0x180025a1b  pop     rsi
0x180025a1c  retn
```
