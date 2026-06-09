# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x1800090fc`
- end: `0x1800091d5`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000af20`

## callees

- `0x1800085b4`
- `0x1800090fc`
- `0x18000ab04`
- `0x18000b740`

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
  unsigned int v10; // eax
  int v11; // r14d
  int v12; // eax
  int v13; // edx
  bool v14; // di
  char v15; // r8
  int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges((volatile signed __int32 *)v7, 0, v11);
    return v14;
  }
}

```

## disassembly

```asm
0x1800090fc  mov     [rsp+arg_0], rbx
0x180009101  mov     [rsp+arg_8], rbp
0x180009106  push    rsi
0x180009107  push    rdi
0x180009108  push    r14
0x18000910a  sub     rsp, 20h
0x18000910e  test    r9d, r9d
0x180009111  movzx   edi, r8b
0x180009115  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000911c  mov     esi, edx
0x18000911e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180009125  mov     rbp, rcx
0x180009128  cmovnz  rbx, rax
0x18000912c  mov     r9d, [rbx]
0x18000912f  mov     eax, r9d
0x180009132  and     al, 3
0x180009134  cmp     al, 2
0x180009136  jnz     short loc_18000913F
0x180009138  xor     al, al
0x18000913a  jmp     loc_1800091C2
0x18000913f  test    r9b, 2
0x180009143  jnz     short loc_1800091A7
0x180009145  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000914a  mov     rcx, [rsp+38h+arg_20]
0x18000914f  lea     r9, [rsp+38h+arg_18]
0x180009154  mov     r8d, edi
0x180009157  mov     [rsp+38h+arg_18], 0
0x18000915f  mov     edx, esi
0x180009161  mov     r14d, eax
0x180009164  mov     dword ptr [rcx], 1
0x18000916a  mov     rcx, rbp
0x18000916d  call    wil_RtlStagingConfig_QueryFeatureState
0x180009172  mov     edx, [rsp+38h+arg_18]
0x180009176  test    eax, eax
0x180009178  mov     ecx, edx
0x18000917a  setnz   dil
0x18000917e  neg     ecx
0x180009180  sbb     r8d, r8d
0x180009183  neg     r8d
0x180009186  add     r8d, 6
0x18000918a  xchg    r8d, [rbx]
0x18000918d  test    edx, edx
0x18000918f  jnz     short loc_1800091A2
0x180009191  test    r8b, 4
0x180009195  jnz     short loc_1800091A2
0x180009197  mov     r8d, r14d
0x18000919a  mov     rcx, rbx
0x18000919d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800091a2  mov     al, dil
0x1800091a5  jmp     short loc_1800091C2
0x1800091a7  mov     rax, [rsp+38h+arg_20]
0x1800091ac  mov     r8d, edi
0x1800091af  xor     r9d, r9d
0x1800091b2  mov     dword ptr [rax], 1
0x1800091b8  call    wil_RtlStagingConfig_QueryFeatureState
0x1800091bd  test    eax, eax
0x1800091bf  setnz   al
0x1800091c2  mov     rbx, [rsp+38h+arg_0]
0x1800091c7  mov     rbp, [rsp+38h+arg_8]
0x1800091cc  add     rsp, 20h
0x1800091d0  pop     r14
0x1800091d2  pop     rdi
0x1800091d3  pop     rsi
0x1800091d4  retn
```
