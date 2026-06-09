# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000464c`
- end: `0x1400046c0`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x140003808`

## callees

- `0x14000464c`
- `0x1400046c8`
- `0x1400085c4`
- `0x14000c2c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004685`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004685`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4)
{
  char v9; // bl
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)a1);
    v9 = wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(a1, a2, a3, a4, a1);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v10);
    return v9;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14000464c  push    rbx
0x14000464e  push    rbp
0x14000464f  push    rsi
0x140004650  push    rdi
0x140004651  sub     rsp, 38h
0x140004655  mov     rsi, r9
0x140004658  mov     ebx, r8d
0x14000465b  mov     ebp, edx
0x14000465d  mov     rdi, rcx
0x140004660  cmp     r8d, 0FEh
0x140004667  jz      short loc_1400046B0
0x140004669  cmp     ebx, 0C8h
0x14000466f  jb      short loc_140004685
0x140004671  cmp     ebx, 100h
0x140004677  jl      short loc_140004681
0x140004679  cmp     ebx, 200h
0x14000467f  jb      short loc_140004685
0x140004681  xor     al, al
0x140004683  jmp     short loc_1400046B7
0x140004685  call    cs:__imp_AcquireSRWLockExclusive
0x14000468b  mov     r9, rsi
0x14000468e  mov     [rsp+58h+var_38], rdi
0x140004693  mov     r8d, ebx
0x140004696  mov     edx, ebp
0x140004698  mov     rcx, rdi
0x14000469b  call    ?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z; wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400046a0  lea     rcx, [rsp+58h+var_38]
0x1400046a5  mov     bl, al
0x1400046a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400046ac  mov     al, bl
0x1400046ae  jmp     short loc_1400046B7
0x1400046b0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1400046b5  mov     al, 1
0x1400046b7  add     rsp, 38h
0x1400046bb  pop     rdi
0x1400046bc  pop     rsi
0x1400046bd  pop     rbp
0x1400046be  pop     rbx
0x1400046bf  retn
```
