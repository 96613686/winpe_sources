# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ddd4`
- end: `0x18000df41`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e8f0`

## callees

- `0x18000d6e0`
- `0x18000ddd4`
- `0x18000ff38`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
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
0x18000ddd4  mov     [rsp+arg_8], rbx
0x18000ddd9  mov     [rsp+arg_10], rbp
0x18000ddde  mov     [rsp+arg_0], rcx
0x18000dde3  push    rsi
0x18000dde4  push    rdi
0x18000dde5  push    r15
0x18000dde7  sub     rsp, 20h
0x18000ddeb  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000ddf2  mov     rbx, rdx
0x18000ddf5  mov     qword ptr [rdx], 0
0x18000ddfc  mov     eax, [rsi]
0x18000ddfe  mov     [rdx], eax
0x18000de00  and     eax, 6
0x18000de03  cmp     al, 6
0x18000de05  jz      loc_18000DF2B
0x18000de0b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000de10  mov     ebp, eax
0x18000de12  mov     dword ptr [rsp+38h+arg_0], 0
0x18000de1a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000de21  test    rax, rax
0x18000de24  jz      short loc_18000DE3E
0x18000de26  lea     r8, [rsp+38h+arg_0]
0x18000de2b  mov     edx, 3
0x18000de30  mov     ecx, 37E287Eh
0x18000de35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de3a  mov     edx, eax
0x18000de3c  jmp     short loc_18000DE4C
0x18000de3e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000de45  test    rax, rax
0x18000de48  jnz     short loc_18000DE26
0x18000de4a  xor     edx, edx
0x18000de4c  mov     r8d, edx
0x18000de4f  mov     eax, edx
0x18000de51  and     r8d, 0FFFFFF3Fh
0x18000de58  and     edx, 80h
0x18000de5e  mov     ecx, r8d
0x18000de61  mov     r15d, 40h ; '@'
0x18000de67  and     ecx, 3
0x18000de6a  and     eax, r15d
0x18000de6d  shl     ecx, 2
0x18000de70  or      ecx, eax
0x18000de72  shl     ecx, 2
0x18000de75  or      ecx, edx
0x18000de77  lea     edi, ds:0[rcx*8]
0x18000de7e  test    r8d, r8d
0x18000de81  jnz     short loc_18000DE88
0x18000de83  mov     eax, r15d
0x18000de86  jmp     short loc_18000DE92
0x18000de88  xor     eax, eax
0x18000de8a  cmp     r8d, 2
0x18000de8e  cmovz   eax, r15d
0x18000de92  or      edi, eax
0x18000de94  mov     eax, [rbx]
0x18000de96  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000de9b  mov     edx, eax
0x18000de9d  mov     [rbx], eax
0x18000de9f  jz      short loc_18000DECB
0x18000dea1  test    dl, 2
0x18000dea4  jnz     short loc_18000DECB
0x18000dea6  xor     eax, edi
0x18000dea8  and     eax, 180h
0x18000dead  xor     eax, edx
0x18000deaf  mov     ecx, eax
0x18000deb1  xor     ecx, edi
0x18000deb3  and     ecx, r15d
0x18000deb6  xor     ecx, eax
0x18000deb8  or      ecx, 1
0x18000debb  mov     eax, ecx
0x18000debd  xor     eax, edi
0x18000debf  and     eax, 800h
0x18000dec4  xor     eax, ecx
0x18000dec6  or      eax, 2
0x18000dec9  mov     [rbx], eax
0x18000decb  mov     r8d, edx
0x18000dece  mov     ecx, eax
0x18000ded0  and     r8d, 4
0x18000ded4  jnz     short loc_18000DEE5
0x18000ded6  xor     ecx, edi
0x18000ded8  and     ecx, 400h
0x18000dede  xor     ecx, eax
0x18000dee0  or      ecx, 4
0x18000dee3  mov     [rbx], ecx
0x18000dee5  mov     eax, edx
0x18000dee7  lock cmpxchg [rsi], ecx
0x18000deeb  jnz     short loc_18000DE96
0x18000deed  test    r8d, r8d
0x18000def0  jnz     short loc_18000DF02
0x18000def2  mov     r8d, ebp
0x18000def5  mov     edx, 3
0x18000defa  mov     rcx, rsi
0x18000defd  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000df02  test    byte ptr [rbx], 2
0x18000df05  jnz     short loc_18000DF2B
0x18000df07  mov     eax, [rbx]
0x18000df09  xor     eax, edi
0x18000df0b  and     eax, 180h
0x18000df10  xor     eax, [rbx]
0x18000df12  mov     ecx, eax
0x18000df14  xor     ecx, edi
0x18000df16  and     ecx, r15d
0x18000df19  xor     ecx, eax
0x18000df1b  or      ecx, 1
0x18000df1e  mov     eax, ecx
0x18000df20  xor     eax, edi
0x18000df22  and     eax, 800h
0x18000df27  xor     eax, ecx
0x18000df29  mov     [rbx], eax
0x18000df2b  mov     rbp, [rsp+38h+arg_10]
0x18000df30  mov     rax, rbx
0x18000df33  mov     rbx, [rsp+38h+arg_8]
0x18000df38  add     rsp, 20h
0x18000df3c  pop     r15
0x18000df3e  pop     rdi
0x18000df3f  pop     rsi
0x18000df40  retn
```
