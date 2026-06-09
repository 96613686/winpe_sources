# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008564`
- end: `0x180008606`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000860c`

## callees

- `0x18000460c`
- `0x180008564`
- `0x180008720`
- `0x180008754`
- `0x18000878c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000859d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000859d`

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
0x180008564  push    rbx
0x180008566  push    rbp
0x180008567  push    rsi
0x180008568  push    rdi
0x180008569  sub     rsp, 38h
0x18000856d  mov     rbp, r9
0x180008570  mov     ebx, r8d
0x180008573  mov     esi, edx
0x180008575  mov     rdi, rcx
0x180008578  cmp     r8d, 0FEh
0x18000857f  jz      short loc_1800085F6
0x180008581  cmp     ebx, 0C8h
0x180008587  jb      short loc_18000859D
0x180008589  cmp     ebx, 100h
0x18000858f  jl      short loc_180008599
0x180008591  cmp     ebx, 200h
0x180008597  jb      short loc_18000859D
0x180008599  xor     al, al
0x18000859b  jmp     short loc_1800085FD
0x18000859d  call    cs:__imp_AcquireSRWLockExclusive
0x1800085a3  mov     [rsp+58h+var_38], rdi
0x1800085a8  cmp     ebx, 7
0x1800085ab  ja      short loc_1800085B7
0x1800085ad  mov     eax, 0CCh
0x1800085b2  bt      eax, ebx
0x1800085b5  jb      short loc_1800085D7
0x1800085b7  lea     eax, [rbx-100h]
0x1800085bd  cmp     eax, 7Fh
0x1800085c0  jbe     short loc_1800085D7
0x1800085c2  mov     r9d, ebp
0x1800085c5  lea     rcx, [rdi+48h]
0x1800085c9  mov     r8d, esi
0x1800085cc  mov     edx, ebx
0x1800085ce  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800085d3  mov     bl, al
0x1800085d5  jmp     short loc_1800085E8
0x1800085d7  mov     r8d, esi
0x1800085da  lea     rcx, [rdi+8]
0x1800085de  mov     edx, ebx
0x1800085e0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800085e5  mov     bl, [rdi+40h]
0x1800085e8  lea     rcx, [rsp+58h+var_38]
0x1800085ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800085f2  mov     al, bl
0x1800085f4  jmp     short loc_1800085FD
0x1800085f6  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800085fb  mov     al, 1
0x1800085fd  add     rsp, 38h
0x180008601  pop     rdi
0x180008602  pop     rsi
0x180008603  pop     rbp
0x180008604  pop     rbx
0x180008605  retn
```
