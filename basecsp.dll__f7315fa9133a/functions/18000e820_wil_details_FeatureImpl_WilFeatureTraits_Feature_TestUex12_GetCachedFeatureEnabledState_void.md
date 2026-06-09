# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e820`
- end: `0x18000e8f9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016114`
- `0x18001875c`

## callees

- `0x18000d7e0`
- `0x18000e820`
- `0x18000f3f8`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestUex12__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e820  mov     [rsp+arg_10], rbx
0x18000e825  mov     [rsp+arg_0], rcx
0x18000e82a  push    rbp
0x18000e82b  push    rsi
0x18000e82c  push    rdi
0x18000e82d  sub     rsp, 20h
0x18000e831  mov     rsi, cs:Feature_TestUex12__descriptor
0x18000e838  mov     rdi, rdx
0x18000e83b  mov     qword ptr [rdx], 0
0x18000e842  mov     eax, [rsi]
0x18000e844  mov     [rdx], eax
0x18000e846  and     eax, 6
0x18000e849  cmp     al, 6
0x18000e84b  jz      loc_18000E8E9
0x18000e851  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e856  lea     r8, [rsp+38h+arg_0]
0x18000e85b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e863  lea     rdx, [rsp+38h+arg_8]
0x18000e868  mov     ebp, eax
0x18000e86a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x18000e86f  mov     eax, [rdi]
0x18000e871  mov     rbx, [rsp+38h+arg_8]
0x18000e876  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e87b  mov     edx, eax
0x18000e87d  mov     [rdi], eax
0x18000e87f  mov     ecx, eax
0x18000e881  jz      short loc_18000E89C
0x18000e883  test    dl, 2
0x18000e886  jnz     short loc_18000E89C
0x18000e888  and     ecx, 0FFFFF63Eh
0x18000e88e  mov     eax, ebx
0x18000e890  and     eax, 9C1h
0x18000e895  or      ecx, eax
0x18000e897  or      ecx, 2
0x18000e89a  mov     [rdi], ecx
0x18000e89c  mov     r8d, edx
0x18000e89f  and     r8d, 4
0x18000e8a3  jnz     short loc_18000E8B7
0x18000e8a5  btr     ecx, 0Ah
0x18000e8a9  mov     eax, ebx
0x18000e8ab  and     eax, 400h
0x18000e8b0  or      ecx, eax
0x18000e8b2  or      ecx, 4
0x18000e8b5  mov     [rdi], ecx
0x18000e8b7  mov     eax, edx
0x18000e8b9  lock cmpxchg [rsi], ecx
0x18000e8bd  jnz     short loc_18000E876
0x18000e8bf  test    r8d, r8d
0x18000e8c2  jnz     short loc_18000E8D4
0x18000e8c4  mov     r8d, ebp
0x18000e8c7  mov     edx, 3
0x18000e8cc  mov     rcx, rsi
0x18000e8cf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e8d4  mov     eax, [rdi]
0x18000e8d6  test    al, 2
0x18000e8d8  jnz     short loc_18000E8E9
0x18000e8da  and     eax, 0FFFFF63Eh
0x18000e8df  and     ebx, 9C1h
0x18000e8e5  or      eax, ebx
0x18000e8e7  mov     [rdi], eax
0x18000e8e9  mov     rbx, [rsp+38h+arg_10]
0x18000e8ee  mov     rax, rdi
0x18000e8f1  add     rsp, 20h
0x18000e8f5  pop     rdi
0x18000e8f6  pop     rsi
0x18000e8f7  pop     rbp
0x18000e8f8  retn
```
