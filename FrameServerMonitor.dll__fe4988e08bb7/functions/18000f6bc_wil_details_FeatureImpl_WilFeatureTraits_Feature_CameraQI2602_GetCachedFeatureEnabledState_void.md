# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f6bc`
- end: `0x18000f7ef`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `307`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015860`
- `0x1800179c8`
- `0x180032ab4`

## callees

- `0x180003158`
- `0x18000366c`
- `0x180005518`
- `0x18000f6bc`
- `0x18001051c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f77a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f77a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::GetCachedFeatureEnabledState(
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
  unsigned __int64 v13; // r8
  _QWORD Source[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v16; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+58h] [rbp+10h] BYREF

  v16 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_CameraQI2602__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CameraQI2602__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v16) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::GetCurrentFeatureEnabledState(v6, &v17, &v16);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v17;
    do
    {
      v9 = (_DWORD)v16 == 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CameraQI2602__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v17 = &SRWLock;
      if ( !v5
        || v5 != dword_18005D444
        || (Source[0] = 3,
            Source[1] = Feature_CameraQI2602__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18005D468, Source, v13)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CameraQI2602__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000f6bc  mov     [rsp+arg_10], rbx
0x18000f6c1  mov     [rsp+arg_18], rbp
0x18000f6c6  mov     [rsp+arg_0], rcx
0x18000f6cb  push    rsi
0x18000f6cc  push    rdi
0x18000f6cd  push    r14
0x18000f6cf  sub     rsp, 30h
0x18000f6d3  mov     rsi, cs:Feature_CameraQI2602__descriptor
0x18000f6da  mov     rdi, rdx
0x18000f6dd  mov     qword ptr [rdx], 0
0x18000f6e4  mov     eax, [rsi]
0x18000f6e6  mov     [rdx], eax
0x18000f6e8  and     eax, 6
0x18000f6eb  cmp     al, 6
0x18000f6ed  jz      loc_18000F7D9
0x18000f6f3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f6f8  lea     r8, [rsp+48h+arg_0]
0x18000f6fd  mov     dword ptr [rsp+48h+arg_0], 0
0x18000f705  lea     rdx, [rsp+48h+arg_8]
0x18000f70a  mov     ebp, eax
0x18000f70c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2602>::GetCurrentFeatureEnabledState(int *)
0x18000f711  mov     eax, [rdi]
0x18000f713  mov     rbx, [rsp+48h+arg_8]
0x18000f718  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000f71d  mov     edx, eax
0x18000f71f  mov     [rdi], eax
0x18000f721  mov     ecx, eax
0x18000f723  jz      short loc_18000F73E
0x18000f725  test    dl, 2
0x18000f728  jnz     short loc_18000F73E
0x18000f72a  and     ecx, 0FFFFF63Eh
0x18000f730  mov     eax, ebx
0x18000f732  and     eax, 9C1h
0x18000f737  or      ecx, eax
0x18000f739  or      ecx, 2
0x18000f73c  mov     [rdi], ecx
0x18000f73e  mov     r8d, edx
0x18000f741  and     r8d, 4
0x18000f745  jnz     short loc_18000F759
0x18000f747  btr     ecx, 0Ah
0x18000f74b  mov     eax, ebx
0x18000f74d  and     eax, 400h
0x18000f752  or      ecx, eax
0x18000f754  or      ecx, 4
0x18000f757  mov     [rdi], ecx
0x18000f759  mov     eax, edx
0x18000f75b  lock cmpxchg [rsi], ecx
0x18000f75f  jnz     short loc_18000F718
0x18000f761  test    r8d, r8d
0x18000f764  jnz     short loc_18000F7C4
0x18000f766  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f76c  test    eax, eax
0x18000f76e  jz      short loc_18000F7C4
0x18000f770  lea     r14, SRWLock
0x18000f777  mov     rcx, r14; SRWLock
0x18000f77a  call    cs:__imp_AcquireSRWLockExclusive
0x18000f780  mov     eax, cs:dword_18005D444
0x18000f786  mov     [rsp+48h+arg_8], r14
0x18000f78b  test    ebp, ebp
0x18000f78d  jz      short loc_18000F7B6
0x18000f78f  cmp     ebp, eax
0x18000f791  jnz     short loc_18000F7B6
0x18000f793  lea     rdx, [rsp+48h+Source]; Source
0x18000f798  mov     [rsp+48h+Source], 3
0x18000f7a1  lea     rcx, qword_18005D468; this
0x18000f7a8  mov     [rsp+48h+var_20], rsi
0x18000f7ad  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f7b2  test    al, al
0x18000f7b4  jnz     short loc_18000F7BA
0x18000f7b6  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000f7ba  lea     rcx, [rsp+48h+arg_8]
0x18000f7bf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f7c4  mov     eax, [rdi]
0x18000f7c6  test    al, 2
0x18000f7c8  jnz     short loc_18000F7D9
0x18000f7ca  and     eax, 0FFFFF63Eh
0x18000f7cf  and     ebx, 9C1h
0x18000f7d5  or      eax, ebx
0x18000f7d7  mov     [rdi], eax
0x18000f7d9  mov     rbx, [rsp+48h+arg_10]
0x18000f7de  mov     rax, rdi
0x18000f7e1  mov     rbp, [rsp+48h+arg_18]
0x18000f7e6  add     rsp, 30h
0x18000f7ea  pop     r14
0x18000f7ec  pop     rdi
0x18000f7ed  pop     rsi
0x18000f7ee  retn
```
