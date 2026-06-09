# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCachedFeatureEnabledState(void)

- ea: `0x18003649c`
- end: `0x180036587`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180039ce4`
- `0x18003be88`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x18003649c`
- `0x18003721c`
- `0x18003b548`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_BufferOverflowFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_BufferOverflowFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_BufferOverflowFix__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_BufferOverflowFix__descriptor,
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
0x18003649c  push    rbx
0x18003649e  push    rbp
0x18003649f  push    rsi
0x1800364a0  push    rdi
0x1800364a1  sub     rsp, 48h
0x1800364a5  mov     rax, cs:__security_cookie
0x1800364ac  xor     rax, rsp
0x1800364af  mov     [rsp+68h+var_38], rax
0x1800364b4  mov     rsi, cs:Feature_Servicing_BufferOverflowFix__descriptor
0x1800364bb  mov     rdi, rdx
0x1800364be  mov     qword ptr [rdx], 0
0x1800364c5  mov     eax, [rsi]
0x1800364c7  mov     [rdx], eax
0x1800364c9  and     eax, 6
0x1800364cc  cmp     al, 6
0x1800364ce  jz      loc_18003656E
0x1800364d4  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800364d9  lea     r8, [rsp+68h+var_40]
0x1800364de  mov     [rsp+68h+var_40], 0
0x1800364e6  lea     rdx, [rsp+68h+var_48]
0x1800364eb  mov     ebp, eax
0x1800364ed  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(int *)
0x1800364f2  mov     eax, [rdi]
0x1800364f4  mov     rbx, [rsp+68h+var_48]
0x1800364f9  cmp     [rsp+68h+var_40], 0
0x1800364fe  mov     edx, eax
0x180036500  mov     [rdi], eax
0x180036502  mov     ecx, eax
0x180036504  jz      short loc_18003651F
0x180036506  test    dl, 2
0x180036509  jnz     short loc_18003651F
0x18003650b  and     ecx, 0FFFFF63Eh
0x180036511  mov     eax, ebx
0x180036513  and     eax, 9C1h
0x180036518  or      ecx, eax
0x18003651a  or      ecx, 2
0x18003651d  mov     [rdi], ecx
0x18003651f  mov     r8d, edx
0x180036522  and     r8d, 4
0x180036526  jnz     short loc_18003653A
0x180036528  btr     ecx, 0Ah
0x18003652c  mov     eax, ebx
0x18003652e  and     eax, 400h
0x180036533  or      ecx, eax
0x180036535  or      ecx, 4
0x180036538  mov     [rdi], ecx
0x18003653a  mov     eax, edx
0x18003653c  lock cmpxchg [rsi], ecx
0x180036540  jnz     short loc_1800364F9
0x180036542  test    r8d, r8d
0x180036545  jnz     short loc_180036557
0x180036547  mov     r8d, ebp
0x18003654a  mov     edx, 3
0x18003654f  mov     rcx, rsi
0x180036552  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036557  mov     ecx, [rdi]
0x180036559  test    cl, 2
0x18003655c  jnz     short loc_18003656E
0x18003655e  and     ecx, 0FFFFF63Eh
0x180036564  and     ebx, 9C1h
0x18003656a  or      ecx, ebx
0x18003656c  mov     [rdi], ecx
0x18003656e  mov     rax, rdi
0x180036571  mov     rcx, [rsp+68h+var_38]
0x180036576  xor     rcx, rsp; StackCookie
0x180036579  call    __security_check_cookie
0x18003657e  add     rsp, 48h
0x180036582  pop     rdi
0x180036583  pop     rsi
0x180036584  pop     rbp
0x180036585  pop     rbx
0x180036586  retn
```
