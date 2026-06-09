# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006804`
- end: `0x1800068a6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800068ac`

## callees

- `0x180003698`
- `0x180006804`
- `0x1800069ac`
- `0x1800069e0`
- `0x180006a18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000683d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000683d`

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
0x180006804  push    rbx
0x180006806  push    rbp
0x180006807  push    rsi
0x180006808  push    rdi
0x180006809  sub     rsp, 38h
0x18000680d  mov     rbp, r9
0x180006810  mov     ebx, r8d
0x180006813  mov     esi, edx
0x180006815  mov     rdi, rcx
0x180006818  cmp     r8d, 0FEh
0x18000681f  jz      short loc_180006896
0x180006821  cmp     ebx, 0C8h
0x180006827  jb      short loc_18000683D
0x180006829  cmp     ebx, 100h
0x18000682f  jl      short loc_180006839
0x180006831  cmp     ebx, 200h
0x180006837  jb      short loc_18000683D
0x180006839  xor     al, al
0x18000683b  jmp     short loc_18000689D
0x18000683d  call    cs:__imp_AcquireSRWLockExclusive
0x180006843  mov     [rsp+58h+var_38], rdi
0x180006848  cmp     ebx, 7
0x18000684b  ja      short loc_180006857
0x18000684d  mov     eax, 0CCh
0x180006852  bt      eax, ebx
0x180006855  jb      short loc_180006877
0x180006857  lea     eax, [rbx-100h]
0x18000685d  cmp     eax, 7Fh
0x180006860  jbe     short loc_180006877
0x180006862  mov     r9d, ebp
0x180006865  lea     rcx, [rdi+48h]
0x180006869  mov     r8d, esi
0x18000686c  mov     edx, ebx
0x18000686e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006873  mov     bl, al
0x180006875  jmp     short loc_180006888
0x180006877  mov     r8d, esi
0x18000687a  lea     rcx, [rdi+8]
0x18000687e  mov     edx, ebx
0x180006880  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006885  mov     bl, [rdi+40h]
0x180006888  lea     rcx, [rsp+58h+var_38]
0x18000688d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006892  mov     al, bl
0x180006894  jmp     short loc_18000689D
0x180006896  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000689b  mov     al, 1
0x18000689d  add     rsp, 38h
0x1800068a1  pop     rdi
0x1800068a2  pop     rsi
0x1800068a3  pop     rbp
0x1800068a4  pop     rbx
0x1800068a5  retn
```
