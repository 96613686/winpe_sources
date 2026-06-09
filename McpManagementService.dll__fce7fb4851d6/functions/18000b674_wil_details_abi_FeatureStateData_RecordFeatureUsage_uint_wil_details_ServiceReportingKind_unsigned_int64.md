# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b674`
- end: `0x18000b716`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000b71c`

## callees

- `0x1800074a8`
- `0x18000b674`
- `0x18000b7e0`
- `0x18000b814`
- `0x18000b84c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6ad`

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
0x18000b674  push    rbx
0x18000b676  push    rbp
0x18000b677  push    rsi
0x18000b678  push    rdi
0x18000b679  sub     rsp, 38h
0x18000b67d  mov     rbp, r9
0x18000b680  mov     ebx, r8d
0x18000b683  mov     esi, edx
0x18000b685  mov     rdi, rcx
0x18000b688  cmp     r8d, 0FEh
0x18000b68f  jz      short loc_18000B706
0x18000b691  cmp     ebx, 0C8h
0x18000b697  jb      short loc_18000B6AD
0x18000b699  cmp     ebx, 100h
0x18000b69f  jl      short loc_18000B6A9
0x18000b6a1  cmp     ebx, 200h
0x18000b6a7  jb      short loc_18000B6AD
0x18000b6a9  xor     al, al
0x18000b6ab  jmp     short loc_18000B70D
0x18000b6ad  call    cs:__imp_AcquireSRWLockExclusive
0x18000b6b3  mov     [rsp+58h+var_38], rdi
0x18000b6b8  cmp     ebx, 7
0x18000b6bb  ja      short loc_18000B6C7
0x18000b6bd  mov     eax, 0CCh
0x18000b6c2  bt      eax, ebx
0x18000b6c5  jb      short loc_18000B6E7
0x18000b6c7  lea     eax, [rbx-100h]
0x18000b6cd  cmp     eax, 7Fh
0x18000b6d0  jbe     short loc_18000B6E7
0x18000b6d2  mov     r9d, ebp
0x18000b6d5  lea     rcx, [rdi+48h]
0x18000b6d9  mov     r8d, esi
0x18000b6dc  mov     edx, ebx
0x18000b6de  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b6e3  mov     bl, al
0x18000b6e5  jmp     short loc_18000B6F8
0x18000b6e7  mov     r8d, esi
0x18000b6ea  lea     rcx, [rdi+8]
0x18000b6ee  mov     edx, ebx
0x18000b6f0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b6f5  mov     bl, [rdi+40h]
0x18000b6f8  lea     rcx, [rsp+58h+var_38]
0x18000b6fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b702  mov     al, bl
0x18000b704  jmp     short loc_18000B70D
0x18000b706  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b70b  mov     al, 1
0x18000b70d  add     rsp, 38h
0x18000b711  pop     rdi
0x18000b712  pop     rsi
0x18000b713  pop     rbp
0x18000b714  pop     rbx
0x18000b715  retn
```
