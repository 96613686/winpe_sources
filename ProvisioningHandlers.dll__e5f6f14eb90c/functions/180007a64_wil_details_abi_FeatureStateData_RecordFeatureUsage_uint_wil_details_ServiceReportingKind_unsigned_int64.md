# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180007a64`
- end: `0x180007b0d`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180007b14`

## callees

- `0x18000468c`
- `0x180007a64`
- `0x180007c40`
- `0x180007c78`
- `0x180007cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007a9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007a9d`

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
0x180007a64  push    rbx
0x180007a66  push    rbp
0x180007a67  push    rsi
0x180007a68  push    rdi
0x180007a69  sub     rsp, 38h
0x180007a6d  mov     rbp, r9
0x180007a70  mov     ebx, r8d
0x180007a73  mov     esi, edx
0x180007a75  mov     rdi, rcx
0x180007a78  cmp     r8d, 0FEh
0x180007a7f  jz      short loc_180007AFC
0x180007a81  cmp     ebx, 0C8h
0x180007a87  jb      short loc_180007A9D
0x180007a89  cmp     ebx, 100h
0x180007a8f  jl      short loc_180007A99
0x180007a91  cmp     ebx, 200h
0x180007a97  jb      short loc_180007A9D
0x180007a99  xor     al, al
0x180007a9b  jmp     short loc_180007B03
0x180007a9d  call    cs:__imp_AcquireSRWLockExclusive
0x180007aa4  nop     dword ptr [rax+rax+00h]
0x180007aa9  mov     [rsp+58h+var_38], rdi
0x180007aae  cmp     ebx, 7
0x180007ab1  ja      short loc_180007ABD
0x180007ab3  mov     eax, 0CCh
0x180007ab8  bt      eax, ebx
0x180007abb  jb      short loc_180007ADD
0x180007abd  lea     eax, [rbx-100h]
0x180007ac3  cmp     eax, 7Fh
0x180007ac6  jbe     short loc_180007ADD
0x180007ac8  mov     r9d, ebp
0x180007acb  lea     rcx, [rdi+48h]
0x180007acf  mov     r8d, esi
0x180007ad2  mov     edx, ebx
0x180007ad4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007ad9  mov     bl, al
0x180007adb  jmp     short loc_180007AEE
0x180007add  mov     r8d, esi
0x180007ae0  lea     rcx, [rdi+8]
0x180007ae4  mov     edx, ebx
0x180007ae6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007aeb  mov     bl, [rdi+40h]
0x180007aee  lea     rcx, [rsp+58h+var_38]
0x180007af3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007af8  mov     al, bl
0x180007afa  jmp     short loc_180007B03
0x180007afc  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007b01  mov     al, 1
0x180007b03  add     rsp, 38h
0x180007b07  pop     rdi
0x180007b08  pop     rsi
0x180007b09  pop     rbp
0x180007b0a  pop     rbx
0x180007b0b  retn
```
