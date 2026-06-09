# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c898`
- end: `0x18000c971`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cbec`
- `0x180017214`

## callees

- `0x1800085b4`
- `0x18000ab04`
- `0x18000c898`
- `0x18000ca40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_StoreUpdateTelemetryEvent__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_StoreUpdateTelemetryEvent__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_StoreUpdateTelemetryEvent__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_StoreUpdateTelemetryEvent__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c898  mov     [rsp+arg_10], rbx
0x18000c89d  mov     [rsp+arg_0], rcx
0x18000c8a2  push    rbp
0x18000c8a3  push    rsi
0x18000c8a4  push    rdi
0x18000c8a5  sub     rsp, 20h
0x18000c8a9  mov     rsi, cs:Feature_StoreUpdateTelemetryEvent__descriptor
0x18000c8b0  mov     rdi, rdx
0x18000c8b3  mov     qword ptr [rdx], 0
0x18000c8ba  mov     eax, [rsi]
0x18000c8bc  mov     [rdx], eax
0x18000c8be  and     eax, 6
0x18000c8c1  cmp     al, 6
0x18000c8c3  jz      loc_18000C961
0x18000c8c9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c8ce  lea     r8, [rsp+38h+arg_0]
0x18000c8d3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c8db  lea     rdx, [rsp+38h+arg_8]
0x18000c8e0  mov     ebp, eax
0x18000c8e2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCurrentFeatureEnabledState(int *)
0x18000c8e7  mov     eax, [rdi]
0x18000c8e9  mov     rbx, [rsp+38h+arg_8]
0x18000c8ee  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c8f3  mov     edx, eax
0x18000c8f5  mov     [rdi], eax
0x18000c8f7  mov     ecx, eax
0x18000c8f9  jz      short loc_18000C914
0x18000c8fb  test    dl, 2
0x18000c8fe  jnz     short loc_18000C914
0x18000c900  and     ecx, 0FFFFF63Eh
0x18000c906  mov     eax, ebx
0x18000c908  and     eax, 9C1h
0x18000c90d  or      ecx, eax
0x18000c90f  or      ecx, 2
0x18000c912  mov     [rdi], ecx
0x18000c914  mov     r8d, edx
0x18000c917  and     r8d, 4
0x18000c91b  jnz     short loc_18000C92F
0x18000c91d  btr     ecx, 0Ah
0x18000c921  mov     eax, ebx
0x18000c923  and     eax, 400h
0x18000c928  or      ecx, eax
0x18000c92a  or      ecx, 4
0x18000c92d  mov     [rdi], ecx
0x18000c92f  mov     eax, edx
0x18000c931  lock cmpxchg [rsi], ecx
0x18000c935  jnz     short loc_18000C8EE
0x18000c937  test    r8d, r8d
0x18000c93a  jnz     short loc_18000C94C
0x18000c93c  mov     r8d, ebp
0x18000c93f  mov     edx, 3
0x18000c944  mov     rcx, rsi
0x18000c947  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c94c  mov     eax, [rdi]
0x18000c94e  test    al, 2
0x18000c950  jnz     short loc_18000C961
0x18000c952  and     eax, 0FFFFF63Eh
0x18000c957  and     ebx, 9C1h
0x18000c95d  or      eax, ebx
0x18000c95f  mov     [rdi], eax
0x18000c961  mov     rbx, [rsp+38h+arg_10]
0x18000c966  mov     rax, rdi
0x18000c969  add     rsp, 20h
0x18000c96d  pop     rdi
0x18000c96e  pop     rsi
0x18000c96f  pop     rbp
0x18000c970  retn
```
