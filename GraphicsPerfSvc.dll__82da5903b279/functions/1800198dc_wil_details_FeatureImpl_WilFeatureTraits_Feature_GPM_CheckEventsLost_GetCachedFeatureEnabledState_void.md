# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CheckEventsLost>::GetCachedFeatureEnabledState(void)

- ea: `0x1800198dc`
- end: `0x180019a15`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CheckEventsLost@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ad20`
- `0x18001c5d0`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x1800198dc`
- `0x180019d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001999a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001999a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CheckEventsLost>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_CheckEventsLost__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_CheckEventsLost__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CheckEventsLost>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_CheckEventsLost__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_CheckEventsLost__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_CheckEventsLost__descriptor, 0xFFFFFFFB);
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
0x1800198dc  mov     [rsp+arg_10], rbx
0x1800198e1  mov     [rsp+arg_18], rbp
0x1800198e6  mov     [rsp+arg_0], rcx
0x1800198eb  push    rsi
0x1800198ec  push    rdi
0x1800198ed  push    r14
0x1800198ef  sub     rsp, 30h
0x1800198f3  mov     rsi, cs:Feature_GPM_CheckEventsLost__descriptor
0x1800198fa  mov     rdi, rdx
0x1800198fd  mov     qword ptr [rdx], 0
0x180019904  mov     eax, [rsi]
0x180019906  mov     [rdx], eax
0x180019908  and     eax, 6
0x18001990b  cmp     al, 6
0x18001990d  jz      loc_1800199FF
0x180019913  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019918  lea     r8, [rsp+48h+arg_0]
0x18001991d  mov     dword ptr [rsp+48h+arg_0], 0
0x180019925  lea     rdx, [rsp+48h+arg_8]
0x18001992a  mov     ebp, eax
0x18001992c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CheckEventsLost@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CheckEventsLost>::GetCurrentFeatureEnabledState(int *)
0x180019931  mov     eax, [rdi]
0x180019933  mov     rbx, [rsp+48h+arg_8]
0x180019938  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001993d  mov     edx, eax
0x18001993f  mov     [rdi], eax
0x180019941  mov     ecx, eax
0x180019943  jz      short loc_18001995E
0x180019945  test    dl, 2
0x180019948  jnz     short loc_18001995E
0x18001994a  and     ecx, 0FFFFF63Eh
0x180019950  mov     eax, ebx
0x180019952  and     eax, 9C1h
0x180019957  or      ecx, eax
0x180019959  or      ecx, 2
0x18001995c  mov     [rdi], ecx
0x18001995e  mov     r8d, edx
0x180019961  and     r8d, 4
0x180019965  jnz     short loc_180019979
0x180019967  btr     ecx, 0Ah
0x18001996b  mov     eax, ebx
0x18001996d  and     eax, 400h
0x180019972  or      ecx, eax
0x180019974  or      ecx, 4
0x180019977  mov     [rdi], ecx
0x180019979  mov     eax, edx
0x18001997b  lock cmpxchg [rsi], ecx
0x18001997f  jnz     short loc_180019938
0x180019981  test    r8d, r8d
0x180019984  jnz     short loc_1800199EA
0x180019986  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001998c  test    eax, eax
0x18001998e  jz      short loc_1800199EA
0x180019990  lea     r14, stru_180042F88
0x180019997  mov     rcx, r14; SRWLock
0x18001999a  call    cs:__imp_AcquireSRWLockExclusive
0x1800199a0  mov     eax, cs:dword_180042F9C
0x1800199a6  mov     [rsp+48h+arg_8], r14
0x1800199ab  test    ebp, ebp
0x1800199ad  jz      short loc_1800199DC
0x1800199af  cmp     ebp, eax
0x1800199b1  jnz     short loc_1800199DC
0x1800199b3  mov     r8d, 10h; unsigned __int64
0x1800199b9  mov     [rsp+48h+var_28], 1
0x1800199c2  lea     rdx, [rsp+48h+var_28]; void *
0x1800199c7  mov     [rsp+48h+var_20], rsi
0x1800199cc  lea     rcx, qword_180042FC0; this
0x1800199d3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800199d8  test    al, al
0x1800199da  jnz     short loc_1800199E0
0x1800199dc  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800199e0  lea     rcx, [rsp+48h+arg_8]
0x1800199e5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800199ea  mov     eax, [rdi]
0x1800199ec  test    al, 2
0x1800199ee  jnz     short loc_1800199FF
0x1800199f0  and     eax, 0FFFFF63Eh
0x1800199f5  and     ebx, 9C1h
0x1800199fb  or      eax, ebx
0x1800199fd  mov     [rdi], eax
0x1800199ff  mov     rbx, [rsp+48h+arg_10]
0x180019a04  mov     rax, rdi
0x180019a07  mov     rbp, [rsp+48h+arg_18]
0x180019a0c  add     rsp, 30h
0x180019a10  pop     r14
0x180019a12  pop     rdi
0x180019a13  pop     rsi
0x180019a14  retn
```
