# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180036b60`
- end: `0x180036c4b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039ffc`
- `0x18003bec4`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036b60`
- `0x1800372e4`
- `0x18003b548`

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
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
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
0x180036b60  push    rbx
0x180036b62  push    rbp
0x180036b63  push    rsi
0x180036b64  push    rdi
0x180036b65  sub     rsp, 48h
0x180036b69  mov     rax, cs:__security_cookie
0x180036b70  xor     rax, rsp
0x180036b73  mov     [rsp+68h+var_38], rax
0x180036b78  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180036b7f  mov     rdi, rdx
0x180036b82  mov     qword ptr [rdx], 0
0x180036b89  mov     eax, [rsi]
0x180036b8b  mov     [rdx], eax
0x180036b8d  and     eax, 6
0x180036b90  cmp     al, 6
0x180036b92  jz      loc_180036C32
0x180036b98  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036b9d  lea     r8, [rsp+68h+var_40]
0x180036ba2  mov     [rsp+68h+var_40], 0
0x180036baa  lea     rdx, [rsp+68h+var_48]
0x180036baf  mov     ebp, eax
0x180036bb1  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180036bb6  mov     eax, [rdi]
0x180036bb8  mov     rbx, [rsp+68h+var_48]
0x180036bbd  cmp     [rsp+68h+var_40], 0
0x180036bc2  mov     edx, eax
0x180036bc4  mov     [rdi], eax
0x180036bc6  mov     ecx, eax
0x180036bc8  jz      short loc_180036BE3
0x180036bca  test    dl, 2
0x180036bcd  jnz     short loc_180036BE3
0x180036bcf  and     ecx, 0FFFFF63Eh
0x180036bd5  mov     eax, ebx
0x180036bd7  and     eax, 9C1h
0x180036bdc  or      ecx, eax
0x180036bde  or      ecx, 2
0x180036be1  mov     [rdi], ecx
0x180036be3  mov     r8d, edx
0x180036be6  and     r8d, 4
0x180036bea  jnz     short loc_180036BFE
0x180036bec  btr     ecx, 0Ah
0x180036bf0  mov     eax, ebx
0x180036bf2  and     eax, 400h
0x180036bf7  or      ecx, eax
0x180036bf9  or      ecx, 4
0x180036bfc  mov     [rdi], ecx
0x180036bfe  mov     eax, edx
0x180036c00  lock cmpxchg [rsi], ecx
0x180036c04  jnz     short loc_180036BBD
0x180036c06  test    r8d, r8d
0x180036c09  jnz     short loc_180036C1B
0x180036c0b  mov     r8d, ebp
0x180036c0e  mov     edx, 3
0x180036c13  mov     rcx, rsi
0x180036c16  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036c1b  mov     ecx, [rdi]
0x180036c1d  test    cl, 2
0x180036c20  jnz     short loc_180036C32
0x180036c22  and     ecx, 0FFFFF63Eh
0x180036c28  and     ebx, 9C1h
0x180036c2e  or      ecx, ebx
0x180036c30  mov     [rdi], ecx
0x180036c32  mov     rax, rdi
0x180036c35  mov     rcx, [rsp+68h+var_38]
0x180036c3a  xor     rcx, rsp; StackCookie
0x180036c3d  call    __security_check_cookie
0x180036c42  add     rsp, 48h
0x180036c46  pop     rdi
0x180036c47  pop     rsi
0x180036c48  pop     rbp
0x180036c49  pop     rbx
0x180036c4a  retn
```
