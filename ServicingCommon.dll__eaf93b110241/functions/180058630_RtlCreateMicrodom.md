# RtlCreateMicrodom

- ea: `0x180058630`
- end: `0x180058db3`
- name: `RtlCreateMicrodom`
- size: `1923`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005bde0`

## callees

- `0x1800032b0`
- `0x180003520`
- `0x180006060`
- `0x18000b410`
- `0x180010c10`
- `0x180015630`
- `0x18001a8a0`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x1800539e0`
- `0x180053bc8`
- `0x180057eb4`
- `0x180058630`
- `0x180099cb0`
- `0x18009a070`
- `0x1800a0020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180058d46`
- `ntdll!RtlRaiseStatus` at `0x180058d46`

## string_xrefs

- `0x1800586a3`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058707`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005875b`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005879b`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800587d6`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005888b`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058af5`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058b60`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058ba9`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058c24`: `onecore\base\xml\udom_microdom.cpp`
- `0x180058cef`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800586c3`: `RtlCreateMicrodom`
- `0x180058721`: `RtlCreateMicrodom`
- `0x180058772`: `RtlCreateMicrodom`
- `0x1800587b2`: `RtlCreateMicrodom`
- `0x1800587ed`: `RtlCreateMicrodom`
- `0x1800588a2`: `RtlCreateMicrodom`
- `0x180058b0c`: `RtlCreateMicrodom`
- `0x180058b75`: `RtlCreateMicrodom`
- `0x180058bbe`: `RtlCreateMicrodom`
- `0x180058c39`: `RtlCreateMicrodom`
- `0x180058d0a`: `RtlCreateMicrodom`
- `0x18005872d`: `(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Xml)`
- `0x18005877d`: `(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Blob)`
- `0x180058b17`: `RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)`
- `0x180058b81`: `RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodom(__int64 a1, __int64 a2)
{
  __int128 *v4; // rdx
  int v5; // eax
  __int128 *v6; // rdx
  int v7; // ecx
  __int64 **v8; // rdi
  _QWORD **v9; // rdx
  _QWORD *v10; // rcx
  int v11; // esi
  int BinaryMicrodomFromXml; // ebx
  __int64 v13; // rsi
  int v14; // r14d
  __int64 *v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rsi
  size_t v18; // rax
  __int64 *v19; // rdi
  int v20; // eax
  __int64 v21; // r8
  __int64 *v22; // rdx
  int v23; // eax
  __int128 v24; // xmm1
  int v25; // r8d
  int v26; // edi
  __int64 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h]
  const char *v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  const char *v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  _BYTE v38[24]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v39[4]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v40[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v41[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v42[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v43[5]; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v44[88]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v45; // [rsp+2C0h] [rbp+1C0h] BYREF
  void *Src; // [rsp+2D0h] [rbp+1D0h]
  const char *v47; // [rsp+2D8h] [rbp+1D8h]
  _OWORD v48[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v49; // [rsp+300h] [rbp+200h]
  __int64 v50; // [rsp+310h] [rbp+210h]
  int v51; // [rsp+318h] [rbp+218h] BYREF
  size_t Size; // [rsp+320h] [rbp+220h] BYREF
  __int128 v53; // [rsp+328h] [rbp+228h] BYREF
  __int64 v54; // [rsp+338h] [rbp+238h]

  v51 = 0;
  v50 = 0;
  memset(v38, 0, sizeof(v38));
  memset(v48, 0, sizeof(v48));
  v49 = 0;
  if ( !a1 )
  {
    Src = (void *)4096;
    *(_QWORD *)&v45 = "onecore\\base\\xml\\udom_microdom.cpp";
    v4 = &v45;
    *((_QWORD *)&v45 + 1) = "RtlCreateMicrodom";
    v47 = "Not-null check failed: Params";
LABEL_3:
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v51,
           v4);
LABEL_75:
    BinaryMicrodomFromXml = v5;
    goto LABEL_76;
  }
  v5 = Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom>::Initialize();
  if ( v5 < 0 )
    goto LABEL_75;
  if ( *(_DWORD *)a1 >= 2u )
  {
    v30 = 4102;
    *(_QWORD *)&v29 = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = &v29;
    *((_QWORD *)&v29 + 1) = "RtlCreateMicrodom";
    v31 = "(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::"
          "Microdom::Rtl::CreateMicrodomSource::Xml)";
LABEL_7:
    v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v51,
           v6);
    goto LABEL_75;
  }
  v7 = *(_DWORD *)(a1 + 4);
  if ( v7 )
  {
    if ( v7 != 2 && v7 != 1 )
    {
      v39[2] = 4107;
      v39[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v6 = (__int128 *)v39;
      v39[1] = "RtlCreateMicrodom";
      v39[3] = "(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Wi"
               "ndows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rt"
               "l::CreateMicrodomSource::Blob)";
      goto LABEL_7;
    }
    v8 = (__int64 **)(a1 + 8);
    v9 = (_QWORD **)(a1 + 8);
    if ( v7 == 1 && !*v8 )
    {
      v40[2] = 4113;
      v40[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v4 = (__int128 *)v40;
      v40[1] = "RtlCreateMicrodom";
      v40[3] = "Not-null check failed: Params->Source.pBlob";
      goto LABEL_3;
    }
  }
  else
  {
    v8 = (__int64 **)(a1 + 8);
    if ( !*(_QWORD *)(a1 + 8) )
    {
      v41[2] = 4110;
      v41[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v4 = (__int128 *)v41;
      v41[1] = "RtlCreateMicrodom";
      v41[3] = "Not-null check failed: Params->Source.pIStream";
      goto LABEL_3;
    }
    v9 = (_QWORD **)(a1 + 8);
  }
  v50 = 0;
  LOBYTE(v50) = *(_BYTE *)(a1 + 48);
  memset(v48, 0, sizeof(v48));
  v49 = 0;
  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
      goto LABEL_72;
    v30 = 0;
    v54 = 0;
    v29 = 0;
    v53 = 0;
    if ( !v7 )
    {
      Size = 0;
      Src = 0;
      v45 = 0;
      v11 = RtlAllocateLBlob(1024, &v45);
      if ( v11 >= 0 )
      {
        v13 = 0;
        while ( 1 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, void *, size_t *))(**v8 + 16))(*v8, 1024, Src, &Size);
          if ( v14 < 0 )
            break;
          v13 += Size;
          if ( Size != 1024 )
          {
            v11 = RtlAllocateLBlob(v13, &v29);
            if ( v11 < 0 )
              goto LABEL_27;
            v15 = *v8;
            v28 = 0;
            v11 = Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlROFOStream>(v15, &v28);
            if ( v11 < 0 )
            {
              Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v28);
              goto LABEL_27;
            }
            v16 = v30;
            v17 = v29;
            while ( 1 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, void *, size_t *))(**v8 + 16))(*v8, 1024, Src, &Size);
              if ( v14 < 0 )
                break;
              v18 = Size;
              if ( Size )
              {
                memmove((void *)(v16 + v17), Src, Size);
                v18 = Size;
                v17 += Size;
                *(_QWORD *)&v29 = v17;
              }
              if ( v18 != 1024 )
              {
                v19 = (__int64 *)&v29;
                Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v28);
                Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v45);
                goto LABEL_43;
              }
            }
            Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v28);
            break;
          }
        }
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v45);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v53);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v29);
        BinaryMicrodomFromXml = v14;
      }
      else
      {
LABEL_27:
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v45);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v53);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v29);
        BinaryMicrodomFromXml = v11;
      }
      goto LABEL_76;
    }
    v19 = *v8;
LABEL_43:
    if ( *(_BYTE *)(a1 + 49) || *(_BYTE *)(a1 + 50) )
    {
      v33 = (const char *)v19[2];
      v34 = *v19;
      v32 = 64;
      v37 = 0;
      v35 = 0;
      v36 = 0;
      memset(v44, 0, sizeof(v44));
      v28 = 0;
      v20 = RtlXmlInitializeTokenization(v44, &v32);
      v21 = (unsigned int)v20;
      if ( v20 < 0 )
      {
        v43[2] = 4193;
        v43[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v22 = v43;
        v43[1] = "RtlCreateMicrodom";
        v43[3] = "RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)";
LABEL_47:
        BinaryMicrodomFromXml = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                                  &v51,
                                  v22,
                                  v21);
LABEL_48:
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v53);
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v29);
LABEL_76:
        Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(v38);
        return (unsigned int)BinaryMicrodomFromXml;
      }
      v23 = RtlXmlDetermineStreamEncoding(v44, &v28, (unsigned int)v20);
      v21 = (unsigned int)v23;
      if ( v23 < 0 )
      {
        v34 = 4194;
        v32 = (__int64)"onecore\\base\\xml\\udom_microdom.cpp";
        v33 = "RtlCreateMicrodom";
        *(_QWORD *)&v35 = "RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)";
LABEL_51:
        v22 = &v32;
        goto LABEL_47;
      }
      if ( v44[12] != 5 )
      {
        if ( *(_BYTE *)(a1 + 49) )
        {
          v34 = 4198;
          v32 = (__int64)"onecore\\base\\xml\\udom_microdom.cpp";
          v33 = "RtlCreateMicrodom";
          *(_QWORD *)&v35 = "Params->fRequireUtf8";
LABEL_55:
          v21 = 3221225485LL;
          goto LABEL_51;
        }
        v24 = *(_OWORD *)v19;
        Src = (void *)(v28 + v19[2]);
        *(_QWORD *)&v45 = v24 - v28;
        *((_QWORD *)&v45 + 1) = v24 - v28;
        switch ( v44[12] )
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
            v34 = 4221;
            v32 = (__int64)"onecore\\base\\xml\\udom_microdom.cpp";
            v33 = "RtlCreateMicrodom";
            *(_QWORD *)&v35 = 0;
            goto LABEL_55;
        }
        v26 = RtlTranscodeLBlobs(5, 0, v25, (unsigned int)&v45, 106, (__int64)&v53);
        if ( v26 < 0 )
        {
          Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v53);
          Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v29);
          BinaryMicrodomFromXml = v26;
          goto LABEL_76;
        }
        v19 = (__int64 *)&v53;
      }
    }
    BinaryMicrodomFromXml = MicrodomImplementation::CreateBinaryMicrodomFromXml(*(_QWORD *)(a1 + 40), v9, v19, v38);
    if ( BinaryMicrodomFromXml < 0 )
      goto LABEL_48;
    *(_QWORD *)&v48[0] = *(_QWORD *)v38;
    *(_OWORD *)((char *)v48 + 8) = *(_OWORD *)&v38[8];
    if ( *(_QWORD *)v38 )
    {
      Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v53);
      Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v29);
      goto LABEL_72;
    }
    v34 = 4251;
    v32 = (__int64)"onecore\\base\\xml\\udom_microdom.cpp";
    v21 = 3221266563LL;
    *(_QWORD *)&v35 = 0;
    v33 = "RtlCreateMicrodom";
    goto LABEL_51;
  }
  if ( v7 == 1 )
  {
    v10 = *v9;
    *(_QWORD *)&v48[0] = **v9;
    *(_OWORD *)((char *)v48 + 8) = *(_OWORD *)(v10 + 1);
  }
  else
  {
    if ( v7 != 2 )
    {
      v42[2] = 4133;
      v42[0] = "onecore\\base\\xml\\udom_microdom.cpp";
      v42[3] = 0;
      v42[1] = "RtlCreateMicrodom";
      v5 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v51,
             v42,
             3221225474LL);
      goto LABEL_75;
    }
    *((_QWORD *)&v48[1] + 1) = *v9;
    v49 = *(_OWORD *)(a1 + 16);
  }
LABEL_72:
  if ( dword_1800D4B08 != 2 )
    RtlRaiseStatus(-1073741595);
  v5 = Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CMicrodom>::CreateInstance<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff,MicrodomImplementation::MdCreateParams,Windows::Microdom::Rtl::IRtlMicrodom>(
         MicrodomImplementation::g_OneShotMicrodomInit,
         v48,
         a2);
  if ( v5 < 0 )
    goto LABEL_75;
  Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(v38);
  return 0;
}

```

