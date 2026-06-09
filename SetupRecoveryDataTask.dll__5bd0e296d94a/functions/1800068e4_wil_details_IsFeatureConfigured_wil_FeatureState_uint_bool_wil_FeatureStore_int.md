# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800068e4`
- end: `0x1800069c6`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009be0`

## callees

- `0x1800049e4`
- `0x1800068e4`
- `0x180009528`
- `0x18000b928`

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
0x1800068e4  mov     [rsp+arg_0], rbx
0x1800068e9  mov     [rsp+arg_8], rbp
0x1800068ee  push    rsi
0x1800068ef  push    rdi
0x1800068f0  push    r14
0x1800068f2  sub     rsp, 30h
0x1800068f6  test    r9d, r9d
0x1800068f9  movzx   edi, r8b
0x1800068fd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180006904  mov     esi, edx
0x180006906  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000690d  mov     rbp, rcx
0x180006910  cmovnz  rbx, rax
0x180006914  mov     r9d, [rbx]
0x180006917  mov     eax, r9d
0x18000691a  and     al, 3
0x18000691c  cmp     al, 2
0x18000691e  jnz     short loc_180006927
0x180006920  xor     al, al
0x180006922  jmp     loc_1800069B3
0x180006927  test    r9b, 2
0x18000692b  jnz     short loc_180006993
0x18000692d  mov     [rsp+48h+arg_18], 1
0x180006935  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000693a  mov     rcx, [rsp+48h+arg_20]
0x18000693f  mov     r14d, eax
0x180006942  mov     [rsp+48h+var_20], rcx
0x180006947  lea     rax, [rsp+48h+arg_18]
0x18000694c  mov     rcx, rbp
0x18000694f  mov     [rsp+48h+var_28], rax
0x180006954  mov     r8d, edi
0x180006957  mov     edx, esi
0x180006959  call    wil_QueryFeatureState
0x18000695e  mov     edx, [rsp+48h+arg_18]
0x180006962  test    eax, eax
0x180006964  mov     ecx, edx
0x180006966  setnz   dil
0x18000696a  neg     ecx
0x18000696c  sbb     r8d, r8d
0x18000696f  neg     r8d
0x180006972  add     r8d, 6
0x180006976  xchg    r8d, [rbx]
0x180006979  test    edx, edx
0x18000697b  jnz     short loc_18000698E
0x18000697d  test    r8b, 4
0x180006981  jnz     short loc_18000698E
0x180006983  mov     r8d, r14d
0x180006986  mov     rcx, rbx
0x180006989  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000698e  mov     al, dil
0x180006991  jmp     short loc_1800069B3
0x180006993  mov     rax, [rsp+48h+arg_20]
0x180006998  mov     r8d, edi
0x18000699b  mov     [rsp+48h+var_20], rax
0x1800069a0  mov     [rsp+48h+var_28], 0
0x1800069a9  call    wil_QueryFeatureState
0x1800069ae  test    eax, eax
0x1800069b0  setnz   al
0x1800069b3  mov     rbx, [rsp+48h+arg_0]
0x1800069b8  mov     rbp, [rsp+48h+arg_8]
0x1800069bd  add     rsp, 30h
0x1800069c1  pop     r14
0x1800069c3  pop     rdi
0x1800069c4  pop     rsi
0x1800069c5  retn
```
