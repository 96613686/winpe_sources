# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180013794`
- end: `0x1800138d4`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015718`
- `0x180015b38`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180013794`
- `0x1800143e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013852`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013852`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180013794  mov     [rsp+arg_10], rbx
0x180013799  mov     [rsp+arg_18], rbp
0x18001379e  mov     [rsp+arg_0], rcx
0x1800137a3  push    rsi
0x1800137a4  push    rdi
0x1800137a5  push    r14
0x1800137a7  sub     rsp, 30h
0x1800137ab  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800137b2  mov     rdi, rdx
0x1800137b5  mov     qword ptr [rdx], 0
0x1800137bc  mov     eax, [rsi]
0x1800137be  mov     [rdx], eax
0x1800137c0  and     eax, 6
0x1800137c3  cmp     al, 6
0x1800137c5  jz      loc_1800138BD
0x1800137cb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800137d0  lea     r8, [rsp+48h+arg_0]
0x1800137d5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800137dd  lea     rdx, [rsp+48h+arg_8]
0x1800137e2  mov     ebp, eax
0x1800137e4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x1800137e9  mov     eax, [rdi]
0x1800137eb  mov     rbx, [rsp+48h+arg_8]
0x1800137f0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800137f5  mov     edx, eax
0x1800137f7  mov     [rdi], eax
0x1800137f9  mov     ecx, eax
0x1800137fb  jz      short loc_180013816
0x1800137fd  test    dl, 2
0x180013800  jnz     short loc_180013816
0x180013802  and     ecx, 0FFFFF63Eh
0x180013808  mov     eax, ebx
0x18001380a  and     eax, 9C1h
0x18001380f  or      ecx, eax
0x180013811  or      ecx, 2
0x180013814  mov     [rdi], ecx
0x180013816  mov     r8d, edx
0x180013819  and     r8d, 4
0x18001381d  jnz     short loc_180013831
0x18001381f  btr     ecx, 0Ah
0x180013823  mov     eax, ebx
0x180013825  and     eax, 400h
0x18001382a  or      ecx, eax
0x18001382c  or      ecx, 4
0x18001382f  mov     [rdi], ecx
0x180013831  mov     eax, edx
0x180013833  lock cmpxchg [rsi], ecx
0x180013837  jnz     short loc_1800137F0
0x180013839  test    r8d, r8d
0x18001383c  jnz     short loc_1800138A8
0x18001383e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013844  test    eax, eax
0x180013846  jz      short loc_1800138A8
0x180013848  lea     r14, stru_180029CA8
0x18001384f  mov     rcx, r14; SRWLock
0x180013852  call    cs:__imp_AcquireSRWLockExclusive
0x180013859  nop     dword ptr [rax+rax+00h]
0x18001385e  mov     eax, cs:dword_180029CBC
0x180013864  mov     [rsp+48h+arg_8], r14
0x180013869  test    ebp, ebp
0x18001386b  jz      short loc_18001389A
0x18001386d  cmp     ebp, eax
0x18001386f  jnz     short loc_18001389A
0x180013871  mov     r8d, 10h; unsigned __int64
0x180013877  mov     [rsp+48h+var_28], 3
0x180013880  lea     rdx, [rsp+48h+var_28]; void *
0x180013885  mov     [rsp+48h+var_20], rsi
0x18001388a  lea     rcx, qword_180029CF0; this
0x180013891  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013896  test    al, al
0x180013898  jnz     short loc_18001389E
0x18001389a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001389e  lea     rcx, [rsp+48h+arg_8]
0x1800138a3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800138a8  mov     eax, [rdi]
0x1800138aa  test    al, 2
0x1800138ac  jnz     short loc_1800138BD
0x1800138ae  and     eax, 0FFFFF63Eh
0x1800138b3  and     ebx, 9C1h
0x1800138b9  or      eax, ebx
0x1800138bb  mov     [rdi], eax
0x1800138bd  mov     rbx, [rsp+48h+arg_10]
0x1800138c2  mov     rax, rdi
0x1800138c5  mov     rbp, [rsp+48h+arg_18]
0x1800138ca  add     rsp, 30h
0x1800138ce  pop     r14
0x1800138d0  pop     rdi
0x1800138d1  pop     rsi
0x1800138d2  retn
```
