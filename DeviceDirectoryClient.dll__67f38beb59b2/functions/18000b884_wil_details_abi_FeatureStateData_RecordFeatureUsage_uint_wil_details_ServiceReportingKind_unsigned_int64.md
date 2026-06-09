# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b884`
- end: `0x18000b926`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000b92c`

## callees

- `0x1800089a4`
- `0x18000b884`
- `0x18000ba40`
- `0x18000ba74`
- `0x18000baac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8bd`

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
0x18000b884  push    rbx
0x18000b886  push    rbp
0x18000b887  push    rsi
0x18000b888  push    rdi
0x18000b889  sub     rsp, 38h
0x18000b88d  mov     rbp, r9
0x18000b890  mov     ebx, r8d
0x18000b893  mov     esi, edx
0x18000b895  mov     rdi, rcx
0x18000b898  cmp     r8d, 0FEh
0x18000b89f  jz      short loc_18000B916
0x18000b8a1  cmp     ebx, 0C8h
0x18000b8a7  jb      short loc_18000B8BD
0x18000b8a9  cmp     ebx, 100h
0x18000b8af  jl      short loc_18000B8B9
0x18000b8b1  cmp     ebx, 200h
0x18000b8b7  jb      short loc_18000B8BD
0x18000b8b9  xor     al, al
0x18000b8bb  jmp     short loc_18000B91D
0x18000b8bd  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8c3  mov     [rsp+58h+var_38], rdi
0x18000b8c8  cmp     ebx, 7
0x18000b8cb  ja      short loc_18000B8D7
0x18000b8cd  mov     eax, 0CCh
0x18000b8d2  bt      eax, ebx
0x18000b8d5  jb      short loc_18000B8F7
0x18000b8d7  lea     eax, [rbx-100h]
0x18000b8dd  cmp     eax, 7Fh
0x18000b8e0  jbe     short loc_18000B8F7
0x18000b8e2  mov     r9d, ebp
0x18000b8e5  lea     rcx, [rdi+48h]
0x18000b8e9  mov     r8d, esi
0x18000b8ec  mov     edx, ebx
0x18000b8ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b8f3  mov     bl, al
0x18000b8f5  jmp     short loc_18000B908
0x18000b8f7  mov     r8d, esi
0x18000b8fa  lea     rcx, [rdi+8]
0x18000b8fe  mov     edx, ebx
0x18000b900  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b905  mov     bl, [rdi+40h]
0x18000b908  lea     rcx, [rsp+58h+var_38]
0x18000b90d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b912  mov     al, bl
0x18000b914  jmp     short loc_18000B91D
0x18000b916  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b91b  mov     al, 1
0x18000b91d  add     rsp, 38h
0x18000b921  pop     rdi
0x18000b922  pop     rsi
0x18000b923  pop     rbp
0x18000b924  pop     rbx
0x18000b925  retn
```
