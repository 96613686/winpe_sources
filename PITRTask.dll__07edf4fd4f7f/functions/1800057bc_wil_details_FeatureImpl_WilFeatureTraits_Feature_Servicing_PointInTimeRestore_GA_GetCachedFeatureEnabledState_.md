# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(void)

- ea: `0x1800057bc`
- end: `0x1800058a7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800087f4`
- `0x18000bb90`
- `0x18000bbd0`

## callees

- `0x180004f64`
- `0x1800057bc`
- `0x180005e88`
- `0x180009800`
- `0x1800107c0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_PointInTimeRestore_GA__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_PointInTimeRestore_GA__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_PointInTimeRestore_GA__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800057bc  push    rbx
0x1800057be  push    rbp
0x1800057bf  push    rsi
0x1800057c0  push    rdi
0x1800057c1  sub     rsp, 48h
0x1800057c5  mov     rax, cs:__security_cookie
0x1800057cc  xor     rax, rsp
0x1800057cf  mov     [rsp+68h+var_38], rax
0x1800057d4  mov     rsi, cs:Feature_Servicing_PointInTimeRestore_GA__descriptor
0x1800057db  mov     rdi, rdx
0x1800057de  mov     qword ptr [rdx], 0
0x1800057e5  mov     eax, [rsi]
0x1800057e7  mov     [rdx], eax
0x1800057e9  and     eax, 6
0x1800057ec  cmp     al, 6
0x1800057ee  jz      loc_18000588E
0x1800057f4  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800057f9  lea     r8, [rsp+68h+var_40]
0x1800057fe  mov     [rsp+68h+var_40], 0
0x180005806  lea     rdx, [rsp+68h+var_48]
0x18000580b  mov     ebp, eax
0x18000580d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(int *)
0x180005812  mov     eax, [rdi]
0x180005814  mov     rbx, [rsp+68h+var_48]
0x180005819  cmp     [rsp+68h+var_40], 0
0x18000581e  mov     edx, eax
0x180005820  mov     [rdi], eax
0x180005822  mov     ecx, eax
0x180005824  jz      short loc_18000583F
0x180005826  test    dl, 2
0x180005829  jnz     short loc_18000583F
0x18000582b  and     ecx, 0FFFFF63Eh
0x180005831  mov     eax, ebx
0x180005833  and     eax, 9C1h
0x180005838  or      ecx, eax
0x18000583a  or      ecx, 2
0x18000583d  mov     [rdi], ecx
0x18000583f  mov     r8d, edx
0x180005842  and     r8d, 4
0x180005846  jnz     short loc_18000585A
0x180005848  btr     ecx, 0Ah
0x18000584c  mov     eax, ebx
0x18000584e  and     eax, 400h
0x180005853  or      ecx, eax
0x180005855  or      ecx, 4
0x180005858  mov     [rdi], ecx
0x18000585a  mov     eax, edx
0x18000585c  lock cmpxchg [rsi], ecx
0x180005860  jnz     short loc_180005819
0x180005862  test    r8d, r8d
0x180005865  jnz     short loc_180005877
0x180005867  mov     r8d, ebp
0x18000586a  mov     edx, 3
0x18000586f  mov     rcx, rsi
0x180005872  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005877  mov     ecx, [rdi]
0x180005879  test    cl, 2
0x18000587c  jnz     short loc_18000588E
0x18000587e  and     ecx, 0FFFFF63Eh
0x180005884  and     ebx, 9C1h
0x18000588a  or      ecx, ebx
0x18000588c  mov     [rdi], ecx
0x18000588e  mov     rax, rdi
0x180005891  mov     rcx, [rsp+68h+var_38]
0x180005896  xor     rcx, rsp; StackCookie
0x180005899  call    __security_check_cookie
0x18000589e  add     rsp, 48h
0x1800058a2  pop     rdi
0x1800058a3  pop     rsi
0x1800058a4  pop     rbp
0x1800058a5  pop     rbx
0x1800058a6  retn
```
