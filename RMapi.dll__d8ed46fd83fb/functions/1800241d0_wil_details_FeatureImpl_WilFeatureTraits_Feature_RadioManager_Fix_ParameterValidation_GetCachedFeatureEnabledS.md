# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetCachedFeatureEnabledState(void)

- ea: `0x1800241d0`
- end: `0x1800242c0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800246c4`
- `0x180024a48`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180016180`
- `0x1800241d0`
- `0x1800244b0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  int v11; // r8d
  __int64 v13; // [rsp+20h] [rbp-48h] BYREF
  int v14; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_RadioManager_Fix_ParameterValidation__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_RadioManager_Fix_ParameterValidation__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v14 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetCurrentFeatureEnabledState(
      v5,
      &v13,
      &v14);
    if ( !v4 )
      v14 = 0;
    v6 = *(_DWORD *)a2;
    v7 = v13;
    do
    {
      v8 = v14 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      v11 = v6 & 4;
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_RadioManager_Fix_ParameterValidation__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( !v11 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_RadioManager_Fix_ParameterValidation__descriptor,
        0,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800241d0  push    rbx
0x1800241d2  push    rbp
0x1800241d3  push    rsi
0x1800241d4  push    rdi
0x1800241d5  sub     rsp, 48h
0x1800241d9  mov     rax, cs:__security_cookie
0x1800241e0  xor     rax, rsp
0x1800241e3  mov     [rsp+68h+var_38], rax
0x1800241e8  mov     rsi, cs:Feature_RadioManager_Fix_ParameterValidation__descriptor
0x1800241ef  mov     rdi, rdx
0x1800241f2  mov     qword ptr [rdx], 0
0x1800241f9  mov     eax, [rsi]
0x1800241fb  mov     [rdx], eax
0x1800241fd  and     eax, 6
0x180024200  cmp     al, 6
0x180024202  jz      loc_1800242A7
0x180024208  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002420d  lea     r8, [rsp+68h+var_40]
0x180024212  mov     [rsp+68h+var_40], 0
0x18002421a  lea     rdx, [rsp+68h+var_48]
0x18002421f  mov     ebp, eax
0x180024221  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_ParameterValidation>::GetCurrentFeatureEnabledState(int *)
0x180024226  test    ebp, ebp
0x180024228  jnz     short loc_18002422E
0x18002422a  mov     [rsp+68h+var_40], ebp
0x18002422e  mov     eax, [rdi]
0x180024230  mov     rbx, [rsp+68h+var_48]
0x180024235  cmp     [rsp+68h+var_40], 0
0x18002423a  mov     edx, eax
0x18002423c  mov     [rdi], eax
0x18002423e  mov     ecx, eax
0x180024240  jz      short loc_18002425B
0x180024242  test    dl, 2
0x180024245  jnz     short loc_18002425B
0x180024247  and     ecx, 0FFFFF63Eh
0x18002424d  mov     eax, ebx
0x18002424f  and     eax, 9C1h
0x180024254  or      ecx, eax
0x180024256  or      ecx, 2
0x180024259  mov     [rdi], ecx
0x18002425b  mov     r8d, edx
0x18002425e  and     r8d, 4
0x180024262  jnz     short loc_180024276
0x180024264  btr     ecx, 0Ah
0x180024268  mov     eax, ebx
0x18002426a  and     eax, 400h
0x18002426f  or      ecx, eax
0x180024271  or      ecx, 4
0x180024274  mov     [rdi], ecx
0x180024276  mov     eax, edx
0x180024278  lock cmpxchg [rsi], ecx
0x18002427c  jnz     short loc_180024235
0x18002427e  test    r8d, r8d
0x180024281  jnz     short loc_180024290
0x180024283  mov     r8d, ebp
0x180024286  xor     edx, edx
0x180024288  mov     rcx, rsi
0x18002428b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180024290  mov     ecx, [rdi]
0x180024292  test    cl, 2
0x180024295  jnz     short loc_1800242A7
0x180024297  and     ecx, 0FFFFF63Eh
0x18002429d  and     ebx, 9C1h
0x1800242a3  or      ecx, ebx
0x1800242a5  mov     [rdi], ecx
0x1800242a7  mov     rax, rdi
0x1800242aa  mov     rcx, [rsp+68h+var_38]
0x1800242af  xor     rcx, rsp; StackCookie
0x1800242b2  call    __security_check_cookie
0x1800242b7  add     rsp, 48h
0x1800242bb  pop     rdi
0x1800242bc  pop     rsi
0x1800242bd  pop     rbp
0x1800242be  pop     rbx
0x1800242bf  retn
```
