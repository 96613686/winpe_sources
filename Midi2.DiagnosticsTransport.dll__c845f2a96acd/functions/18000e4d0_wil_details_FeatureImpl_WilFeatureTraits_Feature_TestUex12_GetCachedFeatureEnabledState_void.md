# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e4d0`
- end: `0x18000e5a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102ec`

## callees

- `0x18000d6e0`
- `0x18000e4d0`
- `0x18000ed40`
- `0x18000ff38`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestUex12__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestUex12__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestUex12__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestUex12__descriptor,
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
0x18000e4d0  mov     [rsp+arg_10], rbx
0x18000e4d5  mov     [rsp+arg_0], rcx
0x18000e4da  push    rbp
0x18000e4db  push    rsi
0x18000e4dc  push    rdi
0x18000e4dd  sub     rsp, 20h
0x18000e4e1  mov     rsi, cs:Feature_TestUex12__descriptor
0x18000e4e8  mov     rdi, rdx
0x18000e4eb  mov     qword ptr [rdx], 0
0x18000e4f2  mov     eax, [rsi]
0x18000e4f4  mov     [rdx], eax
0x18000e4f6  and     eax, 6
0x18000e4f9  cmp     al, 6
0x18000e4fb  jz      loc_18000E599
0x18000e501  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e506  lea     r8, [rsp+38h+arg_0]
0x18000e50b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e513  lea     rdx, [rsp+38h+arg_8]
0x18000e518  mov     ebp, eax
0x18000e51a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x18000e51f  mov     eax, [rdi]
0x18000e521  mov     rbx, [rsp+38h+arg_8]
0x18000e526  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e52b  mov     edx, eax
0x18000e52d  mov     [rdi], eax
0x18000e52f  mov     ecx, eax
0x18000e531  jz      short loc_18000E54C
0x18000e533  test    dl, 2
0x18000e536  jnz     short loc_18000E54C
0x18000e538  and     ecx, 0FFFFF63Eh
0x18000e53e  mov     eax, ebx
0x18000e540  and     eax, 9C1h
0x18000e545  or      ecx, eax
0x18000e547  or      ecx, 2
0x18000e54a  mov     [rdi], ecx
0x18000e54c  mov     r8d, edx
0x18000e54f  and     r8d, 4
0x18000e553  jnz     short loc_18000E567
0x18000e555  btr     ecx, 0Ah
0x18000e559  mov     eax, ebx
0x18000e55b  and     eax, 400h
0x18000e560  or      ecx, eax
0x18000e562  or      ecx, 4
0x18000e565  mov     [rdi], ecx
0x18000e567  mov     eax, edx
0x18000e569  lock cmpxchg [rsi], ecx
0x18000e56d  jnz     short loc_18000E526
0x18000e56f  test    r8d, r8d
0x18000e572  jnz     short loc_18000E584
0x18000e574  mov     r8d, ebp
0x18000e577  mov     edx, 3
0x18000e57c  mov     rcx, rsi
0x18000e57f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e584  mov     eax, [rdi]
0x18000e586  test    al, 2
0x18000e588  jnz     short loc_18000E599
0x18000e58a  and     eax, 0FFFFF63Eh
0x18000e58f  and     ebx, 9C1h
0x18000e595  or      eax, ebx
0x18000e597  mov     [rdi], eax
0x18000e599  mov     rbx, [rsp+38h+arg_10]
0x18000e59e  mov     rax, rdi
0x18000e5a1  add     rsp, 20h
0x18000e5a5  pop     rdi
0x18000e5a6  pop     rsi
0x18000e5a7  pop     rbp
0x18000e5a8  retn
```
