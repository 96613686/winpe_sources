# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x14000a660`
- end: `0x14000a742`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d010`

## callees

- `0x140009018`
- `0x14000a660`
- `0x14000ca88`
- `0x14000db08`

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
0x14000a660  mov     [rsp+arg_0], rbx
0x14000a665  mov     [rsp+arg_8], rbp
0x14000a66a  push    rsi
0x14000a66b  push    rdi
0x14000a66c  push    r14
0x14000a66e  sub     rsp, 30h
0x14000a672  test    r9d, r9d
0x14000a675  movzx   edi, r8b
0x14000a679  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000a680  mov     esi, edx
0x14000a682  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x14000a689  mov     rbp, rcx
0x14000a68c  cmovnz  rbx, rax
0x14000a690  mov     r9d, [rbx]
0x14000a693  mov     eax, r9d
0x14000a696  and     al, 3
0x14000a698  cmp     al, 2
0x14000a69a  jnz     short loc_14000A6A3
0x14000a69c  xor     al, al
0x14000a69e  jmp     loc_14000A72F
0x14000a6a3  test    r9b, 2
0x14000a6a7  jnz     short loc_14000A70F
0x14000a6a9  mov     [rsp+48h+arg_18], 1
0x14000a6b1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a6b6  mov     rcx, [rsp+48h+arg_20]
0x14000a6bb  mov     r14d, eax
0x14000a6be  mov     [rsp+48h+var_20], rcx
0x14000a6c3  lea     rax, [rsp+48h+arg_18]
0x14000a6c8  mov     rcx, rbp
0x14000a6cb  mov     [rsp+48h+var_28], rax
0x14000a6d0  mov     r8d, edi
0x14000a6d3  mov     edx, esi
0x14000a6d5  call    wil_QueryFeatureState
0x14000a6da  mov     edx, [rsp+48h+arg_18]
0x14000a6de  test    eax, eax
0x14000a6e0  mov     ecx, edx
0x14000a6e2  setnz   dil
0x14000a6e6  neg     ecx
0x14000a6e8  sbb     r8d, r8d
0x14000a6eb  neg     r8d
0x14000a6ee  add     r8d, 6
0x14000a6f2  xchg    r8d, [rbx]
0x14000a6f5  test    edx, edx
0x14000a6f7  jnz     short loc_14000A70A
0x14000a6f9  test    r8b, 4
0x14000a6fd  jnz     short loc_14000A70A
0x14000a6ff  mov     r8d, r14d
0x14000a702  mov     rcx, rbx
0x14000a705  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a70a  mov     al, dil
0x14000a70d  jmp     short loc_14000A72F
0x14000a70f  mov     rax, [rsp+48h+arg_20]
0x14000a714  mov     r8d, edi
0x14000a717  mov     [rsp+48h+var_20], rax
0x14000a71c  mov     [rsp+48h+var_28], 0
0x14000a725  call    wil_QueryFeatureState
0x14000a72a  test    eax, eax
0x14000a72c  setnz   al
0x14000a72f  mov     rbx, [rsp+48h+arg_0]
0x14000a734  mov     rbp, [rsp+48h+arg_8]
0x14000a739  add     rsp, 30h
0x14000a73d  pop     r14
0x14000a73f  pop     rdi
0x14000a740  pop     rsi
0x14000a741  retn
```
