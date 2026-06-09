# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c2bc`
- end: `0x18000c395`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cbd4`
- `0x18000d0a0`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000c2bc`
- `0x18000c4c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WhesvcUserFeedbackToast__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WhesvcUserFeedbackToast__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_WhesvcUserFeedbackToast__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_WhesvcUserFeedbackToast__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000c2bc  mov     [rsp+arg_10], rbx
0x18000c2c1  mov     [rsp+arg_0], rcx
0x18000c2c6  push    rbp
0x18000c2c7  push    rsi
0x18000c2c8  push    rdi
0x18000c2c9  sub     rsp, 20h
0x18000c2cd  mov     rsi, cs:Feature_WhesvcUserFeedbackToast__descriptor
0x18000c2d4  mov     rdi, rdx
0x18000c2d7  mov     qword ptr [rdx], 0
0x18000c2de  mov     eax, [rsi]
0x18000c2e0  mov     [rdx], eax
0x18000c2e2  and     eax, 6
0x18000c2e5  cmp     al, 6
0x18000c2e7  jz      loc_18000C385
0x18000c2ed  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c2f2  lea     r8, [rsp+38h+arg_0]
0x18000c2f7  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c2ff  lea     rdx, [rsp+38h+arg_8]
0x18000c304  mov     ebp, eax
0x18000c306  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCurrentFeatureEnabledState(int *)
0x18000c30b  mov     eax, [rdi]
0x18000c30d  mov     rbx, [rsp+38h+arg_8]
0x18000c312  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c317  mov     edx, eax
0x18000c319  mov     [rdi], eax
0x18000c31b  mov     ecx, eax
0x18000c31d  jz      short loc_18000C338
0x18000c31f  test    dl, 2
0x18000c322  jnz     short loc_18000C338
0x18000c324  and     ecx, 0FFFFF63Eh
0x18000c32a  mov     eax, ebx
0x18000c32c  and     eax, 9C1h
0x18000c331  or      ecx, eax
0x18000c333  or      ecx, 2
0x18000c336  mov     [rdi], ecx
0x18000c338  mov     r8d, edx
0x18000c33b  and     r8d, 4
0x18000c33f  jnz     short loc_18000C353
0x18000c341  btr     ecx, 0Ah
0x18000c345  mov     eax, ebx
0x18000c347  and     eax, 400h
0x18000c34c  or      ecx, eax
0x18000c34e  or      ecx, 4
0x18000c351  mov     [rdi], ecx
0x18000c353  mov     eax, edx
0x18000c355  lock cmpxchg [rsi], ecx
0x18000c359  jnz     short loc_18000C312
0x18000c35b  test    r8d, r8d
0x18000c35e  jnz     short loc_18000C370
0x18000c360  mov     r8d, ebp
0x18000c363  mov     edx, 3
0x18000c368  mov     rcx, rsi
0x18000c36b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c370  mov     eax, [rdi]
0x18000c372  test    al, 2
0x18000c374  jnz     short loc_18000C385
0x18000c376  and     eax, 0FFFFF63Eh
0x18000c37b  and     ebx, 9C1h
0x18000c381  or      eax, ebx
0x18000c383  mov     [rdi], eax
0x18000c385  mov     rbx, [rsp+38h+arg_10]
0x18000c38a  mov     rax, rdi
0x18000c38d  add     rsp, 20h
0x18000c391  pop     rdi
0x18000c392  pop     rsi
0x18000c393  pop     rbp
0x18000c394  retn
```
