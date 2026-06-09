# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f9a0`
- end: `0x18000fa79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011b1c`

## callees

- `0x18000ee50`
- `0x18000f9a0`
- `0x180010060`
- `0x180011648`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18000f9a0  mov     [rsp+arg_10], rbx
0x18000f9a5  mov     [rsp+arg_0], rcx
0x18000f9aa  push    rbp
0x18000f9ab  push    rsi
0x18000f9ac  push    rdi
0x18000f9ad  sub     rsp, 20h
0x18000f9b1  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000f9b8  mov     rdi, rdx
0x18000f9bb  mov     qword ptr [rdx], 0
0x18000f9c2  mov     eax, [rsi]
0x18000f9c4  mov     [rdx], eax
0x18000f9c6  and     eax, 6
0x18000f9c9  cmp     al, 6
0x18000f9cb  jz      loc_18000FA69
0x18000f9d1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f9d6  lea     r8, [rsp+38h+arg_0]
0x18000f9db  mov     dword ptr [rsp+38h+arg_0], 0
0x18000f9e3  lea     rdx, [rsp+38h+arg_8]
0x18000f9e8  mov     ebp, eax
0x18000f9ea  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000f9ef  mov     eax, [rdi]
0x18000f9f1  mov     rbx, [rsp+38h+arg_8]
0x18000f9f6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000f9fb  mov     edx, eax
0x18000f9fd  mov     [rdi], eax
0x18000f9ff  mov     ecx, eax
0x18000fa01  jz      short loc_18000FA1C
0x18000fa03  test    dl, 2
0x18000fa06  jnz     short loc_18000FA1C
0x18000fa08  and     ecx, 0FFFFF63Eh
0x18000fa0e  mov     eax, ebx
0x18000fa10  and     eax, 9C1h
0x18000fa15  or      ecx, eax
0x18000fa17  or      ecx, 2
0x18000fa1a  mov     [rdi], ecx
0x18000fa1c  mov     r8d, edx
0x18000fa1f  and     r8d, 4
0x18000fa23  jnz     short loc_18000FA37
0x18000fa25  btr     ecx, 0Ah
0x18000fa29  mov     eax, ebx
0x18000fa2b  and     eax, 400h
0x18000fa30  or      ecx, eax
0x18000fa32  or      ecx, 4
0x18000fa35  mov     [rdi], ecx
0x18000fa37  mov     eax, edx
0x18000fa39  lock cmpxchg [rsi], ecx
0x18000fa3d  jnz     short loc_18000F9F6
0x18000fa3f  test    r8d, r8d
0x18000fa42  jnz     short loc_18000FA54
0x18000fa44  mov     r8d, ebp
0x18000fa47  mov     edx, 3
0x18000fa4c  mov     rcx, rsi
0x18000fa4f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fa54  mov     eax, [rdi]
0x18000fa56  test    al, 2
0x18000fa58  jnz     short loc_18000FA69
0x18000fa5a  and     eax, 0FFFFF63Eh
0x18000fa5f  and     ebx, 9C1h
0x18000fa65  or      eax, ebx
0x18000fa67  mov     [rdi], eax
0x18000fa69  mov     rbx, [rsp+38h+arg_10]
0x18000fa6e  mov     rax, rdi
0x18000fa71  add     rsp, 20h
0x18000fa75  pop     rdi
0x18000fa76  pop     rsi
0x18000fa77  pop     rbp
0x18000fa78  retn
```
