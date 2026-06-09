# CEndpointCharacteristics::IsEffectPackConfigurationApplicableToEndpoint(std::shared_ptr<EffectPackConfiguration const> &,bool *)

- ea: `0x1800badb0`
- end: `0x1800bb31d`
- name: `?IsEffectPackConfigurationApplicableToEndpoint@CEndpointCharacteristics@@AEAAJAEAV?$shared_ptr@$$CBUEffectPackConfiguration@@@std@@PEA_N@Z`
- size: `1389`
- prototype: `__int64 __fastcall(bool *, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180140a7c`

## callees

- `0x18000ae1c`
- `0x18000b0c0`
- `0x18001280c`
- `0x1800182e8`
- `0x1800424ec`
- `0x180071280`
- `0x1800badb0`
- `0x1800bb324`
- `0x1800bb344`
- `0x1800bb364`
- `0x1800bb410`
- `0x18013d2f4`
- `0x18013e14c`
- `0x18013e4c8`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baeef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baf13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baeef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baf13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800baf9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb000`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb269`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb2cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800baf9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb000`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb269`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bb2cb`

## string_xrefs

- `0x1800bae8a`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
  __int64 v19; // rdx
  struct IMMDevice *v20; // rbx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rdi
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // esi
  __int64 *v25; // rdi
  __int64 *v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // r8
  char v30; // bl
  PROPVARIANT v31; // rbx
  PROPVARIANT v33; // rbx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h]
  PROPVARIANT v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h]
  _BYTE v39[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[320]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]
  int v42; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v43; // [rsp+1F0h] [rbp+F0h] BYREF
  struct IMMDevice *v44; // [rsp+1F8h] [rbp+F8h] BYREF

  *a3 = 0;
  v42 = 0;
  v6 = _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(
         (_lambda_f3b092209076b90048129f7b4270089e_ *)pvar,
         a1,
         a2,
         (bool *)&v42);
  wil::scope_exit__lambda_a67354e5279dd348e2b8b7a19b53b9e3___(v39, v6);
  v42 = 1;
  if ( *((_DWORD *)a1 + 16) != 3 )
  {
    v42 = 4;
    if ( !*((_DWORD *)a1 + 110) || *((_DWORD *)a1 + 111) )
      goto LABEL_7;
    v8 = *(_QWORD *)(*(_QWORD *)v7 + 1936LL) - PKEY_FX_EffectPack_Schema_Internal_V1;
    if ( !v8 )
      v8 = *(_QWORD *)(*(_QWORD *)v7 + 1944LL) - *((_QWORD *)&PKEY_FX_EffectPack_Schema_Internal_V1 + 1);
    if ( !v8 )
    {
LABEL_7:
      v42 = 7;
      v9 = *((int *)a1 + 59);
      if ( v9 >= 2 )
      {
        v10 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x860,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCase);
LABEL_60:
        wil::details::lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd___::_lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd___(v39);
        return v10;
      }
      v11 = *(_QWORD *)a2;
      if ( *(_BYTE *)(v9 + *(_QWORD *)a2 + 1915) )
      {
        v12 = 0;
        v42 = 2;
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
          v42 = 6;
          *(_OWORD *)pvar = 0;
          v36 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**((_QWORD **)a1 + 9) + 40LL))(
                 *((_QWORD *)a1 + 9),
                 PKEY_Endpoint_IsBluetooth,
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
          v42 = 5;
          *(_OWORD *)pvar = 0;
          v36 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**((_QWORD **)a1 + 9) + 40LL))(
                 *((_QWORD *)a1 + 9),
                 PKEY_Endpoint_IsUSB,
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
          v42 = 3;
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
          v42 = 8;
          if ( (v15[237] - v15[236]) / 40LL )
          {
            v44 = 0;
            v43 = 0;
            *(_OWORD *)v37 = 0;
            v38 = 0;
            std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(pvar);
            wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v44, v19);
            CEndpointCharacteristics::GetPnpDevnodeFromMMDevice((CEndpointCharacteristics *)a1, &v44);
            v20 = v44;
            if ( v44 )
            {
              OpenPropertyStore = v44->lpVtbl->OpenPropertyStore;
              v22 = v43;
              v43 = 0;
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(v20, 0, &v43) >= 0
                && (*(int (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v43 + 40LL))(
                     v43,
                     &DEVPKEY_Device_HardwareIds,
                     v37) >= 0
                && LOWORD(v37[0]) == 4127 )
              {
                v23 = (unsigned int)v37[1];
                if ( LODWORD(v37[1]) )
                {
                  v24 = 0;
LABEL_48:
                  if ( v24 < v23 )
                  {
                    v25 = *(__int64 **)(*(_QWORD *)a2 + 1888LL);
                    v26 = *(__int64 **)(*(_QWORD *)a2 + 1896LL);
                    while ( 1 )
                    {
                      if ( v25 == v26 )
                      {
                        ++v24;
                        v23 = (unsigned int)v37[1];
                        goto LABEL_48;
                      }
                      v27 = *(_QWORD *)(v38 + 8LL * v24);
                      v28 = -1;
                      do
                        ++v28;
                      while ( *(_WORD *)(v27 + 2 * v28) );
                      if ( *v25 )
                      {
                        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(
                          (unsigned int)v40,
                          v27,
                          v27 + 2 * v28,
                          (_DWORD)v25 + 8,
                          *v25,
                          *(_DWORD *)(*v25 + 40),
                          *(_DWORD *)(*v25 + 32),
                          16);
                        LOBYTE(v29) = 1;
                        v30 = std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                                v40,
                                0,
                                v29);
                        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::~_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(v40);
                        if ( v30 )
                          break;
                      }
                      v25 += 5;
                    }
                    v31 = pvar[0];
                    if ( pvar[0] )
                    {
                      std::_Destroy_range<std::allocator<std::wstring>>(pvar[0]);
                      std::_Deallocate<16>(v31, (v36 - (_QWORD)v31) & 0xFFFFFFFFFFFFFFE0uLL);
                    }
                    PropVariantClear(v37);
                    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
                    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
                    v10 = 0;
                    goto LABEL_60;
                  }
                }
              }
            }
            v33 = pvar[0];
            if ( pvar[0] )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(pvar[0]);
              std::_Deallocate<16>(v33, (v36 - (_QWORD)v33) & 0xFFFFFFFFFFFFFFE0uLL);
            }
            PropVariantClear(v37);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v43);
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v44);
          }
          v42 = 0;
          *a3 = 1;
        }
      }
    }
  }
LABEL_65:
  wil::details::lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd___::_lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd___(v39);
  return 0;
}

```

