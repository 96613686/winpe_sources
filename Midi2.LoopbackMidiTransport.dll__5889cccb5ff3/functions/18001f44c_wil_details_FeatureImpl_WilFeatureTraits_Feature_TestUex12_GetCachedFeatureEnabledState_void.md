# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f44c`
- end: `0x18001f525`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002159c`

## callees

- `0x18001e65c`
- `0x18001f44c`
- `0x18001fcbc`
- `0x180020fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestUex12__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestUex12__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestUex12__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestUex12__descriptor,
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
0x18001f44c  mov     [rsp+arg_10], rbx
0x18001f451  mov     [rsp+arg_0], rcx
0x18001f456  push    rbp
0x18001f457  push    rsi
0x18001f458  push    rdi
0x18001f459  sub     rsp, 20h
0x18001f45d  mov     rsi, cs:Feature_TestUex12__descriptor
0x18001f464  mov     rdi, rdx
0x18001f467  mov     qword ptr [rdx], 0
0x18001f46e  mov     eax, [rsi]
0x18001f470  mov     [rdx], eax
0x18001f472  and     eax, 6
0x18001f475  cmp     al, 6
0x18001f477  jz      loc_18001F515
0x18001f47d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f482  lea     r8, [rsp+38h+arg_0]
0x18001f487  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f48f  lea     rdx, [rsp+38h+arg_8]
0x18001f494  mov     ebp, eax
0x18001f496  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)
0x18001f49b  mov     eax, [rdi]
0x18001f49d  mov     rbx, [rsp+38h+arg_8]
0x18001f4a2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f4a7  mov     edx, eax
0x18001f4a9  mov     [rdi], eax
0x18001f4ab  mov     ecx, eax
0x18001f4ad  jz      short loc_18001F4C8
0x18001f4af  test    dl, 2
0x18001f4b2  jnz     short loc_18001F4C8
0x18001f4b4  and     ecx, 0FFFFF63Eh
0x18001f4ba  mov     eax, ebx
0x18001f4bc  and     eax, 9C1h
0x18001f4c1  or      ecx, eax
0x18001f4c3  or      ecx, 2
0x18001f4c6  mov     [rdi], ecx
0x18001f4c8  mov     r8d, edx
0x18001f4cb  and     r8d, 4
0x18001f4cf  jnz     short loc_18001F4E3
0x18001f4d1  btr     ecx, 0Ah
0x18001f4d5  mov     eax, ebx
0x18001f4d7  and     eax, 400h
0x18001f4dc  or      ecx, eax
0x18001f4de  or      ecx, 4
0x18001f4e1  mov     [rdi], ecx
0x18001f4e3  mov     eax, edx
0x18001f4e5  lock cmpxchg [rsi], ecx
0x18001f4e9  jnz     short loc_18001F4A2
0x18001f4eb  test    r8d, r8d
0x18001f4ee  jnz     short loc_18001F500
0x18001f4f0  mov     r8d, ebp
0x18001f4f3  mov     edx, 3
0x18001f4f8  mov     rcx, rsi
0x18001f4fb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f500  mov     eax, [rdi]
0x18001f502  test    al, 2
0x18001f504  jnz     short loc_18001F515
0x18001f506  and     eax, 0FFFFF63Eh
0x18001f50b  and     ebx, 9C1h
0x18001f511  or      eax, ebx
0x18001f513  mov     [rdi], eax
0x18001f515  mov     rbx, [rsp+38h+arg_10]
0x18001f51a  mov     rax, rdi
0x18001f51d  add     rsp, 20h
0x18001f521  pop     rdi
0x18001f522  pop     rsi
0x18001f523  pop     rbp
0x18001f524  retn
```
