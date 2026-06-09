# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCachedFeatureEnabledState(void)

- ea: `0x180014fc4`
- end: `0x1800150fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b110`
- `0x18001cf70`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180014fc4`
- `0x18001709c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015082`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015082`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID45522024__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID45522024__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID45522024__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_ID45522024__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID45522024__descriptor, 0xFFFFFFFB);
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
0x180014fc4  mov     [rsp+arg_10], rbx
0x180014fc9  mov     [rsp+arg_18], rbp
0x180014fce  mov     [rsp+arg_0], rcx
0x180014fd3  push    rsi
0x180014fd4  push    rdi
0x180014fd5  push    r14
0x180014fd7  sub     rsp, 30h
0x180014fdb  mov     rsi, cs:Feature_ID45522024__descriptor
0x180014fe2  mov     rdi, rdx
0x180014fe5  mov     qword ptr [rdx], 0
0x180014fec  mov     eax, [rsi]
0x180014fee  mov     [rdx], eax
0x180014ff0  and     eax, 6
0x180014ff3  cmp     al, 6
0x180014ff5  jz      loc_1800150E7
0x180014ffb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015000  lea     r8, [rsp+48h+arg_0]
0x180015005  mov     dword ptr [rsp+48h+arg_0], 0
0x18001500d  lea     rdx, [rsp+48h+arg_8]
0x180015012  mov     ebp, eax
0x180015014  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::GetCurrentFeatureEnabledState(int *)
0x180015019  mov     eax, [rdi]
0x18001501b  mov     rbx, [rsp+48h+arg_8]
0x180015020  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015025  mov     edx, eax
0x180015027  mov     [rdi], eax
0x180015029  mov     ecx, eax
0x18001502b  jz      short loc_180015046
0x18001502d  test    dl, 2
0x180015030  jnz     short loc_180015046
0x180015032  and     ecx, 0FFFFF63Eh
0x180015038  mov     eax, ebx
0x18001503a  and     eax, 9C1h
0x18001503f  or      ecx, eax
0x180015041  or      ecx, 2
0x180015044  mov     [rdi], ecx
0x180015046  mov     r8d, edx
0x180015049  and     r8d, 4
0x18001504d  jnz     short loc_180015061
0x18001504f  btr     ecx, 0Ah
0x180015053  mov     eax, ebx
0x180015055  and     eax, 400h
0x18001505a  or      ecx, eax
0x18001505c  or      ecx, 4
0x18001505f  mov     [rdi], ecx
0x180015061  mov     eax, edx
0x180015063  lock cmpxchg [rsi], ecx
0x180015067  jnz     short loc_180015020
0x180015069  test    r8d, r8d
0x18001506c  jnz     short loc_1800150D2
0x18001506e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015074  test    eax, eax
0x180015076  jz      short loc_1800150D2
0x180015078  lea     r14, SRWLock
0x18001507f  mov     rcx, r14; SRWLock
0x180015082  call    cs:__imp_AcquireSRWLockExclusive
0x180015088  mov     eax, cs:dword_18002EED4
0x18001508e  mov     [rsp+48h+arg_8], r14
0x180015093  test    ebp, ebp
0x180015095  jz      short loc_1800150C4
0x180015097  cmp     ebp, eax
0x180015099  jnz     short loc_1800150C4
0x18001509b  mov     r8d, 10h; unsigned __int64
0x1800150a1  mov     [rsp+48h+var_28], 3
0x1800150aa  lea     rdx, [rsp+48h+var_28]; void *
0x1800150af  mov     [rsp+48h+var_20], rsi
0x1800150b4  lea     rcx, qword_18002EEF8; this
0x1800150bb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800150c0  test    al, al
0x1800150c2  jnz     short loc_1800150C8
0x1800150c4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800150c8  lea     rcx, [rsp+48h+arg_8]
0x1800150cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800150d2  mov     eax, [rdi]
0x1800150d4  test    al, 2
0x1800150d6  jnz     short loc_1800150E7
0x1800150d8  and     eax, 0FFFFF63Eh
0x1800150dd  and     ebx, 9C1h
0x1800150e3  or      eax, ebx
0x1800150e5  mov     [rdi], eax
0x1800150e7  mov     rbx, [rsp+48h+arg_10]
0x1800150ec  mov     rax, rdi
0x1800150ef  mov     rbp, [rsp+48h+arg_18]
0x1800150f4  add     rsp, 30h
0x1800150f8  pop     r14
0x1800150fa  pop     rdi
0x1800150fb  pop     rsi
0x1800150fc  retn
```
