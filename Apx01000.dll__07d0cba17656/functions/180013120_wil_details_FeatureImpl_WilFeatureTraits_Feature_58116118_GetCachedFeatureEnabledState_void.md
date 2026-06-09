# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58116118>::GetCachedFeatureEnabledState(void)

- ea: `0x180013120`
- end: `0x1800131f9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58116118@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015438`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013120`
- `0x18001483c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58116118>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_58116118__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58116118__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_58116118>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58116118__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_58116118__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013120  mov     [rsp+arg_10], rbx
0x180013125  mov     [rsp+arg_0], rcx
0x18001312a  push    rbp
0x18001312b  push    rsi
0x18001312c  push    rdi
0x18001312d  sub     rsp, 20h
0x180013131  mov     rsi, cs:Feature_58116118__descriptor
0x180013138  mov     rdi, rdx
0x18001313b  mov     qword ptr [rdx], 0
0x180013142  mov     eax, [rsi]
0x180013144  mov     [rdx], eax
0x180013146  and     eax, 6
0x180013149  cmp     al, 6
0x18001314b  jz      loc_1800131E9
0x180013151  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013156  lea     r8, [rsp+38h+arg_0]
0x18001315b  mov     dword ptr [rsp+38h+arg_0], 0
0x180013163  lea     rdx, [rsp+38h+arg_8]
0x180013168  mov     ebp, eax
0x18001316a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58116118@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58116118>::GetCurrentFeatureEnabledState(int *)
0x18001316f  mov     eax, [rdi]
0x180013171  mov     rbx, [rsp+38h+arg_8]
0x180013176  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001317b  mov     edx, eax
0x18001317d  mov     [rdi], eax
0x18001317f  mov     ecx, eax
0x180013181  jz      short loc_18001319C
0x180013183  test    dl, 2
0x180013186  jnz     short loc_18001319C
0x180013188  and     ecx, 0FFFFF63Eh
0x18001318e  mov     eax, ebx
0x180013190  and     eax, 9C1h
0x180013195  or      ecx, eax
0x180013197  or      ecx, 2
0x18001319a  mov     [rdi], ecx
0x18001319c  mov     r8d, edx
0x18001319f  and     r8d, 4
0x1800131a3  jnz     short loc_1800131B7
0x1800131a5  btr     ecx, 0Ah
0x1800131a9  mov     eax, ebx
0x1800131ab  and     eax, 400h
0x1800131b0  or      ecx, eax
0x1800131b2  or      ecx, 4
0x1800131b5  mov     [rdi], ecx
0x1800131b7  mov     eax, edx
0x1800131b9  lock cmpxchg [rsi], ecx
0x1800131bd  jnz     short loc_180013176
0x1800131bf  test    r8d, r8d
0x1800131c2  jnz     short loc_1800131D4
0x1800131c4  mov     r8d, ebp
0x1800131c7  mov     edx, 3
0x1800131cc  mov     rcx, rsi
0x1800131cf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800131d4  mov     eax, [rdi]
0x1800131d6  test    al, 2
0x1800131d8  jnz     short loc_1800131E9
0x1800131da  and     eax, 0FFFFF63Eh
0x1800131df  and     ebx, 9C1h
0x1800131e5  or      eax, ebx
0x1800131e7  mov     [rdi], eax
0x1800131e9  mov     rbx, [rsp+38h+arg_10]
0x1800131ee  mov     rax, rdi
0x1800131f1  add     rsp, 20h
0x1800131f5  pop     rdi
0x1800131f6  pop     rsi
0x1800131f7  pop     rbp
0x1800131f8  retn
```
