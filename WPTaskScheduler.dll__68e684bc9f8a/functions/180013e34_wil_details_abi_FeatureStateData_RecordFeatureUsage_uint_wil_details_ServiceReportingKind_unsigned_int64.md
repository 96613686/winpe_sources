# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180013e34`
- end: `0x180013ed6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180013edc`

## callees

- `0x1800117f4`
- `0x180013e34`
- `0x180013fdc`
- `0x180014010`
- `0x180014048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e6d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e6d`

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
0x180013e34  push    rbx
0x180013e36  push    rbp
0x180013e37  push    rsi
0x180013e38  push    rdi
0x180013e39  sub     rsp, 38h
0x180013e3d  mov     rbp, r9
0x180013e40  mov     ebx, r8d
0x180013e43  mov     esi, edx
0x180013e45  mov     rdi, rcx
0x180013e48  cmp     r8d, 0FEh
0x180013e4f  jz      short loc_180013EC6
0x180013e51  cmp     ebx, 0C8h
0x180013e57  jb      short loc_180013E6D
0x180013e59  cmp     ebx, 100h
0x180013e5f  jl      short loc_180013E69
0x180013e61  cmp     ebx, 200h
0x180013e67  jb      short loc_180013E6D
0x180013e69  xor     al, al
0x180013e6b  jmp     short loc_180013ECD
0x180013e6d  call    cs:__imp_AcquireSRWLockExclusive
0x180013e73  mov     [rsp+58h+var_38], rdi
0x180013e78  cmp     ebx, 7
0x180013e7b  ja      short loc_180013E87
0x180013e7d  mov     eax, 0CCh
0x180013e82  bt      eax, ebx
0x180013e85  jb      short loc_180013EA7
0x180013e87  lea     eax, [rbx-100h]
0x180013e8d  cmp     eax, 7Fh
0x180013e90  jbe     short loc_180013EA7
0x180013e92  mov     r9d, ebp
0x180013e95  lea     rcx, [rdi+48h]
0x180013e99  mov     r8d, esi
0x180013e9c  mov     edx, ebx
0x180013e9e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180013ea3  mov     bl, al
0x180013ea5  jmp     short loc_180013EB8
0x180013ea7  mov     r8d, esi
0x180013eaa  lea     rcx, [rdi+8]
0x180013eae  mov     edx, ebx
0x180013eb0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180013eb5  mov     bl, [rdi+40h]
0x180013eb8  lea     rcx, [rsp+58h+var_38]
0x180013ebd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013ec2  mov     al, bl
0x180013ec4  jmp     short loc_180013ECD
0x180013ec6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180013ecb  mov     al, 1
0x180013ecd  add     rsp, 38h
0x180013ed1  pop     rdi
0x180013ed2  pop     rsi
0x180013ed3  pop     rbp
0x180013ed4  pop     rbx
0x180013ed5  retn
```
