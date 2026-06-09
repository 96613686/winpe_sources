# wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c7b8`
- end: `0x18000c891`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cb60`
- `0x1800171d8`

## callees

- `0x1800085b4`
- `0x18000ab04`
- `0x18000c7b8`
- `0x18000c978`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_InstallServiceShutdown__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_InstallServiceShutdown__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_InstallServiceShutdown__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_InstallServiceShutdown__descriptor,
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
0x18000c7b8  mov     [rsp+arg_10], rbx
0x18000c7bd  mov     [rsp+arg_0], rcx
0x18000c7c2  push    rbp
0x18000c7c3  push    rsi
0x18000c7c4  push    rdi
0x18000c7c5  sub     rsp, 20h
0x18000c7c9  mov     rsi, cs:Feature_InstallServiceShutdown__descriptor
0x18000c7d0  mov     rdi, rdx
0x18000c7d3  mov     qword ptr [rdx], 0
0x18000c7da  mov     eax, [rsi]
0x18000c7dc  mov     [rdx], eax
0x18000c7de  and     eax, 6
0x18000c7e1  cmp     al, 6
0x18000c7e3  jz      loc_18000C881
0x18000c7e9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c7ee  lea     r8, [rsp+38h+arg_0]
0x18000c7f3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c7fb  lea     rdx, [rsp+38h+arg_8]
0x18000c800  mov     ebp, eax
0x18000c802  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCurrentFeatureEnabledState(int *)
0x18000c807  mov     eax, [rdi]
0x18000c809  mov     rbx, [rsp+38h+arg_8]
0x18000c80e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c813  mov     edx, eax
0x18000c815  mov     [rdi], eax
0x18000c817  mov     ecx, eax
0x18000c819  jz      short loc_18000C834
0x18000c81b  test    dl, 2
0x18000c81e  jnz     short loc_18000C834
0x18000c820  and     ecx, 0FFFFF63Eh
0x18000c826  mov     eax, ebx
0x18000c828  and     eax, 9C1h
0x18000c82d  or      ecx, eax
0x18000c82f  or      ecx, 2
0x18000c832  mov     [rdi], ecx
0x18000c834  mov     r8d, edx
0x18000c837  and     r8d, 4
0x18000c83b  jnz     short loc_18000C84F
0x18000c83d  btr     ecx, 0Ah
0x18000c841  mov     eax, ebx
0x18000c843  and     eax, 400h
0x18000c848  or      ecx, eax
0x18000c84a  or      ecx, 4
0x18000c84d  mov     [rdi], ecx
0x18000c84f  mov     eax, edx
0x18000c851  lock cmpxchg [rsi], ecx
0x18000c855  jnz     short loc_18000C80E
0x18000c857  test    r8d, r8d
0x18000c85a  jnz     short loc_18000C86C
0x18000c85c  mov     r8d, ebp
0x18000c85f  mov     edx, 3
0x18000c864  mov     rcx, rsi
0x18000c867  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c86c  mov     eax, [rdi]
0x18000c86e  test    al, 2
0x18000c870  jnz     short loc_18000C881
0x18000c872  and     eax, 0FFFFF63Eh
0x18000c877  and     ebx, 9C1h
0x18000c87d  or      eax, ebx
0x18000c87f  mov     [rdi], eax
0x18000c881  mov     rbx, [rsp+38h+arg_10]
0x18000c886  mov     rax, rdi
0x18000c889  add     rsp, 20h
0x18000c88d  pop     rdi
0x18000c88e  pop     rsi
0x18000c88f  pop     rbp
0x18000c890  retn
```
