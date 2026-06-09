# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::GetCachedFeatureEnabledState(void)

- ea: `0x180013830`
- end: `0x1800139fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `461`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017710`

## callees

- `0x180005498`
- `0x180008f34`
- `0x18000aff4`
- `0x180013830`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_PREF64_FromDNS>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CLAT_PREF64_FromDNS__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CLAT_PREF64_FromDNS__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v6 = v5(56662994, 3, &v20);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CLAT_PREF64_FromDNS__descriptor, v18, v12);
  }
  while ( v15 != v12 );
  if ( !v17 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_CLAT_PREF64_FromDNS__descriptor, 3, v4);
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
0x180013830  mov     [rsp+arg_0], rcx
0x180013835  push    rbx
0x180013836  push    rbp
0x180013837  push    rsi
0x180013838  push    rdi
0x180013839  push    r12
0x18001383b  push    r14
0x18001383d  sub     rsp, 28h
0x180013841  mov     r14, cs:Feature_CLAT_PREF64_FromDNS__descriptor
0x180013848  mov     rdi, rdx
0x18001384b  mov     qword ptr [rdx], 0
0x180013852  mov     eax, [r14]
0x180013855  mov     [rdx], eax
0x180013857  and     eax, 6
0x18001385a  cmp     al, 6
0x18001385c  jz      loc_1800139ED
0x180013862  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013867  mov     ebp, eax
0x180013869  mov     dword ptr [rsp+58h+arg_0], 0
0x180013871  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013878  test    rax, rax
0x18001387b  jz      short loc_180013895
0x18001387d  lea     r8, [rsp+58h+arg_0]
0x180013882  mov     edx, 3
0x180013887  mov     ecx, 3609BD2h
0x18001388c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013891  mov     edx, eax
0x180013893  jmp     short loc_1800138A3
0x180013895  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001389c  test    rax, rax
0x18001389f  jnz     short loc_18001387D
0x1800138a1  xor     edx, edx
0x1800138a3  mov     r8d, edx
0x1800138a6  mov     eax, edx
0x1800138a8  and     r8d, 0FFFFFF3Fh
0x1800138af  and     edx, 80h
0x1800138b5  mov     ecx, r8d
0x1800138b8  mov     r12d, 40h ; '@'
0x1800138be  and     ecx, 3
0x1800138c1  and     eax, r12d
0x1800138c4  shl     ecx, 2
0x1800138c7  or      ecx, eax
0x1800138c9  shl     ecx, 2
0x1800138cc  or      ecx, edx
0x1800138ce  lea     ebx, ds:0[rcx*8]
0x1800138d5  test    r8d, r8d
0x1800138d8  jnz     short loc_1800138DF
0x1800138da  mov     eax, r12d
0x1800138dd  jmp     short loc_1800138E9
0x1800138df  xor     eax, eax
0x1800138e1  cmp     r8d, 2
0x1800138e5  cmovz   eax, r12d
0x1800138e9  or      ebx, eax
0x1800138eb  mov     ecx, 0C00h
0x1800138f0  mov     eax, ebx
0x1800138f2  and     eax, ecx
0x1800138f4  cmp     eax, ecx
0x1800138f6  jnz     short loc_1800138FD
0x1800138f8  mov     sil, 1
0x1800138fb  jmp     short loc_180013905
0x1800138fd  xor     sil, sil
0x180013900  test    r12b, bl
0x180013903  jz      short loc_180013920
0x180013905  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Core@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Core>::GetImpl(void)'::`2'::impl
0x18001390c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Core@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Core>::__private_IsEnabled(wil::ReportingKind)
0x180013911  test    sil, sil
0x180013914  jz      short loc_180013922
0x180013916  test    al, al
0x180013918  jnz     short loc_180013922
0x18001391a  btr     ebx, 0Ah
0x18001391e  jmp     short loc_180013922
0x180013920  xor     al, al
0x180013922  test    r12b, bl
0x180013925  jz      short loc_180013932
0x180013927  test    al, al
0x180013929  jz      short loc_180013932
0x18001392b  mov     esi, 1
0x180013930  jmp     short loc_180013934
0x180013932  xor     esi, esi
0x180013934  mov     eax, [rdi]
0x180013936  or      esi, ebx
0x180013938  mov     ebx, 180h
0x18001393d  cmp     dword ptr [rsp+58h+arg_0], 0
0x180013942  mov     edx, eax
0x180013944  mov     [rdi], eax
0x180013946  jz      short loc_180013980
0x180013948  test    dl, 2
0x18001394b  jnz     short loc_180013980
0x18001394d  mov     eax, esi
0x18001394f  xor     eax, edx
0x180013951  and     eax, ebx
0x180013953  xor     eax, edx
0x180013955  mov     ecx, eax
0x180013957  xor     ecx, esi
0x180013959  and     ecx, r12d
0x18001395c  xor     ecx, eax
0x18001395e  mov     eax, ecx
0x180013960  xor     eax, esi
0x180013962  and     eax, 1
0x180013965  xor     eax, ecx
0x180013967  mov     r8d, eax
0x18001396a  xor     r8d, esi
0x18001396d  and     r8d, 800h
0x180013974  xor     r8d, eax
0x180013977  or      r8d, 2
0x18001397b  mov     [rdi], r8d
0x18001397e  jmp     short loc_180013983
0x180013980  mov     r8d, edx
0x180013983  mov     r9d, edx
0x180013986  and     r9d, 4
0x18001398a  jnz     short loc_1800139A1
0x18001398c  mov     ecx, esi
0x18001398e  xor     ecx, r8d
0x180013991  and     ecx, 400h
0x180013997  xor     ecx, r8d
0x18001399a  or      ecx, 4
0x18001399d  mov     [rdi], ecx
0x18001399f  jmp     short loc_1800139A4
0x1800139a1  mov     ecx, r8d
0x1800139a4  mov     eax, edx
0x1800139a6  lock cmpxchg [r14], ecx
0x1800139ab  jnz     short loc_18001393D
0x1800139ad  test    r9d, r9d
0x1800139b0  jnz     short loc_1800139C1
0x1800139b2  mov     r8d, ebp
0x1800139b5  lea     edx, [r9+3]
0x1800139b9  mov     rcx, r14
0x1800139bc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800139c1  test    byte ptr [rdi], 2
0x1800139c4  jnz     short loc_1800139ED
0x1800139c6  mov     eax, [rdi]
0x1800139c8  xor     eax, esi
0x1800139ca  and     eax, ebx
0x1800139cc  xor     eax, [rdi]
0x1800139ce  mov     ecx, eax
0x1800139d0  xor     ecx, esi
0x1800139d2  and     ecx, r12d
0x1800139d5  xor     ecx, eax
0x1800139d7  mov     edx, ecx
0x1800139d9  xor     edx, esi
0x1800139db  and     edx, 1
0x1800139de  xor     edx, ecx
0x1800139e0  mov     eax, edx
0x1800139e2  xor     eax, esi
0x1800139e4  and     eax, 800h
0x1800139e9  xor     eax, edx
0x1800139eb  mov     [rdi], eax
0x1800139ed  mov     rax, rdi
0x1800139f0  add     rsp, 28h
0x1800139f4  pop     r14
0x1800139f6  pop     r12
0x1800139f8  pop     rdi
0x1800139f9  pop     rsi
0x1800139fa  pop     rbp
0x1800139fb  pop     rbx
0x1800139fc  retn
```
