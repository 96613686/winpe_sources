# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ed84`
- end: `0x18000ee5d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013f48`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000ed84`
- `0x18000f594`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ed84  mov     [rsp+arg_10], rbx
0x18000ed89  mov     [rsp+arg_0], rcx
0x18000ed8e  push    rbp
0x18000ed8f  push    rsi
0x18000ed90  push    rdi
0x18000ed91  sub     rsp, 20h
0x18000ed95  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000ed9c  mov     rdi, rdx
0x18000ed9f  mov     qword ptr [rdx], 0
0x18000eda6  mov     eax, [rsi]
0x18000eda8  mov     [rdx], eax
0x18000edaa  and     eax, 6
0x18000edad  cmp     al, 6
0x18000edaf  jz      loc_18000EE4D
0x18000edb5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000edba  lea     r8, [rsp+38h+arg_0]
0x18000edbf  mov     dword ptr [rsp+38h+arg_0], 0
0x18000edc7  lea     rdx, [rsp+38h+arg_8]
0x18000edcc  mov     ebp, eax
0x18000edce  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000edd3  mov     eax, [rdi]
0x18000edd5  mov     rbx, [rsp+38h+arg_8]
0x18000edda  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000eddf  mov     edx, eax
0x18000ede1  mov     [rdi], eax
0x18000ede3  mov     ecx, eax
0x18000ede5  jz      short loc_18000EE00
0x18000ede7  test    dl, 2
0x18000edea  jnz     short loc_18000EE00
0x18000edec  and     ecx, 0FFFFF63Eh
0x18000edf2  mov     eax, ebx
0x18000edf4  and     eax, 9C1h
0x18000edf9  or      ecx, eax
0x18000edfb  or      ecx, 2
0x18000edfe  mov     [rdi], ecx
0x18000ee00  mov     r8d, edx
0x18000ee03  and     r8d, 4
0x18000ee07  jnz     short loc_18000EE1B
0x18000ee09  btr     ecx, 0Ah
0x18000ee0d  mov     eax, ebx
0x18000ee0f  and     eax, 400h
0x18000ee14  or      ecx, eax
0x18000ee16  or      ecx, 4
0x18000ee19  mov     [rdi], ecx
0x18000ee1b  mov     eax, edx
0x18000ee1d  lock cmpxchg [rsi], ecx
0x18000ee21  jnz     short loc_18000EDDA
0x18000ee23  test    r8d, r8d
0x18000ee26  jnz     short loc_18000EE38
0x18000ee28  mov     r8d, ebp
0x18000ee2b  mov     edx, 3
0x18000ee30  mov     rcx, rsi
0x18000ee33  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ee38  mov     eax, [rdi]
0x18000ee3a  test    al, 2
0x18000ee3c  jnz     short loc_18000EE4D
0x18000ee3e  and     eax, 0FFFFF63Eh
0x18000ee43  and     ebx, 9C1h
0x18000ee49  or      eax, ebx
0x18000ee4b  mov     [rdi], eax
0x18000ee4d  mov     rbx, [rsp+38h+arg_10]
0x18000ee52  mov     rax, rdi
0x18000ee55  add     rsp, 20h
0x18000ee59  pop     rdi
0x18000ee5a  pop     rsi
0x18000ee5b  pop     rbp
0x18000ee5c  retn
```
