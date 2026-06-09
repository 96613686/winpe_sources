# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e7c4`
- end: `0x18000e89d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x18000da08`
- `0x18000e7c4`
- `0x18000ef84`
- `0x180010c28`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18000e7c4  mov     [rsp+arg_10], rbx
0x18000e7c9  mov     [rsp+arg_0], rcx
0x18000e7ce  push    rbp
0x18000e7cf  push    rsi
0x18000e7d0  push    rdi
0x18000e7d1  sub     rsp, 20h
0x18000e7d5  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000e7dc  mov     rdi, rdx
0x18000e7df  mov     qword ptr [rdx], 0
0x18000e7e6  mov     eax, [rsi]
0x18000e7e8  mov     [rdx], eax
0x18000e7ea  and     eax, 6
0x18000e7ed  cmp     al, 6
0x18000e7ef  jz      loc_18000E88D
0x18000e7f5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e7fa  lea     r8, [rsp+38h+arg_0]
0x18000e7ff  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e807  lea     rdx, [rsp+38h+arg_8]
0x18000e80c  mov     ebp, eax
0x18000e80e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000e813  mov     eax, [rdi]
0x18000e815  mov     rbx, [rsp+38h+arg_8]
0x18000e81a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e81f  mov     edx, eax
0x18000e821  mov     [rdi], eax
0x18000e823  mov     ecx, eax
0x18000e825  jz      short loc_18000E840
0x18000e827  test    dl, 2
0x18000e82a  jnz     short loc_18000E840
0x18000e82c  and     ecx, 0FFFFF63Eh
0x18000e832  mov     eax, ebx
0x18000e834  and     eax, 9C1h
0x18000e839  or      ecx, eax
0x18000e83b  or      ecx, 2
0x18000e83e  mov     [rdi], ecx
0x18000e840  mov     r8d, edx
0x18000e843  and     r8d, 4
0x18000e847  jnz     short loc_18000E85B
0x18000e849  btr     ecx, 0Ah
0x18000e84d  mov     eax, ebx
0x18000e84f  and     eax, 400h
0x18000e854  or      ecx, eax
0x18000e856  or      ecx, 4
0x18000e859  mov     [rdi], ecx
0x18000e85b  mov     eax, edx
0x18000e85d  lock cmpxchg [rsi], ecx
0x18000e861  jnz     short loc_18000E81A
0x18000e863  test    r8d, r8d
0x18000e866  jnz     short loc_18000E878
0x18000e868  mov     r8d, ebp
0x18000e86b  mov     edx, 3
0x18000e870  mov     rcx, rsi
0x18000e873  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e878  mov     eax, [rdi]
0x18000e87a  test    al, 2
0x18000e87c  jnz     short loc_18000E88D
0x18000e87e  and     eax, 0FFFFF63Eh
0x18000e883  and     ebx, 9C1h
0x18000e889  or      eax, ebx
0x18000e88b  mov     [rdi], eax
0x18000e88d  mov     rbx, [rsp+38h+arg_10]
0x18000e892  mov     rax, rdi
0x18000e895  add     rsp, 20h
0x18000e899  pop     rdi
0x18000e89a  pop     rsi
0x18000e89b  pop     rbp
0x18000e89c  retn
```
