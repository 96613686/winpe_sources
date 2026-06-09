# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cc20`
- end: `0x14000cd59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400132d0`
- `0x140018f58`

## callees

- `0x140009158`
- `0x14000b9f4`
- `0x14000cc20`
- `0x14000d220`
- `0x14001a930`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ccde`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ccde`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SharedPasskeyDependencies__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SharedPasskeyDependencies__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_SharedPasskeyDependencies__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_14002A814
        || (v14[0] = 3,
            v14[1] = Feature_SharedPasskeyDependencies__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002A838, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_SharedPasskeyDependencies__descriptor, 0xFFFFFFFB);
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
0x14000cc20  mov     [rsp+arg_10], rbx
0x14000cc25  mov     [rsp+arg_18], rbp
0x14000cc2a  mov     [rsp+arg_0], rcx
0x14000cc2f  push    rsi
0x14000cc30  push    rdi
0x14000cc31  push    r14
0x14000cc33  sub     rsp, 30h
0x14000cc37  mov     rsi, cs:Feature_SharedPasskeyDependencies__descriptor
0x14000cc3e  mov     rdi, rdx
0x14000cc41  mov     qword ptr [rdx], 0
0x14000cc48  mov     eax, [rsi]
0x14000cc4a  mov     [rdx], eax
0x14000cc4c  and     eax, 6
0x14000cc4f  cmp     al, 6
0x14000cc51  jz      loc_14000CD43
0x14000cc57  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cc5c  lea     r8, [rsp+48h+arg_0]
0x14000cc61  mov     dword ptr [rsp+48h+arg_0], 0
0x14000cc69  lea     rdx, [rsp+48h+arg_8]
0x14000cc6e  mov     ebp, eax
0x14000cc70  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SharedPasskeyDependencies@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SharedPasskeyDependencies>::GetCurrentFeatureEnabledState(int *)
0x14000cc75  mov     eax, [rdi]
0x14000cc77  mov     rbx, [rsp+48h+arg_8]
0x14000cc7c  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000cc81  mov     edx, eax
0x14000cc83  mov     [rdi], eax
0x14000cc85  mov     ecx, eax
0x14000cc87  jz      short loc_14000CCA2
0x14000cc89  test    dl, 2
0x14000cc8c  jnz     short loc_14000CCA2
0x14000cc8e  and     ecx, 0FFFFF63Eh
0x14000cc94  mov     eax, ebx
0x14000cc96  and     eax, 9C1h
0x14000cc9b  or      ecx, eax
0x14000cc9d  or      ecx, 2
0x14000cca0  mov     [rdi], ecx
0x14000cca2  mov     r8d, edx
0x14000cca5  and     r8d, 4
0x14000cca9  jnz     short loc_14000CCBD
0x14000ccab  btr     ecx, 0Ah
0x14000ccaf  mov     eax, ebx
0x14000ccb1  and     eax, 400h
0x14000ccb6  or      ecx, eax
0x14000ccb8  or      ecx, 4
0x14000ccbb  mov     [rdi], ecx
0x14000ccbd  mov     eax, edx
0x14000ccbf  lock cmpxchg [rsi], ecx
0x14000ccc3  jnz     short loc_14000CC7C
0x14000ccc5  test    r8d, r8d
0x14000ccc8  jnz     short loc_14000CD2E
0x14000ccca  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ccd0  test    eax, eax
0x14000ccd2  jz      short loc_14000CD2E
0x14000ccd4  lea     r14, SRWLock
0x14000ccdb  mov     rcx, r14; SRWLock
0x14000ccde  call    cs:__imp_AcquireSRWLockExclusive
0x14000cce4  mov     eax, cs:dword_14002A814
0x14000ccea  mov     [rsp+48h+arg_8], r14
0x14000ccef  test    ebp, ebp
0x14000ccf1  jz      short loc_14000CD20
0x14000ccf3  cmp     ebp, eax
0x14000ccf5  jnz     short loc_14000CD20
0x14000ccf7  mov     r8d, 10h; unsigned __int64
0x14000ccfd  mov     [rsp+48h+var_28], 3
0x14000cd06  lea     rdx, [rsp+48h+var_28]; void *
0x14000cd0b  mov     [rsp+48h+var_20], rsi
0x14000cd10  lea     rcx, qword_14002A838; this
0x14000cd17  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000cd1c  test    al, al
0x14000cd1e  jnz     short loc_14000CD24
0x14000cd20  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000cd24  lea     rcx, [rsp+48h+arg_8]
0x14000cd29  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000cd2e  mov     eax, [rdi]
0x14000cd30  test    al, 2
0x14000cd32  jnz     short loc_14000CD43
0x14000cd34  and     eax, 0FFFFF63Eh
0x14000cd39  and     ebx, 9C1h
0x14000cd3f  or      eax, ebx
0x14000cd41  mov     [rdi], eax
0x14000cd43  mov     rbx, [rsp+48h+arg_10]
0x14000cd48  mov     rax, rdi
0x14000cd4b  mov     rbp, [rsp+48h+arg_18]
0x14000cd50  add     rsp, 30h
0x14000cd54  pop     r14
0x14000cd56  pop     rdi
0x14000cd57  pop     rsi
0x14000cd58  retn
```
