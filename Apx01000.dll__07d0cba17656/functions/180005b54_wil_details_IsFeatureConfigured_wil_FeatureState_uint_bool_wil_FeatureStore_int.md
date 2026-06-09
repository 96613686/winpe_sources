# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180005b54`
- end: `0x180005c36`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008a20`

## callees

- `0x180004a48`
- `0x180005b54`
- `0x180008344`
- `0x1800095f8`

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
0x180005b54  mov     [rsp+arg_0], rbx
0x180005b59  mov     [rsp+arg_8], rbp
0x180005b5e  push    rsi
0x180005b5f  push    rdi
0x180005b60  push    r14
0x180005b62  sub     rsp, 30h
0x180005b66  test    r9d, r9d
0x180005b69  movzx   edi, r8b
0x180005b6d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180005b74  mov     esi, edx
0x180005b76  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180005b7d  mov     rbp, rcx
0x180005b80  cmovnz  rbx, rax
0x180005b84  mov     r9d, [rbx]
0x180005b87  mov     eax, r9d
0x180005b8a  and     al, 3
0x180005b8c  cmp     al, 2
0x180005b8e  jnz     short loc_180005B97
0x180005b90  xor     al, al
0x180005b92  jmp     loc_180005C23
0x180005b97  test    r9b, 2
0x180005b9b  jnz     short loc_180005C03
0x180005b9d  mov     [rsp+48h+arg_18], 1
0x180005ba5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005baa  mov     rcx, [rsp+48h+arg_20]
0x180005baf  mov     r14d, eax
0x180005bb2  mov     [rsp+48h+var_20], rcx
0x180005bb7  lea     rax, [rsp+48h+arg_18]
0x180005bbc  mov     rcx, rbp
0x180005bbf  mov     [rsp+48h+var_28], rax
0x180005bc4  mov     r8d, edi
0x180005bc7  mov     edx, esi
0x180005bc9  call    wil_QueryFeatureState
0x180005bce  mov     edx, [rsp+48h+arg_18]
0x180005bd2  test    eax, eax
0x180005bd4  mov     ecx, edx
0x180005bd6  setnz   dil
0x180005bda  neg     ecx
0x180005bdc  sbb     r8d, r8d
0x180005bdf  neg     r8d
0x180005be2  add     r8d, 6
0x180005be6  xchg    r8d, [rbx]
0x180005be9  test    edx, edx
0x180005beb  jnz     short loc_180005BFE
0x180005bed  test    r8b, 4
0x180005bf1  jnz     short loc_180005BFE
0x180005bf3  mov     r8d, r14d
0x180005bf6  mov     rcx, rbx
0x180005bf9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005bfe  mov     al, dil
0x180005c01  jmp     short loc_180005C23
0x180005c03  mov     rax, [rsp+48h+arg_20]
0x180005c08  mov     r8d, edi
0x180005c0b  mov     [rsp+48h+var_20], rax
0x180005c10  mov     [rsp+48h+var_28], 0
0x180005c19  call    wil_QueryFeatureState
0x180005c1e  test    eax, eax
0x180005c20  setnz   al
0x180005c23  mov     rbx, [rsp+48h+arg_0]
0x180005c28  mov     rbp, [rsp+48h+arg_8]
0x180005c2d  add     rsp, 30h
0x180005c31  pop     r14
0x180005c33  pop     rdi
0x180005c34  pop     rsi
0x180005c35  retn
```
