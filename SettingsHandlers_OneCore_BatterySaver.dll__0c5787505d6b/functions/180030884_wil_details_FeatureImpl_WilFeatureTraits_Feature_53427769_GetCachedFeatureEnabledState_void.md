# wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::GetCachedFeatureEnabledState(void)

- ea: `0x180030884`
- end: `0x1800309bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031140`
- `0x1800317b0`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180030884`
- `0x180030c44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030942`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_53427769__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_53427769__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_53427769__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_53427769__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_53427769__descriptor, 0xFFFFFFFB);
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
0x180030884  mov     [rsp+arg_10], rbx
0x180030889  mov     [rsp+arg_18], rbp
0x18003088e  mov     [rsp+arg_0], rcx
0x180030893  push    rsi
0x180030894  push    rdi
0x180030895  push    r14
0x180030897  sub     rsp, 30h
0x18003089b  mov     rsi, cs:Feature_53427769__descriptor
0x1800308a2  mov     rdi, rdx
0x1800308a5  mov     qword ptr [rdx], 0
0x1800308ac  mov     eax, [rsi]
0x1800308ae  mov     [rdx], eax
0x1800308b0  and     eax, 6
0x1800308b3  cmp     al, 6
0x1800308b5  jz      loc_1800309A7
0x1800308bb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800308c0  lea     r8, [rsp+48h+arg_0]
0x1800308c5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800308cd  lea     rdx, [rsp+48h+arg_8]
0x1800308d2  mov     ebp, eax
0x1800308d4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::GetCurrentFeatureEnabledState(int *)
0x1800308d9  mov     eax, [rdi]
0x1800308db  mov     rbx, [rsp+48h+arg_8]
0x1800308e0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800308e5  mov     edx, eax
0x1800308e7  mov     [rdi], eax
0x1800308e9  mov     ecx, eax
0x1800308eb  jz      short loc_180030906
0x1800308ed  test    dl, 2
0x1800308f0  jnz     short loc_180030906
0x1800308f2  and     ecx, 0FFFFF63Eh
0x1800308f8  mov     eax, ebx
0x1800308fa  and     eax, 9C1h
0x1800308ff  or      ecx, eax
0x180030901  or      ecx, 2
0x180030904  mov     [rdi], ecx
0x180030906  mov     r8d, edx
0x180030909  and     r8d, 4
0x18003090d  jnz     short loc_180030921
0x18003090f  btr     ecx, 0Ah
0x180030913  mov     eax, ebx
0x180030915  and     eax, 400h
0x18003091a  or      ecx, eax
0x18003091c  or      ecx, 4
0x18003091f  mov     [rdi], ecx
0x180030921  mov     eax, edx
0x180030923  lock cmpxchg [rsi], ecx
0x180030927  jnz     short loc_1800308E0
0x180030929  test    r8d, r8d
0x18003092c  jnz     short loc_180030992
0x18003092e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180030934  test    eax, eax
0x180030936  jz      short loc_180030992
0x180030938  lea     r14, SRWLock
0x18003093f  mov     rcx, r14; SRWLock
0x180030942  call    cs:__imp_AcquireSRWLockExclusive
0x180030948  mov     eax, cs:dword_180066AF4
0x18003094e  mov     [rsp+48h+arg_8], r14
0x180030953  test    ebp, ebp
0x180030955  jz      short loc_180030984
0x180030957  cmp     ebp, eax
0x180030959  jnz     short loc_180030984
0x18003095b  mov     r8d, 10h; unsigned __int64
0x180030961  mov     [rsp+48h+var_28], 3
0x18003096a  lea     rdx, [rsp+48h+var_28]; void *
0x18003096f  mov     [rsp+48h+var_20], rsi
0x180030974  lea     rcx, qword_180066B18; this
0x18003097b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180030980  test    al, al
0x180030982  jnz     short loc_180030988
0x180030984  lock and dword ptr [rsi], 0FFFFFFFBh
0x180030988  lea     rcx, [rsp+48h+arg_8]
0x18003098d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180030992  mov     eax, [rdi]
0x180030994  test    al, 2
0x180030996  jnz     short loc_1800309A7
0x180030998  and     eax, 0FFFFF63Eh
0x18003099d  and     ebx, 9C1h
0x1800309a3  or      eax, ebx
0x1800309a5  mov     [rdi], eax
0x1800309a7  mov     rbx, [rsp+48h+arg_10]
0x1800309ac  mov     rax, rdi
0x1800309af  mov     rbp, [rsp+48h+arg_18]
0x1800309b4  add     rsp, 30h
0x1800309b8  pop     r14
0x1800309ba  pop     rdi
0x1800309bb  pop     rsi
0x1800309bc  retn
```
