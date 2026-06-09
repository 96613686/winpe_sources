# AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::ConvertAssetIntelligenceListToSafeArray(std::vector<AppV::Shared::AssetIntelligence::AssetIntelligenceData,std::allocator<AppV::Shared::AssetIntelligence::AssetIntelligenceData>> const &,tagSAFEARRAY * *)

- ea: `0x140022fe4`
- end: `0x140023101`
- name: `?ConvertAssetIntelligenceListToSafeArray@?$AssetIntelligenceWrapperT@VAssetIntelligenceEmptyBase@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEBV?$vector@UAssetIntelligenceData@AssetIntelligence@Shared@AppV@@V?$allocator@UAssetIntelligenceData@AssetIntelligence@Shared@AppV@@@std@@@std@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140024830`
- `0x140024b60`

## callees

- `0x140022fe4`
- `0x140023108`
- `0x1400389d0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002309e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400230df`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002309e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1400230df`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140023094`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400230ad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400230d5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140023094`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400230ad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1400230d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::ConvertAssetIntelligenceListToSafeArray(
        __int64 a1,
        __int64 *a2,
        SAFEARRAY **a3)
{
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 i; // rdi
  __int64 v9; // rsi
  SAFEARRAY *v10; // rcx
  SAFEARRAY *v12; // rcx
  _BYTE v13[8]; // [rsp+20h] [rbp-20h] BYREF
  SAFEARRAY *psa[2]; // [rsp+28h] [rbp-18h]
  int v15; // [rsp+38h] [rbp-8h]
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF

  *(_OWORD *)psa = 0;
  v15 = 0;
  v13[0] = 0;
  v16 = 0;
  v6 = AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray(
         a1,
         v13,
         0xF0F0F0F0F0F0F0F1uLL * ((a2[1] - *a2) >> 5),
         &v16);
  if ( (v6 & 0x8000000000LL) != 0 )
  {
    v7 = *a2;
    for ( i = v16; ; i += 144 )
    {
      if ( v7 == a2[1] )
      {
        SafeArrayUnaccessData(psa[0]);
        *a3 = psa[0];
        return 0x8000000000LL;
      }
      v9 = AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray(
             v5,
             v7,
             i);
      if ( (v9 & 0x8000000000LL) == 0 )
        break;
      v7 += 544;
    }
    v10 = psa[0];
    if ( psa[0] )
    {
      if ( v13[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v10 = psa[0];
      }
      SafeArrayDestroy(v10);
    }
    return v9;
  }
  else
  {
    v12 = psa[0];
    if ( psa[0] )
    {
      if ( v13[0] )
      {
        SafeArrayUnaccessData(psa[0]);
        v12 = psa[0];
      }
      SafeArrayDestroy(v12);
    }
    return v6;
  }
}

```

## disassembly

```asm
0x140022fe4  mov     [rsp-28h+arg_8], rbx
0x140022fe9  mov     [rsp-28h+arg_10], rsi
0x140022fee  mov     [rsp-28h+arg_0], rcx
0x140022ff3  push    rbp
0x140022ff4  push    rdi
0x140022ff5  push    r13
0x140022ff7  push    r14
0x140022ff9  push    r15
0x140022ffb  mov     rbp, rsp
0x140022ffe  sub     rsp, 40h
0x140023002  mov     r15, r8
0x140023005  mov     r14, rdx
0x140023008  xorps   xmm0, xmm0
0x14002300b  movdqu  xmmword ptr [rbp+psa], xmm0
0x140023010  mov     [rbp+var_8], 0
0x140023017  mov     [rbp+var_20], 0
0x14002301b  mov     [rbp+arg_0], 0
0x140023023  mov     r8, [rdx+8]
0x140023027  sub     r8, [rdx]
0x14002302a  sar     r8, 5
0x14002302e  mov     rax, 0F0F0F0F0F0F0F0F1h
0x140023038  imul    r8, rax
0x14002303c  lea     r9, [rbp+arg_0]
0x140023040  lea     rdx, [rbp+var_20]
0x140023044  call    ?CreateAssetIntelligenceSafeArray@?$AssetIntelligenceWrapperT@VAssetIntelligenceEmptyBase@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UAssetIntelligenceProperties@@@utility@appv@@IAEAPEAUAssetIntelligenceProperties@@@Z; AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray(appv::utility::safe_array_with_structs<AssetIntelligenceProperties> &,uint,AssetIntelligenceProperties * &)
0x140023049  mov     rbx, rax
0x14002304c  bt      rax, 27h ; '''
0x140023051  jnb     short loc_1400230C6
0x140023053  mov     rbx, [r14]
0x140023056  mov     rdi, [rbp+arg_0]
0x14002305a  cmp     rbx, [r14+8]
0x14002305e  jz      short loc_1400230A9
0x140023060  mov     r8, rdi
0x140023063  mov     rdx, rbx
0x140023066  call    ?WriteOneEntryInSafeArray@?$AssetIntelligenceWrapperT@VAssetIntelligenceEmptyBase@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEBUAssetIntelligenceData@AssetIntelligence@Shared@4@PEAUAssetIntelligenceProperties@@@Z; AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray(AppV::Shared::AssetIntelligence::AssetIntelligenceData const &,AssetIntelligenceProperties *)
0x14002306b  mov     rsi, rax
0x14002306e  bt      rax, 27h ; '''
0x140023073  jnb     short loc_140023085
0x140023075  add     rbx, 220h
0x14002307c  add     rdi, 90h
0x140023083  jmp     short loc_14002305A
0x140023085  mov     rcx, [rbp+psa]; psa
0x140023089  test    rcx, rcx
0x14002308c  jz      short loc_1400230A4
0x14002308e  cmp     [rbp+var_20], 0
0x140023092  jz      short loc_14002309E
0x140023094  call    cs:__imp_SafeArrayUnaccessData
0x14002309a  mov     rcx, [rbp+psa]; psa
0x14002309e  call    cs:__imp_SafeArrayDestroy
0x1400230a4  mov     rax, rsi
0x1400230a7  jmp     short loc_1400230E8
0x1400230a9  mov     rcx, [rbp+psa]; psa
0x1400230ad  call    cs:__imp_SafeArrayUnaccessData
0x1400230b3  mov     rax, [rbp+psa]
0x1400230b7  mov     [r15], rax
0x1400230ba  mov     rax, 8000000000h
0x1400230c4  jmp     short loc_1400230E8
0x1400230c6  mov     rcx, [rbp+psa]; psa
0x1400230ca  test    rcx, rcx
0x1400230cd  jz      short loc_1400230E5
0x1400230cf  cmp     [rbp+var_20], 0
0x1400230d3  jz      short loc_1400230DF
0x1400230d5  call    cs:__imp_SafeArrayUnaccessData
0x1400230db  mov     rcx, [rbp+psa]; psa
0x1400230df  call    cs:__imp_SafeArrayDestroy
0x1400230e5  mov     rax, rbx
0x1400230e8  lea     r11, [rsp+40h+var_s0]
0x1400230ed  mov     rbx, [r11+38h]
0x1400230f1  mov     rsi, [r11+40h]
0x1400230f5  mov     rsp, r11
0x1400230f8  pop     r15
0x1400230fa  pop     r14
0x1400230fc  pop     r13
0x1400230fe  pop     rdi
0x1400230ff  pop     rbp
0x140023100  retn
```
