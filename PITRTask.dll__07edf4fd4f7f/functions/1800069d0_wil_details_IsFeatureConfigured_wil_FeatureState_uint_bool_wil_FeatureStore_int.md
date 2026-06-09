# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800069d0`
- end: `0x180006ab2`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009ec0`

## callees

- `0x180004f64`
- `0x1800069d0`
- `0x180009800`
- `0x18000c8f8`

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
0x1800069d0  mov     [rsp+arg_0], rbx
0x1800069d5  mov     [rsp+arg_8], rbp
0x1800069da  push    rsi
0x1800069db  push    rdi
0x1800069dc  push    r14
0x1800069de  sub     rsp, 30h
0x1800069e2  test    r9d, r9d
0x1800069e5  movzx   edi, r8b
0x1800069e9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x1800069f0  mov     esi, edx
0x1800069f2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800069f9  mov     rbp, rcx
0x1800069fc  cmovnz  rbx, rax
0x180006a00  mov     r9d, [rbx]
0x180006a03  mov     eax, r9d
0x180006a06  and     al, 3
0x180006a08  cmp     al, 2
0x180006a0a  jnz     short loc_180006A13
0x180006a0c  xor     al, al
0x180006a0e  jmp     loc_180006A9F
0x180006a13  test    r9b, 2
0x180006a17  jnz     short loc_180006A7F
0x180006a19  mov     [rsp+48h+arg_18], 1
0x180006a21  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006a26  mov     rcx, [rsp+48h+arg_20]
0x180006a2b  mov     r14d, eax
0x180006a2e  mov     [rsp+48h+var_20], rcx
0x180006a33  lea     rax, [rsp+48h+arg_18]
0x180006a38  mov     rcx, rbp
0x180006a3b  mov     [rsp+48h+var_28], rax
0x180006a40  mov     r8d, edi
0x180006a43  mov     edx, esi
0x180006a45  call    wil_QueryFeatureState
0x180006a4a  mov     edx, [rsp+48h+arg_18]
0x180006a4e  test    eax, eax
0x180006a50  mov     ecx, edx
0x180006a52  setnz   dil
0x180006a56  neg     ecx
0x180006a58  sbb     r8d, r8d
0x180006a5b  neg     r8d
0x180006a5e  add     r8d, 6
0x180006a62  xchg    r8d, [rbx]
0x180006a65  test    edx, edx
0x180006a67  jnz     short loc_180006A7A
0x180006a69  test    r8b, 4
0x180006a6d  jnz     short loc_180006A7A
0x180006a6f  mov     r8d, r14d
0x180006a72  mov     rcx, rbx
0x180006a75  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006a7a  mov     al, dil
0x180006a7d  jmp     short loc_180006A9F
0x180006a7f  mov     rax, [rsp+48h+arg_20]
0x180006a84  mov     r8d, edi
0x180006a87  mov     [rsp+48h+var_20], rax
0x180006a8c  mov     [rsp+48h+var_28], 0
0x180006a95  call    wil_QueryFeatureState
0x180006a9a  test    eax, eax
0x180006a9c  setnz   al
0x180006a9f  mov     rbx, [rsp+48h+arg_0]
0x180006aa4  mov     rbp, [rsp+48h+arg_8]
0x180006aa9  add     rsp, 30h
0x180006aad  pop     r14
0x180006aaf  pop     rdi
0x180006ab0  pop     rsi
0x180006ab1  retn
```
