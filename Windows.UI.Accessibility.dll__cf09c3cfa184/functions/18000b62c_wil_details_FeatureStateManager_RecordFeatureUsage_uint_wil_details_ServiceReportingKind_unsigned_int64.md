# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b62c`
- end: `0x18000b706`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000cbb0`

## callees

- `0x1800084c0`
- `0x180008fa8`
- `0x180009b48`
- `0x18000b0b8`
- `0x18000b62c`
- `0x18000b70c`
- `0x18000b7ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b687`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b687`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6cd`

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
0x18000b62c  mov     [rsp+arg_8], rbx
0x18000b631  mov     [rsp+arg_10], rbp
0x18000b636  push    rsi
0x18000b637  push    rdi
0x18000b638  push    r14
0x18000b63a  sub     rsp, 20h
0x18000b63e  mov     rbp, r9
0x18000b641  mov     ebx, r8d
0x18000b644  mov     r14d, edx
0x18000b647  mov     rdi, rcx
0x18000b64a  cmp     byte ptr [rcx], 0
0x18000b64d  jz      loc_18000B6F3
0x18000b653  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b658  test    al, al
0x18000b65a  jz      loc_18000B6F3
0x18000b660  mov     rsi, [rdi+18h]
0x18000b664  cmp     ebx, 0FEh
0x18000b66a  jz      short loc_18000B6B5
0x18000b66c  cmp     ebx, 0C8h
0x18000b672  jb      short loc_18000B684
0x18000b674  cmp     ebx, 100h
0x18000b67a  jl      short loc_18000B6F3
0x18000b67c  cmp     ebx, 200h
0x18000b682  jnb     short loc_18000B6F3
0x18000b684  mov     rcx, rsi; SRWLock
0x18000b687  call    cs:__imp_AcquireSRWLockExclusive
0x18000b68d  mov     [rsp+38h+arg_0], rsi
0x18000b692  mov     r9, rbp
0x18000b695  mov     r8d, ebx
0x18000b698  mov     edx, r14d
0x18000b69b  mov     rcx, rsi
0x18000b69e  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b6a3  mov     bl, al
0x18000b6a5  lea     rcx, [rsp+38h+arg_0]
0x18000b6aa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b6af  test    bl, bl
0x18000b6b1  jz      short loc_18000B6F3
0x18000b6b3  jmp     short loc_18000B6BD
0x18000b6b5  mov     rcx, rsi; this
0x18000b6b8  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b6bd  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000b6c2  test    al, al
0x18000b6c4  jnz     short loc_18000B6F3
0x18000b6c6  lea     rbx, [rdi+20h]
0x18000b6ca  mov     rcx, rbx; SRWLock
0x18000b6cd  call    cs:__imp_AcquireSRWLockExclusive
0x18000b6d3  mov     [rsp+38h+arg_0], rbx
0x18000b6d8  lea     rdx, [rdi+41h]
0x18000b6dc  lea     rcx, [rdi+30h]
0x18000b6e0  mov     r8, rdi
0x18000b6e3  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000b6e8  lea     rcx, [rsp+38h+arg_0]
0x18000b6ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b6f2  nop
0x18000b6f3  mov     rbx, [rsp+38h+arg_8]
0x18000b6f8  mov     rbp, [rsp+38h+arg_10]
0x18000b6fd  add     rsp, 20h
0x18000b701  pop     r14
0x18000b703  pop     rdi
0x18000b704  pop     rsi
0x18000b705  retn
```
