# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000682c`
- end: `0x18000696b`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800096e0`

## callees

- `0x18000468c`
- `0x180005370`
- `0x18000682c`
- `0x18000a490`
- `0x18000ab28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800068db`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // edi
  int v12; // eax
  int v13; // edx
  bool v14; // si
  char v15; // al
  RTL_SRWLOCK *v16; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+28h] [rbp-30h] BYREF
  int v18; // [rsp+78h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v18 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v18);
    v13 = v18;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v18 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v11
        || v11 != dword_18003E4D4
        || (v17[0] = 0,
            v17[1] = v7,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003E508, v17, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)v7, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    return v14;
  }
}

```

## disassembly

```asm
0x18000682c  mov     [rsp+arg_0], rbx
0x180006831  mov     [rsp+arg_8], rbp
0x180006836  push    rsi
0x180006837  push    rdi
0x180006838  push    r14
0x18000683a  sub     rsp, 40h
0x18000683e  test    r9d, r9d
0x180006841  movzx   esi, r8b
0x180006845  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000684c  mov     ebp, edx
0x18000684e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006855  mov     r14, rcx
0x180006858  cmovnz  rbx, rax
0x18000685c  mov     r9d, [rbx]
0x18000685f  mov     eax, r9d
0x180006862  and     al, 3
0x180006864  cmp     al, 2
0x180006866  jnz     short loc_18000686F
0x180006868  xor     al, al
0x18000686a  jmp     loc_180006957
0x18000686f  test    r9b, 2
0x180006873  jnz     loc_180006939
0x180006879  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000687e  mov     rcx, [rsp+58h+arg_20]
0x180006886  lea     r9, [rsp+58h+arg_18]
0x18000688b  mov     r8d, esi
0x18000688e  mov     [rsp+58h+arg_18], 0
0x180006896  mov     edx, ebp
0x180006898  mov     edi, eax
0x18000689a  mov     dword ptr [rcx], 1
0x1800068a0  mov     rcx, r14
0x1800068a3  call    wil_RtlStagingConfig_QueryFeatureState
0x1800068a8  mov     edx, [rsp+58h+arg_18]
0x1800068ac  test    eax, eax
0x1800068ae  mov     ecx, edx
0x1800068b0  setnz   sil
0x1800068b4  neg     ecx
0x1800068b6  sbb     eax, eax
0x1800068b8  neg     eax
0x1800068ba  add     eax, 6
0x1800068bd  xchg    eax, [rbx]
0x1800068bf  test    edx, edx
0x1800068c1  jnz     short loc_180006934
0x1800068c3  test    al, 4
0x1800068c5  jnz     short loc_180006934
0x1800068c7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800068cd  test    eax, eax
0x1800068cf  jz      short loc_180006934
0x1800068d1  lea     rbp, SRWLock
0x1800068d8  mov     rcx, rbp; SRWLock
0x1800068db  call    cs:__imp_AcquireSRWLockExclusive
0x1800068e2  nop     dword ptr [rax+rax+00h]
0x1800068e7  mov     eax, cs:dword_18003E4D4
0x1800068ed  mov     [rsp+58h+var_38], rbp
0x1800068f2  test    edi, edi
0x1800068f4  jz      short loc_180006923
0x1800068f6  cmp     edi, eax
0x1800068f8  jnz     short loc_180006923
0x1800068fa  mov     r8d, 10h; unsigned __int64
0x180006900  mov     [rsp+58h+var_30], 0
0x180006909  lea     rdx, [rsp+58h+var_30]; void *
0x18000690e  mov     [rsp+58h+var_28], rbx
0x180006913  lea     rcx, qword_18003E508; this
0x18000691a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000691f  test    al, al
0x180006921  jnz     short loc_18000692A
0x180006923  lock and dword ptr [rbx], 0FFFFF7C1h
0x18000692a  lea     rcx, [rsp+58h+var_38]
0x18000692f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180006934  mov     al, sil
0x180006937  jmp     short loc_180006957
0x180006939  mov     rax, [rsp+58h+arg_20]
0x180006941  mov     r8d, esi
0x180006944  xor     r9d, r9d
0x180006947  mov     dword ptr [rax], 1
0x18000694d  call    wil_RtlStagingConfig_QueryFeatureState
0x180006952  test    eax, eax
0x180006954  setnz   al
0x180006957  mov     rbx, [rsp+58h+arg_0]
0x18000695c  mov     rbp, [rsp+58h+arg_8]
0x180006961  add     rsp, 40h
0x180006965  pop     r14
0x180006967  pop     rdi
0x180006968  pop     rsi
0x180006969  retn
```
