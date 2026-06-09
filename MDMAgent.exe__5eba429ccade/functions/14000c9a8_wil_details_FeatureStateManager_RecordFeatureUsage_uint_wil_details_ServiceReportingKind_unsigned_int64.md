# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000c9a8`
- end: `0x14000ca81`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `217`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x140010ec0`

## callees

- `0x14000660c`
- `0x140008a50`
- `0x14000905c`
- `0x14000b36c`
- `0x14000c9a8`
- `0x14000ca88`
- `0x14000cb50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ca49`

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
0x14000c9a8  mov     [rsp+arg_8], rbx
0x14000c9ad  mov     [rsp+arg_10], rbp
0x14000c9b2  push    rsi
0x14000c9b3  push    rdi
0x14000c9b4  push    r14
0x14000c9b6  sub     rsp, 20h
0x14000c9ba  cmp     byte ptr [rcx], 0
0x14000c9bd  mov     rbp, r9
0x14000c9c0  mov     ebx, r8d
0x14000c9c3  mov     r14d, edx
0x14000c9c6  mov     rdi, rcx
0x14000c9c9  jz      loc_14000CA6E
0x14000c9cf  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c9d4  test    al, al
0x14000c9d6  jz      loc_14000CA6E
0x14000c9dc  mov     rsi, [rdi+18h]
0x14000c9e0  cmp     ebx, 0FEh
0x14000c9e6  jz      short loc_14000CA31
0x14000c9e8  cmp     ebx, 0C8h
0x14000c9ee  jb      short loc_14000CA00
0x14000c9f0  cmp     ebx, 100h
0x14000c9f6  jl      short loc_14000CA6E
0x14000c9f8  cmp     ebx, 200h
0x14000c9fe  jnb     short loc_14000CA6E
0x14000ca00  mov     rcx, rsi; SRWLock
0x14000ca03  call    cs:__imp_AcquireSRWLockExclusive
0x14000ca09  mov     r9, rbp
0x14000ca0c  mov     [rsp+38h+arg_0], rsi
0x14000ca11  mov     r8d, ebx
0x14000ca14  mov     edx, r14d
0x14000ca17  mov     rcx, rsi
0x14000ca1a  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000ca1f  lea     rcx, [rsp+38h+arg_0]
0x14000ca24  mov     bl, al
0x14000ca26  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ca2b  test    bl, bl
0x14000ca2d  jz      short loc_14000CA6E
0x14000ca2f  jmp     short loc_14000CA39
0x14000ca31  mov     rcx, rsi; this
0x14000ca34  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000ca39  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000ca3e  test    al, al
0x14000ca40  jnz     short loc_14000CA6E
0x14000ca42  lea     rbx, [rdi+20h]
0x14000ca46  mov     rcx, rbx; SRWLock
0x14000ca49  call    cs:__imp_AcquireSRWLockExclusive
0x14000ca4f  lea     rdx, [rdi+41h]
0x14000ca53  mov     [rsp+38h+arg_0], rbx
0x14000ca58  lea     rcx, [rdi+30h]
0x14000ca5c  mov     r8, rdi
0x14000ca5f  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x14000ca64  lea     rcx, [rsp+38h+arg_0]
0x14000ca69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ca6e  mov     rbx, [rsp+38h+arg_8]
0x14000ca73  mov     rbp, [rsp+38h+arg_10]
0x14000ca78  add     rsp, 20h
0x14000ca7c  pop     r14
0x14000ca7e  pop     rdi
0x14000ca7f  pop     rsi
0x14000ca80  retn
```
