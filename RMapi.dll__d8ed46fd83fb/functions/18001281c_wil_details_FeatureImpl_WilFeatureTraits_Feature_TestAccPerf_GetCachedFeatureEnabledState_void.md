# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001281c`
- end: `0x180012907`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151ec`
- `0x180016a80`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x18001281c`
- `0x180012e2c`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v12, &v13);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18001281c  push    rbx
0x18001281e  push    rbp
0x18001281f  push    rsi
0x180012820  push    rdi
0x180012821  sub     rsp, 48h
0x180012825  mov     rax, cs:__security_cookie
0x18001282c  xor     rax, rsp
0x18001282f  mov     [rsp+68h+var_38], rax
0x180012834  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18001283b  mov     rdi, rdx
0x18001283e  mov     qword ptr [rdx], 0
0x180012845  mov     eax, [rsi]
0x180012847  mov     [rdx], eax
0x180012849  and     eax, 6
0x18001284c  cmp     al, 6
0x18001284e  jz      loc_1800128EE
0x180012854  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012859  lea     r8, [rsp+68h+var_40]
0x18001285e  mov     [rsp+68h+var_40], 0
0x180012866  lea     rdx, [rsp+68h+var_48]
0x18001286b  mov     ebp, eax
0x18001286d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180012872  mov     eax, [rdi]
0x180012874  mov     rbx, [rsp+68h+var_48]
0x180012879  cmp     [rsp+68h+var_40], 0
0x18001287e  mov     edx, eax
0x180012880  mov     [rdi], eax
0x180012882  mov     ecx, eax
0x180012884  jz      short loc_18001289F
0x180012886  test    dl, 2
0x180012889  jnz     short loc_18001289F
0x18001288b  and     ecx, 0FFFFF63Eh
0x180012891  mov     eax, ebx
0x180012893  and     eax, 9C1h
0x180012898  or      ecx, eax
0x18001289a  or      ecx, 2
0x18001289d  mov     [rdi], ecx
0x18001289f  mov     r8d, edx
0x1800128a2  and     r8d, 4
0x1800128a6  jnz     short loc_1800128BA
0x1800128a8  btr     ecx, 0Ah
0x1800128ac  mov     eax, ebx
0x1800128ae  and     eax, 400h
0x1800128b3  or      ecx, eax
0x1800128b5  or      ecx, 4
0x1800128b8  mov     [rdi], ecx
0x1800128ba  mov     eax, edx
0x1800128bc  lock cmpxchg [rsi], ecx
0x1800128c0  jnz     short loc_180012879
0x1800128c2  test    r8d, r8d
0x1800128c5  jnz     short loc_1800128D7
0x1800128c7  mov     r8d, ebp
0x1800128ca  mov     edx, 3
0x1800128cf  mov     rcx, rsi
0x1800128d2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800128d7  mov     ecx, [rdi]
0x1800128d9  test    cl, 2
0x1800128dc  jnz     short loc_1800128EE
0x1800128de  and     ecx, 0FFFFF63Eh
0x1800128e4  and     ebx, 9C1h
0x1800128ea  or      ecx, ebx
0x1800128ec  mov     [rdi], ecx
0x1800128ee  mov     rax, rdi
0x1800128f1  mov     rcx, [rsp+68h+var_38]
0x1800128f6  xor     rcx, rsp; StackCookie
0x1800128f9  call    __security_check_cookie
0x1800128fe  add     rsp, 48h
0x180012902  pop     rdi
0x180012903  pop     rsi
0x180012904  pop     rbp
0x180012905  pop     rbx
0x180012906  retn
```
