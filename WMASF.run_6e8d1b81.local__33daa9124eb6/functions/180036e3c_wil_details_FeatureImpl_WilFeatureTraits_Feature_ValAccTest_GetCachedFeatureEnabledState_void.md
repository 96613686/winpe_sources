# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180036e3c`
- end: `0x180036f27`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a1e8`
- `0x18003bf78`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036e3c`
- `0x180037590`
- `0x18003b548`

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
0x180036e3c  push    rbx
0x180036e3e  push    rbp
0x180036e3f  push    rsi
0x180036e40  push    rdi
0x180036e41  sub     rsp, 48h
0x180036e45  mov     rax, cs:__security_cookie
0x180036e4c  xor     rax, rsp
0x180036e4f  mov     [rsp+68h+var_38], rax
0x180036e54  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180036e5b  mov     rdi, rdx
0x180036e5e  mov     qword ptr [rdx], 0
0x180036e65  mov     eax, [rsi]
0x180036e67  mov     [rdx], eax
0x180036e69  and     eax, 6
0x180036e6c  cmp     al, 6
0x180036e6e  jz      loc_180036F0E
0x180036e74  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036e79  lea     r8, [rsp+68h+var_40]
0x180036e7e  mov     [rsp+68h+var_40], 0
0x180036e86  lea     rdx, [rsp+68h+var_48]
0x180036e8b  mov     ebp, eax
0x180036e8d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180036e92  mov     eax, [rdi]
0x180036e94  mov     rbx, [rsp+68h+var_48]
0x180036e99  cmp     [rsp+68h+var_40], 0
0x180036e9e  mov     edx, eax
0x180036ea0  mov     [rdi], eax
0x180036ea2  mov     ecx, eax
0x180036ea4  jz      short loc_180036EBF
0x180036ea6  test    dl, 2
0x180036ea9  jnz     short loc_180036EBF
0x180036eab  and     ecx, 0FFFFF63Eh
0x180036eb1  mov     eax, ebx
0x180036eb3  and     eax, 9C1h
0x180036eb8  or      ecx, eax
0x180036eba  or      ecx, 2
0x180036ebd  mov     [rdi], ecx
0x180036ebf  mov     r8d, edx
0x180036ec2  and     r8d, 4
0x180036ec6  jnz     short loc_180036EDA
0x180036ec8  btr     ecx, 0Ah
0x180036ecc  mov     eax, ebx
0x180036ece  and     eax, 400h
0x180036ed3  or      ecx, eax
0x180036ed5  or      ecx, 4
0x180036ed8  mov     [rdi], ecx
0x180036eda  mov     eax, edx
0x180036edc  lock cmpxchg [rsi], ecx
0x180036ee0  jnz     short loc_180036E99
0x180036ee2  test    r8d, r8d
0x180036ee5  jnz     short loc_180036EF7
0x180036ee7  mov     r8d, ebp
0x180036eea  mov     edx, 3
0x180036eef  mov     rcx, rsi
0x180036ef2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036ef7  mov     ecx, [rdi]
0x180036ef9  test    cl, 2
0x180036efc  jnz     short loc_180036F0E
0x180036efe  and     ecx, 0FFFFF63Eh
0x180036f04  and     ebx, 9C1h
0x180036f0a  or      ecx, ebx
0x180036f0c  mov     [rdi], ecx
0x180036f0e  mov     rax, rdi
0x180036f11  mov     rcx, [rsp+68h+var_38]
0x180036f16  xor     rcx, rsp; StackCookie
0x180036f19  call    __security_check_cookie
0x180036f1e  add     rsp, 48h
0x180036f22  pop     rdi
0x180036f23  pop     rsi
0x180036f24  pop     rbp
0x180036f25  pop     rbx
0x180036f26  retn
```
