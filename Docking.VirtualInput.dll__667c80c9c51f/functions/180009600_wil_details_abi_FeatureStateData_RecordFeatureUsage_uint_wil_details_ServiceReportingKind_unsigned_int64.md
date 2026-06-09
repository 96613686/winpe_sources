# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180009600`
- end: `0x1800096a2`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800096a8`

## callees

- `0x180007d14`
- `0x180009600`
- `0x180009770`
- `0x1800097a4`
- `0x1800097dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009639`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009639`

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
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v11 = a1;
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
0x180009600  push    rbx
0x180009602  push    rbp
0x180009603  push    rsi
0x180009604  push    rdi
0x180009605  sub     rsp, 38h
0x180009609  mov     rbp, r9
0x18000960c  mov     ebx, r8d
0x18000960f  mov     esi, edx
0x180009611  mov     rdi, rcx
0x180009614  cmp     r8d, 0FEh
0x18000961b  jz      short loc_180009692
0x18000961d  cmp     ebx, 0C8h
0x180009623  jb      short loc_180009639
0x180009625  cmp     ebx, 100h
0x18000962b  jl      short loc_180009635
0x18000962d  cmp     ebx, 200h
0x180009633  jb      short loc_180009639
0x180009635  xor     al, al
0x180009637  jmp     short loc_180009699
0x180009639  call    cs:__imp_AcquireSRWLockExclusive
0x18000963f  mov     [rsp+58h+var_38], rdi
0x180009644  cmp     ebx, 7
0x180009647  ja      short loc_180009653
0x180009649  mov     eax, 0CCh
0x18000964e  bt      eax, ebx
0x180009651  jb      short loc_180009673
0x180009653  lea     eax, [rbx-100h]
0x180009659  cmp     eax, 7Fh
0x18000965c  jbe     short loc_180009673
0x18000965e  mov     r9d, ebp
0x180009661  lea     rcx, [rdi+48h]
0x180009665  mov     r8d, esi
0x180009668  mov     edx, ebx
0x18000966a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000966f  mov     bl, al
0x180009671  jmp     short loc_180009684
0x180009673  mov     r8d, esi
0x180009676  lea     rcx, [rdi+8]
0x18000967a  mov     edx, ebx
0x18000967c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009681  mov     bl, [rdi+40h]
0x180009684  lea     rcx, [rsp+58h+var_38]
0x180009689  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000968e  mov     al, bl
0x180009690  jmp     short loc_180009699
0x180009692  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009697  mov     al, 1
0x180009699  add     rsp, 38h
0x18000969d  pop     rdi
0x18000969e  pop     rsi
0x18000969f  pop     rbp
0x1800096a0  pop     rbx
0x1800096a1  retn
```
