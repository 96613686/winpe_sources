# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::GetCachedFeatureEnabledState(void)

- ea: `0x180018924`
- end: `0x180018a7b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossContainerAuth@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `343`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005500`

## callees

- `0x18000c954`
- `0x18000f974`
- `0x180018924`
- `0x180018b64`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossContainerAuth>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_CrossContainerAuth__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CrossContainerAuth__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v18) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x1512962,
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
    if ( !v5 )
      LODWORD(v18) = 0;
    v13 = *(_DWORD *)a2;
    do
    {
      v14 = (_DWORD)v18 == 0;
      v15 = v13;
      *(_DWORD *)a2 = v13;
      if ( !v14 && (v13 & 2) == 0 )
      {
        v13 = (v13
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v13)
             & 0x180
             ^ (v12
              ^ v13
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v13)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v12
             ^ ((unsigned __int16)(v13 ^ (v12 ^ v13) & 0x180 ^ (v12 ^ v13 ^ (v12 ^ v13) & 0x180) & 0x40) | 1))
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
      v13 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CrossContainerAuth__descriptor, v16, v15);
    }
    while ( v15 != v13 );
    if ( (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        (__int64 *)Feature_CrossContainerAuth__descriptor,
        v15 & 4,
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
0x180018924  mov     [rsp+arg_8], rbx
0x180018929  mov     [rsp+arg_10], rbp
0x18001892e  mov     [rsp+arg_0], rcx
0x180018933  push    rsi
0x180018934  push    rdi
0x180018935  push    r15
0x180018937  sub     rsp, 20h
0x18001893b  mov     rsi, cs:Feature_CrossContainerAuth__descriptor
0x180018942  mov     rbx, rdx
0x180018945  mov     qword ptr [rdx], 0
0x18001894c  mov     eax, [rsi]
0x18001894e  mov     [rdx], eax
0x180018950  and     eax, 6
0x180018953  cmp     al, 6
0x180018955  jz      loc_180018A65
0x18001895b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180018960  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180018965  mov     dword ptr [rsp+38h+arg_0], 0
0x18001896d  mov     ecx, 1512962h; this
0x180018972  mov     ebp, eax
0x180018974  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180018979  mov     r8d, eax
0x18001897c  mov     ecx, eax
0x18001897e  and     r8d, 0FFFFFF3Fh
0x180018985  and     eax, 80h
0x18001898a  mov     edx, r8d
0x18001898d  mov     r15d, 40h ; '@'
0x180018993  and     edx, 3
0x180018996  and     ecx, r15d
0x180018999  shl     edx, 2
0x18001899c  or      edx, ecx
0x18001899e  shl     edx, 2
0x1800189a1  or      edx, eax
0x1800189a3  lea     edi, ds:0[rdx*8]
0x1800189aa  test    r8d, r8d
0x1800189ad  jnz     short loc_1800189B4
0x1800189af  mov     eax, r15d
0x1800189b2  jmp     short loc_1800189BE
0x1800189b4  xor     eax, eax
0x1800189b6  cmp     r8d, 2
0x1800189ba  cmovz   eax, r15d
0x1800189be  or      edi, eax
0x1800189c0  test    ebp, ebp
0x1800189c2  jnz     short loc_1800189C8
0x1800189c4  mov     dword ptr [rsp+38h+arg_0], ebp
0x1800189c8  mov     eax, [rbx]
0x1800189ca  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800189cf  mov     edx, eax
0x1800189d1  mov     [rbx], eax
0x1800189d3  jz      short loc_1800189FF
0x1800189d5  test    dl, 2
0x1800189d8  jnz     short loc_1800189FF
0x1800189da  xor     eax, edi
0x1800189dc  and     eax, 180h
0x1800189e1  xor     eax, edx
0x1800189e3  mov     ecx, eax
0x1800189e5  xor     ecx, edi
0x1800189e7  and     ecx, r15d
0x1800189ea  xor     ecx, eax
0x1800189ec  or      ecx, 1
0x1800189ef  mov     eax, ecx
0x1800189f1  xor     eax, edi
0x1800189f3  and     eax, 800h
0x1800189f8  xor     eax, ecx
0x1800189fa  or      eax, 2
0x1800189fd  mov     [rbx], eax
0x1800189ff  mov     r8d, edx
0x180018a02  and     r8d, 4
0x180018a06  jnz     short loc_180018A1B
0x180018a08  mov     ecx, edi
0x180018a0a  xor     ecx, eax
0x180018a0c  and     ecx, 400h
0x180018a12  xor     ecx, eax
0x180018a14  or      ecx, 4
0x180018a17  mov     [rbx], ecx
0x180018a19  jmp     short loc_180018A1D
0x180018a1b  mov     ecx, eax
0x180018a1d  mov     eax, edx
0x180018a1f  lock cmpxchg [rsi], ecx
0x180018a23  jnz     short loc_1800189CA
0x180018a25  test    r8d, r8d
0x180018a28  jnz     short loc_180018A3C
0x180018a2a  mov     r9d, ebp
0x180018a2d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018a34  mov     rdx, rsi
0x180018a37  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180018a3c  test    byte ptr [rbx], 2
0x180018a3f  jnz     short loc_180018A65
0x180018a41  mov     eax, [rbx]
0x180018a43  xor     eax, edi
0x180018a45  and     eax, 180h
0x180018a4a  xor     eax, [rbx]
0x180018a4c  mov     ecx, eax
0x180018a4e  xor     ecx, edi
0x180018a50  and     ecx, r15d
0x180018a53  xor     ecx, eax
0x180018a55  or      ecx, 1
0x180018a58  mov     eax, ecx
0x180018a5a  xor     eax, edi
0x180018a5c  and     eax, 800h
0x180018a61  xor     eax, ecx
0x180018a63  mov     [rbx], eax
0x180018a65  mov     rbp, [rsp+38h+arg_10]
0x180018a6a  mov     rax, rbx
0x180018a6d  mov     rbx, [rsp+38h+arg_8]
0x180018a72  add     rsp, 20h
0x180018a76  pop     r15
0x180018a78  pop     rdi
0x180018a79  pop     rsi
0x180018a7a  retn
```
