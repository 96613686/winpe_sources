# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800058c4`
- end: `0x1800059a6`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008bc0`

## callees

- `0x1800045f8`
- `0x1800058c4`
- `0x1800084e4`
- `0x18000e704`

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
0x1800058c4  mov     [rsp+arg_0], rbx
0x1800058c9  mov     [rsp+arg_8], rbp
0x1800058ce  push    rsi
0x1800058cf  push    rdi
0x1800058d0  push    r14
0x1800058d2  sub     rsp, 30h
0x1800058d6  test    r9d, r9d
0x1800058d9  movzx   edi, r8b
0x1800058dd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800058e4  mov     esi, edx
0x1800058e6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800058ed  mov     rbp, rcx
0x1800058f0  cmovnz  rbx, rax
0x1800058f4  mov     r9d, [rbx]
0x1800058f7  mov     eax, r9d
0x1800058fa  and     al, 3
0x1800058fc  cmp     al, 2
0x1800058fe  jnz     short loc_180005907
0x180005900  xor     al, al
0x180005902  jmp     loc_180005993
0x180005907  test    r9b, 2
0x18000590b  jnz     short loc_180005973
0x18000590d  mov     [rsp+48h+arg_18], 1
0x180005915  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000591a  mov     rcx, [rsp+48h+arg_20]
0x18000591f  mov     r14d, eax
0x180005922  mov     [rsp+48h+var_20], rcx
0x180005927  lea     rax, [rsp+48h+arg_18]
0x18000592c  mov     rcx, rbp
0x18000592f  mov     [rsp+48h+var_28], rax
0x180005934  mov     r8d, edi
0x180005937  mov     edx, esi
0x180005939  call    wil_QueryFeatureState
0x18000593e  mov     edx, [rsp+48h+arg_18]
0x180005942  test    eax, eax
0x180005944  mov     ecx, edx
0x180005946  setnz   dil
0x18000594a  neg     ecx
0x18000594c  sbb     r8d, r8d
0x18000594f  neg     r8d
0x180005952  add     r8d, 6
0x180005956  xchg    r8d, [rbx]
0x180005959  test    edx, edx
0x18000595b  jnz     short loc_18000596E
0x18000595d  test    r8b, 4
0x180005961  jnz     short loc_18000596E
0x180005963  mov     r8d, r14d
0x180005966  mov     rcx, rbx
0x180005969  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000596e  mov     al, dil
0x180005971  jmp     short loc_180005993
0x180005973  mov     rax, [rsp+48h+arg_20]
0x180005978  mov     r8d, edi
0x18000597b  mov     [rsp+48h+var_20], rax
0x180005980  mov     [rsp+48h+var_28], 0
0x180005989  call    wil_QueryFeatureState
0x18000598e  test    eax, eax
0x180005990  setnz   al
0x180005993  mov     rbx, [rsp+48h+arg_0]
0x180005998  mov     rbp, [rsp+48h+arg_8]
0x18000599d  add     rsp, 30h
0x1800059a1  pop     r14
0x1800059a3  pop     rdi
0x1800059a4  pop     rsi
0x1800059a5  retn
```
