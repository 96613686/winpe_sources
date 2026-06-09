# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800138dc`
- end: `0x180013a1c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800157a4`
- `0x180015b74`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x1800138dc`
- `0x1800144d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001399a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001399a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, 0xFFFFFFFB);
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
0x1800138dc  mov     [rsp+arg_10], rbx
0x1800138e1  mov     [rsp+arg_18], rbp
0x1800138e6  mov     [rsp+arg_0], rcx
0x1800138eb  push    rsi
0x1800138ec  push    rdi
0x1800138ed  push    r14
0x1800138ef  sub     rsp, 30h
0x1800138f3  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800138fa  mov     rdi, rdx
0x1800138fd  mov     qword ptr [rdx], 0
0x180013904  mov     eax, [rsi]
0x180013906  mov     [rdx], eax
0x180013908  and     eax, 6
0x18001390b  cmp     al, 6
0x18001390d  jz      loc_180013A05
0x180013913  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013918  lea     r8, [rsp+48h+arg_0]
0x18001391d  mov     dword ptr [rsp+48h+arg_0], 0
0x180013925  lea     rdx, [rsp+48h+arg_8]
0x18001392a  mov     ebp, eax
0x18001392c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180013931  mov     eax, [rdi]
0x180013933  mov     rbx, [rsp+48h+arg_8]
0x180013938  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001393d  mov     edx, eax
0x18001393f  mov     [rdi], eax
0x180013941  mov     ecx, eax
0x180013943  jz      short loc_18001395E
0x180013945  test    dl, 2
0x180013948  jnz     short loc_18001395E
0x18001394a  and     ecx, 0FFFFF63Eh
0x180013950  mov     eax, ebx
0x180013952  and     eax, 9C1h
0x180013957  or      ecx, eax
0x180013959  or      ecx, 2
0x18001395c  mov     [rdi], ecx
0x18001395e  mov     r8d, edx
0x180013961  and     r8d, 4
0x180013965  jnz     short loc_180013979
0x180013967  btr     ecx, 0Ah
0x18001396b  mov     eax, ebx
0x18001396d  and     eax, 400h
0x180013972  or      ecx, eax
0x180013974  or      ecx, 4
0x180013977  mov     [rdi], ecx
0x180013979  mov     eax, edx
0x18001397b  lock cmpxchg [rsi], ecx
0x18001397f  jnz     short loc_180013938
0x180013981  test    r8d, r8d
0x180013984  jnz     short loc_1800139F0
0x180013986  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001398c  test    eax, eax
0x18001398e  jz      short loc_1800139F0
0x180013990  lea     r14, stru_180029CA8
0x180013997  mov     rcx, r14; SRWLock
0x18001399a  call    cs:__imp_AcquireSRWLockExclusive
0x1800139a1  nop     dword ptr [rax+rax+00h]
0x1800139a6  mov     eax, cs:dword_180029CBC
0x1800139ac  mov     [rsp+48h+arg_8], r14
0x1800139b1  test    ebp, ebp
0x1800139b3  jz      short loc_1800139E2
0x1800139b5  cmp     ebp, eax
0x1800139b7  jnz     short loc_1800139E2
0x1800139b9  mov     r8d, 10h; unsigned __int64
0x1800139bf  mov     [rsp+48h+var_28], 3
0x1800139c8  lea     rdx, [rsp+48h+var_28]; void *
0x1800139cd  mov     [rsp+48h+var_20], rsi
0x1800139d2  lea     rcx, qword_180029CF0; this
0x1800139d9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800139de  test    al, al
0x1800139e0  jnz     short loc_1800139E6
0x1800139e2  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800139e6  lea     rcx, [rsp+48h+arg_8]
0x1800139eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800139f0  mov     eax, [rdi]
0x1800139f2  test    al, 2
0x1800139f4  jnz     short loc_180013A05
0x1800139f6  and     eax, 0FFFFF63Eh
0x1800139fb  and     ebx, 9C1h
0x180013a01  or      eax, ebx
0x180013a03  mov     [rdi], eax
0x180013a05  mov     rbx, [rsp+48h+arg_10]
0x180013a0a  mov     rax, rdi
0x180013a0d  mov     rbp, [rsp+48h+arg_18]
0x180013a12  add     rsp, 30h
0x180013a16  pop     r14
0x180013a18  pop     rdi
0x180013a19  pop     rsi
0x180013a1a  retn
```
