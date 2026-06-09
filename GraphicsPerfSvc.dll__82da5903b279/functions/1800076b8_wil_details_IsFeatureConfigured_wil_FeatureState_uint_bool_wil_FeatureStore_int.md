# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800076b8`
- end: `0x18000779f`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a0e0`
- `0x18000a150`

## callees

- `0x180006744`
- `0x1800076b8`
- `0x180009a60`
- `0x18000b038`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, int a2, unsigned __int8 a3, int a4, __int64 a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  int v8; // ebp
  volatile __int32 v9; // r9d
  int v11; // r14d
  int v12; // r9d
  int FeatureState; // eax
  int v14; // r8d
  bool v15; // di
  char v16; // dl
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      (__int64)&wil::details::g_enabledStateManager,
      (volatile signed __int32 *)v7,
      0,
      v11);
  return v15;
}

```

## disassembly

```asm
0x1800076b8  mov     [rsp+arg_0], rbx
0x1800076bd  mov     [rsp+arg_8], rbp
0x1800076c2  push    rsi
0x1800076c3  push    rdi
0x1800076c4  push    r14
0x1800076c6  sub     rsp, 30h
0x1800076ca  test    r9d, r9d
0x1800076cd  movzx   edi, r8b
0x1800076d1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800076d8  mov     esi, edx
0x1800076da  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800076e1  mov     rbp, rcx
0x1800076e4  cmovnz  rbx, rax
0x1800076e8  mov     r9d, [rbx]
0x1800076eb  mov     eax, r9d
0x1800076ee  and     al, 3
0x1800076f0  cmp     al, 2
0x1800076f2  jnz     short loc_1800076FB
0x1800076f4  xor     al, al
0x1800076f6  jmp     loc_18000778C
0x1800076fb  test    r9b, 2
0x1800076ff  jnz     short loc_18000776C
0x180007701  mov     [rsp+48h+arg_18], 1
0x180007709  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000770e  mov     rcx, [rsp+48h+arg_20]
0x180007713  mov     r14d, eax
0x180007716  mov     [rsp+48h+var_20], rcx
0x18000771b  lea     rax, [rsp+48h+arg_18]
0x180007720  mov     rcx, rbp
0x180007723  mov     [rsp+48h+var_28], rax
0x180007728  mov     r8d, edi
0x18000772b  mov     edx, esi
0x18000772d  call    wil_QueryFeatureState
0x180007732  mov     r8d, [rsp+48h+arg_18]
0x180007737  test    eax, eax
0x180007739  mov     ecx, r8d
0x18000773c  setnz   dil
0x180007740  neg     ecx
0x180007742  sbb     edx, edx
0x180007744  neg     edx
0x180007746  add     edx, 6
0x180007749  xchg    edx, [rbx]
0x18000774b  test    r8d, r8d
0x18000774e  jnz     short loc_180007767
0x180007750  test    dl, 4
0x180007753  jnz     short loc_180007767
0x180007755  mov     r9d, r14d
0x180007758  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000775f  mov     rdx, rbx
0x180007762  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007767  mov     al, dil
0x18000776a  jmp     short loc_18000778C
0x18000776c  mov     rax, [rsp+48h+arg_20]
0x180007771  mov     r8d, edi
0x180007774  mov     [rsp+48h+var_20], rax
0x180007779  mov     [rsp+48h+var_28], 0
0x180007782  call    wil_QueryFeatureState
0x180007787  test    eax, eax
0x180007789  setnz   al
0x18000778c  mov     rbx, [rsp+48h+arg_0]
0x180007791  mov     rbp, [rsp+48h+arg_8]
0x180007796  add     rsp, 30h
0x18000779a  pop     r14
0x18000779c  pop     rdi
0x18000779d  pop     rsi
0x18000779e  retn
```
