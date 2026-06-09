# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800080d4`
- end: `0x1800081a9`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18000a3b0`

## callees

- `0x180002dcc`
- `0x180003d78`
- `0x180004650`
- `0x1800048c8`
- `0x180007c98`
- `0x1800080d4`
- `0x1800081b0`
- `0x1800082cc`

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
  char v11; // [rsp+40h] [rbp+8h] BYREF

  if ( *a1 && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
  {
    v8 = *((_QWORD *)a1 + 3);
    if ( a3 == 254 )
    {
      wil::details_abi::FeatureStateData::RecordUsage(*((wil::details_abi::FeatureStateData **)a1 + 3));
LABEL_10:
      if ( !wil::ProcessShutdownInProgress(v10) )
      {
        wil::AcquireSRWLockExclusive(&v11, a1 + 32);
        wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>((_QWORD *)a1 + 6, a1 + 65, a1);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
      }
      return;
    }
    if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
    {
      wil::AcquireSRWLockExclusive(&v11, *((_QWORD *)a1 + 3));
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
0x1800080d4  mov     [rsp+arg_8], rbx
0x1800080d9  mov     [rsp+arg_10], rbp
0x1800080de  push    rsi
0x1800080df  push    rdi
0x1800080e0  push    r14
0x1800080e2  sub     rsp, 20h
0x1800080e6  mov     rbp, r9
0x1800080e9  mov     ebx, r8d
0x1800080ec  mov     r14d, edx
0x1800080ef  mov     rdi, rcx
0x1800080f2  cmp     byte ptr [rcx], 0
0x1800080f5  jz      loc_180008196
0x1800080fb  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008100  test    al, al
0x180008102  jz      loc_180008196
0x180008108  mov     rsi, [rdi+18h]
0x18000810c  cmp     ebx, 0FEh
0x180008112  jz      short loc_18000815C
0x180008114  cmp     ebx, 0C8h
0x18000811a  jb      short loc_18000812C
0x18000811c  cmp     ebx, 100h
0x180008122  jl      short loc_180008196
0x180008124  cmp     ebx, 200h
0x18000812a  jnb     short loc_180008196
0x18000812c  mov     rdx, rsi
0x18000812f  lea     rcx, [rsp+38h+arg_0]
0x180008134  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180008139  mov     r9, rbp
0x18000813c  mov     r8d, ebx
0x18000813f  mov     edx, r14d
0x180008142  mov     rcx, rsi
0x180008145  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000814a  mov     bl, al
0x18000814c  lea     rcx, [rsp+38h+arg_0]
0x180008151  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008156  test    bl, bl
0x180008158  jz      short loc_180008196
0x18000815a  jmp     short loc_180008164
0x18000815c  mov     rcx, rsi; this
0x18000815f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008164  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180008169  test    al, al
0x18000816b  jnz     short loc_180008196
0x18000816d  lea     rdx, [rdi+20h]
0x180008171  lea     rcx, [rsp+38h+arg_0]
0x180008176  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000817b  lea     rdx, [rdi+41h]
0x18000817f  lea     rcx, [rdi+30h]
0x180008183  mov     r8, rdi
0x180008186  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x18000818b  lea     rcx, [rsp+38h+arg_0]
0x180008190  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008195  nop
0x180008196  mov     rbx, [rsp+38h+arg_8]
0x18000819b  mov     rbp, [rsp+38h+arg_10]
0x1800081a0  add     rsp, 20h
0x1800081a4  pop     r14
0x1800081a6  pop     rdi
0x1800081a7  pop     rsi
0x1800081a8  retn
```
