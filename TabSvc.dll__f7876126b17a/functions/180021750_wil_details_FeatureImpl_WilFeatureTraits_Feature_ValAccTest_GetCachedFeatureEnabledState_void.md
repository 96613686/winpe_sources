# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180021750`
- end: `0x180021829`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025794`
- `0x180028bc8`

## callees

- `0x180019930`
- `0x18001a080`
- `0x180021750`
- `0x1800223b4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180021750  mov     [rsp+arg_10], rbx
0x180021755  mov     [rsp+arg_0], rcx
0x18002175a  push    rbp
0x18002175b  push    rsi
0x18002175c  push    rdi
0x18002175d  sub     rsp, 20h
0x180021761  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180021768  mov     rdi, rdx
0x18002176b  mov     qword ptr [rdx], 0
0x180021772  mov     eax, [rsi]
0x180021774  mov     [rdx], eax
0x180021776  and     eax, 6
0x180021779  cmp     al, 6
0x18002177b  jz      loc_180021819
0x180021781  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180021786  lea     r8, [rsp+38h+arg_0]
0x18002178b  mov     dword ptr [rsp+38h+arg_0], 0
0x180021793  lea     rdx, [rsp+38h+arg_8]
0x180021798  mov     ebp, eax
0x18002179a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18002179f  mov     eax, [rdi]
0x1800217a1  mov     rbx, [rsp+38h+arg_8]
0x1800217a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800217ab  mov     edx, eax
0x1800217ad  mov     [rdi], eax
0x1800217af  mov     ecx, eax
0x1800217b1  jz      short loc_1800217CC
0x1800217b3  test    dl, 2
0x1800217b6  jnz     short loc_1800217CC
0x1800217b8  and     ecx, 0FFFFF63Eh
0x1800217be  mov     eax, ebx
0x1800217c0  and     eax, 9C1h
0x1800217c5  or      ecx, eax
0x1800217c7  or      ecx, 2
0x1800217ca  mov     [rdi], ecx
0x1800217cc  mov     r8d, edx
0x1800217cf  and     r8d, 4
0x1800217d3  jnz     short loc_1800217E7
0x1800217d5  btr     ecx, 0Ah
0x1800217d9  mov     eax, ebx
0x1800217db  and     eax, 400h
0x1800217e0  or      ecx, eax
0x1800217e2  or      ecx, 4
0x1800217e5  mov     [rdi], ecx
0x1800217e7  mov     eax, edx
0x1800217e9  lock cmpxchg [rsi], ecx
0x1800217ed  jnz     short loc_1800217A6
0x1800217ef  test    r8d, r8d
0x1800217f2  jnz     short loc_180021804
0x1800217f4  mov     r8d, ebp
0x1800217f7  mov     edx, 3
0x1800217fc  mov     rcx, rsi
0x1800217ff  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180021804  mov     eax, [rdi]
0x180021806  test    al, 2
0x180021808  jnz     short loc_180021819
0x18002180a  and     eax, 0FFFFF63Eh
0x18002180f  and     ebx, 9C1h
0x180021815  or      eax, ebx
0x180021817  mov     [rdi], eax
0x180021819  mov     rbx, [rsp+38h+arg_10]
0x18002181e  mov     rax, rdi
0x180021821  add     rsp, 20h
0x180021825  pop     rdi
0x180021826  pop     rsi
0x180021827  pop     rbp
0x180021828  retn
```
