# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_CrashFix>::GetCachedFeatureEnabledState(void)

- ea: `0x18006de90`
- end: `0x18006dfd0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_CrashFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006e1d0`
- `0x18006e4f4`

## callees

- `0x180052984`
- `0x180053800`
- `0x180058168`
- `0x18006de90`
- `0x18006dfd8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18006df4e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006df4e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_CrashFix>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  int v10; // r8d
  _QWORD v12[5]; // [rsp+20h] [rbp-28h] BYREF
  RTL_SRWLOCK *v13; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UniDrv_CrashFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UniDrv_CrashFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_CrashFix>::GetCurrentFeatureEnabledState(v5, &v13);
    v6 = *(_DWORD *)a2;
    v7 = (__int16)v13;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      v10 = v6 & 4;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UniDrv_CrashFix__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( !v10 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v13 = &SRWLock;
      if ( !v4
        || v4 != dword_1800933F4
        || (v12[0] = 3,
            v12[1] = Feature_UniDrv_CrashFix__descriptor,
            !wil::details_abi::heap_buffer::push_back((void **)qword_180093428, v12, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UniDrv_CrashFix__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18006de90  mov     [rsp+arg_10], rbx
0x18006de95  mov     [rsp+arg_18], rbp
0x18006de9a  mov     [rsp+arg_0], rcx
0x18006de9f  push    rsi
0x18006dea0  push    rdi
0x18006dea1  push    r14
0x18006dea3  sub     rsp, 30h
0x18006dea7  mov     rsi, cs:Feature_UniDrv_CrashFix__descriptor
0x18006deae  mov     rdi, rdx
0x18006deb1  mov     qword ptr [rdx], 0
0x18006deb8  mov     eax, [rsi]
0x18006deba  mov     [rdx], eax
0x18006debc  and     eax, 6
0x18006debf  cmp     al, 6
0x18006dec1  jz      loc_18006DFB9
0x18006dec7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18006decc  lea     r8, [rsp+48h+arg_0]
0x18006ded1  mov     dword ptr [rsp+48h+arg_0], 0
0x18006ded9  lea     rdx, [rsp+48h+arg_8]
0x18006dede  mov     ebp, eax
0x18006dee0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UniDrv_CrashFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UniDrv_CrashFix>::GetCurrentFeatureEnabledState(int *)
0x18006dee5  mov     eax, [rdi]
0x18006dee7  mov     rbx, [rsp+48h+arg_8]
0x18006deec  cmp     dword ptr [rsp+48h+arg_0], 0
0x18006def1  mov     edx, eax
0x18006def3  mov     [rdi], eax
0x18006def5  mov     ecx, eax
0x18006def7  jz      short loc_18006DF12
0x18006def9  test    dl, 2
0x18006defc  jnz     short loc_18006DF12
0x18006defe  and     ecx, 0FFFFF63Eh
0x18006df04  mov     eax, ebx
0x18006df06  and     eax, 9C1h
0x18006df0b  or      ecx, eax
0x18006df0d  or      ecx, 2
0x18006df10  mov     [rdi], ecx
0x18006df12  mov     r8d, edx
0x18006df15  and     r8d, 4
0x18006df19  jnz     short loc_18006DF2D
0x18006df1b  btr     ecx, 0Ah
0x18006df1f  mov     eax, ebx
0x18006df21  and     eax, 400h
0x18006df26  or      ecx, eax
0x18006df28  or      ecx, 4
0x18006df2b  mov     [rdi], ecx
0x18006df2d  mov     eax, edx
0x18006df2f  lock cmpxchg [rsi], ecx
0x18006df33  jnz     short loc_18006DEEC
0x18006df35  test    r8d, r8d
0x18006df38  jnz     short loc_18006DFA4
0x18006df3a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18006df40  test    eax, eax
0x18006df42  jz      short loc_18006DFA4
0x18006df44  lea     r14, SRWLock
0x18006df4b  mov     rcx, r14; SRWLock
0x18006df4e  call    cs:__imp_AcquireSRWLockExclusive
0x18006df55  nop     dword ptr [rax+rax+00h]
0x18006df5a  mov     eax, cs:dword_1800933F4
0x18006df60  mov     [rsp+48h+arg_8], r14
0x18006df65  test    ebp, ebp
0x18006df67  jz      short loc_18006DF96
0x18006df69  cmp     ebp, eax
0x18006df6b  jnz     short loc_18006DF96
0x18006df6d  mov     r8d, 10h; unsigned __int64
0x18006df73  mov     [rsp+48h+var_28], 3
0x18006df7c  lea     rdx, [rsp+48h+var_28]; void *
0x18006df81  mov     [rsp+48h+var_20], rsi
0x18006df86  lea     rcx, qword_180093428; this
0x18006df8d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006df92  test    al, al
0x18006df94  jnz     short loc_18006DF9A
0x18006df96  lock and dword ptr [rsi], 0FFFFFFFBh
0x18006df9a  lea     rcx, [rsp+48h+arg_8]
0x18006df9f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006dfa4  mov     eax, [rdi]
0x18006dfa6  test    al, 2
0x18006dfa8  jnz     short loc_18006DFB9
0x18006dfaa  and     eax, 0FFFFF63Eh
0x18006dfaf  and     ebx, 9C1h
0x18006dfb5  or      eax, ebx
0x18006dfb7  mov     [rdi], eax
0x18006dfb9  mov     rbx, [rsp+48h+arg_10]
0x18006dfbe  mov     rax, rdi
0x18006dfc1  mov     rbp, [rsp+48h+arg_18]
0x18006dfc6  add     rsp, 30h
0x18006dfca  pop     r14
0x18006dfcc  pop     rdi
0x18006dfcd  pop     rsi
0x18006dfce  retn
```
