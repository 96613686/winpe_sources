# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001468c`
- end: `0x180014735`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001473c`

## callees

- `0x180011904`
- `0x18001468c`
- `0x180014820`
- `0x180014874`
- `0x1800148cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800146c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800146c8`

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
  wil::details_abi::FeatureStateData *v11; // [rsp+20h] [rbp-28h] BYREF

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
0x18001468c  mov     [rsp+arg_18], rbx
0x180014691  push    rbp
0x180014692  push    rsi
0x180014693  push    rdi
0x180014694  sub     rsp, 30h
0x180014698  mov     rbp, r9
0x18001469b  mov     ebx, r8d
0x18001469e  mov     esi, edx
0x1800146a0  mov     rdi, rcx
0x1800146a3  cmp     r8d, 0FEh
0x1800146aa  jz      short loc_180014721
0x1800146ac  cmp     ebx, 0C8h
0x1800146b2  jb      short loc_1800146C8
0x1800146b4  cmp     ebx, 100h
0x1800146ba  jl      short loc_1800146C4
0x1800146bc  cmp     ebx, 200h
0x1800146c2  jb      short loc_1800146C8
0x1800146c4  xor     al, al
0x1800146c6  jmp     short loc_180014728
0x1800146c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800146ce  mov     [rsp+48h+var_28], rdi
0x1800146d3  cmp     ebx, 7
0x1800146d6  ja      short loc_1800146E2
0x1800146d8  mov     eax, 0CCh
0x1800146dd  bt      eax, ebx
0x1800146e0  jb      short loc_180014702
0x1800146e2  lea     eax, [rbx-100h]
0x1800146e8  cmp     eax, 7Fh
0x1800146eb  jbe     short loc_180014702
0x1800146ed  mov     r9d, ebp
0x1800146f0  lea     rcx, [rdi+48h]
0x1800146f4  mov     r8d, esi
0x1800146f7  mov     edx, ebx
0x1800146f9  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800146fe  mov     bl, al
0x180014700  jmp     short loc_180014713
0x180014702  mov     r8d, esi
0x180014705  lea     rcx, [rdi+8]
0x180014709  mov     edx, ebx
0x18001470b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180014710  mov     bl, [rdi+40h]
0x180014713  lea     rcx, [rsp+48h+var_28]
0x180014718  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001471d  mov     al, bl
0x18001471f  jmp     short loc_180014728
0x180014721  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014726  mov     al, 1
0x180014728  mov     rbx, [rsp+48h+arg_18]
0x18001472d  add     rsp, 30h
0x180014731  pop     rdi
0x180014732  pop     rsi
0x180014733  pop     rbp
0x180014734  retn
```
