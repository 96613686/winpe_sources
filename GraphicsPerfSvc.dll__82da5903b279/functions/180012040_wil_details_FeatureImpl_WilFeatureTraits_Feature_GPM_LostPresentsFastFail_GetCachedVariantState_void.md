# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetCachedVariantState(void)

- ea: `0x180012040`
- end: `0x180012199`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LostPresentsFastFail@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c84`
- `0x180013070`
- `0x180013344`

## callees

- `0x180006744`
- `0x180009a60`
- `0x180012040`
- `0x1800132cc`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LostPresentsFastFail>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  unsigned int v4; // esi
  unsigned int v5; // edx
  unsigned int FeatureVariant; // eax
  int v7; // r9d
  int v8; // r8d
  unsigned int v9; // eax
  int v10; // r8d
  FEATURE_CHANGE_TIME v11; // r10d
  __int64 v12; // r9
  signed __int64 v13; // rax
  signed __int64 v14; // r11
  int v15; // eax
  int v16; // eax
  bool v17; // zf
  int *v19; // [rsp+28h] [rbp-20h]
  wil::details *v20; // [rsp+50h] [rbp+8h] BYREF
  FEATURE_CHANGE_TIME v21; // [rsp+58h] [rbp+10h] BYREF
  int v22; // [rsp+60h] [rbp+18h] BYREF

  v20 = a1;
  v3 = *Feature_GPM_LostPresentsFastFail__descriptor;
  *a2 = *Feature_GPM_LostPresentsFastFail__descriptor;
  if ( (v3 & 0xC) == 0xC )
    return a2;
  v22 = 0;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v21 = FEATURE_CHANGE_TIME_READ;
  FeatureVariant = wil::details::WilApi_GetFeatureVariant(
                     (wil::details *)0x1C5B2AA,
                     v5,
                     (enum FEATURE_CHANGE_TIME)&v21,
                     (unsigned int *)&v20,
                     &v22,
                     v19);
  v7 = FeatureVariant & 0x100;
  v8 = ((_DWORD)v20 != 0 ? 0x400 : 0) | (16 * (FeatureVariant & 0x80));
  v9 = FeatureVariant & 0xFFFFFE7F;
  if ( v9 )
  {
    v11 = v21;
    v10 = ((v9 & 0x3F) << 12) ^ v8;
    if ( v7 )
      goto LABEL_6;
  }
  else
  {
    v10 = v8 | 0x1000;
  }
  v11 = 80;
LABEL_6:
  v12 = *a2;
  v13 = *a2;
  v14 = *a2;
  while ( 1 )
  {
    *(_DWORD *)a2 = v12;
    *((_DWORD *)a2 + 1) = HIDWORD(v13);
    if ( (v12 & 8) != 0 )
    {
      v16 = v12;
    }
    else
    {
      v15 = v22;
      *((_DWORD *)a2 + 1) = v11;
      v16 = ((v15 != 0 ? 8 : 0) | (v12 ^ (v10 ^ v12) & 0x3F000) & 0xFFFFFFF7)
          ^ ((unsigned __int16)v10
           ^ ((v15 != 0 ? 8 : 0)
            | ((unsigned __int16)v12 ^ ((unsigned __int16)v10 ^ (unsigned __int16)v12) & 0xF000) & 0xFFF7))
          & 0x800;
      *(_DWORD *)a2 = v16;
    }
    if ( (v12 & 4) == 0 )
      *(_DWORD *)a2 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)v10) & 0x400 | 4;
    v13 = _InterlockedCompareExchange64(Feature_GPM_LostPresentsFastFail__descriptor, *a2, v14);
    v17 = v14 == v13;
    v14 = v13;
    if ( v17 )
      break;
    LODWORD(v12) = v13;
  }
  if ( (v12 & 4) == 0 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      &wil::details::g_enabledStateManager,
      Feature_GPM_LostPresentsFastFail__descriptor,
      1,
      v4);
  return a2;
}

```

## disassembly

