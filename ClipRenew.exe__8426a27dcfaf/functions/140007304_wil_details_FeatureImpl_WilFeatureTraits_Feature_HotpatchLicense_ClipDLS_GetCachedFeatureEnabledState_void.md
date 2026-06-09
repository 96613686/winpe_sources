# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HotpatchLicense_ClipDLS>::GetCachedFeatureEnabledState(void)

- ea: `0x140007304`
- end: `0x1400074ba`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HotpatchLicense_ClipDLS@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `438`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140011e0c`

## callees

- `0x140006cac`
- `0x140007304`
- `0x1400114d4`
- `0x140014010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HotpatchLicense_ClipDLS>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // ebx
  char v9; // al
  int v10; // eax
  int v11; // ebx
  signed __int32 v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  int v15; // r8d
  int v16; // r9d
  signed __int32 v17; // ecx
  wil::details *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_HotpatchLicense_ClipDLS__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_HotpatchLicense_ClipDLS__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v19) = 0;
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  v6 = 0;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60565610, 0, &v19);
  }
  v7 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v7 = 64;
  v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v9 = 1;
  }
  else
  {
    if ( (v8 & 0x40) != 0 )
    {
LABEL_14:
      v10 = 1;
      goto LABEL_15;
    }
    v9 = 0;
  }
  if ( (v8 & 0x40) != 0 && v9 )
    goto LABEL_14;
  v10 = 0;
LABEL_15:
  v11 = v10 | v8;
  if ( !v4 )
    LODWORD(v19) = 0;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = (_DWORD)v19 == 0;
    v14 = v12;
    *(_DWORD *)a2 = v12;
    if ( v13 || (v12 & 2) != 0 )
    {
      v15 = v12;
    }
    else
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v11)
          & 0x180
          ^ (v11
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v11)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v11
           ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v11
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v11)
                              & 0x180
                              ^ (v11
                               ^ v12
                               ^ (v12
                                ^ v11)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v11
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v11) & 0x80 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v16 = v12 & 4;
    if ( (v12 & 4) != 0 )
    {
      v17 = v15;
    }
    else
    {
      v17 = v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)v11) & 0x400 | 4;
      *(_DWORD *)a2 = v17;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_HotpatchLicense_ClipDLS__descriptor, v17, v12);
  }
  while ( v14 != v12 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_HotpatchLicense_ClipDLS__descriptor, 0, v4);
  if ( (*(_BYTE *)a2 & 2) == 0 )
    *(_DWORD *)a2 ^= ((unsigned __int16)v11
                    ^ (unsigned __int16)*(_DWORD *)a2)
                   & 0x180
                   ^ (v11
                    ^ *(_DWORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180)
                   & 0x40
                   ^ ((unsigned __int8)v11
                    ^ *(_BYTE *)a2
                    ^ ((unsigned __int8)v11
                     ^ (unsigned __int8)*(_DWORD *)a2)
                    & 0x80
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80)
                    & 0x40)
                   & 1
                   ^ ((unsigned __int16)v11
                    ^ *(_WORD *)a2
                    ^ ((unsigned __int16)v11
                     ^ (unsigned __int16)*(_DWORD *)a2)
                    & 0x180
                    ^ ((unsigned __int16)v11
                     ^ *(_WORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180)
                    & 0x40
                    ^ ((unsigned __int8)v11
                     ^ *(_BYTE *)a2
                     ^ ((unsigned __int8)v11
                      ^ (unsigned __int8)*(_DWORD *)a2)
                     & 0x80
                     ^ ((unsigned __int8)v11
                      ^ *(_BYTE *)a2
                      ^ ((unsigned __int8)v11
                       ^ (unsigned __int8)*(_DWORD *)a2)
                      & 0x80)
                     & 0x40)
                    & 1)
                   & 0x800;
  return a2;
}

