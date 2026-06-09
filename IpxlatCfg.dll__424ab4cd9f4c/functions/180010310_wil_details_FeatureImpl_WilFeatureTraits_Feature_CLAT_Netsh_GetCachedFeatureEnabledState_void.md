# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::GetCachedFeatureEnabledState(void)

- ea: `0x180010310`
- end: `0x1800104dd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Netsh@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001109c`
- `0x180011efc`
- `0x1800176d0`

## callees

- `0x180005498`
- `0x180008f34`
- `0x180010310`
- `0x180011e60`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
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
  v3 = *(_DWORD *)Feature_CLAT_Netsh__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Netsh__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(51777658, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Management>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Management>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Netsh__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Netsh__descriptor, 3, v4);
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
0x180010310  mov     [rsp+arg_0], rcx
0x180010315  push    rbx
0x180010316  push    rbp
0x180010317  push    rsi
0x180010318  push    rdi
0x180010319  push    r12
0x18001031b  push    r14
0x18001031d  sub     rsp, 28h
0x180010321  mov     r14, cs:Feature_CLAT_Netsh__descriptor
0x180010328  mov     rdi, rdx
0x18001032b  mov     qword ptr [rdx], 0
0x180010332  mov     eax, [r14]
0x180010335  mov     [rdx], eax
0x180010337  and     eax, 6
0x18001033a  cmp     al, 6
0x18001033c  jz      loc_1800104CD
0x180010342  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180010347  mov     ebp, eax
0x180010349  mov     dword ptr [rsp+58h+arg_0], 0
0x180010351  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010358  test    rax, rax
0x18001035b  jz      short loc_180010375
0x18001035d  lea     r8, [rsp+58h+arg_0]
0x180010362  mov     edx, 3
0x180010367  mov     ecx, 316107Ah
0x18001036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010371  mov     edx, eax
0x180010373  jmp     short loc_180010383
0x180010375  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001037c  test    rax, rax
0x18001037f  jnz     short loc_18001035D
0x180010381  xor     edx, edx
0x180010383  mov     r8d, edx
0x180010386  mov     eax, edx
0x180010388  and     r8d, 0FFFFFF3Fh
0x18001038f  and     edx, 80h
0x180010395  mov     ecx, r8d
0x180010398  mov     r12d, 40h ; '@'
0x18001039e  and     ecx, 3
0x1800103a1  and     eax, r12d
0x1800103a4  shl     ecx, 2
0x1800103a7  or      ecx, eax
0x1800103a9  shl     ecx, 2
0x1800103ac  or      ecx, edx
0x1800103ae  lea     ebx, ds:0[rcx*8]
0x1800103b5  test    r8d, r8d
0x1800103b8  jnz     short loc_1800103BF
0x1800103ba  mov     eax, r12d
0x1800103bd  jmp     short loc_1800103C9
0x1800103bf  xor     eax, eax
0x1800103c1  cmp     r8d, 2
0x1800103c5  cmovz   eax, r12d
0x1800103c9  or      ebx, eax
0x1800103cb  mov     ecx, 0C00h
0x1800103d0  mov     eax, ebx
0x1800103d2  and     eax, ecx
0x1800103d4  cmp     eax, ecx
0x1800103d6  jnz     short loc_1800103DD
0x1800103d8  mov     sil, 1
0x1800103db  jmp     short loc_1800103E5
0x1800103dd  xor     sil, sil
0x1800103e0  test    r12b, bl
0x1800103e3  jz      short loc_180010400
0x1800103e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Management@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Management@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Management> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Management>::GetImpl(void)'::`2'::impl
0x1800103ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Management@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Management>::__private_IsEnabled(wil::ReportingKind)
0x1800103f1  test    sil, sil
0x1800103f4  jz      short loc_180010402
0x1800103f6  test    al, al
0x1800103f8  jnz     short loc_180010402
0x1800103fa  btr     ebx, 0Ah
0x1800103fe  jmp     short loc_180010402
0x180010400  xor     al, al
0x180010402  test    r12b, bl
0x180010405  jz      short loc_180010412
0x180010407  test    al, al
0x180010409  jz      short loc_180010412
0x18001040b  mov     esi, 1
0x180010410  jmp     short loc_180010414
0x180010412  xor     esi, esi
0x180010414  mov     eax, [rdi]
0x180010416  or      esi, ebx
0x180010418  mov     ebx, 180h
0x18001041d  cmp     dword ptr [rsp+58h+arg_0], 0
0x180010422  mov     edx, eax
0x180010424  mov     [rdi], eax
0x180010426  jz      short loc_180010460
0x180010428  test    dl, 2
0x18001042b  jnz     short loc_180010460
0x18001042d  mov     eax, esi
0x18001042f  xor     eax, edx
0x180010431  and     eax, ebx
0x180010433  xor     eax, edx
0x180010435  mov     ecx, eax
0x180010437  xor     ecx, esi
0x180010439  and     ecx, r12d
0x18001043c  xor     ecx, eax
0x18001043e  mov     eax, ecx
0x180010440  xor     eax, esi
0x180010442  and     eax, 1
0x180010445  xor     eax, ecx
0x180010447  mov     r8d, eax
0x18001044a  xor     r8d, esi
0x18001044d  and     r8d, 800h
0x180010454  xor     r8d, eax
0x180010457  or      r8d, 2
0x18001045b  mov     [rdi], r8d
0x18001045e  jmp     short loc_180010463
0x180010460  mov     r8d, edx
0x180010463  mov     r9d, edx
0x180010466  and     r9d, 4
0x18001046a  jnz     short loc_180010481
0x18001046c  mov     ecx, esi
0x18001046e  xor     ecx, r8d
0x180010471  and     ecx, 400h
0x180010477  xor     ecx, r8d
0x18001047a  or      ecx, 4
0x18001047d  mov     [rdi], ecx
0x18001047f  jmp     short loc_180010484
0x180010481  mov     ecx, r8d
0x180010484  mov     eax, edx
0x180010486  lock cmpxchg [r14], ecx
0x18001048b  jnz     short loc_18001041D
0x18001048d  test    r9d, r9d
0x180010490  jnz     short loc_1800104A1
0x180010492  mov     r8d, ebp
0x180010495  lea     edx, [r9+3]
0x180010499  mov     rcx, r14
0x18001049c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800104a1  test    byte ptr [rdi], 2
0x1800104a4  jnz     short loc_1800104CD
0x1800104a6  mov     eax, [rdi]
0x1800104a8  xor     eax, esi
0x1800104aa  and     eax, ebx
0x1800104ac  xor     eax, [rdi]
0x1800104ae  mov     ecx, eax
0x1800104b0  xor     ecx, esi
0x1800104b2  and     ecx, r12d
0x1800104b5  xor     ecx, eax
0x1800104b7  mov     edx, ecx
0x1800104b9  xor     edx, esi
0x1800104bb  and     edx, 1
0x1800104be  xor     edx, ecx
0x1800104c0  mov     eax, edx
0x1800104c2  xor     eax, esi
0x1800104c4  and     eax, 800h
0x1800104c9  xor     eax, edx
0x1800104cb  mov     [rdi], eax
0x1800104cd  mov     rax, rdi
0x1800104d0  add     rsp, 28h
0x1800104d4  pop     r14
0x1800104d6  pop     r12
0x1800104d8  pop     rdi
0x1800104d9  pop     rsi
0x1800104da  pop     rbp
0x1800104db  pop     rbx
0x1800104dc  retn
```
