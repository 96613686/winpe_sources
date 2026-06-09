# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140005684`
- end: `0x140005726`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14000572c`

## callees

- `0x140002fd4`
- `0x140005684`
- `0x14000582c`
- `0x140005860`
- `0x140005898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400056bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400056bd`

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
0x140005684  push    rbx
0x140005686  push    rbp
0x140005687  push    rsi
0x140005688  push    rdi
0x140005689  sub     rsp, 38h
0x14000568d  mov     rbp, r9
0x140005690  mov     ebx, r8d
0x140005693  mov     esi, edx
0x140005695  mov     rdi, rcx
0x140005698  cmp     r8d, 0FEh
0x14000569f  jz      short loc_140005716
0x1400056a1  cmp     ebx, 0C8h
0x1400056a7  jb      short loc_1400056BD
0x1400056a9  cmp     ebx, 100h
0x1400056af  jl      short loc_1400056B9
0x1400056b1  cmp     ebx, 200h
0x1400056b7  jb      short loc_1400056BD
0x1400056b9  xor     al, al
0x1400056bb  jmp     short loc_14000571D
0x1400056bd  call    cs:__imp_AcquireSRWLockExclusive
0x1400056c3  mov     [rsp+58h+var_38], rdi
0x1400056c8  cmp     ebx, 7
0x1400056cb  ja      short loc_1400056D7
0x1400056cd  mov     eax, 0CCh
0x1400056d2  bt      eax, ebx
0x1400056d5  jb      short loc_1400056F7
0x1400056d7  lea     eax, [rbx-100h]
0x1400056dd  cmp     eax, 7Fh
0x1400056e0  jbe     short loc_1400056F7
0x1400056e2  mov     r9d, ebp
0x1400056e5  lea     rcx, [rdi+48h]
0x1400056e9  mov     r8d, esi
0x1400056ec  mov     edx, ebx
0x1400056ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400056f3  mov     bl, al
0x1400056f5  jmp     short loc_140005708
0x1400056f7  mov     r8d, esi
0x1400056fa  lea     rcx, [rdi+8]
0x1400056fe  mov     edx, ebx
0x140005700  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140005705  mov     bl, [rdi+40h]
0x140005708  lea     rcx, [rsp+58h+var_38]
0x14000570d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005712  mov     al, bl
0x140005714  jmp     short loc_14000571D
0x140005716  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000571b  mov     al, 1
0x14000571d  add     rsp, 38h
0x140005721  pop     rdi
0x140005722  pop     rsi
0x140005723  pop     rbp
0x140005724  pop     rbx
0x140005725  retn
```
