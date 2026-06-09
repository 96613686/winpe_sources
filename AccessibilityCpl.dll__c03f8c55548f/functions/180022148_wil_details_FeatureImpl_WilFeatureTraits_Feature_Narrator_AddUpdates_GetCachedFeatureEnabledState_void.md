# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(void)

- ea: `0x180022148`
- end: `0x180022281`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800238ac`
- `0x1800249d4`

## callees

- `0x1800049d0`
- `0x180005f28`
- `0x18001b77c`
- `0x180022148`
- `0x180022288`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022206`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022206`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Narrator_AddUpdates__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180040C30);
      v16 = &stru_180040C30;
      if ( !v5
        || v5 != dword_180040C44
        || (v14[0] = 1,
            v14[1] = Feature_Narrator_AddUpdates__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180040C68, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Narrator_AddUpdates__descriptor, 0xFFFFFFFB);
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
0x180022148  mov     [rsp+arg_10], rbx
0x18002214d  mov     [rsp+arg_18], rbp
0x180022152  mov     [rsp+arg_0], rcx
0x180022157  push    rsi
0x180022158  push    rdi
0x180022159  push    r14
0x18002215b  sub     rsp, 30h
0x18002215f  mov     rsi, cs:Feature_Narrator_AddUpdates__descriptor
0x180022166  mov     rdi, rdx
0x180022169  mov     qword ptr [rdx], 0
0x180022170  mov     eax, [rsi]
0x180022172  mov     [rdx], eax
0x180022174  and     eax, 6
0x180022177  cmp     al, 6
0x180022179  jz      loc_18002226B
0x18002217f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180022184  lea     r8, [rsp+48h+arg_0]
0x180022189  mov     dword ptr [rsp+48h+arg_0], 0
0x180022191  lea     rdx, [rsp+48h+arg_8]
0x180022196  mov     ebp, eax
0x180022198  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetCurrentFeatureEnabledState(int *)
0x18002219d  mov     eax, [rdi]
0x18002219f  mov     rbx, [rsp+48h+arg_8]
0x1800221a4  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800221a9  mov     edx, eax
0x1800221ab  mov     [rdi], eax
0x1800221ad  mov     ecx, eax
0x1800221af  jz      short loc_1800221CA
0x1800221b1  test    dl, 2
0x1800221b4  jnz     short loc_1800221CA
0x1800221b6  and     ecx, 0FFFFF63Eh
0x1800221bc  mov     eax, ebx
0x1800221be  and     eax, 9C1h
0x1800221c3  or      ecx, eax
0x1800221c5  or      ecx, 2
0x1800221c8  mov     [rdi], ecx
0x1800221ca  mov     r8d, edx
0x1800221cd  and     r8d, 4
0x1800221d1  jnz     short loc_1800221E5
0x1800221d3  btr     ecx, 0Ah
0x1800221d7  mov     eax, ebx
0x1800221d9  and     eax, 400h
0x1800221de  or      ecx, eax
0x1800221e0  or      ecx, 4
0x1800221e3  mov     [rdi], ecx
0x1800221e5  mov     eax, edx
0x1800221e7  lock cmpxchg [rsi], ecx
0x1800221eb  jnz     short loc_1800221A4
0x1800221ed  test    r8d, r8d
0x1800221f0  jnz     short loc_180022256
0x1800221f2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800221f8  test    eax, eax
0x1800221fa  jz      short loc_180022256
0x1800221fc  lea     r14, stru_180040C30
0x180022203  mov     rcx, r14; SRWLock
0x180022206  call    cs:__imp_AcquireSRWLockExclusive
0x18002220c  mov     eax, cs:dword_180040C44
0x180022212  mov     [rsp+48h+arg_8], r14
0x180022217  test    ebp, ebp
0x180022219  jz      short loc_180022248
0x18002221b  cmp     ebp, eax
0x18002221d  jnz     short loc_180022248
0x18002221f  mov     r8d, 10h; unsigned __int64
0x180022225  mov     [rsp+48h+var_28], 1
0x18002222e  lea     rdx, [rsp+48h+var_28]; void *
0x180022233  mov     [rsp+48h+var_20], rsi
0x180022238  lea     rcx, qword_180040C68; this
0x18002223f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180022244  test    al, al
0x180022246  jnz     short loc_18002224C
0x180022248  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002224c  lea     rcx, [rsp+48h+arg_8]
0x180022251  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022256  mov     eax, [rdi]
0x180022258  test    al, 2
0x18002225a  jnz     short loc_18002226B
0x18002225c  and     eax, 0FFFFF63Eh
0x180022261  and     ebx, 9C1h
0x180022267  or      eax, ebx
0x180022269  mov     [rdi], eax
0x18002226b  mov     rbx, [rsp+48h+arg_10]
0x180022270  mov     rax, rdi
0x180022273  mov     rbp, [rsp+48h+arg_18]
0x180022278  add     rsp, 30h
0x18002227c  pop     r14
0x18002227e  pop     rdi
0x18002227f  pop     rsi
0x180022280  retn
```
