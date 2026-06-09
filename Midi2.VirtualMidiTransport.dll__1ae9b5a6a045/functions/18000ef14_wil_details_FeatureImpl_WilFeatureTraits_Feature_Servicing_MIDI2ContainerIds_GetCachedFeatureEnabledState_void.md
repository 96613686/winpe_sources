# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ef14`
- end: `0x18000f0e1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011a7c`

## callees

- `0x18000ee50`
- `0x18000ef14`
- `0x180011648`
- `0x180011cf0`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2ContainerIds>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // si
  char IsEnabled; // al
  BOOL v11; // esi
  signed __int32 v12; // eax
  int v13; // esi
  bool v14; // zf
  signed __int32 v15; // edx
  int v16; // r8d
  int v17; // r9d
  signed __int32 v18; // ecx
  wil::details *v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2ContainerIds__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(61091483, 3, &v20);
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
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
LABEL_13:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
    if ( v9 && !IsEnabled )
      v8 &= ~0x400u;
    goto LABEL_17;
  }
  v9 = 0;
  if ( (v8 & 0x40) != 0 )
    goto LABEL_13;
  IsEnabled = 0;
LABEL_17:
  v11 = (v8 & 0x40) != 0 && IsEnabled;
  v12 = *(_DWORD *)a2;
  v13 = v8 | v11;
  do
  {
    v14 = (_DWORD)v20 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( v14 || (v12 & 2) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v16 = v12
          ^ (v12
           ^ v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ (v12
            ^ v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v12 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2ContainerIds__descriptor,
      3,
      v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= (v13
                    ^ *(_DWORD *)a2)
                   & 0x180
                   ^ (v13
                    ^ *(_DWORD *)a2
                    ^ (v13
                     ^ *(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v13
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v13
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v13
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v13
                      ^ *(_WORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v13
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v13
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v13
                       ^ *(_BYTE *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x18000ef14  mov     [rsp+arg_0], rcx
0x18000ef19  push    rbx
0x18000ef1a  push    rbp
0x18000ef1b  push    rsi
0x18000ef1c  push    rdi
0x18000ef1d  push    r12
0x18000ef1f  push    r14
0x18000ef21  sub     rsp, 28h
0x18000ef25  mov     r14, cs:Feature_Servicing_MIDI2ContainerIds__descriptor
0x18000ef2c  mov     rdi, rdx
0x18000ef2f  mov     qword ptr [rdx], 0
0x18000ef36  mov     eax, [r14]
0x18000ef39  mov     [rdx], eax
0x18000ef3b  and     eax, 6
0x18000ef3e  cmp     al, 6
0x18000ef40  jz      loc_18000F0D1
0x18000ef46  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ef4b  mov     ebp, eax
0x18000ef4d  mov     dword ptr [rsp+58h+arg_0], 0
0x18000ef55  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ef5c  test    rax, rax
0x18000ef5f  jz      short loc_18000EF79
0x18000ef61  lea     r8, [rsp+58h+arg_0]
0x18000ef66  mov     edx, 3
0x18000ef6b  mov     ecx, 3A42E9Bh
0x18000ef70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef75  mov     edx, eax
0x18000ef77  jmp     short loc_18000EF87
0x18000ef79  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ef80  test    rax, rax
0x18000ef83  jnz     short loc_18000EF61
0x18000ef85  xor     edx, edx
0x18000ef87  mov     r8d, edx
0x18000ef8a  mov     eax, edx
0x18000ef8c  and     r8d, 0FFFFFF3Fh
0x18000ef93  and     edx, 80h
0x18000ef99  mov     ecx, r8d
0x18000ef9c  mov     r12d, 40h ; '@'
0x18000efa2  and     ecx, 3
0x18000efa5  and     eax, r12d
0x18000efa8  shl     ecx, 2
0x18000efab  or      ecx, eax
0x18000efad  shl     ecx, 2
0x18000efb0  or      ecx, edx
0x18000efb2  lea     ebx, ds:0[rcx*8]
0x18000efb9  test    r8d, r8d
0x18000efbc  jnz     short loc_18000EFC3
0x18000efbe  mov     eax, r12d
0x18000efc1  jmp     short loc_18000EFCD
0x18000efc3  xor     eax, eax
0x18000efc5  cmp     r8d, 2
0x18000efc9  cmovz   eax, r12d
0x18000efcd  or      ebx, eax
0x18000efcf  mov     ecx, 0C00h
0x18000efd4  mov     eax, ebx
0x18000efd6  and     eax, ecx
0x18000efd8  cmp     eax, ecx
0x18000efda  jnz     short loc_18000EFE1
0x18000efdc  mov     sil, 1
0x18000efdf  jmp     short loc_18000EFE9
0x18000efe1  xor     sil, sil
0x18000efe4  test    r12b, bl
0x18000efe7  jz      short loc_18000F004
0x18000efe9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18000eff0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18000eff5  test    sil, sil
0x18000eff8  jz      short loc_18000F006
0x18000effa  test    al, al
0x18000effc  jnz     short loc_18000F006
0x18000effe  btr     ebx, 0Ah
0x18000f002  jmp     short loc_18000F006
0x18000f004  xor     al, al
0x18000f006  test    r12b, bl
0x18000f009  jz      short loc_18000F016
0x18000f00b  test    al, al
0x18000f00d  jz      short loc_18000F016
0x18000f00f  mov     esi, 1
0x18000f014  jmp     short loc_18000F018
0x18000f016  xor     esi, esi
0x18000f018  mov     eax, [rdi]
0x18000f01a  or      esi, ebx
0x18000f01c  mov     ebx, 180h
0x18000f021  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000f026  mov     edx, eax
0x18000f028  mov     [rdi], eax
0x18000f02a  jz      short loc_18000F064
0x18000f02c  test    dl, 2
0x18000f02f  jnz     short loc_18000F064
0x18000f031  mov     eax, esi
0x18000f033  xor     eax, edx
0x18000f035  and     eax, ebx
0x18000f037  xor     eax, edx
0x18000f039  mov     ecx, eax
0x18000f03b  xor     ecx, esi
0x18000f03d  and     ecx, r12d
0x18000f040  xor     ecx, eax
0x18000f042  mov     eax, ecx
0x18000f044  xor     eax, esi
0x18000f046  and     eax, 1
0x18000f049  xor     eax, ecx
0x18000f04b  mov     r8d, eax
0x18000f04e  xor     r8d, esi
0x18000f051  and     r8d, 800h
0x18000f058  xor     r8d, eax
0x18000f05b  or      r8d, 2
0x18000f05f  mov     [rdi], r8d
0x18000f062  jmp     short loc_18000F067
0x18000f064  mov     r8d, edx
0x18000f067  mov     r9d, edx
0x18000f06a  and     r9d, 4
0x18000f06e  jnz     short loc_18000F085
0x18000f070  mov     ecx, esi
0x18000f072  xor     ecx, r8d
0x18000f075  and     ecx, 400h
0x18000f07b  xor     ecx, r8d
0x18000f07e  or      ecx, 4
0x18000f081  mov     [rdi], ecx
0x18000f083  jmp     short loc_18000F088
0x18000f085  mov     ecx, r8d
0x18000f088  mov     eax, edx
0x18000f08a  lock cmpxchg [r14], ecx
0x18000f08f  jnz     short loc_18000F021
0x18000f091  test    r9d, r9d
0x18000f094  jnz     short loc_18000F0A5
0x18000f096  mov     r8d, ebp
0x18000f099  lea     edx, [r9+3]
0x18000f09d  mov     rcx, r14
0x18000f0a0  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000f0a5  test    byte ptr [rdi], 2
0x18000f0a8  jnz     short loc_18000F0D1
0x18000f0aa  mov     eax, [rdi]
0x18000f0ac  xor     eax, esi
0x18000f0ae  and     eax, ebx
0x18000f0b0  xor     eax, [rdi]
0x18000f0b2  mov     ecx, eax
0x18000f0b4  xor     ecx, esi
0x18000f0b6  and     ecx, r12d
0x18000f0b9  xor     ecx, eax
0x18000f0bb  mov     edx, ecx
0x18000f0bd  xor     edx, esi
0x18000f0bf  and     edx, 1
0x18000f0c2  xor     edx, ecx
0x18000f0c4  mov     eax, edx
0x18000f0c6  xor     eax, esi
0x18000f0c8  and     eax, 800h
0x18000f0cd  xor     eax, edx
0x18000f0cf  mov     [rdi], eax
0x18000f0d1  mov     rax, rdi
0x18000f0d4  add     rsp, 28h
0x18000f0d8  pop     r14
0x18000f0da  pop     r12
0x18000f0dc  pop     rdi
0x18000f0dd  pop     rsi
0x18000f0de  pop     rbp
0x18000f0df  pop     rbx
0x18000f0e0  retn
```
