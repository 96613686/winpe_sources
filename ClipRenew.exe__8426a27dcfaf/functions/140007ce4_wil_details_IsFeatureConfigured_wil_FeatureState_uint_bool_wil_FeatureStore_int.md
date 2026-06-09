# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140007ce4`
- end: `0x140007dc6`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400118b0`

## callees

- `0x140006cac`
- `0x140007ce4`
- `0x1400114d4`
- `0x1400122e8`

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
0x140007ce4  mov     [rsp+arg_0], rbx
0x140007ce9  mov     [rsp+arg_8], rbp
0x140007cee  push    rsi
0x140007cef  push    rdi
0x140007cf0  push    r14
0x140007cf2  sub     rsp, 30h
0x140007cf6  test    r9d, r9d
0x140007cf9  movzx   edi, r8b
0x140007cfd  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140007d04  mov     esi, edx
0x140007d06  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140007d0d  mov     rbp, rcx
0x140007d10  cmovnz  rbx, rax
0x140007d14  mov     r9d, [rbx]
0x140007d17  mov     eax, r9d
0x140007d1a  and     al, 3
0x140007d1c  cmp     al, 2
0x140007d1e  jnz     short loc_140007D27
0x140007d20  xor     al, al
0x140007d22  jmp     loc_140007DB3
0x140007d27  test    r9b, 2
0x140007d2b  jnz     short loc_140007D93
0x140007d2d  mov     [rsp+48h+arg_18], 1
0x140007d35  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007d3a  mov     rcx, [rsp+48h+arg_20]
0x140007d3f  mov     r14d, eax
0x140007d42  mov     [rsp+48h+var_20], rcx
0x140007d47  lea     rax, [rsp+48h+arg_18]
0x140007d4c  mov     rcx, rbp
0x140007d4f  mov     [rsp+48h+var_28], rax
0x140007d54  mov     r8d, edi
0x140007d57  mov     edx, esi
0x140007d59  call    wil_QueryFeatureState
0x140007d5e  mov     edx, [rsp+48h+arg_18]
0x140007d62  test    eax, eax
0x140007d64  mov     ecx, edx
0x140007d66  setnz   dil
0x140007d6a  neg     ecx
0x140007d6c  sbb     r8d, r8d
0x140007d6f  neg     r8d
0x140007d72  add     r8d, 6
0x140007d76  xchg    r8d, [rbx]
0x140007d79  test    edx, edx
0x140007d7b  jnz     short loc_140007D8E
0x140007d7d  test    r8b, 4
0x140007d81  jnz     short loc_140007D8E
0x140007d83  mov     r8d, r14d
0x140007d86  mov     rcx, rbx
0x140007d89  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007d8e  mov     al, dil
0x140007d91  jmp     short loc_140007DB3
0x140007d93  mov     rax, [rsp+48h+arg_20]
0x140007d98  mov     r8d, edi
0x140007d9b  mov     [rsp+48h+var_20], rax
0x140007da0  mov     [rsp+48h+var_28], 0
0x140007da9  call    wil_QueryFeatureState
0x140007dae  test    eax, eax
0x140007db0  setnz   al
0x140007db3  mov     rbx, [rsp+48h+arg_0]
0x140007db8  mov     rbp, [rsp+48h+arg_8]
0x140007dbd  add     rsp, 30h
0x140007dc1  pop     r14
0x140007dc3  pop     rdi
0x140007dc4  pop     rsi
0x140007dc5  retn
```
