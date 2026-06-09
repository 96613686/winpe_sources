# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18002af08`
- end: `0x18002b048`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c9e8`
- `0x18002d4ec`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002af08`
- `0x18002b4f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002afc6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002afc6`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
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
0x18002af08  mov     [rsp+arg_10], rbx
0x18002af0d  mov     [rsp+arg_18], rbp
0x18002af12  mov     [rsp+arg_0], rcx
0x18002af17  push    rsi
0x18002af18  push    rdi
0x18002af19  push    r14
0x18002af1b  sub     rsp, 30h
0x18002af1f  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18002af26  mov     rdi, rdx
0x18002af29  mov     qword ptr [rdx], 0
0x18002af30  mov     eax, [rsi]
0x18002af32  mov     [rdx], eax
0x18002af34  and     eax, 6
0x18002af37  cmp     al, 6
0x18002af39  jz      loc_18002B031
0x18002af3f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002af44  lea     r8, [rsp+48h+arg_0]
0x18002af49  mov     dword ptr [rsp+48h+arg_0], 0
0x18002af51  lea     rdx, [rsp+48h+arg_8]
0x18002af56  mov     ebp, eax
0x18002af58  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18002af5d  mov     eax, [rdi]
0x18002af5f  mov     rbx, [rsp+48h+arg_8]
0x18002af64  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002af69  mov     edx, eax
0x18002af6b  mov     [rdi], eax
0x18002af6d  mov     ecx, eax
0x18002af6f  jz      short loc_18002AF8A
0x18002af71  test    dl, 2
0x18002af74  jnz     short loc_18002AF8A
0x18002af76  and     ecx, 0FFFFF63Eh
0x18002af7c  mov     eax, ebx
0x18002af7e  and     eax, 9C1h
0x18002af83  or      ecx, eax
0x18002af85  or      ecx, 2
0x18002af88  mov     [rdi], ecx
0x18002af8a  mov     r8d, edx
0x18002af8d  and     r8d, 4
0x18002af91  jnz     short loc_18002AFA5
0x18002af93  btr     ecx, 0Ah
0x18002af97  mov     eax, ebx
0x18002af99  and     eax, 400h
0x18002af9e  or      ecx, eax
0x18002afa0  or      ecx, 4
0x18002afa3  mov     [rdi], ecx
0x18002afa5  mov     eax, edx
0x18002afa7  lock cmpxchg [rsi], ecx
0x18002afab  jnz     short loc_18002AF64
0x18002afad  test    r8d, r8d
0x18002afb0  jnz     short loc_18002B01C
0x18002afb2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002afb8  test    eax, eax
0x18002afba  jz      short loc_18002B01C
0x18002afbc  lea     r14, SRWLock
0x18002afc3  mov     rcx, r14; SRWLock
0x18002afc6  call    cs:__imp_AcquireSRWLockExclusive
0x18002afcd  nop     dword ptr [rax+rax+00h]
0x18002afd2  mov     eax, cs:dword_1800578F4
0x18002afd8  mov     [rsp+48h+arg_8], r14
0x18002afdd  test    ebp, ebp
0x18002afdf  jz      short loc_18002B00E
0x18002afe1  cmp     ebp, eax
0x18002afe3  jnz     short loc_18002B00E
0x18002afe5  mov     r8d, 10h; unsigned __int64
0x18002afeb  mov     [rsp+48h+var_28], 3
0x18002aff4  lea     rdx, [rsp+48h+var_28]; void *
0x18002aff9  mov     [rsp+48h+var_20], rsi
0x18002affe  lea     rcx, qword_180057928; this
0x18002b005  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002b00a  test    al, al
0x18002b00c  jnz     short loc_18002B012
0x18002b00e  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002b012  lea     rcx, [rsp+48h+arg_8]
0x18002b017  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b01c  mov     eax, [rdi]
0x18002b01e  test    al, 2
0x18002b020  jnz     short loc_18002B031
0x18002b022  and     eax, 0FFFFF63Eh
0x18002b027  and     ebx, 9C1h
0x18002b02d  or      eax, ebx
0x18002b02f  mov     [rdi], eax
0x18002b031  mov     rbx, [rsp+48h+arg_10]
0x18002b036  mov     rax, rdi
0x18002b039  mov     rbp, [rsp+48h+arg_18]
0x18002b03e  add     rsp, 30h
0x18002b042  pop     r14
0x18002b044  pop     rdi
0x18002b045  pop     rsi
0x18002b046  retn
```
