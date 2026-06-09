# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetCachedFeatureEnabledState(void)

- ea: `0x180021210`
- end: `0x1800212e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025460`
- `0x180028a60`

## callees

- `0x180019930`
- `0x18001a080`
- `0x180021210`
- `0x180021c10`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TabsvcLeaveTabTipOnDetach__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TabsvcLeaveTabTipOnDetach__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_TabsvcLeaveTabTipOnDetach__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_TabsvcLeaveTabTipOnDetach__descriptor,
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
0x180021210  mov     [rsp+arg_10], rbx
0x180021215  mov     [rsp+arg_0], rcx
0x18002121a  push    rbp
0x18002121b  push    rsi
0x18002121c  push    rdi
0x18002121d  sub     rsp, 20h
0x180021221  mov     rsi, cs:Feature_TabsvcLeaveTabTipOnDetach__descriptor
0x180021228  mov     rdi, rdx
0x18002122b  mov     qword ptr [rdx], 0
0x180021232  mov     eax, [rsi]
0x180021234  mov     [rdx], eax
0x180021236  and     eax, 6
0x180021239  cmp     al, 6
0x18002123b  jz      loc_1800212D9
0x180021241  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180021246  lea     r8, [rsp+38h+arg_0]
0x18002124b  mov     dword ptr [rsp+38h+arg_0], 0
0x180021253  lea     rdx, [rsp+38h+arg_8]
0x180021258  mov     ebp, eax
0x18002125a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcLeaveTabTipOnDetach>::GetCurrentFeatureEnabledState(int *)
0x18002125f  mov     eax, [rdi]
0x180021261  mov     rbx, [rsp+38h+arg_8]
0x180021266  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002126b  mov     edx, eax
0x18002126d  mov     [rdi], eax
0x18002126f  mov     ecx, eax
0x180021271  jz      short loc_18002128C
0x180021273  test    dl, 2
0x180021276  jnz     short loc_18002128C
0x180021278  and     ecx, 0FFFFF63Eh
0x18002127e  mov     eax, ebx
0x180021280  and     eax, 9C1h
0x180021285  or      ecx, eax
0x180021287  or      ecx, 2
0x18002128a  mov     [rdi], ecx
0x18002128c  mov     r8d, edx
0x18002128f  and     r8d, 4
0x180021293  jnz     short loc_1800212A7
0x180021295  btr     ecx, 0Ah
0x180021299  mov     eax, ebx
0x18002129b  and     eax, 400h
0x1800212a0  or      ecx, eax
0x1800212a2  or      ecx, 4
0x1800212a5  mov     [rdi], ecx
0x1800212a7  mov     eax, edx
0x1800212a9  lock cmpxchg [rsi], ecx
0x1800212ad  jnz     short loc_180021266
0x1800212af  test    r8d, r8d
0x1800212b2  jnz     short loc_1800212C4
0x1800212b4  mov     r8d, ebp
0x1800212b7  mov     edx, 3
0x1800212bc  mov     rcx, rsi
0x1800212bf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800212c4  mov     eax, [rdi]
0x1800212c6  test    al, 2
0x1800212c8  jnz     short loc_1800212D9
0x1800212ca  and     eax, 0FFFFF63Eh
0x1800212cf  and     ebx, 9C1h
0x1800212d5  or      eax, ebx
0x1800212d7  mov     [rdi], eax
0x1800212d9  mov     rbx, [rsp+38h+arg_10]
0x1800212de  mov     rax, rdi
0x1800212e1  add     rsp, 20h
0x1800212e5  pop     rdi
0x1800212e6  pop     rsi
0x1800212e7  pop     rbp
0x1800212e8  retn
```
