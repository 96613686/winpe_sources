# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180015474`
- end: `0x1800155ad`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b32c`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015474`
- `0x18001732c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015532`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015532`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180015474  mov     [rsp+arg_10], rbx
0x180015479  mov     [rsp+arg_18], rbp
0x18001547e  mov     [rsp+arg_0], rcx
0x180015483  push    rsi
0x180015484  push    rdi
0x180015485  push    r14
0x180015487  sub     rsp, 30h
0x18001548b  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180015492  mov     rdi, rdx
0x180015495  mov     qword ptr [rdx], 0
0x18001549c  mov     eax, [rsi]
0x18001549e  mov     [rdx], eax
0x1800154a0  and     eax, 6
0x1800154a3  cmp     al, 6
0x1800154a5  jz      loc_180015597
0x1800154ab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800154b0  lea     r8, [rsp+48h+arg_0]
0x1800154b5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800154bd  lea     rdx, [rsp+48h+arg_8]
0x1800154c2  mov     ebp, eax
0x1800154c4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800154c9  mov     eax, [rdi]
0x1800154cb  mov     rbx, [rsp+48h+arg_8]
0x1800154d0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800154d5  mov     edx, eax
0x1800154d7  mov     [rdi], eax
0x1800154d9  mov     ecx, eax
0x1800154db  jz      short loc_1800154F6
0x1800154dd  test    dl, 2
0x1800154e0  jnz     short loc_1800154F6
0x1800154e2  and     ecx, 0FFFFF63Eh
0x1800154e8  mov     eax, ebx
0x1800154ea  and     eax, 9C1h
0x1800154ef  or      ecx, eax
0x1800154f1  or      ecx, 2
0x1800154f4  mov     [rdi], ecx
0x1800154f6  mov     r8d, edx
0x1800154f9  and     r8d, 4
0x1800154fd  jnz     short loc_180015511
0x1800154ff  btr     ecx, 0Ah
0x180015503  mov     eax, ebx
0x180015505  and     eax, 400h
0x18001550a  or      ecx, eax
0x18001550c  or      ecx, 4
0x18001550f  mov     [rdi], ecx
0x180015511  mov     eax, edx
0x180015513  lock cmpxchg [rsi], ecx
0x180015517  jnz     short loc_1800154D0
0x180015519  test    r8d, r8d
0x18001551c  jnz     short loc_180015582
0x18001551e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015524  test    eax, eax
0x180015526  jz      short loc_180015582
0x180015528  lea     r14, SRWLock
0x18001552f  mov     rcx, r14; SRWLock
0x180015532  call    cs:__imp_AcquireSRWLockExclusive
0x180015538  mov     eax, cs:dword_18002EED4
0x18001553e  mov     [rsp+48h+arg_8], r14
0x180015543  test    ebp, ebp
0x180015545  jz      short loc_180015574
0x180015547  cmp     ebp, eax
0x180015549  jnz     short loc_180015574
0x18001554b  mov     r8d, 10h; unsigned __int64
0x180015551  mov     [rsp+48h+var_28], 3
0x18001555a  lea     rdx, [rsp+48h+var_28]; void *
0x18001555f  mov     [rsp+48h+var_20], rsi
0x180015564  lea     rcx, qword_18002EEF8; this
0x18001556b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015570  test    al, al
0x180015572  jnz     short loc_180015578
0x180015574  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015578  lea     rcx, [rsp+48h+arg_8]
0x18001557d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015582  mov     eax, [rdi]
0x180015584  test    al, 2
0x180015586  jnz     short loc_180015597
0x180015588  and     eax, 0FFFFF63Eh
0x18001558d  and     ebx, 9C1h
0x180015593  or      eax, ebx
0x180015595  mov     [rdi], eax
0x180015597  mov     rbx, [rsp+48h+arg_10]
0x18001559c  mov     rax, rdi
0x18001559f  mov     rbp, [rsp+48h+arg_18]
0x1800155a4  add     rsp, 30h
0x1800155a8  pop     r14
0x1800155aa  pop     rdi
0x1800155ab  pop     rsi
0x1800155ac  retn
```
