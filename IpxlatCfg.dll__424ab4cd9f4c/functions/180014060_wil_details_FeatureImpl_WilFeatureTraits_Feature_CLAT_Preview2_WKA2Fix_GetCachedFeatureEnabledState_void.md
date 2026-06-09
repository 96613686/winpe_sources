# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_WKA2Fix>::GetCachedFeatureEnabledState(void)

- ea: `0x180014060`
- end: `0x18001422d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_WKA2Fix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017a70`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000b090`
- `0x180014060`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_WKA2Fix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_WKA2Fix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_WKA2Fix__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(59100856, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2_WKA2Fix__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_WKA2Fix__descriptor, 3, v4);
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
0x180014060  mov     [rsp+arg_0], rcx
0x180014065  push    rbx
0x180014066  push    rbp
0x180014067  push    rsi
0x180014068  push    rdi
0x180014069  push    r12
0x18001406b  push    r14
0x18001406d  sub     rsp, 28h
0x180014071  mov     r14, cs:Feature_CLAT_Preview2_WKA2Fix__descriptor
0x180014078  mov     rdi, rdx
0x18001407b  mov     qword ptr [rdx], 0
0x180014082  mov     eax, [r14]
0x180014085  mov     [rdx], eax
0x180014087  and     eax, 6
0x18001408a  cmp     al, 6
0x18001408c  jz      loc_18001421D
0x180014092  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014097  mov     ebp, eax
0x180014099  mov     dword ptr [rsp+58h+arg_0], 0
0x1800140a1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800140a8  test    rax, rax
0x1800140ab  jz      short loc_1800140C5
0x1800140ad  lea     r8, [rsp+58h+arg_0]
0x1800140b2  mov     edx, 3
0x1800140b7  mov     ecx, 385CEB8h
0x1800140bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c1  mov     edx, eax
0x1800140c3  jmp     short loc_1800140D3
0x1800140c5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800140cc  test    rax, rax
0x1800140cf  jnz     short loc_1800140AD
0x1800140d1  xor     edx, edx
0x1800140d3  mov     r8d, edx
0x1800140d6  mov     eax, edx
0x1800140d8  and     r8d, 0FFFFFF3Fh
0x1800140df  and     edx, 80h
0x1800140e5  mov     ecx, r8d
0x1800140e8  mov     r12d, 40h ; '@'
0x1800140ee  and     ecx, 3
0x1800140f1  and     eax, r12d
0x1800140f4  shl     ecx, 2
0x1800140f7  or      ecx, eax
0x1800140f9  shl     ecx, 2
0x1800140fc  or      ecx, edx
0x1800140fe  lea     ebx, ds:0[rcx*8]
0x180014105  test    r8d, r8d
0x180014108  jnz     short loc_18001410F
0x18001410a  mov     eax, r12d
0x18001410d  jmp     short loc_180014119
0x18001410f  xor     eax, eax
0x180014111  cmp     r8d, 2
0x180014115  cmovz   eax, r12d
0x180014119  or      ebx, eax
0x18001411b  mov     ecx, 0C00h
0x180014120  mov     eax, ebx
0x180014122  and     eax, ecx
0x180014124  cmp     eax, ecx
0x180014126  jnz     short loc_18001412D
0x180014128  mov     sil, 1
0x18001412b  jmp     short loc_180014135
0x18001412d  xor     sil, sil
0x180014130  test    r12b, bl
0x180014133  jz      short loc_180014150
0x180014135  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2>::GetImpl(void)'::`2'::impl
0x18001413c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2>::__private_IsEnabled(wil::ReportingKind)
0x180014141  test    sil, sil
0x180014144  jz      short loc_180014152
0x180014146  test    al, al
0x180014148  jnz     short loc_180014152
0x18001414a  btr     ebx, 0Ah
0x18001414e  jmp     short loc_180014152
0x180014150  xor     al, al
0x180014152  test    r12b, bl
0x180014155  jz      short loc_180014162
0x180014157  test    al, al
0x180014159  jz      short loc_180014162
0x18001415b  mov     esi, 1
0x180014160  jmp     short loc_180014164
0x180014162  xor     esi, esi
0x180014164  mov     eax, [rdi]
0x180014166  or      esi, ebx
0x180014168  mov     ebx, 180h
0x18001416d  cmp     dword ptr [rsp+58h+arg_0], 0
0x180014172  mov     edx, eax
0x180014174  mov     [rdi], eax
0x180014176  jz      short loc_1800141B0
0x180014178  test    dl, 2
0x18001417b  jnz     short loc_1800141B0
0x18001417d  mov     eax, esi
0x18001417f  xor     eax, edx
0x180014181  and     eax, ebx
0x180014183  xor     eax, edx
0x180014185  mov     ecx, eax
0x180014187  xor     ecx, esi
0x180014189  and     ecx, r12d
0x18001418c  xor     ecx, eax
0x18001418e  mov     eax, ecx
0x180014190  xor     eax, esi
0x180014192  and     eax, 1
0x180014195  xor     eax, ecx
0x180014197  mov     r8d, eax
0x18001419a  xor     r8d, esi
0x18001419d  and     r8d, 800h
0x1800141a4  xor     r8d, eax
0x1800141a7  or      r8d, 2
0x1800141ab  mov     [rdi], r8d
0x1800141ae  jmp     short loc_1800141B3
0x1800141b0  mov     r8d, edx
0x1800141b3  mov     r9d, edx
0x1800141b6  and     r9d, 4
0x1800141ba  jnz     short loc_1800141D1
0x1800141bc  mov     ecx, esi
0x1800141be  xor     ecx, r8d
0x1800141c1  and     ecx, 400h
0x1800141c7  xor     ecx, r8d
0x1800141ca  or      ecx, 4
0x1800141cd  mov     [rdi], ecx
0x1800141cf  jmp     short loc_1800141D4
0x1800141d1  mov     ecx, r8d
0x1800141d4  mov     eax, edx
0x1800141d6  lock cmpxchg [r14], ecx
0x1800141db  jnz     short loc_18001416D
0x1800141dd  test    r9d, r9d
0x1800141e0  jnz     short loc_1800141F1
0x1800141e2  mov     r8d, ebp
0x1800141e5  lea     edx, [r9+3]
0x1800141e9  mov     rcx, r14
0x1800141ec  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800141f1  test    byte ptr [rdi], 2
0x1800141f4  jnz     short loc_18001421D
0x1800141f6  mov     eax, [rdi]
0x1800141f8  xor     eax, esi
0x1800141fa  and     eax, ebx
0x1800141fc  xor     eax, [rdi]
0x1800141fe  mov     ecx, eax
0x180014200  xor     ecx, esi
0x180014202  and     ecx, r12d
0x180014205  xor     ecx, eax
0x180014207  mov     edx, ecx
0x180014209  xor     edx, esi
0x18001420b  and     edx, 1
0x18001420e  xor     edx, ecx
0x180014210  mov     eax, edx
0x180014212  xor     eax, esi
0x180014214  and     eax, 800h
0x180014219  xor     eax, edx
0x18001421b  mov     [rdi], eax
0x18001421d  mov     rax, rdi
0x180014220  add     rsp, 28h
0x180014224  pop     r14
0x180014226  pop     r12
0x180014228  pop     rdi
0x180014229  pop     rsi
0x18001422a  pop     rbp
0x18001422b  pop     rbx
0x18001422c  retn
```
