# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000dbb4`
- end: `0x18000dc56`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000dc5c`

## callees

- `0x180008720`
- `0x18000dbb4`
- `0x18000dd5c`
- `0x18000dd90`
- `0x18000ddc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dbed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dbed`

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
0x18000dbb4  push    rbx
0x18000dbb6  push    rbp
0x18000dbb7  push    rsi
0x18000dbb8  push    rdi
0x18000dbb9  sub     rsp, 38h
0x18000dbbd  mov     rbp, r9
0x18000dbc0  mov     ebx, r8d
0x18000dbc3  mov     esi, edx
0x18000dbc5  mov     rdi, rcx
0x18000dbc8  cmp     r8d, 0FEh
0x18000dbcf  jz      short loc_18000DC46
0x18000dbd1  cmp     ebx, 0C8h
0x18000dbd7  jb      short loc_18000DBED
0x18000dbd9  cmp     ebx, 100h
0x18000dbdf  jl      short loc_18000DBE9
0x18000dbe1  cmp     ebx, 200h
0x18000dbe7  jb      short loc_18000DBED
0x18000dbe9  xor     al, al
0x18000dbeb  jmp     short loc_18000DC4D
0x18000dbed  call    cs:__imp_AcquireSRWLockExclusive
0x18000dbf3  mov     [rsp+58h+var_38], rdi
0x18000dbf8  cmp     ebx, 7
0x18000dbfb  ja      short loc_18000DC07
0x18000dbfd  mov     eax, 0CCh
0x18000dc02  bt      eax, ebx
0x18000dc05  jb      short loc_18000DC27
0x18000dc07  lea     eax, [rbx-100h]
0x18000dc0d  cmp     eax, 7Fh
0x18000dc10  jbe     short loc_18000DC27
0x18000dc12  mov     r9d, ebp
0x18000dc15  lea     rcx, [rdi+48h]
0x18000dc19  mov     r8d, esi
0x18000dc1c  mov     edx, ebx
0x18000dc1e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000dc23  mov     bl, al
0x18000dc25  jmp     short loc_18000DC38
0x18000dc27  mov     r8d, esi
0x18000dc2a  lea     rcx, [rdi+8]
0x18000dc2e  mov     edx, ebx
0x18000dc30  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000dc35  mov     bl, [rdi+40h]
0x18000dc38  lea     rcx, [rsp+58h+var_38]
0x18000dc3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000dc42  mov     al, bl
0x18000dc44  jmp     short loc_18000DC4D
0x18000dc46  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000dc4b  mov     al, 1
0x18000dc4d  add     rsp, 38h
0x18000dc51  pop     rdi
0x18000dc52  pop     rsi
0x18000dc53  pop     rbp
0x18000dc54  pop     rbx
0x18000dc55  retn
```
