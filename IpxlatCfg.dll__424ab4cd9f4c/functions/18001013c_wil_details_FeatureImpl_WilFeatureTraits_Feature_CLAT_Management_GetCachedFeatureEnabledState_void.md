# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Management>::GetCachedFeatureEnabledState(void)

- ea: `0x18001013c`
- end: `0x180010309`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Management@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011e60`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000aff4`
- `0x18001013c`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Management>::GetCachedFeatureEnabledState(
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
  unsigned __int8 IsEnabled; // al
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
  v3 = *(_DWORD *)Feature_CLAT_Management__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Management__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(57709655, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Management__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Management__descriptor, 3, v4);
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
0x18001013c  mov     [rsp+arg_0], rcx
0x180010141  push    rbx
0x180010142  push    rbp
0x180010143  push    rsi
0x180010144  push    rdi
0x180010145  push    r12
0x180010147  push    r14
0x180010149  sub     rsp, 28h
0x18001014d  mov     r14, cs:Feature_CLAT_Management__descriptor
0x180010154  mov     rdi, rdx
0x180010157  mov     qword ptr [rdx], 0
0x18001015e  mov     eax, [r14]
0x180010161  mov     [rdx], eax
0x180010163  and     eax, 6
0x180010166  cmp     al, 6
0x180010168  jz      loc_1800102F9
0x18001016e  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180010173  mov     ebp, eax
0x180010175  mov     dword ptr [rsp+58h+arg_0], 0
0x18001017d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010184  test    rax, rax
0x180010187  jz      short loc_1800101A1
0x180010189  lea     r8, [rsp+58h+arg_0]
0x18001018e  mov     edx, 3
0x180010193  mov     ecx, 3709457h
0x180010198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019d  mov     edx, eax
0x18001019f  jmp     short loc_1800101AF
0x1800101a1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800101a8  test    rax, rax
0x1800101ab  jnz     short loc_180010189
0x1800101ad  xor     edx, edx
0x1800101af  mov     r8d, edx
0x1800101b2  mov     eax, edx
0x1800101b4  and     r8d, 0FFFFFF3Fh
0x1800101bb  and     edx, 80h
0x1800101c1  mov     ecx, r8d
0x1800101c4  mov     r12d, 40h ; '@'
0x1800101ca  and     ecx, 3
0x1800101cd  and     eax, r12d
0x1800101d0  shl     ecx, 2
0x1800101d3  or      ecx, eax
0x1800101d5  shl     ecx, 2
0x1800101d8  or      ecx, edx
0x1800101da  lea     ebx, ds:0[rcx*8]
0x1800101e1  test    r8d, r8d
0x1800101e4  jnz     short loc_1800101EB
0x1800101e6  mov     eax, r12d
0x1800101e9  jmp     short loc_1800101F5
0x1800101eb  xor     eax, eax
0x1800101ed  cmp     r8d, 2
0x1800101f1  cmovz   eax, r12d
0x1800101f5  or      ebx, eax
0x1800101f7  mov     ecx, 0C00h
0x1800101fc  mov     eax, ebx
0x1800101fe  and     eax, ecx
0x180010200  cmp     eax, ecx
0x180010202  jnz     short loc_180010209
0x180010204  mov     sil, 1
0x180010207  jmp     short loc_180010211
0x180010209  xor     sil, sil
0x18001020c  test    r12b, bl
0x18001020f  jz      short loc_18001022C
0x180010211  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Core@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl(void)'::`2'::impl
0x180010218  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)
0x18001021d  test    sil, sil
0x180010220  jz      short loc_18001022E
0x180010222  test    al, al
0x180010224  jnz     short loc_18001022E
0x180010226  btr     ebx, 0Ah
0x18001022a  jmp     short loc_18001022E
0x18001022c  xor     al, al
0x18001022e  test    r12b, bl
0x180010231  jz      short loc_18001023E
0x180010233  test    al, al
0x180010235  jz      short loc_18001023E
0x180010237  mov     esi, 1
0x18001023c  jmp     short loc_180010240
0x18001023e  xor     esi, esi
0x180010240  mov     eax, [rdi]
0x180010242  or      esi, ebx
0x180010244  mov     ebx, 180h
0x180010249  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001024e  mov     edx, eax
0x180010250  mov     [rdi], eax
0x180010252  jz      short loc_18001028C
0x180010254  test    dl, 2
0x180010257  jnz     short loc_18001028C
0x180010259  mov     eax, esi
0x18001025b  xor     eax, edx
0x18001025d  and     eax, ebx
0x18001025f  xor     eax, edx
0x180010261  mov     ecx, eax
0x180010263  xor     ecx, esi
0x180010265  and     ecx, r12d
0x180010268  xor     ecx, eax
0x18001026a  mov     eax, ecx
0x18001026c  xor     eax, esi
0x18001026e  and     eax, 1
0x180010271  xor     eax, ecx
0x180010273  mov     r8d, eax
0x180010276  xor     r8d, esi
0x180010279  and     r8d, 800h
0x180010280  xor     r8d, eax
0x180010283  or      r8d, 2
0x180010287  mov     [rdi], r8d
0x18001028a  jmp     short loc_18001028F
0x18001028c  mov     r8d, edx
0x18001028f  mov     r9d, edx
0x180010292  and     r9d, 4
0x180010296  jnz     short loc_1800102AD
0x180010298  mov     ecx, esi
0x18001029a  xor     ecx, r8d
0x18001029d  and     ecx, 400h
0x1800102a3  xor     ecx, r8d
0x1800102a6  or      ecx, 4
0x1800102a9  mov     [rdi], ecx
0x1800102ab  jmp     short loc_1800102B0
0x1800102ad  mov     ecx, r8d
0x1800102b0  mov     eax, edx
0x1800102b2  lock cmpxchg [r14], ecx
0x1800102b7  jnz     short loc_180010249
0x1800102b9  test    r9d, r9d
0x1800102bc  jnz     short loc_1800102CD
0x1800102be  mov     r8d, ebp
0x1800102c1  lea     edx, [r9+3]
0x1800102c5  mov     rcx, r14
0x1800102c8  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800102cd  test    byte ptr [rdi], 2
0x1800102d0  jnz     short loc_1800102F9
0x1800102d2  mov     eax, [rdi]
0x1800102d4  xor     eax, esi
0x1800102d6  and     eax, ebx
0x1800102d8  xor     eax, [rdi]
0x1800102da  mov     ecx, eax
0x1800102dc  xor     ecx, esi
0x1800102de  and     ecx, r12d
0x1800102e1  xor     ecx, eax
0x1800102e3  mov     edx, ecx
0x1800102e5  xor     edx, esi
0x1800102e7  and     edx, 1
0x1800102ea  xor     edx, ecx
0x1800102ec  mov     eax, edx
0x1800102ee  xor     eax, esi
0x1800102f0  and     eax, 800h
0x1800102f5  xor     eax, edx
0x1800102f7  mov     [rdi], eax
0x1800102f9  mov     rax, rdi
0x1800102fc  add     rsp, 28h
0x180010300  pop     r14
0x180010302  pop     r12
0x180010304  pop     rdi
0x180010305  pop     rsi
0x180010306  pop     rbp
0x180010307  pop     rbx
0x180010308  retn
```
