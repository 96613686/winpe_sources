# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000c3a0`
- end: `0x18000c482`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f5d0`

## callees

- `0x18000ace8`
- `0x18000c3a0`
- `0x18000eed4`
- `0x180010198`

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
0x18000c3a0  mov     [rsp+arg_0], rbx
0x18000c3a5  mov     [rsp+arg_8], rbp
0x18000c3aa  push    rsi
0x18000c3ab  push    rdi
0x18000c3ac  push    r14
0x18000c3ae  sub     rsp, 30h
0x18000c3b2  test    r9d, r9d
0x18000c3b5  movzx   edi, r8b
0x18000c3b9  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000c3c0  mov     esi, edx
0x18000c3c2  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18000c3c9  mov     rbp, rcx
0x18000c3cc  cmovnz  rbx, rax
0x18000c3d0  mov     r9d, [rbx]
0x18000c3d3  mov     eax, r9d
0x18000c3d6  and     al, 3
0x18000c3d8  cmp     al, 2
0x18000c3da  jnz     short loc_18000C3E3
0x18000c3dc  xor     al, al
0x18000c3de  jmp     loc_18000C46F
0x18000c3e3  test    r9b, 2
0x18000c3e7  jnz     short loc_18000C44F
0x18000c3e9  mov     [rsp+48h+arg_18], 1
0x18000c3f1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c3f6  mov     rcx, [rsp+48h+arg_20]
0x18000c3fb  mov     r14d, eax
0x18000c3fe  mov     [rsp+48h+var_20], rcx
0x18000c403  lea     rax, [rsp+48h+arg_18]
0x18000c408  mov     rcx, rbp
0x18000c40b  mov     [rsp+48h+var_28], rax
0x18000c410  mov     r8d, edi
0x18000c413  mov     edx, esi
0x18000c415  call    wil_QueryFeatureState
0x18000c41a  mov     edx, [rsp+48h+arg_18]
0x18000c41e  test    eax, eax
0x18000c420  mov     ecx, edx
0x18000c422  setnz   dil
0x18000c426  neg     ecx
0x18000c428  sbb     r8d, r8d
0x18000c42b  neg     r8d
0x18000c42e  add     r8d, 6
0x18000c432  xchg    r8d, [rbx]
0x18000c435  test    edx, edx
0x18000c437  jnz     short loc_18000C44A
0x18000c439  test    r8b, 4
0x18000c43d  jnz     short loc_18000C44A
0x18000c43f  mov     r8d, r14d
0x18000c442  mov     rcx, rbx
0x18000c445  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c44a  mov     al, dil
0x18000c44d  jmp     short loc_18000C46F
0x18000c44f  mov     rax, [rsp+48h+arg_20]
0x18000c454  mov     r8d, edi
0x18000c457  mov     [rsp+48h+var_20], rax
0x18000c45c  mov     [rsp+48h+var_28], 0
0x18000c465  call    wil_QueryFeatureState
0x18000c46a  test    eax, eax
0x18000c46c  setnz   al
0x18000c46f  mov     rbx, [rsp+48h+arg_0]
0x18000c474  mov     rbp, [rsp+48h+arg_8]
0x18000c479  add     rsp, 30h
0x18000c47d  pop     r14
0x18000c47f  pop     rdi
0x18000c480  pop     rsi
0x18000c481  retn
```
