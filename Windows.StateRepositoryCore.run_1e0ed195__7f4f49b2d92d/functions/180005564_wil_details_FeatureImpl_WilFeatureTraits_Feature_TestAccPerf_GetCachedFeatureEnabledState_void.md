# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180005564`
- end: `0x18000568d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ec0`
- `0x18000a9ac`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180005564`
- `0x18000607c`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180005564  mov     [rsp+arg_10], rbx
0x180005569  mov     [rsp+arg_0], rcx
0x18000556e  push    rbp
0x18000556f  push    rsi
0x180005570  push    rdi
0x180005571  sub     rsp, 30h
0x180005575  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000557c  mov     rdi, rdx
0x18000557f  mov     qword ptr [rdx], 0
0x180005586  mov     eax, [rsi]
0x180005588  mov     [rdx], eax
0x18000558a  and     eax, 6
0x18000558d  cmp     al, 6
0x18000558f  jz      loc_18000567D
0x180005595  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000559a  lea     r8, [rsp+48h+arg_0]
0x18000559f  mov     dword ptr [rsp+48h+arg_0], 0
0x1800055a7  lea     rdx, [rsp+48h+arg_8]
0x1800055ac  mov     ebp, eax
0x1800055ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x1800055b3  mov     eax, [rdi]
0x1800055b5  mov     rbx, [rsp+48h+arg_8]
0x1800055ba  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800055bf  mov     edx, eax
0x1800055c1  mov     [rdi], eax
0x1800055c3  mov     ecx, eax
0x1800055c5  jz      short loc_1800055E0
0x1800055c7  test    dl, 2
0x1800055ca  jnz     short loc_1800055E0
0x1800055cc  and     ecx, 0FFFFF63Eh
0x1800055d2  mov     eax, ebx
0x1800055d4  and     eax, 9C1h
0x1800055d9  or      ecx, eax
0x1800055db  or      ecx, 2
0x1800055de  mov     [rdi], ecx
0x1800055e0  mov     r8d, edx
0x1800055e3  and     r8d, 4
0x1800055e7  jnz     short loc_1800055FB
0x1800055e9  btr     ecx, 0Ah
0x1800055ed  mov     eax, ebx
0x1800055ef  and     eax, 400h
0x1800055f4  or      ecx, eax
0x1800055f6  or      ecx, 4
0x1800055f9  mov     [rdi], ecx
0x1800055fb  mov     eax, edx
0x1800055fd  lock cmpxchg [rsi], ecx
0x180005601  jnz     short loc_1800055BA
0x180005603  test    r8d, r8d
0x180005606  jnz     short loc_180005668
0x180005608  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000560e  test    eax, eax
0x180005610  jz      short loc_180005668
0x180005612  lea     rdx, qword_180018220
0x180005619  lea     rcx, [rsp+48h+arg_8]
0x18000561e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005623  mov     eax, cs:dword_180018234
0x180005629  test    ebp, ebp
0x18000562b  jz      short loc_18000565A
0x18000562d  cmp     ebp, eax
0x18000562f  jnz     short loc_18000565A
0x180005631  mov     r8d, 10h; unsigned __int64
0x180005637  mov     [rsp+48h+var_28], 3
0x180005640  lea     rdx, [rsp+48h+var_28]; void *
0x180005645  mov     [rsp+48h+var_20], rsi
0x18000564a  lea     rcx, qword_180018258; this
0x180005651  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005656  test    al, al
0x180005658  jnz     short loc_18000565E
0x18000565a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000565e  lea     rcx, [rsp+48h+arg_8]
0x180005663  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005668  mov     eax, [rdi]
0x18000566a  test    al, 2
0x18000566c  jnz     short loc_18000567D
0x18000566e  and     eax, 0FFFFF63Eh
0x180005673  and     ebx, 9C1h
0x180005679  or      eax, ebx
0x18000567b  mov     [rdi], eax
0x18000567d  mov     rbx, [rsp+48h+arg_10]
0x180005682  mov     rax, rdi
0x180005685  add     rsp, 30h
0x180005689  pop     rdi
0x18000568a  pop     rsi
0x18000568b  pop     rbp
0x18000568c  retn
```
