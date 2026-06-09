# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1400068c8`
- end: `0x1400069aa`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000a1a0`

## callees

- `0x140004d18`
- `0x1400068c8`
- `0x140009b34`
- `0x14000acd4`

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
  int v11; // r14d
  __int64 v12; // r9
  int v13; // eax
  int v14; // edx
  bool v15; // di
  char v16; // r8
  int v17; // [rsp+68h] [rbp+20h] BYREF

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
  if ( !v14 && (v16 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
  return v15;
}

```

## disassembly

```asm
0x1400068c8  mov     [rsp+arg_0], rbx
0x1400068cd  mov     [rsp+arg_8], rbp
0x1400068d2  push    rsi
0x1400068d3  push    rdi
0x1400068d4  push    r14
0x1400068d6  sub     rsp, 30h
0x1400068da  test    r9d, r9d
0x1400068dd  movzx   edi, r8b
0x1400068e1  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1400068e8  mov     esi, edx
0x1400068ea  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1400068f1  mov     rbp, rcx
0x1400068f4  cmovnz  rbx, rax
0x1400068f8  mov     r9d, [rbx]
0x1400068fb  mov     eax, r9d
0x1400068fe  and     al, 3
0x140006900  cmp     al, 2
0x140006902  jnz     short loc_14000690B
0x140006904  xor     al, al
0x140006906  jmp     loc_140006997
0x14000690b  test    r9b, 2
0x14000690f  jnz     short loc_140006977
0x140006911  mov     [rsp+48h+arg_18], 1
0x140006919  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000691e  mov     rcx, [rsp+48h+arg_20]
0x140006923  mov     r14d, eax
0x140006926  mov     [rsp+48h+var_20], rcx
0x14000692b  lea     rax, [rsp+48h+arg_18]
0x140006930  mov     rcx, rbp
0x140006933  mov     [rsp+48h+var_28], rax
0x140006938  mov     r8d, edi
0x14000693b  mov     edx, esi
0x14000693d  call    wil_QueryFeatureState
0x140006942  mov     edx, [rsp+48h+arg_18]
0x140006946  test    eax, eax
0x140006948  mov     ecx, edx
0x14000694a  setnz   dil
0x14000694e  neg     ecx
0x140006950  sbb     r8d, r8d
0x140006953  neg     r8d
0x140006956  add     r8d, 6
0x14000695a  xchg    r8d, [rbx]
0x14000695d  test    edx, edx
0x14000695f  jnz     short loc_140006972
0x140006961  test    r8b, 4
0x140006965  jnz     short loc_140006972
0x140006967  mov     r8d, r14d
0x14000696a  mov     rcx, rbx
0x14000696d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140006972  mov     al, dil
0x140006975  jmp     short loc_140006997
0x140006977  mov     rax, [rsp+48h+arg_20]
0x14000697c  mov     r8d, edi
0x14000697f  mov     [rsp+48h+var_20], rax
0x140006984  mov     [rsp+48h+var_28], 0
0x14000698d  call    wil_QueryFeatureState
0x140006992  test    eax, eax
0x140006994  setnz   al
0x140006997  mov     rbx, [rsp+48h+arg_0]
0x14000699c  mov     rbp, [rsp+48h+arg_8]
0x1400069a1  add     rsp, 30h
0x1400069a5  pop     r14
0x1400069a7  pop     rdi
0x1400069a8  pop     rsi
0x1400069a9  retn
```
