# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140010084`
- end: `0x140010166`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140012d20`

## callees

- `0x14000e738`
- `0x140010084`
- `0x1400121c4`
- `0x1400135a8`

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
0x140010084  mov     [rsp+arg_0], rbx
0x140010089  mov     [rsp+arg_8], rbp
0x14001008e  push    rsi
0x14001008f  push    rdi
0x140010090  push    r14
0x140010092  sub     rsp, 30h
0x140010096  test    r9d, r9d
0x140010099  movzx   edi, r8b
0x14001009d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1400100a4  mov     esi, edx
0x1400100a6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1400100ad  mov     rbp, rcx
0x1400100b0  cmovnz  rbx, rax
0x1400100b4  mov     r9d, [rbx]
0x1400100b7  mov     eax, r9d
0x1400100ba  and     al, 3
0x1400100bc  cmp     al, 2
0x1400100be  jnz     short loc_1400100C7
0x1400100c0  xor     al, al
0x1400100c2  jmp     loc_140010153
0x1400100c7  test    r9b, 2
0x1400100cb  jnz     short loc_140010133
0x1400100cd  mov     [rsp+48h+arg_18], 1
0x1400100d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400100da  mov     rcx, [rsp+48h+arg_20]
0x1400100df  mov     r14d, eax
0x1400100e2  mov     [rsp+48h+var_20], rcx
0x1400100e7  lea     rax, [rsp+48h+arg_18]
0x1400100ec  mov     rcx, rbp
0x1400100ef  mov     [rsp+48h+var_28], rax
0x1400100f4  mov     r8d, edi
0x1400100f7  mov     edx, esi
0x1400100f9  call    wil_QueryFeatureState
0x1400100fe  mov     edx, [rsp+48h+arg_18]
0x140010102  test    eax, eax
0x140010104  mov     ecx, edx
0x140010106  setnz   dil
0x14001010a  neg     ecx
0x14001010c  sbb     r8d, r8d
0x14001010f  neg     r8d
0x140010112  add     r8d, 6
0x140010116  xchg    r8d, [rbx]
0x140010119  test    edx, edx
0x14001011b  jnz     short loc_14001012E
0x14001011d  test    r8b, 4
0x140010121  jnz     short loc_14001012E
0x140010123  mov     r8d, r14d
0x140010126  mov     rcx, rbx
0x140010129  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001012e  mov     al, dil
0x140010131  jmp     short loc_140010153
0x140010133  mov     rax, [rsp+48h+arg_20]
0x140010138  mov     r8d, edi
0x14001013b  mov     [rsp+48h+var_20], rax
0x140010140  mov     [rsp+48h+var_28], 0
0x140010149  call    wil_QueryFeatureState
0x14001014e  test    eax, eax
0x140010150  setnz   al
0x140010153  mov     rbx, [rsp+48h+arg_0]
0x140010158  mov     rbp, [rsp+48h+arg_8]
0x14001015d  add     rsp, 30h
0x140010161  pop     r14
0x140010163  pop     rdi
0x140010164  pop     rsi
0x140010165  retn
```
