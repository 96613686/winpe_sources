# wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCachedFeatureEnabledState(void)

- ea: `0x180012e80`
- end: `0x180012f59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53100197@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800152c0`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180012e80`
- `0x180014478`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_53100197__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_53100197__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_53100197__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_53100197__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180012e80  mov     [rsp+arg_10], rbx
0x180012e85  mov     [rsp+arg_0], rcx
0x180012e8a  push    rbp
0x180012e8b  push    rsi
0x180012e8c  push    rdi
0x180012e8d  sub     rsp, 20h
0x180012e91  mov     rsi, cs:Feature_53100197__descriptor
0x180012e98  mov     rdi, rdx
0x180012e9b  mov     qword ptr [rdx], 0
0x180012ea2  mov     eax, [rsi]
0x180012ea4  mov     [rdx], eax
0x180012ea6  and     eax, 6
0x180012ea9  cmp     al, 6
0x180012eab  jz      loc_180012F49
0x180012eb1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012eb6  lea     r8, [rsp+38h+arg_0]
0x180012ebb  mov     dword ptr [rsp+38h+arg_0], 0
0x180012ec3  lea     rdx, [rsp+38h+arg_8]
0x180012ec8  mov     ebp, eax
0x180012eca  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53100197@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCurrentFeatureEnabledState(int *)
0x180012ecf  mov     eax, [rdi]
0x180012ed1  mov     rbx, [rsp+38h+arg_8]
0x180012ed6  cmp     dword ptr [rsp+38h+arg_0], 0
0x180012edb  mov     edx, eax
0x180012edd  mov     [rdi], eax
0x180012edf  mov     ecx, eax
0x180012ee1  jz      short loc_180012EFC
0x180012ee3  test    dl, 2
0x180012ee6  jnz     short loc_180012EFC
0x180012ee8  and     ecx, 0FFFFF63Eh
0x180012eee  mov     eax, ebx
0x180012ef0  and     eax, 9C1h
0x180012ef5  or      ecx, eax
0x180012ef7  or      ecx, 2
0x180012efa  mov     [rdi], ecx
0x180012efc  mov     r8d, edx
0x180012eff  and     r8d, 4
0x180012f03  jnz     short loc_180012F17
0x180012f05  btr     ecx, 0Ah
0x180012f09  mov     eax, ebx
0x180012f0b  and     eax, 400h
0x180012f10  or      ecx, eax
0x180012f12  or      ecx, 4
0x180012f15  mov     [rdi], ecx
0x180012f17  mov     eax, edx
0x180012f19  lock cmpxchg [rsi], ecx
0x180012f1d  jnz     short loc_180012ED6
0x180012f1f  test    r8d, r8d
0x180012f22  jnz     short loc_180012F34
0x180012f24  mov     r8d, ebp
0x180012f27  mov     edx, 3
0x180012f2c  mov     rcx, rsi
0x180012f2f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012f34  mov     eax, [rdi]
0x180012f36  test    al, 2
0x180012f38  jnz     short loc_180012F49
0x180012f3a  and     eax, 0FFFFF63Eh
0x180012f3f  and     ebx, 9C1h
0x180012f45  or      eax, ebx
0x180012f47  mov     [rdi], eax
0x180012f49  mov     rbx, [rsp+38h+arg_10]
0x180012f4e  mov     rax, rdi
0x180012f51  add     rsp, 20h
0x180012f55  pop     rdi
0x180012f56  pop     rsi
0x180012f57  pop     rbp
0x180012f58  retn
```
