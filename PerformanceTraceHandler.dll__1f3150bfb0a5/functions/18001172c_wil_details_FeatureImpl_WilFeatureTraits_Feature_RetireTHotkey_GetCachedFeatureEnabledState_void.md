# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCachedFeatureEnabledState(void)

- ea: `0x18001172c`
- end: `0x180011805`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RetireTHotkey@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012704`
- `0x180012cdc`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18001172c`
- `0x18001180c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_RetireTHotkey__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_RetireTHotkey__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_RetireTHotkey__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_RetireTHotkey__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001172c  mov     [rsp+arg_10], rbx
0x180011731  mov     [rsp+arg_0], rcx
0x180011736  push    rbp
0x180011737  push    rsi
0x180011738  push    rdi
0x180011739  sub     rsp, 20h
0x18001173d  mov     rsi, cs:Feature_RetireTHotkey__descriptor
0x180011744  mov     rdi, rdx
0x180011747  mov     qword ptr [rdx], 0
0x18001174e  mov     eax, [rsi]
0x180011750  mov     [rdx], eax
0x180011752  and     eax, 6
0x180011755  cmp     al, 6
0x180011757  jz      loc_1800117F5
0x18001175d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011762  lea     r8, [rsp+38h+arg_0]
0x180011767  mov     dword ptr [rsp+38h+arg_0], 0
0x18001176f  lea     rdx, [rsp+38h+arg_8]
0x180011774  mov     ebp, eax
0x180011776  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RetireTHotkey@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCurrentFeatureEnabledState(int *)
0x18001177b  mov     eax, [rdi]
0x18001177d  mov     rbx, [rsp+38h+arg_8]
0x180011782  cmp     dword ptr [rsp+38h+arg_0], 0
0x180011787  mov     edx, eax
0x180011789  mov     [rdi], eax
0x18001178b  mov     ecx, eax
0x18001178d  jz      short loc_1800117A8
0x18001178f  test    dl, 2
0x180011792  jnz     short loc_1800117A8
0x180011794  and     ecx, 0FFFFF63Eh
0x18001179a  mov     eax, ebx
0x18001179c  and     eax, 9C1h
0x1800117a1  or      ecx, eax
0x1800117a3  or      ecx, 2
0x1800117a6  mov     [rdi], ecx
0x1800117a8  mov     r8d, edx
0x1800117ab  and     r8d, 4
0x1800117af  jnz     short loc_1800117C3
0x1800117b1  btr     ecx, 0Ah
0x1800117b5  mov     eax, ebx
0x1800117b7  and     eax, 400h
0x1800117bc  or      ecx, eax
0x1800117be  or      ecx, 4
0x1800117c1  mov     [rdi], ecx
0x1800117c3  mov     eax, edx
0x1800117c5  lock cmpxchg [rsi], ecx
0x1800117c9  jnz     short loc_180011782
0x1800117cb  test    r8d, r8d
0x1800117ce  jnz     short loc_1800117E0
0x1800117d0  mov     r8d, ebp
0x1800117d3  mov     edx, 3
0x1800117d8  mov     rcx, rsi
0x1800117db  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800117e0  mov     eax, [rdi]
0x1800117e2  test    al, 2
0x1800117e4  jnz     short loc_1800117F5
0x1800117e6  and     eax, 0FFFFF63Eh
0x1800117eb  and     ebx, 9C1h
0x1800117f1  or      eax, ebx
0x1800117f3  mov     [rdi], eax
0x1800117f5  mov     rbx, [rsp+38h+arg_10]
0x1800117fa  mov     rax, rdi
0x1800117fd  add     rsp, 20h
0x180011801  pop     rdi
0x180011802  pop     rsi
0x180011803  pop     rbp
0x180011804  retn
```
