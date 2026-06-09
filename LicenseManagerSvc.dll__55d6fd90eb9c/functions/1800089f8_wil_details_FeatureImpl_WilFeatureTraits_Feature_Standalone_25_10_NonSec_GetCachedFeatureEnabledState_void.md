# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800089f8`
- end: `0x180008ad1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4b0`

## callees

- `0x1800085b4`
- `0x1800089f8`
- `0x180008e40`
- `0x18000ab04`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x1800089f8  mov     [rsp+arg_10], rbx
0x1800089fd  mov     [rsp+arg_0], rcx
0x180008a02  push    rbp
0x180008a03  push    rsi
0x180008a04  push    rdi
0x180008a05  sub     rsp, 20h
0x180008a09  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180008a10  mov     rdi, rdx
0x180008a13  mov     qword ptr [rdx], 0
0x180008a1a  mov     eax, [rsi]
0x180008a1c  mov     [rdx], eax
0x180008a1e  and     eax, 6
0x180008a21  cmp     al, 6
0x180008a23  jz      loc_180008AC1
0x180008a29  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008a2e  lea     r8, [rsp+38h+arg_0]
0x180008a33  mov     dword ptr [rsp+38h+arg_0], 0
0x180008a3b  lea     rdx, [rsp+38h+arg_8]
0x180008a40  mov     ebp, eax
0x180008a42  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180008a47  mov     eax, [rdi]
0x180008a49  mov     rbx, [rsp+38h+arg_8]
0x180008a4e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008a53  mov     edx, eax
0x180008a55  mov     [rdi], eax
0x180008a57  mov     ecx, eax
0x180008a59  jz      short loc_180008A74
0x180008a5b  test    dl, 2
0x180008a5e  jnz     short loc_180008A74
0x180008a60  and     ecx, 0FFFFF63Eh
0x180008a66  mov     eax, ebx
0x180008a68  and     eax, 9C1h
0x180008a6d  or      ecx, eax
0x180008a6f  or      ecx, 2
0x180008a72  mov     [rdi], ecx
0x180008a74  mov     r8d, edx
0x180008a77  and     r8d, 4
0x180008a7b  jnz     short loc_180008A8F
0x180008a7d  btr     ecx, 0Ah
0x180008a81  mov     eax, ebx
0x180008a83  and     eax, 400h
0x180008a88  or      ecx, eax
0x180008a8a  or      ecx, 4
0x180008a8d  mov     [rdi], ecx
0x180008a8f  mov     eax, edx
0x180008a91  lock cmpxchg [rsi], ecx
0x180008a95  jnz     short loc_180008A4E
0x180008a97  test    r8d, r8d
0x180008a9a  jnz     short loc_180008AAC
0x180008a9c  mov     r8d, ebp
0x180008a9f  mov     edx, 3
0x180008aa4  mov     rcx, rsi
0x180008aa7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008aac  mov     eax, [rdi]
0x180008aae  test    al, 2
0x180008ab0  jnz     short loc_180008AC1
0x180008ab2  and     eax, 0FFFFF63Eh
0x180008ab7  and     ebx, 9C1h
0x180008abd  or      eax, ebx
0x180008abf  mov     [rdi], eax
0x180008ac1  mov     rbx, [rsp+38h+arg_10]
0x180008ac6  mov     rax, rdi
0x180008ac9  add     rsp, 20h
0x180008acd  pop     rdi
0x180008ace  pop     rsi
0x180008acf  pop     rbp
0x180008ad0  retn
```