## disassembly

```asm
0x180058630  mov     [rsp-8+arg_10], rbx
0x180058635  mov     [rsp-8+arg_18], rsi
0x18005863a  push    rbp
0x18005863b  push    rdi
0x18005863c  push    r12
0x18005863e  push    r13
0x180058640  push    r14
0x180058642  lea     rbp, [rsp-250h]
0x18005864a  sub     rsp, 350h
0x180058651  mov     rax, cs:__security_cookie
0x180058658  xor     rax, rsp
0x18005865b  mov     [rbp+270h+var_30], rax
0x180058662  xor     eax, eax
0x180058664  xorps   xmm1, xmm1
0x180058667  xor     r12d, r12d
0x18005866a  mov     [rbp+270h+var_2C0], rax
0x18005866e  mov     [rbp+270h+var_58], r12d
0x180058675  xorps   xmm0, xmm0
0x180058678  mov     [rbp+270h+var_60], rax
0x18005867f  mov     r13, rdx
0x180058682  mov     rbx, rcx
0x180058685  movups  [rbp+270h+var_2D0], xmm0
0x180058689  movups  [rbp+270h+var_90], xmm1
0x180058690  movups  [rbp+270h+var_80], xmm1
0x180058697  movups  [rbp+270h+var_70], xmm1
0x18005869e  test    rcx, rcx
0x1800586a1  jnz     short loc_1800586F0
0x1800586a3  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800586aa  mov     [rbp+270h+Src], 1000h
0x1800586b5  mov     qword ptr [rbp+270h+var_B0], rax
0x1800586bc  lea     rdx, [rbp+270h+var_B0]
0x1800586c3  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x1800586ca  mov     qword ptr [rbp+270h+var_B0+8], rax
0x1800586d1  lea     rax, aNotNullCheckFa_12; "Not-null check failed: Params"
0x1800586d8  mov     [rbp+270h+var_98], rax
0x1800586df  lea     rcx, [rbp+270h+var_58]
0x1800586e6  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800586eb  jmp     loc_180058D6D
0x1800586f0  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom>::Initialize(void)
0x1800586f5  test    eax, eax
0x1800586f7  js      loc_180058D6D
0x1800586fd  cmp     [rbx], r12d
0x180058700  jz      short loc_18005874A
0x180058702  cmp     dword ptr [rbx], 1
0x180058705  jz      short loc_18005874A
0x180058707  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005870e  mov     [rsp+370h+var_328], 1006h
0x180058717  mov     qword ptr [rsp+370h+var_338], rax
0x18005871c  lea     rdx, [rsp+370h+var_338]
0x180058721  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180058728  mov     qword ptr [rsp+370h+var_338+8], rax
0x18005872d  lea     rax, aParamsInputtyp; "(Params->InputType == Windows::Microdom"...
0x180058734  mov     [rsp+370h+var_320], rax
0x180058739  lea     rcx, [rbp+270h+var_58]
0x180058740  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180058745  jmp     loc_180058D6D
0x18005874a  mov     ecx, [rbx+4]
0x18005874d  test    ecx, ecx
0x18005874f  jz      short loc_1800587CD
0x180058751  cmp     ecx, 2
0x180058754  jz      short loc_18005878A
0x180058756  cmp     ecx, 1
0x180058759  jz      short loc_18005878A
0x18005875b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058762  mov     [rbp+270h+var_2A8], 100Bh
0x18005876a  mov     [rbp+270h+var_2B8], rax
0x18005876e  lea     rdx, [rbp+270h+var_2B8]
0x180058772  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180058779  mov     [rbp+270h+var_2B0], rax
0x18005877d  lea     rax, aParamsSourcety; "(Params->SourceType == Windows::Microdo"...
0x180058784  mov     [rbp+270h+var_2A0], rax
0x180058788  jmp     short loc_180058739
0x18005878a  lea     rdi, [rbx+8]
0x18005878e  mov     rdx, rdi
0x180058791  cmp     ecx, 1
0x180058794  jnz     short loc_18005880B
0x180058796  cmp     [rdi], r12
0x180058799  jnz     short loc_18005880B
0x18005879b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800587a2  mov     [rbp+270h+var_288], 1011h
0x1800587aa  mov     [rbp+270h+var_298], rax
0x1800587ae  lea     rdx, [rbp+270h+var_298]
0x1800587b2  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x1800587b9  mov     [rbp+270h+var_290], rax
0x1800587bd  lea     rax, aNotNullCheckFa_3; "Not-null check failed: Params->Source.p"...
0x1800587c4  mov     [rbp+270h+var_280], rax
0x1800587c8  jmp     loc_1800586DF
0x1800587cd  lea     rdi, [rbx+8]
0x1800587d1  cmp     [rdi], r12
0x1800587d4  jnz     short loc_180058808
0x1800587d6  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800587dd  mov     [rbp+270h+var_268], 100Eh
0x1800587e5  mov     [rbp+270h+var_278], rax
0x1800587e9  lea     rdx, [rbp+270h+var_278]
0x1800587ed  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x1800587f4  mov     [rbp+270h+var_270], rax
0x1800587f8  lea     rax, aNotNullCheckFa_98; "Not-null check failed: Params->Source.p"...
0x1800587ff  mov     [rbp+270h+var_260], rax
0x180058803  jmp     loc_1800586DF
0x180058808  mov     rdx, rdi
0x18005880b  xor     eax, eax
0x18005880d  xorps   xmm0, xmm0
0x180058810  mov     [rbp+270h+var_60], rax
0x180058817  mov     al, [rbx+30h]
0x18005881a  mov     byte ptr [rbp+270h+var_60], al
0x180058820  movups  [rbp+270h+var_90], xmm0
0x180058827  movups  [rbp+270h+var_80], xmm0
0x18005882e  movups  [rbp+270h+var_70], xmm0
0x180058835  cmp     [rbx], r12d
0x180058838  jnz     loc_1800588C8
0x18005883e  cmp     ecx, 1
0x180058841  jnz     short loc_180058861
0x180058843  mov     rcx, [rdx]
0x180058846  mov     rax, [rcx]
0x180058849  mov     qword ptr [rbp+270h+var_90], rax
0x180058850  movups  xmm0, xmmword ptr [rcx+8]
0x180058854  movdqu  [rbp+270h+var_90+8], xmm0
0x18005885c  jmp     loc_180058D36
0x180058861  cmp     ecx, 2
0x180058864  jnz     short loc_18005888B
0x180058866  mov     rax, [rdx]
0x180058869  mov     qword ptr [rbp+270h+var_80+8], rax
0x180058870  mov     rax, [rbx+10h]
0x180058874  mov     qword ptr [rbp+270h+var_70], rax
0x18005887b  mov     rax, [rbx+18h]
0x18005887f  mov     qword ptr [rbp+270h+var_70+8], rax
0x180058886  jmp     loc_180058D36
0x18005888b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058892  mov     [rbp+270h+var_248], 1025h
0x18005889a  mov     [rbp+270h+var_258], rax
0x18005889e  lea     rdx, [rbp+270h+var_258]
0x1800588a2  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x1800588a9  mov     [rbp+270h+var_240], r12
0x1800588ad  mov     r8d, 0C0000002h
0x1800588b3  mov     [rbp+270h+var_250], rax
0x1800588b7  lea     rcx, [rbp+270h+var_58]
0x1800588be  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800588c3  jmp     loc_180058D6D
0x1800588c8  cmp     dword ptr [rbx], 1
0x1800588cb  jnz     loc_180058D36
0x1800588d1  xor     eax, eax
0x1800588d3  xorps   xmm1, xmm1
0x1800588d6  mov     [rsp+370h+var_328], rax
0x1800588db  mov     [rbp+270h+var_38], rax
0x1800588e2  movups  [rsp+370h+var_338], xmm0
0x1800588e7  movups  [rbp+270h+var_48], xmm1
0x1800588ee  test    ecx, ecx
0x1800588f0  jnz     loc_180058A8B
0x1800588f6  mov     r14d, 400h
0x1800588fc  mov     [rbp+270h+Size], r12
0x180058903  mov     ecx, r14d
0x180058906  mov     [rbp+270h+Src], rax
0x18005890d  lea     rdx, [rbp+270h+var_B0]
0x180058914  movups  [rbp+270h+var_B0], xmm0
0x18005891b  call    RtlAllocateLBlob
0x180058920  mov     esi, eax
0x180058922  test    eax, eax
0x180058924  jns     short loc_18005894F
0x180058926  lea     rcx, [rbp+270h+var_B0]
0x18005892d  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058932  lea     rcx, [rbp+270h+var_48]
0x180058939  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x18005893e  lea     rcx, [rsp+370h+var_338]
0x180058943  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058948  mov     ebx, esi
0x18005894a  jmp     loc_180058D6F
0x18005894f  mov     rsi, r12
0x180058952  mov     rcx, [rdi]
0x180058955  lea     r9, [rbp+270h+Size]
0x18005895c  mov     r8, [rbp+270h+Src]
0x180058963  mov     rdx, r14
0x180058966  mov     rax, [rcx]
0x180058969  mov     rax, [rax+10h]
0x18005896d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058972  mov     r14d, eax
0x180058975  test    eax, eax
0x180058977  js      loc_180058A61
0x18005897d  add     rsi, [rbp+270h+Size]
0x180058984  mov     r14d, 400h
0x18005898a  cmp     [rbp+270h+Size], r14
0x180058991  jz      short loc_180058952
0x180058993  lea     rdx, [rsp+370h+var_338]
0x180058998  mov     rcx, rsi
0x18005899b  call    RtlAllocateLBlob
0x1800589a0  mov     esi, eax
0x1800589a2  test    eax, eax
0x1800589a4  js      short loc_180058926
0x1800589a6  mov     rcx, [rdi]
0x1800589a9  lea     rdx, [rsp+370h+var_340]
0x1800589ae  mov     [rsp+370h+var_340], r12
0x1800589b3  call    ??$CreateRequiredInterface@UIRtlROFOStream@Rtl@Windows@@@IRtlObject@Rtl@Windows@@QEAAJPEAV?$Auto@PEAUIRtlROFOStream@Rtl@Windows@@@2@@Z; Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlROFOStream>(Windows::Auto<Windows::Rtl::IRtlROFOStream *> *)
0x1800589b8  mov     esi, eax
0x1800589ba  test    eax, eax
0x1800589bc  jns     short loc_1800589CD
0x1800589be  lea     rcx, [rsp+370h+var_340]
0x1800589c3  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800589c8  jmp     loc_180058926
0x1800589cd  mov     r12, [rsp+370h+var_328]
0x1800589d2  mov     rsi, qword ptr [rsp+370h+var_338]
0x1800589d7  mov     rcx, [rdi]
0x1800589da  lea     r9, [rbp+270h+Size]
0x1800589e1  mov     r8, [rbp+270h+Src]
0x1800589e8  mov     rdx, r14
0x1800589eb  mov     rax, [rcx]
0x1800589ee  mov     rax, [rax+10h]
0x1800589f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589f7  mov     r14d, eax
0x1800589fa  test    eax, eax
0x1800589fc  js      short loc_180058A57
0x1800589fe  mov     rax, [rbp+270h+Size]
0x180058a05  test    rax, rax
0x180058a08  jz      short loc_180058A2C
0x180058a0a  mov     rdx, [rbp+270h+Src]; Src
0x180058a11  lea     rcx, [r12+rsi]; void *
0x180058a15  mov     r8, rax; Size
0x180058a18  call    memmove
0x180058a1d  mov     rax, [rbp+270h+Size]
0x180058a24  add     rsi, rax
0x180058a27  mov     qword ptr [rsp+370h+var_338], rsi
0x180058a2c  mov     r14d, 400h
0x180058a32  cmp     rax, r14
0x180058a35  jz      short loc_1800589D7
0x180058a37  lea     rcx, [rsp+370h+var_340]
0x180058a3c  lea     rdi, [rsp+370h+var_338]
0x180058a41  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180058a46  lea     rcx, [rbp+270h+var_B0]
0x180058a4d  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058a52  xor     r12d, r12d
0x180058a55  jmp     short loc_180058A8E
0x180058a57  lea     rcx, [rsp+370h+var_340]
0x180058a5c  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180058a61  lea     rcx, [rbp+270h+var_B0]
0x180058a68  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058a6d  lea     rcx, [rbp+270h+var_48]
0x180058a74  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058a79  lea     rcx, [rsp+370h+var_338]
0x180058a7e  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058a83  mov     ebx, r14d
0x180058a86  jmp     loc_180058D6F
0x180058a8b  mov     rdi, [rdi]
0x180058a8e  cmp     [rbx+31h], r12b
0x180058a92  jnz     short loc_180058A9E
0x180058a94  cmp     [rbx+32h], r12b
0x180058a98  jz      loc_180058CB9
0x180058a9e  mov     rax, [rdi+10h]
0x180058aa2  lea     rcx, [rbp+270h+var_210]; void *
0x180058aa6  mov     [rsp+370h+var_308], rax
0x180058aab  xorps   xmm0, xmm0
0x180058aae  mov     rax, [rdi]
0x180058ab1  xor     edx, edx; Val
0x180058ab3  mov     [rsp+370h+var_300], rax
0x180058ab8  mov     r8d, 160h; Size
0x180058abe  xor     eax, eax
0x180058ac0  mov     [rsp+370h+var_310], 40h ; '@'
0x180058ac9  mov     [rbp+270h+var_2D8], rax
0x180058acd  movups  [rsp+370h+var_2F8], xmm0
0x180058ad2  movups  [rbp+270h+var_2E8], xmm0
0x180058ad6  call    memset
0x180058adb  lea     rdx, [rsp+370h+var_310]
0x180058ae0  mov     [rsp+370h+var_340], r12
0x180058ae5  lea     rcx, [rbp+270h+var_210]
0x180058ae9  call    RtlXmlInitializeTokenization
0x180058aee  mov     r8d, eax
0x180058af1  test    eax, eax
0x180058af3  jns     short loc_180058B4B
0x180058af5  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058afc  mov     [rbp+270h+var_228], 1061h
0x180058b04  mov     [rbp+270h+var_238], rax
0x180058b08  lea     rdx, [rbp+270h+var_238]
0x180058b0c  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180058b13  mov     [rbp+270h+var_230], rax
0x180058b17  lea     rax, aRtlxmlinitiali_2; "RtlXmlInitializeTokenization(&Tokenizer"...
0x180058b1e  mov     [rbp+270h+var_220], rax
0x180058b22  lea     rcx, [rbp+270h+var_58]
0x180058b29  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180058b2e  mov     ebx, eax
0x180058b30  lea     rcx, [rbp+270h+var_48]
0x180058b37  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058b3c  lea     rcx, [rsp+370h+var_338]
0x180058b41  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x180058b46  jmp     loc_180058D6F
0x180058b4b  lea     rdx, [rsp+370h+var_340]
0x180058b50  lea     rcx, [rbp+270h+var_210]
0x180058b54  call    RtlXmlDetermineStreamEncoding
0x180058b59  mov     r8d, eax
0x180058b5c  test    eax, eax
0x180058b5e  jns     short loc_180058B94
0x180058b60  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180058b67  mov     [rsp+370h+var_300], 1062h
0x180058b70  mov     [rsp+370h+var_310], rax
0x180058b75  lea     rax, aRtlcreatemicro_1; "RtlCreateMicrodom"
0x180058b7c  mov     [rsp+370h+var_308], rax
0x180058b81  lea     rax, aRtlxmldetermin_0; "RtlXmlDetermineStreamEncoding(&Tokenize"...
0x180058b88  mov     qword ptr [rsp+370h+var_2F8], rax
0x180058b8d  lea     rdx, [rsp+370h+var_310]
0x180058b92  jmp     short loc_180058B22
0x180058b94  mov     ecx, [rbp+270h+var_1E0]
0x180058b9a  cmp     ecx, 5
0x180058b9d  jz      loc_180058CB9
0x180058ba3  cmp     [rbx+31h], r12b
  ... truncated ...
```
