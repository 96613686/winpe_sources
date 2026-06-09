# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180015224`
- end: `0x1800152c6`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800152cc`

## callees

- `0x18000bc80`
- `0x180015224`
- `0x1800154d0`
- `0x180015504`
- `0x18001553c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001525d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001525d`

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
0x180015224  push    rbx
0x180015226  push    rbp
0x180015227  push    rsi
0x180015228  push    rdi
0x180015229  sub     rsp, 38h
0x18001522d  mov     rbp, r9
0x180015230  mov     ebx, r8d
0x180015233  mov     esi, edx
0x180015235  mov     rdi, rcx
0x180015238  cmp     r8d, 0FEh
0x18001523f  jz      short loc_1800152B6
0x180015241  cmp     ebx, 0C8h
0x180015247  jb      short loc_18001525D
0x180015249  cmp     ebx, 100h
0x18001524f  jl      short loc_180015259
0x180015251  cmp     ebx, 200h
0x180015257  jb      short loc_18001525D
0x180015259  xor     al, al
0x18001525b  jmp     short loc_1800152BD
0x18001525d  call    cs:__imp_AcquireSRWLockExclusive
0x180015263  mov     [rsp+58h+var_38], rdi
0x180015268  cmp     ebx, 7
0x18001526b  ja      short loc_180015277
0x18001526d  mov     eax, 0CCh
0x180015272  bt      eax, ebx
0x180015275  jb      short loc_180015297
0x180015277  lea     eax, [rbx-100h]
0x18001527d  cmp     eax, 7Fh
0x180015280  jbe     short loc_180015297
0x180015282  mov     r9d, ebp
0x180015285  lea     rcx, [rdi+48h]
0x180015289  mov     r8d, esi
0x18001528c  mov     edx, ebx
0x18001528e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180015293  mov     bl, al
0x180015295  jmp     short loc_1800152A8
0x180015297  mov     r8d, esi
0x18001529a  lea     rcx, [rdi+8]
0x18001529e  mov     edx, ebx
0x1800152a0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800152a5  mov     bl, [rdi+40h]
0x1800152a8  lea     rcx, [rsp+58h+var_38]
0x1800152ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800152b2  mov     al, bl
0x1800152b4  jmp     short loc_1800152BD
0x1800152b6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800152bb  mov     al, 1
0x1800152bd  add     rsp, 38h
0x1800152c1  pop     rdi
0x1800152c2  pop     rsi
0x1800152c3  pop     rbp
0x1800152c4  pop     rbx
0x1800152c5  retn
```
