# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x14000c008`
- end: `0x14000c141`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010028`
- `0x140011c18`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000c008`
- `0x14000c8d0`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c0c6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c0c6`

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
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_TestLoc1Perf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000c008  mov     [rsp+arg_10], rbx
0x14000c00d  mov     [rsp+arg_18], rbp
0x14000c012  mov     [rsp+arg_0], rcx
0x14000c017  push    rsi
0x14000c018  push    rdi
0x14000c019  push    r14
0x14000c01b  sub     rsp, 30h
0x14000c01f  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x14000c026  mov     rdi, rdx
0x14000c029  mov     qword ptr [rdx], 0
0x14000c030  mov     eax, [rsi]
0x14000c032  mov     [rdx], eax
0x14000c034  and     eax, 6
0x14000c037  cmp     al, 6
0x14000c039  jz      loc_14000C12B
0x14000c03f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000c044  lea     r8, [rsp+48h+arg_0]
0x14000c049  mov     dword ptr [rsp+48h+arg_0], 0
0x14000c051  lea     rdx, [rsp+48h+arg_8]
0x14000c056  mov     ebp, eax
0x14000c058  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x14000c05d  mov     eax, [rdi]
0x14000c05f  mov     rbx, [rsp+48h+arg_8]
0x14000c064  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000c069  mov     edx, eax
0x14000c06b  mov     [rdi], eax
0x14000c06d  mov     ecx, eax
0x14000c06f  jz      short loc_14000C08A
0x14000c071  test    dl, 2
0x14000c074  jnz     short loc_14000C08A
0x14000c076  and     ecx, 0FFFFF63Eh
0x14000c07c  mov     eax, ebx
0x14000c07e  and     eax, 9C1h
0x14000c083  or      ecx, eax
0x14000c085  or      ecx, 2
0x14000c088  mov     [rdi], ecx
0x14000c08a  mov     r8d, edx
0x14000c08d  and     r8d, 4
0x14000c091  jnz     short loc_14000C0A5
0x14000c093  btr     ecx, 0Ah
0x14000c097  mov     eax, ebx
0x14000c099  and     eax, 400h
0x14000c09e  or      ecx, eax
0x14000c0a0  or      ecx, 4
0x14000c0a3  mov     [rdi], ecx
0x14000c0a5  mov     eax, edx
0x14000c0a7  lock cmpxchg [rsi], ecx
0x14000c0ab  jnz     short loc_14000C064
0x14000c0ad  test    r8d, r8d
0x14000c0b0  jnz     short loc_14000C116
0x14000c0b2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000c0b8  test    eax, eax
0x14000c0ba  jz      short loc_14000C116
0x14000c0bc  lea     r14, stru_14002BCD0
0x14000c0c3  mov     rcx, r14; SRWLock
0x14000c0c6  call    cs:__imp_AcquireSRWLockExclusive
0x14000c0cc  mov     eax, cs:dword_14002BCE4
0x14000c0d2  mov     [rsp+48h+arg_8], r14
0x14000c0d7  test    ebp, ebp
0x14000c0d9  jz      short loc_14000C108
0x14000c0db  cmp     ebp, eax
0x14000c0dd  jnz     short loc_14000C108
0x14000c0df  mov     r8d, 10h; unsigned __int64
0x14000c0e5  mov     [rsp+48h+var_28], 3
0x14000c0ee  lea     rdx, [rsp+48h+var_28]; void *
0x14000c0f3  mov     [rsp+48h+var_20], rsi
0x14000c0f8  lea     rcx, qword_14002BD08; this
0x14000c0ff  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c104  test    al, al
0x14000c106  jnz     short loc_14000C10C
0x14000c108  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000c10c  lea     rcx, [rsp+48h+arg_8]
0x14000c111  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c116  mov     eax, [rdi]
0x14000c118  test    al, 2
0x14000c11a  jnz     short loc_14000C12B
0x14000c11c  and     eax, 0FFFFF63Eh
0x14000c121  and     ebx, 9C1h
0x14000c127  or      eax, ebx
0x14000c129  mov     [rdi], eax
0x14000c12b  mov     rbx, [rsp+48h+arg_10]
0x14000c130  mov     rax, rdi
0x14000c133  mov     rbp, [rsp+48h+arg_18]
0x14000c138  add     rsp, 30h
0x14000c13c  pop     r14
0x14000c13e  pop     rdi
0x14000c13f  pop     rsi
0x14000c140  retn
```
