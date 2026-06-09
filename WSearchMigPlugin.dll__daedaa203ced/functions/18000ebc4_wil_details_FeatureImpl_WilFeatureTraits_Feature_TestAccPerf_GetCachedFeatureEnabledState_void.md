# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ebc4`
- end: `0x18000ec9d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013e10`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000ebc4`
- `0x18000f2b4`

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
0x18000ebc4  mov     [rsp+arg_10], rbx
0x18000ebc9  mov     [rsp+arg_0], rcx
0x18000ebce  push    rbp
0x18000ebcf  push    rsi
0x18000ebd0  push    rdi
0x18000ebd1  sub     rsp, 20h
0x18000ebd5  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000ebdc  mov     rdi, rdx
0x18000ebdf  mov     qword ptr [rdx], 0
0x18000ebe6  mov     eax, [rsi]
0x18000ebe8  mov     [rdx], eax
0x18000ebea  and     eax, 6
0x18000ebed  cmp     al, 6
0x18000ebef  jz      loc_18000EC8D
0x18000ebf5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ebfa  lea     r8, [rsp+38h+arg_0]
0x18000ebff  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ec07  lea     rdx, [rsp+38h+arg_8]
0x18000ec0c  mov     ebp, eax
0x18000ec0e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000ec13  mov     eax, [rdi]
0x18000ec15  mov     rbx, [rsp+38h+arg_8]
0x18000ec1a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ec1f  mov     edx, eax
0x18000ec21  mov     [rdi], eax
0x18000ec23  mov     ecx, eax
0x18000ec25  jz      short loc_18000EC40
0x18000ec27  test    dl, 2
0x18000ec2a  jnz     short loc_18000EC40
0x18000ec2c  and     ecx, 0FFFFF63Eh
0x18000ec32  mov     eax, ebx
0x18000ec34  and     eax, 9C1h
0x18000ec39  or      ecx, eax
0x18000ec3b  or      ecx, 2
0x18000ec3e  mov     [rdi], ecx
0x18000ec40  mov     r8d, edx
0x18000ec43  and     r8d, 4
0x18000ec47  jnz     short loc_18000EC5B
0x18000ec49  btr     ecx, 0Ah
0x18000ec4d  mov     eax, ebx
0x18000ec4f  and     eax, 400h
0x18000ec54  or      ecx, eax
0x18000ec56  or      ecx, 4
0x18000ec59  mov     [rdi], ecx
0x18000ec5b  mov     eax, edx
0x18000ec5d  lock cmpxchg [rsi], ecx
0x18000ec61  jnz     short loc_18000EC1A
0x18000ec63  test    r8d, r8d
0x18000ec66  jnz     short loc_18000EC78
0x18000ec68  mov     r8d, ebp
0x18000ec6b  mov     edx, 3
0x18000ec70  mov     rcx, rsi
0x18000ec73  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ec78  mov     eax, [rdi]
0x18000ec7a  test    al, 2
0x18000ec7c  jnz     short loc_18000EC8D
0x18000ec7e  and     eax, 0FFFFF63Eh
0x18000ec83  and     ebx, 9C1h
0x18000ec89  or      eax, ebx
0x18000ec8b  mov     [rdi], eax
0x18000ec8d  mov     rbx, [rsp+38h+arg_10]
0x18000ec92  mov     rax, rdi
0x18000ec95  add     rsp, 20h
0x18000ec99  pop     rdi
0x18000ec9a  pop     rsi
0x18000ec9b  pop     rbp
0x18000ec9c  retn
```
