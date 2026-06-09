# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ee64`
- end: `0x18000ef3d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013fe4`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000ee64`
- `0x18000f704`

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
0x18000ee64  mov     [rsp+arg_10], rbx
0x18000ee69  mov     [rsp+arg_0], rcx
0x18000ee6e  push    rbp
0x18000ee6f  push    rsi
0x18000ee70  push    rdi
0x18000ee71  sub     rsp, 20h
0x18000ee75  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000ee7c  mov     rdi, rdx
0x18000ee7f  mov     qword ptr [rdx], 0
0x18000ee86  mov     eax, [rsi]
0x18000ee88  mov     [rdx], eax
0x18000ee8a  and     eax, 6
0x18000ee8d  cmp     al, 6
0x18000ee8f  jz      loc_18000EF2D
0x18000ee95  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ee9a  lea     r8, [rsp+38h+arg_0]
0x18000ee9f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000eea7  lea     rdx, [rsp+38h+arg_8]
0x18000eeac  mov     ebp, eax
0x18000eeae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000eeb3  mov     eax, [rdi]
0x18000eeb5  mov     rbx, [rsp+38h+arg_8]
0x18000eeba  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000eebf  mov     edx, eax
0x18000eec1  mov     [rdi], eax
0x18000eec3  mov     ecx, eax
0x18000eec5  jz      short loc_18000EEE0
0x18000eec7  test    dl, 2
0x18000eeca  jnz     short loc_18000EEE0
0x18000eecc  and     ecx, 0FFFFF63Eh
0x18000eed2  mov     eax, ebx
0x18000eed4  and     eax, 9C1h
0x18000eed9  or      ecx, eax
0x18000eedb  or      ecx, 2
0x18000eede  mov     [rdi], ecx
0x18000eee0  mov     r8d, edx
0x18000eee3  and     r8d, 4
0x18000eee7  jnz     short loc_18000EEFB
0x18000eee9  btr     ecx, 0Ah
0x18000eeed  mov     eax, ebx
0x18000eeef  and     eax, 400h
0x18000eef4  or      ecx, eax
0x18000eef6  or      ecx, 4
0x18000eef9  mov     [rdi], ecx
0x18000eefb  mov     eax, edx
0x18000eefd  lock cmpxchg [rsi], ecx
0x18000ef01  jnz     short loc_18000EEBA
0x18000ef03  test    r8d, r8d
0x18000ef06  jnz     short loc_18000EF18
0x18000ef08  mov     r8d, ebp
0x18000ef0b  mov     edx, 3
0x18000ef10  mov     rcx, rsi
0x18000ef13  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ef18  mov     eax, [rdi]
0x18000ef1a  test    al, 2
0x18000ef1c  jnz     short loc_18000EF2D
0x18000ef1e  and     eax, 0FFFFF63Eh
0x18000ef23  and     ebx, 9C1h
0x18000ef29  or      eax, ebx
0x18000ef2b  mov     [rdi], eax
0x18000ef2d  mov     rbx, [rsp+38h+arg_10]
0x18000ef32  mov     rax, rdi
0x18000ef35  add     rsp, 20h
0x18000ef39  pop     rdi
0x18000ef3a  pop     rsi
0x18000ef3b  pop     rbp
0x18000ef3c  retn
```
