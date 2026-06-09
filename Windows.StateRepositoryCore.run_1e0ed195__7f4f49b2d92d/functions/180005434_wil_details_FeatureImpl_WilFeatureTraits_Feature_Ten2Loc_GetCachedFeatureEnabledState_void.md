# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180005434`
- end: `0x18000555d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e38`
- `0x18000a970`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180005434`
- `0x180005f98`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
    v7 = *(_DWORD *)a2;
    v8 = v16;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Ten2Loc__descriptor, 0xFFFFFFFB);
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
0x180005434  mov     [rsp+arg_10], rbx
0x180005439  mov     [rsp+arg_0], rcx
0x18000543e  push    rbp
0x18000543f  push    rsi
0x180005440  push    rdi
0x180005441  sub     rsp, 30h
0x180005445  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000544c  mov     rdi, rdx
0x18000544f  mov     qword ptr [rdx], 0
0x180005456  mov     eax, [rsi]
0x180005458  mov     [rdx], eax
0x18000545a  and     eax, 6
0x18000545d  cmp     al, 6
0x18000545f  jz      loc_18000554D
0x180005465  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000546a  lea     r8, [rsp+48h+arg_0]
0x18000546f  mov     dword ptr [rsp+48h+arg_0], 0
0x180005477  lea     rdx, [rsp+48h+arg_8]
0x18000547c  mov     ebp, eax
0x18000547e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180005483  mov     eax, [rdi]
0x180005485  mov     rbx, [rsp+48h+arg_8]
0x18000548a  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000548f  mov     edx, eax
0x180005491  mov     [rdi], eax
0x180005493  mov     ecx, eax
0x180005495  jz      short loc_1800054B0
0x180005497  test    dl, 2
0x18000549a  jnz     short loc_1800054B0
0x18000549c  and     ecx, 0FFFFF63Eh
0x1800054a2  mov     eax, ebx
0x1800054a4  and     eax, 9C1h
0x1800054a9  or      ecx, eax
0x1800054ab  or      ecx, 2
0x1800054ae  mov     [rdi], ecx
0x1800054b0  mov     r8d, edx
0x1800054b3  and     r8d, 4
0x1800054b7  jnz     short loc_1800054CB
0x1800054b9  btr     ecx, 0Ah
0x1800054bd  mov     eax, ebx
0x1800054bf  and     eax, 400h
0x1800054c4  or      ecx, eax
0x1800054c6  or      ecx, 4
0x1800054c9  mov     [rdi], ecx
0x1800054cb  mov     eax, edx
0x1800054cd  lock cmpxchg [rsi], ecx
0x1800054d1  jnz     short loc_18000548A
0x1800054d3  test    r8d, r8d
0x1800054d6  jnz     short loc_180005538
0x1800054d8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800054de  test    eax, eax
0x1800054e0  jz      short loc_180005538
0x1800054e2  lea     rdx, qword_180018220
0x1800054e9  lea     rcx, [rsp+48h+arg_8]
0x1800054ee  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800054f3  mov     eax, cs:dword_180018234
0x1800054f9  test    ebp, ebp
0x1800054fb  jz      short loc_18000552A
0x1800054fd  cmp     ebp, eax
0x1800054ff  jnz     short loc_18000552A
0x180005501  mov     r8d, 10h; unsigned __int64
0x180005507  mov     [rsp+48h+var_28], 3
0x180005510  lea     rdx, [rsp+48h+var_28]; void *
0x180005515  mov     [rsp+48h+var_20], rsi
0x18000551a  lea     rcx, qword_180018258; this
0x180005521  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005526  test    al, al
0x180005528  jnz     short loc_18000552E
0x18000552a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000552e  lea     rcx, [rsp+48h+arg_8]
0x180005533  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005538  mov     eax, [rdi]
0x18000553a  test    al, 2
0x18000553c  jnz     short loc_18000554D
0x18000553e  and     eax, 0FFFFF63Eh
0x180005543  and     ebx, 9C1h
0x180005549  or      eax, ebx
0x18000554b  mov     [rdi], eax
0x18000554d  mov     rbx, [rsp+48h+arg_10]
0x180005552  mov     rax, rdi
0x180005555  add     rsp, 30h
0x180005559  pop     rdi
0x18000555a  pop     rsi
0x18000555b  pop     rbp
0x18000555c  retn
```
