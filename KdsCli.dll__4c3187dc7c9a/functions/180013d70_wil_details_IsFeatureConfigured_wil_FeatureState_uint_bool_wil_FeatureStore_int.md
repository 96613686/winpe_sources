# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180013d70`
- end: `0x180013e52`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016070`

## callees

- `0x18000ae28`
- `0x18000cd04`
- `0x180013d70`
- `0x18001688c`

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
0x180013d70  mov     [rsp+arg_0], rbx
0x180013d75  mov     [rsp+arg_8], rbp
0x180013d7a  push    rsi
0x180013d7b  push    rdi
0x180013d7c  push    r14
0x180013d7e  sub     rsp, 30h
0x180013d82  test    r9d, r9d
0x180013d85  movzx   edi, r8b
0x180013d89  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180013d90  mov     esi, edx
0x180013d92  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180013d99  mov     rbp, rcx
0x180013d9c  cmovnz  rbx, rax
0x180013da0  mov     r9d, [rbx]
0x180013da3  mov     eax, r9d
0x180013da6  and     al, 3
0x180013da8  cmp     al, 2
0x180013daa  jnz     short loc_180013DB3
0x180013dac  xor     al, al
0x180013dae  jmp     loc_180013E3F
0x180013db3  test    r9b, 2
0x180013db7  jnz     short loc_180013E1F
0x180013db9  mov     [rsp+48h+arg_18], 1
0x180013dc1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013dc6  mov     rcx, [rsp+48h+arg_20]
0x180013dcb  mov     r14d, eax
0x180013dce  mov     [rsp+48h+var_20], rcx
0x180013dd3  lea     rax, [rsp+48h+arg_18]
0x180013dd8  mov     rcx, rbp
0x180013ddb  mov     [rsp+48h+var_28], rax
0x180013de0  mov     r8d, edi
0x180013de3  mov     edx, esi
0x180013de5  call    wil_QueryFeatureState
0x180013dea  mov     edx, [rsp+48h+arg_18]
0x180013dee  test    eax, eax
0x180013df0  mov     ecx, edx
0x180013df2  setnz   dil
0x180013df6  neg     ecx
0x180013df8  sbb     r8d, r8d
0x180013dfb  neg     r8d
0x180013dfe  add     r8d, 6
0x180013e02  xchg    r8d, [rbx]
0x180013e05  test    edx, edx
0x180013e07  jnz     short loc_180013E1A
0x180013e09  test    r8b, 4
0x180013e0d  jnz     short loc_180013E1A
0x180013e0f  mov     r8d, r14d
0x180013e12  mov     rcx, rbx
0x180013e15  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013e1a  mov     al, dil
0x180013e1d  jmp     short loc_180013E3F
0x180013e1f  mov     rax, [rsp+48h+arg_20]
0x180013e24  mov     r8d, edi
0x180013e27  mov     [rsp+48h+var_20], rax
0x180013e2c  mov     [rsp+48h+var_28], 0
0x180013e35  call    wil_QueryFeatureState
0x180013e3a  test    eax, eax
0x180013e3c  setnz   al
0x180013e3f  mov     rbx, [rsp+48h+arg_0]
0x180013e44  mov     rbp, [rsp+48h+arg_8]
0x180013e49  add     rsp, 30h
0x180013e4d  pop     r14
0x180013e4f  pop     rdi
0x180013e50  pop     rsi
0x180013e51  retn
```
