# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x14000c148`
- end: `0x14000c281`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400100b0`
- `0x140011c54`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000c148`
- `0x14000c9bc`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c206`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000c206`

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
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000c148  mov     [rsp+arg_10], rbx
0x14000c14d  mov     [rsp+arg_18], rbp
0x14000c152  mov     [rsp+arg_0], rcx
0x14000c157  push    rsi
0x14000c158  push    rdi
0x14000c159  push    r14
0x14000c15b  sub     rsp, 30h
0x14000c15f  mov     rsi, cs:Feature_ValAccTest__descriptor
0x14000c166  mov     rdi, rdx
0x14000c169  mov     qword ptr [rdx], 0
0x14000c170  mov     eax, [rsi]
0x14000c172  mov     [rdx], eax
0x14000c174  and     eax, 6
0x14000c177  cmp     al, 6
0x14000c179  jz      loc_14000C26B
0x14000c17f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000c184  lea     r8, [rsp+48h+arg_0]
0x14000c189  mov     dword ptr [rsp+48h+arg_0], 0
0x14000c191  lea     rdx, [rsp+48h+arg_8]
0x14000c196  mov     ebp, eax
0x14000c198  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x14000c19d  mov     eax, [rdi]
0x14000c19f  mov     rbx, [rsp+48h+arg_8]
0x14000c1a4  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000c1a9  mov     edx, eax
0x14000c1ab  mov     [rdi], eax
0x14000c1ad  mov     ecx, eax
0x14000c1af  jz      short loc_14000C1CA
0x14000c1b1  test    dl, 2
0x14000c1b4  jnz     short loc_14000C1CA
0x14000c1b6  and     ecx, 0FFFFF63Eh
0x14000c1bc  mov     eax, ebx
0x14000c1be  and     eax, 9C1h
0x14000c1c3  or      ecx, eax
0x14000c1c5  or      ecx, 2
0x14000c1c8  mov     [rdi], ecx
0x14000c1ca  mov     r8d, edx
0x14000c1cd  and     r8d, 4
0x14000c1d1  jnz     short loc_14000C1E5
0x14000c1d3  btr     ecx, 0Ah
0x14000c1d7  mov     eax, ebx
0x14000c1d9  and     eax, 400h
0x14000c1de  or      ecx, eax
0x14000c1e0  or      ecx, 4
0x14000c1e3  mov     [rdi], ecx
0x14000c1e5  mov     eax, edx
0x14000c1e7  lock cmpxchg [rsi], ecx
0x14000c1eb  jnz     short loc_14000C1A4
0x14000c1ed  test    r8d, r8d
0x14000c1f0  jnz     short loc_14000C256
0x14000c1f2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000c1f8  test    eax, eax
0x14000c1fa  jz      short loc_14000C256
0x14000c1fc  lea     r14, stru_14002BCD0
0x14000c203  mov     rcx, r14; SRWLock
0x14000c206  call    cs:__imp_AcquireSRWLockExclusive
0x14000c20c  mov     eax, cs:dword_14002BCE4
0x14000c212  mov     [rsp+48h+arg_8], r14
0x14000c217  test    ebp, ebp
0x14000c219  jz      short loc_14000C248
0x14000c21b  cmp     ebp, eax
0x14000c21d  jnz     short loc_14000C248
0x14000c21f  mov     r8d, 10h; unsigned __int64
0x14000c225  mov     [rsp+48h+var_28], 3
0x14000c22e  lea     rdx, [rsp+48h+var_28]; void *
0x14000c233  mov     [rsp+48h+var_20], rsi
0x14000c238  lea     rcx, qword_14002BD08; this
0x14000c23f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000c244  test    al, al
0x14000c246  jnz     short loc_14000C24C
0x14000c248  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000c24c  lea     rcx, [rsp+48h+arg_8]
0x14000c251  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000c256  mov     eax, [rdi]
0x14000c258  test    al, 2
0x14000c25a  jnz     short loc_14000C26B
0x14000c25c  and     eax, 0FFFFF63Eh
0x14000c261  and     ebx, 9C1h
0x14000c267  or      eax, ebx
0x14000c269  mov     [rdi], eax
0x14000c26b  mov     rbx, [rsp+48h+arg_10]
0x14000c270  mov     rax, rdi
0x14000c273  mov     rbp, [rsp+48h+arg_18]
0x14000c278  add     rsp, 30h
0x14000c27c  pop     r14
0x14000c27e  pop     rdi
0x14000c27f  pop     rsi
0x14000c280  retn
```
