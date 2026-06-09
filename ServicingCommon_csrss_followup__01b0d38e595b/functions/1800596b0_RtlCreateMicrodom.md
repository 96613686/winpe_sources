# RtlCreateMicrodom

- ea: `0x1800596b0`
- end: `0x180059ea9`
- name: `RtlCreateMicrodom`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005cd60`

## callees

- `0x1800040e0`
- `0x180005258`
- `0x18000c3d0`
- `0x18000dcd0`
- `0x180014250`
- `0x18001a620`
- `0x18001af00`
- `0x18001cd2c`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x180058e50`
- `0x1800596b0`
- `0x180097e20`
- `0x1800981e0`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180059e3a`
- `ntdll!RtlRaiseStatus` at `0x180059e3a`

## string_xrefs

- `0x180059724`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059779`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800597c8`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059808`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059843`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800598f8`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059bac`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059c1a`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059c61`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059cee`: `onecore\base\xml\udom_microdom.cpp`
- `0x180059dd4`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005973b`: `RtlCreateMicrodom`
- `0x180059790`: `RtlCreateMicrodom`
- `0x1800597df`: `RtlCreateMicrodom`
- `0x18005981f`: `RtlCreateMicrodom`
- `0x18005985a`: `RtlCreateMicrodom`
- `0x18005990f`: `RtlCreateMicrodom`
- `0x180059bc3`: `RtlCreateMicrodom`
- `0x180059c31`: `RtlCreateMicrodom`
- `0x180059c81`: `RtlCreateMicrodom`
- `0x180059d0e`: `RtlCreateMicrodom`
- `0x180059df4`: `RtlCreateMicrodom`
- `0x18005979b`: `(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Xml)`
- `0x1800597ea`: `(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Blob)`
- `0x180059bce`: `RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)`
- `0x180059c3c`: `RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodom(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdx
  int v5; // eax
  _QWORD *v6; // rdx
  int v7; // ecx
  __int128 **v8; // rdi
  _QWORD **v9; // rdx
  _QWORD *v10; // rcx
  int v11; // esi
  int BinaryMicrodomFromXml; // ebx
  __int64 v13; // rsi
  int v14; // r14d
  __int128 *v15; // rcx
  __int64 v16; // r15
  __int64 v17; // rsi
  size_t v18; // rax
  __int128 *v19; // rdi
  int v20; // eax
  __int64 v21; // r8
  _QWORD *v22; // rdx
  int v23; // eax
  __int128 v24; // xmm1
  int v25; // r8d
  int v26; // edi
  __int128 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h] BYREF
  void *Src; // [rsp+68h] [rbp-98h]
  _BYTE v34[24]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v35[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v36[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v37[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v38[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v39[4]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v40[4]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v41[4]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v42[4]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v43[4]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v44[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v45[5]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v46[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v47; // [rsp+208h] [rbp+108h]
  __int128 v48; // [rsp+218h] [rbp+118h]
  __int64 v49; // [rsp+228h] [rbp+128h]
  _DWORD v50[88]; // [rsp+230h] [rbp+130h] BYREF
  _OWORD v51[2]; // [rsp+390h] [rbp+290h] BYREF
  __int128 v52; // [rsp+3B0h] [rbp+2B0h]
  __int64 v53; // [rsp+3C0h] [rbp+2C0h]
  _QWORD v54[3]; // [rsp+3C8h] [rbp+2C8h] BYREF
  int v55; // [rsp+3E0h] [rbp+2E0h] BYREF
  size_t Size; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int128 v57; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v58; // [rsp+400h] [rbp+300h]
  __int64 v59; // [rsp+408h] [rbp+308h] BYREF

  v55 = 0;
  v53 = 0;
  memset(v34, 0, sizeof(v34));
  memset(v51, 0, sizeof(v51));
  v52 = 0;
  if ( !a1 )
  {
    v35[2] = 4096;
    v35[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = v35;
    v35[1] = "RtlCreateMicrodom";
    v35[3] = "Not-null check failed: Params";
LABEL_3:
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v55,
           v4);
LABEL_77:
    BinaryMicrodomFromXml = v5;
    goto LABEL_78;
  }
  v5 = Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom>::Initialize();
  if ( v5 < 0 )
    goto LABEL_77;
  if ( *(_DWORD *)a1 >= 2u )
  {
    v36[2] = 4102;
    v36[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = v36;
    v36[1] = "RtlCreateMicrodom";
    v36[3] = "(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Window"
             "s::Microdom::Rtl::CreateMicrodomSource::Xml)";
LABEL_7:
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v55,
           v6);
    goto LABEL_77;
  }
  v7 = *(_DWORD *)(a1 + 4);
  if ( v7 )
  {
    if ( v7 != 2 && v7 != 1 )
    {
      v37[2] = 4107;
      v37[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v6 = v37;
      v37[1] = "RtlCreateMicrodom";
      v37[3] = "(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Wi"
               "ndows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rt"
               "l::CreateMicrodomSource::Blob)";
      goto LABEL_7;
    }
    v8 = (__int128 **)(a1 + 8);
    v9 = (_QWORD **)(a1 + 8);
    if ( v7 == 1 && !*v8 )
    {
      v38[2] = 4113;
      v38[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v4 = v38;
      v38[1] = "RtlCreateMicrodom";
      v38[3] = "Not-null check failed: Params->Source.pBlob";
      goto LABEL_3;
    }
  }
  else
  {
    v8 = (__int128 **)(a1 + 8);
    if ( !*(_QWORD *)(a1 + 8) )
    {
      v39[2] = 4110;
      v39[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v4 = v39;
      v39[1] = "RtlCreateMicrodom";
      v39[3] = "Not-null check failed: Params->Source.pIStream";
      goto LABEL_3;
    }
    v9 = (_QWORD **)(a1 + 8);
  }
  v53 = 0;
  LOBYTE(v53) = *(_BYTE *)(a1 + 48);
  memset(v51, 0, sizeof(v51));
  v52 = 0;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
      goto LABEL_74;
    v29 = 0;
    v58 = 0;
    v28 = 0;
    v57 = 0;
    if ( !v7 )
    {
      Size = 0;
      Src = 0;
      v32 = 0;
      v11 = RtlAllocateLBlob(1024, &v32);
      if ( v11 >= 0 )
      {
        v13 = 0;
        while ( 1 )
        {
          v14 = (*(__int64 (__fastcall **)(__int128 *, __int64, void *, size_t *))(*(_QWORD *)*v8 + 16LL))(
                  *v8,
                  1024,
                  Src,
                  &Size);
          if ( v14 < 0 )
            break;
          v13 += Size;
          if ( Size != 1024 )
          {
            v11 = RtlAllocateLBlob(v13, &v28);
            if ( v11 < 0 )
              goto LABEL_27;
            v15 = *v8;
            v30 = 0;
            v59 = 0;
            v11 = (*(__int64 (__fastcall **)(__int128 *, GUID *, __int64 *))(*(_QWORD *)v15 + 8LL))(
                    v15,
                    &GUID_55eab610_3945_4595_b7f9_75bebf9486f4,
                    &v59);
            if ( v11 >= 0 )
            {
              if ( v59 )
              {
                v30 = v59;
                v59 = 0;
              }
              else
              {
                v11 = -1073741127;
              }
            }
            Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v59);
            if ( v11 < 0 )
            {
              Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v30);
              goto LABEL_27;
            }
            v16 = v29;
            v17 = v28;
            while ( 1 )
            {
              v14 = (*(__int64 (__fastcall **)(__int128 *, __int64, void *, size_t *))(*(_QWORD *)*v8 + 16LL))(
                      *v8,
                      1024,
                      Src,
                      &Size);
              if ( v14 < 0 )
                break;
              v18 = Size;
              if ( Size )
              {
                memmove((void *)(v16 + v17), Src, Size);
                v18 = Size;
                v17 += Size;
                *(_QWORD *)&v28 = v17;
              }
              if ( v18 != 1024 )
              {
                v19 = &v28;
                Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v30);
                Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v32);
                goto LABEL_47;
              }
            }
            Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v30);
            break;
          }
        }
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v32);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v57);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v28);
        BinaryMicrodomFromXml = v14;
      }
      else
      {
LABEL_27:
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v32);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v57);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v28);
        BinaryMicrodomFromXml = v11;
      }
      goto LABEL_78;
    }
    v19 = *v8;
