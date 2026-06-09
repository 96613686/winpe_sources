# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetCachedFeatureEnabledState(void)

- ea: `0x18001e994`
- end: `0x18001ea7f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fc30`
- `0x180022b3c`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180016180`
- `0x18001e994`
- `0x18001ead0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_RadioManager_Fix_NullRadioInstance__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_RadioManager_Fix_NullRadioInstance__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_RadioManager_Fix_NullRadioInstance__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_RadioManager_Fix_NullRadioInstance__descriptor,
        1,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001e994  push    rbx
0x18001e996  push    rbp
0x18001e997  push    rsi
0x18001e998  push    rdi
0x18001e999  sub     rsp, 48h
0x18001e99d  mov     rax, cs:__security_cookie
0x18001e9a4  xor     rax, rsp
0x18001e9a7  mov     [rsp+68h+var_38], rax
0x18001e9ac  mov     rsi, cs:Feature_RadioManager_Fix_NullRadioInstance__descriptor
0x18001e9b3  mov     rdi, rdx
0x18001e9b6  mov     qword ptr [rdx], 0
0x18001e9bd  mov     eax, [rsi]
0x18001e9bf  mov     [rdx], eax
0x18001e9c1  and     eax, 6
0x18001e9c4  cmp     al, 6
0x18001e9c6  jz      loc_18001EA66
0x18001e9cc  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001e9d1  lea     r8, [rsp+68h+var_40]
0x18001e9d6  mov     [rsp+68h+var_40], 0
0x18001e9de  lea     rdx, [rsp+68h+var_48]
0x18001e9e3  mov     ebp, eax
0x18001e9e5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetCurrentFeatureEnabledState(int *)
0x18001e9ea  mov     eax, [rdi]
0x18001e9ec  mov     rbx, [rsp+68h+var_48]
0x18001e9f1  cmp     [rsp+68h+var_40], 0
0x18001e9f6  mov     edx, eax
0x18001e9f8  mov     [rdi], eax
0x18001e9fa  mov     ecx, eax
0x18001e9fc  jz      short loc_18001EA17
0x18001e9fe  test    dl, 2
0x18001ea01  jnz     short loc_18001EA17
0x18001ea03  and     ecx, 0FFFFF63Eh
0x18001ea09  mov     eax, ebx
0x18001ea0b  and     eax, 9C1h
0x18001ea10  or      ecx, eax
0x18001ea12  or      ecx, 2
0x18001ea15  mov     [rdi], ecx
0x18001ea17  mov     r8d, edx
0x18001ea1a  and     r8d, 4
0x18001ea1e  jnz     short loc_18001EA32
0x18001ea20  btr     ecx, 0Ah
0x18001ea24  mov     eax, ebx
0x18001ea26  and     eax, 400h
0x18001ea2b  or      ecx, eax
0x18001ea2d  or      ecx, 4
0x18001ea30  mov     [rdi], ecx
0x18001ea32  mov     eax, edx
0x18001ea34  lock cmpxchg [rsi], ecx
0x18001ea38  jnz     short loc_18001E9F1
0x18001ea3a  test    r8d, r8d
0x18001ea3d  jnz     short loc_18001EA4F
0x18001ea3f  mov     r8d, ebp
0x18001ea42  mov     edx, 1
0x18001ea47  mov     rcx, rsi
0x18001ea4a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ea4f  mov     ecx, [rdi]
0x18001ea51  test    cl, 2
0x18001ea54  jnz     short loc_18001EA66
0x18001ea56  and     ecx, 0FFFFF63Eh
0x18001ea5c  and     ebx, 9C1h
0x18001ea62  or      ecx, ebx
0x18001ea64  mov     [rdi], ecx
0x18001ea66  mov     rax, rdi
0x18001ea69  mov     rcx, [rsp+68h+var_38]
0x18001ea6e  xor     rcx, rsp; StackCookie
0x18001ea71  call    __security_check_cookie
0x18001ea76  add     rsp, 48h
0x18001ea7a  pop     rdi
0x18001ea7b  pop     rsi
0x18001ea7c  pop     rbp
0x18001ea7d  pop     rbx
0x18001ea7e  retn
```
