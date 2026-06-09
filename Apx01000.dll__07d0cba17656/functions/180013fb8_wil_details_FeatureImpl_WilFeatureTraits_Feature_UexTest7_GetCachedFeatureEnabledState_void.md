# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x180013fb8`
- end: `0x180014091`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015748`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013fb8`
- `0x180014f0c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UexTest7__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013fb8  mov     [rsp+arg_10], rbx
0x180013fbd  mov     [rsp+arg_0], rcx
0x180013fc2  push    rbp
0x180013fc3  push    rsi
0x180013fc4  push    rdi
0x180013fc5  sub     rsp, 20h
0x180013fc9  mov     rsi, cs:Feature_UexTest7__descriptor
0x180013fd0  mov     rdi, rdx
0x180013fd3  mov     qword ptr [rdx], 0
0x180013fda  mov     eax, [rsi]
0x180013fdc  mov     [rdx], eax
0x180013fde  and     eax, 6
0x180013fe1  cmp     al, 6
0x180013fe3  jz      loc_180014081
0x180013fe9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013fee  lea     r8, [rsp+38h+arg_0]
0x180013ff3  mov     dword ptr [rsp+38h+arg_0], 0
0x180013ffb  lea     rdx, [rsp+38h+arg_8]
0x180014000  mov     ebp, eax
0x180014002  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180014007  mov     eax, [rdi]
0x180014009  mov     rbx, [rsp+38h+arg_8]
0x18001400e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014013  mov     edx, eax
0x180014015  mov     [rdi], eax
0x180014017  mov     ecx, eax
0x180014019  jz      short loc_180014034
0x18001401b  test    dl, 2
0x18001401e  jnz     short loc_180014034
0x180014020  and     ecx, 0FFFFF63Eh
0x180014026  mov     eax, ebx
0x180014028  and     eax, 9C1h
0x18001402d  or      ecx, eax
0x18001402f  or      ecx, 2
0x180014032  mov     [rdi], ecx
0x180014034  mov     r8d, edx
0x180014037  and     r8d, 4
0x18001403b  jnz     short loc_18001404F
0x18001403d  btr     ecx, 0Ah
0x180014041  mov     eax, ebx
0x180014043  and     eax, 400h
0x180014048  or      ecx, eax
0x18001404a  or      ecx, 4
0x18001404d  mov     [rdi], ecx
0x18001404f  mov     eax, edx
0x180014051  lock cmpxchg [rsi], ecx
0x180014055  jnz     short loc_18001400E
0x180014057  test    r8d, r8d
0x18001405a  jnz     short loc_18001406C
0x18001405c  mov     r8d, ebp
0x18001405f  mov     edx, 3
0x180014064  mov     rcx, rsi
0x180014067  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001406c  mov     eax, [rdi]
0x18001406e  test    al, 2
0x180014070  jnz     short loc_180014081
0x180014072  and     eax, 0FFFFF63Eh
0x180014077  and     ebx, 9C1h
0x18001407d  or      eax, ebx
0x18001407f  mov     [rdi], eax
0x180014081  mov     rbx, [rsp+38h+arg_10]
0x180014086  mov     rax, rdi
0x180014089  add     rsp, 20h
0x18001408d  pop     rdi
0x18001408e  pop     rsi
0x18001408f  pop     rbp
0x180014090  retn
```