LABEL_47:
    if ( *(_BYTE *)(a1 + 49) || *(_BYTE *)(a1 + 50) )
    {
      v46[1] = *((_QWORD *)v19 + 2);
      v46[2] = *(_QWORD *)v19;
      v46[0] = 64;
      v49 = 0;
      v47 = 0;
      v48 = 0;
      memset(v50, 0, sizeof(v50));
      v31 = 0;
      v20 = RtlXmlInitializeTokenization(v50, v46);
      v21 = (unsigned int)v20;
      if ( v20 < 0 )
      {
        v41[2] = 4193;
        v41[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v22 = v41;
        v41[1] = "RtlCreateMicrodom";
        v41[3] = "RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)";
        goto LABEL_51;
      }
      v23 = RtlXmlDetermineStreamEncoding(v50, &v31, (unsigned int)v20);
      v21 = (unsigned int)v23;
      if ( v23 < 0 )
      {
        v42[2] = 4194;
        v42[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v22 = v42;
        v42[1] = "RtlCreateMicrodom";
        v42[3] = "RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)";
        goto LABEL_51;
      }
      if ( v50[12] != 5 )
      {
        if ( *(_BYTE *)(a1 + 49) )
        {
          v43[2] = 4198;
          v43[0] = "onecore\\base\\xml\\udom_microdom.cpp";
          v22 = v43;
          v21 = 3221225485LL;
          v43[1] = "RtlCreateMicrodom";
          v43[3] = "Params->fRequireUtf8";
          goto LABEL_51;
        }
        v24 = *v19;
        v54[2] = v31 + *((_QWORD *)v19 + 2);
        v54[0] = v24 - v31;
        v54[1] = v24 - v31;
        switch ( v50[12] )
        {
          case 1:
            v25 = 1019;
            break;
          case 2:
            v25 = 1018;
            break;
          case 3:
            v25 = 1014;
            break;
          case 4:
            v25 = 1013;
            break;
          default:
            v44[2] = 4221;
            v44[0] = "onecore\\base\\xml\\udom_microdom.cpp";
            v22 = v44;
            v44[3] = 0;
            v44[1] = "RtlCreateMicrodom";
            v21 = 3221225485LL;
            goto LABEL_51;
        }
        v26 = RtlTranscodeLBlobs(5, 0, v25, (unsigned int)v54, 106, (__int64)&v57);
        if ( v26 < 0 )
        {
          Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v57);
          Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v28);
          BinaryMicrodomFromXml = v26;
          goto LABEL_78;
        }
        v19 = &v57;
      }
    }
    BinaryMicrodomFromXml = MicrodomImplementation::CreateBinaryMicrodomFromXml(*(_QWORD *)(a1 + 40), v9, v19, v34);
    if ( BinaryMicrodomFromXml < 0 )
      goto LABEL_52;
    *(_QWORD *)&v51[0] = *(_QWORD *)v34;
    *(_OWORD *)((char *)v51 + 8) = *(_OWORD *)&v34[8];
    if ( *(_QWORD *)v34 )
    {
      Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v57);
      Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v28);
      goto LABEL_74;
    }
    v45[2] = 4251;
    v45[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v22 = v45;
    v45[3] = 0;
    v45[1] = "RtlCreateMicrodom";
    v21 = 3221266563LL;
LABEL_51:
    BinaryMicrodomFromXml = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                              &v55,
                              v22,
                              v21);
