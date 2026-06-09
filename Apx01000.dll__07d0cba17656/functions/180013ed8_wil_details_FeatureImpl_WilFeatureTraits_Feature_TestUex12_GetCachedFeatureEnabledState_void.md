# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x180013ed8`
- end: `0x180013fb1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800156ac`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013ed8`
- `0x180014d9c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestUex12__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestUex12__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestUex12__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestUex12__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013ed8  mov     [rsp+arg_10], rbx
0x180013edd  mov     [rsp+arg_0], rcx
0x180013ee2  push    rbp
0x180013ee3  push    rsi
0x180013ee4  push    rdi
0x180013ee5  sub     rsp, 20h
0x180013ee9  mov     rsi, cs:Feature_TestUex12__descriptor
0x180013ef0  mov     rdi, rdx
0x180013ef3  mov     qword ptr [rdx], 0
0x180013efa  mov     eax, [rsi]
0x180013efc  mov     [rdx], eax
0x180013efe  and     eax, 6
0x180013f01  cmp     al, 6
0x180013f03  jz      loc_180013FA1
0x180013f09  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013f0e  lea     r8, [rsp+38h+arg_0]
0x180013f13  mov     dword ptr [rsp+38h+arg_0], 0
0x180013f1b  lea     rdx, [rsp+38h+arg_8]
0x180013f20  mov     ebp, eax
0x180013f22  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x180013f27  mov     eax, [rdi]
0x180013f29  mov     rbx, [rsp+38h+arg_8]
0x180013f2e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013f33  mov     edx, eax
0x180013f35  mov     [rdi], eax
0x180013f37  mov     ecx, eax
0x180013f39  jz      short loc_180013F54
0x180013f3b  test    dl, 2
0x180013f3e  jnz     short loc_180013F54
0x180013f40  and     ecx, 0FFFFF63Eh
0x180013f46  mov     eax, ebx
0x180013f48  and     eax, 9C1h
0x180013f4d  or      ecx, eax
0x180013f4f  or      ecx, 2
0x180013f52  mov     [rdi], ecx
0x180013f54  mov     r8d, edx
0x180013f57  and     r8d, 4
0x180013f5b  jnz     short loc_180013F6F
0x180013f5d  btr     ecx, 0Ah
0x180013f61  mov     eax, ebx
0x180013f63  and     eax, 400h
0x180013f68  or      ecx, eax
0x180013f6a  or      ecx, 4
0x180013f6d  mov     [rdi], ecx
0x180013f6f  mov     eax, edx
0x180013f71  lock cmpxchg [rsi], ecx
0x180013f75  jnz     short loc_180013F2E
0x180013f77  test    r8d, r8d
0x180013f7a  jnz     short loc_180013F8C
0x180013f7c  mov     r8d, ebp
0x180013f7f  mov     edx, 3
0x180013f84  mov     rcx, rsi
0x180013f87  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013f8c  mov     eax, [rdi]
0x180013f8e  test    al, 2
0x180013f90  jnz     short loc_180013FA1
0x180013f92  and     eax, 0FFFFF63Eh
0x180013f97  and     ebx, 9C1h
0x180013f9d  or      eax, ebx
0x180013f9f  mov     [rdi], eax
0x180013fa1  mov     rbx, [rsp+38h+arg_10]
0x180013fa6  mov     rax, rdi
0x180013fa9  add     rsp, 20h
0x180013fad  pop     rdi
0x180013fae  pop     rsi
0x180013faf  pop     rbp
0x180013fb0  retn
```
