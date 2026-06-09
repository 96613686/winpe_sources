# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1400078c4`
- end: `0x1400079ab`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000a9b0`

## callees

- `0x140007374`
- `0x1400078c4`
- `0x140008f28`
- `0x14000b268`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, int a2, unsigned __int8 a3, int a4, __int64 a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  int v8; // ebp
  volatile __int32 v9; // r9d
  unsigned int v11; // r14d
  int v12; // r9d
  int FeatureState; // eax
  __int64 v14; // r8
  bool v15; // di
  char v16; // dl
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v8 = (int)a1;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(_DWORD *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((_DWORD)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  FeatureState = wil_QueryFeatureState(v8, a2, v5, v12, (__int64)&v17, a5);
  v14 = v17;
  v15 = FeatureState != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      wil::details::g_enabledStateManager,
      v7,
      v14,
      v11);
  return v15;
}

```

## disassembly

```asm
0x1400078c4  mov     [rsp+arg_0], rbx
0x1400078c9  mov     [rsp+arg_8], rbp
0x1400078ce  push    rsi
0x1400078cf  push    rdi
0x1400078d0  push    r14
0x1400078d2  sub     rsp, 30h
0x1400078d6  test    r9d, r9d
0x1400078d9  movzx   edi, r8b
0x1400078dd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1400078e4  mov     esi, edx
0x1400078e6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1400078ed  mov     rbp, rcx
0x1400078f0  cmovnz  rbx, rax
0x1400078f4  mov     r9d, [rbx]
0x1400078f7  mov     eax, r9d
0x1400078fa  and     al, 3
0x1400078fc  cmp     al, 2
0x1400078fe  jnz     short loc_140007907
0x140007900  xor     al, al
0x140007902  jmp     loc_140007998
0x140007907  test    r9b, 2
0x14000790b  jnz     short loc_140007978
0x14000790d  mov     [rsp+48h+arg_18], 1
0x140007915  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000791a  mov     rcx, [rsp+48h+arg_20]
0x14000791f  mov     r14d, eax
0x140007922  mov     [rsp+48h+var_20], rcx
0x140007927  lea     rax, [rsp+48h+arg_18]
0x14000792c  mov     rcx, rbp
0x14000792f  mov     [rsp+48h+var_28], rax
0x140007934  mov     r8d, edi
0x140007937  mov     edx, esi
0x140007939  call    wil_QueryFeatureState
0x14000793e  mov     r8d, [rsp+48h+arg_18]
0x140007943  test    eax, eax
0x140007945  mov     ecx, r8d
0x140007948  setnz   dil
0x14000794c  neg     ecx
0x14000794e  sbb     edx, edx
0x140007950  neg     edx
0x140007952  add     edx, 6
0x140007955  xchg    edx, [rbx]
0x140007957  test    r8d, r8d
0x14000795a  jnz     short loc_140007973
0x14000795c  test    dl, 4
0x14000795f  jnz     short loc_140007973
0x140007961  mov     r9d, r14d
0x140007964  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000796b  mov     rdx, rbx
0x14000796e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007973  mov     al, dil
0x140007976  jmp     short loc_140007998
0x140007978  mov     rax, [rsp+48h+arg_20]
0x14000797d  mov     r8d, edi
0x140007980  mov     [rsp+48h+var_20], rax
0x140007985  mov     [rsp+48h+var_28], 0
0x14000798e  call    wil_QueryFeatureState
0x140007993  test    eax, eax
0x140007995  setnz   al
0x140007998  mov     rbx, [rsp+48h+arg_0]
0x14000799d  mov     rbp, [rsp+48h+arg_8]
0x1400079a2  add     rsp, 30h
0x1400079a6  pop     r14
0x1400079a8  pop     rdi
0x1400079a9  pop     rsi
0x1400079aa  retn
```
