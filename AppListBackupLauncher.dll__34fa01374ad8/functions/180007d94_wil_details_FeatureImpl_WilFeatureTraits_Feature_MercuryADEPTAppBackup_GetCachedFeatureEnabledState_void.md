# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCachedFeatureEnabledState(void)

- ea: `0x180007d94`
- end: `0x180007e6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e904`

## callees

- `0x180007854`
- `0x180007d94`
- `0x1800083d0`
- `0x18000d31c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MercuryADEPTAppBackup__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MercuryADEPTAppBackup__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MercuryADEPTAppBackup__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_MercuryADEPTAppBackup__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180007d94  mov     [rsp+arg_10], rbx
0x180007d99  mov     [rsp+arg_0], rcx
0x180007d9e  push    rbp
0x180007d9f  push    rsi
0x180007da0  push    rdi
0x180007da1  sub     rsp, 20h
0x180007da5  mov     rsi, cs:Feature_MercuryADEPTAppBackup__descriptor
0x180007dac  mov     rdi, rdx
0x180007daf  mov     qword ptr [rdx], 0
0x180007db6  mov     eax, [rsi]
0x180007db8  mov     [rdx], eax
0x180007dba  and     eax, 6
0x180007dbd  cmp     al, 6
0x180007dbf  jz      loc_180007E5D
0x180007dc5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007dca  lea     r8, [rsp+38h+arg_0]
0x180007dcf  mov     dword ptr [rsp+38h+arg_0], 0
0x180007dd7  lea     rdx, [rsp+38h+arg_8]
0x180007ddc  mov     ebp, eax
0x180007dde  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MercuryADEPTAppBackup@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MercuryADEPTAppBackup>::GetCurrentFeatureEnabledState(int *)
0x180007de3  mov     eax, [rdi]
0x180007de5  mov     rbx, [rsp+38h+arg_8]
0x180007dea  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007def  mov     edx, eax
0x180007df1  mov     [rdi], eax
0x180007df3  mov     ecx, eax
0x180007df5  jz      short loc_180007E10
0x180007df7  test    dl, 2
0x180007dfa  jnz     short loc_180007E10
0x180007dfc  and     ecx, 0FFFFF63Eh
0x180007e02  mov     eax, ebx
0x180007e04  and     eax, 9C1h
0x180007e09  or      ecx, eax
0x180007e0b  or      ecx, 2
0x180007e0e  mov     [rdi], ecx
0x180007e10  mov     r8d, edx
0x180007e13  and     r8d, 4
0x180007e17  jnz     short loc_180007E2B
0x180007e19  btr     ecx, 0Ah
0x180007e1d  mov     eax, ebx
0x180007e1f  and     eax, 400h
0x180007e24  or      ecx, eax
0x180007e26  or      ecx, 4
0x180007e29  mov     [rdi], ecx
0x180007e2b  mov     eax, edx
0x180007e2d  lock cmpxchg [rsi], ecx
0x180007e31  jnz     short loc_180007DEA
0x180007e33  test    r8d, r8d
0x180007e36  jnz     short loc_180007E48
0x180007e38  mov     r8d, ebp
0x180007e3b  mov     edx, 3
0x180007e40  mov     rcx, rsi
0x180007e43  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007e48  mov     eax, [rdi]
0x180007e4a  test    al, 2
0x180007e4c  jnz     short loc_180007E5D
0x180007e4e  and     eax, 0FFFFF63Eh
0x180007e53  and     ebx, 9C1h
0x180007e59  or      eax, ebx
0x180007e5b  mov     [rdi], eax
0x180007e5d  mov     rbx, [rsp+38h+arg_10]
0x180007e62  mov     rax, rdi
0x180007e65  add     rsp, 20h
0x180007e69  pop     rdi
0x180007e6a  pop     rsi
0x180007e6b  pop     rbp
0x180007e6c  retn
```
