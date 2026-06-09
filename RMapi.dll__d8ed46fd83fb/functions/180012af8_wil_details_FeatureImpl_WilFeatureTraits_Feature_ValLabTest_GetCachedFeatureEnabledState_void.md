# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180012af8`
- end: `0x180012be3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800153d8`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180012af8`
- `0x1800130e0`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x180012af8  push    rbx
0x180012afa  push    rbp
0x180012afb  push    rsi
0x180012afc  push    rdi
0x180012afd  sub     rsp, 48h
0x180012b01  mov     rax, cs:__security_cookie
0x180012b08  xor     rax, rsp
0x180012b0b  mov     [rsp+68h+var_38], rax
0x180012b10  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180012b17  mov     rdi, rdx
0x180012b1a  mov     qword ptr [rdx], 0
0x180012b21  mov     eax, [rsi]
0x180012b23  mov     [rdx], eax
0x180012b25  and     eax, 6
0x180012b28  cmp     al, 6
0x180012b2a  jz      loc_180012BCA
0x180012b30  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012b35  lea     r8, [rsp+68h+var_40]
0x180012b3a  mov     [rsp+68h+var_40], 0
0x180012b42  lea     rdx, [rsp+68h+var_48]
0x180012b47  mov     ebp, eax
0x180012b49  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180012b4e  mov     eax, [rdi]
0x180012b50  mov     rbx, [rsp+68h+var_48]
0x180012b55  cmp     [rsp+68h+var_40], 0
0x180012b5a  mov     edx, eax
0x180012b5c  mov     [rdi], eax
0x180012b5e  mov     ecx, eax
0x180012b60  jz      short loc_180012B7B
0x180012b62  test    dl, 2
0x180012b65  jnz     short loc_180012B7B
0x180012b67  and     ecx, 0FFFFF63Eh
0x180012b6d  mov     eax, ebx
0x180012b6f  and     eax, 9C1h
0x180012b74  or      ecx, eax
0x180012b76  or      ecx, 2
0x180012b79  mov     [rdi], ecx
0x180012b7b  mov     r8d, edx
0x180012b7e  and     r8d, 4
0x180012b82  jnz     short loc_180012B96
0x180012b84  btr     ecx, 0Ah
0x180012b88  mov     eax, ebx
0x180012b8a  and     eax, 400h
0x180012b8f  or      ecx, eax
0x180012b91  or      ecx, 4
0x180012b94  mov     [rdi], ecx
0x180012b96  mov     eax, edx
0x180012b98  lock cmpxchg [rsi], ecx
0x180012b9c  jnz     short loc_180012B55
0x180012b9e  test    r8d, r8d
0x180012ba1  jnz     short loc_180012BB3
0x180012ba3  mov     r8d, ebp
0x180012ba6  mov     edx, 3
0x180012bab  mov     rcx, rsi
0x180012bae  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012bb3  mov     ecx, [rdi]
0x180012bb5  test    cl, 2
0x180012bb8  jnz     short loc_180012BCA
0x180012bba  and     ecx, 0FFFFF63Eh
0x180012bc0  and     ebx, 9C1h
0x180012bc6  or      ecx, ebx
0x180012bc8  mov     [rdi], ecx
0x180012bca  mov     rax, rdi
0x180012bcd  mov     rcx, [rsp+68h+var_38]
0x180012bd2  xor     rcx, rsp; StackCookie
0x180012bd5  call    __security_check_cookie
0x180012bda  add     rsp, 48h
0x180012bde  pop     rdi
0x180012bdf  pop     rsi
0x180012be0  pop     rbp
0x180012be1  pop     rbx
0x180012be2  retn
```
