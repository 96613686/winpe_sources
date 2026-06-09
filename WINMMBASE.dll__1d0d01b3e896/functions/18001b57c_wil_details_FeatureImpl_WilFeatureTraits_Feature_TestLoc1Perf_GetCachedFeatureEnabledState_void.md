# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001b57c`
- end: `0x18001b655`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c638`
- `0x18001c924`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001b57c`
- `0x18001be2c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
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
0x18001b57c  mov     [rsp+arg_10], rbx
0x18001b581  mov     [rsp+arg_0], rcx
0x18001b586  push    rbp
0x18001b587  push    rsi
0x18001b588  push    rdi
0x18001b589  sub     rsp, 20h
0x18001b58d  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18001b594  mov     rdi, rdx
0x18001b597  mov     qword ptr [rdx], 0
0x18001b59e  mov     eax, [rsi]
0x18001b5a0  mov     [rdx], eax
0x18001b5a2  and     eax, 6
0x18001b5a5  cmp     al, 6
0x18001b5a7  jz      loc_18001B645
0x18001b5ad  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001b5b2  lea     r8, [rsp+38h+arg_0]
0x18001b5b7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b5bf  lea     rdx, [rsp+38h+arg_8]
0x18001b5c4  mov     ebp, eax
0x18001b5c6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18001b5cb  mov     eax, [rdi]
0x18001b5cd  mov     rbx, [rsp+38h+arg_8]
0x18001b5d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001b5d7  mov     edx, eax
0x18001b5d9  mov     [rdi], eax
0x18001b5db  mov     ecx, eax
0x18001b5dd  jz      short loc_18001B5F8
0x18001b5df  test    dl, 2
0x18001b5e2  jnz     short loc_18001B5F8
0x18001b5e4  and     ecx, 0FFFFF63Eh
0x18001b5ea  mov     eax, ebx
0x18001b5ec  and     eax, 9C1h
0x18001b5f1  or      ecx, eax
0x18001b5f3  or      ecx, 2
0x18001b5f6  mov     [rdi], ecx
0x18001b5f8  mov     r8d, edx
0x18001b5fb  and     r8d, 4
0x18001b5ff  jnz     short loc_18001B613
0x18001b601  btr     ecx, 0Ah
0x18001b605  mov     eax, ebx
0x18001b607  and     eax, 400h
0x18001b60c  or      ecx, eax
0x18001b60e  or      ecx, 4
0x18001b611  mov     [rdi], ecx
0x18001b613  mov     eax, edx
0x18001b615  lock cmpxchg [rsi], ecx
0x18001b619  jnz     short loc_18001B5D2
0x18001b61b  test    r8d, r8d
0x18001b61e  jnz     short loc_18001B630
0x18001b620  mov     r8d, ebp
0x18001b623  mov     edx, 3
0x18001b628  mov     rcx, rsi
0x18001b62b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b630  mov     eax, [rdi]
0x18001b632  test    al, 2
0x18001b634  jnz     short loc_18001B645
0x18001b636  and     eax, 0FFFFF63Eh
0x18001b63b  and     ebx, 9C1h
0x18001b641  or      eax, ebx
0x18001b643  mov     [rdi], eax
0x18001b645  mov     rbx, [rsp+38h+arg_10]
0x18001b64a  mov     rax, rdi
0x18001b64d  add     rsp, 20h
0x18001b651  pop     rdi
0x18001b652  pop     rsi
0x18001b653  pop     rbp
0x18001b654  retn
```
