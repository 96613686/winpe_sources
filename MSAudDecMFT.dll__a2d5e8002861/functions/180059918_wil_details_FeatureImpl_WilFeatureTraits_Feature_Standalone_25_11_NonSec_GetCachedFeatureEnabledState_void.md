# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180059918`
- end: `0x180059a74`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005af5c`

## callees

- `0x180048c10`
- `0x18004c07c`
- `0x180059918`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34FD,
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
              (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
              v16,
              v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x180059918  mov     [rsp+arg_8], rbx
0x18005991d  mov     [rsp+arg_10], rbp
0x180059922  mov     [rsp+arg_0], rcx
0x180059927  push    rsi
0x180059928  push    rdi
0x180059929  push    r15
0x18005992b  sub     rsp, 20h
0x18005992f  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180059936  mov     rbx, rdx
0x180059939  mov     qword ptr [rdx], 0
0x180059940  mov     eax, [rsi]
0x180059942  mov     [rdx], eax
0x180059944  and     eax, 6
0x180059947  cmp     al, 6
0x180059949  jz      loc_180059A5D
0x18005994f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180059954  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180059959  mov     dword ptr [rsp+38h+arg_0], 0
0x180059961  mov     ecx, 2AF34FDh; this
0x180059966  mov     ebp, eax
0x180059968  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18005996d  mov     r8d, eax
0x180059970  mov     ecx, eax
0x180059972  and     r8d, 0FFFFFF3Fh
0x180059979  and     eax, 80h
0x18005997e  mov     edx, r8d
0x180059981  mov     r15d, 40h ; '@'
0x180059987  and     edx, 3
0x18005998a  and     ecx, r15d
0x18005998d  shl     edx, 2
0x180059990  or      edx, ecx
0x180059992  shl     edx, 2
0x180059995  or      edx, eax
0x180059997  lea     edi, ds:0[rdx*8]
0x18005999e  test    r8d, r8d
0x1800599a1  jnz     short loc_1800599A8
0x1800599a3  mov     eax, r15d
0x1800599a6  jmp     short loc_1800599B2
0x1800599a8  xor     eax, eax
0x1800599aa  cmp     r8d, 2
0x1800599ae  cmovz   eax, r15d
0x1800599b2  or      edi, eax
0x1800599b4  mov     eax, [rbx]
0x1800599b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800599bb  mov     edx, eax
0x1800599bd  mov     [rbx], eax
0x1800599bf  jz      short loc_1800599EF
0x1800599c1  test    dl, 2
0x1800599c4  jnz     short loc_1800599EF
0x1800599c6  mov     eax, edi
0x1800599c8  xor     eax, edx
0x1800599ca  and     eax, 180h
0x1800599cf  xor     eax, edx
0x1800599d1  mov     ecx, eax
0x1800599d3  xor     ecx, edi
0x1800599d5  and     ecx, r15d
0x1800599d8  xor     ecx, eax
0x1800599da  or      ecx, 1
0x1800599dd  mov     eax, ecx
0x1800599df  xor     eax, edi
0x1800599e1  and     eax, 800h
0x1800599e6  xor     eax, ecx
0x1800599e8  or      eax, 2
0x1800599eb  mov     [rbx], eax
0x1800599ed  jmp     short loc_1800599F1
0x1800599ef  mov     eax, edx
0x1800599f1  mov     r8d, edx
0x1800599f4  and     r8d, 4
0x1800599f8  jnz     short loc_180059A0D
0x1800599fa  mov     ecx, edi
0x1800599fc  xor     ecx, eax
0x1800599fe  and     ecx, 400h
0x180059a04  xor     ecx, eax
0x180059a06  or      ecx, 4
0x180059a09  mov     [rbx], ecx
0x180059a0b  jmp     short loc_180059A0F
0x180059a0d  mov     ecx, eax
0x180059a0f  mov     eax, edx
0x180059a11  lock cmpxchg [rsi], ecx
0x180059a15  jnz     short loc_1800599B6
0x180059a17  test    r8d, r8d
0x180059a1a  jnz     short loc_180059A34
0x180059a1c  mov     r9d, ebp
0x180059a1f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180059a26  mov     r8d, 3
0x180059a2c  mov     rdx, rsi
0x180059a2f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180059a34  test    byte ptr [rbx], 2
0x180059a37  jnz     short loc_180059A5D
0x180059a39  mov     eax, [rbx]
0x180059a3b  xor     eax, edi
0x180059a3d  and     eax, 180h
0x180059a42  xor     eax, [rbx]
0x180059a44  mov     ecx, eax
0x180059a46  xor     ecx, edi
0x180059a48  and     ecx, r15d
0x180059a4b  xor     ecx, eax
0x180059a4d  or      ecx, 1
0x180059a50  mov     eax, ecx
0x180059a52  xor     eax, edi
0x180059a54  and     eax, 800h
0x180059a59  xor     eax, ecx
0x180059a5b  mov     [rbx], eax
0x180059a5d  mov     rbp, [rsp+38h+arg_10]
0x180059a62  mov     rax, rbx
0x180059a65  mov     rbx, [rsp+38h+arg_8]
0x180059a6a  add     rsp, 20h
0x180059a6e  pop     r15
0x180059a70  pop     rdi
0x180059a71  pop     rsi
0x180059a72  retn
```
