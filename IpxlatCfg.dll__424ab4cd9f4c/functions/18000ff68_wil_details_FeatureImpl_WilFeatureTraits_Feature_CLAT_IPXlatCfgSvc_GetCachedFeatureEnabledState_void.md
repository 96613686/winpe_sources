# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ff68`
- end: `0x180010135`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011dc0`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000aff4`
- `0x18000ff68`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_IPXlatCfgSvc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_IPXlatCfgSvc__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56738205, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_IPXlatCfgSvc__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_IPXlatCfgSvc__descriptor, 3, v4);
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
0x18000ff68  mov     [rsp+arg_0], rcx
0x18000ff6d  push    rbx
0x18000ff6e  push    rbp
0x18000ff6f  push    rsi
0x18000ff70  push    rdi
0x18000ff71  push    r12
0x18000ff73  push    r14
0x18000ff75  sub     rsp, 28h
0x18000ff79  mov     r14, cs:Feature_CLAT_IPXlatCfgSvc__descriptor
0x18000ff80  mov     rdi, rdx
0x18000ff83  mov     qword ptr [rdx], 0
0x18000ff8a  mov     eax, [r14]
0x18000ff8d  mov     [rdx], eax
0x18000ff8f  and     eax, 6
0x18000ff92  cmp     al, 6
0x18000ff94  jz      loc_180010125
0x18000ff9a  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ff9f  mov     ebp, eax
0x18000ffa1  mov     dword ptr [rsp+58h+arg_0], 0
0x18000ffa9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ffb0  test    rax, rax
0x18000ffb3  jz      short loc_18000FFCD
0x18000ffb5  lea     r8, [rsp+58h+arg_0]
0x18000ffba  mov     edx, 3
0x18000ffbf  mov     ecx, 361C19Dh
0x18000ffc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc9  mov     edx, eax
0x18000ffcb  jmp     short loc_18000FFDB
0x18000ffcd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ffd4  test    rax, rax
0x18000ffd7  jnz     short loc_18000FFB5
0x18000ffd9  xor     edx, edx
0x18000ffdb  mov     r8d, edx
0x18000ffde  mov     eax, edx
0x18000ffe0  and     r8d, 0FFFFFF3Fh
0x18000ffe7  and     edx, 80h
0x18000ffed  mov     ecx, r8d
0x18000fff0  mov     r12d, 40h ; '@'
0x18000fff6  and     ecx, 3
0x18000fff9  and     eax, r12d
0x18000fffc  shl     ecx, 2
0x18000ffff  or      ecx, eax
0x180010001  shl     ecx, 2
0x180010004  or      ecx, edx
0x180010006  lea     ebx, ds:0[rcx*8]
0x18001000d  test    r8d, r8d
0x180010010  jnz     short loc_180010017
0x180010012  mov     eax, r12d
0x180010015  jmp     short loc_180010021
0x180010017  xor     eax, eax
0x180010019  cmp     r8d, 2
0x18001001d  cmovz   eax, r12d
0x180010021  or      ebx, eax
0x180010023  mov     ecx, 0C00h
0x180010028  mov     eax, ebx
0x18001002a  and     eax, ecx
0x18001002c  cmp     eax, ecx
0x18001002e  jnz     short loc_180010035
0x180010030  mov     sil, 1
0x180010033  jmp     short loc_18001003D
0x180010035  xor     sil, sil
0x180010038  test    r12b, bl
0x18001003b  jz      short loc_180010058
0x18001003d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Core@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl(void)'::`2'::impl
0x180010044  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)
0x180010049  test    sil, sil
0x18001004c  jz      short loc_18001005A
0x18001004e  test    al, al
0x180010050  jnz     short loc_18001005A
0x180010052  btr     ebx, 0Ah
0x180010056  jmp     short loc_18001005A
0x180010058  xor     al, al
0x18001005a  test    r12b, bl
0x18001005d  jz      short loc_18001006A
0x18001005f  test    al, al
0x180010061  jz      short loc_18001006A
0x180010063  mov     esi, 1
0x180010068  jmp     short loc_18001006C
0x18001006a  xor     esi, esi
0x18001006c  mov     eax, [rdi]
0x18001006e  or      esi, ebx
0x180010070  mov     ebx, 180h
0x180010075  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001007a  mov     edx, eax
0x18001007c  mov     [rdi], eax
0x18001007e  jz      short loc_1800100B8
0x180010080  test    dl, 2
0x180010083  jnz     short loc_1800100B8
0x180010085  mov     eax, esi
0x180010087  xor     eax, edx
0x180010089  and     eax, ebx
0x18001008b  xor     eax, edx
0x18001008d  mov     ecx, eax
0x18001008f  xor     ecx, esi
0x180010091  and     ecx, r12d
0x180010094  xor     ecx, eax
0x180010096  mov     eax, ecx
0x180010098  xor     eax, esi
0x18001009a  and     eax, 1
0x18001009d  xor     eax, ecx
0x18001009f  mov     r8d, eax
0x1800100a2  xor     r8d, esi
0x1800100a5  and     r8d, 800h
0x1800100ac  xor     r8d, eax
0x1800100af  or      r8d, 2
0x1800100b3  mov     [rdi], r8d
0x1800100b6  jmp     short loc_1800100BB
0x1800100b8  mov     r8d, edx
0x1800100bb  mov     r9d, edx
0x1800100be  and     r9d, 4
0x1800100c2  jnz     short loc_1800100D9
0x1800100c4  mov     ecx, esi
0x1800100c6  xor     ecx, r8d
0x1800100c9  and     ecx, 400h
0x1800100cf  xor     ecx, r8d
0x1800100d2  or      ecx, 4
0x1800100d5  mov     [rdi], ecx
0x1800100d7  jmp     short loc_1800100DC
0x1800100d9  mov     ecx, r8d
0x1800100dc  mov     eax, edx
0x1800100de  lock cmpxchg [r14], ecx
0x1800100e3  jnz     short loc_180010075
0x1800100e5  test    r9d, r9d
0x1800100e8  jnz     short loc_1800100F9
0x1800100ea  mov     r8d, ebp
0x1800100ed  lea     edx, [r9+3]
0x1800100f1  mov     rcx, r14
0x1800100f4  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800100f9  test    byte ptr [rdi], 2
0x1800100fc  jnz     short loc_180010125
0x1800100fe  mov     eax, [rdi]
0x180010100  xor     eax, esi
0x180010102  and     eax, ebx
0x180010104  xor     eax, [rdi]
0x180010106  mov     ecx, eax
0x180010108  xor     ecx, esi
0x18001010a  and     ecx, r12d
0x18001010d  xor     ecx, eax
0x18001010f  mov     edx, ecx
0x180010111  xor     edx, esi
0x180010113  and     edx, 1
0x180010116  xor     edx, ecx
0x180010118  mov     eax, edx
0x18001011a  xor     eax, esi
0x18001011c  and     eax, 800h
0x180010121  xor     eax, edx
0x180010123  mov     [rdi], eax
0x180010125  mov     rax, rdi
0x180010128  add     rsp, 28h
0x18001012c  pop     r14
0x18001012e  pop     r12
0x180010130  pop     rdi
0x180010131  pop     rsi
0x180010132  pop     rbp
0x180010133  pop     rbx
0x180010134  retn
```
