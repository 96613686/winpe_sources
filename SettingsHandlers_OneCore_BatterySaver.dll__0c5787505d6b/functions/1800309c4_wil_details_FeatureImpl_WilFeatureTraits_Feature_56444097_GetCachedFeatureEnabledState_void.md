# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56444097>::GetCachedFeatureEnabledState(void)

- ea: `0x1800309c4`
- end: `0x180030afd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56444097@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800311c8`
- `0x1800317ec`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x1800309c4`
- `0x180030d14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030a82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030a82`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56444097>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56444097__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56444097__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56444097>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56444097__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_56444097__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_56444097__descriptor, 0xFFFFFFFB);
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
0x1800309c4  mov     [rsp+arg_10], rbx
0x1800309c9  mov     [rsp+arg_18], rbp
0x1800309ce  mov     [rsp+arg_0], rcx
0x1800309d3  push    rsi
0x1800309d4  push    rdi
0x1800309d5  push    r14
0x1800309d7  sub     rsp, 30h
0x1800309db  mov     rsi, cs:Feature_56444097__descriptor
0x1800309e2  mov     rdi, rdx
0x1800309e5  mov     qword ptr [rdx], 0
0x1800309ec  mov     eax, [rsi]
0x1800309ee  mov     [rdx], eax
0x1800309f0  and     eax, 6
0x1800309f3  cmp     al, 6
0x1800309f5  jz      loc_180030AE7
0x1800309fb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180030a00  lea     r8, [rsp+48h+arg_0]
0x180030a05  mov     dword ptr [rsp+48h+arg_0], 0
0x180030a0d  lea     rdx, [rsp+48h+arg_8]
0x180030a12  mov     ebp, eax
0x180030a14  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56444097@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56444097>::GetCurrentFeatureEnabledState(int *)
0x180030a19  mov     eax, [rdi]
0x180030a1b  mov     rbx, [rsp+48h+arg_8]
0x180030a20  cmp     dword ptr [rsp+48h+arg_0], 0
0x180030a25  mov     edx, eax
0x180030a27  mov     [rdi], eax
0x180030a29  mov     ecx, eax
0x180030a2b  jz      short loc_180030A46
0x180030a2d  test    dl, 2
0x180030a30  jnz     short loc_180030A46
0x180030a32  and     ecx, 0FFFFF63Eh
0x180030a38  mov     eax, ebx
0x180030a3a  and     eax, 9C1h
0x180030a3f  or      ecx, eax
0x180030a41  or      ecx, 2
0x180030a44  mov     [rdi], ecx
0x180030a46  mov     r8d, edx
0x180030a49  and     r8d, 4
0x180030a4d  jnz     short loc_180030A61
0x180030a4f  btr     ecx, 0Ah
0x180030a53  mov     eax, ebx
0x180030a55  and     eax, 400h
0x180030a5a  or      ecx, eax
0x180030a5c  or      ecx, 4
0x180030a5f  mov     [rdi], ecx
0x180030a61  mov     eax, edx
0x180030a63  lock cmpxchg [rsi], ecx
0x180030a67  jnz     short loc_180030A20
0x180030a69  test    r8d, r8d
0x180030a6c  jnz     short loc_180030AD2
0x180030a6e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180030a74  test    eax, eax
0x180030a76  jz      short loc_180030AD2
0x180030a78  lea     r14, SRWLock
0x180030a7f  mov     rcx, r14; SRWLock
0x180030a82  call    cs:__imp_AcquireSRWLockExclusive
0x180030a88  mov     eax, cs:dword_180066AF4
0x180030a8e  mov     [rsp+48h+arg_8], r14
0x180030a93  test    ebp, ebp
0x180030a95  jz      short loc_180030AC4
0x180030a97  cmp     ebp, eax
0x180030a99  jnz     short loc_180030AC4
0x180030a9b  mov     r8d, 10h; unsigned __int64
0x180030aa1  mov     [rsp+48h+var_28], 3
0x180030aaa  lea     rdx, [rsp+48h+var_28]; void *
0x180030aaf  mov     [rsp+48h+var_20], rsi
0x180030ab4  lea     rcx, qword_180066B18; this
0x180030abb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180030ac0  test    al, al
0x180030ac2  jnz     short loc_180030AC8
0x180030ac4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180030ac8  lea     rcx, [rsp+48h+arg_8]
0x180030acd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030ad2  mov     eax, [rdi]
0x180030ad4  test    al, 2
0x180030ad6  jnz     short loc_180030AE7
0x180030ad8  and     eax, 0FFFFF63Eh
0x180030add  and     ebx, 9C1h
0x180030ae3  or      eax, ebx
0x180030ae5  mov     [rdi], eax
0x180030ae7  mov     rbx, [rsp+48h+arg_10]
0x180030aec  mov     rax, rdi
0x180030aef  mov     rbp, [rsp+48h+arg_18]
0x180030af4  add     rsp, 30h
0x180030af8  pop     r14
0x180030afa  pop     rdi
0x180030afb  pop     rsi
0x180030afc  retn
```
