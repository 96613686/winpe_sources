# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetCachedFeatureEnabledState(void)

- ea: `0x180013e8c`
- end: `0x180014059`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800179d0`

## callees

- `0x180005498`
- `0x180008f34`
- `0x180013e8c`
- `0x180017850`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_Preview2_Telemetry__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_Preview2_Telemetry__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(51856468, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_Preview2_Telemetry__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_Preview2_Telemetry__descriptor, 3, v4);
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
0x180013e8c  mov     [rsp+arg_0], rcx
0x180013e91  push    rbx
0x180013e92  push    rbp
0x180013e93  push    rsi
0x180013e94  push    rdi
0x180013e95  push    r12
0x180013e97  push    r14
0x180013e99  sub     rsp, 28h
0x180013e9d  mov     r14, cs:Feature_CLAT_Preview2_Telemetry__descriptor
0x180013ea4  mov     rdi, rdx
0x180013ea7  mov     qword ptr [rdx], 0
0x180013eae  mov     eax, [r14]
0x180013eb1  mov     [rdx], eax
0x180013eb3  and     eax, 6
0x180013eb6  cmp     al, 6
0x180013eb8  jz      loc_180014049
0x180013ebe  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013ec3  mov     ebp, eax
0x180013ec5  mov     dword ptr [rsp+58h+arg_0], 0
0x180013ecd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013ed4  test    rax, rax
0x180013ed7  jz      short loc_180013EF1
0x180013ed9  lea     r8, [rsp+58h+arg_0]
0x180013ede  mov     edx, 3
0x180013ee3  mov     ecx, 3174454h
0x180013ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eed  mov     edx, eax
0x180013eef  jmp     short loc_180013EFF
0x180013ef1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180013ef8  test    rax, rax
0x180013efb  jnz     short loc_180013ED9
0x180013efd  xor     edx, edx
0x180013eff  mov     r8d, edx
0x180013f02  mov     eax, edx
0x180013f04  and     r8d, 0FFFFFF3Fh
0x180013f0b  and     edx, 80h
0x180013f11  mov     ecx, r8d
0x180013f14  mov     r12d, 40h ; '@'
0x180013f1a  and     ecx, 3
0x180013f1d  and     eax, r12d
0x180013f20  shl     ecx, 2
0x180013f23  or      ecx, eax
0x180013f25  shl     ecx, 2
0x180013f28  or      ecx, edx
0x180013f2a  lea     ebx, ds:0[rcx*8]
0x180013f31  test    r8d, r8d
0x180013f34  jnz     short loc_180013F3B
0x180013f36  mov     eax, r12d
0x180013f39  jmp     short loc_180013F45
0x180013f3b  xor     eax, eax
0x180013f3d  cmp     r8d, 2
0x180013f41  cmovz   eax, r12d
0x180013f45  or      ebx, eax
0x180013f47  mov     ecx, 0C00h
0x180013f4c  mov     eax, ebx
0x180013f4e  and     eax, ecx
0x180013f50  cmp     eax, ecx
0x180013f52  jnz     short loc_180013F59
0x180013f54  mov     sil, 1
0x180013f57  jmp     short loc_180013F61
0x180013f59  xor     sil, sil
0x180013f5c  test    r12b, bl
0x180013f5f  jz      short loc_180013F7C
0x180013f61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl(void)'::`2'::impl
0x180013f68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(wil::ReportingKind)
0x180013f6d  test    sil, sil
0x180013f70  jz      short loc_180013F7E
0x180013f72  test    al, al
0x180013f74  jnz     short loc_180013F7E
0x180013f76  btr     ebx, 0Ah
0x180013f7a  jmp     short loc_180013F7E
0x180013f7c  xor     al, al
0x180013f7e  test    r12b, bl
0x180013f81  jz      short loc_180013F8E
0x180013f83  test    al, al
0x180013f85  jz      short loc_180013F8E
0x180013f87  mov     esi, 1
0x180013f8c  jmp     short loc_180013F90
0x180013f8e  xor     esi, esi
0x180013f90  mov     eax, [rdi]
0x180013f92  or      esi, ebx
0x180013f94  mov     ebx, 180h
0x180013f99  cmp     dword ptr [rsp+58h+arg_0], 0
0x180013f9e  mov     edx, eax
0x180013fa0  mov     [rdi], eax
0x180013fa2  jz      short loc_180013FDC
0x180013fa4  test    dl, 2
0x180013fa7  jnz     short loc_180013FDC
0x180013fa9  mov     eax, esi
0x180013fab  xor     eax, edx
0x180013fad  and     eax, ebx
0x180013faf  xor     eax, edx
0x180013fb1  mov     ecx, eax
0x180013fb3  xor     ecx, esi
0x180013fb5  and     ecx, r12d
0x180013fb8  xor     ecx, eax
0x180013fba  mov     eax, ecx
0x180013fbc  xor     eax, esi
0x180013fbe  and     eax, 1
0x180013fc1  xor     eax, ecx
0x180013fc3  mov     r8d, eax
0x180013fc6  xor     r8d, esi
0x180013fc9  and     r8d, 800h
0x180013fd0  xor     r8d, eax
0x180013fd3  or      r8d, 2
0x180013fd7  mov     [rdi], r8d
0x180013fda  jmp     short loc_180013FDF
0x180013fdc  mov     r8d, edx
0x180013fdf  mov     r9d, edx
0x180013fe2  and     r9d, 4
0x180013fe6  jnz     short loc_180013FFD
0x180013fe8  mov     ecx, esi
0x180013fea  xor     ecx, r8d
0x180013fed  and     ecx, 400h
0x180013ff3  xor     ecx, r8d
0x180013ff6  or      ecx, 4
0x180013ff9  mov     [rdi], ecx
0x180013ffb  jmp     short loc_180014000
0x180013ffd  mov     ecx, r8d
0x180014000  mov     eax, edx
0x180014002  lock cmpxchg [r14], ecx
0x180014007  jnz     short loc_180013F99
0x180014009  test    r9d, r9d
0x18001400c  jnz     short loc_18001401D
0x18001400e  mov     r8d, ebp
0x180014011  lea     edx, [r9+3]
0x180014015  mov     rcx, r14
0x180014018  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001401d  test    byte ptr [rdi], 2
0x180014020  jnz     short loc_180014049
0x180014022  mov     eax, [rdi]
0x180014024  xor     eax, esi
0x180014026  and     eax, ebx
0x180014028  xor     eax, [rdi]
0x18001402a  mov     ecx, eax
0x18001402c  xor     ecx, esi
0x18001402e  and     ecx, r12d
0x180014031  xor     ecx, eax
0x180014033  mov     edx, ecx
0x180014035  xor     edx, esi
0x180014037  and     edx, 1
0x18001403a  xor     edx, ecx
0x18001403c  mov     eax, edx
0x18001403e  xor     eax, esi
0x180014040  and     eax, 800h
0x180014045  xor     eax, edx
0x180014047  mov     [rdi], eax
0x180014049  mov     rax, rdi
0x18001404c  add     rsp, 28h
0x180014050  pop     r14
0x180014052  pop     r12
0x180014054  pop     rdi
0x180014055  pop     rsi
0x180014056  pop     rbp
0x180014057  pop     rbx
0x180014058  retn
```
