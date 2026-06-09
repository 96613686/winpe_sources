# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180008ad8`
- end: `0x180008bb1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a534`

## callees

- `0x1800085b4`
- `0x180008ad8`
- `0x180008eb4`
- `0x18000ab04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxLabTest__descriptor,
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
0x180008ad8  mov     [rsp+arg_10], rbx
0x180008add  mov     [rsp+arg_0], rcx
0x180008ae2  push    rbp
0x180008ae3  push    rsi
0x180008ae4  push    rdi
0x180008ae5  sub     rsp, 20h
0x180008ae9  mov     rsi, cs:Feature_UxLabTest__descriptor
0x180008af0  mov     rdi, rdx
0x180008af3  mov     qword ptr [rdx], 0
0x180008afa  mov     eax, [rsi]
0x180008afc  mov     [rdx], eax
0x180008afe  and     eax, 6
0x180008b01  cmp     al, 6
0x180008b03  jz      loc_180008BA1
0x180008b09  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008b0e  lea     r8, [rsp+38h+arg_0]
0x180008b13  mov     dword ptr [rsp+38h+arg_0], 0
0x180008b1b  lea     rdx, [rsp+38h+arg_8]
0x180008b20  mov     ebp, eax
0x180008b22  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(int *)
0x180008b27  mov     eax, [rdi]
0x180008b29  mov     rbx, [rsp+38h+arg_8]
0x180008b2e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008b33  mov     edx, eax
0x180008b35  mov     [rdi], eax
0x180008b37  mov     ecx, eax
0x180008b39  jz      short loc_180008B54
0x180008b3b  test    dl, 2
0x180008b3e  jnz     short loc_180008B54
0x180008b40  and     ecx, 0FFFFF63Eh
0x180008b46  mov     eax, ebx
0x180008b48  and     eax, 9C1h
0x180008b4d  or      ecx, eax
0x180008b4f  or      ecx, 2
0x180008b52  mov     [rdi], ecx
0x180008b54  mov     r8d, edx
0x180008b57  and     r8d, 4
0x180008b5b  jnz     short loc_180008B6F
0x180008b5d  btr     ecx, 0Ah
0x180008b61  mov     eax, ebx
0x180008b63  and     eax, 400h
0x180008b68  or      ecx, eax
0x180008b6a  or      ecx, 4
0x180008b6d  mov     [rdi], ecx
0x180008b6f  mov     eax, edx
0x180008b71  lock cmpxchg [rsi], ecx
0x180008b75  jnz     short loc_180008B2E
0x180008b77  test    r8d, r8d
0x180008b7a  jnz     short loc_180008B8C
0x180008b7c  mov     r8d, ebp
0x180008b7f  mov     edx, 3
0x180008b84  mov     rcx, rsi
0x180008b87  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008b8c  mov     eax, [rdi]
0x180008b8e  test    al, 2
0x180008b90  jnz     short loc_180008BA1
0x180008b92  and     eax, 0FFFFF63Eh
0x180008b97  and     ebx, 9C1h
0x180008b9d  or      eax, ebx
0x180008b9f  mov     [rdi], eax
0x180008ba1  mov     rbx, [rsp+38h+arg_10]
0x180008ba6  mov     rax, rdi
0x180008ba9  add     rsp, 20h
0x180008bad  pop     rdi
0x180008bae  pop     rsi
0x180008baf  pop     rbp
0x180008bb0  retn
```
