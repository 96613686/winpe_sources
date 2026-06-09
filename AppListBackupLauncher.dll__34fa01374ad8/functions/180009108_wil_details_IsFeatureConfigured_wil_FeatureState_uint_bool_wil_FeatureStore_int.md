# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180009108`
- end: `0x1800091ea`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `226`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000da70`

## callees

- `0x180007854`
- `0x180009108`
- `0x18000d31c`
- `0x18000fc88`

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
0x180009108  mov     [rsp+arg_0], rbx
0x18000910d  mov     [rsp+arg_8], rbp
0x180009112  push    rsi
0x180009113  push    rdi
0x180009114  push    r14
0x180009116  sub     rsp, 30h
0x18000911a  test    r9d, r9d
0x18000911d  movzx   edi, r8b
0x180009121  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180009128  mov     esi, edx
0x18000912a  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180009131  mov     rbp, rcx
0x180009134  cmovnz  rbx, rax
0x180009138  mov     r9d, [rbx]
0x18000913b  mov     eax, r9d
0x18000913e  and     al, 3
0x180009140  cmp     al, 2
0x180009142  jnz     short loc_18000914B
0x180009144  xor     al, al
0x180009146  jmp     loc_1800091D7
0x18000914b  test    r9b, 2
0x18000914f  jnz     short loc_1800091B7
0x180009151  mov     [rsp+48h+arg_18], 1
0x180009159  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000915e  mov     rcx, [rsp+48h+arg_20]
0x180009163  mov     r14d, eax
0x180009166  mov     [rsp+48h+var_20], rcx
0x18000916b  lea     rax, [rsp+48h+arg_18]
0x180009170  mov     rcx, rbp
0x180009173  mov     [rsp+48h+var_28], rax
0x180009178  mov     r8d, edi
0x18000917b  mov     edx, esi
0x18000917d  call    wil_QueryFeatureState
0x180009182  mov     edx, [rsp+48h+arg_18]
0x180009186  test    eax, eax
0x180009188  mov     ecx, edx
0x18000918a  setnz   dil
0x18000918e  neg     ecx
0x180009190  sbb     r8d, r8d
0x180009193  neg     r8d
0x180009196  add     r8d, 6
0x18000919a  xchg    r8d, [rbx]
0x18000919d  test    edx, edx
0x18000919f  jnz     short loc_1800091B2
0x1800091a1  test    r8b, 4
0x1800091a5  jnz     short loc_1800091B2
0x1800091a7  mov     r8d, r14d
0x1800091aa  mov     rcx, rbx
0x1800091ad  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800091b2  mov     al, dil
0x1800091b5  jmp     short loc_1800091D7
0x1800091b7  mov     rax, [rsp+48h+arg_20]
0x1800091bc  mov     r8d, edi
0x1800091bf  mov     [rsp+48h+var_20], rax
0x1800091c4  mov     [rsp+48h+var_28], 0
0x1800091cd  call    wil_QueryFeatureState
0x1800091d2  test    eax, eax
0x1800091d4  setnz   al
0x1800091d7  mov     rbx, [rsp+48h+arg_0]
0x1800091dc  mov     rbp, [rsp+48h+arg_8]
0x1800091e1  add     rsp, 30h
0x1800091e5  pop     r14
0x1800091e7  pop     rdi
0x1800091e8  pop     rsi
0x1800091e9  retn
```
