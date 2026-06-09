# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000c288`
- end: `0x14000c3c1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010138`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000c288`
- `0x14000ca98`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c346`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c346`

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
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000c288  mov     [rsp+arg_10], rbx
0x14000c28d  mov     [rsp+arg_18], rbp
0x14000c292  mov     [rsp+arg_0], rcx
0x14000c297  push    rsi
0x14000c298  push    rdi
0x14000c299  push    r14
0x14000c29b  sub     rsp, 30h
0x14000c29f  mov     rsi, cs:Feature_ValLabTest__descriptor
0x14000c2a6  mov     rdi, rdx
0x14000c2a9  mov     qword ptr [rdx], 0
0x14000c2b0  mov     eax, [rsi]
0x14000c2b2  mov     [rdx], eax
0x14000c2b4  and     eax, 6
0x14000c2b7  cmp     al, 6
0x14000c2b9  jz      loc_14000C3AB
0x14000c2bf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000c2c4  lea     r8, [rsp+48h+arg_0]
0x14000c2c9  mov     dword ptr [rsp+48h+arg_0], 0
0x14000c2d1  lea     rdx, [rsp+48h+arg_8]
0x14000c2d6  mov     ebp, eax
0x14000c2d8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x14000c2dd  mov     eax, [rdi]
0x14000c2df  mov     rbx, [rsp+48h+arg_8]
0x14000c2e4  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000c2e9  mov     edx, eax
0x14000c2eb  mov     [rdi], eax
0x14000c2ed  mov     ecx, eax
0x14000c2ef  jz      short loc_14000C30A
0x14000c2f1  test    dl, 2
0x14000c2f4  jnz     short loc_14000C30A
0x14000c2f6  and     ecx, 0FFFFF63Eh
0x14000c2fc  mov     eax, ebx
0x14000c2fe  and     eax, 9C1h
0x14000c303  or      ecx, eax
0x14000c305  or      ecx, 2
0x14000c308  mov     [rdi], ecx
0x14000c30a  mov     r8d, edx
0x14000c30d  and     r8d, 4
0x14000c311  jnz     short loc_14000C325
0x14000c313  btr     ecx, 0Ah
0x14000c317  mov     eax, ebx
0x14000c319  and     eax, 400h
0x14000c31e  or      ecx, eax
0x14000c320  or      ecx, 4
0x14000c323  mov     [rdi], ecx
0x14000c325  mov     eax, edx
0x14000c327  lock cmpxchg [rsi], ecx
0x14000c32b  jnz     short loc_14000C2E4
0x14000c32d  test    r8d, r8d
0x14000c330  jnz     short loc_14000C396
0x14000c332  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000c338  test    eax, eax
0x14000c33a  jz      short loc_14000C396
0x14000c33c  lea     r14, stru_14002BCD0
0x14000c343  mov     rcx, r14; SRWLock
0x14000c346  call    cs:__imp_AcquireSRWLockExclusive
0x14000c34c  mov     eax, cs:dword_14002BCE4
0x14000c352  mov     [rsp+48h+arg_8], r14
0x14000c357  test    ebp, ebp
0x14000c359  jz      short loc_14000C388
0x14000c35b  cmp     ebp, eax
0x14000c35d  jnz     short loc_14000C388
0x14000c35f  mov     r8d, 10h; unsigned __int64
0x14000c365  mov     [rsp+48h+var_28], 3
0x14000c36e  lea     rdx, [rsp+48h+var_28]; void *
0x14000c373  mov     [rsp+48h+var_20], rsi
0x14000c378  lea     rcx, qword_14002BD08; this
0x14000c37f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c384  test    al, al
0x14000c386  jnz     short loc_14000C38C
0x14000c388  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000c38c  lea     rcx, [rsp+48h+arg_8]
0x14000c391  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c396  mov     eax, [rdi]
0x14000c398  test    al, 2
0x14000c39a  jnz     short loc_14000C3AB
0x14000c39c  and     eax, 0FFFFF63Eh
0x14000c3a1  and     ebx, 9C1h
0x14000c3a7  or      eax, ebx
0x14000c3a9  mov     [rdi], eax
0x14000c3ab  mov     rbx, [rsp+48h+arg_10]
0x14000c3b0  mov     rax, rdi
0x14000c3b3  mov     rbp, [rsp+48h+arg_18]
0x14000c3b8  add     rsp, 30h
0x14000c3bc  pop     r14
0x14000c3be  pop     rdi
0x14000c3bf  pop     rsi
0x14000c3c0  retn
```
