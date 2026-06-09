# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetCachedFeatureEnabledState(void)

- ea: `0x18002647c`
- end: `0x180026649`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800270a8`

## callees

- `0x180007d0c`
- `0x18000b2e0`
- `0x18002647c`
- `0x18002700c`
- `0x180041010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_MIDI2DeviceRemoval__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_MIDI2DeviceRemoval__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(60471030, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl'::`2'::impl);
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
            (volatile signed __int32 *)Feature_Servicing_MIDI2DeviceRemoval__descriptor,
            v18,
            v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_Servicing_MIDI2DeviceRemoval__descriptor,
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
0x18002647c  mov     [rsp+arg_0], rcx
0x180026481  push    rbx
0x180026482  push    rbp
0x180026483  push    rsi
0x180026484  push    rdi
0x180026485  push    r12
0x180026487  push    r14
0x180026489  sub     rsp, 28h
0x18002648d  mov     r14, cs:Feature_Servicing_MIDI2DeviceRemoval__descriptor
0x180026494  mov     rdi, rdx
0x180026497  mov     qword ptr [rdx], 0
0x18002649e  mov     eax, [r14]
0x1800264a1  mov     [rdx], eax
0x1800264a3  and     eax, 6
0x1800264a6  cmp     al, 6
0x1800264a8  jz      loc_180026639
0x1800264ae  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800264b3  mov     ebp, eax
0x1800264b5  mov     dword ptr [rsp+58h+arg_0], 0
0x1800264bd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800264c4  test    rax, rax
0x1800264c7  jz      short loc_1800264E1
0x1800264c9  lea     r8, [rsp+58h+arg_0]
0x1800264ce  mov     edx, 3
0x1800264d3  mov     ecx, 39AB6F6h
0x1800264d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264dd  mov     edx, eax
0x1800264df  jmp     short loc_1800264EF
0x1800264e1  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800264e8  test    rax, rax
0x1800264eb  jnz     short loc_1800264C9
0x1800264ed  xor     edx, edx
0x1800264ef  mov     r8d, edx
0x1800264f2  mov     eax, edx
0x1800264f4  and     r8d, 0FFFFFF3Fh
0x1800264fb  and     edx, 80h
0x180026501  mov     ecx, r8d
0x180026504  mov     r12d, 40h ; '@'
0x18002650a  and     ecx, 3
0x18002650d  and     eax, r12d
0x180026510  shl     ecx, 2
0x180026513  or      ecx, eax
0x180026515  shl     ecx, 2
0x180026518  or      ecx, edx
0x18002651a  lea     ebx, ds:0[rcx*8]
0x180026521  test    r8d, r8d
0x180026524  jnz     short loc_18002652B
0x180026526  mov     eax, r12d
0x180026529  jmp     short loc_180026535
0x18002652b  xor     eax, eax
0x18002652d  cmp     r8d, 2
0x180026531  cmovz   eax, r12d
0x180026535  or      ebx, eax
0x180026537  mov     ecx, 0C00h
0x18002653c  mov     eax, ebx
0x18002653e  and     eax, ecx
0x180026540  cmp     eax, ecx
0x180026542  jnz     short loc_180026549
0x180026544  mov     sil, 1
0x180026547  jmp     short loc_180026551
0x180026549  xor     sil, sil
0x18002654c  test    r12b, bl
0x18002654f  jz      short loc_18002656C
0x180026551  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl(void)'::`2'::impl
0x180026558  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(wil::ReportingKind)
0x18002655d  test    sil, sil
0x180026560  jz      short loc_18002656E
0x180026562  test    al, al
0x180026564  jnz     short loc_18002656E
0x180026566  btr     ebx, 0Ah
0x18002656a  jmp     short loc_18002656E
0x18002656c  xor     al, al
0x18002656e  test    r12b, bl
0x180026571  jz      short loc_18002657E
0x180026573  test    al, al
0x180026575  jz      short loc_18002657E
0x180026577  mov     esi, 1
0x18002657c  jmp     short loc_180026580
0x18002657e  xor     esi, esi
0x180026580  mov     eax, [rdi]
0x180026582  or      esi, ebx
0x180026584  mov     ebx, 180h
0x180026589  cmp     dword ptr [rsp+58h+arg_0], 0
0x18002658e  mov     edx, eax
0x180026590  mov     [rdi], eax
0x180026592  jz      short loc_1800265CC
0x180026594  test    dl, 2
0x180026597  jnz     short loc_1800265CC
0x180026599  mov     eax, esi
0x18002659b  xor     eax, edx
0x18002659d  and     eax, ebx
0x18002659f  xor     eax, edx
0x1800265a1  mov     ecx, eax
0x1800265a3  xor     ecx, esi
0x1800265a5  and     ecx, r12d
0x1800265a8  xor     ecx, eax
0x1800265aa  mov     eax, ecx
0x1800265ac  xor     eax, esi
0x1800265ae  and     eax, 1
0x1800265b1  xor     eax, ecx
0x1800265b3  mov     r8d, eax
0x1800265b6  xor     r8d, esi
0x1800265b9  and     r8d, 800h
0x1800265c0  xor     r8d, eax
0x1800265c3  or      r8d, 2
0x1800265c7  mov     [rdi], r8d
0x1800265ca  jmp     short loc_1800265CF
0x1800265cc  mov     r8d, edx
0x1800265cf  mov     r9d, edx
0x1800265d2  and     r9d, 4
0x1800265d6  jnz     short loc_1800265ED
0x1800265d8  mov     ecx, esi
0x1800265da  xor     ecx, r8d
0x1800265dd  and     ecx, 400h
0x1800265e3  xor     ecx, r8d
0x1800265e6  or      ecx, 4
0x1800265e9  mov     [rdi], ecx
0x1800265eb  jmp     short loc_1800265F0
0x1800265ed  mov     ecx, r8d
0x1800265f0  mov     eax, edx
0x1800265f2  lock cmpxchg [r14], ecx
0x1800265f7  jnz     short loc_180026589
0x1800265f9  test    r9d, r9d
0x1800265fc  jnz     short loc_18002660D
0x1800265fe  mov     r8d, ebp
0x180026601  lea     edx, [r9+3]
0x180026605  mov     rcx, r14
0x180026608  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002660d  test    byte ptr [rdi], 2
0x180026610  jnz     short loc_180026639
0x180026612  mov     eax, [rdi]
0x180026614  xor     eax, esi
0x180026616  and     eax, ebx
0x180026618  xor     eax, [rdi]
0x18002661a  mov     ecx, eax
0x18002661c  xor     ecx, esi
0x18002661e  and     ecx, r12d
0x180026621  xor     ecx, eax
0x180026623  mov     edx, ecx
0x180026625  xor     edx, esi
0x180026627  and     edx, 1
0x18002662a  xor     edx, ecx
0x18002662c  mov     eax, edx
0x18002662e  xor     eax, esi
0x180026630  and     eax, 800h
0x180026635  xor     eax, edx
0x180026637  mov     [rdi], eax
0x180026639  mov     rax, rdi
0x18002663c  add     rsp, 28h
0x180026640  pop     r14
0x180026642  pop     r12
0x180026644  pop     rdi
0x180026645  pop     rsi
0x180026646  pop     rbp
0x180026647  pop     rbx
0x180026648  retn
```
