# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180013c38`
- end: `0x180013d11`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800154d8`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013c38`
- `0x18001494c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180013c38  mov     [rsp+arg_10], rbx
0x180013c3d  mov     [rsp+arg_0], rcx
0x180013c42  push    rbp
0x180013c43  push    rsi
0x180013c44  push    rdi
0x180013c45  sub     rsp, 20h
0x180013c49  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180013c50  mov     rdi, rdx
0x180013c53  mov     qword ptr [rdx], 0
0x180013c5a  mov     eax, [rsi]
0x180013c5c  mov     [rdx], eax
0x180013c5e  and     eax, 6
0x180013c61  cmp     al, 6
0x180013c63  jz      loc_180013D01
0x180013c69  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013c6e  lea     r8, [rsp+38h+arg_0]
0x180013c73  mov     dword ptr [rsp+38h+arg_0], 0
0x180013c7b  lea     rdx, [rsp+38h+arg_8]
0x180013c80  mov     ebp, eax
0x180013c82  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x180013c87  mov     eax, [rdi]
0x180013c89  mov     rbx, [rsp+38h+arg_8]
0x180013c8e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013c93  mov     edx, eax
0x180013c95  mov     [rdi], eax
0x180013c97  mov     ecx, eax
0x180013c99  jz      short loc_180013CB4
0x180013c9b  test    dl, 2
0x180013c9e  jnz     short loc_180013CB4
0x180013ca0  and     ecx, 0FFFFF63Eh
0x180013ca6  mov     eax, ebx
0x180013ca8  and     eax, 9C1h
0x180013cad  or      ecx, eax
0x180013caf  or      ecx, 2
0x180013cb2  mov     [rdi], ecx
0x180013cb4  mov     r8d, edx
0x180013cb7  and     r8d, 4
0x180013cbb  jnz     short loc_180013CCF
0x180013cbd  btr     ecx, 0Ah
0x180013cc1  mov     eax, ebx
0x180013cc3  and     eax, 400h
0x180013cc8  or      ecx, eax
0x180013cca  or      ecx, 4
0x180013ccd  mov     [rdi], ecx
0x180013ccf  mov     eax, edx
0x180013cd1  lock cmpxchg [rsi], ecx
0x180013cd5  jnz     short loc_180013C8E
0x180013cd7  test    r8d, r8d
0x180013cda  jnz     short loc_180013CEC
0x180013cdc  mov     r8d, ebp
0x180013cdf  mov     edx, 3
0x180013ce4  mov     rcx, rsi
0x180013ce7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013cec  mov     eax, [rdi]
0x180013cee  test    al, 2
0x180013cf0  jnz     short loc_180013D01
0x180013cf2  and     eax, 0FFFFF63Eh
0x180013cf7  and     ebx, 9C1h
0x180013cfd  or      eax, ebx
0x180013cff  mov     [rdi], eax
0x180013d01  mov     rbx, [rsp+38h+arg_10]
0x180013d06  mov     rax, rdi
0x180013d09  add     rsp, 20h
0x180013d0d  pop     rdi
0x180013d0e  pop     rsi
0x180013d0f  pop     rbp
0x180013d10  retn
```
