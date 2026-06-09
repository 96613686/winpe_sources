# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007744`
- end: `0x14000781e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140009150`

## callees

- `0x140002dd0`
- `0x140004250`
- `0x140004ec8`
- `0x140005818`
- `0x140007744`
- `0x140007824`
- `0x140007924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000779f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400077e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000779f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400077e5`

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
0x140007744  mov     [rsp+arg_8], rbx
0x140007749  mov     [rsp+arg_10], rbp
0x14000774e  push    rsi
0x14000774f  push    rdi
0x140007750  push    r14
0x140007752  sub     rsp, 20h
0x140007756  mov     rbp, r9
0x140007759  mov     ebx, r8d
0x14000775c  mov     r14d, edx
0x14000775f  mov     rdi, rcx
0x140007762  cmp     byte ptr [rcx], 0
0x140007765  jz      loc_14000780B
0x14000776b  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007770  test    al, al
0x140007772  jz      loc_14000780B
0x140007778  mov     rsi, [rdi+18h]
0x14000777c  cmp     ebx, 0FEh
0x140007782  jz      short loc_1400077CD
0x140007784  cmp     ebx, 0C8h
0x14000778a  jb      short loc_14000779C
0x14000778c  cmp     ebx, 100h
0x140007792  jl      short loc_14000780B
0x140007794  cmp     ebx, 200h
0x14000779a  jnb     short loc_14000780B
0x14000779c  mov     rcx, rsi; SRWLock
0x14000779f  call    cs:__imp_AcquireSRWLockExclusive
0x1400077a5  mov     [rsp+38h+arg_0], rsi
0x1400077aa  mov     r9, rbp
0x1400077ad  mov     r8d, ebx
0x1400077b0  mov     edx, r14d
0x1400077b3  mov     rcx, rsi
0x1400077b6  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400077bb  mov     bl, al
0x1400077bd  lea     rcx, [rsp+38h+arg_0]
0x1400077c2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400077c7  test    bl, bl
0x1400077c9  jz      short loc_14000780B
0x1400077cb  jmp     short loc_1400077D5
0x1400077cd  mov     rcx, rsi; this
0x1400077d0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400077d5  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400077da  test    al, al
0x1400077dc  jnz     short loc_14000780B
0x1400077de  lea     rbx, [rdi+20h]
0x1400077e2  mov     rcx, rbx; SRWLock
0x1400077e5  call    cs:__imp_AcquireSRWLockExclusive
0x1400077eb  mov     [rsp+38h+arg_0], rbx
0x1400077f0  lea     rdx, [rdi+41h]
0x1400077f4  lea     rcx, [rdi+30h]
0x1400077f8  mov     r8, rdi
0x1400077fb  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x140007800  lea     rcx, [rsp+38h+arg_0]
0x140007805  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000780a  nop
0x14000780b  mov     rbx, [rsp+38h+arg_8]
0x140007810  mov     rbp, [rsp+38h+arg_10]
0x140007815  add     rsp, 20h
0x140007819  pop     r14
0x14000781b  pop     rdi
0x14000781c  pop     rsi
0x14000781d  retn
```