```asm
0x180012040  mov     [rsp+arg_0], rcx
0x180012045  push    rbx
0x180012046  push    rsi
0x180012047  push    rdi
0x180012048  sub     rsp, 30h
0x18001204c  mov     rdi, cs:Feature_GPM_LostPresentsFastFail__descriptor
0x180012053  mov     rbx, rdx
0x180012056  mov     rax, [rdi]
0x180012059  mov     [rdx], rax
0x18001205c  and     eax, 0Ch
0x18001205f  cmp     al, 0Ch
0x180012061  jz      loc_18001218E
0x180012067  mov     [rsp+48h+arg_10], 0
0x18001206f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012074  mov     esi, eax
0x180012076  mov     dword ptr [rsp+48h+arg_0], 0
0x18001207e  lea     rax, [rsp+48h+arg_10]
0x180012083  mov     [rsp+48h+arg_8], 0
0x18001208b  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x180012090  mov     [rsp+48h+var_28], rax; int *
0x180012095  lea     r8, [rsp+48h+arg_8]; enum FEATURE_CHANGE_TIME
0x18001209a  mov     ecx, 1C5B2AAh; this
0x18001209f  call    ?WilApi_GetFeatureVariant@details@wil@@YAIIW4FEATURE_CHANGE_TIME@@PEAIPEAH2@Z; wil::details::WilApi_GetFeatureVariant(uint,FEATURE_CHANGE_TIME,uint *,int *,int *)
0x1800120a4  mov     ecx, dword ptr [rsp+48h+arg_0]
0x1800120a8  mov     r9d, eax
0x1800120ab  and     r9d, 100h
0x1800120b2  mov     r8d, eax
0x1800120b5  neg     ecx
0x1800120b7  sbb     edx, edx
0x1800120b9  and     r8d, 80h
0x1800120c0  shl     r8d, 4
0x1800120c4  and     edx, 400h
0x1800120ca  or      r8d, edx
0x1800120cd  and     eax, 0FFFFFE7Fh
0x1800120d2  jnz     short loc_1800120DB
0x1800120d4  bts     r8d, 0Ch
0x1800120d9  jmp     short loc_1800120EE
0x1800120db  mov     r10d, [rsp+48h+arg_8]
0x1800120e0  and     eax, 3Fh
0x1800120e3  shl     eax, 0Ch
0x1800120e6  xor     r8d, eax
0x1800120e9  test    r9d, r9d
0x1800120ec  jnz     short loc_1800120F4
0x1800120ee  mov     r10d, 50h ; 'P'
0x1800120f4  mov     r9, [rbx]
0x1800120f7  mov     rax, r9
0x1800120fa  mov     r11, r9
0x1800120fd  shr     rax, 20h
0x180012101  mov     [rbx], r9d
0x180012104  mov     [rbx+4], eax
0x180012107  test    r9b, 8
0x18001210b  jnz     short loc_180012140
0x18001210d  mov     eax, [rsp+48h+arg_10]
0x180012111  mov     edx, r9d
0x180012114  xor     edx, r8d
0x180012117  mov     [rbx+4], r10d
0x18001211b  and     edx, 3F000h
0x180012121  xor     edx, r9d
0x180012124  neg     eax
0x180012126  sbb     ecx, ecx
0x180012128  and     edx, 0FFFFFFF7h
0x18001212b  and     ecx, 8
0x18001212e  or      edx, ecx
0x180012130  mov     eax, edx
0x180012132  xor     eax, r8d
0x180012135  and     eax, 800h
0x18001213a  xor     eax, edx
0x18001213c  mov     [rbx], eax
0x18001213e  jmp     short loc_180012143
0x180012140  mov     eax, r9d
0x180012143  test    r9b, 4
0x180012147  jnz     short loc_18001215B
0x180012149  mov     ecx, r8d
0x18001214c  xor     ecx, eax
0x18001214e  and     ecx, 400h
0x180012154  xor     ecx, eax
0x180012156  or      ecx, 4
0x180012159  mov     [rbx], ecx
0x18001215b  mov     rcx, [rbx]
0x18001215e  mov     rax, r11
0x180012161  lock cmpxchg [rdi], rcx
0x180012166  mov     r11, rax
0x180012169  jz      short loc_180012170
0x18001216b  mov     r9d, eax
0x18001216e  jmp     short loc_1800120FD
0x180012170  test    r9b, 4
0x180012174  jnz     short loc_18001218E
0x180012176  mov     r9d, esi
0x180012179  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012180  mov     r8d, 1
0x180012186  mov     rdx, rdi
0x180012189  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001218e  mov     rax, rbx
0x180012191  add     rsp, 30h
0x180012195  pop     rdi
0x180012196  pop     rsi
0x180012197  pop     rbx
0x180012198  retn
```
