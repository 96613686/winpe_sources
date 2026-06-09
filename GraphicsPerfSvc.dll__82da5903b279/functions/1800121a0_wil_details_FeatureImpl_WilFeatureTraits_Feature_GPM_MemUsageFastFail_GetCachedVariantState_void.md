# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetCachedVariantState(void)

- ea: `0x1800121a0`
- end: `0x1800122f9`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MemUsageFastFail@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `345`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012c84`
- `0x18001313c`
- `0x18001338c`

## callees

- `0x180006744`
- `0x180009a60`
- `0x1800121a0`
- `0x1800132cc`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MemUsageFastFail>::GetCachedVariantState(
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
  enum FEATURE_CHANGE_TIME v11; // r10d
  __int64 v12; // r9
  signed __int64 v13; // rax
  signed __int64 v14; // r11
  int v15; // eax
  int v16; // eax
  bool v17; // zf
  int *v19; // [rsp+28h] [rbp-20h]
  wil::details *v20; // [rsp+50h] [rbp+8h] BYREF
  enum FEATURE_CHANGE_TIME v21; // [rsp+58h] [rbp+10h] BYREF
  int v22; // [rsp+60h] [rbp+18h] BYREF

  v20 = a1;
  v3 = *Feature_GPM_MemUsageFastFail__descriptor;
  *a2 = *Feature_GPM_MemUsageFastFail__descriptor;
  if ( (v3 & 0xC) == 0xC )
    return a2;
  v22 = 0;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  LODWORD(v20) = 0;
  v21 = FEATURE_CHANGE_TIME_READ;
  FeatureVariant = wil::details::WilApi_GetFeatureVariant(
                     (wil::details *)0x1DDF8BB,
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
  v11 = 18000000;
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
    v13 = _InterlockedCompareExchange64(Feature_GPM_MemUsageFastFail__descriptor, *a2, v14);
    v17 = v14 == v13;
    v14 = v13;
    if ( v17 )
      break;
    LODWORD(v12) = v13;
  }
  if ( (v12 & 4) == 0 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      &wil::details::g_enabledStateManager,
      Feature_GPM_MemUsageFastFail__descriptor,
      1,
      v4);
  return a2;
}

```

## disassembly

```asm
0x1800121a0  mov     [rsp+arg_0], rcx
0x1800121a5  push    rbx
0x1800121a6  push    rsi
0x1800121a7  push    rdi
0x1800121a8  sub     rsp, 30h
0x1800121ac  mov     rdi, cs:Feature_GPM_MemUsageFastFail__descriptor
0x1800121b3  mov     rbx, rdx
0x1800121b6  mov     rax, [rdi]
0x1800121b9  mov     [rdx], rax
0x1800121bc  and     eax, 0Ch
0x1800121bf  cmp     al, 0Ch
0x1800121c1  jz      loc_1800122EE
0x1800121c7  mov     [rsp+48h+arg_10], 0
0x1800121cf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800121d4  mov     esi, eax
0x1800121d6  mov     dword ptr [rsp+48h+arg_0], 0
0x1800121de  lea     rax, [rsp+48h+arg_10]
0x1800121e3  mov     [rsp+48h+arg_8], 0
0x1800121eb  lea     r9, [rsp+48h+arg_0]; unsigned int *
0x1800121f0  mov     [rsp+48h+var_28], rax; int *
0x1800121f5  lea     r8, [rsp+48h+arg_8]; enum FEATURE_CHANGE_TIME
0x1800121fa  mov     ecx, 1DDF8BBh; this
0x1800121ff  call    ?WilApi_GetFeatureVariant@details@wil@@YAIIW4FEATURE_CHANGE_TIME@@PEAIPEAH2@Z; wil::details::WilApi_GetFeatureVariant(uint,FEATURE_CHANGE_TIME,uint *,int *,int *)
0x180012204  mov     ecx, dword ptr [rsp+48h+arg_0]
0x180012208  mov     r9d, eax
0x18001220b  and     r9d, 100h
0x180012212  mov     r8d, eax
0x180012215  neg     ecx
0x180012217  sbb     edx, edx
0x180012219  and     r8d, 80h
0x180012220  shl     r8d, 4
0x180012224  and     edx, 400h
0x18001222a  or      r8d, edx
0x18001222d  and     eax, 0FFFFFE7Fh
0x180012232  jnz     short loc_18001223B
0x180012234  bts     r8d, 0Ch
0x180012239  jmp     short loc_18001224E
0x18001223b  mov     r10d, [rsp+48h+arg_8]
0x180012240  and     eax, 3Fh
0x180012243  shl     eax, 0Ch
0x180012246  xor     r8d, eax
0x180012249  test    r9d, r9d
0x18001224c  jnz     short loc_180012254
0x18001224e  mov     r10d, 112A880h
0x180012254  mov     r9, [rbx]
0x180012257  mov     rax, r9
0x18001225a  mov     r11, r9
0x18001225d  shr     rax, 20h
0x180012261  mov     [rbx], r9d
0x180012264  mov     [rbx+4], eax
0x180012267  test    r9b, 8
0x18001226b  jnz     short loc_1800122A0
0x18001226d  mov     eax, [rsp+48h+arg_10]
0x180012271  mov     edx, r9d
0x180012274  xor     edx, r8d
0x180012277  mov     [rbx+4], r10d
0x18001227b  and     edx, 3F000h
0x180012281  xor     edx, r9d
0x180012284  neg     eax
0x180012286  sbb     ecx, ecx
0x180012288  and     edx, 0FFFFFFF7h
0x18001228b  and     ecx, 8
0x18001228e  or      edx, ecx
0x180012290  mov     eax, edx
0x180012292  xor     eax, r8d
0x180012295  and     eax, 800h
0x18001229a  xor     eax, edx
0x18001229c  mov     [rbx], eax
0x18001229e  jmp     short loc_1800122A3
0x1800122a0  mov     eax, r9d
0x1800122a3  test    r9b, 4
0x1800122a7  jnz     short loc_1800122BB
0x1800122a9  mov     ecx, r8d
0x1800122ac  xor     ecx, eax
0x1800122ae  and     ecx, 400h
0x1800122b4  xor     ecx, eax
0x1800122b6  or      ecx, 4
0x1800122b9  mov     [rbx], ecx
0x1800122bb  mov     rcx, [rbx]
0x1800122be  mov     rax, r11
0x1800122c1  lock cmpxchg [rdi], rcx
0x1800122c6  mov     r11, rax
0x1800122c9  jz      short loc_1800122D0
0x1800122cb  mov     r9d, eax
0x1800122ce  jmp     short loc_18001225D
0x1800122d0  test    r9b, 4
0x1800122d4  jnz     short loc_1800122EE
0x1800122d6  mov     r9d, esi
0x1800122d9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800122e0  mov     r8d, 1
0x1800122e6  mov     rdx, rdi
0x1800122e9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800122ee  mov     rax, rbx
0x1800122f1  add     rsp, 30h
0x1800122f5  pop     rdi
0x1800122f6  pop     rsi
0x1800122f7  pop     rbx
0x1800122f8  retn
```
