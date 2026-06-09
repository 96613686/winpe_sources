# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800242c8`
- end: `0x1800243b3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002476c`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180016180`
- `0x1800242c8`
- `0x180024578`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
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
0x1800242c8  push    rbx
0x1800242ca  push    rbp
0x1800242cb  push    rsi
0x1800242cc  push    rdi
0x1800242cd  sub     rsp, 48h
0x1800242d1  mov     rax, cs:__security_cookie
0x1800242d8  xor     rax, rsp
0x1800242db  mov     [rsp+68h+var_38], rax
0x1800242e0  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800242e7  mov     rdi, rdx
0x1800242ea  mov     qword ptr [rdx], 0
0x1800242f1  mov     eax, [rsi]
0x1800242f3  mov     [rdx], eax
0x1800242f5  and     eax, 6
0x1800242f8  cmp     al, 6
0x1800242fa  jz      loc_18002439A
0x180024300  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180024305  lea     r8, [rsp+68h+var_40]
0x18002430a  mov     [rsp+68h+var_40], 0
0x180024312  lea     rdx, [rsp+68h+var_48]
0x180024317  mov     ebp, eax
0x180024319  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x18002431e  mov     eax, [rdi]
0x180024320  mov     rbx, [rsp+68h+var_48]
0x180024325  cmp     [rsp+68h+var_40], 0
0x18002432a  mov     edx, eax
0x18002432c  mov     [rdi], eax
0x18002432e  mov     ecx, eax
0x180024330  jz      short loc_18002434B
0x180024332  test    dl, 2
0x180024335  jnz     short loc_18002434B
0x180024337  and     ecx, 0FFFFF63Eh
0x18002433d  mov     eax, ebx
0x18002433f  and     eax, 9C1h
0x180024344  or      ecx, eax
0x180024346  or      ecx, 2
0x180024349  mov     [rdi], ecx
0x18002434b  mov     r8d, edx
0x18002434e  and     r8d, 4
0x180024352  jnz     short loc_180024366
0x180024354  btr     ecx, 0Ah
0x180024358  mov     eax, ebx
0x18002435a  and     eax, 400h
0x18002435f  or      ecx, eax
0x180024361  or      ecx, 4
0x180024364  mov     [rdi], ecx
0x180024366  mov     eax, edx
0x180024368  lock cmpxchg [rsi], ecx
0x18002436c  jnz     short loc_180024325
0x18002436e  test    r8d, r8d
0x180024371  jnz     short loc_180024383
0x180024373  mov     r8d, ebp
0x180024376  mov     edx, 3
0x18002437b  mov     rcx, rsi
0x18002437e  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180024383  mov     ecx, [rdi]
0x180024385  test    cl, 2
0x180024388  jnz     short loc_18002439A
0x18002438a  and     ecx, 0FFFFF63Eh
0x180024390  and     ebx, 9C1h
0x180024396  or      ecx, ebx
0x180024398  mov     [rdi], ecx
0x18002439a  mov     rax, rdi
0x18002439d  mov     rcx, [rsp+68h+var_38]
0x1800243a2  xor     rcx, rsp; StackCookie
0x1800243a5  call    __security_check_cookie
0x1800243aa  add     rsp, 48h
0x1800243ae  pop     rdi
0x1800243af  pop     rsi
0x1800243b0  pop     rbp
0x1800243b1  pop     rbx
0x1800243b2  retn
```
