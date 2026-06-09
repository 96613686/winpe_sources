# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180012a04`
- end: `0x180012aef`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015334`
- `0x180016af8`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012a04`
- `0x180013004`
- `0x180016180`

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
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
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
0x180012a04  push    rbx
0x180012a06  push    rbp
0x180012a07  push    rsi
0x180012a08  push    rdi
0x180012a09  sub     rsp, 48h
0x180012a0d  mov     rax, cs:__security_cookie
0x180012a14  xor     rax, rsp
0x180012a17  mov     [rsp+68h+var_38], rax
0x180012a1c  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180012a23  mov     rdi, rdx
0x180012a26  mov     qword ptr [rdx], 0
0x180012a2d  mov     eax, [rsi]
0x180012a2f  mov     [rdx], eax
0x180012a31  and     eax, 6
0x180012a34  cmp     al, 6
0x180012a36  jz      loc_180012AD6
0x180012a3c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012a41  lea     r8, [rsp+68h+var_40]
0x180012a46  mov     [rsp+68h+var_40], 0
0x180012a4e  lea     rdx, [rsp+68h+var_48]
0x180012a53  mov     ebp, eax
0x180012a55  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180012a5a  mov     eax, [rdi]
0x180012a5c  mov     rbx, [rsp+68h+var_48]
0x180012a61  cmp     [rsp+68h+var_40], 0
0x180012a66  mov     edx, eax
0x180012a68  mov     [rdi], eax
0x180012a6a  mov     ecx, eax
0x180012a6c  jz      short loc_180012A87
0x180012a6e  test    dl, 2
0x180012a71  jnz     short loc_180012A87
0x180012a73  and     ecx, 0FFFFF63Eh
0x180012a79  mov     eax, ebx
0x180012a7b  and     eax, 9C1h
0x180012a80  or      ecx, eax
0x180012a82  or      ecx, 2
0x180012a85  mov     [rdi], ecx
0x180012a87  mov     r8d, edx
0x180012a8a  and     r8d, 4
0x180012a8e  jnz     short loc_180012AA2
0x180012a90  btr     ecx, 0Ah
0x180012a94  mov     eax, ebx
0x180012a96  and     eax, 400h
0x180012a9b  or      ecx, eax
0x180012a9d  or      ecx, 4
0x180012aa0  mov     [rdi], ecx
0x180012aa2  mov     eax, edx
0x180012aa4  lock cmpxchg [rsi], ecx
0x180012aa8  jnz     short loc_180012A61
0x180012aaa  test    r8d, r8d
0x180012aad  jnz     short loc_180012ABF
0x180012aaf  mov     r8d, ebp
0x180012ab2  mov     edx, 3
0x180012ab7  mov     rcx, rsi
0x180012aba  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012abf  mov     ecx, [rdi]
0x180012ac1  test    cl, 2
0x180012ac4  jnz     short loc_180012AD6
0x180012ac6  and     ecx, 0FFFFF63Eh
0x180012acc  and     ebx, 9C1h
0x180012ad2  or      ecx, ebx
0x180012ad4  mov     [rdi], ecx
0x180012ad6  mov     rax, rdi
0x180012ad9  mov     rcx, [rsp+68h+var_38]
0x180012ade  xor     rcx, rsp; StackCookie
0x180012ae1  call    __security_check_cookie
0x180012ae6  add     rsp, 48h
0x180012aea  pop     rdi
0x180012aeb  pop     rsi
0x180012aec  pop     rbp
0x180012aed  pop     rbx
0x180012aee  retn
```
