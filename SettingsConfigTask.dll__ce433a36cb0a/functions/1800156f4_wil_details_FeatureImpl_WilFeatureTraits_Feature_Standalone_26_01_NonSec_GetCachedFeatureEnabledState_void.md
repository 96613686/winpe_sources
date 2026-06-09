# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800156f4`
- end: `0x18001582d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b434`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x1800156f4`
- `0x180017424`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800157b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800157b2`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
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
0x1800156f4  mov     [rsp+arg_10], rbx
0x1800156f9  mov     [rsp+arg_18], rbp
0x1800156fe  mov     [rsp+arg_0], rcx
0x180015703  push    rsi
0x180015704  push    rdi
0x180015705  push    r14
0x180015707  sub     rsp, 30h
0x18001570b  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180015712  mov     rdi, rdx
0x180015715  mov     qword ptr [rdx], 0
0x18001571c  mov     eax, [rsi]
0x18001571e  mov     [rdx], eax
0x180015720  and     eax, 6
0x180015723  cmp     al, 6
0x180015725  jz      loc_180015817
0x18001572b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015730  lea     r8, [rsp+48h+arg_0]
0x180015735  mov     dword ptr [rsp+48h+arg_0], 0
0x18001573d  lea     rdx, [rsp+48h+arg_8]
0x180015742  mov     ebp, eax
0x180015744  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180015749  mov     eax, [rdi]
0x18001574b  mov     rbx, [rsp+48h+arg_8]
0x180015750  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015755  mov     edx, eax
0x180015757  mov     [rdi], eax
0x180015759  mov     ecx, eax
0x18001575b  jz      short loc_180015776
0x18001575d  test    dl, 2
0x180015760  jnz     short loc_180015776
0x180015762  and     ecx, 0FFFFF63Eh
0x180015768  mov     eax, ebx
0x18001576a  and     eax, 9C1h
0x18001576f  or      ecx, eax
0x180015771  or      ecx, 2
0x180015774  mov     [rdi], ecx
0x180015776  mov     r8d, edx
0x180015779  and     r8d, 4
0x18001577d  jnz     short loc_180015791
0x18001577f  btr     ecx, 0Ah
0x180015783  mov     eax, ebx
0x180015785  and     eax, 400h
0x18001578a  or      ecx, eax
0x18001578c  or      ecx, 4
0x18001578f  mov     [rdi], ecx
0x180015791  mov     eax, edx
0x180015793  lock cmpxchg [rsi], ecx
0x180015797  jnz     short loc_180015750
0x180015799  test    r8d, r8d
0x18001579c  jnz     short loc_180015802
0x18001579e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800157a4  test    eax, eax
0x1800157a6  jz      short loc_180015802
0x1800157a8  lea     r14, SRWLock
0x1800157af  mov     rcx, r14; SRWLock
0x1800157b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800157b8  mov     eax, cs:dword_18002EED4
0x1800157be  mov     [rsp+48h+arg_8], r14
0x1800157c3  test    ebp, ebp
0x1800157c5  jz      short loc_1800157F4
0x1800157c7  cmp     ebp, eax
0x1800157c9  jnz     short loc_1800157F4
0x1800157cb  mov     r8d, 10h; unsigned __int64
0x1800157d1  mov     [rsp+48h+var_28], 3
0x1800157da  lea     rdx, [rsp+48h+var_28]; void *
0x1800157df  mov     [rsp+48h+var_20], rsi
0x1800157e4  lea     rcx, qword_18002EEF8; this
0x1800157eb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800157f0  test    al, al
0x1800157f2  jnz     short loc_1800157F8
0x1800157f4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800157f8  lea     rcx, [rsp+48h+arg_8]
0x1800157fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015802  mov     eax, [rdi]
0x180015804  test    al, 2
0x180015806  jnz     short loc_180015817
0x180015808  and     eax, 0FFFFF63Eh
0x18001580d  and     ebx, 9C1h
0x180015813  or      eax, ebx
0x180015815  mov     [rdi], eax
0x180015817  mov     rbx, [rsp+48h+arg_10]
0x18001581c  mov     rax, rdi
0x18001581f  mov     rbp, [rsp+48h+arg_18]
0x180015824  add     rsp, 30h
0x180015828  pop     r14
0x18001582a  pop     rdi
0x18001582b  pop     rsi
0x18001582c  retn
```
