# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18002bdd4`
- end: `0x18002be76`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800204d0`

## callees

- `0x1800205fc`
- `0x18002bdd4`
- `0x18002bed0`
- `0x18002bf04`
- `0x18002bf3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002be0d`

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
0x18002bdd4  push    rbx
0x18002bdd6  push    rbp
0x18002bdd7  push    rsi
0x18002bdd8  push    rdi
0x18002bdd9  sub     rsp, 38h
0x18002bddd  mov     rbp, r9
0x18002bde0  mov     ebx, r8d
0x18002bde3  mov     esi, edx
0x18002bde5  mov     rdi, rcx
0x18002bde8  cmp     r8d, 0FEh
0x18002bdef  jz      short loc_18002BE66
0x18002bdf1  cmp     ebx, 0C8h
0x18002bdf7  jb      short loc_18002BE0D
0x18002bdf9  cmp     ebx, 100h
0x18002bdff  jl      short loc_18002BE09
0x18002be01  cmp     ebx, 200h
0x18002be07  jb      short loc_18002BE0D
0x18002be09  xor     al, al
0x18002be0b  jmp     short loc_18002BE6D
0x18002be0d  call    cs:__imp_AcquireSRWLockExclusive
0x18002be13  mov     [rsp+58h+var_38], rdi
0x18002be18  cmp     ebx, 7
0x18002be1b  ja      short loc_18002BE27
0x18002be1d  mov     eax, 0CCh
0x18002be22  bt      eax, ebx
0x18002be25  jb      short loc_18002BE47
0x18002be27  lea     eax, [rbx-100h]
0x18002be2d  cmp     eax, 7Fh
0x18002be30  jbe     short loc_18002BE47
0x18002be32  mov     r9d, ebp
0x18002be35  lea     rcx, [rdi+48h]
0x18002be39  mov     r8d, esi
0x18002be3c  mov     edx, ebx
0x18002be3e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002be43  mov     bl, al
0x18002be45  jmp     short loc_18002BE58
0x18002be47  mov     r8d, esi
0x18002be4a  lea     rcx, [rdi+8]
0x18002be4e  mov     edx, ebx
0x18002be50  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18002be55  mov     bl, [rdi+40h]
0x18002be58  lea     rcx, [rsp+58h+var_38]
0x18002be5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002be62  mov     al, bl
0x18002be64  jmp     short loc_18002BE6D
0x18002be66  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002be6b  mov     al, 1
0x18002be6d  add     rsp, 38h
0x18002be71  pop     rdi
0x18002be72  pop     rsi
0x18002be73  pop     rbp
0x18002be74  pop     rbx
0x18002be75  retn
```
