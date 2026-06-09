# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCachedFeatureEnabledState(void)

- ea: `0x180014b6c`
- end: `0x180014c45`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001733c`
- `0x180017ce4`

## callees

- `0x18000543c`
- `0x180008794`
- `0x180014b6c`
- `0x180015a64`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixesQ3__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixesQ3__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_BugFixesQ3__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_BugFixesQ3__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180014b6c  mov     [rsp+arg_10], rbx
0x180014b71  mov     [rsp+arg_0], rcx
0x180014b76  push    rbp
0x180014b77  push    rsi
0x180014b78  push    rdi
0x180014b79  sub     rsp, 20h
0x180014b7d  mov     rsi, cs:Feature_BugFixesQ3__descriptor
0x180014b84  mov     rdi, rdx
0x180014b87  mov     qword ptr [rdx], 0
0x180014b8e  mov     eax, [rsi]
0x180014b90  mov     [rdx], eax
0x180014b92  and     eax, 6
0x180014b95  cmp     al, 6
0x180014b97  jz      loc_180014C35
0x180014b9d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014ba2  lea     r8, [rsp+38h+arg_0]
0x180014ba7  mov     dword ptr [rsp+38h+arg_0], 0
0x180014baf  lea     rdx, [rsp+38h+arg_8]
0x180014bb4  mov     ebp, eax
0x180014bb6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCurrentFeatureEnabledState(int *)
0x180014bbb  mov     eax, [rdi]
0x180014bbd  mov     rbx, [rsp+38h+arg_8]
0x180014bc2  cmp     dword ptr [rsp+38h+arg_0], 0
0x180014bc7  mov     edx, eax
0x180014bc9  mov     [rdi], eax
0x180014bcb  mov     ecx, eax
0x180014bcd  jz      short loc_180014BE8
0x180014bcf  test    dl, 2
0x180014bd2  jnz     short loc_180014BE8
0x180014bd4  and     ecx, 0FFFFF63Eh
0x180014bda  mov     eax, ebx
0x180014bdc  and     eax, 9C1h
0x180014be1  or      ecx, eax
0x180014be3  or      ecx, 2
0x180014be6  mov     [rdi], ecx
0x180014be8  mov     r8d, edx
0x180014beb  and     r8d, 4
0x180014bef  jnz     short loc_180014C03
0x180014bf1  btr     ecx, 0Ah
0x180014bf5  mov     eax, ebx
0x180014bf7  and     eax, 400h
0x180014bfc  or      ecx, eax
0x180014bfe  or      ecx, 4
0x180014c01  mov     [rdi], ecx
0x180014c03  mov     eax, edx
0x180014c05  lock cmpxchg [rsi], ecx
0x180014c09  jnz     short loc_180014BC2
0x180014c0b  test    r8d, r8d
0x180014c0e  jnz     short loc_180014C20
0x180014c10  mov     r8d, ebp
0x180014c13  mov     edx, 3
0x180014c18  mov     rcx, rsi
0x180014c1b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014c20  mov     eax, [rdi]
0x180014c22  test    al, 2
0x180014c24  jnz     short loc_180014C35
0x180014c26  and     eax, 0FFFFF63Eh
0x180014c2b  and     ebx, 9C1h
0x180014c31  or      eax, ebx
0x180014c33  mov     [rdi], eax
0x180014c35  mov     rbx, [rsp+38h+arg_10]
0x180014c3a  mov     rax, rdi
0x180014c3d  add     rsp, 20h
0x180014c41  pop     rdi
0x180014c42  pop     rsi
0x180014c43  pop     rbp
0x180014c44  retn
```