## disassembly

```asm
0x1800badb0  mov     [rsp-8+arg_8], rbx
0x1800badb5  push    rbp
0x1800badb6  push    rsi
0x1800badb7  push    rdi
0x1800badb8  push    r12
0x1800badba  push    r13
0x1800badbc  push    r14
0x1800badbe  push    r15
0x1800badc0  lea     rbp, [rsp-0A0h]
0x1800badc8  sub     rsp, 1A0h
0x1800badcf  mov     r12, r8
0x1800badd2  mov     r14, rdx
0x1800badd5  mov     rbx, rcx
0x1800badd8  xor     r13d, r13d
0x1800baddb  mov     [r8], r13b
0x1800badde  mov     [rbp+0D0h+arg_0], r13d
0x1800bade5  lea     r9, [rbp+0D0h+arg_0]; bool *
0x1800badec  mov     r8, rdx; int *
0x1800badef  mov     rdx, rcx; bool *
0x1800badf2  lea     rcx, [rsp+1D0h+pvar]; this
0x1800badf7  call    ??0_lambda_f3b092209076b90048129f7b4270089e_@@QEAA@AEA_NAEBH0@Z; _lambda_f3b092209076b90048129f7b4270089e_::_lambda_f3b092209076b90048129f7b4270089e_(bool &,int const &,bool &)
0x1800badfc  mov     rdx, rax
0x1800badff  lea     rcx, [rsp+1D0h+var_160]
0x1800bae04  call    wil__scope_exit__lambda_a67354e5279dd348e2b8b7a19b53b9e3___
0x1800bae09  nop
0x1800bae0a  lea     edx, [r13+1]
0x1800bae0e  mov     [rbp+0D0h+arg_0], edx
0x1800bae14  cmp     dword ptr [rbx+40h], 3
0x1800bae18  jz      loc_1800BB2F6
0x1800bae1e  mov     [rbp+0D0h+arg_0], 4
0x1800bae28  cmp     [rbx+1B8h], r13d
0x1800bae2f  jz      short loc_1800BAE64
0x1800bae31  cmp     [rbx+1BCh], r13d
0x1800bae38  jnz     short loc_1800BAE64
0x1800bae3a  mov     rcx, [r8]
0x1800bae3d  mov     rax, [rcx+790h]
0x1800bae44  sub     rax, qword ptr cs:PKEY_FX_EffectPack_Schema_Internal_V1
0x1800bae4b  jnz     short loc_1800BAE5B
0x1800bae4d  mov     rax, [rcx+798h]
0x1800bae54  sub     rax, qword ptr cs:PKEY_FX_EffectPack_Schema_Internal_V1+8
0x1800bae5b  test    rax, rax
0x1800bae5e  jnz     loc_1800BB2F6
0x1800bae64  mov     [rbp+0D0h+arg_0], 7
0x1800bae6e  movsxd  rcx, dword ptr [rbx+0ECh]
0x1800bae75  cmp     rcx, 2
0x1800bae79  jb      short loc_1800BAEA0
0x1800bae7b  mov     rcx, [rbp+0D8h]; this
0x1800bae82  mov     ebx, 8000FFFFh
0x1800bae87  mov     r9d, ebx; char *
0x1800bae8a  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800bae91  mov     edx, 860h; void *
0x1800bae96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bae9b  jmp     loc_1800BB28C
0x1800baea0  mov     rax, [r14]
0x1800baea3  cmp     [rcx+rax+77Bh], r13b
0x1800baeab  jz      loc_1800BB2F6
0x1800baeb1  mov     dil, r13b
0x1800baeb4  mov     [rbp+0D0h+arg_0], 2
0x1800baebe  mov     rsi, [rax+748h]
0x1800baec5  mov     r15, [rax+750h]
0x1800baecc  cmp     rsi, r15
0x1800baecf  jz      short loc_1800BAF34
0x1800baed1  cmp     [rbx+1A0h], r13
0x1800baed8  jz      short loc_1800BAF23
0x1800baeda  mov     [rsp+1D0h+bIgnoreCase], edx; bIgnoreCase
0x1800baede  or      r9d, 0FFFFFFFFh; cchCount2
0x1800baee2  lea     r8, asc_180196CA8; "*"
0x1800baee9  or      edx, r9d; cchCount1
0x1800baeec  mov     rcx, [rsi]; lpString1
0x1800baeef  call    cs:__imp_CompareStringOrdinal
0x1800baef5  cmp     eax, 2
0x1800baef8  jz      short loc_1800BAF29
0x1800baefa  mov     [rsp+1D0h+bIgnoreCase], 1; bIgnoreCase
0x1800baf02  or      r9d, 0FFFFFFFFh; cchCount2
0x1800baf06  mov     r8, [rbx+1A0h]; lpString2
0x1800baf0d  or      edx, r9d; cchCount1
0x1800baf10  mov     rcx, [rsi]; lpString1
0x1800baf13  call    cs:__imp_CompareStringOrdinal
0x1800baf19  cmp     eax, 2
0x1800baf1c  jz      short loc_1800BAF29
0x1800baf1e  mov     edx, 1
0x1800baf23  add     rsi, 8
0x1800baf27  jmp     short loc_1800BAECC
0x1800baf29  mov     r15d, 1
0x1800baf2f  mov     dil, r15b
0x1800baf32  jmp     short loc_1800BAF3A
0x1800baf34  mov     r15d, 1
0x1800baf3a  mov     rax, [r14]
0x1800baf3d  cmp     [rax+778h], r13b
0x1800baf44  jz      short loc_1800BAFA0
0x1800baf46  mov     [rbp+0D0h+arg_0], 6
0x1800baf50  xorps   xmm0, xmm0
0x1800baf53  xor     eax, eax
0x1800baf55  movups  xmmword ptr [rsp+1D0h+pvar], xmm0
0x1800baf5a  mov     [rsp+1D0h+var_180], rax
0x1800baf5f  mov     rcx, [rbx+48h]
0x1800baf63  mov     rax, [rcx]
0x1800baf66  lea     r8, [rsp+1D0h+pvar]
0x1800baf6b  lea     rdx, PKEY_Endpoint_IsBluetooth
0x1800baf72  mov     rax, [rax+28h]
0x1800baf76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baf7b  test    eax, eax
0x1800baf7d  js      short loc_1800BAF95
0x1800baf7f  cmp     word ptr [rsp+1D0h+pvar], 0Bh
0x1800baf85  jnz     short loc_1800BAF95
0x1800baf87  movzx   edi, dil
0x1800baf8b  cmp     word ptr [rsp+1D0h+pvar+8], r13w
0x1800baf91  cmovnz  edi, r15d
0x1800baf95  lea     rcx, [rsp+1D0h+pvar]; pvar
0x1800baf9a  call    cs:__imp_PropVariantClear
0x1800bafa0  mov     rax, [r14]
0x1800bafa3  cmp     [rax+779h], r13b
0x1800bafaa  jz      short loc_1800BB006
0x1800bafac  mov     [rbp+0D0h+arg_0], 5
0x1800bafb6  xorps   xmm0, xmm0
0x1800bafb9  xor     eax, eax
0x1800bafbb  movups  xmmword ptr [rsp+1D0h+pvar], xmm0
0x1800bafc0  mov     [rsp+1D0h+var_180], rax
0x1800bafc5  mov     rcx, [rbx+48h]
0x1800bafc9  mov     rax, [rcx]
0x1800bafcc  lea     r8, [rsp+1D0h+pvar]
0x1800bafd1  lea     rdx, PKEY_Endpoint_IsUSB
0x1800bafd8  mov     rax, [rax+28h]
0x1800bafdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafe1  test    eax, eax
0x1800bafe3  js      short loc_1800BAFFB
0x1800bafe5  cmp     word ptr [rsp+1D0h+pvar], 0Bh
0x1800bafeb  jnz     short loc_1800BAFFB
0x1800bafed  movzx   edi, dil
0x1800baff1  cmp     word ptr [rsp+1D0h+pvar+8], r13w
0x1800baff7  cmovnz  edi, r15d
0x1800baffb  lea     rcx, [rsp+1D0h+pvar]; pvar
0x1800bb000  call    cs:__imp_PropVariantClear
0x1800bb006  test    dil, dil
0x1800bb009  jz      loc_1800BB2F6
0x1800bb00f  mov     [rbp+0D0h+arg_0], 3
0x1800bb019  mov     r8, [r14]
0x1800bb01c  mov     rcx, [r8+720h]
0x1800bb023  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800bb02a  cmp     rcx, [r8+728h]
0x1800bb031  jz      loc_1800BB2F6
0x1800bb037  mov     rax, [rcx]
0x1800bb03a  sub     rax, [rbx+1A8h]
0x1800bb041  jnz     short loc_1800BB04E
0x1800bb043  mov     rax, [rcx+8]
0x1800bb047  sub     rax, [rbx+1B0h]
0x1800bb04e  test    rax, rax
0x1800bb051  jz      short loc_1800BB080
0x1800bb053  mov     rdx, [rcx]
0x1800bb056  movq    rax, xmm1
0x1800bb05b  sub     rdx, rax
0x1800bb05e  jnz     short loc_1800BB075
0x1800bb060  mov     rdx, [rcx+8]
0x1800bb064  movdqa  xmm0, xmm1
0x1800bb068  psrldq  xmm0, 8
0x1800bb06d  movq    rax, xmm0
0x1800bb072  sub     rdx, rax
0x1800bb075  test    rdx, rdx
0x1800bb078  jz      short loc_1800BB080
0x1800bb07a  add     rcx, 10h
0x1800bb07e  jmp     short loc_1800BB02A
0x1800bb080  mov     [rbp+0D0h+arg_0], 8
0x1800bb08a  mov     rcx, [r8+768h]
0x1800bb091  sub     rcx, [r8+760h]
0x1800bb098  mov     rax, 6666666666666667h
0x1800bb0a2  imul    rcx
0x1800bb0a5  sar     rdx, 4
0x1800bb0a9  mov     rax, rdx
0x1800bb0ac  shr     rax, 3Fh
0x1800bb0b0  add     rdx, rax
0x1800bb0b3  jz      loc_1800BB2EB
0x1800bb0b9  mov     [rbp+0D0h+arg_18], r13
0x1800bb0c0  mov     [rbp+0D0h+arg_10], r13
0x1800bb0c7  xorps   xmm0, xmm0
0x1800bb0ca  xor     eax, eax
0x1800bb0cc  movups  xmmword ptr [rsp+1D0h+var_178], xmm0
0x1800bb0d1  mov     [rsp+1D0h+var_168], rax
0x1800bb0d6  lea     rcx, [rsp+1D0h+pvar]; void *
0x1800bb0db  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x1800bb0e0  nop
0x1800bb0e1  lea     rcx, [rbp+0D0h+arg_18]
0x1800bb0e8  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800bb0ed  lea     rdx, [rbp+0D0h+arg_18]; struct IMMDevice **
0x1800bb0f4  mov     rcx, rbx; this
0x1800bb0f7  call    ?GetPnpDevnodeFromMMDevice@CEndpointCharacteristics@@AEAAJPEAPEAUIMMDevice@@@Z; CEndpointCharacteristics::GetPnpDevnodeFromMMDevice(IMMDevice * *)
0x1800bb0fc  mov     rbx, [rbp+0D0h+arg_18]
0x1800bb103  test    rbx, rbx
0x1800bb106  jz      loc_1800BB29A
0x1800bb10c  mov     rax, [rbx]
0x1800bb10f  mov     rdi, [rax+20h]
0x1800bb113  mov     rcx, [rbp+0D0h+arg_10]
0x1800bb11a  mov     [rbp+0D0h+arg_10], r13
0x1800bb121  test    rcx, rcx
0x1800bb124  jz      short loc_1800BB133
0x1800bb126  mov     rdx, [rcx]
0x1800bb129  mov     rax, [rdx+10h]
0x1800bb12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb132  nop
0x1800bb133  lea     r8, [rbp+0D0h+arg_10]
0x1800bb13a  xor     edx, edx
0x1800bb13c  mov     rcx, rbx
0x1800bb13f  mov     rax, rdi
0x1800bb142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb147  test    eax, eax
0x1800bb149  js      loc_1800BB29A
0x1800bb14f  mov     rcx, [rbp+0D0h+arg_10]
0x1800bb156  mov     rax, [rcx]
0x1800bb159  lea     r8, [rsp+1D0h+var_178]
0x1800bb15e  lea     rdx, DEVPKEY_Device_HardwareIds
0x1800bb165  mov     rax, [rax+28h]
0x1800bb169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb16e  test    eax, eax
0x1800bb170  js      loc_1800BB29A
0x1800bb176  mov     eax, 101Fh
0x1800bb17b  cmp     word ptr [rsp+1D0h+var_178], ax
0x1800bb180  jnz     loc_1800BB29A
0x1800bb186  mov     rax, [rsp+1D0h+var_178+8]
0x1800bb18b  test    eax, eax
0x1800bb18d  jz      loc_1800BB29A
0x1800bb193  mov     esi, r13d
0x1800bb196  cmp     esi, eax
0x1800bb198  jnb     loc_1800BB29A
0x1800bb19e  mov     rax, [r14]
0x1800bb1a1  mov     rdi, [rax+760h]
0x1800bb1a8  mov     r15, [rax+768h]
0x1800bb1af  cmp     rdi, r15
0x1800bb1b2  jz      short loc_1800BB225
0x1800bb1b4  mov     ecx, esi
0x1800bb1b6  mov     rax, [rsp+1D0h+var_168]
0x1800bb1bb  mov     rdx, [rax+rcx*8]
0x1800bb1bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bb1c3  inc     rax
0x1800bb1c6  cmp     [rdx+rax*2], r13w
0x1800bb1cb  jnz     short loc_1800BB1C3
0x1800bb1cd  mov     rcx, [rdi]
0x1800bb1d0  test    rcx, rcx
0x1800bb1d3  jz      short loc_1800BB21F
0x1800bb1d5  lea     r9, [rdi+8]
0x1800bb1d9  lea     r8, [rdx+rax*2]
0x1800bb1dd  mov     [rsp+1D0h+var_198], 10h
0x1800bb1e5  mov     eax, [rcx+20h]
0x1800bb1e8  mov     [rsp+1D0h+var_1A0], eax
0x1800bb1ec  mov     eax, [rcx+28h]
0x1800bb1ef  mov     [rsp+1D0h+var_1A8], eax
0x1800bb1f3  mov     qword ptr [rsp+1D0h+bIgnoreCase], rcx
0x1800bb1f8  lea     rcx, [rbp+0D0h+var_140]
0x1800bb1fc  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x1800bb201  nop
0x1800bb202  mov     r8b, 1
0x1800bb205  xor     edx, edx
0x1800bb207  lea     rcx, [rbp+0D0h+var_140]
0x1800bb20b  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x1800bb210  mov     bl, al
0x1800bb212  lea     rcx, [rbp+0D0h+var_140]
0x1800bb216  call    ??1?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@XZ; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::~_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(void)
0x1800bb21b  test    bl, bl
0x1800bb21d  jnz     short loc_1800BB238
0x1800bb21f  add     rdi, 28h ; '('
0x1800bb223  jmp     short loc_1800BB1AF
0x1800bb225  mov     r15d, 1
0x1800bb22b  add     esi, r15d
0x1800bb22e  mov     rax, [rsp+1D0h+var_178+8]
0x1800bb233  jmp     loc_1800BB196
0x1800bb238  mov     rbx, [rsp+1D0h+pvar]
0x1800bb23d  test    rbx, rbx
0x1800bb240  jz      short loc_1800BB264
0x1800bb242  mov     rdx, [rsp+1D0h+pvar+8]
0x1800bb247  mov     rcx, rbx
0x1800bb24a  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800bb24f  mov     rdx, [rsp+1D0h+var_180]
0x1800bb254  sub     rdx, rbx
0x1800bb257  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800bb25b  mov     rcx, rbx
0x1800bb25e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bb263  nop
0x1800bb264  lea     rcx, [rsp+1D0h+var_178]; pvar
0x1800bb269  call    cs:__imp_PropVariantClear
0x1800bb26f  nop
0x1800bb270  lea     rcx, [rbp+0D0h+arg_10]
0x1800bb277  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bb27c  nop
0x1800bb27d  lea     rcx, [rbp+0D0h+arg_18]
0x1800bb284  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800bb289  mov     ebx, r13d
0x1800bb28c  lea     rcx, [rsp+1D0h+var_160]
0x1800bb291  call    wil__details__lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd______lambda_call__lambda_a20b7d585fd9dab0721287e04a29eedd___
0x1800bb296  mov     eax, ebx
0x1800bb298  jmp     short loc_1800BB302
0x1800bb29a  mov     rbx, [rsp+1D0h+pvar]
0x1800bb29f  test    rbx, rbx
0x1800bb2a2  jz      short loc_1800BB2C6
0x1800bb2a4  mov     rdx, [rsp+1D0h+pvar+8]
0x1800bb2a9  mov     rcx, rbx
0x1800bb2ac  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800bb2b1  mov     rdx, [rsp+1D0h+var_180]
0x1800bb2b6  sub     rdx, rbx
0x1800bb2b9  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800bb2bd  mov     rcx, rbx
0x1800bb2c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800bb2c5  nop
  ... truncated ...
```
