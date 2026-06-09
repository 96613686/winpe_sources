# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCachedFeatureEnabledState(void)

- ea: `0x180015250`
- end: `0x180015390`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c3f0`

## callees

- `0x18000468c`
- `0x180005370`
- `0x18000a490`
- `0x180015250`
- `0x1800153b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001530e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001530e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ModernizeHandlerSingleton__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ModernizeHandlerSingleton__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_ModernizeHandlerSingleton__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18003E4D4
        || (v14[0] = 1,
            v14[1] = Feature_ModernizeHandlerSingleton__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003E508, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ModernizeHandlerSingleton__descriptor, 0xFFFFFFFB);
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
0x180015250  mov     [rsp+arg_10], rbx
0x180015255  mov     [rsp+arg_18], rbp
0x18001525a  mov     [rsp+arg_0], rcx
0x18001525f  push    rsi
0x180015260  push    rdi
0x180015261  push    r14
0x180015263  sub     rsp, 30h
0x180015267  mov     rsi, cs:Feature_ModernizeHandlerSingleton__descriptor
0x18001526e  mov     rdi, rdx
0x180015271  mov     qword ptr [rdx], 0
0x180015278  mov     eax, [rsi]
0x18001527a  mov     [rdx], eax
0x18001527c  and     eax, 6
0x18001527f  cmp     al, 6
0x180015281  jz      loc_180015379
0x180015287  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001528c  lea     r8, [rsp+48h+arg_0]
0x180015291  mov     dword ptr [rsp+48h+arg_0], 0
0x180015299  lea     rdx, [rsp+48h+arg_8]
0x18001529e  mov     ebp, eax
0x1800152a0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ModernizeHandlerSingleton@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModernizeHandlerSingleton>::GetCurrentFeatureEnabledState(int *)
0x1800152a5  mov     eax, [rdi]
0x1800152a7  mov     rbx, [rsp+48h+arg_8]
0x1800152ac  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800152b1  mov     edx, eax
0x1800152b3  mov     [rdi], eax
0x1800152b5  mov     ecx, eax
0x1800152b7  jz      short loc_1800152D2
0x1800152b9  test    dl, 2
0x1800152bc  jnz     short loc_1800152D2
0x1800152be  and     ecx, 0FFFFF63Eh
0x1800152c4  mov     eax, ebx
0x1800152c6  and     eax, 9C1h
0x1800152cb  or      ecx, eax
0x1800152cd  or      ecx, 2
0x1800152d0  mov     [rdi], ecx
0x1800152d2  mov     r8d, edx
0x1800152d5  and     r8d, 4
0x1800152d9  jnz     short loc_1800152ED
0x1800152db  btr     ecx, 0Ah
0x1800152df  mov     eax, ebx
0x1800152e1  and     eax, 400h
0x1800152e6  or      ecx, eax
0x1800152e8  or      ecx, 4
0x1800152eb  mov     [rdi], ecx
0x1800152ed  mov     eax, edx
0x1800152ef  lock cmpxchg [rsi], ecx
0x1800152f3  jnz     short loc_1800152AC
0x1800152f5  test    r8d, r8d
0x1800152f8  jnz     short loc_180015364
0x1800152fa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015300  test    eax, eax
0x180015302  jz      short loc_180015364
0x180015304  lea     r14, SRWLock
0x18001530b  mov     rcx, r14; SRWLock
0x18001530e  call    cs:__imp_AcquireSRWLockExclusive
0x180015315  nop     dword ptr [rax+rax+00h]
0x18001531a  mov     eax, cs:dword_18003E4D4
0x180015320  mov     [rsp+48h+arg_8], r14
0x180015325  test    ebp, ebp
0x180015327  jz      short loc_180015356
0x180015329  cmp     ebp, eax
0x18001532b  jnz     short loc_180015356
0x18001532d  mov     r8d, 10h; unsigned __int64
0x180015333  mov     [rsp+48h+var_28], 1
0x18001533c  lea     rdx, [rsp+48h+var_28]; void *
0x180015341  mov     [rsp+48h+var_20], rsi
0x180015346  lea     rcx, qword_18003E508; this
0x18001534d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015352  test    al, al
0x180015354  jnz     short loc_18001535A
0x180015356  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001535a  lea     rcx, [rsp+48h+arg_8]
0x18001535f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015364  mov     eax, [rdi]
0x180015366  test    al, 2
0x180015368  jnz     short loc_180015379
0x18001536a  and     eax, 0FFFFF63Eh
0x18001536f  and     ebx, 9C1h
0x180015375  or      eax, ebx
0x180015377  mov     [rdi], eax
0x180015379  mov     rbx, [rsp+48h+arg_10]
0x18001537e  mov     rax, rdi
0x180015381  mov     rbp, [rsp+48h+arg_18]
0x180015386  add     rsp, 30h
0x18001538a  pop     r14
0x18001538c  pop     rdi
0x18001538d  pop     rsi
0x18001538e  retn
```
