# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800268f4`
- end: `0x180026990`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180028050`

## callees

- `0x18000fff0`
- `0x1800221d8`
- `0x1800233cc`
- `0x180024528`
- `0x180026824`
- `0x1800268f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002694e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002694e`

## pseudocode

```c
char __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  _UNKNOWN **v4; // rax
  wil *v9; // rcx
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = &retaddr;
  if ( *(_BYTE *)a1 )
  {
    LOBYTE(v4) = wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1);
    if ( (_BYTE)v4 )
    {
      LOBYTE(v4) = wil::details_abi::FeatureStateData::RecordFeatureUsage(*(_QWORD *)(a1 + 24), a2, a3, a4, -2);
      if ( (_BYTE)v4 )
      {
        LOBYTE(v4) = wil::ProcessShutdownInProgress(v9);
        if ( !(_BYTE)v4 )
        {
          AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
          v12 = a1 + 32;
          wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(
            (_QWORD *)(a1 + 48),
            (_BYTE *)(a1 + 65),
            (void *)a1);
          LOBYTE(v4) = wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
        }
      }
    }
  }
  return (char)v4;
}

```

## disassembly

```asm
0x1800268f4  mov     rax, rsp
0x1800268f7  push    rdi
0x1800268f8  sub     rsp, 30h
0x1800268fc  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x180026904  mov     [rax+10h], rbx
0x180026908  mov     [rax+18h], rbp
0x18002690c  mov     [rax+20h], rsi
0x180026910  mov     rbx, r9
0x180026913  mov     esi, r8d
0x180026916  mov     ebp, edx
0x180026918  mov     rdi, rcx
0x18002691b  cmp     byte ptr [rcx], 0
0x18002691e  jz      short loc_18002697A
0x180026920  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180026925  test    al, al
0x180026927  jz      short loc_18002697A
0x180026929  mov     r9, rbx
0x18002692c  mov     r8d, esi
0x18002692f  mov     edx, ebp
0x180026931  mov     rcx, [rdi+18h]
0x180026935  call    ?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18002693a  test    al, al
0x18002693c  jz      short loc_18002697A
0x18002693e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180026943  test    al, al
0x180026945  jnz     short loc_18002697A
0x180026947  lea     rbx, [rdi+20h]
0x18002694b  mov     rcx, rbx; SRWLock
0x18002694e  call    cs:__imp_AcquireSRWLockExclusive
0x180026955  nop     dword ptr [rax+rax+00h]
0x18002695a  mov     [rsp+38h+arg_0], rbx
0x18002695f  lea     rdx, [rdi+41h]
0x180026963  lea     rcx, [rdi+30h]
0x180026967  mov     r8, rdi
0x18002696a  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18002696f  lea     rcx, [rsp+38h+arg_0]
0x180026974  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026979  nop
0x18002697a  mov     rbx, [rsp+38h+arg_8]
0x18002697f  mov     rbp, [rsp+38h+arg_10]
0x180026984  mov     rsi, [rsp+38h+arg_18]
0x180026989  add     rsp, 30h
0x18002698d  pop     rdi
0x18002698e  retn
```