LABEL_52:
    Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v57);
    Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v28);
LABEL_78:
    Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(v34);
    return (unsigned int)BinaryMicrodomFromXml;
  }
  if ( v7 == 1 )
  {
    v10 = *v9;
    *(_QWORD *)&v51[0] = **v9;
    *(_OWORD *)((char *)v51 + 8) = *(_OWORD *)(v10 + 1);
  }
  else
  {
    if ( v7 != 2 )
    {
      v40[2] = 4133;
      v40[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v40[3] = 0;
      v40[1] = "RtlCreateMicrodom";
      v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v55,
             v40,
             3221225474LL);
      goto LABEL_77;
    }
    *((_QWORD *)&v51[1] + 1) = *v9;
    v52 = *(_OWORD *)(a1 + 16);
  }
LABEL_74:
  if ( dword_1800D2B18 != 2 )
    RtlRaiseStatus(-1073741595);
  v5 = Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CMicrodom>::CreateInstance<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff,MicrodomImplementation::MdCreateParams,Windows::Microdom::Rtl::IRtlMicrodom>(
         MicrodomImplementation::g_OneShotMicrodomInit,
         v51,
         a2);
  if ( v5 < 0 )
    goto LABEL_77;
  Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(v34);
  return 0;
}

```

## disassembly

```asm
0x1800596b0  mov     [rsp-8+arg_10], rbx
0x1800596b5  mov     [rsp-8+arg_18], rsi
0x1800596ba  push    rbp
0x1800596bb  push    rdi
0x1800596bc  push    r13
0x1800596be  push    r14
0x1800596c0  push    r15
0x1800596c2  lea     rbp, [rsp-320h]
0x1800596ca  sub     rsp, 420h
0x1800596d1  mov     rax, cs:__security_cookie
0x1800596d8  xor     rax, rsp
0x1800596db  mov     [rbp+340h+var_30], rax
0x1800596e2  xor     eax, eax
0x1800596e4  xorps   xmm1, xmm1
0x1800596e7  xor     r15d, r15d
0x1800596ea  mov     [rbp+340h+var_3C0], rax
0x1800596ee  mov     [rbp+340h+var_60], r15d
0x1800596f5  xorps   xmm0, xmm0
0x1800596f8  mov     [rbp+340h+var_80], rax
0x1800596ff  mov     r13, rdx
0x180059702  mov     rbx, rcx
0x180059705  movups  [rsp+440h+var_3D0], xmm0
0x18005970a  movups  [rbp+340h+var_B0], xmm1
0x180059711  movups  [rbp+340h+var_A0], xmm1
0x180059718  movups  [rbp+340h+var_90], xmm1
0x18005971f  test    rcx, rcx
0x180059722  jnz     short loc_180059762
0x180059724  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005972b  mov     [rbp+340h+var_3A8], 1000h
0x180059733  mov     [rbp+340h+var_3B8], rax
0x180059737  lea     rdx, [rbp+340h+var_3B8]
0x18005973b  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059742  mov     [rbp+340h+var_3B0], rax
0x180059746  lea     rax, aNotNullCheckFa_12; "Not-null check failed: Params"
0x18005974d  mov     [rbp+340h+var_3A0], rax
0x180059751  lea     rcx, [rbp+340h+var_60]
0x180059758  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005975d  jmp     loc_180059E61
0x180059762  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom>::Initialize(void)
0x180059767  test    eax, eax
0x180059769  js      loc_180059E61
0x18005976f  cmp     [rbx], r15d
0x180059772  jz      short loc_1800597B7
0x180059774  cmp     dword ptr [rbx], 1
0x180059777  jz      short loc_1800597B7
0x180059779  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180059780  mov     [rbp+340h+var_388], 1006h
0x180059788  mov     [rbp+340h+var_398], rax
0x18005978c  lea     rdx, [rbp+340h+var_398]
0x180059790  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059797  mov     [rbp+340h+var_390], rax
0x18005979b  lea     rax, aParamsInputtyp; "(Params->InputType == Windows::Microdom"...
0x1800597a2  mov     [rbp+340h+var_380], rax
0x1800597a6  lea     rcx, [rbp+340h+var_60]
0x1800597ad  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800597b2  jmp     loc_180059E61
0x1800597b7  mov     ecx, [rbx+4]
0x1800597ba  test    ecx, ecx
0x1800597bc  jz      short loc_18005983A
0x1800597be  cmp     ecx, 2
0x1800597c1  jz      short loc_1800597F7
0x1800597c3  cmp     ecx, 1
0x1800597c6  jz      short loc_1800597F7
0x1800597c8  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800597cf  mov     [rbp+340h+var_368], 100Bh
0x1800597d7  mov     [rbp+340h+var_378], rax
0x1800597db  lea     rdx, [rbp+340h+var_378]
0x1800597df  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x1800597e6  mov     [rbp+340h+var_370], rax
0x1800597ea  lea     rax, aParamsSourcety; "(Params->SourceType == Windows::Microdo"...
0x1800597f1  mov     [rbp+340h+var_360], rax
0x1800597f5  jmp     short loc_1800597A6
0x1800597f7  lea     rdi, [rbx+8]
0x1800597fb  mov     rdx, rdi
0x1800597fe  cmp     ecx, 1
0x180059801  jnz     short loc_180059878
0x180059803  cmp     [rdi], r15
0x180059806  jnz     short loc_180059878
0x180059808  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005980f  mov     [rbp+340h+var_348], 1011h
0x180059817  mov     [rbp+340h+var_358], rax
0x18005981b  lea     rdx, [rbp+340h+var_358]
0x18005981f  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059826  mov     [rbp+340h+var_350], rax
0x18005982a  lea     rax, aNotNullCheckFa_3; "Not-null check failed: Params->Source.p"...
0x180059831  mov     [rbp+340h+var_340], rax
0x180059835  jmp     loc_180059751
0x18005983a  lea     rdi, [rbx+8]
0x18005983e  cmp     [rdi], r15
0x180059841  jnz     short loc_180059875
0x180059843  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005984a  mov     [rbp+340h+var_328], 100Eh
0x180059852  mov     [rbp+340h+var_338], rax
0x180059856  lea     rdx, [rbp+340h+var_338]
0x18005985a  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059861  mov     [rbp+340h+var_330], rax
0x180059865  lea     rax, aNotNullCheckFa_98; "Not-null check failed: Params->Source.p"...
0x18005986c  mov     [rbp+340h+var_320], rax
0x180059870  jmp     loc_180059751
0x180059875  mov     rdx, rdi
0x180059878  xor     eax, eax
0x18005987a  xorps   xmm0, xmm0
0x18005987d  mov     [rbp+340h+var_80], rax
0x180059884  mov     al, [rbx+30h]
0x180059887  mov     byte ptr [rbp+340h+var_80], al
0x18005988d  movups  [rbp+340h+var_B0], xmm0
0x180059894  movups  [rbp+340h+var_A0], xmm0
0x18005989b  movups  [rbp+340h+var_90], xmm0
0x1800598a2  cmp     [rbx], r15d
0x1800598a5  jnz     loc_180059935
0x1800598ab  cmp     ecx, 1
0x1800598ae  jnz     short loc_1800598CE
0x1800598b0  mov     rcx, [rdx]
0x1800598b3  mov     rax, [rcx]
0x1800598b6  mov     qword ptr [rbp+340h+var_B0], rax
0x1800598bd  movups  xmm0, xmmword ptr [rcx+8]
0x1800598c1  movdqu  [rbp+340h+var_B0+8], xmm0
0x1800598c9  jmp     loc_180059E2A
0x1800598ce  cmp     ecx, 2
0x1800598d1  jnz     short loc_1800598F8
0x1800598d3  mov     rax, [rdx]
0x1800598d6  mov     qword ptr [rbp+340h+var_A0+8], rax
0x1800598dd  mov     rax, [rbx+10h]
0x1800598e1  mov     qword ptr [rbp+340h+var_90], rax
0x1800598e8  mov     rax, [rbx+18h]
0x1800598ec  mov     qword ptr [rbp+340h+var_90+8], rax
0x1800598f3  jmp     loc_180059E2A
0x1800598f8  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800598ff  mov     [rbp+340h+var_308], 1025h
0x180059907  mov     [rbp+340h+var_318], rax
0x18005990b  lea     rdx, [rbp+340h+var_318]
0x18005990f  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059916  mov     [rbp+340h+var_300], r15
0x18005991a  mov     r8d, 0C0000002h
0x180059920  mov     [rbp+340h+var_310], rax
0x180059924  lea     rcx, [rbp+340h+var_60]
0x18005992b  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180059930  jmp     loc_180059E61
0x180059935  cmp     dword ptr [rbx], 1
0x180059938  jnz     loc_180059E2A
0x18005993e  xor     eax, eax
0x180059940  xorps   xmm1, xmm1
0x180059943  mov     [rsp+440h+var_400], rax
0x180059948  mov     [rbp+340h+var_40], rax
0x18005994f  movups  [rsp+440h+var_410], xmm0
0x180059954  movups  [rbp+340h+var_50], xmm1
0x18005995b  test    ecx, ecx
0x18005995d  jnz     loc_180059B2C
0x180059963  mov     r14d, 400h
0x180059969  mov     [rbp+340h+Size], r15
0x180059970  mov     ecx, r14d
0x180059973  mov     [rsp+440h+Src], rax
0x180059978  lea     rdx, [rsp+440h+var_3E8]
0x18005997d  movups  [rsp+440h+var_3E8], xmm0
0x180059982  call    RtlAllocateLBlob
0x180059987  mov     esi, eax
0x180059989  test    eax, eax
0x18005998b  jns     short loc_1800599B4
0x18005998d  lea     rcx, [rsp+440h+var_3E8]
0x180059992  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059997  lea     rcx, [rbp+340h+var_50]
0x18005999e  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x1800599a3  lea     rcx, [rsp+440h+var_410]
0x1800599a8  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x1800599ad  mov     ebx, esi
0x1800599af  jmp     loc_180059E63
0x1800599b4  mov     rsi, r15
0x1800599b7  mov     rcx, [rdi]
0x1800599ba  lea     r9, [rbp+340h+Size]
0x1800599c1  mov     r8, [rsp+440h+Src]
0x1800599c6  mov     rdx, r14
0x1800599c9  mov     rax, [rcx]
0x1800599cc  mov     rax, [rax+10h]
0x1800599d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599d5  mov     r14d, eax
0x1800599d8  test    eax, eax
0x1800599da  js      loc_180059B04
0x1800599e0  add     rsi, [rbp+340h+Size]
0x1800599e7  mov     r14d, 400h
0x1800599ed  cmp     [rbp+340h+Size], r14
0x1800599f4  jz      short loc_1800599B7
0x1800599f6  lea     rdx, [rsp+440h+var_410]
0x1800599fb  mov     rcx, rsi
0x1800599fe  call    RtlAllocateLBlob
0x180059a03  mov     esi, eax
0x180059a05  test    eax, eax
0x180059a07  js      short loc_18005998D
0x180059a09  mov     rcx, [rdi]
0x180059a0c  lea     r8, [rbp+340h+var_38]
0x180059a13  lea     rdx, _GUID_55eab610_3945_4595_b7f9_75bebf9486f4
0x180059a1a  mov     [rsp+440h+var_3F8], r15
0x180059a1f  mov     [rbp+340h+var_38], r15
0x180059a26  mov     rax, [rcx]
0x180059a29  mov     rax, [rax+8]
0x180059a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a32  mov     esi, eax
0x180059a34  test    eax, eax
0x180059a36  js      short loc_180059A57
0x180059a38  mov     rcx, [rbp+340h+var_38]
0x180059a3f  test    rcx, rcx
0x180059a42  jnz     short loc_180059A4B
0x180059a44  mov     esi, 0C00002B9h
0x180059a49  jmp     short loc_180059A57
0x180059a4b  mov     [rsp+440h+var_3F8], rcx
0x180059a50  mov     [rbp+340h+var_38], r15
0x180059a57  lea     rcx, [rbp+340h+var_38]
0x180059a5e  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180059a63  test    esi, esi
0x180059a65  jns     short loc_180059A76
0x180059a67  lea     rcx, [rsp+440h+var_3F8]
0x180059a6c  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180059a71  jmp     loc_18005998D
0x180059a76  mov     r15, [rsp+440h+var_400]
0x180059a7b  mov     rsi, qword ptr [rsp+440h+var_410]
0x180059a80  mov     rcx, [rdi]
0x180059a83  lea     r9, [rbp+340h+Size]
0x180059a8a  mov     r8, [rsp+440h+Src]
0x180059a8f  mov     rdx, r14
0x180059a92  mov     rax, [rcx]
0x180059a95  mov     rax, [rax+10h]
0x180059a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a9e  mov     r14d, eax
0x180059aa1  test    eax, eax
0x180059aa3  js      short loc_180059AFA
0x180059aa5  mov     rax, [rbp+340h+Size]
0x180059aac  test    rax, rax
0x180059aaf  jz      short loc_180059AD1
0x180059ab1  mov     rdx, [rsp+440h+Src]; Src
0x180059ab6  lea     rcx, [r15+rsi]; void *
0x180059aba  mov     r8, rax; Size
0x180059abd  call    memmove
0x180059ac2  mov     rax, [rbp+340h+Size]
0x180059ac9  add     rsi, rax
0x180059acc  mov     qword ptr [rsp+440h+var_410], rsi
0x180059ad1  mov     r14d, 400h
0x180059ad7  cmp     rax, r14
0x180059ada  jz      short loc_180059A80
0x180059adc  lea     rcx, [rsp+440h+var_3F8]
0x180059ae1  lea     rdi, [rsp+440h+var_410]
0x180059ae6  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180059aeb  lea     rcx, [rsp+440h+var_3E8]
0x180059af0  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059af5  xor     r15d, r15d
0x180059af8  jmp     short loc_180059B2F
0x180059afa  lea     rcx, [rsp+440h+var_3F8]
0x180059aff  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180059b04  lea     rcx, [rsp+440h+var_3E8]
0x180059b09  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059b0e  lea     rcx, [rbp+340h+var_50]
0x180059b15  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059b1a  lea     rcx, [rsp+440h+var_410]
0x180059b1f  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059b24  mov     ebx, r14d
0x180059b27  jmp     loc_180059E63
0x180059b2c  mov     rdi, [rdi]
0x180059b2f  cmp     [rbx+31h], r15b
0x180059b33  jnz     short loc_180059B3F
0x180059b35  cmp     [rbx+32h], r15b
0x180059b39  jz      loc_180059D9B
0x180059b3f  mov     rax, [rdi+10h]
0x180059b43  lea     rcx, [rbp+340h+var_210]; void *
0x180059b4a  mov     [rbp+340h+var_248], rax
0x180059b51  xorps   xmm0, xmm0
0x180059b54  mov     rax, [rdi]
0x180059b57  xor     edx, edx; Val
0x180059b59  mov     [rbp+340h+var_240], rax
0x180059b60  mov     r8d, 160h; Size
0x180059b66  xor     eax, eax
0x180059b68  mov     [rbp+340h+var_250], 40h ; '@'
0x180059b73  mov     [rbp+340h+var_218], rax
0x180059b7a  movups  [rbp+340h+var_238], xmm0
0x180059b81  movups  [rbp+340h+var_228], xmm0
0x180059b88  call    memset
0x180059b8d  lea     rdx, [rbp+340h+var_250]
0x180059b94  mov     [rsp+440h+var_3F0], r15
0x180059b99  lea     rcx, [rbp+340h+var_210]
0x180059ba0  call    RtlXmlInitializeTokenization
0x180059ba5  mov     r8d, eax
0x180059ba8  test    eax, eax
0x180059baa  jns     short loc_180059C02
0x180059bac  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180059bb3  mov     [rbp+340h+var_2E8], 1061h
0x180059bbb  mov     [rbp+340h+var_2F8], rax
0x180059bbf  lea     rdx, [rbp+340h+var_2F8]
0x180059bc3  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180059bca  mov     [rbp+340h+var_2F0], rax
0x180059bce  lea     rax, aRtlxmlinitiali_2; "RtlXmlInitializeTokenization(&Tokenizer"...
0x180059bd5  mov     [rbp+340h+var_2E0], rax
0x180059bd9  lea     rcx, [rbp+340h+var_60]
0x180059be0  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180059be5  mov     ebx, eax
0x180059be7  lea     rcx, [rbp+340h+var_50]
0x180059bee  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059bf3  lea     rcx, [rsp+440h+var_410]
0x180059bf8  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180059bfd  jmp     loc_180059E63
0x180059c02  lea     rdx, [rsp+440h+var_3F0]
0x180059c07  lea     rcx, [rbp+340h+var_210]
0x180059c0e  call    RtlXmlDetermineStreamEncoding
0x180059c13  mov     r8d, eax
  ... truncated ...
```