```

## disassembly

```asm
0x140007304  mov     [rsp+arg_8], rbx
0x140007309  mov     [rsp+arg_10], rbp
0x14000730e  mov     [rsp+arg_0], rcx
0x140007313  push    rsi
0x140007314  push    rdi
0x140007315  push    r15
0x140007317  sub     rsp, 20h
0x14000731b  mov     rsi, cs:Feature_HotpatchLicense_ClipDLS__descriptor
0x140007322  mov     rdi, rdx
0x140007325  mov     qword ptr [rdx], 0
0x14000732c  mov     eax, [rsi]
0x14000732e  mov     [rdx], eax
0x140007330  and     eax, 6
0x140007333  cmp     al, 6
0x140007335  jz      loc_1400074A4
0x14000733b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140007340  mov     ebp, eax
0x140007342  mov     dword ptr [rsp+38h+arg_0], 0
0x14000734a  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140007351  xor     edx, edx
0x140007353  test    rax, rax
0x140007356  jnz     short loc_140007364
0x140007358  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x14000735f  test    rax, rax
0x140007362  jz      short loc_140007375
0x140007364  lea     r8, [rsp+38h+arg_0]
0x140007369  mov     ecx, 39C286Ah
0x14000736e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007373  mov     edx, eax
0x140007375  mov     r8d, edx
0x140007378  mov     eax, edx
0x14000737a  and     r8d, 0FFFFFF3Fh
0x140007381  and     edx, 80h
0x140007387  mov     ecx, r8d
0x14000738a  mov     r15d, 40h ; '@'
0x140007390  and     ecx, 3
0x140007393  and     eax, r15d
0x140007396  shl     ecx, 2
0x140007399  or      ecx, eax
0x14000739b  xor     eax, eax
0x14000739d  shl     ecx, 2
0x1400073a0  or      ecx, edx
0x1400073a2  lea     ebx, ds:0[rcx*8]
0x1400073a9  test    r8d, r8d
0x1400073ac  jz      short loc_1400073B6
0x1400073ae  cmp     r8d, 2
0x1400073b2  cmovz   eax, r15d
0x1400073b6  or      ebx, eax
0x1400073b8  mov     edx, 0C00h
0x1400073bd  mov     ecx, ebx
0x1400073bf  mov     eax, ebx
0x1400073c1  and     ecx, r15d
0x1400073c4  and     eax, edx
0x1400073c6  cmp     eax, edx
0x1400073c8  jnz     short loc_1400073CE
0x1400073ca  mov     al, 1
0x1400073cc  jmp     short loc_1400073D4
0x1400073ce  test    ecx, ecx
0x1400073d0  jnz     short loc_1400073E0
0x1400073d2  xor     al, al
0x1400073d4  test    ecx, ecx
0x1400073d6  jz      short loc_1400073DC
0x1400073d8  test    al, al
0x1400073da  jnz     short loc_1400073E0
0x1400073dc  xor     eax, eax
0x1400073de  jmp     short loc_1400073E5
0x1400073e0  mov     eax, 1
0x1400073e5  or      ebx, eax
0x1400073e7  test    ebp, ebp
0x1400073e9  jnz     short loc_1400073EF
0x1400073eb  mov     dword ptr [rsp+38h+arg_0], ebp
0x1400073ef  mov     eax, [rdi]
0x1400073f1  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400073f6  mov     edx, eax
0x1400073f8  mov     [rdi], eax
0x1400073fa  jz      short loc_140007437
0x1400073fc  test    dl, 2
0x1400073ff  jnz     short loc_140007437
0x140007401  mov     eax, ebx
0x140007403  xor     eax, edx
0x140007405  and     eax, 180h
0x14000740a  xor     eax, edx
0x14000740c  mov     ecx, eax
0x14000740e  xor     ecx, ebx
0x140007410  and     ecx, r15d
0x140007413  xor     ecx, eax
0x140007415  mov     eax, ecx
0x140007417  xor     eax, ebx
0x140007419  and     eax, 1
0x14000741c  xor     eax, ecx
0x14000741e  mov     r8d, eax
0x140007421  xor     r8d, ebx
0x140007424  and     r8d, 800h
0x14000742b  xor     r8d, eax
0x14000742e  or      r8d, 2
0x140007432  mov     [rdi], r8d
0x140007435  jmp     short loc_14000743A
0x140007437  mov     r8d, edx
0x14000743a  mov     r9d, edx
0x14000743d  and     r9d, 4
0x140007441  jnz     short loc_140007458
0x140007443  mov     ecx, ebx
0x140007445  xor     ecx, r8d
0x140007448  and     ecx, 400h
0x14000744e  xor     ecx, r8d
0x140007451  or      ecx, 4
0x140007454  mov     [rdi], ecx
0x140007456  jmp     short loc_14000745B
0x140007458  mov     ecx, r8d
0x14000745b  mov     eax, edx
0x14000745d  lock cmpxchg [rsi], ecx
0x140007461  jnz     short loc_1400073F1
0x140007463  test    r9d, r9d
0x140007466  jnz     short loc_140007475
0x140007468  mov     r8d, ebp
0x14000746b  xor     edx, edx
0x14000746d  mov     rcx, rsi
0x140007470  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140007475  test    byte ptr [rdi], 2
0x140007478  jnz     short loc_1400074A4
0x14000747a  mov     eax, [rdi]
0x14000747c  xor     eax, ebx
0x14000747e  and     eax, 180h
0x140007483  xor     eax, [rdi]
0x140007485  mov     ecx, eax
0x140007487  xor     ecx, ebx
0x140007489  and     ecx, r15d
0x14000748c  xor     ecx, eax
0x14000748e  mov     edx, ecx
0x140007490  xor     edx, ebx
0x140007492  and     edx, 1
0x140007495  xor     edx, ecx
0x140007497  mov     eax, edx
0x140007499  xor     eax, ebx
0x14000749b  and     eax, 800h
0x1400074a0  xor     eax, edx
0x1400074a2  mov     [rdi], eax
0x1400074a4  mov     rbx, [rsp+38h+arg_8]
0x1400074a9  mov     rax, rdi
0x1400074ac  mov     rbp, [rsp+38h+arg_10]
0x1400074b1  add     rsp, 20h
0x1400074b5  pop     r15
0x1400074b7  pop     rdi
0x1400074b8  pop     rsi
0x1400074b9  retn
```
