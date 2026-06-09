# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(void)

- ea: `0x18000dacc`
- end: `0x18000dc99`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800111e4`

## callees

- `0x18000da08`
- `0x18000dacc`
- `0x180010c28`
- `0x180011458`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(58156969, 3, &v20);
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
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2511__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      (volatile signed __int32 *)Feature_MediaQI2511__descriptor,
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
0x18000dacc  mov     [rsp+arg_0], rcx
0x18000dad1  push    rbx
0x18000dad2  push    rbp
0x18000dad3  push    rsi
0x18000dad4  push    rdi
0x18000dad5  push    r12
0x18000dad7  push    r14
0x18000dad9  sub     rsp, 28h
0x18000dadd  mov     r14, cs:Feature_MediaQI2511__descriptor
0x18000dae4  mov     rdi, rdx
0x18000dae7  mov     qword ptr [rdx], 0
0x18000daee  mov     eax, [r14]
0x18000daf1  mov     [rdx], eax
0x18000daf3  and     eax, 6
0x18000daf6  cmp     al, 6
0x18000daf8  jz      loc_18000DC89
0x18000dafe  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000db03  mov     ebp, eax
0x18000db05  mov     dword ptr [rsp+58h+arg_0], 0
0x18000db0d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000db14  test    rax, rax
0x18000db17  jz      short loc_18000DB31
0x18000db19  lea     r8, [rsp+58h+arg_0]
0x18000db1e  mov     edx, 3
0x18000db23  mov     ecx, 37767A9h
0x18000db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db2d  mov     edx, eax
0x18000db2f  jmp     short loc_18000DB3F
0x18000db31  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000db38  test    rax, rax
0x18000db3b  jnz     short loc_18000DB19
0x18000db3d  xor     edx, edx
0x18000db3f  mov     r8d, edx
0x18000db42  mov     eax, edx
0x18000db44  and     r8d, 0FFFFFF3Fh
0x18000db4b  and     edx, 80h
0x18000db51  mov     ecx, r8d
0x18000db54  mov     r12d, 40h ; '@'
0x18000db5a  and     ecx, 3
0x18000db5d  and     eax, r12d
0x18000db60  shl     ecx, 2
0x18000db63  or      ecx, eax
0x18000db65  shl     ecx, 2
0x18000db68  or      ecx, edx
0x18000db6a  lea     ebx, ds:0[rcx*8]
0x18000db71  test    r8d, r8d
0x18000db74  jnz     short loc_18000DB7B
0x18000db76  mov     eax, r12d
0x18000db79  jmp     short loc_18000DB85
0x18000db7b  xor     eax, eax
0x18000db7d  cmp     r8d, 2
0x18000db81  cmovz   eax, r12d
0x18000db85  or      ebx, eax
0x18000db87  mov     ecx, 0C00h
0x18000db8c  mov     eax, ebx
0x18000db8e  and     eax, ecx
0x18000db90  cmp     eax, ecx
0x18000db92  jnz     short loc_18000DB99
0x18000db94  mov     sil, 1
0x18000db97  jmp     short loc_18000DBA1
0x18000db99  xor     sil, sil
0x18000db9c  test    r12b, bl
0x18000db9f  jz      short loc_18000DBBC
0x18000dba1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18000dba8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18000dbad  test    sil, sil
0x18000dbb0  jz      short loc_18000DBBE
0x18000dbb2  test    al, al
0x18000dbb4  jnz     short loc_18000DBBE
0x18000dbb6  btr     ebx, 0Ah
0x18000dbba  jmp     short loc_18000DBBE
0x18000dbbc  xor     al, al
0x18000dbbe  test    r12b, bl
0x18000dbc1  jz      short loc_18000DBCE
0x18000dbc3  test    al, al
0x18000dbc5  jz      short loc_18000DBCE
0x18000dbc7  mov     esi, 1
0x18000dbcc  jmp     short loc_18000DBD0
0x18000dbce  xor     esi, esi
0x18000dbd0  mov     eax, [rdi]
0x18000dbd2  or      esi, ebx
0x18000dbd4  mov     ebx, 180h
0x18000dbd9  cmp     dword ptr [rsp+58h+arg_0], 0
0x18000dbde  mov     edx, eax
0x18000dbe0  mov     [rdi], eax
0x18000dbe2  jz      short loc_18000DC1C
0x18000dbe4  test    dl, 2
0x18000dbe7  jnz     short loc_18000DC1C
0x18000dbe9  mov     eax, esi
0x18000dbeb  xor     eax, edx
0x18000dbed  and     eax, ebx
0x18000dbef  xor     eax, edx
0x18000dbf1  mov     ecx, eax
0x18000dbf3  xor     ecx, esi
0x18000dbf5  and     ecx, r12d
0x18000dbf8  xor     ecx, eax
0x18000dbfa  mov     eax, ecx
0x18000dbfc  xor     eax, esi
0x18000dbfe  and     eax, 1
0x18000dc01  xor     eax, ecx
0x18000dc03  mov     r8d, eax
0x18000dc06  xor     r8d, esi
0x18000dc09  and     r8d, 800h
0x18000dc10  xor     r8d, eax
0x18000dc13  or      r8d, 2
0x18000dc17  mov     [rdi], r8d
0x18000dc1a  jmp     short loc_18000DC1F
0x18000dc1c  mov     r8d, edx
0x18000dc1f  mov     r9d, edx
0x18000dc22  and     r9d, 4
0x18000dc26  jnz     short loc_18000DC3D
0x18000dc28  mov     ecx, esi
0x18000dc2a  xor     ecx, r8d
0x18000dc2d  and     ecx, 400h
0x18000dc33  xor     ecx, r8d
0x18000dc36  or      ecx, 4
0x18000dc39  mov     [rdi], ecx
0x18000dc3b  jmp     short loc_18000DC40
0x18000dc3d  mov     ecx, r8d
0x18000dc40  mov     eax, edx
0x18000dc42  lock cmpxchg [r14], ecx
0x18000dc47  jnz     short loc_18000DBD9
0x18000dc49  test    r9d, r9d
0x18000dc4c  jnz     short loc_18000DC5D
0x18000dc4e  mov     r8d, ebp
0x18000dc51  lea     edx, [r9+3]
0x18000dc55  mov     rcx, r14
0x18000dc58  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc5d  test    byte ptr [rdi], 2
0x18000dc60  jnz     short loc_18000DC89
0x18000dc62  mov     eax, [rdi]
0x18000dc64  xor     eax, esi
0x18000dc66  and     eax, ebx
0x18000dc68  xor     eax, [rdi]
0x18000dc6a  mov     ecx, eax
0x18000dc6c  xor     ecx, esi
0x18000dc6e  and     ecx, r12d
0x18000dc71  xor     ecx, eax
0x18000dc73  mov     edx, ecx
0x18000dc75  xor     edx, esi
0x18000dc77  and     edx, 1
0x18000dc7a  xor     edx, ecx
0x18000dc7c  mov     eax, edx
0x18000dc7e  xor     eax, esi
0x18000dc80  and     eax, 800h
0x18000dc85  xor     eax, edx
0x18000dc87  mov     [rdi], eax
0x18000dc89  mov     rax, rdi
0x18000dc8c  add     rsp, 28h
0x18000dc90  pop     r14
0x18000dc92  pop     r12
0x18000dc94  pop     rdi
0x18000dc95  pop     rsi
0x18000dc96  pop     rbp
0x18000dc97  pop     rbx
0x18000dc98  retn
```
