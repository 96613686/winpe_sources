# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCachedFeatureEnabledState(void)

- ea: `0x180012320`
- end: `0x180012459`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ECP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013034`
- `0x180013fb8`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180012320`
- `0x180012908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800123de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800123de`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ECP__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ECP__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ECP__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_ECP__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ECP__descriptor, 0xFFFFFFFB);
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
0x180012320  mov     [rsp+arg_10], rbx
0x180012325  mov     [rsp+arg_18], rbp
0x18001232a  mov     [rsp+arg_0], rcx
0x18001232f  push    rsi
0x180012330  push    rdi
0x180012331  push    r14
0x180012333  sub     rsp, 30h
0x180012337  mov     rsi, cs:Feature_ECP__descriptor
0x18001233e  mov     rdi, rdx
0x180012341  mov     qword ptr [rdx], 0
0x180012348  mov     eax, [rsi]
0x18001234a  mov     [rdx], eax
0x18001234c  and     eax, 6
0x18001234f  cmp     al, 6
0x180012351  jz      loc_180012443
0x180012357  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001235c  lea     r8, [rsp+48h+arg_0]
0x180012361  mov     dword ptr [rsp+48h+arg_0], 0
0x180012369  lea     rdx, [rsp+48h+arg_8]
0x18001236e  mov     ebp, eax
0x180012370  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ECP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ECP>::GetCurrentFeatureEnabledState(int *)
0x180012375  mov     eax, [rdi]
0x180012377  mov     rbx, [rsp+48h+arg_8]
0x18001237c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180012381  mov     edx, eax
0x180012383  mov     [rdi], eax
0x180012385  mov     ecx, eax
0x180012387  jz      short loc_1800123A2
0x180012389  test    dl, 2
0x18001238c  jnz     short loc_1800123A2
0x18001238e  and     ecx, 0FFFFF63Eh
0x180012394  mov     eax, ebx
0x180012396  and     eax, 9C1h
0x18001239b  or      ecx, eax
0x18001239d  or      ecx, 2
0x1800123a0  mov     [rdi], ecx
0x1800123a2  mov     r8d, edx
0x1800123a5  and     r8d, 4
0x1800123a9  jnz     short loc_1800123BD
0x1800123ab  btr     ecx, 0Ah
0x1800123af  mov     eax, ebx
0x1800123b1  and     eax, 400h
0x1800123b6  or      ecx, eax
0x1800123b8  or      ecx, 4
0x1800123bb  mov     [rdi], ecx
0x1800123bd  mov     eax, edx
0x1800123bf  lock cmpxchg [rsi], ecx
0x1800123c3  jnz     short loc_18001237C
0x1800123c5  test    r8d, r8d
0x1800123c8  jnz     short loc_18001242E
0x1800123ca  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800123d0  test    eax, eax
0x1800123d2  jz      short loc_18001242E
0x1800123d4  lea     r14, SRWLock
0x1800123db  mov     rcx, r14; SRWLock
0x1800123de  call    cs:__imp_AcquireSRWLockExclusive
0x1800123e4  mov     eax, cs:dword_180066AF4
0x1800123ea  mov     [rsp+48h+arg_8], r14
0x1800123ef  test    ebp, ebp
0x1800123f1  jz      short loc_180012420
0x1800123f3  cmp     ebp, eax
0x1800123f5  jnz     short loc_180012420
0x1800123f7  mov     r8d, 10h; unsigned __int64
0x1800123fd  mov     [rsp+48h+var_28], 3
0x180012406  lea     rdx, [rsp+48h+var_28]; void *
0x18001240b  mov     [rsp+48h+var_20], rsi
0x180012410  lea     rcx, qword_180066B18; this
0x180012417  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001241c  test    al, al
0x18001241e  jnz     short loc_180012424
0x180012420  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012424  lea     rcx, [rsp+48h+arg_8]
0x180012429  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001242e  mov     eax, [rdi]
0x180012430  test    al, 2
0x180012432  jnz     short loc_180012443
0x180012434  and     eax, 0FFFFF63Eh
0x180012439  and     ebx, 9C1h
0x18001243f  or      eax, ebx
0x180012441  mov     [rdi], eax
0x180012443  mov     rbx, [rsp+48h+arg_10]
0x180012448  mov     rax, rdi
0x18001244b  mov     rbp, [rsp+48h+arg_18]
0x180012450  add     rsp, 30h
0x180012454  pop     r14
0x180012456  pop     rdi
0x180012457  pop     rsi
0x180012458  retn
```
