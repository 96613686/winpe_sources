# CEndpointCharacteristics::IsEffectPackConfigurationApplicableToEndpoint(std::shared_ptr<EffectPackConfiguration const> &,bool *)

- ea: `0x1800bc900`
- end: `0x1800bce6d`
- name: `?IsEffectPackConfigurationApplicableToEndpoint@CEndpointCharacteristics@@AEAAJAEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@PEA_N@Z`
- size: `1389`
- prototype: `__int64 __fastcall(bool *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18014010c`

## callees

- `0x18000accc`
- `0x18000af70`
- `0x1800126bc`
- `0x180018198`
- `0x1800423cc`
- `0x180071780`
- `0x1800bc900`
- `0x1800bce74`
- `0x1800bce94`
- `0x1800bceb4`
- `0x1800bcf60`
- `0x18013d004`
- `0x18013dd78`
- `0x18013e0f4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bca3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bca63`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bca3f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bca63`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcaea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcb50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcdb9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bce1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcaea`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcb50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bcdb9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bce1b`

## string_xrefs

- `0x1800bc9da`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CEndpointCharacteristics::IsEffectPackConfigurationApplicableToEndpoint(
        bool *a1,
        int *a2,
        _BYTE *a3)
{
  _lambda_f3b092209076b90048129f7b4270089e_ *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rax
  char v12; // di
  LPCWCH *v13; // rsi
  LPCWCH *v14; // r15
  _QWORD *v15; // r8
  _QWORD *i; // rcx
  __int64 v17; // rax
  unsigned __int64 v18; // rdx
  struct IMMDevice *v19; // rbx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rdi
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // esi
  __int64 *v24; // rdi
  __int64 *v25; // r15
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // r8
  char v29; // bl
  PROPVARIANT v30; // rbx
  PROPVARIANT v32; // rbx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  PROPVARIANT v36[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  _BYTE v38[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[320]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]
  int v41; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v42; // [rsp+1F0h] [rbp+F0h] BYREF
  struct IMMDevice *v43; // [rsp+1F8h] [rbp+F8h] BYREF

  *a3 = 0;
  v41 = 0;
  v6 = _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(
         (_lambda_f3b092209076b90048129f7b4270089e_ *)pvar,
         a1,
         a2,
         (bool *)&v41);
  wil::scope_exit__lambda_13a0b1290610caf0dece1d9cd3ee83cf___(v38, v6);
  v41 = 1;
  if ( *((_DWORD *)a1 + 16) != 3 )
  {
    v41 = 4;
    if ( !*((_DWORD *)a1 + 110) || *((_DWORD *)a1 + 111) )
      goto LABEL_7;
    v8 = *(_QWORD *)(*(_QWORD *)v7 + 1936LL) - PKEY_FX_EffectPack_Schema_Internal_V1;
    if ( !v8 )
      v8 = *(_QWORD *)(*(_QWORD *)v7 + 1944LL) - *((_QWORD *)&PKEY_FX_EffectPack_Schema_Internal_V1 + 1);
    if ( !v8 )
    {
LABEL_7:
      v41 = 7;
      v9 = *((int *)a1 + 59);
      if ( v9 >= 2 )
      {
        v10 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x861,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCase);
LABEL_60:
        wil::details::lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea___::_lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea___(v38);
        return v10;
      }
      v11 = *(_QWORD *)a2;
      if ( *(_BYTE *)(v9 + *(_QWORD *)a2 + 1915) )
      {
        v12 = 0;
        v41 = 2;
        v13 = *(LPCWCH **)(v11 + 1864);
        v14 = *(LPCWCH **)(v11 + 1872);
        while ( v13 != v14 )
        {
          if ( *((_QWORD *)a1 + 52)
            && (CompareStringOrdinal(*v13, -1, L"*", -1, 1) == 2
             || CompareStringOrdinal(*v13, -1, *((LPCWCH *)a1 + 52), -1, 1) == 2) )
          {
            v12 = 1;
            break;
          }
          ++v13;
        }
        if ( *(_BYTE *)(*(_QWORD *)a2 + 1912LL) )
        {
          v41 = 6;
          *(_OWORD *)pvar = 0;
          v35 = 0;
          if ( (*(int (__fastcall **)(_QWORD, void *, PROPVARIANT *))(**((_QWORD **)a1 + 9) + 40LL))(
                 *((_QWORD *)a1 + 9),
                 &PKEY_Endpoint_IsBluetooth,
                 pvar) >= 0
            && LOWORD(pvar[0]) == 11
            && LOWORD(pvar[1]) )
          {
            v12 = 1;
          }
          PropVariantClear(pvar);
        }
        if ( *(_BYTE *)(*(_QWORD *)a2 + 1913LL) )
        {
          v41 = 5;
          *(_OWORD *)pvar = 0;
          v35 = 0;
          if ( (*(int (__fastcall **)(_QWORD, void *, PROPVARIANT *))(**((_QWORD **)a1 + 9) + 40LL))(
                 *((_QWORD *)a1 + 9),
                 &PKEY_Endpoint_IsUSB,
                 pvar) >= 0
            && LOWORD(pvar[0]) == 11
            && LOWORD(pvar[1]) )
          {
            v12 = 1;
          }
          PropVariantClear(pvar);
        }
        if ( v12 )
        {
          v41 = 3;
          v15 = *(_QWORD **)a2;
          for ( i = *(_QWORD **)(*(_QWORD *)a2 + 1824LL); ; i += 2 )
          {
            if ( i == (_QWORD *)v15[229] )
              goto LABEL_65;
            v17 = *i - *((_QWORD *)a1 + 53);
            if ( *i == *((_QWORD *)a1 + 53) )
              v17 = i[1] - *((_QWORD *)a1 + 54);
            if ( !v17 )
              break;
            v18 = *i - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
            if ( *i == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
              v18 = i[1] - _mm_srli_si128((__m128i)GUID_00000000_0000_0000_0000_000000000000, 8).m128i_u64[0];
            if ( !v18 )
              break;
          }
          v41 = 8;
          if ( (v15[237] - v15[236]) / 40LL )
          {
            v43 = 0;
            v42 = 0;
            *(_OWORD *)v36 = 0;
            v37 = 0;
            std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(pvar);
            wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v43);
            CEndpointCharacteristics::GetPnpDevnodeFromMMDevice((CEndpointCharacteristics *)a1, &v43);
            v19 = v43;
            if ( v43 )
            {
              OpenPropertyStore = v43->lpVtbl->OpenPropertyStore;
              v21 = v42;
              v42 = 0;
              if ( v21 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(v19, 0, &v42) >= 0
                && (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v42 + 40LL))(
                     v42,
                     &DEVPKEY_Device_HardwareIds,
                     v36) >= 0
                && LOWORD(v36[0]) == 4127 )
              {
                v22 = (unsigned int)v36[1];
                if ( LODWORD(v36[1]) )
                {
                  v23 = 0;
LABEL_48:
                  if ( v23 < v22 )
                  {
                    v24 = *(__int64 **)(*(_QWORD *)a2 + 1888LL);
                    v25 = *(__int64 **)(*(_QWORD *)a2 + 1896LL);
                    while ( 1 )
                    {
                      if ( v24 == v25 )
                      {
                        ++v23;
                        v22 = (unsigned int)v36[1];
                        goto LABEL_48;
                      }
                      v26 = *(_QWORD *)(v37 + 8LL * v23);
                      v27 = -1;
                      do
                        ++v27;
                      while ( *(_WORD *)(v26 + 2 * v27) );
                      if ( *v24 )
                      {
                        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(
                          (unsigned int)v39,
                          v26,
                          v26 + 2 * v27,
                          (_DWORD)v24 + 8,
                          *v24,
                          *(_DWORD *)(*v24 + 40),
                          *(_DWORD *)(*v24 + 32),
                          16);
                        LOBYTE(v28) = 1;
                        v29 = std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                                v39,
                                0,
                                v28);
                        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::~_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(v39);
                        if ( v29 )
                          break;
                      }
                      v24 += 5;
                    }
                    v30 = pvar[0];
                    if ( pvar[0] )
                    {
                      std::_Destroy_range<std::allocator<std::wstring>>(pvar[0]);
                      std::_Deallocate<16>(v30, (v35 - (_QWORD)v30) & 0xFFFFFFFFFFFFFFE0uLL);
                    }
                    PropVariantClear(v36);
                    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
                    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
                    v10 = 0;
                    goto LABEL_60;
                  }
                }
              }
            }
            v32 = pvar[0];
            if ( pvar[0] )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(pvar[0]);
              std::_Deallocate<16>(v32, (v35 - (_QWORD)v32) & 0xFFFFFFFFFFFFFFE0uLL);
            }
            PropVariantClear(v36);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v42);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
          }
          v41 = 0;
          *a3 = 1;
        }
      }
    }
  }
LABEL_65:
  wil::details::lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea___::_lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea___(v38);
  return 0;
}

```

