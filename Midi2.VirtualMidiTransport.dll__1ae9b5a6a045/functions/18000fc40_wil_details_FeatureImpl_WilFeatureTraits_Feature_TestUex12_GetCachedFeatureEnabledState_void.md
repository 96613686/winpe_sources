# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fc40`
- end: `0x18000fd19`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011cf0`

## callees

- `0x18000ee50`
- `0x18000fc40`
- `0x1800104b0`
- `0x180011648`

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
0x18000fc40  mov     [rsp+arg_10], rbx
0x18000fc45  mov     [rsp+arg_0], rcx
0x18000fc4a  push    rbp
0x18000fc4b  push    rsi
0x18000fc4c  push    rdi
0x18000fc4d  sub     rsp, 20h
0x18000fc51  mov     rsi, cs:Feature_TestUex12__descriptor
0x18000fc58  mov     rdi, rdx
0x18000fc5b  mov     qword ptr [rdx], 0
0x18000fc62  mov     eax, [rsi]
0x18000fc64  mov     [rdx], eax
0x18000fc66  and     eax, 6
0x18000fc69  cmp     al, 6
0x18000fc6b  jz      loc_18000FD09
0x18000fc71  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fc76  lea     r8, [rsp+38h+arg_0]
0x18000fc7b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fc83  lea     rdx, [rsp+38h+arg_8]
0x18000fc88  mov     ebp, eax
0x18000fc8a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x18000fc8f  mov     eax, [rdi]
0x18000fc91  mov     rbx, [rsp+38h+arg_8]
0x18000fc96  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fc9b  mov     edx, eax
0x18000fc9d  mov     [rdi], eax
0x18000fc9f  mov     ecx, eax
0x18000fca1  jz      short loc_18000FCBC
0x18000fca3  test    dl, 2
0x18000fca6  jnz     short loc_18000FCBC
0x18000fca8  and     ecx, 0FFFFF63Eh
0x18000fcae  mov     eax, ebx
0x18000fcb0  and     eax, 9C1h
0x18000fcb5  or      ecx, eax
0x18000fcb7  or      ecx, 2
0x18000fcba  mov     [rdi], ecx
0x18000fcbc  mov     r8d, edx
0x18000fcbf  and     r8d, 4
0x18000fcc3  jnz     short loc_18000FCD7
0x18000fcc5  btr     ecx, 0Ah
0x18000fcc9  mov     eax, ebx
0x18000fccb  and     eax, 400h
0x18000fcd0  or      ecx, eax
0x18000fcd2  or      ecx, 4
0x18000fcd5  mov     [rdi], ecx
0x18000fcd7  mov     eax, edx
0x18000fcd9  lock cmpxchg [rsi], ecx
0x18000fcdd  jnz     short loc_18000FC96
0x18000fcdf  test    r8d, r8d
0x18000fce2  jnz     short loc_18000FCF4
0x18000fce4  mov     r8d, ebp
0x18000fce7  mov     edx, 3
0x18000fcec  mov     rcx, rsi
0x18000fcef  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fcf4  mov     eax, [rdi]
0x18000fcf6  test    al, 2
0x18000fcf8  jnz     short loc_18000FD09
0x18000fcfa  and     eax, 0FFFFF63Eh
0x18000fcff  and     ebx, 9C1h
0x18000fd05  or      eax, ebx
0x18000fd07  mov     [rdi], eax
0x18000fd09  mov     rbx, [rsp+38h+arg_10]
0x18000fd0e  mov     rax, rdi
0x18000fd11  add     rsp, 20h
0x18000fd15  pop     rdi
0x18000fd16  pop     rsi
0x18000fd17  pop     rbp
0x18000fd18  retn
```
