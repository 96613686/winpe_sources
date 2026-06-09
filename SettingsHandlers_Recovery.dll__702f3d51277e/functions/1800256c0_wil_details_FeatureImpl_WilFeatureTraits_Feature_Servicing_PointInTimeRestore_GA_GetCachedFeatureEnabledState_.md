# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(void)

- ea: `0x1800256c0`
- end: `0x180025799`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800263d4`

## callees

- `0x180005b50`
- `0x1800097b0`
- `0x1800256c0`
- `0x180025ad8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore_GA__descriptor,
             v9,
             v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore_GA__descriptor,
        3u,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800256c0  mov     [rsp+arg_10], rbx
0x1800256c5  mov     [rsp+arg_0], rcx
0x1800256ca  push    rbp
0x1800256cb  push    rsi
0x1800256cc  push    rdi
0x1800256cd  sub     rsp, 20h
0x1800256d1  mov     rsi, cs:Feature_Servicing_PointInTimeRestore_GA__descriptor
0x1800256d8  mov     rdi, rdx
0x1800256db  mov     qword ptr [rdx], 0
0x1800256e2  mov     eax, [rsi]
0x1800256e4  mov     [rdx], eax
0x1800256e6  and     eax, 6
0x1800256e9  cmp     al, 6
0x1800256eb  jz      loc_180025789
0x1800256f1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800256f6  lea     r8, [rsp+38h+arg_0]
0x1800256fb  mov     dword ptr [rsp+38h+arg_0], 0
0x180025703  lea     rdx, [rsp+38h+arg_8]
0x180025708  mov     ebp, eax
0x18002570a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(int *)
0x18002570f  mov     eax, [rdi]
0x180025711  mov     rbx, [rsp+38h+arg_8]
0x180025716  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002571b  mov     edx, eax
0x18002571d  mov     [rdi], eax
0x18002571f  mov     ecx, eax
0x180025721  jz      short loc_18002573C
0x180025723  test    dl, 2
0x180025726  jnz     short loc_18002573C
0x180025728  and     ecx, 0FFFFF63Eh
0x18002572e  mov     eax, ebx
0x180025730  and     eax, 9C1h
0x180025735  or      ecx, eax
0x180025737  or      ecx, 2
0x18002573a  mov     [rdi], ecx
0x18002573c  mov     r8d, edx
0x18002573f  and     r8d, 4
0x180025743  jnz     short loc_180025757
0x180025745  btr     ecx, 0Ah
0x180025749  mov     eax, ebx
0x18002574b  and     eax, 400h
0x180025750  or      ecx, eax
0x180025752  or      ecx, 4
0x180025755  mov     [rdi], ecx
0x180025757  mov     eax, edx
0x180025759  lock cmpxchg [rsi], ecx
0x18002575d  jnz     short loc_180025716
0x18002575f  test    r8d, r8d
0x180025762  jnz     short loc_180025774
0x180025764  mov     r8d, ebp
0x180025767  mov     edx, 3
0x18002576c  mov     rcx, rsi
0x18002576f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180025774  mov     eax, [rdi]
0x180025776  test    al, 2
0x180025778  jnz     short loc_180025789
0x18002577a  and     eax, 0FFFFF63Eh
0x18002577f  and     ebx, 9C1h
0x180025785  or      eax, ebx
0x180025787  mov     [rdi], eax
0x180025789  mov     rbx, [rsp+38h+arg_10]
0x18002578e  mov     rax, rdi
0x180025791  add     rsp, 20h
0x180025795  pop     rdi
0x180025796  pop     rsi
0x180025797  pop     rbp
0x180025798  retn
```