## disassembly

```asm
0x1800bc900  mov     [rsp-8+arg_8], rbx
0x1800bc905  push    rbp
0x1800bc906  push    rsi
0x1800bc907  push    rdi
0x1800bc908  push    r12
0x1800bc90a  push    r13
0x1800bc90c  push    r14
0x1800bc90e  push    r15
0x1800bc910  lea     rbp, [rsp-0A0h]
0x1800bc918  sub     rsp, 1A0h
0x1800bc91f  mov     r12, r8
0x1800bc922  mov     r14, rdx
0x1800bc925  mov     rbx, rcx
0x1800bc928  xor     r13d, r13d
0x1800bc92b  mov     [r8], r13b
0x1800bc92e  mov     [rbp+0D0h+arg_0], r13d
0x1800bc935  lea     r9, [rbp+0D0h+arg_0]; bool *
0x1800bc93c  mov     r8, rdx; int *
0x1800bc93f  mov     rdx, rcx; bool *
0x1800bc942  lea     rcx, [rsp+1D0h+pvar]; this
0x1800bc947  call    ??0_lambda_f3b092209076b90048129f7b4270089e_@@QEAA@AEA_NAEBH0@Z; _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(bool &,int const &,bool &)
0x1800bc94c  mov     rdx, rax
0x1800bc94f  lea     rcx, [rsp+1D0h+var_160]
0x1800bc954  call    wil__scope_exit__lambda_13a0b1290610caf0dece1d9cd3ee83cf___
0x1800bc959  nop
0x1800bc95a  lea     edx, [r13+1]
0x1800bc95e  mov     [rbp+0D0h+arg_0], edx
0x1800bc964  cmp     dword ptr [rbx+40h], 3
0x1800bc968  jz      loc_1800BCE46
0x1800bc96e  mov     [rbp+0D0h+arg_0], 4
0x1800bc978  cmp     [rbx+1B8h], r13d
0x1800bc97f  jz      short loc_1800BC9B4
0x1800bc981  cmp     [rbx+1BCh], r13d
0x1800bc988  jnz     short loc_1800BC9B4
0x1800bc98a  mov     rcx, [r8]
0x1800bc98d  mov     rax, [rcx+790h]
0x1800bc994  sub     rax, qword ptr cs:PKEY_FX_EffectPack_Schema_Internal_V1
0x1800bc99b  jnz     short loc_1800BC9AB
0x1800bc99d  mov     rax, [rcx+798h]
0x1800bc9a4  sub     rax, qword ptr cs:PKEY_FX_EffectPack_Schema_Internal_V1+8
0x1800bc9ab  test    rax, rax
0x1800bc9ae  jnz     loc_1800BCE46
0x1800bc9b4  mov     [rbp+0D0h+arg_0], 7
0x1800bc9be  movsxd  rcx, dword ptr [rbx+0ECh]
0x1800bc9c5  cmp     rcx, 2
0x1800bc9c9  jb      short loc_1800BC9F0
0x1800bc9cb  mov     rcx, [rbp+0D8h]; this
0x1800bc9d2  mov     ebx, 8000FFFFh
0x1800bc9d7  mov     r9d, ebx; char *
0x1800bc9da  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bc9e1  mov     edx, 861h; void *
0x1800bc9e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc9eb  jmp     loc_1800BCDDC
0x1800bc9f0  mov     rax, [r14]
0x1800bc9f3  cmp     [rcx+rax+77Bh], r13b
0x1800bc9fb  jz      loc_1800BCE46
0x1800bca01  mov     dil, r13b
0x1800bca04  mov     [rbp+0D0h+arg_0], 2
0x1800bca0e  mov     rsi, [rax+748h]
0x1800bca15  mov     r15, [rax+750h]
0x1800bca1c  cmp     rsi, r15
0x1800bca1f  jz      short loc_1800BCA84
0x1800bca21  cmp     [rbx+1A0h], r13
0x1800bca28  jz      short loc_1800BCA73
0x1800bca2a  mov     [rsp+1D0h+bIgnoreCase], edx; bIgnoreCase
0x1800bca2e  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bca32  lea     r8, asc_180196398; "*"
0x1800bca39  or      edx, r9d; cchCount1
0x1800bca3c  mov     rcx, [rsi]; lpString1
0x1800bca3f  call    cs:__imp_CompareStringOrdinal
0x1800bca45  cmp     eax, 2
0x1800bca48  jz      short loc_1800BCA79
0x1800bca4a  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x1800bca52  or      r9d, 0FFFFFFFFh; cchCount2
0x1800bca56  mov     r8, [rbx+1A0h]; lpString2
0x1800bca5d  or      edx, r9d; cchCount1
0x1800bca60  mov     rcx, [rsi]; lpString1
0x1800bca63  call    cs:__imp_CompareStringOrdinal
0x1800bca69  cmp     eax, 2
0x1800bca6c  jz      short loc_1800BCA79
0x1800bca6e  mov     edx, 1
0x1800bca73  add     rsi, 8
0x1800bca77  jmp     short loc_1800BCA1C
0x1800bca79  mov     r15d, 1
0x1800bca7f  mov     dil, r15b
0x1800bca82  jmp     short loc_1800BCA8A
0x1800bca84  mov     r15d, 1
0x1800bca8a  mov     rax, [r14]
0x1800bca8d  cmp     [rax+778h], r13b
0x1800bca94  jz      short loc_1800BCAF0
0x1800bca96  mov     [rbp+0D0h+arg_0], 6
0x1800bcaa0  xorps   xmm0, xmm0
0x1800bcaa3  xor     eax, eax
0x1800bcaa5  movups  xmmword ptr [rsp+1D0h+pvar], xmm0
0x1800bcaaa  mov     [rsp+1D0h+var_180], rax
0x1800bcaaf  mov     rcx, [rbx+48h]
0x1800bcab3  mov     rax, [rcx]
0x1800bcab6  lea     r8, [rsp+1D0h+pvar]
0x1800bcabb  lea     rdx, PKEY_Endpoint_IsBluetooth
0x1800bcac2  mov     rax, [rax+28h]
0x1800bcac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcacb  test    eax, eax
0x1800bcacd  js      short loc_1800BCAE5
0x1800bcacf  cmp     word ptr [rsp+1D0h+pvar], 0Bh
0x1800bcad5  jnz     short loc_1800BCAE5
0x1800bcad7  movzx   edi, dil
0x1800bcadb  cmp     word ptr [rsp+1D0h+pvar+8], r13w
0x1800bcae1  cmovnz  edi, r15d
0x1800bcae5  lea     rcx, [rsp+1D0h+pvar]; pvar
0x1800bcaea  call    cs:__imp_PropVariantClear
0x1800bcaf0  mov     rax, [r14]
0x1800bcaf3  cmp     [rax+779h], r13b
0x1800bcafa  jz      short loc_1800BCB56
0x1800bcafc  mov     [rbp+0D0h+arg_0], 5
0x1800bcb06  xorps   xmm0, xmm0
0x1800bcb09  xor     eax, eax
0x1800bcb0b  movups  xmmword ptr [rsp+1D0h+pvar], xmm0
0x1800bcb10  mov     [rsp+1D0h+var_180], rax
0x1800bcb15  mov     rcx, [rbx+48h]
0x1800bcb19  mov     rax, [rcx]
0x1800bcb1c  lea     r8, [rsp+1D0h+pvar]
0x1800bcb21  lea     rdx, PKEY_Endpoint_IsUSB
0x1800bcb28  mov     rax, [rax+28h]
0x1800bcb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcb31  test    eax, eax
0x1800bcb33  js      short loc_1800BCB4B
0x1800bcb35  cmp     word ptr [rsp+1D0h+pvar], 0Bh
0x1800bcb3b  jnz     short loc_1800BCB4B
0x1800bcb3d  movzx   edi, dil
0x1800bcb41  cmp     word ptr [rsp+1D0h+pvar+8], r13w
0x1800bcb47  cmovnz  edi, r15d
0x1800bcb4b  lea     rcx, [rsp+1D0h+pvar]; pvar
0x1800bcb50  call    cs:__imp_PropVariantClear
0x1800bcb56  test    dil, dil
0x1800bcb59  jz      loc_1800BCE46
0x1800bcb5f  mov     [rbp+0D0h+arg_0], 3
0x1800bcb69  mov     r8, [r14]
0x1800bcb6c  mov     rcx, [r8+720h]
0x1800bcb73  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bcb7a  cmp     rcx, [r8+728h]
0x1800bcb81  jz      loc_1800BCE46
0x1800bcb87  mov     rax, [rcx]
0x1800bcb8a  sub     rax, [rbx+1A8h]
0x1800bcb91  jnz     short loc_1800BCB9E
0x1800bcb93  mov     rax, [rcx+8]
0x1800bcb97  sub     rax, [rbx+1B0h]
0x1800bcb9e  test    rax, rax
0x1800bcba1  jz      short loc_1800BCBD0
0x1800bcba3  mov     rdx, [rcx]
0x1800bcba6  movq    rax, xmm1
0x1800bcbab  sub     rdx, rax
0x1800bcbae  jnz     short loc_1800BCBC5
0x1800bcbb0  mov     rdx, [rcx+8]
0x1800bcbb4  movdqa  xmm0, xmm1
0x1800bcbb8  psrldq  xmm0, 8
0x1800bcbbd  movq    rax, xmm0
0x1800bcbc2  sub     rdx, rax
0x1800bcbc5  test    rdx, rdx
0x1800bcbc8  jz      short loc_1800BCBD0
0x1800bcbca  add     rcx, 10h
0x1800bcbce  jmp     short loc_1800BCB7A
0x1800bcbd0  mov     [rbp+0D0h+arg_0], 8
0x1800bcbda  mov     rcx, [r8+768h]
0x1800bcbe1  sub     rcx, [r8+760h]
0x1800bcbe8  mov     rax, 6666666666666667h
0x1800bcbf2  imul    rcx
0x1800bcbf5  sar     rdx, 4
0x1800bcbf9  mov     rax, rdx
0x1800bcbfc  shr     rax, 3Fh
0x1800bcc00  add     rdx, rax
0x1800bcc03  jz      loc_1800BCE3B
0x1800bcc09  mov     [rbp+0D0h+arg_18], r13
0x1800bcc10  mov     [rbp+0D0h+arg_10], r13
0x1800bcc17  xorps   xmm0, xmm0
0x1800bcc1a  xor     eax, eax
0x1800bcc1c  movups  xmmword ptr [rsp+1D0h+var_178], xmm0
0x1800bcc21  mov     [rsp+1D0h+var_168], rax
0x1800bcc26  lea     rcx, [rsp+1D0h+pvar]; void *
0x1800bcc2b  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x1800bcc30  nop
0x1800bcc31  lea     rcx, [rbp+0D0h+arg_18]
0x1800bcc38  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800bcc3d  lea     rdx, [rbp+0D0h+arg_18]; struct IMMDevice **
0x1800bcc44  mov     rcx, rbx; this
0x1800bcc47  call    ?GetPnpDevnodeFromMMDevice@CEndpointCharacteristics@@AEAAJPEAPEAUIMMDevice@@@Z; CEndpointCharacteristics::GetPnpDevnodeFromMMDevice(IMMDevice * *)
0x1800bcc4c  mov     rbx, [rbp+0D0h+arg_18]
0x1800bcc53  test    rbx, rbx
0x1800bcc56  jz      loc_1800BCDEA
0x1800bcc5c  mov     rax, [rbx]
0x1800bcc5f  mov     rdi, [rax+20h]
0x1800bcc63  mov     rcx, [rbp+0D0h+arg_10]
0x1800bcc6a  mov     [rbp+0D0h+arg_10], r13
0x1800bcc71  test    rcx, rcx
0x1800bcc74  jz      short loc_1800BCC83
0x1800bcc76  mov     rdx, [rcx]
0x1800bcc79  mov     rax, [rdx+10h]
0x1800bcc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc82  nop
0x1800bcc83  lea     r8, [rbp+0D0h+arg_10]
0x1800bcc8a  xor     edx, edx
0x1800bcc8c  mov     rcx, rbx
0x1800bcc8f  mov     rax, rdi
0x1800bcc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcc97  test    eax, eax
0x1800bcc99  js      loc_1800BCDEA
0x1800bcc9f  mov     rcx, [rbp+0D0h+arg_10]
0x1800bcca6  mov     rax, [rcx]
0x1800bcca9  lea     r8, [rsp+1D0h+var_178]
0x1800bccae  lea     rdx, DEVPKEY_Device_HardwareIds
0x1800bccb5  mov     rax, [rax+28h]
0x1800bccb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bccbe  test    eax, eax
0x1800bccc0  js      loc_1800BCDEA
0x1800bccc6  mov     eax, 101Fh
0x1800bcccb  cmp     word ptr [rsp+1D0h+var_178], ax
0x1800bccd0  jnz     loc_1800BCDEA
0x1800bccd6  mov     rax, [rsp+1D0h+var_178+8]
0x1800bccdb  test    eax, eax
0x1800bccdd  jz      loc_1800BCDEA
0x1800bcce3  mov     esi, r13d
0x1800bcce6  cmp     esi, eax
0x1800bcce8  jnb     loc_1800BCDEA
0x1800bccee  mov     rax, [r14]
0x1800bccf1  mov     rdi, [rax+760h]
0x1800bccf8  mov     r15, [rax+768h]
0x1800bccff  cmp     rdi, r15
0x1800bcd02  jz      short loc_1800BCD75
0x1800bcd04  mov     ecx, esi
0x1800bcd06  mov     rax, [rsp+1D0h+var_168]
0x1800bcd0b  mov     rdx, [rax+rcx*8]
0x1800bcd0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bcd13  inc     rax
0x1800bcd16  cmp     [rdx+rax*2], r13w
0x1800bcd1b  jnz     short loc_1800BCD13
0x1800bcd1d  mov     rcx, [rdi]
0x1800bcd20  test    rcx, rcx
0x1800bcd23  jz      short loc_1800BCD6F
0x1800bcd25  lea     r9, [rdi+8]
0x1800bcd29  lea     r8, [rdx+rax*2]
0x1800bcd2d  mov     [rsp+1D0h+var_198], 10h
0x1800bcd35  mov     eax, [rcx+20h]
0x1800bcd38  mov     [rsp+1D0h+var_1A0], eax
0x1800bcd3c  mov     eax, [rcx+28h]
0x1800bcd3f  mov     [rsp+1D0h+var_1A8], eax
0x1800bcd43  mov     qword ptr [rsp+1D0h+bIgnoreCase], rcx
0x1800bcd48  lea     rcx, [rbp+0D0h+var_140]
0x1800bcd4c  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x1800bcd51  nop
0x1800bcd52  mov     r8b, 1
0x1800bcd55  xor     edx, edx
0x1800bcd57  lea     rcx, [rbp+0D0h+var_140]
0x1800bcd5b  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x1800bcd60  mov     bl, al
0x1800bcd62  lea     rcx, [rbp+0D0h+var_140]
0x1800bcd66  call    ??1?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@XZ; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::~_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(void)
0x1800bcd6b  test    bl, bl
0x1800bcd6d  jnz     short loc_1800BCD88
0x1800bcd6f  add     rdi, 28h ; '('
0x1800bcd73  jmp     short loc_1800BCCFF
0x1800bcd75  mov     r15d, 1
0x1800bcd7b  add     esi, r15d
0x1800bcd7e  mov     rax, [rsp+1D0h+var_178+8]
0x1800bcd83  jmp     loc_1800BCCE6
0x1800bcd88  mov     rbx, [rsp+1D0h+pvar]
0x1800bcd8d  test    rbx, rbx
0x1800bcd90  jz      short loc_1800BCDB4
0x1800bcd92  mov     rdx, [rsp+1D0h+pvar+8]
0x1800bcd97  mov     rcx, rbx
0x1800bcd9a  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800bcd9f  mov     rdx, [rsp+1D0h+var_180]
0x1800bcda4  sub     rdx, rbx
0x1800bcda7  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800bcdab  mov     rcx, rbx
0x1800bcdae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bcdb3  nop
0x1800bcdb4  lea     rcx, [rsp+1D0h+var_178]; pvar
0x1800bcdb9  call    cs:__imp_PropVariantClear
0x1800bcdbf  nop
0x1800bcdc0  lea     rcx, [rbp+0D0h+arg_10]
0x1800bcdc7  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bcdcc  nop
0x1800bcdcd  lea     rcx, [rbp+0D0h+arg_18]
0x1800bcdd4  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bcdd9  mov     ebx, r13d
0x1800bcddc  lea     rcx, [rsp+1D0h+var_160]
0x1800bcde1  call    wil__details__lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea______lambda_call__lambda_086d72bf25ab43678e4bd3b50b848cea___
0x1800bcde6  mov     eax, ebx
0x1800bcde8  jmp     short loc_1800BCE52
0x1800bcdea  mov     rbx, [rsp+1D0h+pvar]
0x1800bcdef  test    rbx, rbx
0x1800bcdf2  jz      short loc_1800BCE16
0x1800bcdf4  mov     rdx, [rsp+1D0h+pvar+8]
0x1800bcdf9  mov     rcx, rbx
0x1800bcdfc  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800bce01  mov     rdx, [rsp+1D0h+var_180]
0x1800bce06  sub     rdx, rbx
0x1800bce09  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800bce0d  mov     rcx, rbx
0x1800bce10  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bce15  nop
  ... truncated ...
```
