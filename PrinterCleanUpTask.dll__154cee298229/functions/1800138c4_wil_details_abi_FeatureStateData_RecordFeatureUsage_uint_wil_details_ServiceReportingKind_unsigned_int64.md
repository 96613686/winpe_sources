# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800138c4`
- end: `0x180013966`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `char __fastcall(wil::details_abi::FeatureStateData *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001396c`

## callees

- `0x1800116f0`
- `0x1800138c4`
- `0x1800139e8`
- `0x180013a1c`
- `0x180013a54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800138fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800138fd`

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
0x1800138c4  push    rbx
0x1800138c6  push    rbp
0x1800138c7  push    rsi
0x1800138c8  push    rdi
0x1800138c9  sub     rsp, 38h
0x1800138cd  mov     rbp, r9
0x1800138d0  mov     ebx, r8d
0x1800138d3  mov     esi, edx
0x1800138d5  mov     rdi, rcx
0x1800138d8  cmp     r8d, 0FEh
0x1800138df  jz      short loc_180013956
0x1800138e1  cmp     ebx, 0C8h
0x1800138e7  jb      short loc_1800138FD
0x1800138e9  cmp     ebx, 100h
0x1800138ef  jl      short loc_1800138F9
0x1800138f1  cmp     ebx, 200h
0x1800138f7  jb      short loc_1800138FD
0x1800138f9  xor     al, al
0x1800138fb  jmp     short loc_18001395D
0x1800138fd  call    cs:__imp_AcquireSRWLockExclusive
0x180013903  mov     [rsp+58h+var_38], rdi
0x180013908  cmp     ebx, 7
0x18001390b  ja      short loc_180013917
0x18001390d  mov     eax, 0CCh
0x180013912  bt      eax, ebx
0x180013915  jb      short loc_180013937
0x180013917  lea     eax, [rbx-100h]
0x18001391d  cmp     eax, 7Fh
0x180013920  jbe     short loc_180013937
0x180013922  mov     r9d, ebp
0x180013925  lea     rcx, [rdi+48h]
0x180013929  mov     r8d, esi
0x18001392c  mov     edx, ebx
0x18001392e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180013933  mov     bl, al
0x180013935  jmp     short loc_180013948
0x180013937  mov     r8d, esi
0x18001393a  lea     rcx, [rdi+8]
0x18001393e  mov     edx, ebx
0x180013940  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180013945  mov     bl, [rdi+40h]
0x180013948  lea     rcx, [rsp+58h+var_38]
0x18001394d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013952  mov     al, bl
0x180013954  jmp     short loc_18001395D
0x180013956  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001395b  mov     al, 1
0x18001395d  add     rsp, 38h
0x180013961  pop     rdi
0x180013962  pop     rsi
0x180013963  pop     rbp
0x180013964  pop     rbx
0x180013965  retn
```
