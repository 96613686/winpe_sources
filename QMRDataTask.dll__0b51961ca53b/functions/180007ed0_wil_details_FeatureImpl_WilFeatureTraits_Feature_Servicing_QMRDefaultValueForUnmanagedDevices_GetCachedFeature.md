# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCachedFeatureEnabledState(void)

- ea: `0x180007ed0`
- end: `0x180007fa9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800117a0`

## callees

- `0x18000787c`
- `0x180007ed0`
- `0x180008c88`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_QMRDefaultValueForUnmanagedDevices__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_QMRDefaultValueForUnmanagedDevices__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_QMRDefaultValueForUnmanagedDevices__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_QMRDefaultValueForUnmanagedDevices__descriptor,
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
0x180007ed0  mov     [rsp+arg_10], rbx
0x180007ed5  mov     [rsp+arg_0], rcx
0x180007eda  push    rbp
0x180007edb  push    rsi
0x180007edc  push    rdi
0x180007edd  sub     rsp, 20h
0x180007ee1  mov     rsi, cs:Feature_Servicing_QMRDefaultValueForUnmanagedDevices__descriptor
0x180007ee8  mov     rdi, rdx
0x180007eeb  mov     qword ptr [rdx], 0
0x180007ef2  mov     eax, [rsi]
0x180007ef4  mov     [rdx], eax
0x180007ef6  and     eax, 6
0x180007ef9  cmp     al, 6
0x180007efb  jz      loc_180007F99
0x180007f01  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007f06  lea     r8, [rsp+38h+arg_0]
0x180007f0b  mov     dword ptr [rsp+38h+arg_0], 0
0x180007f13  lea     rdx, [rsp+38h+arg_8]
0x180007f18  mov     ebp, eax
0x180007f1a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetCurrentFeatureEnabledState(int *)
0x180007f1f  mov     eax, [rdi]
0x180007f21  mov     rbx, [rsp+38h+arg_8]
0x180007f26  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007f2b  mov     edx, eax
0x180007f2d  mov     [rdi], eax
0x180007f2f  mov     ecx, eax
0x180007f31  jz      short loc_180007F4C
0x180007f33  test    dl, 2
0x180007f36  jnz     short loc_180007F4C
0x180007f38  and     ecx, 0FFFFF63Eh
0x180007f3e  mov     eax, ebx
0x180007f40  and     eax, 9C1h
0x180007f45  or      ecx, eax
0x180007f47  or      ecx, 2
0x180007f4a  mov     [rdi], ecx
0x180007f4c  mov     r8d, edx
0x180007f4f  and     r8d, 4
0x180007f53  jnz     short loc_180007F67
0x180007f55  btr     ecx, 0Ah
0x180007f59  mov     eax, ebx
0x180007f5b  and     eax, 400h
0x180007f60  or      ecx, eax
0x180007f62  or      ecx, 4
0x180007f65  mov     [rdi], ecx
0x180007f67  mov     eax, edx
0x180007f69  lock cmpxchg [rsi], ecx
0x180007f6d  jnz     short loc_180007F26
0x180007f6f  test    r8d, r8d
0x180007f72  jnz     short loc_180007F84
0x180007f74  mov     r8d, ebp
0x180007f77  mov     edx, 3
0x180007f7c  mov     rcx, rsi
0x180007f7f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007f84  mov     eax, [rdi]
0x180007f86  test    al, 2
0x180007f88  jnz     short loc_180007F99
0x180007f8a  and     eax, 0FFFFF63Eh
0x180007f8f  and     ebx, 9C1h
0x180007f95  or      eax, ebx
0x180007f97  mov     [rdi], eax
0x180007f99  mov     rbx, [rsp+38h+arg_10]
0x180007f9e  mov     rax, rdi
0x180007fa1  add     rsp, 20h
0x180007fa5  pop     rdi
0x180007fa6  pop     rsi
0x180007fa7  pop     rbp
0x180007fa8  retn
```
