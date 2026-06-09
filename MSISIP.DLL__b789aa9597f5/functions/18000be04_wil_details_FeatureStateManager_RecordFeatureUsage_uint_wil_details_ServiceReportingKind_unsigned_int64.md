# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000be04`
- end: `0x18000bee8`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000cb80`

## callees

- `0x1800065d4`
- `0x180007334`
- `0x1800084c8`
- `0x18000afa0`
- `0x18000be04`
- `0x18000bef0`
- `0x18000bf80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000beaf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000beaf`

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
  _BYTE *v11; // [rsp+50h] [rbp+8h] BYREF

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
      v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(v8, a2, a3, a4, -2);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      if ( v9 )
        goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x18000be04  push    rsi
0x18000be06  push    rdi
0x18000be07  push    r14
0x18000be09  sub     rsp, 30h
0x18000be0d  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18000be16  mov     [rsp+48h+arg_8], rbx
0x18000be1b  mov     [rsp+48h+arg_10], rbp
0x18000be20  mov     rbp, r9
0x18000be23  mov     ebx, r8d
0x18000be26  mov     r14d, edx
0x18000be29  mov     rdi, rcx
0x18000be2c  cmp     byte ptr [rcx], 0
0x18000be2f  jz      loc_18000BED5
0x18000be35  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000be3a  test    al, al
0x18000be3c  jz      loc_18000BED5
0x18000be42  mov     rsi, [rdi+18h]
0x18000be46  cmp     ebx, 0FEh
0x18000be4c  jz      short loc_18000BE97
0x18000be4e  cmp     ebx, 0C8h
0x18000be54  jb      short loc_18000BE66
0x18000be56  cmp     ebx, 100h
0x18000be5c  jl      short loc_18000BED5
0x18000be5e  cmp     ebx, 200h
0x18000be64  jnb     short loc_18000BED5
0x18000be66  mov     rcx, rsi; SRWLock
0x18000be69  call    cs:__imp_AcquireSRWLockExclusive
0x18000be6f  mov     [rsp+48h+arg_0], rsi
0x18000be74  mov     r9, rbp
0x18000be77  mov     r8d, ebx
0x18000be7a  mov     edx, r14d
0x18000be7d  mov     rcx, rsi
0x18000be80  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000be85  mov     bl, al
0x18000be87  lea     rcx, [rsp+48h+arg_0]
0x18000be8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000be91  test    bl, bl
0x18000be93  jz      short loc_18000BED5
0x18000be95  jmp     short loc_18000BE9F
0x18000be97  mov     rcx, rsi; this
0x18000be9a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000be9f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000bea4  test    al, al
0x18000bea6  jnz     short loc_18000BED5
0x18000bea8  lea     rbx, [rdi+20h]
0x18000beac  mov     rcx, rbx; SRWLock
0x18000beaf  call    cs:__imp_AcquireSRWLockExclusive
0x18000beb5  mov     [rsp+48h+arg_0], rbx
0x18000beba  lea     rdx, [rdi+41h]
0x18000bebe  lea     rcx, [rdi+30h]
0x18000bec2  mov     r8, rdi
0x18000bec5  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000beca  lea     rcx, [rsp+48h+arg_0]
0x18000becf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bed4  nop
0x18000bed5  mov     rbx, [rsp+48h+arg_8]
0x18000beda  mov     rbp, [rsp+48h+arg_10]
0x18000bedf  add     rsp, 30h
0x18000bee3  pop     r14
0x18000bee5  pop     rdi
0x18000bee6  pop     rsi
0x18000bee7  retn
```
