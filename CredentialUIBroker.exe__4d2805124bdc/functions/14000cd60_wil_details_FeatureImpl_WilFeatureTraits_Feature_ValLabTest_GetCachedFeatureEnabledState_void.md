# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cd60`
- end: `0x14000ce99`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013358`

## callees

- `0x140009158`
- `0x14000b9f4`
- `0x14000cd60`
- `0x14000d2f0`
- `0x14001a930`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ce1e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ce1e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_14002A814
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002A838, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x14000cd60  mov     [rsp+arg_10], rbx
0x14000cd65  mov     [rsp+arg_18], rbp
0x14000cd6a  mov     [rsp+arg_0], rcx
0x14000cd6f  push    rsi
0x14000cd70  push    rdi
0x14000cd71  push    r14
0x14000cd73  sub     rsp, 30h
0x14000cd77  mov     rsi, cs:Feature_ValLabTest__descriptor
0x14000cd7e  mov     rdi, rdx
0x14000cd81  mov     qword ptr [rdx], 0
0x14000cd88  mov     eax, [rsi]
0x14000cd8a  mov     [rdx], eax
0x14000cd8c  and     eax, 6
0x14000cd8f  cmp     al, 6
0x14000cd91  jz      loc_14000CE83
0x14000cd97  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cd9c  lea     r8, [rsp+48h+arg_0]
0x14000cda1  mov     dword ptr [rsp+48h+arg_0], 0
0x14000cda9  lea     rdx, [rsp+48h+arg_8]
0x14000cdae  mov     ebp, eax
0x14000cdb0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x14000cdb5  mov     eax, [rdi]
0x14000cdb7  mov     rbx, [rsp+48h+arg_8]
0x14000cdbc  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000cdc1  mov     edx, eax
0x14000cdc3  mov     [rdi], eax
0x14000cdc5  mov     ecx, eax
0x14000cdc7  jz      short loc_14000CDE2
0x14000cdc9  test    dl, 2
0x14000cdcc  jnz     short loc_14000CDE2
0x14000cdce  and     ecx, 0FFFFF63Eh
0x14000cdd4  mov     eax, ebx
0x14000cdd6  and     eax, 9C1h
0x14000cddb  or      ecx, eax
0x14000cddd  or      ecx, 2
0x14000cde0  mov     [rdi], ecx
0x14000cde2  mov     r8d, edx
0x14000cde5  and     r8d, 4
0x14000cde9  jnz     short loc_14000CDFD
0x14000cdeb  btr     ecx, 0Ah
0x14000cdef  mov     eax, ebx
0x14000cdf1  and     eax, 400h
0x14000cdf6  or      ecx, eax
0x14000cdf8  or      ecx, 4
0x14000cdfb  mov     [rdi], ecx
0x14000cdfd  mov     eax, edx
0x14000cdff  lock cmpxchg [rsi], ecx
0x14000ce03  jnz     short loc_14000CDBC
0x14000ce05  test    r8d, r8d
0x14000ce08  jnz     short loc_14000CE6E
0x14000ce0a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ce10  test    eax, eax
0x14000ce12  jz      short loc_14000CE6E
0x14000ce14  lea     r14, SRWLock
0x14000ce1b  mov     rcx, r14; SRWLock
0x14000ce1e  call    cs:__imp_AcquireSRWLockExclusive
0x14000ce24  mov     eax, cs:dword_14002A814
0x14000ce2a  mov     [rsp+48h+arg_8], r14
0x14000ce2f  test    ebp, ebp
0x14000ce31  jz      short loc_14000CE60
0x14000ce33  cmp     ebp, eax
0x14000ce35  jnz     short loc_14000CE60
0x14000ce37  mov     r8d, 10h; unsigned __int64
0x14000ce3d  mov     [rsp+48h+var_28], 3
0x14000ce46  lea     rdx, [rsp+48h+var_28]; void *
0x14000ce4b  mov     [rsp+48h+var_20], rsi
0x14000ce50  lea     rcx, qword_14002A838; this
0x14000ce57  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000ce5c  test    al, al
0x14000ce5e  jnz     short loc_14000CE64
0x14000ce60  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000ce64  lea     rcx, [rsp+48h+arg_8]
0x14000ce69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ce6e  mov     eax, [rdi]
0x14000ce70  test    al, 2
0x14000ce72  jnz     short loc_14000CE83
0x14000ce74  and     eax, 0FFFFF63Eh
0x14000ce79  and     ebx, 9C1h
0x14000ce7f  or      eax, ebx
0x14000ce81  mov     [rdi], eax
0x14000ce83  mov     rbx, [rsp+48h+arg_10]
0x14000ce88  mov     rax, rdi
0x14000ce8b  mov     rbp, [rsp+48h+arg_18]
0x14000ce90  add     rsp, 30h
0x14000ce94  pop     r14
0x14000ce96  pop     rdi
0x14000ce97  pop     rsi
0x14000ce98  retn
```
