# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180016f74`
- end: `0x1800170b4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d208`
- `0x180020f9c`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x180016f74`
- `0x1800174c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017032`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017032`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180016f74  mov     [rsp+arg_10], rbx
0x180016f79  mov     [rsp+arg_18], rbp
0x180016f7e  mov     [rsp+arg_0], rcx
0x180016f83  push    rsi
0x180016f84  push    rdi
0x180016f85  push    r14
0x180016f87  sub     rsp, 30h
0x180016f8b  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180016f92  mov     rdi, rdx
0x180016f95  mov     qword ptr [rdx], 0
0x180016f9c  mov     eax, [rsi]
0x180016f9e  mov     [rdx], eax
0x180016fa0  and     eax, 6
0x180016fa3  cmp     al, 6
0x180016fa5  jz      loc_18001709D
0x180016fab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016fb0  lea     r8, [rsp+48h+arg_0]
0x180016fb5  mov     dword ptr [rsp+48h+arg_0], 0
0x180016fbd  lea     rdx, [rsp+48h+arg_8]
0x180016fc2  mov     ebp, eax
0x180016fc4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180016fc9  mov     eax, [rdi]
0x180016fcb  mov     rbx, [rsp+48h+arg_8]
0x180016fd0  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016fd5  mov     edx, eax
0x180016fd7  mov     [rdi], eax
0x180016fd9  mov     ecx, eax
0x180016fdb  jz      short loc_180016FF6
0x180016fdd  test    dl, 2
0x180016fe0  jnz     short loc_180016FF6
0x180016fe2  and     ecx, 0FFFFF63Eh
0x180016fe8  mov     eax, ebx
0x180016fea  and     eax, 9C1h
0x180016fef  or      ecx, eax
0x180016ff1  or      ecx, 2
0x180016ff4  mov     [rdi], ecx
0x180016ff6  mov     r8d, edx
0x180016ff9  and     r8d, 4
0x180016ffd  jnz     short loc_180017011
0x180016fff  btr     ecx, 0Ah
0x180017003  mov     eax, ebx
0x180017005  and     eax, 400h
0x18001700a  or      ecx, eax
0x18001700c  or      ecx, 4
0x18001700f  mov     [rdi], ecx
0x180017011  mov     eax, edx
0x180017013  lock cmpxchg [rsi], ecx
0x180017017  jnz     short loc_180016FD0
0x180017019  test    r8d, r8d
0x18001701c  jnz     short loc_180017088
0x18001701e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017024  test    eax, eax
0x180017026  jz      short loc_180017088
0x180017028  lea     r14, SRWLock
0x18001702f  mov     rcx, r14; SRWLock
0x180017032  call    cs:__imp_AcquireSRWLockExclusive
0x180017039  nop     dword ptr [rax+rax+00h]
0x18001703e  mov     eax, cs:dword_1800578F4
0x180017044  mov     [rsp+48h+arg_8], r14
0x180017049  test    ebp, ebp
0x18001704b  jz      short loc_18001707A
0x18001704d  cmp     ebp, eax
0x18001704f  jnz     short loc_18001707A
0x180017051  mov     r8d, 10h; unsigned __int64
0x180017057  mov     [rsp+48h+var_28], 3
0x180017060  lea     rdx, [rsp+48h+var_28]; void *
0x180017065  mov     [rsp+48h+var_20], rsi
0x18001706a  lea     rcx, qword_180057928; this
0x180017071  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017076  test    al, al
0x180017078  jnz     short loc_18001707E
0x18001707a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001707e  lea     rcx, [rsp+48h+arg_8]
0x180017083  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017088  mov     eax, [rdi]
0x18001708a  test    al, 2
0x18001708c  jnz     short loc_18001709D
0x18001708e  and     eax, 0FFFFF63Eh
0x180017093  and     ebx, 9C1h
0x180017099  or      eax, ebx
0x18001709b  mov     [rdi], eax
0x18001709d  mov     rbx, [rsp+48h+arg_10]
0x1800170a2  mov     rax, rdi
0x1800170a5  mov     rbp, [rsp+48h+arg_18]
0x1800170aa  add     rsp, 30h
0x1800170ae  pop     r14
0x1800170b0  pop     rdi
0x1800170b1  pop     rsi
0x1800170b2  retn
```
