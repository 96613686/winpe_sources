# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800199f4`
- end: `0x180019a96`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180019a9c`

## callees

- `0x1800174a8`
- `0x1800199f4`
- `0x180019b9c`
- `0x180019bd0`
- `0x180019c08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019a2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019a2d`

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
0x1800199f4  push    rbx
0x1800199f6  push    rbp
0x1800199f7  push    rsi
0x1800199f8  push    rdi
0x1800199f9  sub     rsp, 38h
0x1800199fd  mov     rbp, r9
0x180019a00  mov     ebx, r8d
0x180019a03  mov     esi, edx
0x180019a05  mov     rdi, rcx
0x180019a08  cmp     r8d, 0FEh
0x180019a0f  jz      short loc_180019A86
0x180019a11  cmp     ebx, 0C8h
0x180019a17  jb      short loc_180019A2D
0x180019a19  cmp     ebx, 100h
0x180019a1f  jl      short loc_180019A29
0x180019a21  cmp     ebx, 200h
0x180019a27  jb      short loc_180019A2D
0x180019a29  xor     al, al
0x180019a2b  jmp     short loc_180019A8D
0x180019a2d  call    cs:__imp_AcquireSRWLockExclusive
0x180019a33  mov     [rsp+58h+var_38], rdi
0x180019a38  cmp     ebx, 7
0x180019a3b  ja      short loc_180019A47
0x180019a3d  mov     eax, 0CCh
0x180019a42  bt      eax, ebx
0x180019a45  jb      short loc_180019A67
0x180019a47  lea     eax, [rbx-100h]
0x180019a4d  cmp     eax, 7Fh
0x180019a50  jbe     short loc_180019A67
0x180019a52  mov     r9d, ebp
0x180019a55  lea     rcx, [rdi+48h]
0x180019a59  mov     r8d, esi
0x180019a5c  mov     edx, ebx
0x180019a5e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019a63  mov     bl, al
0x180019a65  jmp     short loc_180019A78
0x180019a67  mov     r8d, esi
0x180019a6a  lea     rcx, [rdi+8]
0x180019a6e  mov     edx, ebx
0x180019a70  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180019a75  mov     bl, [rdi+40h]
0x180019a78  lea     rcx, [rsp+58h+var_38]
0x180019a7d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019a82  mov     al, bl
0x180019a84  jmp     short loc_180019A8D
0x180019a86  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180019a8b  mov     al, 1
0x180019a8d  add     rsp, 38h
0x180019a91  pop     rdi
0x180019a92  pop     rsi
0x180019a93  pop     rbp
0x180019a94  pop     rbx
0x180019a95  retn
```
