# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000bfb8`
- end: `0x18000c05a`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000c060`

## callees

- `0x18000a398`
- `0x18000bfb8`
- `0x18000c128`
- `0x18000c15c`
- `0x18000c194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bff1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bff1`

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
0x18000bfb8  push    rbx
0x18000bfba  push    rbp
0x18000bfbb  push    rsi
0x18000bfbc  push    rdi
0x18000bfbd  sub     rsp, 38h
0x18000bfc1  mov     rbp, r9
0x18000bfc4  mov     ebx, r8d
0x18000bfc7  mov     esi, edx
0x18000bfc9  mov     rdi, rcx
0x18000bfcc  cmp     r8d, 0FEh
0x18000bfd3  jz      short loc_18000C04A
0x18000bfd5  cmp     ebx, 0C8h
0x18000bfdb  jb      short loc_18000BFF1
0x18000bfdd  cmp     ebx, 100h
0x18000bfe3  jl      short loc_18000BFED
0x18000bfe5  cmp     ebx, 200h
0x18000bfeb  jb      short loc_18000BFF1
0x18000bfed  xor     al, al
0x18000bfef  jmp     short loc_18000C051
0x18000bff1  call    cs:__imp_AcquireSRWLockExclusive
0x18000bff7  mov     [rsp+58h+var_38], rdi
0x18000bffc  cmp     ebx, 7
0x18000bfff  ja      short loc_18000C00B
0x18000c001  mov     eax, 0CCh
0x18000c006  bt      eax, ebx
0x18000c009  jb      short loc_18000C02B
0x18000c00b  lea     eax, [rbx-100h]
0x18000c011  cmp     eax, 7Fh
0x18000c014  jbe     short loc_18000C02B
0x18000c016  mov     r9d, ebp
0x18000c019  lea     rcx, [rdi+48h]
0x18000c01d  mov     r8d, esi
0x18000c020  mov     edx, ebx
0x18000c022  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c027  mov     bl, al
0x18000c029  jmp     short loc_18000C03C
0x18000c02b  mov     r8d, esi
0x18000c02e  lea     rcx, [rdi+8]
0x18000c032  mov     edx, ebx
0x18000c034  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c039  mov     bl, [rdi+40h]
0x18000c03c  lea     rcx, [rsp+58h+var_38]
0x18000c041  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c046  mov     al, bl
0x18000c048  jmp     short loc_18000C051
0x18000c04a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c04f  mov     al, 1
0x18000c051  add     rsp, 38h
0x18000c055  pop     rdi
0x18000c056  pop     rsi
0x18000c057  pop     rbp
0x18000c058  pop     rbx
0x18000c059  retn
```
