# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18002b258`
- end: `0x18002b33a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002f520`

## callees

- `0x180029a34`
- `0x18002b258`
- `0x18002ee7c`
- `0x180030c78`

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
0x18002b258  mov     [rsp+arg_0], rbx
0x18002b25d  mov     [rsp+arg_8], rbp
0x18002b262  push    rsi
0x18002b263  push    rdi
0x18002b264  push    r14
0x18002b266  sub     rsp, 30h
0x18002b26a  test    r9d, r9d
0x18002b26d  movzx   edi, r8b
0x18002b271  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18002b278  mov     esi, edx
0x18002b27a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18002b281  mov     rbp, rcx
0x18002b284  cmovnz  rbx, rax
0x18002b288  mov     r9d, [rbx]
0x18002b28b  mov     eax, r9d
0x18002b28e  and     al, 3
0x18002b290  cmp     al, 2
0x18002b292  jnz     short loc_18002B29B
0x18002b294  xor     al, al
0x18002b296  jmp     loc_18002B327
0x18002b29b  test    r9b, 2
0x18002b29f  jnz     short loc_18002B307
0x18002b2a1  mov     [rsp+48h+arg_18], 1
0x18002b2a9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002b2ae  mov     rcx, [rsp+48h+arg_20]
0x18002b2b3  mov     r14d, eax
0x18002b2b6  mov     [rsp+48h+var_20], rcx
0x18002b2bb  lea     rax, [rsp+48h+arg_18]
0x18002b2c0  mov     rcx, rbp
0x18002b2c3  mov     [rsp+48h+var_28], rax
0x18002b2c8  mov     r8d, edi
0x18002b2cb  mov     edx, esi
0x18002b2cd  call    wil_QueryFeatureState
0x18002b2d2  mov     edx, [rsp+48h+arg_18]
0x18002b2d6  test    eax, eax
0x18002b2d8  mov     ecx, edx
0x18002b2da  setnz   dil
0x18002b2de  neg     ecx
0x18002b2e0  sbb     r8d, r8d
0x18002b2e3  neg     r8d
0x18002b2e6  add     r8d, 6
0x18002b2ea  xchg    r8d, [rbx]
0x18002b2ed  test    edx, edx
0x18002b2ef  jnz     short loc_18002B302
0x18002b2f1  test    r8b, 4
0x18002b2f5  jnz     short loc_18002B302
0x18002b2f7  mov     r8d, r14d
0x18002b2fa  mov     rcx, rbx
0x18002b2fd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002b302  mov     al, dil
0x18002b305  jmp     short loc_18002B327
0x18002b307  mov     rax, [rsp+48h+arg_20]
0x18002b30c  mov     r8d, edi
0x18002b30f  mov     [rsp+48h+var_20], rax
0x18002b314  mov     [rsp+48h+var_28], 0
0x18002b31d  call    wil_QueryFeatureState
0x18002b322  test    eax, eax
0x18002b324  setnz   al
0x18002b327  mov     rbx, [rsp+48h+arg_0]
0x18002b32c  mov     rbp, [rsp+48h+arg_8]
0x18002b331  add     rsp, 30h
0x18002b335  pop     r14
0x18002b337  pop     rdi
0x18002b338  pop     rsi
0x18002b339  retn
```
