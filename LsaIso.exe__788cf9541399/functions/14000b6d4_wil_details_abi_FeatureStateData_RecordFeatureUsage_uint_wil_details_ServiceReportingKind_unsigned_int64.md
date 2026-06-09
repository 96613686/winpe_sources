# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000b6d4`
- end: `0x14000b776`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140002b9c`

## callees

- `0x140002cec`
- `0x14000b6d4`
- `0x14000b7b4`
- `0x14000b7e8`
- `0x14000b820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b70d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b70d`

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
0x14000b6d4  push    rbx
0x14000b6d6  push    rbp
0x14000b6d7  push    rsi
0x14000b6d8  push    rdi
0x14000b6d9  sub     rsp, 38h
0x14000b6dd  mov     rbp, r9
0x14000b6e0  mov     ebx, r8d
0x14000b6e3  mov     esi, edx
0x14000b6e5  mov     rdi, rcx
0x14000b6e8  cmp     r8d, 0FEh
0x14000b6ef  jz      short loc_14000B766
0x14000b6f1  cmp     ebx, 0C8h
0x14000b6f7  jb      short loc_14000B70D
0x14000b6f9  cmp     ebx, 100h
0x14000b6ff  jl      short loc_14000B709
0x14000b701  cmp     ebx, 200h
0x14000b707  jb      short loc_14000B70D
0x14000b709  xor     al, al
0x14000b70b  jmp     short loc_14000B76D
0x14000b70d  call    cs:__imp_AcquireSRWLockExclusive
0x14000b713  mov     [rsp+58h+var_38], rdi
0x14000b718  cmp     ebx, 7
0x14000b71b  ja      short loc_14000B727
0x14000b71d  mov     eax, 0CCh
0x14000b722  bt      eax, ebx
0x14000b725  jb      short loc_14000B747
0x14000b727  lea     eax, [rbx-100h]
0x14000b72d  cmp     eax, 7Fh
0x14000b730  jbe     short loc_14000B747
0x14000b732  mov     r9d, ebp
0x14000b735  lea     rcx, [rdi+48h]
0x14000b739  mov     r8d, esi
0x14000b73c  mov     edx, ebx
0x14000b73e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b743  mov     bl, al
0x14000b745  jmp     short loc_14000B758
0x14000b747  mov     r8d, esi
0x14000b74a  lea     rcx, [rdi+8]
0x14000b74e  mov     edx, ebx
0x14000b750  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000b755  mov     bl, [rdi+40h]
0x14000b758  lea     rcx, [rsp+58h+var_38]
0x14000b75d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b762  mov     al, bl
0x14000b764  jmp     short loc_14000B76D
0x14000b766  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000b76b  mov     al, 1
0x14000b76d  add     rsp, 38h
0x14000b771  pop     rdi
0x14000b772  pop     rsi
0x14000b773  pop     rbp
0x14000b774  pop     rbx
0x14000b775  retn
```
