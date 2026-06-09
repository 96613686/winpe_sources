# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x180036d48`
- end: `0x180036e33`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a144`
- `0x18003bf3c`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036d48`
- `0x1800374ac`
- `0x18003b548`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x180036d48  push    rbx
0x180036d4a  push    rbp
0x180036d4b  push    rsi
0x180036d4c  push    rdi
0x180036d4d  sub     rsp, 48h
0x180036d51  mov     rax, cs:__security_cookie
0x180036d58  xor     rax, rsp
0x180036d5b  mov     [rsp+68h+var_38], rax
0x180036d60  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x180036d67  mov     rdi, rdx
0x180036d6a  mov     qword ptr [rdx], 0
0x180036d71  mov     eax, [rsi]
0x180036d73  mov     [rdx], eax
0x180036d75  and     eax, 6
0x180036d78  cmp     al, 6
0x180036d7a  jz      loc_180036E1A
0x180036d80  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036d85  lea     r8, [rsp+68h+var_40]
0x180036d8a  mov     [rsp+68h+var_40], 0
0x180036d92  lea     rdx, [rsp+68h+var_48]
0x180036d97  mov     ebp, eax
0x180036d99  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180036d9e  mov     eax, [rdi]
0x180036da0  mov     rbx, [rsp+68h+var_48]
0x180036da5  cmp     [rsp+68h+var_40], 0
0x180036daa  mov     edx, eax
0x180036dac  mov     [rdi], eax
0x180036dae  mov     ecx, eax
0x180036db0  jz      short loc_180036DCB
0x180036db2  test    dl, 2
0x180036db5  jnz     short loc_180036DCB
0x180036db7  and     ecx, 0FFFFF63Eh
0x180036dbd  mov     eax, ebx
0x180036dbf  and     eax, 9C1h
0x180036dc4  or      ecx, eax
0x180036dc6  or      ecx, 2
0x180036dc9  mov     [rdi], ecx
0x180036dcb  mov     r8d, edx
0x180036dce  and     r8d, 4
0x180036dd2  jnz     short loc_180036DE6
0x180036dd4  btr     ecx, 0Ah
0x180036dd8  mov     eax, ebx
0x180036dda  and     eax, 400h
0x180036ddf  or      ecx, eax
0x180036de1  or      ecx, 4
0x180036de4  mov     [rdi], ecx
0x180036de6  mov     eax, edx
0x180036de8  lock cmpxchg [rsi], ecx
0x180036dec  jnz     short loc_180036DA5
0x180036dee  test    r8d, r8d
0x180036df1  jnz     short loc_180036E03
0x180036df3  mov     r8d, ebp
0x180036df6  mov     edx, 3
0x180036dfb  mov     rcx, rsi
0x180036dfe  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036e03  mov     ecx, [rdi]
0x180036e05  test    cl, 2
0x180036e08  jnz     short loc_180036E1A
0x180036e0a  and     ecx, 0FFFFF63Eh
0x180036e10  and     ebx, 9C1h
0x180036e16  or      ecx, ebx
0x180036e18  mov     [rdi], ecx
0x180036e1a  mov     rax, rdi
0x180036e1d  mov     rcx, [rsp+68h+var_38]
0x180036e22  xor     rcx, rsp; StackCookie
0x180036e25  call    __security_check_cookie
0x180036e2a  add     rsp, 48h
0x180036e2e  pop     rdi
0x180036e2f  pop     rsi
0x180036e30  pop     rbp
0x180036e31  pop     rbx
0x180036e32  retn
```
