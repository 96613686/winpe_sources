# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180015bf4`
- end: `0x180015d2d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b64c`
- `0x18001d060`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015bf4`
- `0x1800176f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015cb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015cb2`

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
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
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
0x180015bf4  mov     [rsp+arg_10], rbx
0x180015bf9  mov     [rsp+arg_18], rbp
0x180015bfe  mov     [rsp+arg_0], rcx
0x180015c03  push    rsi
0x180015c04  push    rdi
0x180015c05  push    r14
0x180015c07  sub     rsp, 30h
0x180015c0b  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180015c12  mov     rdi, rdx
0x180015c15  mov     qword ptr [rdx], 0
0x180015c1c  mov     eax, [rsi]
0x180015c1e  mov     [rdx], eax
0x180015c20  and     eax, 6
0x180015c23  cmp     al, 6
0x180015c25  jz      loc_180015D17
0x180015c2b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015c30  lea     r8, [rsp+48h+arg_0]
0x180015c35  mov     dword ptr [rsp+48h+arg_0], 0
0x180015c3d  lea     rdx, [rsp+48h+arg_8]
0x180015c42  mov     ebp, eax
0x180015c44  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180015c49  mov     eax, [rdi]
0x180015c4b  mov     rbx, [rsp+48h+arg_8]
0x180015c50  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015c55  mov     edx, eax
0x180015c57  mov     [rdi], eax
0x180015c59  mov     ecx, eax
0x180015c5b  jz      short loc_180015C76
0x180015c5d  test    dl, 2
0x180015c60  jnz     short loc_180015C76
0x180015c62  and     ecx, 0FFFFF63Eh
0x180015c68  mov     eax, ebx
0x180015c6a  and     eax, 9C1h
0x180015c6f  or      ecx, eax
0x180015c71  or      ecx, 2
0x180015c74  mov     [rdi], ecx
0x180015c76  mov     r8d, edx
0x180015c79  and     r8d, 4
0x180015c7d  jnz     short loc_180015C91
0x180015c7f  btr     ecx, 0Ah
0x180015c83  mov     eax, ebx
0x180015c85  and     eax, 400h
0x180015c8a  or      ecx, eax
0x180015c8c  or      ecx, 4
0x180015c8f  mov     [rdi], ecx
0x180015c91  mov     eax, edx
0x180015c93  lock cmpxchg [rsi], ecx
0x180015c97  jnz     short loc_180015C50
0x180015c99  test    r8d, r8d
0x180015c9c  jnz     short loc_180015D02
0x180015c9e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015ca4  test    eax, eax
0x180015ca6  jz      short loc_180015D02
0x180015ca8  lea     r14, SRWLock
0x180015caf  mov     rcx, r14; SRWLock
0x180015cb2  call    cs:__imp_AcquireSRWLockExclusive
0x180015cb8  mov     eax, cs:dword_18002EED4
0x180015cbe  mov     [rsp+48h+arg_8], r14
0x180015cc3  test    ebp, ebp
0x180015cc5  jz      short loc_180015CF4
0x180015cc7  cmp     ebp, eax
0x180015cc9  jnz     short loc_180015CF4
0x180015ccb  mov     r8d, 10h; unsigned __int64
0x180015cd1  mov     [rsp+48h+var_28], 3
0x180015cda  lea     rdx, [rsp+48h+var_28]; void *
0x180015cdf  mov     [rsp+48h+var_20], rsi
0x180015ce4  lea     rcx, qword_18002EEF8; this
0x180015ceb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015cf0  test    al, al
0x180015cf2  jnz     short loc_180015CF8
0x180015cf4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015cf8  lea     rcx, [rsp+48h+arg_8]
0x180015cfd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015d02  mov     eax, [rdi]
0x180015d04  test    al, 2
0x180015d06  jnz     short loc_180015D17
0x180015d08  and     eax, 0FFFFF63Eh
0x180015d0d  and     ebx, 9C1h
0x180015d13  or      eax, ebx
0x180015d15  mov     [rdi], eax
0x180015d17  mov     rbx, [rsp+48h+arg_10]
0x180015d1c  mov     rax, rdi
0x180015d1f  mov     rbp, [rsp+48h+arg_18]
0x180015d24  add     rsp, 30h
0x180015d28  pop     r14
0x180015d2a  pop     rdi
0x180015d2b  pop     rsi
0x180015d2c  retn
```
