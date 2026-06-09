# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800074b4`
- end: `0x180007556`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000755c`

## callees

- `0x18000490c`
- `0x1800074b4`
- `0x180007670`
- `0x1800076a4`
- `0x1800076dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800074ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800074ed`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  RTL_SRWLOCK *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = (RTL_SRWLOCK *)a1;
    if ( a3 <= 7 && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        (char *)a1 + 8,
        a3,
        a2);
      v10 = *((_BYTE *)a1 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              (char *)a1 + 72,
              a3,
              a2,
              a4,
              v11);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    return v10;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800074b4  push    rbx
0x1800074b6  push    rbp
0x1800074b7  push    rsi
0x1800074b8  push    rdi
0x1800074b9  sub     rsp, 38h
0x1800074bd  mov     rbp, r9
0x1800074c0  mov     ebx, r8d
0x1800074c3  mov     esi, edx
0x1800074c5  mov     rdi, rcx
0x1800074c8  cmp     r8d, 0FEh
0x1800074cf  jz      short loc_180007546
0x1800074d1  cmp     ebx, 0C8h
0x1800074d7  jb      short loc_1800074ED
0x1800074d9  cmp     ebx, 100h
0x1800074df  jl      short loc_1800074E9
0x1800074e1  cmp     ebx, 200h
0x1800074e7  jb      short loc_1800074ED
0x1800074e9  xor     al, al
0x1800074eb  jmp     short loc_18000754D
0x1800074ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800074f3  mov     [rsp+58h+var_38], rdi
0x1800074f8  cmp     ebx, 7
0x1800074fb  ja      short loc_180007507
0x1800074fd  mov     eax, 0CCh
0x180007502  bt      eax, ebx
0x180007505  jb      short loc_180007527
0x180007507  lea     eax, [rbx-100h]
0x18000750d  cmp     eax, 7Fh
0x180007510  jbe     short loc_180007527
0x180007512  mov     r9d, ebp
0x180007515  lea     rcx, [rdi+48h]
0x180007519  mov     r8d, esi
0x18000751c  mov     edx, ebx
0x18000751e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007523  mov     bl, al
0x180007525  jmp     short loc_180007538
0x180007527  mov     r8d, esi
0x18000752a  lea     rcx, [rdi+8]
0x18000752e  mov     edx, ebx
0x180007530  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007535  mov     bl, [rdi+40h]
0x180007538  lea     rcx, [rsp+58h+var_38]
0x18000753d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007542  mov     al, bl
0x180007544  jmp     short loc_18000754D
0x180007546  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000754b  mov     al, 1
0x18000754d  add     rsp, 38h
0x180007551  pop     rdi
0x180007552  pop     rsi
0x180007553  pop     rbp
0x180007554  pop     rbx
0x180007555  retn
```
