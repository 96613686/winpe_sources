# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180013d18`
- end: `0x180013df1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015574`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013d18`
- `0x180014abc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013d18  mov     [rsp+arg_10], rbx
0x180013d1d  mov     [rsp+arg_0], rcx
0x180013d22  push    rbp
0x180013d23  push    rsi
0x180013d24  push    rdi
0x180013d25  sub     rsp, 20h
0x180013d29  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180013d30  mov     rdi, rdx
0x180013d33  mov     qword ptr [rdx], 0
0x180013d3a  mov     eax, [rsi]
0x180013d3c  mov     [rdx], eax
0x180013d3e  and     eax, 6
0x180013d41  cmp     al, 6
0x180013d43  jz      loc_180013DE1
0x180013d49  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013d4e  lea     r8, [rsp+38h+arg_0]
0x180013d53  mov     dword ptr [rsp+38h+arg_0], 0
0x180013d5b  lea     rdx, [rsp+38h+arg_8]
0x180013d60  mov     ebp, eax
0x180013d62  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180013d67  mov     eax, [rdi]
0x180013d69  mov     rbx, [rsp+38h+arg_8]
0x180013d6e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013d73  mov     edx, eax
0x180013d75  mov     [rdi], eax
0x180013d77  mov     ecx, eax
0x180013d79  jz      short loc_180013D94
0x180013d7b  test    dl, 2
0x180013d7e  jnz     short loc_180013D94
0x180013d80  and     ecx, 0FFFFF63Eh
0x180013d86  mov     eax, ebx
0x180013d88  and     eax, 9C1h
0x180013d8d  or      ecx, eax
0x180013d8f  or      ecx, 2
0x180013d92  mov     [rdi], ecx
0x180013d94  mov     r8d, edx
0x180013d97  and     r8d, 4
0x180013d9b  jnz     short loc_180013DAF
0x180013d9d  btr     ecx, 0Ah
0x180013da1  mov     eax, ebx
0x180013da3  and     eax, 400h
0x180013da8  or      ecx, eax
0x180013daa  or      ecx, 4
0x180013dad  mov     [rdi], ecx
0x180013daf  mov     eax, edx
0x180013db1  lock cmpxchg [rsi], ecx
0x180013db5  jnz     short loc_180013D6E
0x180013db7  test    r8d, r8d
0x180013dba  jnz     short loc_180013DCC
0x180013dbc  mov     r8d, ebp
0x180013dbf  mov     edx, 3
0x180013dc4  mov     rcx, rsi
0x180013dc7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013dcc  mov     eax, [rdi]
0x180013dce  test    al, 2
0x180013dd0  jnz     short loc_180013DE1
0x180013dd2  and     eax, 0FFFFF63Eh
0x180013dd7  and     ebx, 9C1h
0x180013ddd  or      eax, ebx
0x180013ddf  mov     [rdi], eax
0x180013de1  mov     rbx, [rsp+38h+arg_10]
0x180013de6  mov     rax, rdi
0x180013de9  add     rsp, 20h
0x180013ded  pop     rdi
0x180013dee  pop     rsi
0x180013def  pop     rbp
0x180013df0  retn
```
