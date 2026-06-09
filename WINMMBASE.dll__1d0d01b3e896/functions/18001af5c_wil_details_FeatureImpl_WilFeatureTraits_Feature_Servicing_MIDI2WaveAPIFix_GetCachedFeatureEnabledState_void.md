# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCachedFeatureEnabledState(void)

- ea: `0x18001af5c`
- end: `0x18001b035`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c28c`
- `0x18001c870`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001af5c`
- `0x18001b9cc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2WaveAPIFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2WaveAPIFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_MIDI2WaveAPIFix__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_MIDI2WaveAPIFix__descriptor,
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
0x18001af5c  mov     [rsp+arg_10], rbx
0x18001af61  mov     [rsp+arg_0], rcx
0x18001af66  push    rbp
0x18001af67  push    rsi
0x18001af68  push    rdi
0x18001af69  sub     rsp, 20h
0x18001af6d  mov     rsi, cs:Feature_Servicing_MIDI2WaveAPIFix__descriptor
0x18001af74  mov     rdi, rdx
0x18001af77  mov     qword ptr [rdx], 0
0x18001af7e  mov     eax, [rsi]
0x18001af80  mov     [rdx], eax
0x18001af82  and     eax, 6
0x18001af85  cmp     al, 6
0x18001af87  jz      loc_18001B025
0x18001af8d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001af92  lea     r8, [rsp+38h+arg_0]
0x18001af97  mov     dword ptr [rsp+38h+arg_0], 0
0x18001af9f  lea     rdx, [rsp+38h+arg_8]
0x18001afa4  mov     ebp, eax
0x18001afa6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCurrentFeatureEnabledState(int *)
0x18001afab  mov     eax, [rdi]
0x18001afad  mov     rbx, [rsp+38h+arg_8]
0x18001afb2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001afb7  mov     edx, eax
0x18001afb9  mov     [rdi], eax
0x18001afbb  mov     ecx, eax
0x18001afbd  jz      short loc_18001AFD8
0x18001afbf  test    dl, 2
0x18001afc2  jnz     short loc_18001AFD8
0x18001afc4  and     ecx, 0FFFFF63Eh
0x18001afca  mov     eax, ebx
0x18001afcc  and     eax, 9C1h
0x18001afd1  or      ecx, eax
0x18001afd3  or      ecx, 2
0x18001afd6  mov     [rdi], ecx
0x18001afd8  mov     r8d, edx
0x18001afdb  and     r8d, 4
0x18001afdf  jnz     short loc_18001AFF3
0x18001afe1  btr     ecx, 0Ah
0x18001afe5  mov     eax, ebx
0x18001afe7  and     eax, 400h
0x18001afec  or      ecx, eax
0x18001afee  or      ecx, 4
0x18001aff1  mov     [rdi], ecx
0x18001aff3  mov     eax, edx
0x18001aff5  lock cmpxchg [rsi], ecx
0x18001aff9  jnz     short loc_18001AFB2
0x18001affb  test    r8d, r8d
0x18001affe  jnz     short loc_18001B010
0x18001b000  mov     r8d, ebp
0x18001b003  mov     edx, 3
0x18001b008  mov     rcx, rsi
0x18001b00b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001b010  mov     eax, [rdi]
0x18001b012  test    al, 2
0x18001b014  jnz     short loc_18001B025
0x18001b016  and     eax, 0FFFFF63Eh
0x18001b01b  and     ebx, 9C1h
0x18001b021  or      eax, ebx
0x18001b023  mov     [rdi], eax
0x18001b025  mov     rbx, [rsp+38h+arg_10]
0x18001b02a  mov     rax, rdi
0x18001b02d  add     rsp, 20h
0x18001b031  pop     rdi
0x18001b032  pop     rsi
0x18001b033  pop     rbp
0x18001b034  retn
```
