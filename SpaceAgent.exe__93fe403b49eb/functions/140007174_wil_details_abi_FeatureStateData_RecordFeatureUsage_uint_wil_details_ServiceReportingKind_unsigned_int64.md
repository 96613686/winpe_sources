# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007174`
- end: `0x140007216`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x14000721c`

## callees

- `0x140004604`
- `0x140007174`
- `0x140007330`
- `0x140007364`
- `0x14000739c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400071ad`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400071ad`

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
0x140007174  push    rbx
0x140007176  push    rbp
0x140007177  push    rsi
0x140007178  push    rdi
0x140007179  sub     rsp, 38h
0x14000717d  mov     rbp, r9
0x140007180  mov     ebx, r8d
0x140007183  mov     esi, edx
0x140007185  mov     rdi, rcx
0x140007188  cmp     r8d, 0FEh
0x14000718f  jz      short loc_140007206
0x140007191  cmp     ebx, 0C8h
0x140007197  jb      short loc_1400071AD
0x140007199  cmp     ebx, 100h
0x14000719f  jl      short loc_1400071A9
0x1400071a1  cmp     ebx, 200h
0x1400071a7  jb      short loc_1400071AD
0x1400071a9  xor     al, al
0x1400071ab  jmp     short loc_14000720D
0x1400071ad  call    cs:__imp_AcquireSRWLockExclusive
0x1400071b3  mov     [rsp+58h+var_38], rdi
0x1400071b8  cmp     ebx, 7
0x1400071bb  ja      short loc_1400071C7
0x1400071bd  mov     eax, 0CCh
0x1400071c2  bt      eax, ebx
0x1400071c5  jb      short loc_1400071E7
0x1400071c7  lea     eax, [rbx-100h]
0x1400071cd  cmp     eax, 7Fh
0x1400071d0  jbe     short loc_1400071E7
0x1400071d2  mov     r9d, ebp
0x1400071d5  lea     rcx, [rdi+48h]
0x1400071d9  mov     r8d, esi
0x1400071dc  mov     edx, ebx
0x1400071de  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400071e3  mov     bl, al
0x1400071e5  jmp     short loc_1400071F8
0x1400071e7  mov     r8d, esi
0x1400071ea  lea     rcx, [rdi+8]
0x1400071ee  mov     edx, ebx
0x1400071f0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400071f5  mov     bl, [rdi+40h]
0x1400071f8  lea     rcx, [rsp+58h+var_38]
0x1400071fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140007202  mov     al, bl
0x140007204  jmp     short loc_14000720D
0x140007206  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000720b  mov     al, 1
0x14000720d  add     rsp, 38h
0x140007211  pop     rdi
0x140007212  pop     rsi
0x140007213  pop     rbp
0x140007214  pop     rbx
0x140007215  retn
```
