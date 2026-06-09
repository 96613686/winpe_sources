# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001312c`
- end: `0x18001326c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001547c`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x18001312c`
- `0x18001410c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800131ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800131ea`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x18001312c  mov     [rsp+arg_10], rbx
0x180013131  mov     [rsp+arg_18], rbp
0x180013136  mov     [rsp+arg_0], rcx
0x18001313b  push    rsi
0x18001313c  push    rdi
0x18001313d  push    r14
0x18001313f  sub     rsp, 30h
0x180013143  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18001314a  mov     rdi, rdx
0x18001314d  mov     qword ptr [rdx], 0
0x180013154  mov     eax, [rsi]
0x180013156  mov     [rdx], eax
0x180013158  and     eax, 6
0x18001315b  cmp     al, 6
0x18001315d  jz      loc_180013255
0x180013163  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013168  lea     r8, [rsp+48h+arg_0]
0x18001316d  mov     dword ptr [rsp+48h+arg_0], 0
0x180013175  lea     rdx, [rsp+48h+arg_8]
0x18001317a  mov     ebp, eax
0x18001317c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180013181  mov     eax, [rdi]
0x180013183  mov     rbx, [rsp+48h+arg_8]
0x180013188  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001318d  mov     edx, eax
0x18001318f  mov     [rdi], eax
0x180013191  mov     ecx, eax
0x180013193  jz      short loc_1800131AE
0x180013195  test    dl, 2
0x180013198  jnz     short loc_1800131AE
0x18001319a  and     ecx, 0FFFFF63Eh
0x1800131a0  mov     eax, ebx
0x1800131a2  and     eax, 9C1h
0x1800131a7  or      ecx, eax
0x1800131a9  or      ecx, 2
0x1800131ac  mov     [rdi], ecx
0x1800131ae  mov     r8d, edx
0x1800131b1  and     r8d, 4
0x1800131b5  jnz     short loc_1800131C9
0x1800131b7  btr     ecx, 0Ah
0x1800131bb  mov     eax, ebx
0x1800131bd  and     eax, 400h
0x1800131c2  or      ecx, eax
0x1800131c4  or      ecx, 4
0x1800131c7  mov     [rdi], ecx
0x1800131c9  mov     eax, edx
0x1800131cb  lock cmpxchg [rsi], ecx
0x1800131cf  jnz     short loc_180013188
0x1800131d1  test    r8d, r8d
0x1800131d4  jnz     short loc_180013240
0x1800131d6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800131dc  test    eax, eax
0x1800131de  jz      short loc_180013240
0x1800131e0  lea     r14, stru_180029CA8
0x1800131e7  mov     rcx, r14; SRWLock
0x1800131ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800131f1  nop     dword ptr [rax+rax+00h]
0x1800131f6  mov     eax, cs:dword_180029CBC
0x1800131fc  mov     [rsp+48h+arg_8], r14
0x180013201  test    ebp, ebp
0x180013203  jz      short loc_180013232
0x180013205  cmp     ebp, eax
0x180013207  jnz     short loc_180013232
0x180013209  mov     r8d, 10h; unsigned __int64
0x18001320f  mov     [rsp+48h+var_28], 3
0x180013218  lea     rdx, [rsp+48h+var_28]; void *
0x18001321d  mov     [rsp+48h+var_20], rsi
0x180013222  lea     rcx, qword_180029CF0; this
0x180013229  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001322e  test    al, al
0x180013230  jnz     short loc_180013236
0x180013232  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013236  lea     rcx, [rsp+48h+arg_8]
0x18001323b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013240  mov     eax, [rdi]
0x180013242  test    al, 2
0x180013244  jnz     short loc_180013255
0x180013246  and     eax, 0FFFFF63Eh
0x18001324b  and     ebx, 9C1h
0x180013251  or      eax, ebx
0x180013253  mov     [rdi], eax
0x180013255  mov     rbx, [rsp+48h+arg_10]
0x18001325a  mov     rax, rdi
0x18001325d  mov     rbp, [rsp+48h+arg_18]
0x180013262  add     rsp, 30h
0x180013266  pop     r14
0x180013268  pop     rdi
0x180013269  pop     rsi
0x18001326a  retn
```
