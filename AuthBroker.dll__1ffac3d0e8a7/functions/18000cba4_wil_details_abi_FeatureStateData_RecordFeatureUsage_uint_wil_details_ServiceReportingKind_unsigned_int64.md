# wil::details_abi::FeatureStateData::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000cba4`
- end: `0x18000cc46`
- name: `?RecordFeatureUsage@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `162`
- prototype: `bool __fastcall(wil::details_abi::FeatureStateData *this, unsigned int featureId, wil_details_ServiceReportingKind kind, unsigned __int64 addend)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180006588`

## callees

- `0x1800066b4`
- `0x18000cba4`
- `0x18000cc84`
- `0x18000ccb8`
- `0x18000ccf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cbdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cbdd`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsage(
        wil::details_abi::FeatureStateData *this,
        unsigned int featureId,
        unsigned int kind,
        unsigned __int64 addend)
{
  unsigned int v4; // ebp
  unsigned int v9; // r9d
  int v10; // eax
  bool m_isDirty; // bl
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (__cdecl*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive,wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t> > > lock; // [rsp+20h] [rbp-38h] BYREF

  v4 = addend;
  if ( kind == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(this);
    return 1;
  }
  else if ( kind < 0xC8 || (int)kind >= 256 && kind < 0x200 )
  {
    AcquireSRWLockExclusive(&this->m_lock.m_lock);
    lock.m_ptr = &this->m_lock.m_lock;
    if ( kind <= 7 && (v10 = 204, _bittest(&v10, kind)) || kind - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        &this->m_usage.device,
        (wil_details_ServiceReportingKind)kind,
        featureId,
        v9);
      m_isDirty = this->m_usage.device.m_isDirty;
    }
    else
    {
      m_isDirty = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
                    &this->m_usage.unique,
                    (wil_details_ServiceReportingKind)kind,
                    featureId,
                    v4);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&lock);
    return m_isDirty;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18000cba4  push    rbx
0x18000cba6  push    rbp
0x18000cba7  push    rsi
0x18000cba8  push    rdi
0x18000cba9  sub     rsp, 38h
0x18000cbad  mov     rbp, addend
0x18000cbb0  mov     ebx, kind
0x18000cbb3  mov     esi, featureId
0x18000cbb5  mov     rdi, this
0x18000cbb8  cmp     kind, 0FEh
0x18000cbbf  jz      short loc_18000CC36
0x18000cbc1  cmp     ebx, 0C8h
0x18000cbc7  jb      short loc_18000CBDD
0x18000cbc9  cmp     ebx, 100h
0x18000cbcf  jl      short loc_18000CBD9
0x18000cbd1  cmp     ebx, 200h
0x18000cbd7  jb      short loc_18000CBDD
0x18000cbd9  xor     al, al
0x18000cbdb  jmp     short loc_18000CC3D
0x18000cbdd  call    cs:__imp_AcquireSRWLockExclusive
0x18000cbe3  mov     [rsp+58h+lock.m_ptr], rdi
0x18000cbe8  cmp     ebx, 7
0x18000cbeb  ja      short loc_18000CBF7
0x18000cbed  mov     eax, 0CCh
0x18000cbf2  bt      eax, ebx
0x18000cbf5  jb      short loc_18000CC17
0x18000cbf7  lea     eax, [rbx-100h]
0x18000cbfd  cmp     eax, 7Fh
0x18000cc00  jbe     short loc_18000CC17
0x18000cc02  mov     r9d, ebp; addend
0x18000cc05  lea     this, [rdi+48h]; this
0x18000cc09  mov     kind, esi; value
0x18000cc0c  mov     featureId, ebx; index
0x18000cc0e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000cc13  mov     bl, al
0x18000cc15  jmp     short loc_18000CC28
0x18000cc17  mov     kind, esi; value
0x18000cc1a  lea     this, [rdi+8]; this
0x18000cc1e  mov     featureId, ebx; index
0x18000cc20  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000cc25  mov     bl, [rdi+40h]
0x18000cc28  lea     this, [rsp+58h+lock]; this
0x18000cc2d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000cc32  mov     al, bl
0x18000cc34  jmp     short loc_18000CC3D
0x18000cc36  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000cc3b  mov     al, 1
0x18000cc3d  add     rsp, 38h
0x18000cc41  pop     rdi
0x18000cc42  pop     rsi
0x18000cc43  pop     rbp
0x18000cc44  pop     rbx
0x18000cc45  retn
```
