# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18002b050`
- end: `0x18002b190`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ca74`
- `0x18002d528`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002b050`
- `0x18002b5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b10e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b10e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_UexTest7__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UexTest7__descriptor, 0xFFFFFFFB);
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
0x18002b050  mov     [rsp+arg_10], rbx
0x18002b055  mov     [rsp+arg_18], rbp
0x18002b05a  mov     [rsp+arg_0], rcx
0x18002b05f  push    rsi
0x18002b060  push    rdi
0x18002b061  push    r14
0x18002b063  sub     rsp, 30h
0x18002b067  mov     rsi, cs:Feature_UexTest7__descriptor
0x18002b06e  mov     rdi, rdx
0x18002b071  mov     qword ptr [rdx], 0
0x18002b078  mov     eax, [rsi]
0x18002b07a  mov     [rdx], eax
0x18002b07c  and     eax, 6
0x18002b07f  cmp     al, 6
0x18002b081  jz      loc_18002B179
0x18002b087  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002b08c  lea     r8, [rsp+48h+arg_0]
0x18002b091  mov     dword ptr [rsp+48h+arg_0], 0
0x18002b099  lea     rdx, [rsp+48h+arg_8]
0x18002b09e  mov     ebp, eax
0x18002b0a0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18002b0a5  mov     eax, [rdi]
0x18002b0a7  mov     rbx, [rsp+48h+arg_8]
0x18002b0ac  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002b0b1  mov     edx, eax
0x18002b0b3  mov     [rdi], eax
0x18002b0b5  mov     ecx, eax
0x18002b0b7  jz      short loc_18002B0D2
0x18002b0b9  test    dl, 2
0x18002b0bc  jnz     short loc_18002B0D2
0x18002b0be  and     ecx, 0FFFFF63Eh
0x18002b0c4  mov     eax, ebx
0x18002b0c6  and     eax, 9C1h
0x18002b0cb  or      ecx, eax
0x18002b0cd  or      ecx, 2
0x18002b0d0  mov     [rdi], ecx
0x18002b0d2  mov     r8d, edx
0x18002b0d5  and     r8d, 4
0x18002b0d9  jnz     short loc_18002B0ED
0x18002b0db  btr     ecx, 0Ah
0x18002b0df  mov     eax, ebx
0x18002b0e1  and     eax, 400h
0x18002b0e6  or      ecx, eax
0x18002b0e8  or      ecx, 4
0x18002b0eb  mov     [rdi], ecx
0x18002b0ed  mov     eax, edx
0x18002b0ef  lock cmpxchg [rsi], ecx
0x18002b0f3  jnz     short loc_18002B0AC
0x18002b0f5  test    r8d, r8d
0x18002b0f8  jnz     short loc_18002B164
0x18002b0fa  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002b100  test    eax, eax
0x18002b102  jz      short loc_18002B164
0x18002b104  lea     r14, SRWLock
0x18002b10b  mov     rcx, r14; SRWLock
0x18002b10e  call    cs:__imp_AcquireSRWLockExclusive
0x18002b115  nop     dword ptr [rax+rax+00h]
0x18002b11a  mov     eax, cs:dword_1800578F4
0x18002b120  mov     [rsp+48h+arg_8], r14
0x18002b125  test    ebp, ebp
0x18002b127  jz      short loc_18002B156
0x18002b129  cmp     ebp, eax
0x18002b12b  jnz     short loc_18002B156
0x18002b12d  mov     r8d, 10h; unsigned __int64
0x18002b133  mov     [rsp+48h+var_28], 3
0x18002b13c  lea     rdx, [rsp+48h+var_28]; void *
0x18002b141  mov     [rsp+48h+var_20], rsi
0x18002b146  lea     rcx, qword_180057928; this
0x18002b14d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002b152  test    al, al
0x18002b154  jnz     short loc_18002B15A
0x18002b156  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002b15a  lea     rcx, [rsp+48h+arg_8]
0x18002b15f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b164  mov     eax, [rdi]
0x18002b166  test    al, 2
0x18002b168  jnz     short loc_18002B179
0x18002b16a  and     eax, 0FFFFF63Eh
0x18002b16f  and     ebx, 9C1h
0x18002b175  or      eax, ebx
0x18002b177  mov     [rdi], eax
0x18002b179  mov     rbx, [rsp+48h+arg_10]
0x18002b17e  mov     rax, rdi
0x18002b181  mov     rbp, [rsp+48h+arg_18]
0x18002b186  add     rsp, 30h
0x18002b18a  pop     r14
0x18002b18c  pop     rdi
0x18002b18d  pop     rsi
0x18002b18e  retn
```
