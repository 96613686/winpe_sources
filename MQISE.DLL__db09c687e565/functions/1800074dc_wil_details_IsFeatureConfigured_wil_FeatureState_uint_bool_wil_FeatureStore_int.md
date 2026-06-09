# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800074dc`
- end: `0x1800075be`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000aab0`

## callees

- `0x180005a94`
- `0x1800074dc`
- `0x18000a048`
- `0x18000e368`

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
0x1800074dc  mov     [rsp+arg_0], rbx
0x1800074e1  mov     [rsp+arg_8], rbp
0x1800074e6  push    rsi
0x1800074e7  push    rdi
0x1800074e8  push    r14
0x1800074ea  sub     rsp, 30h
0x1800074ee  test    r9d, r9d
0x1800074f1  movzx   edi, r8b
0x1800074f5  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800074fc  mov     esi, edx
0x1800074fe  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007505  mov     rbp, rcx
0x180007508  cmovnz  rbx, rax
0x18000750c  mov     r9d, [rbx]
0x18000750f  mov     eax, r9d
0x180007512  and     al, 3
0x180007514  cmp     al, 2
0x180007516  jnz     short loc_18000751F
0x180007518  xor     al, al
0x18000751a  jmp     loc_1800075AB
0x18000751f  test    r9b, 2
0x180007523  jnz     short loc_18000758B
0x180007525  mov     [rsp+48h+arg_18], 1
0x18000752d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007532  mov     rcx, [rsp+48h+arg_20]
0x180007537  mov     r14d, eax
0x18000753a  mov     [rsp+48h+var_20], rcx
0x18000753f  lea     rax, [rsp+48h+arg_18]
0x180007544  mov     rcx, rbp
0x180007547  mov     [rsp+48h+var_28], rax
0x18000754c  mov     r8d, edi
0x18000754f  mov     edx, esi
0x180007551  call    wil_QueryFeatureState
0x180007556  mov     edx, [rsp+48h+arg_18]
0x18000755a  test    eax, eax
0x18000755c  mov     ecx, edx
0x18000755e  setnz   dil
0x180007562  neg     ecx
0x180007564  sbb     r8d, r8d
0x180007567  neg     r8d
0x18000756a  add     r8d, 6
0x18000756e  xchg    r8d, [rbx]
0x180007571  test    edx, edx
0x180007573  jnz     short loc_180007586
0x180007575  test    r8b, 4
0x180007579  jnz     short loc_180007586
0x18000757b  mov     r8d, r14d
0x18000757e  mov     rcx, rbx
0x180007581  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007586  mov     al, dil
0x180007589  jmp     short loc_1800075AB
0x18000758b  mov     rax, [rsp+48h+arg_20]
0x180007590  mov     r8d, edi
0x180007593  mov     [rsp+48h+var_20], rax
0x180007598  mov     [rsp+48h+var_28], 0
0x1800075a1  call    wil_QueryFeatureState
0x1800075a6  test    eax, eax
0x1800075a8  setnz   al
0x1800075ab  mov     rbx, [rsp+48h+arg_0]
0x1800075b0  mov     rbp, [rsp+48h+arg_8]
0x1800075b5  add     rsp, 30h
0x1800075b9  pop     r14
0x1800075bb  pop     rdi
0x1800075bc  pop     rsi
0x1800075bd  retn
```
