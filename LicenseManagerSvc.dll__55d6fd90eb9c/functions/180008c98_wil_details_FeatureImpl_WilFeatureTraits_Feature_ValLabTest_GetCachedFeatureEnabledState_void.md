# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180008c98`
- end: `0x180008d71`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a640`

## callees

- `0x1800085b4`
- `0x180008c98`
- `0x180008ffc`
- `0x18000ab04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x180008c98  mov     [rsp+arg_10], rbx
0x180008c9d  mov     [rsp+arg_0], rcx
0x180008ca2  push    rbp
0x180008ca3  push    rsi
0x180008ca4  push    rdi
0x180008ca5  sub     rsp, 20h
0x180008ca9  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180008cb0  mov     rdi, rdx
0x180008cb3  mov     qword ptr [rdx], 0
0x180008cba  mov     eax, [rsi]
0x180008cbc  mov     [rdx], eax
0x180008cbe  and     eax, 6
0x180008cc1  cmp     al, 6
0x180008cc3  jz      loc_180008D61
0x180008cc9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008cce  lea     r8, [rsp+38h+arg_0]
0x180008cd3  mov     dword ptr [rsp+38h+arg_0], 0
0x180008cdb  lea     rdx, [rsp+38h+arg_8]
0x180008ce0  mov     ebp, eax
0x180008ce2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180008ce7  mov     eax, [rdi]
0x180008ce9  mov     rbx, [rsp+38h+arg_8]
0x180008cee  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008cf3  mov     edx, eax
0x180008cf5  mov     [rdi], eax
0x180008cf7  mov     ecx, eax
0x180008cf9  jz      short loc_180008D14
0x180008cfb  test    dl, 2
0x180008cfe  jnz     short loc_180008D14
0x180008d00  and     ecx, 0FFFFF63Eh
0x180008d06  mov     eax, ebx
0x180008d08  and     eax, 9C1h
0x180008d0d  or      ecx, eax
0x180008d0f  or      ecx, 2
0x180008d12  mov     [rdi], ecx
0x180008d14  mov     r8d, edx
0x180008d17  and     r8d, 4
0x180008d1b  jnz     short loc_180008D2F
0x180008d1d  btr     ecx, 0Ah
0x180008d21  mov     eax, ebx
0x180008d23  and     eax, 400h
0x180008d28  or      ecx, eax
0x180008d2a  or      ecx, 4
0x180008d2d  mov     [rdi], ecx
0x180008d2f  mov     eax, edx
0x180008d31  lock cmpxchg [rsi], ecx
0x180008d35  jnz     short loc_180008CEE
0x180008d37  test    r8d, r8d
0x180008d3a  jnz     short loc_180008D4C
0x180008d3c  mov     r8d, ebp
0x180008d3f  mov     edx, 3
0x180008d44  mov     rcx, rsi
0x180008d47  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008d4c  mov     eax, [rdi]
0x180008d4e  test    al, 2
0x180008d50  jnz     short loc_180008D61
0x180008d52  and     eax, 0FFFFF63Eh
0x180008d57  and     ebx, 9C1h
0x180008d5d  or      eax, ebx
0x180008d5f  mov     [rdi], eax
0x180008d61  mov     rbx, [rsp+38h+arg_10]
0x180008d66  mov     rax, rdi
0x180008d69  add     rsp, 20h
0x180008d6d  pop     rdi
0x180008d6e  pop     rsi
0x180008d6f  pop     rbp
0x180008d70  retn
```
