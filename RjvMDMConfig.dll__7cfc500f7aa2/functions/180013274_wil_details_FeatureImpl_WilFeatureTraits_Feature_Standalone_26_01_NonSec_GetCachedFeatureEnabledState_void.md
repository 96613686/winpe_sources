# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013274`
- end: `0x1800133b4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180013274`
- `0x180014188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013332`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013332`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
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
0x180013274  mov     [rsp+arg_10], rbx
0x180013279  mov     [rsp+arg_18], rbp
0x18001327e  mov     [rsp+arg_0], rcx
0x180013283  push    rsi
0x180013284  push    rdi
0x180013285  push    r14
0x180013287  sub     rsp, 30h
0x18001328b  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180013292  mov     rdi, rdx
0x180013295  mov     qword ptr [rdx], 0
0x18001329c  mov     eax, [rsi]
0x18001329e  mov     [rdx], eax
0x1800132a0  and     eax, 6
0x1800132a3  cmp     al, 6
0x1800132a5  jz      loc_18001339D
0x1800132ab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800132b0  lea     r8, [rsp+48h+arg_0]
0x1800132b5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800132bd  lea     rdx, [rsp+48h+arg_8]
0x1800132c2  mov     ebp, eax
0x1800132c4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800132c9  mov     eax, [rdi]
0x1800132cb  mov     rbx, [rsp+48h+arg_8]
0x1800132d0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800132d5  mov     edx, eax
0x1800132d7  mov     [rdi], eax
0x1800132d9  mov     ecx, eax
0x1800132db  jz      short loc_1800132F6
0x1800132dd  test    dl, 2
0x1800132e0  jnz     short loc_1800132F6
0x1800132e2  and     ecx, 0FFFFF63Eh
0x1800132e8  mov     eax, ebx
0x1800132ea  and     eax, 9C1h
0x1800132ef  or      ecx, eax
0x1800132f1  or      ecx, 2
0x1800132f4  mov     [rdi], ecx
0x1800132f6  mov     r8d, edx
0x1800132f9  and     r8d, 4
0x1800132fd  jnz     short loc_180013311
0x1800132ff  btr     ecx, 0Ah
0x180013303  mov     eax, ebx
0x180013305  and     eax, 400h
0x18001330a  or      ecx, eax
0x18001330c  or      ecx, 4
0x18001330f  mov     [rdi], ecx
0x180013311  mov     eax, edx
0x180013313  lock cmpxchg [rsi], ecx
0x180013317  jnz     short loc_1800132D0
0x180013319  test    r8d, r8d
0x18001331c  jnz     short loc_180013388
0x18001331e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013324  test    eax, eax
0x180013326  jz      short loc_180013388
0x180013328  lea     r14, stru_180029CA8
0x18001332f  mov     rcx, r14; SRWLock
0x180013332  call    cs:__imp_AcquireSRWLockExclusive
0x180013339  nop     dword ptr [rax+rax+00h]
0x18001333e  mov     eax, cs:dword_180029CBC
0x180013344  mov     [rsp+48h+arg_8], r14
0x180013349  test    ebp, ebp
0x18001334b  jz      short loc_18001337A
0x18001334d  cmp     ebp, eax
0x18001334f  jnz     short loc_18001337A
0x180013351  mov     r8d, 10h; unsigned __int64
0x180013357  mov     [rsp+48h+var_28], 3
0x180013360  lea     rdx, [rsp+48h+var_28]; void *
0x180013365  mov     [rsp+48h+var_20], rsi
0x18001336a  lea     rcx, qword_180029CF0; this
0x180013371  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013376  test    al, al
0x180013378  jnz     short loc_18001337E
0x18001337a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001337e  lea     rcx, [rsp+48h+arg_8]
0x180013383  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013388  mov     eax, [rdi]
0x18001338a  test    al, 2
0x18001338c  jnz     short loc_18001339D
0x18001338e  and     eax, 0FFFFF63Eh
0x180013393  and     ebx, 9C1h
0x180013399  or      eax, ebx
0x18001339b  mov     [rdi], eax
0x18001339d  mov     rbx, [rsp+48h+arg_10]
0x1800133a2  mov     rax, rdi
0x1800133a5  mov     rbp, [rsp+48h+arg_18]
0x1800133aa  add     rsp, 30h
0x1800133ae  pop     r14
0x1800133b0  pop     rdi
0x1800133b1  pop     rsi
0x1800133b2  retn
```
