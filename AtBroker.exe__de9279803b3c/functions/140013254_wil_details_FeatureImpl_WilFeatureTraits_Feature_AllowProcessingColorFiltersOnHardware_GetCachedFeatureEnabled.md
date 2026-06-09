# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCachedFeatureEnabledState(void)

- ea: `0x140013254`
- end: `0x1400133c3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400143ac`

## callees

- `0x140004d18`
- `0x140009b34`
- `0x140013254`
- `0x140017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowProcessingColorFiltersOnHardware>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AllowProcessingColorFiltersOnHardware__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(39905418, 0, &v14);
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    if ( !v4 )
      LODWORD(v14) = 0;
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_AllowProcessingColorFiltersOnHardware__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_AllowProcessingColorFiltersOnHardware__descriptor,
        0,
        v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
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
0x140013254  mov     [rsp+arg_8], rbx
0x140013259  mov     [rsp+arg_10], rbp
0x14001325e  mov     [rsp+arg_0], rcx
0x140013263  push    rsi
0x140013264  push    rdi
0x140013265  push    r15
0x140013267  sub     rsp, 20h
0x14001326b  mov     rsi, cs:Feature_AllowProcessingColorFiltersOnHardware__descriptor
0x140013272  mov     rbx, rdx
0x140013275  mov     qword ptr [rdx], 0
0x14001327c  mov     eax, [rsi]
0x14001327e  mov     [rdx], eax
0x140013280  and     eax, 6
0x140013283  cmp     al, 6
0x140013285  jz      loc_1400133AD
0x14001328b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140013290  mov     ebp, eax
0x140013292  mov     dword ptr [rsp+38h+arg_0], 0
0x14001329a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1400132a1  xor     edx, edx
0x1400132a3  test    rax, rax
0x1400132a6  jnz     short loc_1400132B4
0x1400132a8  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1400132af  test    rax, rax
0x1400132b2  jz      short loc_1400132C5
0x1400132b4  lea     r8, [rsp+38h+arg_0]
0x1400132b9  mov     ecx, 260E88Ah
0x1400132be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400132c3  mov     edx, eax
0x1400132c5  mov     r8d, edx
0x1400132c8  mov     eax, edx
0x1400132ca  and     r8d, 0FFFFFF3Fh
0x1400132d1  and     edx, 80h
0x1400132d7  mov     ecx, r8d
0x1400132da  mov     r15d, 40h ; '@'
0x1400132e0  and     ecx, 3
0x1400132e3  and     eax, r15d
0x1400132e6  shl     ecx, 2
0x1400132e9  or      ecx, eax
0x1400132eb  shl     ecx, 2
0x1400132ee  or      ecx, edx
0x1400132f0  lea     edi, ds:0[rcx*8]
0x1400132f7  test    r8d, r8d
0x1400132fa  jnz     short loc_140013301
0x1400132fc  mov     eax, r15d
0x1400132ff  jmp     short loc_14001330B
0x140013301  xor     eax, eax
0x140013303  cmp     r8d, 2
0x140013307  cmovz   eax, r15d
0x14001330b  or      edi, eax
0x14001330d  test    ebp, ebp
0x14001330f  jnz     short loc_140013315
0x140013311  mov     dword ptr [rsp+38h+arg_0], ebp
0x140013315  mov     eax, [rbx]
0x140013317  cmp     dword ptr [rsp+38h+arg_0], 0
0x14001331c  mov     edx, eax
0x14001331e  mov     [rbx], eax
0x140013320  jz      short loc_14001334C
0x140013322  test    dl, 2
0x140013325  jnz     short loc_14001334C
0x140013327  xor     eax, edi
0x140013329  and     eax, 180h
0x14001332e  xor     eax, edx
0x140013330  mov     ecx, eax
0x140013332  xor     ecx, edi
0x140013334  and     ecx, r15d
0x140013337  xor     ecx, eax
0x140013339  or      ecx, 1
0x14001333c  mov     eax, ecx
0x14001333e  xor     eax, edi
0x140013340  and     eax, 800h
0x140013345  xor     eax, ecx
0x140013347  or      eax, 2
0x14001334a  mov     [rbx], eax
0x14001334c  mov     r8d, edx
0x14001334f  and     r8d, 4
0x140013353  jnz     short loc_140013368
0x140013355  mov     ecx, edi
0x140013357  xor     ecx, eax
0x140013359  and     ecx, 400h
0x14001335f  xor     ecx, eax
0x140013361  or      ecx, 4
0x140013364  mov     [rbx], ecx
0x140013366  jmp     short loc_14001336A
0x140013368  mov     ecx, eax
0x14001336a  mov     eax, edx
0x14001336c  lock cmpxchg [rsi], ecx
0x140013370  jnz     short loc_140013317
0x140013372  test    r8d, r8d
0x140013375  jnz     short loc_140013384
0x140013377  mov     r8d, ebp
0x14001337a  xor     edx, edx
0x14001337c  mov     rcx, rsi
0x14001337f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140013384  test    byte ptr [rbx], 2
0x140013387  jnz     short loc_1400133AD
0x140013389  mov     eax, [rbx]
0x14001338b  xor     eax, edi
0x14001338d  and     eax, 180h
0x140013392  xor     eax, [rbx]
0x140013394  mov     ecx, eax
0x140013396  xor     ecx, edi
0x140013398  and     ecx, r15d
0x14001339b  xor     ecx, eax
0x14001339d  or      ecx, 1
0x1400133a0  mov     eax, ecx
0x1400133a2  xor     eax, edi
0x1400133a4  and     eax, 800h
0x1400133a9  xor     eax, ecx
0x1400133ab  mov     [rbx], eax
0x1400133ad  mov     rbp, [rsp+38h+arg_10]
0x1400133b2  mov     rax, rbx
0x1400133b5  mov     rbx, [rsp+38h+arg_8]
0x1400133ba  add     rsp, 20h
0x1400133be  pop     r15
0x1400133c0  pop     rdi
0x1400133c1  pop     rsi
0x1400133c2  retn
```
