# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006350`
- end: `0x180006429`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008ec0`

## callees

- `0x18000543c`
- `0x180006350`
- `0x180008794`
- `0x18000a148`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // di
  char v15; // r8
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState(a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v13, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180006350  mov     [rsp+arg_0], rbx
0x180006355  mov     [rsp+arg_8], rbp
0x18000635a  push    rsi
0x18000635b  push    rdi
0x18000635c  push    r14
0x18000635e  sub     rsp, 20h
0x180006362  test    r9d, r9d
0x180006365  movzx   edi, r8b
0x180006369  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180006370  mov     esi, edx
0x180006372  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180006379  mov     rbp, rcx
0x18000637c  cmovnz  rbx, rax
0x180006380  mov     r9d, [rbx]
0x180006383  mov     eax, r9d
0x180006386  and     al, 3
0x180006388  cmp     al, 2
0x18000638a  jnz     short loc_180006393
0x18000638c  xor     al, al
0x18000638e  jmp     loc_180006416
0x180006393  test    r9b, 2
0x180006397  jnz     short loc_1800063FB
0x180006399  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000639e  mov     rcx, [rsp+38h+arg_20]
0x1800063a3  lea     r9, [rsp+38h+arg_18]
0x1800063a8  mov     r8d, edi
0x1800063ab  mov     [rsp+38h+arg_18], 0
0x1800063b3  mov     edx, esi
0x1800063b5  mov     r14d, eax
0x1800063b8  mov     dword ptr [rcx], 1
0x1800063be  mov     rcx, rbp
0x1800063c1  call    wil_RtlStagingConfig_QueryFeatureState
0x1800063c6  mov     edx, [rsp+38h+arg_18]
0x1800063ca  test    eax, eax
0x1800063cc  mov     ecx, edx
0x1800063ce  setnz   dil
0x1800063d2  neg     ecx
0x1800063d4  sbb     r8d, r8d
0x1800063d7  neg     r8d
0x1800063da  add     r8d, 6
0x1800063de  xchg    r8d, [rbx]
0x1800063e1  test    edx, edx
0x1800063e3  jnz     short loc_1800063F6
0x1800063e5  test    r8b, 4
0x1800063e9  jnz     short loc_1800063F6
0x1800063eb  mov     r8d, r14d
0x1800063ee  mov     rcx, rbx
0x1800063f1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800063f6  mov     al, dil
0x1800063f9  jmp     short loc_180006416
0x1800063fb  mov     rax, [rsp+38h+arg_20]
0x180006400  mov     r8d, edi
0x180006403  xor     r9d, r9d
0x180006406  mov     dword ptr [rax], 1
0x18000640c  call    wil_RtlStagingConfig_QueryFeatureState
0x180006411  test    eax, eax
0x180006413  setnz   al
0x180006416  mov     rbx, [rsp+38h+arg_0]
0x18000641b  mov     rbp, [rsp+38h+arg_8]
0x180006420  add     rsp, 20h
0x180006424  pop     r14
0x180006426  pop     rdi
0x180006427  pop     rsi
0x180006428  retn
```
