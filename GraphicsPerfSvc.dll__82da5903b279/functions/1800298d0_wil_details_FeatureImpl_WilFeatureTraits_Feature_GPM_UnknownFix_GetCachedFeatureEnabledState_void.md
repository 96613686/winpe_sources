# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetCachedFeatureEnabledState(void)

- ea: `0x1800298d0`
- end: `0x180029a09`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_UnknownFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d3e4`
- `0x18002dd7c`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x1800298d0`
- `0x180029a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002998e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002998e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_UnknownFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_UnknownFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_UnknownFix__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_UnknownFix__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_UnknownFix__descriptor, 0xFFFFFFFB);
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
0x1800298d0  mov     [rsp+arg_10], rbx
0x1800298d5  mov     [rsp+arg_18], rbp
0x1800298da  mov     [rsp+arg_0], rcx
0x1800298df  push    rsi
0x1800298e0  push    rdi
0x1800298e1  push    r14
0x1800298e3  sub     rsp, 30h
0x1800298e7  mov     rsi, cs:Feature_GPM_UnknownFix__descriptor
0x1800298ee  mov     rdi, rdx
0x1800298f1  mov     qword ptr [rdx], 0
0x1800298f8  mov     eax, [rsi]
0x1800298fa  mov     [rdx], eax
0x1800298fc  and     eax, 6
0x1800298ff  cmp     al, 6
0x180029901  jz      loc_1800299F3
0x180029907  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002990c  lea     r8, [rsp+48h+arg_0]
0x180029911  mov     dword ptr [rsp+48h+arg_0], 0
0x180029919  lea     rdx, [rsp+48h+arg_8]
0x18002991e  mov     ebp, eax
0x180029920  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_UnknownFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_UnknownFix>::GetCurrentFeatureEnabledState(int *)
0x180029925  mov     eax, [rdi]
0x180029927  mov     rbx, [rsp+48h+arg_8]
0x18002992c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180029931  mov     edx, eax
0x180029933  mov     [rdi], eax
0x180029935  mov     ecx, eax
0x180029937  jz      short loc_180029952
0x180029939  test    dl, 2
0x18002993c  jnz     short loc_180029952
0x18002993e  and     ecx, 0FFFFF63Eh
0x180029944  mov     eax, ebx
0x180029946  and     eax, 9C1h
0x18002994b  or      ecx, eax
0x18002994d  or      ecx, 2
0x180029950  mov     [rdi], ecx
0x180029952  mov     r8d, edx
0x180029955  and     r8d, 4
0x180029959  jnz     short loc_18002996D
0x18002995b  btr     ecx, 0Ah
0x18002995f  mov     eax, ebx
0x180029961  and     eax, 400h
0x180029966  or      ecx, eax
0x180029968  or      ecx, 4
0x18002996b  mov     [rdi], ecx
0x18002996d  mov     eax, edx
0x18002996f  lock cmpxchg [rsi], ecx
0x180029973  jnz     short loc_18002992C
0x180029975  test    r8d, r8d
0x180029978  jnz     short loc_1800299DE
0x18002997a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180029980  test    eax, eax
0x180029982  jz      short loc_1800299DE
0x180029984  lea     r14, stru_180042F88
0x18002998b  mov     rcx, r14; SRWLock
0x18002998e  call    cs:__imp_AcquireSRWLockExclusive
0x180029994  mov     eax, cs:dword_180042F9C
0x18002999a  mov     [rsp+48h+arg_8], r14
0x18002999f  test    ebp, ebp
0x1800299a1  jz      short loc_1800299D0
0x1800299a3  cmp     ebp, eax
0x1800299a5  jnz     short loc_1800299D0
0x1800299a7  mov     r8d, 10h; unsigned __int64
0x1800299ad  mov     [rsp+48h+var_28], 1
0x1800299b6  lea     rdx, [rsp+48h+var_28]; void *
0x1800299bb  mov     [rsp+48h+var_20], rsi
0x1800299c0  lea     rcx, qword_180042FC0; this
0x1800299c7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800299cc  test    al, al
0x1800299ce  jnz     short loc_1800299D4
0x1800299d0  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800299d4  lea     rcx, [rsp+48h+arg_8]
0x1800299d9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800299de  mov     eax, [rdi]
0x1800299e0  test    al, 2
0x1800299e2  jnz     short loc_1800299F3
0x1800299e4  and     eax, 0FFFFF63Eh
0x1800299e9  and     ebx, 9C1h
0x1800299ef  or      eax, ebx
0x1800299f1  mov     [rdi], eax
0x1800299f3  mov     rbx, [rsp+48h+arg_10]
0x1800299f8  mov     rax, rdi
0x1800299fb  mov     rbp, [rsp+48h+arg_18]
0x180029a00  add     rsp, 30h
0x180029a04  pop     r14
0x180029a06  pop     rdi
0x180029a07  pop     rsi
0x180029a08  retn
```
