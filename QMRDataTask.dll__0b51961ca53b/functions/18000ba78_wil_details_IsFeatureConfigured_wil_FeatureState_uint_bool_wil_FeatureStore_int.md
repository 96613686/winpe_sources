# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000ba78`
- end: `0x18000bb5a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010df0`

## callees

- `0x18000787c`
- `0x18000ba78`
- `0x180010684`
- `0x180012320`

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
0x18000ba78  mov     [rsp+arg_0], rbx
0x18000ba7d  mov     [rsp+arg_8], rbp
0x18000ba82  push    rsi
0x18000ba83  push    rdi
0x18000ba84  push    r14
0x18000ba86  sub     rsp, 30h
0x18000ba8a  test    r9d, r9d
0x18000ba8d  movzx   edi, r8b
0x18000ba91  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000ba98  mov     esi, edx
0x18000ba9a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000baa1  mov     rbp, rcx
0x18000baa4  cmovnz  rbx, rax
0x18000baa8  mov     r9d, [rbx]
0x18000baab  mov     eax, r9d
0x18000baae  and     al, 3
0x18000bab0  cmp     al, 2
0x18000bab2  jnz     short loc_18000BABB
0x18000bab4  xor     al, al
0x18000bab6  jmp     loc_18000BB47
0x18000babb  test    r9b, 2
0x18000babf  jnz     short loc_18000BB27
0x18000bac1  mov     [rsp+48h+arg_18], 1
0x18000bac9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000bace  mov     rcx, [rsp+48h+arg_20]
0x18000bad3  mov     r14d, eax
0x18000bad6  mov     [rsp+48h+var_20], rcx
0x18000badb  lea     rax, [rsp+48h+arg_18]
0x18000bae0  mov     rcx, rbp
0x18000bae3  mov     [rsp+48h+var_28], rax
0x18000bae8  mov     r8d, edi
0x18000baeb  mov     edx, esi
0x18000baed  call    wil_QueryFeatureState
0x18000baf2  mov     edx, [rsp+48h+arg_18]
0x18000baf6  test    eax, eax
0x18000baf8  mov     ecx, edx
0x18000bafa  setnz   dil
0x18000bafe  neg     ecx
0x18000bb00  sbb     r8d, r8d
0x18000bb03  neg     r8d
0x18000bb06  add     r8d, 6
0x18000bb0a  xchg    r8d, [rbx]
0x18000bb0d  test    edx, edx
0x18000bb0f  jnz     short loc_18000BB22
0x18000bb11  test    r8b, 4
0x18000bb15  jnz     short loc_18000BB22
0x18000bb17  mov     r8d, r14d
0x18000bb1a  mov     rcx, rbx
0x18000bb1d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000bb22  mov     al, dil
0x18000bb25  jmp     short loc_18000BB47
0x18000bb27  mov     rax, [rsp+48h+arg_20]
0x18000bb2c  mov     r8d, edi
0x18000bb2f  mov     [rsp+48h+var_20], rax
0x18000bb34  mov     [rsp+48h+var_28], 0
0x18000bb3d  call    wil_QueryFeatureState
0x18000bb42  test    eax, eax
0x18000bb44  setnz   al
0x18000bb47  mov     rbx, [rsp+48h+arg_0]
0x18000bb4c  mov     rbp, [rsp+48h+arg_8]
0x18000bb51  add     rsp, 30h
0x18000bb55  pop     r14
0x18000bb57  pop     rdi
0x18000bb58  pop     rsi
0x18000bb59  retn
```
