# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1400075d0`
- end: `0x1400076b2`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000af70`

## callees

- `0x1400049e0`
- `0x1400075d0`
- `0x14000a88c`
- `0x14000c234`

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
  v7 = `wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
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
0x1400075d0  mov     [rsp+arg_0], rbx
0x1400075d5  mov     [rsp+arg_8], rbp
0x1400075da  push    rsi
0x1400075db  push    rdi
0x1400075dc  push    r14
0x1400075de  sub     rsp, 30h
0x1400075e2  test    r9d, r9d
0x1400075e5  movzx   edi, r8b
0x1400075e9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1400075f0  mov     esi, edx
0x1400075f2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1400075f9  mov     rbp, rcx
0x1400075fc  cmovnz  rbx, rax
0x140007600  mov     r9d, [rbx]
0x140007603  mov     eax, r9d
0x140007606  and     al, 3
0x140007608  cmp     al, 2
0x14000760a  jnz     short loc_140007613
0x14000760c  xor     al, al
0x14000760e  jmp     loc_14000769F
0x140007613  test    r9b, 2
0x140007617  jnz     short loc_14000767F
0x140007619  mov     [rsp+48h+arg_18], 1
0x140007621  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007626  mov     rcx, [rsp+48h+arg_20]
0x14000762b  mov     r14d, eax
0x14000762e  mov     [rsp+48h+var_20], rcx
0x140007633  lea     rax, [rsp+48h+arg_18]
0x140007638  mov     rcx, rbp
0x14000763b  mov     [rsp+48h+var_28], rax
0x140007640  mov     r8d, edi
0x140007643  mov     edx, esi
0x140007645  call    wil_QueryFeatureState
0x14000764a  mov     edx, [rsp+48h+arg_18]
0x14000764e  test    eax, eax
0x140007650  mov     ecx, edx
0x140007652  setnz   dil
0x140007656  neg     ecx
0x140007658  sbb     r8d, r8d
0x14000765b  neg     r8d
0x14000765e  add     r8d, 6
0x140007662  xchg    r8d, [rbx]
0x140007665  test    edx, edx
0x140007667  jnz     short loc_14000767A
0x140007669  test    r8b, 4
0x14000766d  jnz     short loc_14000767A
0x14000766f  mov     r8d, r14d
0x140007672  mov     rcx, rbx
0x140007675  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000767a  mov     al, dil
0x14000767d  jmp     short loc_14000769F
0x14000767f  mov     rax, [rsp+48h+arg_20]
0x140007684  mov     r8d, edi
0x140007687  mov     [rsp+48h+var_20], rax
0x14000768c  mov     [rsp+48h+var_28], 0
0x140007695  call    wil_QueryFeatureState
0x14000769a  test    eax, eax
0x14000769c  setnz   al
0x14000769f  mov     rbx, [rsp+48h+arg_0]
0x1400076a4  mov     rbp, [rsp+48h+arg_8]
0x1400076a9  add     rsp, 30h
0x1400076ad  pop     r14
0x1400076af  pop     rdi
0x1400076b0  pop     rsi
0x1400076b1  retn
```
