# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180012fe4`
- end: `0x180013124`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800153f8`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180012fe4`
- `0x180014090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800130a2`

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
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
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
0x180012fe4  mov     [rsp+arg_10], rbx
0x180012fe9  mov     [rsp+arg_18], rbp
0x180012fee  mov     [rsp+arg_0], rcx
0x180012ff3  push    rsi
0x180012ff4  push    rdi
0x180012ff5  push    r14
0x180012ff7  sub     rsp, 30h
0x180012ffb  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180013002  mov     rdi, rdx
0x180013005  mov     qword ptr [rdx], 0
0x18001300c  mov     eax, [rsi]
0x18001300e  mov     [rdx], eax
0x180013010  and     eax, 6
0x180013013  cmp     al, 6
0x180013015  jz      loc_18001310D
0x18001301b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013020  lea     r8, [rsp+48h+arg_0]
0x180013025  mov     dword ptr [rsp+48h+arg_0], 0
0x18001302d  lea     rdx, [rsp+48h+arg_8]
0x180013032  mov     ebp, eax
0x180013034  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180013039  mov     eax, [rdi]
0x18001303b  mov     rbx, [rsp+48h+arg_8]
0x180013040  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013045  mov     edx, eax
0x180013047  mov     [rdi], eax
0x180013049  mov     ecx, eax
0x18001304b  jz      short loc_180013066
0x18001304d  test    dl, 2
0x180013050  jnz     short loc_180013066
0x180013052  and     ecx, 0FFFFF63Eh
0x180013058  mov     eax, ebx
0x18001305a  and     eax, 9C1h
0x18001305f  or      ecx, eax
0x180013061  or      ecx, 2
0x180013064  mov     [rdi], ecx
0x180013066  mov     r8d, edx
0x180013069  and     r8d, 4
0x18001306d  jnz     short loc_180013081
0x18001306f  btr     ecx, 0Ah
0x180013073  mov     eax, ebx
0x180013075  and     eax, 400h
0x18001307a  or      ecx, eax
0x18001307c  or      ecx, 4
0x18001307f  mov     [rdi], ecx
0x180013081  mov     eax, edx
0x180013083  lock cmpxchg [rsi], ecx
0x180013087  jnz     short loc_180013040
0x180013089  test    r8d, r8d
0x18001308c  jnz     short loc_1800130F8
0x18001308e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013094  test    eax, eax
0x180013096  jz      short loc_1800130F8
0x180013098  lea     r14, stru_180029CA8
0x18001309f  mov     rcx, r14; SRWLock
0x1800130a2  call    cs:__imp_AcquireSRWLockExclusive
0x1800130a9  nop     dword ptr [rax+rax+00h]
0x1800130ae  mov     eax, cs:dword_180029CBC
0x1800130b4  mov     [rsp+48h+arg_8], r14
0x1800130b9  test    ebp, ebp
0x1800130bb  jz      short loc_1800130EA
0x1800130bd  cmp     ebp, eax
0x1800130bf  jnz     short loc_1800130EA
0x1800130c1  mov     r8d, 10h; unsigned __int64
0x1800130c7  mov     [rsp+48h+var_28], 3
0x1800130d0  lea     rdx, [rsp+48h+var_28]; void *
0x1800130d5  mov     [rsp+48h+var_20], rsi
0x1800130da  lea     rcx, qword_180029CF0; this
0x1800130e1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800130e6  test    al, al
0x1800130e8  jnz     short loc_1800130EE
0x1800130ea  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800130ee  lea     rcx, [rsp+48h+arg_8]
0x1800130f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800130f8  mov     eax, [rdi]
0x1800130fa  test    al, 2
0x1800130fc  jnz     short loc_18001310D
0x1800130fe  and     eax, 0FFFFF63Eh
0x180013103  and     ebx, 9C1h
0x180013109  or      eax, ebx
0x18001310b  mov     [rdi], eax
0x18001310d  mov     rbx, [rsp+48h+arg_10]
0x180013112  mov     rax, rdi
0x180013115  mov     rbp, [rsp+48h+arg_18]
0x18001311a  add     rsp, 30h
0x18001311e  pop     r14
0x180013120  pop     rdi
0x180013121  pop     rsi
0x180013122  retn
```
