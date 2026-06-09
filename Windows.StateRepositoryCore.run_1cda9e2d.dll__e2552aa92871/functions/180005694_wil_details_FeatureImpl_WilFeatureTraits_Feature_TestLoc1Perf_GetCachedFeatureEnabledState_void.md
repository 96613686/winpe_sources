# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180005694`
- end: `0x1800057bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008f48`
- `0x18000a9e8`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180005694`
- `0x180006160`
- `0x18000ad18`

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
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

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
    v8 = v16;
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
      wil::AcquireSRWLockExclusive(&v16, &unk_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&unk_180018258, v14, 0x10u)) )
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
0x180005694  mov     [rsp+arg_10], rbx
0x180005699  mov     [rsp+arg_0], rcx
0x18000569e  push    rbp
0x18000569f  push    rsi
0x1800056a0  push    rdi
0x1800056a1  sub     rsp, 30h
0x1800056a5  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800056ac  mov     rdi, rdx
0x1800056af  mov     qword ptr [rdx], 0
0x1800056b6  mov     eax, [rsi]
0x1800056b8  mov     [rdx], eax
0x1800056ba  and     eax, 6
0x1800056bd  cmp     al, 6
0x1800056bf  jz      loc_1800057AD
0x1800056c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800056ca  lea     r8, [rsp+48h+arg_0]
0x1800056cf  mov     dword ptr [rsp+48h+arg_0], 0
0x1800056d7  lea     rdx, [rsp+48h+arg_8]
0x1800056dc  mov     ebp, eax
0x1800056de  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x1800056e3  mov     eax, [rdi]
0x1800056e5  mov     rbx, [rsp+48h+arg_8]
0x1800056ea  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800056ef  mov     edx, eax
0x1800056f1  mov     [rdi], eax
0x1800056f3  mov     ecx, eax
0x1800056f5  jz      short loc_180005710
0x1800056f7  test    dl, 2
0x1800056fa  jnz     short loc_180005710
0x1800056fc  and     ecx, 0FFFFF63Eh
0x180005702  mov     eax, ebx
0x180005704  and     eax, 9C1h
0x180005709  or      ecx, eax
0x18000570b  or      ecx, 2
0x18000570e  mov     [rdi], ecx
0x180005710  mov     r8d, edx
0x180005713  and     r8d, 4
0x180005717  jnz     short loc_18000572B
0x180005719  btr     ecx, 0Ah
0x18000571d  mov     eax, ebx
0x18000571f  and     eax, 400h
0x180005724  or      ecx, eax
0x180005726  or      ecx, 4
0x180005729  mov     [rdi], ecx
0x18000572b  mov     eax, edx
0x18000572d  lock cmpxchg [rsi], ecx
0x180005731  jnz     short loc_1800056EA
0x180005733  test    r8d, r8d
0x180005736  jnz     short loc_180005798
0x180005738  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000573e  test    eax, eax
0x180005740  jz      short loc_180005798
0x180005742  lea     rdx, unk_180018220
0x180005749  lea     rcx, [rsp+48h+arg_8]
0x18000574e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005753  mov     eax, cs:dword_180018234
0x180005759  test    ebp, ebp
0x18000575b  jz      short loc_18000578A
0x18000575d  cmp     ebp, eax
0x18000575f  jnz     short loc_18000578A
0x180005761  mov     r8d, 10h; unsigned __int64
0x180005767  mov     [rsp+48h+var_28], 3
0x180005770  lea     rdx, [rsp+48h+var_28]; void *
0x180005775  mov     [rsp+48h+var_20], rsi
0x18000577a  lea     rcx, unk_180018258; this
0x180005781  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005786  test    al, al
0x180005788  jnz     short loc_18000578E
0x18000578a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000578e  lea     rcx, [rsp+48h+arg_8]
0x180005793  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005798  mov     eax, [rdi]
0x18000579a  test    al, 2
0x18000579c  jnz     short loc_1800057AD
0x18000579e  and     eax, 0FFFFF63Eh
0x1800057a3  and     ebx, 9C1h
0x1800057a9  or      eax, ebx
0x1800057ab  mov     [rdi], eax
0x1800057ad  mov     rbx, [rsp+48h+arg_10]
0x1800057b2  mov     rax, rdi
0x1800057b5  add     rsp, 30h
0x1800057b9  pop     rdi
0x1800057ba  pop     rsi
0x1800057bb  pop     rbp
0x1800057bc  retn
```
