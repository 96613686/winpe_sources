# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCachedFeatureEnabledState(void)

- ea: `0x180013bd8`
- end: `0x180013cb1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017890`

## callees

- `0x180005498`
- `0x180008f34`
- `0x180013bd8`
- `0x180014234`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_NetshInterface__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_NetshInterface__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_CLAT_Preview2_NetshInterface__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_CLAT_Preview2_NetshInterface__descriptor,
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
0x180013bd8  mov     [rsp+arg_10], rbx
0x180013bdd  mov     [rsp+arg_0], rcx
0x180013be2  push    rbp
0x180013be3  push    rsi
0x180013be4  push    rdi
0x180013be5  sub     rsp, 20h
0x180013be9  mov     rsi, cs:Feature_CLAT_Preview2_NetshInterface__descriptor
0x180013bf0  mov     rdi, rdx
0x180013bf3  mov     qword ptr [rdx], 0
0x180013bfa  mov     eax, [rsi]
0x180013bfc  mov     [rdx], eax
0x180013bfe  and     eax, 6
0x180013c01  cmp     al, 6
0x180013c03  jz      loc_180013CA1
0x180013c09  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013c0e  lea     r8, [rsp+38h+arg_0]
0x180013c13  mov     dword ptr [rsp+38h+arg_0], 0
0x180013c1b  lea     rdx, [rsp+38h+arg_8]
0x180013c20  mov     ebp, eax
0x180013c22  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCurrentFeatureEnabledState(int *)
0x180013c27  mov     eax, [rdi]
0x180013c29  mov     rbx, [rsp+38h+arg_8]
0x180013c2e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013c33  mov     edx, eax
0x180013c35  mov     [rdi], eax
0x180013c37  mov     ecx, eax
0x180013c39  jz      short loc_180013C54
0x180013c3b  test    dl, 2
0x180013c3e  jnz     short loc_180013C54
0x180013c40  and     ecx, 0FFFFF63Eh
0x180013c46  mov     eax, ebx
0x180013c48  and     eax, 9C1h
0x180013c4d  or      ecx, eax
0x180013c4f  or      ecx, 2
0x180013c52  mov     [rdi], ecx
0x180013c54  mov     r8d, edx
0x180013c57  and     r8d, 4
0x180013c5b  jnz     short loc_180013C6F
0x180013c5d  btr     ecx, 0Ah
0x180013c61  mov     eax, ebx
0x180013c63  and     eax, 400h
0x180013c68  or      ecx, eax
0x180013c6a  or      ecx, 4
0x180013c6d  mov     [rdi], ecx
0x180013c6f  mov     eax, edx
0x180013c71  lock cmpxchg [rsi], ecx
0x180013c75  jnz     short loc_180013C2E
0x180013c77  test    r8d, r8d
0x180013c7a  jnz     short loc_180013C8C
0x180013c7c  mov     r8d, ebp
0x180013c7f  mov     edx, 3
0x180013c84  mov     rcx, rsi
0x180013c87  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013c8c  mov     eax, [rdi]
0x180013c8e  test    al, 2
0x180013c90  jnz     short loc_180013CA1
0x180013c92  and     eax, 0FFFFF63Eh
0x180013c97  and     ebx, 9C1h
0x180013c9d  or      eax, ebx
0x180013c9f  mov     [rdi], eax
0x180013ca1  mov     rbx, [rsp+38h+arg_10]
0x180013ca6  mov     rax, rdi
0x180013ca9  add     rsp, 20h
0x180013cad  pop     rdi
0x180013cae  pop     rsi
0x180013caf  pop     rbp
0x180013cb0  retn
```
