# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x14000bec8`
- end: `0x14000c001`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ffa0`
- `0x140011bdc`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000bec8`
- `0x14000c7e4`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bf86`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bf86`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x14000bec8  mov     [rsp+arg_10], rbx
0x14000becd  mov     [rsp+arg_18], rbp
0x14000bed2  mov     [rsp+arg_0], rcx
0x14000bed7  push    rsi
0x14000bed8  push    rdi
0x14000bed9  push    r14
0x14000bedb  sub     rsp, 30h
0x14000bedf  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x14000bee6  mov     rdi, rdx
0x14000bee9  mov     qword ptr [rdx], 0
0x14000bef0  mov     eax, [rsi]
0x14000bef2  mov     [rdx], eax
0x14000bef4  and     eax, 6
0x14000bef7  cmp     al, 6
0x14000bef9  jz      loc_14000BFEB
0x14000beff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000bf04  lea     r8, [rsp+48h+arg_0]
0x14000bf09  mov     dword ptr [rsp+48h+arg_0], 0
0x14000bf11  lea     rdx, [rsp+48h+arg_8]
0x14000bf16  mov     ebp, eax
0x14000bf18  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x14000bf1d  mov     eax, [rdi]
0x14000bf1f  mov     rbx, [rsp+48h+arg_8]
0x14000bf24  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000bf29  mov     edx, eax
0x14000bf2b  mov     [rdi], eax
0x14000bf2d  mov     ecx, eax
0x14000bf2f  jz      short loc_14000BF4A
0x14000bf31  test    dl, 2
0x14000bf34  jnz     short loc_14000BF4A
0x14000bf36  and     ecx, 0FFFFF63Eh
0x14000bf3c  mov     eax, ebx
0x14000bf3e  and     eax, 9C1h
0x14000bf43  or      ecx, eax
0x14000bf45  or      ecx, 2
0x14000bf48  mov     [rdi], ecx
0x14000bf4a  mov     r8d, edx
0x14000bf4d  and     r8d, 4
0x14000bf51  jnz     short loc_14000BF65
0x14000bf53  btr     ecx, 0Ah
0x14000bf57  mov     eax, ebx
0x14000bf59  and     eax, 400h
0x14000bf5e  or      ecx, eax
0x14000bf60  or      ecx, 4
0x14000bf63  mov     [rdi], ecx
0x14000bf65  mov     eax, edx
0x14000bf67  lock cmpxchg [rsi], ecx
0x14000bf6b  jnz     short loc_14000BF24
0x14000bf6d  test    r8d, r8d
0x14000bf70  jnz     short loc_14000BFD6
0x14000bf72  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000bf78  test    eax, eax
0x14000bf7a  jz      short loc_14000BFD6
0x14000bf7c  lea     r14, stru_14002BCD0
0x14000bf83  mov     rcx, r14; SRWLock
0x14000bf86  call    cs:__imp_AcquireSRWLockExclusive
0x14000bf8c  mov     eax, cs:dword_14002BCE4
0x14000bf92  mov     [rsp+48h+arg_8], r14
0x14000bf97  test    ebp, ebp
0x14000bf99  jz      short loc_14000BFC8
0x14000bf9b  cmp     ebp, eax
0x14000bf9d  jnz     short loc_14000BFC8
0x14000bf9f  mov     r8d, 10h; unsigned __int64
0x14000bfa5  mov     [rsp+48h+var_28], 3
0x14000bfae  lea     rdx, [rsp+48h+var_28]; void *
0x14000bfb3  mov     [rsp+48h+var_20], rsi
0x14000bfb8  lea     rcx, qword_14002BD08; this
0x14000bfbf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000bfc4  test    al, al
0x14000bfc6  jnz     short loc_14000BFCC
0x14000bfc8  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000bfcc  lea     rcx, [rsp+48h+arg_8]
0x14000bfd1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000bfd6  mov     eax, [rdi]
0x14000bfd8  test    al, 2
0x14000bfda  jnz     short loc_14000BFEB
0x14000bfdc  and     eax, 0FFFFF63Eh
0x14000bfe1  and     ebx, 9C1h
0x14000bfe7  or      eax, ebx
0x14000bfe9  mov     [rdi], eax
0x14000bfeb  mov     rbx, [rsp+48h+arg_10]
0x14000bff0  mov     rax, rdi
0x14000bff3  mov     rbp, [rsp+48h+arg_18]
0x14000bff8  add     rsp, 30h
0x14000bffc  pop     r14
0x14000bffe  pop     rdi
0x14000bfff  pop     rsi
0x14000c000  retn
```
