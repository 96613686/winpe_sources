# wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCachedFeatureEnabledState(void)

- ea: `0x180018adc`
- end: `0x180018bb5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_46572530@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ffc`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180018adc`
- `0x180018bbc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_46572530__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_46572530__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_46572530__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_46572530__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180018adc  mov     [rsp+arg_10], rbx
0x180018ae1  mov     [rsp+arg_0], rcx
0x180018ae6  push    rbp
0x180018ae7  push    rsi
0x180018ae8  push    rdi
0x180018ae9  sub     rsp, 20h
0x180018aed  mov     rsi, cs:Feature_46572530__descriptor
0x180018af4  mov     rdi, rdx
0x180018af7  mov     qword ptr [rdx], 0
0x180018afe  mov     eax, [rsi]
0x180018b00  mov     [rdx], eax
0x180018b02  and     eax, 6
0x180018b05  cmp     al, 6
0x180018b07  jz      loc_180018BA5
0x180018b0d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018b12  lea     r8, [rsp+38h+arg_0]
0x180018b17  mov     dword ptr [rsp+38h+arg_0], 0
0x180018b1f  lea     rdx, [rsp+38h+arg_8]
0x180018b24  mov     ebp, eax
0x180018b26  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_46572530@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_46572530>::GetCurrentFeatureEnabledState(int *)
0x180018b2b  mov     eax, [rdi]
0x180018b2d  mov     rbx, [rsp+38h+arg_8]
0x180018b32  cmp     dword ptr [rsp+38h+arg_0], 0
0x180018b37  mov     edx, eax
0x180018b39  mov     [rdi], eax
0x180018b3b  mov     ecx, eax
0x180018b3d  jz      short loc_180018B58
0x180018b3f  test    dl, 2
0x180018b42  jnz     short loc_180018B58
0x180018b44  and     ecx, 0FFFFF63Eh
0x180018b4a  mov     eax, ebx
0x180018b4c  and     eax, 9C1h
0x180018b51  or      ecx, eax
0x180018b53  or      ecx, 2
0x180018b56  mov     [rdi], ecx
0x180018b58  mov     r8d, edx
0x180018b5b  and     r8d, 4
0x180018b5f  jnz     short loc_180018B73
0x180018b61  btr     ecx, 0Ah
0x180018b65  mov     eax, ebx
0x180018b67  and     eax, 400h
0x180018b6c  or      ecx, eax
0x180018b6e  or      ecx, 4
0x180018b71  mov     [rdi], ecx
0x180018b73  mov     eax, edx
0x180018b75  lock cmpxchg [rsi], ecx
0x180018b79  jnz     short loc_180018B32
0x180018b7b  test    r8d, r8d
0x180018b7e  jnz     short loc_180018B90
0x180018b80  mov     r8d, ebp
0x180018b83  mov     edx, 3
0x180018b88  mov     rcx, rsi
0x180018b8b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180018b90  mov     eax, [rdi]
0x180018b92  test    al, 2
0x180018b94  jnz     short loc_180018BA5
0x180018b96  and     eax, 0FFFFF63Eh
0x180018b9b  and     ebx, 9C1h
0x180018ba1  or      eax, ebx
0x180018ba3  mov     [rdi], eax
0x180018ba5  mov     rbx, [rsp+38h+arg_10]
0x180018baa  mov     rax, rdi
0x180018bad  add     rsp, 20h
0x180018bb1  pop     rdi
0x180018bb2  pop     rsi
0x180018bb3  pop     rbp
0x180018bb4  retn
```
