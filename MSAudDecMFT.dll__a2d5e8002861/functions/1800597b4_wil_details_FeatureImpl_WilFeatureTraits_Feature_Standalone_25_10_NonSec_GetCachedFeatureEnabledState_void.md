# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800597b4`
- end: `0x180059910`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005b1d4`

## callees

- `0x180048c10`
- `0x18004c07c`
- `0x1800597b4`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  unsigned int v6; // edx
  int *v7; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v9; // r8d
  int v10; // edi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  bool v14; // zf
  signed __int32 v15; // edx
  signed __int32 v16; // ecx
  wil::details *v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
                            v6,
                            (enum FEATURE_CHANGE_TIME)&v18,
                            v7);
    v9 = FeatureEnabledState & 0xFFFFFF3F;
    v10 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v11 = 0;
      if ( v9 == 2 )
        v11 = 64;
    }
    else
    {
      v11 = 64;
    }
    v12 = v11 | v10;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v18 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v13
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v13
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v13 ^ v12) & 0x180 ^ (v12 ^ v13 ^ (v13 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v13;
      }
      if ( (v15 & 4) != 0 )
      {
        v16 = v13;
      }
      else
      {
        v16 = v13 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v12) & 0x400 | 4;
        *(_DWORD *)a2 = v16;
      }
      v13 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v12
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v12
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v12
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v12
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v12
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v12
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x1800597b4  mov     [rsp+arg_8], rbx
0x1800597b9  mov     [rsp+arg_10], rbp
0x1800597be  mov     [rsp+arg_0], rcx
0x1800597c3  push    rsi
0x1800597c4  push    rdi
0x1800597c5  push    r15
0x1800597c7  sub     rsp, 20h
0x1800597cb  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800597d2  mov     rbx, rdx
0x1800597d5  mov     qword ptr [rdx], 0
0x1800597dc  mov     eax, [rsi]
0x1800597de  mov     [rdx], eax
0x1800597e0  and     eax, 6
0x1800597e3  cmp     al, 6
0x1800597e5  jz      loc_1800598F9
0x1800597eb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800597f0  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x1800597f5  mov     dword ptr [rsp+38h+arg_0], 0
0x1800597fd  mov     ecx, 2AF34F8h; this
0x180059802  mov     ebp, eax
0x180059804  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180059809  mov     r8d, eax
0x18005980c  mov     ecx, eax
0x18005980e  and     r8d, 0FFFFFF3Fh
0x180059815  and     eax, 80h
0x18005981a  mov     edx, r8d
0x18005981d  mov     r15d, 40h ; '@'
0x180059823  and     edx, 3
0x180059826  and     ecx, r15d
0x180059829  shl     edx, 2
0x18005982c  or      edx, ecx
0x18005982e  shl     edx, 2
0x180059831  or      edx, eax
0x180059833  lea     edi, ds:0[rdx*8]
0x18005983a  test    r8d, r8d
0x18005983d  jnz     short loc_180059844
0x18005983f  mov     eax, r15d
0x180059842  jmp     short loc_18005984E
0x180059844  xor     eax, eax
0x180059846  cmp     r8d, 2
0x18005984a  cmovz   eax, r15d
0x18005984e  or      edi, eax
0x180059850  mov     eax, [rbx]
0x180059852  cmp     dword ptr [rsp+38h+arg_0], 0
0x180059857  mov     edx, eax
0x180059859  mov     [rbx], eax
0x18005985b  jz      short loc_18005988B
0x18005985d  test    dl, 2
0x180059860  jnz     short loc_18005988B
0x180059862  mov     eax, edi
0x180059864  xor     eax, edx
0x180059866  and     eax, 180h
0x18005986b  xor     eax, edx
0x18005986d  mov     ecx, eax
0x18005986f  xor     ecx, edi
0x180059871  and     ecx, r15d
0x180059874  xor     ecx, eax
0x180059876  or      ecx, 1
0x180059879  mov     eax, ecx
0x18005987b  xor     eax, edi
0x18005987d  and     eax, 800h
0x180059882  xor     eax, ecx
0x180059884  or      eax, 2
0x180059887  mov     [rbx], eax
0x180059889  jmp     short loc_18005988D
0x18005988b  mov     eax, edx
0x18005988d  mov     r8d, edx
0x180059890  and     r8d, 4
0x180059894  jnz     short loc_1800598A9
0x180059896  mov     ecx, edi
0x180059898  xor     ecx, eax
0x18005989a  and     ecx, 400h
0x1800598a0  xor     ecx, eax
0x1800598a2  or      ecx, 4
0x1800598a5  mov     [rbx], ecx
0x1800598a7  jmp     short loc_1800598AB
0x1800598a9  mov     ecx, eax
0x1800598ab  mov     eax, edx
0x1800598ad  lock cmpxchg [rsi], ecx
0x1800598b1  jnz     short loc_180059852
0x1800598b3  test    r8d, r8d
0x1800598b6  jnz     short loc_1800598D0
0x1800598b8  mov     r9d, ebp
0x1800598bb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800598c2  mov     r8d, 3
0x1800598c8  mov     rdx, rsi
0x1800598cb  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800598d0  test    byte ptr [rbx], 2
0x1800598d3  jnz     short loc_1800598F9
0x1800598d5  mov     eax, [rbx]
0x1800598d7  xor     eax, edi
0x1800598d9  and     eax, 180h
0x1800598de  xor     eax, [rbx]
0x1800598e0  mov     ecx, eax
0x1800598e2  xor     ecx, edi
0x1800598e4  and     ecx, r15d
0x1800598e7  xor     ecx, eax
0x1800598e9  or      ecx, 1
0x1800598ec  mov     eax, ecx
0x1800598ee  xor     eax, edi
0x1800598f0  and     eax, 800h
0x1800598f5  xor     eax, ecx
0x1800598f7  mov     [rbx], eax
0x1800598f9  mov     rbp, [rsp+38h+arg_10]
0x1800598fe  mov     rax, rbx
0x180059901  mov     rbx, [rsp+38h+arg_8]
0x180059906  add     rsp, 20h
0x18005990a  pop     r15
0x18005990c  pop     rdi
0x18005990d  pop     rsi
0x18005990e  retn
```
