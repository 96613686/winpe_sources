# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140005674`
- end: `0x140005756`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008540`

## callees

- `0x140004568`
- `0x140005674`
- `0x140007e64`
- `0x140009118`

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
0x140005674  mov     [rsp+arg_0], rbx
0x140005679  mov     [rsp+arg_8], rbp
0x14000567e  push    rsi
0x14000567f  push    rdi
0x140005680  push    r14
0x140005682  sub     rsp, 30h
0x140005686  test    r9d, r9d
0x140005689  movzx   edi, r8b
0x14000568d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140005694  mov     esi, edx
0x140005696  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x14000569d  mov     rbp, rcx
0x1400056a0  cmovnz  rbx, rax
0x1400056a4  mov     r9d, [rbx]
0x1400056a7  mov     eax, r9d
0x1400056aa  and     al, 3
0x1400056ac  cmp     al, 2
0x1400056ae  jnz     short loc_1400056B7
0x1400056b0  xor     al, al
0x1400056b2  jmp     loc_140005743
0x1400056b7  test    r9b, 2
0x1400056bb  jnz     short loc_140005723
0x1400056bd  mov     [rsp+48h+arg_18], 1
0x1400056c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400056ca  mov     rcx, [rsp+48h+arg_20]
0x1400056cf  mov     r14d, eax
0x1400056d2  mov     [rsp+48h+var_20], rcx
0x1400056d7  lea     rax, [rsp+48h+arg_18]
0x1400056dc  mov     rcx, rbp
0x1400056df  mov     [rsp+48h+var_28], rax
0x1400056e4  mov     r8d, edi
0x1400056e7  mov     edx, esi
0x1400056e9  call    wil_QueryFeatureState
0x1400056ee  mov     edx, [rsp+48h+arg_18]
0x1400056f2  test    eax, eax
0x1400056f4  mov     ecx, edx
0x1400056f6  setnz   dil
0x1400056fa  neg     ecx
0x1400056fc  sbb     r8d, r8d
0x1400056ff  neg     r8d
0x140005702  add     r8d, 6
0x140005706  xchg    r8d, [rbx]
0x140005709  test    edx, edx
0x14000570b  jnz     short loc_14000571E
0x14000570d  test    r8b, 4
0x140005711  jnz     short loc_14000571E
0x140005713  mov     r8d, r14d
0x140005716  mov     rcx, rbx
0x140005719  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000571e  mov     al, dil
0x140005721  jmp     short loc_140005743
0x140005723  mov     rax, [rsp+48h+arg_20]
0x140005728  mov     r8d, edi
0x14000572b  mov     [rsp+48h+var_20], rax
0x140005730  mov     [rsp+48h+var_28], 0
0x140005739  call    wil_QueryFeatureState
0x14000573e  test    eax, eax
0x140005740  setnz   al
0x140005743  mov     rbx, [rsp+48h+arg_0]
0x140005748  mov     rbp, [rsp+48h+arg_8]
0x14000574d  add     rsp, 30h
0x140005751  pop     r14
0x140005753  pop     rdi
0x140005754  pop     rsi
0x140005755  retn
```
