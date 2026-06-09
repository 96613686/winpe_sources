# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001364c`
- end: `0x18001378c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001568c`
- `0x180015afc`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x18001364c`
- `0x1800142fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001370a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001370a`

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
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
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
0x18001364c  mov     [rsp+arg_10], rbx
0x180013651  mov     [rsp+arg_18], rbp
0x180013656  mov     [rsp+arg_0], rcx
0x18001365b  push    rsi
0x18001365c  push    rdi
0x18001365d  push    r14
0x18001365f  sub     rsp, 30h
0x180013663  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001366a  mov     rdi, rdx
0x18001366d  mov     qword ptr [rdx], 0
0x180013674  mov     eax, [rsi]
0x180013676  mov     [rdx], eax
0x180013678  and     eax, 6
0x18001367b  cmp     al, 6
0x18001367d  jz      loc_180013775
0x180013683  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013688  lea     r8, [rsp+48h+arg_0]
0x18001368d  mov     dword ptr [rsp+48h+arg_0], 0
0x180013695  lea     rdx, [rsp+48h+arg_8]
0x18001369a  mov     ebp, eax
0x18001369c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x1800136a1  mov     eax, [rdi]
0x1800136a3  mov     rbx, [rsp+48h+arg_8]
0x1800136a8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800136ad  mov     edx, eax
0x1800136af  mov     [rdi], eax
0x1800136b1  mov     ecx, eax
0x1800136b3  jz      short loc_1800136CE
0x1800136b5  test    dl, 2
0x1800136b8  jnz     short loc_1800136CE
0x1800136ba  and     ecx, 0FFFFF63Eh
0x1800136c0  mov     eax, ebx
0x1800136c2  and     eax, 9C1h
0x1800136c7  or      ecx, eax
0x1800136c9  or      ecx, 2
0x1800136cc  mov     [rdi], ecx
0x1800136ce  mov     r8d, edx
0x1800136d1  and     r8d, 4
0x1800136d5  jnz     short loc_1800136E9
0x1800136d7  btr     ecx, 0Ah
0x1800136db  mov     eax, ebx
0x1800136dd  and     eax, 400h
0x1800136e2  or      ecx, eax
0x1800136e4  or      ecx, 4
0x1800136e7  mov     [rdi], ecx
0x1800136e9  mov     eax, edx
0x1800136eb  lock cmpxchg [rsi], ecx
0x1800136ef  jnz     short loc_1800136A8
0x1800136f1  test    r8d, r8d
0x1800136f4  jnz     short loc_180013760
0x1800136f6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800136fc  test    eax, eax
0x1800136fe  jz      short loc_180013760
0x180013700  lea     r14, stru_180029CA8
0x180013707  mov     rcx, r14; SRWLock
0x18001370a  call    cs:__imp_AcquireSRWLockExclusive
0x180013711  nop     dword ptr [rax+rax+00h]
0x180013716  mov     eax, cs:dword_180029CBC
0x18001371c  mov     [rsp+48h+arg_8], r14
0x180013721  test    ebp, ebp
0x180013723  jz      short loc_180013752
0x180013725  cmp     ebp, eax
0x180013727  jnz     short loc_180013752
0x180013729  mov     r8d, 10h; unsigned __int64
0x18001372f  mov     [rsp+48h+var_28], 3
0x180013738  lea     rdx, [rsp+48h+var_28]; void *
0x18001373d  mov     [rsp+48h+var_20], rsi
0x180013742  lea     rcx, qword_180029CF0; this
0x180013749  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001374e  test    al, al
0x180013750  jnz     short loc_180013756
0x180013752  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013756  lea     rcx, [rsp+48h+arg_8]
0x18001375b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013760  mov     eax, [rdi]
0x180013762  test    al, 2
0x180013764  jnz     short loc_180013775
0x180013766  and     eax, 0FFFFF63Eh
0x18001376b  and     ebx, 9C1h
0x180013771  or      eax, ebx
0x180013773  mov     [rdi], eax
0x180013775  mov     rbx, [rsp+48h+arg_10]
0x18001377a  mov     rax, rdi
0x18001377d  mov     rbp, [rsp+48h+arg_18]
0x180013782  add     rsp, 30h
0x180013786  pop     r14
0x180013788  pop     rdi
0x180013789  pop     rsi
0x18001378a  retn
```
