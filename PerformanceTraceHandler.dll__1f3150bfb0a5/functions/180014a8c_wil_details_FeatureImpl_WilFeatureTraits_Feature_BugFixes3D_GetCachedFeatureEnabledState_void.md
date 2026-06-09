# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCachedFeatureEnabledState(void)

- ea: `0x180014a8c`
- end: `0x180014b65`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800172b0`
- `0x180017ca8`

## callees

- `0x18000543c`
- `0x180008794`
- `0x180014a8c`
- `0x18001599c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixes3D__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixes3D__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixes3D__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixes3D__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180014a8c  mov     [rsp+arg_10], rbx
0x180014a91  mov     [rsp+arg_0], rcx
0x180014a96  push    rbp
0x180014a97  push    rsi
0x180014a98  push    rdi
0x180014a99  sub     rsp, 20h
0x180014a9d  mov     rsi, cs:Feature_BugFixes3D__descriptor
0x180014aa4  mov     rdi, rdx
0x180014aa7  mov     qword ptr [rdx], 0
0x180014aae  mov     eax, [rsi]
0x180014ab0  mov     [rdx], eax
0x180014ab2  and     eax, 6
0x180014ab5  cmp     al, 6
0x180014ab7  jz      loc_180014B55
0x180014abd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014ac2  lea     r8, [rsp+38h+arg_0]
0x180014ac7  mov     dword ptr [rsp+38h+arg_0], 0
0x180014acf  lea     rdx, [rsp+38h+arg_8]
0x180014ad4  mov     ebp, eax
0x180014ad6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCurrentFeatureEnabledState(int *)
0x180014adb  mov     eax, [rdi]
0x180014add  mov     rbx, [rsp+38h+arg_8]
0x180014ae2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014ae7  mov     edx, eax
0x180014ae9  mov     [rdi], eax
0x180014aeb  mov     ecx, eax
0x180014aed  jz      short loc_180014B08
0x180014aef  test    dl, 2
0x180014af2  jnz     short loc_180014B08
0x180014af4  and     ecx, 0FFFFF63Eh
0x180014afa  mov     eax, ebx
0x180014afc  and     eax, 9C1h
0x180014b01  or      ecx, eax
0x180014b03  or      ecx, 2
0x180014b06  mov     [rdi], ecx
0x180014b08  mov     r8d, edx
0x180014b0b  and     r8d, 4
0x180014b0f  jnz     short loc_180014B23
0x180014b11  btr     ecx, 0Ah
0x180014b15  mov     eax, ebx
0x180014b17  and     eax, 400h
0x180014b1c  or      ecx, eax
0x180014b1e  or      ecx, 4
0x180014b21  mov     [rdi], ecx
0x180014b23  mov     eax, edx
0x180014b25  lock cmpxchg [rsi], ecx
0x180014b29  jnz     short loc_180014AE2
0x180014b2b  test    r8d, r8d
0x180014b2e  jnz     short loc_180014B40
0x180014b30  mov     r8d, ebp
0x180014b33  mov     edx, 3
0x180014b38  mov     rcx, rsi
0x180014b3b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014b40  mov     eax, [rdi]
0x180014b42  test    al, 2
0x180014b44  jnz     short loc_180014B55
0x180014b46  and     eax, 0FFFFF63Eh
0x180014b4b  and     ebx, 9C1h
0x180014b51  or      eax, ebx
0x180014b53  mov     [rdi], eax
0x180014b55  mov     rbx, [rsp+38h+arg_10]
0x180014b5a  mov     rax, rdi
0x180014b5d  add     rsp, 20h
0x180014b61  pop     rdi
0x180014b62  pop     rsi
0x180014b63  pop     rbp
0x180014b64  retn
```
