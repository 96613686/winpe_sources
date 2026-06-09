# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCachedFeatureEnabledState(void)

- ea: `0x18001cd7c`
- end: `0x18001ce5b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001db60`

## callees

- `0x18000b284`
- `0x18000f6bc`
- `0x18001cd7c`
- `0x18001cf4c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // esi
  __int64 v6; // rcx
  signed __int32 i; // r8d
  bool v8; // zf
  unsigned int v9; // edx
  __int16 v10; // ax
  signed __int32 v11; // eax
  int v13; // [rsp+38h] [rbp+10h] BYREF
  __int64 v14; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UOvNext__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UOvNext__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v13 = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
    for ( i = *(_DWORD *)a2; ; i = v11 )
    {
      v8 = v13 == 0;
      v9 = i;
      v10 = v14;
      *(_DWORD *)a2 = i;
      if ( !v8 && (i & 2) == 0 )
      {
        v9 = v10 & 0x9C1 | i & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (i & 4) == 0 )
      {
        v9 = v10 & 0x400 | v9 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UOvNext__descriptor, v9, i);
      if ( i == v11 )
        break;
    }
    if ( (i & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UOvNext__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v14 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001cd7c  mov     [rsp+arg_0], rbx
0x18001cd81  mov     [rsp+arg_18], rsi
0x18001cd86  push    rdi
0x18001cd87  sub     rsp, 20h
0x18001cd8b  and     qword ptr [rdx], 0
0x18001cd8f  mov     rbx, rdx
0x18001cd92  mov     rdi, cs:Feature_UOvNext__descriptor
0x18001cd99  mov     eax, [rdi]
0x18001cd9b  mov     [rdx], eax
0x18001cd9d  and     eax, 6
0x18001cda0  cmp     al, 6
0x18001cda2  jz      loc_18001CE47
0x18001cda8  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001cdad  and     [rsp+28h+arg_8], 0
0x18001cdb2  lea     r8, [rsp+28h+arg_8]
0x18001cdb7  lea     rdx, [rsp+28h+arg_10]
0x18001cdbc  mov     esi, eax
0x18001cdbe  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UOvNext@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UOvNext>::GetCurrentFeatureEnabledState(int *)
0x18001cdc3  mov     r8d, [rbx]
0x18001cdc6  cmp     [rsp+28h+arg_8], 0
0x18001cdcb  mov     edx, r8d
0x18001cdce  mov     rax, [rsp+28h+arg_10]
0x18001cdd3  mov     [rbx], r8d
0x18001cdd6  jz      short loc_18001CDF3
0x18001cdd8  test    r8b, 2
0x18001cddc  jnz     short loc_18001CDF3
0x18001cdde  and     edx, 0FFFFF63Eh
0x18001cde4  mov     ecx, eax
0x18001cde6  and     ecx, 9C1h
0x18001cdec  or      edx, ecx
0x18001cdee  or      edx, 2
0x18001cdf1  mov     [rbx], edx
0x18001cdf3  test    r8b, 4
0x18001cdf7  jnz     short loc_18001CE09
0x18001cdf9  btr     edx, 0Ah
0x18001cdfd  and     eax, 400h
0x18001ce02  or      edx, eax
0x18001ce04  or      edx, 4
0x18001ce07  mov     [rbx], edx
0x18001ce09  mov     eax, r8d
0x18001ce0c  lock cmpxchg [rdi], edx
0x18001ce10  jz      short loc_18001CE17
0x18001ce12  mov     r8d, eax
0x18001ce15  jmp     short loc_18001CDC6
0x18001ce17  test    r8b, 4
0x18001ce1b  jnz     short loc_18001CE2D
0x18001ce1d  mov     r8d, esi
0x18001ce20  mov     edx, 3
0x18001ce25  mov     rcx, rdi
0x18001ce28  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ce2d  mov     ecx, [rbx]
0x18001ce2f  test    cl, 2
0x18001ce32  jnz     short loc_18001CE47
0x18001ce34  mov     eax, dword ptr [rsp+28h+arg_10]
0x18001ce38  and     ecx, 0FFFFF63Eh
0x18001ce3e  and     eax, 9C1h
0x18001ce43  or      ecx, eax
0x18001ce45  mov     [rbx], ecx
0x18001ce47  mov     rsi, [rsp+28h+arg_18]
0x18001ce4c  mov     rax, rbx
0x18001ce4f  mov     rbx, [rsp+28h+arg_0]
0x18001ce54  add     rsp, 20h
0x18001ce58  pop     rdi
0x18001ce59  retn
```
