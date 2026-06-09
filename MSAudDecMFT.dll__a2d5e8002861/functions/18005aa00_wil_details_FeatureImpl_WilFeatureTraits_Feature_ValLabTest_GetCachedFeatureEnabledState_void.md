# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18005aa00`
- end: `0x18005ab5c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
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
- `0x18005aa00`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667CA2,
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x18005aa00  mov     [rsp+arg_8], rbx
0x18005aa05  mov     [rsp+arg_10], rbp
0x18005aa0a  mov     [rsp+arg_0], rcx
0x18005aa0f  push    rsi
0x18005aa10  push    rdi
0x18005aa11  push    r15
0x18005aa13  sub     rsp, 20h
0x18005aa17  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18005aa1e  mov     rbx, rdx
0x18005aa21  mov     qword ptr [rdx], 0
0x18005aa28  mov     eax, [rsi]
0x18005aa2a  mov     [rdx], eax
0x18005aa2c  and     eax, 6
0x18005aa2f  cmp     al, 6
0x18005aa31  jz      loc_18005AB45
0x18005aa37  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18005aa3c  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18005aa41  mov     dword ptr [rsp+38h+arg_0], 0
0x18005aa49  mov     ecx, 3667CA2h; this
0x18005aa4e  mov     ebp, eax
0x18005aa50  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18005aa55  mov     r8d, eax
0x18005aa58  mov     ecx, eax
0x18005aa5a  and     r8d, 0FFFFFF3Fh
0x18005aa61  and     eax, 80h
0x18005aa66  mov     edx, r8d
0x18005aa69  mov     r15d, 40h ; '@'
0x18005aa6f  and     edx, 3
0x18005aa72  and     ecx, r15d
0x18005aa75  shl     edx, 2
0x18005aa78  or      edx, ecx
0x18005aa7a  shl     edx, 2
0x18005aa7d  or      edx, eax
0x18005aa7f  lea     edi, ds:0[rdx*8]
0x18005aa86  test    r8d, r8d
0x18005aa89  jnz     short loc_18005AA90
0x18005aa8b  mov     eax, r15d
0x18005aa8e  jmp     short loc_18005AA9A
0x18005aa90  xor     eax, eax
0x18005aa92  cmp     r8d, 2
0x18005aa96  cmovz   eax, r15d
0x18005aa9a  or      edi, eax
0x18005aa9c  mov     eax, [rbx]
0x18005aa9e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18005aaa3  mov     edx, eax
0x18005aaa5  mov     [rbx], eax
0x18005aaa7  jz      short loc_18005AAD7
0x18005aaa9  test    dl, 2
0x18005aaac  jnz     short loc_18005AAD7
0x18005aaae  mov     eax, edi
0x18005aab0  xor     eax, edx
0x18005aab2  and     eax, 180h
0x18005aab7  xor     eax, edx
0x18005aab9  mov     ecx, eax
0x18005aabb  xor     ecx, edi
0x18005aabd  and     ecx, r15d
0x18005aac0  xor     ecx, eax
0x18005aac2  or      ecx, 1
0x18005aac5  mov     eax, ecx
0x18005aac7  xor     eax, edi
0x18005aac9  and     eax, 800h
0x18005aace  xor     eax, ecx
0x18005aad0  or      eax, 2
0x18005aad3  mov     [rbx], eax
0x18005aad5  jmp     short loc_18005AAD9
0x18005aad7  mov     eax, edx
0x18005aad9  mov     r8d, edx
0x18005aadc  and     r8d, 4
0x18005aae0  jnz     short loc_18005AAF5
0x18005aae2  mov     ecx, edi
0x18005aae4  xor     ecx, eax
0x18005aae6  and     ecx, 400h
0x18005aaec  xor     ecx, eax
0x18005aaee  or      ecx, 4
0x18005aaf1  mov     [rbx], ecx
0x18005aaf3  jmp     short loc_18005AAF7
0x18005aaf5  mov     ecx, eax
0x18005aaf7  mov     eax, edx
0x18005aaf9  lock cmpxchg [rsi], ecx
0x18005aafd  jnz     short loc_18005AA9E
0x18005aaff  test    r8d, r8d
0x18005ab02  jnz     short loc_18005AB1C
0x18005ab04  mov     r9d, ebp
0x18005ab07  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005ab0e  mov     r8d, 3
0x18005ab14  mov     rdx, rsi
0x18005ab17  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18005ab1c  test    byte ptr [rbx], 2
0x18005ab1f  jnz     short loc_18005AB45
0x18005ab21  mov     eax, [rbx]
0x18005ab23  xor     eax, edi
0x18005ab25  and     eax, 180h
0x18005ab2a  xor     eax, [rbx]
0x18005ab2c  mov     ecx, eax
0x18005ab2e  xor     ecx, edi
0x18005ab30  and     ecx, r15d
0x18005ab33  xor     ecx, eax
0x18005ab35  or      ecx, 1
0x18005ab38  mov     eax, ecx
0x18005ab3a  xor     eax, edi
0x18005ab3c  and     eax, 800h
0x18005ab41  xor     eax, ecx
0x18005ab43  mov     [rbx], eax
0x18005ab45  mov     rbp, [rsp+38h+arg_10]
0x18005ab4a  mov     rax, rbx
0x18005ab4d  mov     rbx, [rsp+38h+arg_8]
0x18005ab52  add     rsp, 20h
0x18005ab56  pop     r15
0x18005ab58  pop     rdi
0x18005ab59  pop     rsi
0x18005ab5a  retn
```
