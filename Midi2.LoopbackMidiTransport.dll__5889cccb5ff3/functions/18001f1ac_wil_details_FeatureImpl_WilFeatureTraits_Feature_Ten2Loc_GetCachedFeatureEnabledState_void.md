# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f1ac`
- end: `0x18001f285`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213c8`

## callees

- `0x18001e65c`
- `0x18001f1ac`
- `0x18001f86c`
- `0x180020fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001f1ac  mov     [rsp+arg_10], rbx
0x18001f1b1  mov     [rsp+arg_0], rcx
0x18001f1b6  push    rbp
0x18001f1b7  push    rsi
0x18001f1b8  push    rdi
0x18001f1b9  sub     rsp, 20h
0x18001f1bd  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18001f1c4  mov     rdi, rdx
0x18001f1c7  mov     qword ptr [rdx], 0
0x18001f1ce  mov     eax, [rsi]
0x18001f1d0  mov     [rdx], eax
0x18001f1d2  and     eax, 6
0x18001f1d5  cmp     al, 6
0x18001f1d7  jz      loc_18001F275
0x18001f1dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f1e2  lea     r8, [rsp+38h+arg_0]
0x18001f1e7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f1ef  lea     rdx, [rsp+38h+arg_8]
0x18001f1f4  mov     ebp, eax
0x18001f1f6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18001f1fb  mov     eax, [rdi]
0x18001f1fd  mov     rbx, [rsp+38h+arg_8]
0x18001f202  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f207  mov     edx, eax
0x18001f209  mov     [rdi], eax
0x18001f20b  mov     ecx, eax
0x18001f20d  jz      short loc_18001F228
0x18001f20f  test    dl, 2
0x18001f212  jnz     short loc_18001F228
0x18001f214  and     ecx, 0FFFFF63Eh
0x18001f21a  mov     eax, ebx
0x18001f21c  and     eax, 9C1h
0x18001f221  or      ecx, eax
0x18001f223  or      ecx, 2
0x18001f226  mov     [rdi], ecx
0x18001f228  mov     r8d, edx
0x18001f22b  and     r8d, 4
0x18001f22f  jnz     short loc_18001F243
0x18001f231  btr     ecx, 0Ah
0x18001f235  mov     eax, ebx
0x18001f237  and     eax, 400h
0x18001f23c  or      ecx, eax
0x18001f23e  or      ecx, 4
0x18001f241  mov     [rdi], ecx
0x18001f243  mov     eax, edx
0x18001f245  lock cmpxchg [rsi], ecx
0x18001f249  jnz     short loc_18001F202
0x18001f24b  test    r8d, r8d
0x18001f24e  jnz     short loc_18001F260
0x18001f250  mov     r8d, ebp
0x18001f253  mov     edx, 3
0x18001f258  mov     rcx, rsi
0x18001f25b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f260  mov     eax, [rdi]
0x18001f262  test    al, 2
0x18001f264  jnz     short loc_18001F275
0x18001f266  and     eax, 0FFFFF63Eh
0x18001f26b  and     ebx, 9C1h
0x18001f271  or      eax, ebx
0x18001f273  mov     [rdi], eax
0x18001f275  mov     rbx, [rsp+38h+arg_10]
0x18001f27a  mov     rax, rdi
0x18001f27d  add     rsp, 20h
0x18001f281  pop     rdi
0x18001f282  pop     rsi
0x18001f283  pop     rbp
0x18001f284  retn
```
