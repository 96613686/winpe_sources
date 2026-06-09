# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x140005714`
- end: `0x1400057ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b7ac`

## callees

- `0x1400049e0`
- `0x140005714`
- `0x140005e70`
- `0x14000a88c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_ValAccTest__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x140005714  mov     [rsp+arg_10], rbx
0x140005719  mov     [rsp+arg_0], rcx
0x14000571e  push    rbp
0x14000571f  push    rsi
0x140005720  push    rdi
0x140005721  sub     rsp, 20h
0x140005725  mov     rsi, cs:Feature_ValAccTest__descriptor
0x14000572c  mov     rdi, rdx
0x14000572f  mov     qword ptr [rdx], 0
0x140005736  mov     eax, [rsi]
0x140005738  mov     [rdx], eax
0x14000573a  and     eax, 6
0x14000573d  cmp     al, 6
0x14000573f  jz      loc_1400057DD
0x140005745  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000574a  lea     r8, [rsp+38h+arg_0]
0x14000574f  mov     dword ptr [rsp+38h+arg_0], 0
0x140005757  lea     rdx, [rsp+38h+arg_8]
0x14000575c  mov     ebp, eax
0x14000575e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x140005763  mov     eax, [rdi]
0x140005765  mov     rbx, [rsp+38h+arg_8]
0x14000576a  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000576f  mov     edx, eax
0x140005771  mov     [rdi], eax
0x140005773  mov     ecx, eax
0x140005775  jz      short loc_140005790
0x140005777  test    dl, 2
0x14000577a  jnz     short loc_140005790
0x14000577c  and     ecx, 0FFFFF63Eh
0x140005782  mov     eax, ebx
0x140005784  and     eax, 9C1h
0x140005789  or      ecx, eax
0x14000578b  or      ecx, 2
0x14000578e  mov     [rdi], ecx
0x140005790  mov     r8d, edx
0x140005793  and     r8d, 4
0x140005797  jnz     short loc_1400057AB
0x140005799  btr     ecx, 0Ah
0x14000579d  mov     eax, ebx
0x14000579f  and     eax, 400h
0x1400057a4  or      ecx, eax
0x1400057a6  or      ecx, 4
0x1400057a9  mov     [rdi], ecx
0x1400057ab  mov     eax, edx
0x1400057ad  lock cmpxchg [rsi], ecx
0x1400057b1  jnz     short loc_14000576A
0x1400057b3  test    r8d, r8d
0x1400057b6  jnz     short loc_1400057C8
0x1400057b8  mov     r8d, ebp
0x1400057bb  mov     edx, 3
0x1400057c0  mov     rcx, rsi
0x1400057c3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400057c8  mov     eax, [rdi]
0x1400057ca  test    al, 2
0x1400057cc  jnz     short loc_1400057DD
0x1400057ce  and     eax, 0FFFFF63Eh
0x1400057d3  and     ebx, 9C1h
0x1400057d9  or      eax, ebx
0x1400057db  mov     [rdi], eax
0x1400057dd  mov     rbx, [rsp+38h+arg_10]
0x1400057e2  mov     rax, rdi
0x1400057e5  add     rsp, 20h
0x1400057e9  pop     rdi
0x1400057ea  pop     rsi
0x1400057eb  pop     rbp
0x1400057ec  retn
```
