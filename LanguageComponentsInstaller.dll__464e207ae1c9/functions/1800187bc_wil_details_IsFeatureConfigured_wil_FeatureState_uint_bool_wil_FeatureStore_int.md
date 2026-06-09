# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800187bc`
- end: `0x18001889e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001cd30`

## callees

- `0x180016060`
- `0x1800187bc`
- `0x18001c760`
- `0x1800236a8`

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
  __int64 v14; // rdx
  bool v15; // di
  char v16; // r8
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
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, v14, v11);
  return v15;
}

```

## disassembly

```asm
0x1800187bc  mov     [rsp+arg_0], rbx
0x1800187c1  mov     [rsp+arg_8], rbp
0x1800187c6  push    rsi
0x1800187c7  push    rdi
0x1800187c8  push    r14
0x1800187ca  sub     rsp, 30h
0x1800187ce  test    r9d, r9d
0x1800187d1  movzx   edi, r8b
0x1800187d5  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800187dc  mov     esi, edx
0x1800187de  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800187e5  mov     rbp, rcx
0x1800187e8  cmovnz  rbx, rax
0x1800187ec  mov     r9d, [rbx]
0x1800187ef  mov     eax, r9d
0x1800187f2  and     al, 3
0x1800187f4  cmp     al, 2
0x1800187f6  jnz     short loc_1800187FF
0x1800187f8  xor     al, al
0x1800187fa  jmp     loc_18001888B
0x1800187ff  test    r9b, 2
0x180018803  jnz     short loc_18001886B
0x180018805  mov     [rsp+48h+arg_18], 1
0x18001880d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018812  mov     rcx, [rsp+48h+arg_20]
0x180018817  mov     r14d, eax
0x18001881a  mov     [rsp+48h+var_20], rcx
0x18001881f  lea     rax, [rsp+48h+arg_18]
0x180018824  mov     rcx, rbp
0x180018827  mov     [rsp+48h+var_28], rax
0x18001882c  mov     r8d, edi
0x18001882f  mov     edx, esi
0x180018831  call    wil_QueryFeatureState
0x180018836  mov     edx, [rsp+48h+arg_18]
0x18001883a  test    eax, eax
0x18001883c  mov     ecx, edx
0x18001883e  setnz   dil
0x180018842  neg     ecx
0x180018844  sbb     r8d, r8d
0x180018847  neg     r8d
0x18001884a  add     r8d, 6
0x18001884e  xchg    r8d, [rbx]
0x180018851  test    edx, edx
0x180018853  jnz     short loc_180018866
0x180018855  test    r8b, 4
0x180018859  jnz     short loc_180018866
0x18001885b  mov     r8d, r14d
0x18001885e  mov     rcx, rbx
0x180018861  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180018866  mov     al, dil
0x180018869  jmp     short loc_18001888B
0x18001886b  mov     rax, [rsp+48h+arg_20]
0x180018870  mov     r8d, edi
0x180018873  mov     [rsp+48h+var_20], rax
0x180018878  mov     [rsp+48h+var_28], 0
0x180018881  call    wil_QueryFeatureState
0x180018886  test    eax, eax
0x180018888  setnz   al
0x18001888b  mov     rbx, [rsp+48h+arg_0]
0x180018890  mov     rbp, [rsp+48h+arg_8]
0x180018895  add     rsp, 30h
0x180018899  pop     r14
0x18001889b  pop     rdi
0x18001889c  pop     rsi
0x18001889d  retn
```
