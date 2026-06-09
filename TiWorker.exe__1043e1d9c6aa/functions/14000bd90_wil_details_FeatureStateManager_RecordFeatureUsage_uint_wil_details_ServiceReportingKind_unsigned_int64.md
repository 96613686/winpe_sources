# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000bd90`
- end: `0x14000be5a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `202`
- prototype: `void __fastcall(_BYTE *, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x14000ced0`

## callees

- `0x14000528c`
- `0x140009b50`
- `0x14000a06c`
- `0x14000aacc`
- `0x14000bd90`
- `0x14000be60`
- `0x14000bf68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bde4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000be2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000bde4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000be2a`

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
  RTL_SRWLOCK *v11[7]; // [rsp+20h] [rbp-38h] BYREF

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
        v11[0] = (RTL_SRWLOCK *)(a1 + 32);
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
0x14000bd90  push    rbx
0x14000bd92  push    rbp
0x14000bd93  push    rsi
0x14000bd94  push    rdi
0x14000bd95  push    r14
0x14000bd97  sub     rsp, 30h
0x14000bd9b  cmp     byte ptr [rcx], 0
0x14000bd9e  mov     rbp, r9
0x14000bda1  mov     ebx, r8d
0x14000bda4  mov     r14d, edx
0x14000bda7  mov     rdi, rcx
0x14000bdaa  jz      loc_14000BE4F
0x14000bdb0  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000bdb5  test    al, al
0x14000bdb7  jz      loc_14000BE4F
0x14000bdbd  mov     rsi, [rdi+18h]
0x14000bdc1  cmp     ebx, 0FEh
0x14000bdc7  jz      short loc_14000BE12
0x14000bdc9  cmp     ebx, 0C8h
0x14000bdcf  jb      short loc_14000BDE1
0x14000bdd1  cmp     ebx, 100h
0x14000bdd7  jl      short loc_14000BE4F
0x14000bdd9  cmp     ebx, 200h
0x14000bddf  jnb     short loc_14000BE4F
0x14000bde1  mov     rcx, rsi; SRWLock
0x14000bde4  call    cs:__imp_AcquireSRWLockExclusive
0x14000bdea  mov     r9, rbp
0x14000bded  mov     [rsp+58h+var_38], rsi
0x14000bdf2  mov     r8d, ebx
0x14000bdf5  mov     edx, r14d
0x14000bdf8  mov     rcx, rsi
0x14000bdfb  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000be00  lea     rcx, [rsp+58h+var_38]
0x14000be05  mov     bl, al
0x14000be07  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000be0c  test    bl, bl
0x14000be0e  jz      short loc_14000BE4F
0x14000be10  jmp     short loc_14000BE1A
0x14000be12  mov     rcx, rsi; this
0x14000be15  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000be1a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000be1f  test    al, al
0x14000be21  jnz     short loc_14000BE4F
0x14000be23  lea     rbx, [rdi+20h]
0x14000be27  mov     rcx, rbx; SRWLock
0x14000be2a  call    cs:__imp_AcquireSRWLockExclusive
0x14000be30  lea     rdx, [rdi+41h]
0x14000be34  mov     [rsp+58h+var_38], rbx
0x14000be39  lea     rcx, [rdi+30h]
0x14000be3d  mov     r8, rdi
0x14000be40  call    ??$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@AEA_NPEAVFeatureStateManager@01@@Z; wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,wil::details::FeatureStateManager *)
0x14000be45  lea     rcx, [rsp+58h+var_38]
0x14000be4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000be4f  add     rsp, 30h
0x14000be53  pop     r14
0x14000be55  pop     rdi
0x14000be56  pop     rsi
0x14000be57  pop     rbp
0x14000be58  pop     rbx
0x14000be59  retn
```
