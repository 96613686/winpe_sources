# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCachedFeatureEnabledState(void)

- ea: `0x1800149ac`
- end: `0x180014a85`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017224`
- `0x180017c6c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x1800149ac`
- `0x1800158d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixes2D__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixes2D__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixes2D__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixes2D__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800149ac  mov     [rsp+arg_10], rbx
0x1800149b1  mov     [rsp+arg_0], rcx
0x1800149b6  push    rbp
0x1800149b7  push    rsi
0x1800149b8  push    rdi
0x1800149b9  sub     rsp, 20h
0x1800149bd  mov     rsi, cs:Feature_BugFixes2D__descriptor
0x1800149c4  mov     rdi, rdx
0x1800149c7  mov     qword ptr [rdx], 0
0x1800149ce  mov     eax, [rsi]
0x1800149d0  mov     [rdx], eax
0x1800149d2  and     eax, 6
0x1800149d5  cmp     al, 6
0x1800149d7  jz      loc_180014A75
0x1800149dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800149e2  lea     r8, [rsp+38h+arg_0]
0x1800149e7  mov     dword ptr [rsp+38h+arg_0], 0
0x1800149ef  lea     rdx, [rsp+38h+arg_8]
0x1800149f4  mov     ebp, eax
0x1800149f6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCurrentFeatureEnabledState(int *)
0x1800149fb  mov     eax, [rdi]
0x1800149fd  mov     rbx, [rsp+38h+arg_8]
0x180014a02  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014a07  mov     edx, eax
0x180014a09  mov     [rdi], eax
0x180014a0b  mov     ecx, eax
0x180014a0d  jz      short loc_180014A28
0x180014a0f  test    dl, 2
0x180014a12  jnz     short loc_180014A28
0x180014a14  and     ecx, 0FFFFF63Eh
0x180014a1a  mov     eax, ebx
0x180014a1c  and     eax, 9C1h
0x180014a21  or      ecx, eax
0x180014a23  or      ecx, 2
0x180014a26  mov     [rdi], ecx
0x180014a28  mov     r8d, edx
0x180014a2b  and     r8d, 4
0x180014a2f  jnz     short loc_180014A43
0x180014a31  btr     ecx, 0Ah
0x180014a35  mov     eax, ebx
0x180014a37  and     eax, 400h
0x180014a3c  or      ecx, eax
0x180014a3e  or      ecx, 4
0x180014a41  mov     [rdi], ecx
0x180014a43  mov     eax, edx
0x180014a45  lock cmpxchg [rsi], ecx
0x180014a49  jnz     short loc_180014A02
0x180014a4b  test    r8d, r8d
0x180014a4e  jnz     short loc_180014A60
0x180014a50  mov     r8d, ebp
0x180014a53  mov     edx, 3
0x180014a58  mov     rcx, rsi
0x180014a5b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014a60  mov     eax, [rdi]
0x180014a62  test    al, 2
0x180014a64  jnz     short loc_180014A75
0x180014a66  and     eax, 0FFFFF63Eh
0x180014a6b  and     ebx, 9C1h
0x180014a71  or      eax, ebx
0x180014a73  mov     [rdi], eax
0x180014a75  mov     rbx, [rsp+38h+arg_10]
0x180014a7a  mov     rax, rdi
0x180014a7d  add     rsp, 20h
0x180014a81  pop     rdi
0x180014a82  pop     rsi
0x180014a83  pop     rbp
0x180014a84  retn
```
