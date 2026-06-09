# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180012b24`
- end: `0x180012bc6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000da14`

## callees

- `0x18000db40`
- `0x180012b24`
- `0x180012c20`
- `0x180012c54`
- `0x180012c8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012b5d`

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
0x180012b24  push    rbx
0x180012b26  push    rbp
0x180012b27  push    rsi
0x180012b28  push    rdi
0x180012b29  sub     rsp, 38h
0x180012b2d  mov     rbp, r9
0x180012b30  mov     ebx, r8d
0x180012b33  mov     esi, edx
0x180012b35  mov     rdi, rcx
0x180012b38  cmp     r8d, 0FEh
0x180012b3f  jz      short loc_180012BB6
0x180012b41  cmp     ebx, 0C8h
0x180012b47  jb      short loc_180012B5D
0x180012b49  cmp     ebx, 100h
0x180012b4f  jl      short loc_180012B59
0x180012b51  cmp     ebx, 200h
0x180012b57  jb      short loc_180012B5D
0x180012b59  xor     al, al
0x180012b5b  jmp     short loc_180012BBD
0x180012b5d  call    cs:__imp_AcquireSRWLockExclusive
0x180012b63  mov     [rsp+58h+var_38], rdi
0x180012b68  cmp     ebx, 7
0x180012b6b  ja      short loc_180012B77
0x180012b6d  mov     eax, 0CCh
0x180012b72  bt      eax, ebx
0x180012b75  jb      short loc_180012B97
0x180012b77  lea     eax, [rbx-100h]
0x180012b7d  cmp     eax, 7Fh
0x180012b80  jbe     short loc_180012B97
0x180012b82  mov     r9d, ebp
0x180012b85  lea     rcx, [rdi+48h]
0x180012b89  mov     r8d, esi
0x180012b8c  mov     edx, ebx
0x180012b8e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012b93  mov     bl, al
0x180012b95  jmp     short loc_180012BA8
0x180012b97  mov     r8d, esi
0x180012b9a  lea     rcx, [rdi+8]
0x180012b9e  mov     edx, ebx
0x180012ba0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012ba5  mov     bl, [rdi+40h]
0x180012ba8  lea     rcx, [rsp+58h+var_38]
0x180012bad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012bb2  mov     al, bl
0x180012bb4  jmp     short loc_180012BBD
0x180012bb6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012bbb  mov     al, 1
0x180012bbd  add     rsp, 38h
0x180012bc1  pop     rdi
0x180012bc2  pop     rsi
0x180012bc3  pop     rbp
0x180012bc4  pop     rbx
0x180012bc5  retn
```
