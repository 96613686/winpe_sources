# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ae10`
- end: `0x18000af7d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f4`

## callees

- `0x18000ab78`
- `0x18000ae10`
- `0x18000d258`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036792, 3, &v14);
    }
    else
    {
      v6 = 0;
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
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
        3,
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
0x18000ae10  mov     [rsp+arg_8], rbx
0x18000ae15  mov     [rsp+arg_10], rbp
0x18000ae1a  mov     [rsp+arg_0], rcx
0x18000ae1f  push    rsi
0x18000ae20  push    rdi
0x18000ae21  push    r15
0x18000ae23  sub     rsp, 20h
0x18000ae27  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18000ae2e  mov     rbx, rdx
0x18000ae31  mov     qword ptr [rdx], 0
0x18000ae38  mov     eax, [rsi]
0x18000ae3a  mov     [rdx], eax
0x18000ae3c  and     eax, 6
0x18000ae3f  cmp     al, 6
0x18000ae41  jz      loc_18000AF67
0x18000ae47  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ae4c  mov     ebp, eax
0x18000ae4e  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ae56  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ae5d  test    rax, rax
0x18000ae60  jz      short loc_18000AE7A
0x18000ae62  lea     r8, [rsp+38h+arg_0]
0x18000ae67  mov     edx, 3
0x18000ae6c  mov     ecx, 2AF34F8h
0x18000ae71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae76  mov     edx, eax
0x18000ae78  jmp     short loc_18000AE88
0x18000ae7a  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ae81  test    rax, rax
0x18000ae84  jnz     short loc_18000AE62
0x18000ae86  xor     edx, edx
0x18000ae88  mov     r8d, edx
0x18000ae8b  mov     eax, edx
0x18000ae8d  and     r8d, 0FFFFFF3Fh
0x18000ae94  and     edx, 80h
0x18000ae9a  mov     ecx, r8d
0x18000ae9d  mov     r15d, 40h ; '@'
0x18000aea3  and     ecx, 3
0x18000aea6  and     eax, r15d
0x18000aea9  shl     ecx, 2
0x18000aeac  or      ecx, eax
0x18000aeae  shl     ecx, 2
0x18000aeb1  or      ecx, edx
0x18000aeb3  lea     edi, ds:0[rcx*8]
0x18000aeba  test    r8d, r8d
0x18000aebd  jnz     short loc_18000AEC4
0x18000aebf  mov     eax, r15d
0x18000aec2  jmp     short loc_18000AECE
0x18000aec4  xor     eax, eax
0x18000aec6  cmp     r8d, 2
0x18000aeca  cmovz   eax, r15d
0x18000aece  or      edi, eax
0x18000aed0  mov     eax, [rbx]
0x18000aed2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000aed7  mov     edx, eax
0x18000aed9  mov     [rbx], eax
0x18000aedb  jz      short loc_18000AF07
0x18000aedd  test    dl, 2
0x18000aee0  jnz     short loc_18000AF07
0x18000aee2  xor     eax, edi
0x18000aee4  and     eax, 180h
0x18000aee9  xor     eax, edx
0x18000aeeb  mov     ecx, eax
0x18000aeed  xor     ecx, edi
0x18000aeef  and     ecx, r15d
0x18000aef2  xor     ecx, eax
0x18000aef4  or      ecx, 1
0x18000aef7  mov     eax, ecx
0x18000aef9  xor     eax, edi
0x18000aefb  and     eax, 800h
0x18000af00  xor     eax, ecx
0x18000af02  or      eax, 2
0x18000af05  mov     [rbx], eax
0x18000af07  mov     r8d, edx
0x18000af0a  mov     ecx, eax
0x18000af0c  and     r8d, 4
0x18000af10  jnz     short loc_18000AF21
0x18000af12  xor     ecx, edi
0x18000af14  and     ecx, 400h
0x18000af1a  xor     ecx, eax
0x18000af1c  or      ecx, 4
0x18000af1f  mov     [rbx], ecx
0x18000af21  mov     eax, edx
0x18000af23  lock cmpxchg [rsi], ecx
0x18000af27  jnz     short loc_18000AED2
0x18000af29  test    r8d, r8d
0x18000af2c  jnz     short loc_18000AF3E
0x18000af2e  mov     r8d, ebp
0x18000af31  mov     edx, 3
0x18000af36  mov     rcx, rsi
0x18000af39  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000af3e  test    byte ptr [rbx], 2
0x18000af41  jnz     short loc_18000AF67
0x18000af43  mov     eax, [rbx]
0x18000af45  xor     eax, edi
0x18000af47  and     eax, 180h
0x18000af4c  xor     eax, [rbx]
0x18000af4e  mov     ecx, eax
0x18000af50  xor     ecx, edi
0x18000af52  and     ecx, r15d
0x18000af55  xor     ecx, eax
0x18000af57  or      ecx, 1
0x18000af5a  mov     eax, ecx
0x18000af5c  xor     eax, edi
0x18000af5e  and     eax, 800h
0x18000af63  xor     eax, ecx
0x18000af65  mov     [rbx], eax
0x18000af67  mov     rbp, [rsp+38h+arg_10]
0x18000af6c  mov     rax, rbx
0x18000af6f  mov     rbx, [rsp+38h+arg_8]
0x18000af74  add     rsp, 20h
0x18000af78  pop     r15
0x18000af7a  pop     rdi
0x18000af7b  pop     rsi
0x18000af7c  retn
```
