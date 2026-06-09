# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18001364c`
- end: `0x18001372e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015d80`

## callees

- `0x1800119a8`
- `0x18001364c`
- `0x1800159a4`
- `0x1800165e0`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  __int64 v9; // r9
  unsigned int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
  unsigned int v17; // [rsp+68h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v9 = *(unsigned int *)v7;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (v9 & 2) != 0 )
    return (unsigned int)wil_QueryFeatureState((__int64)a1, a2, a3, v9, 0, a5) != 0;
  v17 = 1;
  v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v13 = wil_QueryFeatureState((__int64)a1, a2, v5, v12, &v17, a5);
  v14 = v17;
  v15 = v13 != 0;
  v16 = _InterlockedExchange((volatile __int32 *)v7, (v17 != 0) + 6);
  if ( !(_DWORD)v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x18001364c  mov     [rsp+arg_0], rbx
0x180013651  mov     [rsp+arg_8], rbp
0x180013656  push    rsi
0x180013657  push    rdi
0x180013658  push    r14
0x18001365a  sub     rsp, 30h
0x18001365e  test    r9d, r9d
0x180013661  movzx   edi, r8b
0x180013665  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18001366c  mov     esi, edx
0x18001366e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180013675  mov     rbp, rcx
0x180013678  cmovnz  rbx, rax
0x18001367c  mov     r9d, [rbx]
0x18001367f  mov     eax, r9d
0x180013682  and     al, 3
0x180013684  cmp     al, 2
0x180013686  jnz     short loc_18001368F
0x180013688  xor     al, al
0x18001368a  jmp     loc_18001371B
0x18001368f  test    r9b, 2
0x180013693  jnz     short loc_1800136FB
0x180013695  mov     [rsp+48h+arg_18], 1
0x18001369d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800136a2  mov     rcx, [rsp+48h+arg_20]
0x1800136a7  mov     r14d, eax
0x1800136aa  mov     [rsp+48h+var_20], rcx
0x1800136af  lea     rax, [rsp+48h+arg_18]
0x1800136b4  mov     rcx, rbp
0x1800136b7  mov     [rsp+48h+var_28], rax
0x1800136bc  mov     r8d, edi
0x1800136bf  mov     edx, esi
0x1800136c1  call    wil_QueryFeatureState
0x1800136c6  mov     edx, [rsp+48h+arg_18]
0x1800136ca  test    eax, eax
0x1800136cc  mov     ecx, edx
0x1800136ce  setnz   dil
0x1800136d2  neg     ecx
0x1800136d4  sbb     r8d, r8d
0x1800136d7  neg     r8d
0x1800136da  add     r8d, 6
0x1800136de  xchg    r8d, [rbx]
0x1800136e1  test    edx, edx
0x1800136e3  jnz     short loc_1800136F6
0x1800136e5  test    r8b, 4
0x1800136e9  jnz     short loc_1800136F6
0x1800136eb  mov     r8d, r14d
0x1800136ee  mov     rcx, rbx
0x1800136f1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800136f6  mov     al, dil
0x1800136f9  jmp     short loc_18001371B
0x1800136fb  mov     rax, [rsp+48h+arg_20]
0x180013700  mov     r8d, edi
0x180013703  mov     [rsp+48h+var_20], rax
0x180013708  mov     [rsp+48h+var_28], 0
0x180013711  call    wil_QueryFeatureState
0x180013716  test    eax, eax
0x180013718  setnz   al
0x18001371b  mov     rbx, [rsp+48h+arg_0]
0x180013720  mov     rbp, [rsp+48h+arg_8]
0x180013725  add     rsp, 30h
0x180013729  pop     r14
0x18001372b  pop     rdi
0x18001372c  pop     rsi
0x18001372d  retn
```
