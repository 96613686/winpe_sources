# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001cfec`
- end: `0x18001d08e`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001d094`

## callees

- `0x18001c010`
- `0x18001cfec`
- `0x18001d15c`
- `0x18001d190`
- `0x18001d1c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d025`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d025`

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
0x18001cfec  push    rbx
0x18001cfee  push    rbp
0x18001cfef  push    rsi
0x18001cff0  push    rdi
0x18001cff1  sub     rsp, 38h
0x18001cff5  mov     rbp, r9
0x18001cff8  mov     ebx, r8d
0x18001cffb  mov     esi, edx
0x18001cffd  mov     rdi, rcx
0x18001d000  cmp     r8d, 0FEh
0x18001d007  jz      short loc_18001D07E
0x18001d009  cmp     ebx, 0C8h
0x18001d00f  jb      short loc_18001D025
0x18001d011  cmp     ebx, 100h
0x18001d017  jl      short loc_18001D021
0x18001d019  cmp     ebx, 200h
0x18001d01f  jb      short loc_18001D025
0x18001d021  xor     al, al
0x18001d023  jmp     short loc_18001D085
0x18001d025  call    cs:__imp_AcquireSRWLockExclusive
0x18001d02b  mov     [rsp+58h+var_38], rdi
0x18001d030  cmp     ebx, 7
0x18001d033  ja      short loc_18001D03F
0x18001d035  mov     eax, 0CCh
0x18001d03a  bt      eax, ebx
0x18001d03d  jb      short loc_18001D05F
0x18001d03f  lea     eax, [rbx-100h]
0x18001d045  cmp     eax, 7Fh
0x18001d048  jbe     short loc_18001D05F
0x18001d04a  mov     r9d, ebp
0x18001d04d  lea     rcx, [rdi+48h]
0x18001d051  mov     r8d, esi
0x18001d054  mov     edx, ebx
0x18001d056  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001d05b  mov     bl, al
0x18001d05d  jmp     short loc_18001D070
0x18001d05f  mov     r8d, esi
0x18001d062  lea     rcx, [rdi+8]
0x18001d066  mov     edx, ebx
0x18001d068  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001d06d  mov     bl, [rdi+40h]
0x18001d070  lea     rcx, [rsp+58h+var_38]
0x18001d075  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d07a  mov     al, bl
0x18001d07c  jmp     short loc_18001D085
0x18001d07e  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001d083  mov     al, 1
0x18001d085  add     rsp, 38h
0x18001d089  pop     rdi
0x18001d08a  pop     rsi
0x18001d08b  pop     rbp
0x18001d08c  pop     rbx
0x18001d08d  retn
```
