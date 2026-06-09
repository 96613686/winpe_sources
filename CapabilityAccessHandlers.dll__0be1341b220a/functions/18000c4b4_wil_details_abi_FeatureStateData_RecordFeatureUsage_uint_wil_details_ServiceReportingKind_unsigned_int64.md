# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000c4b4`
- end: `0x18000c556`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180003654`

## callees

- `0x180003780`
- `0x18000c4b4`
- `0x18000c55c`
- `0x18000c590`
- `0x18000c5c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c4ed`

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
0x18000c4b4  push    rbx
0x18000c4b6  push    rbp
0x18000c4b7  push    rsi
0x18000c4b8  push    rdi
0x18000c4b9  sub     rsp, 38h
0x18000c4bd  mov     rbp, r9
0x18000c4c0  mov     ebx, r8d
0x18000c4c3  mov     esi, edx
0x18000c4c5  mov     rdi, rcx
0x18000c4c8  cmp     r8d, 0FEh
0x18000c4cf  jz      short loc_18000C546
0x18000c4d1  cmp     ebx, 0C8h
0x18000c4d7  jb      short loc_18000C4ED
0x18000c4d9  cmp     ebx, 100h
0x18000c4df  jl      short loc_18000C4E9
0x18000c4e1  cmp     ebx, 200h
0x18000c4e7  jb      short loc_18000C4ED
0x18000c4e9  xor     al, al
0x18000c4eb  jmp     short loc_18000C54D
0x18000c4ed  call    cs:__imp_AcquireSRWLockExclusive
0x18000c4f3  mov     [rsp+58h+var_38], rdi
0x18000c4f8  cmp     ebx, 7
0x18000c4fb  ja      short loc_18000C507
0x18000c4fd  mov     eax, 0CCh
0x18000c502  bt      eax, ebx
0x18000c505  jb      short loc_18000C527
0x18000c507  lea     eax, [rbx-100h]
0x18000c50d  cmp     eax, 7Fh
0x18000c510  jbe     short loc_18000C527
0x18000c512  mov     r9d, ebp
0x18000c515  lea     rcx, [rdi+48h]
0x18000c519  mov     r8d, esi
0x18000c51c  mov     edx, ebx
0x18000c51e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c523  mov     bl, al
0x18000c525  jmp     short loc_18000C538
0x18000c527  mov     r8d, esi
0x18000c52a  lea     rcx, [rdi+8]
0x18000c52e  mov     edx, ebx
0x18000c530  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c535  mov     bl, [rdi+40h]
0x18000c538  lea     rcx, [rsp+58h+var_38]
0x18000c53d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c542  mov     al, bl
0x18000c544  jmp     short loc_18000C54D
0x18000c546  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c54b  mov     al, 1
0x18000c54d  add     rsp, 38h
0x18000c551  pop     rdi
0x18000c552  pop     rsi
0x18000c553  pop     rbp
0x18000c554  pop     rbx
0x18000c555  retn
```
