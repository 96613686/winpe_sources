# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800206b4`
- end: `0x180020756`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800183d8`

## callees

- `0x180018504`
- `0x18001b964`
- `0x1800206b4`
- `0x1800207b0`
- `0x1800207e4`
- `0x18002081c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  int v9; // eax
  char v10; // bl
  _BYTE v11[56]; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(a1);
    return 1;
  }
  else if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    wil::srwlock::lock_exclusive(a1, v11);
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
              a4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v11);
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
0x1800206b4  push    rbx
0x1800206b6  push    rbp
0x1800206b7  push    rsi
0x1800206b8  push    rdi
0x1800206b9  sub     rsp, 38h
0x1800206bd  mov     rbp, r9
0x1800206c0  mov     ebx, r8d
0x1800206c3  mov     esi, edx
0x1800206c5  mov     rdi, rcx
0x1800206c8  cmp     r8d, 0FEh
0x1800206cf  jz      short loc_180020746
0x1800206d1  cmp     ebx, 0C8h
0x1800206d7  jb      short loc_1800206ED
0x1800206d9  cmp     ebx, 100h
0x1800206df  jl      short loc_1800206E9
0x1800206e1  cmp     ebx, 200h
0x1800206e7  jb      short loc_1800206ED
0x1800206e9  xor     al, al
0x1800206eb  jmp     short loc_18002074D
0x1800206ed  lea     rdx, [rsp+58h+var_38]
0x1800206f2  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x1800206f7  nop
0x1800206f8  cmp     ebx, 7
0x1800206fb  ja      short loc_180020707
0x1800206fd  mov     eax, 0CCh
0x180020702  bt      eax, ebx
0x180020705  jb      short loc_180020727
0x180020707  lea     eax, [rbx-100h]
0x18002070d  cmp     eax, 7Fh
0x180020710  jbe     short loc_180020727
0x180020712  mov     r9d, ebp
0x180020715  lea     rcx, [rdi+48h]
0x180020719  mov     r8d, esi
0x18002071c  mov     edx, ebx
0x18002071e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020723  mov     bl, al
0x180020725  jmp     short loc_180020738
0x180020727  mov     r8d, esi
0x18002072a  mov     edx, ebx
0x18002072c  lea     rcx, [rdi+8]
0x180020730  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180020735  mov     bl, [rdi+40h]
0x180020738  lea     rcx, [rsp+58h+var_38]
0x18002073d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180020742  mov     al, bl
0x180020744  jmp     short loc_18002074D
0x180020746  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18002074b  mov     al, 1
0x18002074d  add     rsp, 38h
0x180020751  pop     rdi
0x180020752  pop     rsi
0x180020753  pop     rbp
0x180020754  pop     rbx
0x180020755  retn
```
