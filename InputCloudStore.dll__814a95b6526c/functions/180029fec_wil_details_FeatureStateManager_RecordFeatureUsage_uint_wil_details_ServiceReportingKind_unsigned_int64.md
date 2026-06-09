# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180029fec`
- end: `0x18002a0c6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002ae80`

## callees

- `0x180006814`
- `0x18001b3fc`
- `0x180028970`
- `0x180029254`
- `0x180029fec`
- `0x18002a0cc`
- `0x18002a1ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a047`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a08d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a047`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a08d`

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
0x180029fec  mov     [rsp+arg_8], rbx
0x180029ff1  mov     [rsp+arg_10], rbp
0x180029ff6  push    rsi
0x180029ff7  push    rdi
0x180029ff8  push    r14
0x180029ffa  sub     rsp, 20h
0x180029ffe  mov     rbp, r9
0x18002a001  mov     ebx, r8d
0x18002a004  mov     r14d, edx
0x18002a007  mov     rdi, rcx
0x18002a00a  cmp     byte ptr [rcx], 0
0x18002a00d  jz      loc_18002A0B3
0x18002a013  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18002a018  test    al, al
0x18002a01a  jz      loc_18002A0B3
0x18002a020  mov     rsi, [rdi+18h]
0x18002a024  cmp     ebx, 0FEh
0x18002a02a  jz      short loc_18002A075
0x18002a02c  cmp     ebx, 0C8h
0x18002a032  jb      short loc_18002A044
0x18002a034  cmp     ebx, 100h
0x18002a03a  jl      short loc_18002A0B3
0x18002a03c  cmp     ebx, 200h
0x18002a042  jnb     short loc_18002A0B3
0x18002a044  mov     rcx, rsi; SRWLock
0x18002a047  call    cs:__imp_AcquireSRWLockExclusive
0x18002a04d  mov     [rsp+38h+arg_0], rsi
0x18002a052  mov     r9, rbp
0x18002a055  mov     r8d, ebx
0x18002a058  mov     edx, r14d
0x18002a05b  mov     rcx, rsi
0x18002a05e  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18002a063  mov     bl, al
0x18002a065  lea     rcx, [rsp+38h+arg_0]
0x18002a06a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a06f  test    bl, bl
0x18002a071  jz      short loc_18002A0B3
0x18002a073  jmp     short loc_18002A07D
0x18002a075  mov     rcx, rsi; this
0x18002a078  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002a07d  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002a082  test    al, al
0x18002a084  jnz     short loc_18002A0B3
0x18002a086  lea     rbx, [rdi+20h]
0x18002a08a  mov     rcx, rbx; SRWLock
0x18002a08d  call    cs:__imp_AcquireSRWLockExclusive
0x18002a093  mov     [rsp+38h+arg_0], rbx
0x18002a098  lea     rdx, [rdi+41h]
0x18002a09c  lea     rcx, [rdi+30h]
0x18002a0a0  mov     r8, rdi
0x18002a0a3  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18002a0a8  lea     rcx, [rsp+38h+arg_0]
0x18002a0ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a0b2  nop
0x18002a0b3  mov     rbx, [rsp+38h+arg_8]
0x18002a0b8  mov     rbp, [rsp+38h+arg_10]
0x18002a0bd  add     rsp, 20h
0x18002a0c1  pop     r14
0x18002a0c3  pop     rdi
0x18002a0c4  pop     rsi
0x18002a0c5  retn
```
