# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180006594`
- end: `0x180006676`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009610`

## callees

- `0x180005498`
- `0x180006594`
- `0x180008f34`
- `0x18000a1f8`

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
0x180006594  mov     [rsp+arg_0], rbx
0x180006599  mov     [rsp+arg_8], rbp
0x18000659e  push    rsi
0x18000659f  push    rdi
0x1800065a0  push    r14
0x1800065a2  sub     rsp, 30h
0x1800065a6  test    r9d, r9d
0x1800065a9  movzx   edi, r8b
0x1800065ad  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800065b4  mov     esi, edx
0x1800065b6  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800065bd  mov     rbp, rcx
0x1800065c0  cmovnz  rbx, rax
0x1800065c4  mov     r9d, [rbx]
0x1800065c7  mov     eax, r9d
0x1800065ca  and     al, 3
0x1800065cc  cmp     al, 2
0x1800065ce  jnz     short loc_1800065D7
0x1800065d0  xor     al, al
0x1800065d2  jmp     loc_180006663
0x1800065d7  test    r9b, 2
0x1800065db  jnz     short loc_180006643
0x1800065dd  mov     [rsp+48h+arg_18], 1
0x1800065e5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800065ea  mov     rcx, [rsp+48h+arg_20]
0x1800065ef  mov     r14d, eax
0x1800065f2  mov     [rsp+48h+var_20], rcx
0x1800065f7  lea     rax, [rsp+48h+arg_18]
0x1800065fc  mov     rcx, rbp
0x1800065ff  mov     [rsp+48h+var_28], rax
0x180006604  mov     r8d, edi
0x180006607  mov     edx, esi
0x180006609  call    wil_QueryFeatureState
0x18000660e  mov     edx, [rsp+48h+arg_18]
0x180006612  test    eax, eax
0x180006614  mov     ecx, edx
0x180006616  setnz   dil
0x18000661a  neg     ecx
0x18000661c  sbb     r8d, r8d
0x18000661f  neg     r8d
0x180006622  add     r8d, 6
0x180006626  xchg    r8d, [rbx]
0x180006629  test    edx, edx
0x18000662b  jnz     short loc_18000663E
0x18000662d  test    r8b, 4
0x180006631  jnz     short loc_18000663E
0x180006633  mov     r8d, r14d
0x180006636  mov     rcx, rbx
0x180006639  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000663e  mov     al, dil
0x180006641  jmp     short loc_180006663
0x180006643  mov     rax, [rsp+48h+arg_20]
0x180006648  mov     r8d, edi
0x18000664b  mov     [rsp+48h+var_20], rax
0x180006650  mov     [rsp+48h+var_28], 0
0x180006659  call    wil_QueryFeatureState
0x18000665e  test    eax, eax
0x180006660  setnz   al
0x180006663  mov     rbx, [rsp+48h+arg_0]
0x180006668  mov     rbp, [rsp+48h+arg_8]
0x18000666d  add     rsp, 30h
0x180006671  pop     r14
0x180006673  pop     rdi
0x180006674  pop     rsi
0x180006675  retn
```
