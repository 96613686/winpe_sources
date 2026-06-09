# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140005bf4`
- end: `0x140005c96`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x140001b18`

## callees

- `0x140001c44`
- `0x140005bf4`
- `0x140005cd4`
- `0x140005d08`
- `0x140005d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005c2d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005c2d`

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
0x140005bf4  push    rbx
0x140005bf6  push    rbp
0x140005bf7  push    rsi
0x140005bf8  push    rdi
0x140005bf9  sub     rsp, 38h
0x140005bfd  mov     rbp, r9
0x140005c00  mov     ebx, r8d
0x140005c03  mov     esi, edx
0x140005c05  mov     rdi, rcx
0x140005c08  cmp     r8d, 0FEh
0x140005c0f  jz      short loc_140005C86
0x140005c11  cmp     ebx, 0C8h
0x140005c17  jb      short loc_140005C2D
0x140005c19  cmp     ebx, 100h
0x140005c1f  jl      short loc_140005C29
0x140005c21  cmp     ebx, 200h
0x140005c27  jb      short loc_140005C2D
0x140005c29  xor     al, al
0x140005c2b  jmp     short loc_140005C8D
0x140005c2d  call    cs:__imp_AcquireSRWLockExclusive
0x140005c33  mov     [rsp+58h+var_38], rdi
0x140005c38  cmp     ebx, 7
0x140005c3b  ja      short loc_140005C47
0x140005c3d  mov     eax, 0CCh
0x140005c42  bt      eax, ebx
0x140005c45  jb      short loc_140005C67
0x140005c47  lea     eax, [rbx-100h]
0x140005c4d  cmp     eax, 7Fh
0x140005c50  jbe     short loc_140005C67
0x140005c52  mov     r9d, ebp
0x140005c55  lea     rcx, [rdi+48h]
0x140005c59  mov     r8d, esi
0x140005c5c  mov     edx, ebx
0x140005c5e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140005c63  mov     bl, al
0x140005c65  jmp     short loc_140005C78
0x140005c67  mov     r8d, esi
0x140005c6a  lea     rcx, [rdi+8]
0x140005c6e  mov     edx, ebx
0x140005c70  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140005c75  mov     bl, [rdi+40h]
0x140005c78  lea     rcx, [rsp+58h+var_38]
0x140005c7d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005c82  mov     al, bl
0x140005c84  jmp     short loc_140005C8D
0x140005c86  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140005c8b  mov     al, 1
0x140005c8d  add     rsp, 38h
0x140005c91  pop     rdi
0x140005c92  pop     rsi
0x140005c93  pop     rbp
0x140005c94  pop     rbx
0x140005c95  retn
```
