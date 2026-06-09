# wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCachedFeatureEnabledState(void)

- ea: `0x180012c0c`
- end: `0x180012d4c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_4920_0542@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015250`
- `0x180015a48`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180012c0c`
- `0x180013dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012cca`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_4920_0542__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_4920_0542__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_4920_0542__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_4920_0542__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_4920_0542__descriptor, 0xFFFFFFFB);
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
0x180012c0c  mov     [rsp+arg_10], rbx
0x180012c11  mov     [rsp+arg_18], rbp
0x180012c16  mov     [rsp+arg_0], rcx
0x180012c1b  push    rsi
0x180012c1c  push    rdi
0x180012c1d  push    r14
0x180012c1f  sub     rsp, 30h
0x180012c23  mov     rsi, cs:Feature_4920_0542__descriptor
0x180012c2a  mov     rdi, rdx
0x180012c2d  mov     qword ptr [rdx], 0
0x180012c34  mov     eax, [rsi]
0x180012c36  mov     [rdx], eax
0x180012c38  and     eax, 6
0x180012c3b  cmp     al, 6
0x180012c3d  jz      loc_180012D35
0x180012c43  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012c48  lea     r8, [rsp+48h+arg_0]
0x180012c4d  mov     dword ptr [rsp+48h+arg_0], 0
0x180012c55  lea     rdx, [rsp+48h+arg_8]
0x180012c5a  mov     ebp, eax
0x180012c5c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_4920_0542@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCurrentFeatureEnabledState(int *)
0x180012c61  mov     eax, [rdi]
0x180012c63  mov     rbx, [rsp+48h+arg_8]
0x180012c68  cmp     dword ptr [rsp+48h+arg_0], 0
0x180012c6d  mov     edx, eax
0x180012c6f  mov     [rdi], eax
0x180012c71  mov     ecx, eax
0x180012c73  jz      short loc_180012C8E
0x180012c75  test    dl, 2
0x180012c78  jnz     short loc_180012C8E
0x180012c7a  and     ecx, 0FFFFF63Eh
0x180012c80  mov     eax, ebx
0x180012c82  and     eax, 9C1h
0x180012c87  or      ecx, eax
0x180012c89  or      ecx, 2
0x180012c8c  mov     [rdi], ecx
0x180012c8e  mov     r8d, edx
0x180012c91  and     r8d, 4
0x180012c95  jnz     short loc_180012CA9
0x180012c97  btr     ecx, 0Ah
0x180012c9b  mov     eax, ebx
0x180012c9d  and     eax, 400h
0x180012ca2  or      ecx, eax
0x180012ca4  or      ecx, 4
0x180012ca7  mov     [rdi], ecx
0x180012ca9  mov     eax, edx
0x180012cab  lock cmpxchg [rsi], ecx
0x180012caf  jnz     short loc_180012C68
0x180012cb1  test    r8d, r8d
0x180012cb4  jnz     short loc_180012D20
0x180012cb6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012cbc  test    eax, eax
0x180012cbe  jz      short loc_180012D20
0x180012cc0  lea     r14, stru_180029CA8
0x180012cc7  mov     rcx, r14; SRWLock
0x180012cca  call    cs:__imp_AcquireSRWLockExclusive
0x180012cd1  nop     dword ptr [rax+rax+00h]
0x180012cd6  mov     eax, cs:dword_180029CBC
0x180012cdc  mov     [rsp+48h+arg_8], r14
0x180012ce1  test    ebp, ebp
0x180012ce3  jz      short loc_180012D12
0x180012ce5  cmp     ebp, eax
0x180012ce7  jnz     short loc_180012D12
0x180012ce9  mov     r8d, 10h; unsigned __int64
0x180012cef  mov     [rsp+48h+var_28], 3
0x180012cf8  lea     rdx, [rsp+48h+var_28]; void *
0x180012cfd  mov     [rsp+48h+var_20], rsi
0x180012d02  lea     rcx, qword_180029CF0; this
0x180012d09  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012d0e  test    al, al
0x180012d10  jnz     short loc_180012D16
0x180012d12  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012d16  lea     rcx, [rsp+48h+arg_8]
0x180012d1b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012d20  mov     eax, [rdi]
0x180012d22  test    al, 2
0x180012d24  jnz     short loc_180012D35
0x180012d26  and     eax, 0FFFFF63Eh
0x180012d2b  and     ebx, 9C1h
0x180012d31  or      eax, ebx
0x180012d33  mov     [rdi], eax
0x180012d35  mov     rbx, [rsp+48h+arg_10]
0x180012d3a  mov     rax, rdi
0x180012d3d  mov     rbp, [rsp+48h+arg_18]
0x180012d42  add     rsp, 30h
0x180012d46  pop     r14
0x180012d48  pop     rdi
0x180012d49  pop     rsi
0x180012d4a  retn
```
