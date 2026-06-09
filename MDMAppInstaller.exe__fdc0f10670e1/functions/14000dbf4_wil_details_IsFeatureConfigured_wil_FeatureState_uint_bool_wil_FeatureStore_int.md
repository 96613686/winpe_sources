# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x14000dbf4`
- end: `0x14000dcdb`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `231`
- prototype: `bool __fastcall(wil::details *, int, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011250`

## callees

- `0x14000b36c`
- `0x14000dbf4`
- `0x140010e28`
- `0x1400133b4`

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
  __int64 v14; // r8
  bool v15; // di
  char v16; // dl
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
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      &wil::details::g_enabledStateManager,
      v7,
      v14,
      v11);
  return v15;
}

```

## disassembly

```asm
0x14000dbf4  mov     [rsp+arg_0], rbx
0x14000dbf9  mov     [rsp+arg_8], rbp
0x14000dbfe  push    rsi
0x14000dbff  push    rdi
0x14000dc00  push    r14
0x14000dc02  sub     rsp, 30h
0x14000dc06  test    r9d, r9d
0x14000dc09  movzx   edi, r8b
0x14000dc0d  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x14000dc14  mov     esi, edx
0x14000dc16  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x14000dc1d  mov     rbp, rcx
0x14000dc20  cmovnz  rbx, rax
0x14000dc24  mov     r9d, [rbx]
0x14000dc27  mov     eax, r9d
0x14000dc2a  and     al, 3
0x14000dc2c  cmp     al, 2
0x14000dc2e  jnz     short loc_14000DC37
0x14000dc30  xor     al, al
0x14000dc32  jmp     loc_14000DCC8
0x14000dc37  test    r9b, 2
0x14000dc3b  jnz     short loc_14000DCA8
0x14000dc3d  mov     [rsp+48h+arg_18], 1
0x14000dc45  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000dc4a  mov     rcx, [rsp+48h+arg_20]
0x14000dc4f  mov     r14d, eax
0x14000dc52  mov     [rsp+48h+var_20], rcx
0x14000dc57  lea     rax, [rsp+48h+arg_18]
0x14000dc5c  mov     rcx, rbp
0x14000dc5f  mov     [rsp+48h+var_28], rax
0x14000dc64  mov     r8d, edi
0x14000dc67  mov     edx, esi
0x14000dc69  call    wil_QueryFeatureState
0x14000dc6e  mov     r8d, [rsp+48h+arg_18]
0x14000dc73  test    eax, eax
0x14000dc75  mov     ecx, r8d
0x14000dc78  setnz   dil
0x14000dc7c  neg     ecx
0x14000dc7e  sbb     edx, edx
0x14000dc80  neg     edx
0x14000dc82  add     edx, 6
0x14000dc85  xchg    edx, [rbx]
0x14000dc87  test    r8d, r8d
0x14000dc8a  jnz     short loc_14000DCA3
0x14000dc8c  test    dl, 4
0x14000dc8f  jnz     short loc_14000DCA3
0x14000dc91  mov     r9d, r14d
0x14000dc94  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000dc9b  mov     rdx, rbx
0x14000dc9e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000dca3  mov     al, dil
0x14000dca6  jmp     short loc_14000DCC8
0x14000dca8  mov     rax, [rsp+48h+arg_20]
0x14000dcad  mov     r8d, edi
0x14000dcb0  mov     [rsp+48h+var_20], rax
0x14000dcb5  mov     [rsp+48h+var_28], 0
0x14000dcbe  call    wil_QueryFeatureState
0x14000dcc3  test    eax, eax
0x14000dcc5  setnz   al
0x14000dcc8  mov     rbx, [rsp+48h+arg_0]
0x14000dccd  mov     rbp, [rsp+48h+arg_8]
0x14000dcd2  add     rsp, 30h
0x14000dcd6  pop     r14
0x14000dcd8  pop     rdi
0x14000dcd9  pop     rsi
0x14000dcda  retn
```
