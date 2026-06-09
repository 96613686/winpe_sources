# RtlCreateMicrodom

- ea: `0x14006db80`
- end: `0x14006e64f`
- name: `RtlCreateMicrodom`
- size: `2767`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140060b80`
- `0x140060da0`
- `0x140065918`

## callees

- `0x140002116`
- `0x140002326`
- `0x1400663c8`
- `0x14006db80`
- `0x140071100`
- `0x140071e0c`
- `0x140072764`
- `0x140075e48`
- `0x14007be10`
- `0x14007c0e8`
- `0x14007d9b4`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x14006e642`
- `ntdll!RtlRaiseStatus` at `0x14006e642`
- `ntdll!NtYieldExecution` at `0x14006dca4`
- `ntdll!NtYieldExecution` at `0x14006dca4`

## string_xrefs

- `0x14006dbd2`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006dcd9`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006dd1d`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006dd5a`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006dd93`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006de49`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006e19a`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006e2be`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006e2fd`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006e38e`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006e517`: `onecore\base\xml\udom_microdom.cpp`
- `0x14006dbeb`: `RtlCreateMicrodom`
- `0x14006dcf2`: `RtlCreateMicrodom`
- `0x14006dd36`: `RtlCreateMicrodom`
- `0x14006dd73`: `RtlCreateMicrodom`
- `0x14006ddac`: `RtlCreateMicrodom`
- `0x14006de69`: `RtlCreateMicrodom`
- `0x14006e1af`: `RtlCreateMicrodom`
- `0x14006e2d3`: `RtlCreateMicrodom`
- `0x14006e312`: `RtlCreateMicrodom`
- `0x14006e3a3`: `RtlCreateMicrodom`
- `0x14006e52e`: `RtlCreateMicrodom`
- `0x14006dd00`: `(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Xml)`
- `0x14006dd44`: `(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Blob)`
- `0x14006e1bb`: `RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)`
- `0x14006e2df`: `RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)`

## pseudocode

```c
__int64 __fastcall RtlCreateMicrodom(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  const char *v5; // rax
  signed __int32 v7; // eax
  int v8; // ecx
  __int64 v9; // rax
  __int128 *v10; // r12
  __int64 v11; // rsi
  __int64 v12; // rbx
  int v13; // r14d
  void *v14; // r14
  int v15; // r12d
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  void (__fastcall ***v19)(_QWORD); // rbx
  int v20; // esi
  void (__fastcall ***v21)(_QWORD); // rcx
  __int64 v22; // r12
  int v23; // r13d
  size_t v24; // rax
  __int64 v25; // rdx
  const char *v26; // rax
  __int64 v27; // rax
  int v28; // r8d
  __int64 v29; // rdx
  signed __int32 v30[8]; // [rsp+0h] [rbp-100h] BYREF
  __int128 v31; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h]
  const char *v33; // [rsp+48h] [rbp-B8h]
  __int128 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  const char *v36; // [rsp+68h] [rbp-98h]
  _QWORD *v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  const char *v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int128 v41; // [rsp+98h] [rbp-68h]
  __int128 v42; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  _BYTE v44[48]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v45; // [rsp+F0h] [rbp-10h]
  __int128 v46; // [rsp+220h] [rbp+120h] BYREF
  void *Src; // [rsp+230h] [rbp+130h]
  const char *v48; // [rsp+238h] [rbp+138h]
  __int128 v49; // [rsp+240h] [rbp+140h] BYREF
  __int128 v50; // [rsp+250h] [rbp+150h]
  __int128 v51; // [rsp+260h] [rbp+160h]
  __int64 v52; // [rsp+270h] [rbp+170h]
  __int128 v53; // [rsp+278h] [rbp+178h] BYREF
  __int64 v54; // [rsp+288h] [rbp+188h]
  void (__fastcall ***v55)(_QWORD); // [rsp+290h] [rbp+190h] BYREF
  size_t Size; // [rsp+298h] [rbp+198h] BYREF

  v2 = 0;
  v37 = (_QWORD *)a2;
  v32 = 0;
  v3 = (_QWORD *)a2;
  v31 = 0;
  if ( !a1 )
  {
    Src = (void *)4096;
    *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
    v5 = "Not-null check failed: Params";
LABEL_3:
    v48 = v5;
    RtlReportErrorOrigination(&v46, a2, 3221225485LL);
    return 3221225485LL;
  }
  if ( dword_1400A5E30 != 2 )
  {
    _InterlockedOr(v30, 0);
    v7 = _InterlockedCompareExchange(&dword_1400A5E30, 1, 0);
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        while ( dword_1400A5E30 != 2 )
          NtYieldExecution();
      }
    }
    else
    {
      if ( MicrodomImplementation::g_OneShotMicrodomInit )
        goto LABEL_149;
      dword_1400A5E20 = 0;
      MicrodomImplementation::g_OneShotMicrodomInit = (__int64)&dword_1400A5E20;
      dword_1400A5E24 = 0;
      _InterlockedExchange(&dword_1400A5E30, 2);
    }
    _InterlockedOr(v30, 0);
  }
  if ( dword_1400A5E30 != 2 )
LABEL_149:
    RtlRaiseStatus(-1073741595);
  if ( *(_DWORD *)a1 >= 2u )
  {
    Src = (void *)4102;
    *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
    v5 = "(Params->InputType == Windows::Microdom::Rtl::CreateMicrodomSource::Binary) || (Params->InputType == Windows::M"
         "icrodom::Rtl::CreateMicrodomSource::Xml)";
    goto LABEL_3;
  }
  v8 = *(_DWORD *)(a1 + 4);
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      if ( v8 != 1 )
      {
        Src = (void *)4107;
        *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
        *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
        v5 = "(Params->SourceType == Windows::Microdom::Rtl::CreateMicrodomSource::Stream) || (Params->SourceType == Wind"
             "ows::Microdom::Rtl::CreateMicrodomSource::BlobProvider) || (Params->SourceType == Windows::Microdom::Rtl::C"
             "reateMicrodomSource::Blob)";
        goto LABEL_3;
      }
      if ( !*(_QWORD *)(a1 + 8) )
      {
        Src = (void *)4113;
        *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
        *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
        v5 = "Not-null check failed: Params->Source.pBlob";
        goto LABEL_3;
      }
    }
  }
  else if ( !*(_QWORD *)(a1 + 8) )
  {
    Src = (void *)4110;
    *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
    v5 = "Not-null check failed: Params->Source.pIStream";
    goto LABEL_3;
  }
  v52 = 0;
  LOBYTE(v52) = *(_BYTE *)(a1 + 48);
  v49 = 0;
  v50 = 0;
  v51 = 0;
  if ( !*(_DWORD *)a1 )
  {
    if ( v8 == 1 )
    {
      v9 = *(_QWORD *)(a1 + 8);
      v49 = *(_OWORD *)v9;
      *(_QWORD *)&v50 = *(_QWORD *)(v9 + 16);
    }
    else
    {
      if ( v8 != 2 )
      {
        Src = (void *)4133;
        *(_QWORD *)&v46 = "onecore\\base\\xml\\udom_microdom.cpp";
        v48 = 0;
        *((_QWORD *)&v46 + 1) = "RtlCreateMicrodom";
        RtlReportErrorOrigination(&v46, a2, 3221225474LL);
        return 3221225474LL;
      }
      *((_QWORD *)&v50 + 1) = *(_QWORD *)(a1 + 8);
      v51 = *(_OWORD *)(a1 + 16);
    }
LABEL_142:
    if ( dword_1400A5E30 == 2 )
    {
      v16 = Windows::Rtl::CRtlObjectTypeDescription<MicrodomImplementation::CMicrodom>::CreateInstance<MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff,MicrodomImplementation::MdCreateParams,Windows::Microdom::Rtl::IRtlMicrodom>(
              MicrodomImplementation::g_OneShotMicrodomInit,
              (const struct MicrodomImplementation::MdCreateParams *)&v49,
              v3);
      if ( v16 >= 0 )
      {
        if ( v2 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v2);
        return 0;
      }
      if ( v2 )
      {
        v17 = v2;
LABEL_50:
        anonymous_namespace_::OurRtlFreeStringRoutine(v17);
      }
      return (unsigned int)v16;
    }
    goto LABEL_149;
  }
  if ( *(_DWORD *)a1 != 1 )
    goto LABEL_142;
  v10 = *(__int128 **)(a1 + 8);
  v11 = 0;
  v35 = 0;
  v54 = 0;
  v34 = 0;
  v53 = 0;
  if ( v8 )
    goto LABEL_78;
  Size = 0;
  Src = 0;
  v12 = 0;
  v46 = 0;
  v13 = RtlAllocateLBlob(1024, &v46);
  if ( v13 < 0 )
  {
    if ( Src )
      anonymous_namespace_::OurRtlFreeStringRoutine(Src);
    if ( v54 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v54);
    return (unsigned int)v13;
  }
  v14 = Src;
  do
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, size_t *))(**(_QWORD **)(a1 + 8) + 16LL))(
            *(_QWORD *)(a1 + 8),
            1024,
            v14,
            &Size);
    if ( v15 < 0 )
    {
      if ( v14 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v14);
      if ( v54 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
      return (unsigned int)v15;
    }
    v12 += Size;
  }
  while ( Size == 1024 );
  v16 = RtlAllocateLBlob(v12, &v34);
  if ( v16 < 0 )
  {
    if ( v14 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v14);
    if ( v54 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(v54);
      Src = 0;
      v53 = 0;
      v54 = 0;
    }
    v17 = v35;
    goto LABEL_49;
  }
  v18 = *(_QWORD *)(a1 + 8);
  v55 = 0;
  v19 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, GUID *, void (__fastcall ****)(_QWORD)))(*(_QWORD *)v18 + 8LL))(
          v18,
          &GUID_55eab610_3945_4595_b7f9_75bebf9486f4,
          &v55);
  if ( v20 < 0 )
  {
    v21 = v55;
  }
  else
  {
    v19 = v55;
    if ( !v55 )
    {
      v20 = -1073741127;
LABEL_62:
      if ( v14 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v14);
      if ( v54 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
        Src = 0;
        v53 = 0;
        v54 = 0;
      }
      if ( v35 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v35);
      return (unsigned int)v20;
    }
    v21 = 0;
  }
  if ( v21 )
  {
    v55 = 0;
    (**v21)(v21);
  }
  if ( v20 < 0 )
  {
    if ( v19 )
      (**v19)(v19);
    goto LABEL_62;
  }
  v11 = v35;
  v22 = v34;
  do
  {
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, void *, size_t *))(**(_QWORD **)(a1 + 8) + 16LL))(
            *(_QWORD *)(a1 + 8),
            1024,
            v14,
            &Size);
    if ( v23 < 0 )
    {
      if ( v19 )
        (**v19)(v19);
      if ( v14 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v14);
      if ( v54 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
        Src = 0;
        v53 = 0;
        v54 = 0;
      }
      if ( v11 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v11);
      return (unsigned int)v23;
    }
    v24 = Size;
    if ( Size )
    {
      memcpy_0((void *)(v22 + v11), v14, Size);
      v24 = Size;
      v22 += Size;
      *(_QWORD *)&v34 = v22;
    }
  }
  while ( v24 == 1024 );
  v10 = &v34;
  if ( v19 )
    (**v19)(v19);
  if ( v14 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v14);
LABEL_78:
  if ( !*(_BYTE *)(a1 + 49) && !*(_BYTE *)(a1 + 50) )
    goto LABEL_123;
  v39 = (const char *)*((_QWORD *)v10 + 2);
  v40 = *(_QWORD *)v10;
  v38 = 64;
  v43 = 0;
  v41 = 0;
  v42 = 0;
  memset_0(v44, 0, 0x160u);
  v55 = 0;
  v16 = RtlXmlInitializeTokenization(v44, &v38);
  if ( v16 < 0 )
  {
    v32 = 4193;
    *(_QWORD *)&v31 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v31 + 1) = "RtlCreateMicrodom";
    v26 = "RtlXmlInitializeTokenization(&TokenizerState, &TokenizerInit)";
    goto LABEL_82;
  }
  v16 = RtlXmlDetermineStreamEncoding(v44, &v55);
  if ( v16 < 0 )
  {
    v32 = 4194;
    *(_QWORD *)&v31 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v31 + 1) = "RtlCreateMicrodom";
    v26 = "RtlXmlDetermineStreamEncoding(&TokenizerState, &EncodingLength)";
LABEL_82:
    v33 = v26;
    RtlReportErrorOrigination(&v31, v25, (unsigned int)v16);
    if ( v54 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(v54);
      Src = 0;
      v53 = 0;
      goto LABEL_84;
    }
    goto LABEL_85;
  }
  a2 = v45;
  if ( v45 == 5 )
  {
LABEL_123:
    v16 = MicrodomImplementation::CreateBinaryMicrodomFromXml(
            *(void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, int, __int128 *))(a1 + 40),
            a2,
            (__int64)v10,
            &v31);
    if ( v16 < 0 )
    {
      if ( v54 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
        Src = 0;
        v53 = 0;
        v54 = 0;
      }
      if ( v35 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v35);
      v17 = v32;
LABEL_49:
      if ( v17 )
        goto LABEL_50;
      return (unsigned int)v16;
    }
    *(_QWORD *)&v50 = v32;
    v49 = v31;
    if ( !(_QWORD)v31 )
    {
      v40 = 4251;
      v38 = (__int64)"onecore\\base\\xml\\udom_microdom.cpp";
      *(_QWORD *)&v41 = 0;
      v39 = "RtlCreateMicrodom";
      RtlReportErrorOrigination(&v38, v29, 3221266563LL);
      if ( v54 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
        Src = 0;
        v53 = 0;
        v54 = 0;
      }
      if ( v35 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v35);
      if ( v32 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v32);
      return 3221266563LL;
    }
    if ( v54 )
    {
      anonymous_namespace_::OurRtlFreeStringRoutine(v54);
      Src = 0;
      v53 = 0;
      v54 = 0;
    }
    if ( v35 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v35);
    v3 = v37;
    v2 = v32;
    goto LABEL_142;
  }
  if ( *(_BYTE *)(a1 + 49) )
  {
    v35 = 4198;
    *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v34 + 1) = "RtlCreateMicrodom";
    v36 = "Params->fRequireUtf8";
    goto LABEL_111;
  }
  v27 = *(_QWORD *)v10;
  Src = (void *)*((_QWORD *)v10 + 2);
  Src = (char *)Src + (_QWORD)v55;
  *(_QWORD *)&v46 = v27 - (_QWORD)v55;
  *((_QWORD *)&v46 + 1) = v27 - (_QWORD)v55;
  if ( v45 == 1 )
  {
    v28 = 1019;
    goto LABEL_119;
  }
  if ( v45 == 2 )
  {
    v28 = 1018;
    goto LABEL_119;
  }
  a2 = v45 - 3;
  if ( v45 == 3 )
  {
    v28 = 1014;
    goto LABEL_119;
  }
  if ( v45 == 4 )
  {
    v28 = 1013;
LABEL_119:
    v16 = RtlTranscodeLBlobs(5, 0, v28, (unsigned int)&v46, 106, (__int64)&v53);
    if ( v16 < 0 )
    {
      if ( v54 )
      {
        anonymous_namespace_::OurRtlFreeStringRoutine(v54);
        v32 = 0;
        v53 = 0;
LABEL_84:
        v54 = 0;
      }
LABEL_85:
      if ( !v11 )
        return (unsigned int)v16;
      v17 = v11;
      goto LABEL_50;
    }
    v10 = &v53;
    goto LABEL_123;
  }
  v35 = 4221;
  *(_QWORD *)&v34 = "onecore\\base\\xml\\udom_microdom.cpp";
  *((_QWORD *)&v34 + 1) = "RtlCreateMicrodom";
  v36 = 0;
LABEL_111:
  RtlReportErrorOrigination(&v34, a2, 3221225485LL);
  if ( v54 )
  {
    anonymous_namespace_::OurRtlFreeStringRoutine(v54);
    v53 = 0;
    v32 = 0;
    v54 = 0;
  }
  if ( v11 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v11);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14006db80  mov     [rsp-8+arg_10], rbx
0x14006db85  push    rbp
0x14006db86  push    rsi
0x14006db87  push    rdi
0x14006db88  push    r12
0x14006db8a  push    r13
0x14006db8c  push    r14
0x14006db8e  push    r15
0x14006db90  lea     rbp, [rsp-1B0h]
0x14006db98  sub     rsp, 2B0h
0x14006db9f  mov     rax, cs:__security_cookie
0x14006dba6  xor     rax, rsp
0x14006dba9  mov     [rbp+1E0h+var_40], rax
0x14006dbb0  xor     edi, edi
0x14006dbb2  mov     [rsp+2E0h+var_270], rdx
0x14006dbb7  xor     r13d, r13d
0x14006dbba  mov     [rsp+2E0h+var_2A0], rdi
0x14006dbbf  xorps   xmm0, xmm0
0x14006dbc2  mov     rbx, rdx
0x14006dbc5  mov     r15, rcx
0x14006dbc8  movups  [rsp+2E0h+var_2B0], xmm0
0x14006dbcd  test    rcx, rcx
0x14006dbd0  jnz     short loc_14006DC49
0x14006dbd2  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006dbd9  mov     [rbp+1E0h+Src], 1000h
0x14006dbe4  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006dbeb  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006dbf2  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006dbf9  lea     rax, aNotNullCheckFa_3; "Not-null check failed: Params"
0x14006dc00  mov     r8d, 0C000000Dh
0x14006dc06  mov     [rbp+1E0h+var_A8], rax
0x14006dc0d  lea     rcx, [rbp+1E0h+var_C0]
0x14006dc14  call    RtlReportErrorOrigination
0x14006dc19  mov     eax, 0C000000Dh
0x14006dc1e  mov     rcx, [rbp+1E0h+var_40]
0x14006dc25  xor     rcx, rsp; StackCookie
0x14006dc28  call    __security_check_cookie
0x14006dc2d  mov     rbx, [rsp+2E0h+arg_10]
0x14006dc35  add     rsp, 2B0h
0x14006dc3c  pop     r15
0x14006dc3e  pop     r14
0x14006dc40  pop     r13
0x14006dc42  pop     r12
0x14006dc44  pop     rdi
0x14006dc45  pop     rsi
0x14006dc46  pop     rbp
0x14006dc47  retn
0x14006dc49  mov     eax, cs:dword_1400A5E30
0x14006dc4f  mov     esi, 1
0x14006dc54  cmp     eax, 2
0x14006dc57  jz      short loc_14006DCC0
0x14006dc59  lock or [rsp+2E0h+var_2E0], r13d
0x14006dc5e  xor     eax, eax
0x14006dc60  lock cmpxchg cs:dword_1400A5E30, esi
0x14006dc68  jnz     short loc_14006DC9E
0x14006dc6a  cmp     cs:?g_OneShotMicrodomInit@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@A, r13; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom> MicrodomImplementation::g_OneShotMicrodomInit
0x14006dc71  jnz     loc_14006E63D
0x14006dc77  lea     rax, dword_1400A5E20
0x14006dc7e  mov     cs:dword_1400A5E20, r13d
0x14006dc85  mov     cs:?g_OneShotMicrodomInit@MicrodomImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodom@MicrodomImplementation@@@Rtl@Windows@@A, rax; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomImplementation::CMicrodom> MicrodomImplementation::g_OneShotMicrodomInit
0x14006dc8c  lea     eax, [rsi+1]
0x14006dc8f  mov     cs:dword_1400A5E24, r13d
0x14006dc96  xchg    eax, cs:dword_1400A5E30
0x14006dc9c  jmp     short loc_14006DCBB
0x14006dc9e  cmp     eax, esi
0x14006dca0  jnz     short loc_14006DCBB
0x14006dca2  jmp     short loc_14006DCB0
0x14006dca4  call    cs:__imp_NtYieldExecution
0x14006dcab  nop     dword ptr [rax+rax+00h]
0x14006dcb0  mov     eax, cs:dword_1400A5E30
0x14006dcb6  cmp     eax, 2
0x14006dcb9  jnz     short loc_14006DCA4
0x14006dcbb  lock or [rsp+2E0h+var_2E0], r13d
0x14006dcc0  mov     eax, cs:dword_1400A5E30
0x14006dcc6  cmp     eax, 2
0x14006dcc9  jnz     loc_14006E63D
0x14006dccf  cmp     [r15], r13d
0x14006dcd2  jz      short loc_14006DD0C
0x14006dcd4  cmp     [r15], esi
0x14006dcd7  jz      short loc_14006DD0C
0x14006dcd9  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006dce0  mov     [rbp+1E0h+Src], 1006h
0x14006dceb  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006dcf2  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006dcf9  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006dd00  lea     rax, aParamsInputtyp; "(Params->InputType == Windows::Microdom"...
0x14006dd07  jmp     loc_14006DC00
0x14006dd0c  mov     ecx, [r15+4]
0x14006dd10  test    ecx, ecx
0x14006dd12  jz      short loc_14006DD8D
0x14006dd14  cmp     ecx, 2
0x14006dd17  jz      short loc_14006DD50
0x14006dd19  cmp     ecx, esi
0x14006dd1b  jz      short loc_14006DD54
0x14006dd1d  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006dd24  mov     [rbp+1E0h+Src], 100Bh
0x14006dd2f  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006dd36  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006dd3d  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006dd44  lea     rax, aParamsSourcety; "(Params->SourceType == Windows::Microdo"...
0x14006dd4b  jmp     loc_14006DC00
0x14006dd50  cmp     ecx, esi
0x14006dd52  jnz     short loc_14006DDC6
0x14006dd54  cmp     [r15+8], r13
0x14006dd58  jnz     short loc_14006DDC6
0x14006dd5a  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006dd61  mov     [rbp+1E0h+Src], 1011h
0x14006dd6c  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006dd73  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006dd7a  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006dd81  lea     rax, aNotNullCheckFa_0; "Not-null check failed: Params->Source.p"...
0x14006dd88  jmp     loc_14006DC00
0x14006dd8d  cmp     [r15+8], r13
0x14006dd91  jnz     short loc_14006DDC6
0x14006dd93  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006dd9a  mov     [rbp+1E0h+Src], 100Eh
0x14006dda5  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006ddac  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006ddb3  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006ddba  lea     rax, aNotNullCheckFa_29; "Not-null check failed: Params->Source.p"...
0x14006ddc1  jmp     loc_14006DC00
0x14006ddc6  xor     eax, eax
0x14006ddc8  xorps   xmm0, xmm0
0x14006ddcb  mov     [rbp+1E0h+var_70], rax
0x14006ddd2  mov     al, [r15+30h]
0x14006ddd6  mov     byte ptr [rbp+1E0h+var_70], al
0x14006dddc  movups  [rbp+1E0h+var_A0], xmm0
0x14006dde3  movups  [rbp+1E0h+var_90], xmm0
0x14006ddea  movups  [rbp+1E0h+var_80], xmm0
0x14006ddf1  cmp     [r15], r13d
0x14006ddf4  jnz     loc_14006DE93
0x14006ddfa  cmp     ecx, esi
0x14006ddfc  jnz     short loc_14006DE1E
0x14006ddfe  mov     rax, [r15+8]
0x14006de02  movups  xmm0, xmmword ptr [rax]
0x14006de05  movups  [rbp+1E0h+var_A0], xmm0
0x14006de0c  movsd   xmm1, qword ptr [rax+10h]
0x14006de11  movsd   qword ptr [rbp+1E0h+var_90], xmm1
0x14006de19  jmp     loc_14006E5F1
0x14006de1e  cmp     ecx, 2
0x14006de21  jnz     short loc_14006DE49
0x14006de23  mov     rax, [r15+8]
0x14006de27  mov     qword ptr [rbp+1E0h+var_90+8], rax
0x14006de2e  mov     rax, [r15+10h]
0x14006de32  mov     qword ptr [rbp+1E0h+var_80], rax
0x14006de39  mov     rax, [r15+18h]
0x14006de3d  mov     qword ptr [rbp+1E0h+var_80+8], rax
0x14006de44  jmp     loc_14006E5F1
0x14006de49  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_microdom.cpp"
0x14006de50  mov     [rbp+1E0h+Src], 1025h
0x14006de5b  mov     qword ptr [rbp+1E0h+var_C0], rax
0x14006de62  lea     rcx, [rbp+1E0h+var_C0]
0x14006de69  lea     rax, aRtlcreatemicro; "RtlCreateMicrodom"
0x14006de70  mov     [rbp+1E0h+var_A8], r13
0x14006de77  mov     r8d, 0C0000002h
0x14006de7d  mov     qword ptr [rbp+1E0h+var_C0+8], rax
0x14006de84  call    RtlReportErrorOrigination
0x14006de89  mov     eax, 0C0000002h
0x14006de8e  jmp     loc_14006DC1E
0x14006de93  cmp     [r15], esi
0x14006de96  jnz     loc_14006E5F1
0x14006de9c  mov     r12, [r15+8]
0x14006dea0  xor     esi, esi
0x14006dea2  xor     eax, eax
0x14006dea4  mov     [rsp+2E0h+var_280], rsi
0x14006dea9  mov     [rbp+1E0h+var_58], rax
0x14006deb0  movups  [rsp+2E0h+var_290], xmm0
0x14006deb5  movups  [rbp+1E0h+var_68], xmm0
0x14006debc  test    ecx, ecx
0x14006debe  jnz     loc_14006E131
0x14006dec4  mov     r12d, 400h
0x14006deca  mov     [rbp+1E0h+Size], r13
0x14006ded1  mov     ecx, r12d
0x14006ded4  mov     [rbp+1E0h+Src], rax
0x14006dedb  lea     rdx, [rbp+1E0h+var_C0]
0x14006dee2  mov     rbx, r13
0x14006dee5  movups  [rbp+1E0h+var_C0], xmm0
0x14006deec  call    RtlAllocateLBlob
0x14006def1  mov     r14d, eax
0x14006def4  test    eax, eax
0x14006def6  jns     short loc_14006DF22
0x14006def8  mov     rcx, [rbp+1E0h+Src]
0x14006deff  test    rcx, rcx
0x14006df02  jz      short loc_14006DF09
0x14006df04  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006df09  mov     rcx, [rbp+1E0h+var_58]
0x14006df10  test    rcx, rcx
0x14006df13  jz      short loc_14006DF1A
0x14006df15  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006df1a  mov     eax, r14d
0x14006df1d  jmp     loc_14006DC1E
0x14006df22  mov     r14, [rbp+1E0h+Src]
0x14006df29  mov     rcx, [r15+8]
0x14006df2d  lea     r9, [rbp+1E0h+Size]
0x14006df34  mov     r8, r14
0x14006df37  mov     rdx, r12
0x14006df3a  mov     rax, [rcx]
0x14006df3d  mov     rax, [rax+10h]
0x14006df41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006df46  mov     r12d, eax
0x14006df49  test    eax, eax
0x14006df4b  js      loc_14006E282
0x14006df51  add     rbx, [rbp+1E0h+Size]
0x14006df58  mov     r12d, 400h
0x14006df5e  cmp     [rbp+1E0h+Size], r12
0x14006df65  jz      short loc_14006DF29
0x14006df67  lea     rdx, [rsp+2E0h+var_290]
0x14006df6c  mov     rcx, rbx
0x14006df6f  call    RtlAllocateLBlob
0x14006df74  mov     ebx, eax
0x14006df76  test    eax, eax
0x14006df78  jns     short loc_14006DFD1
0x14006df7a  test    r14, r14
0x14006df7d  jz      short loc_14006DF87
0x14006df7f  mov     rcx, r14
0x14006df82  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006df87  mov     rcx, [rbp+1E0h+var_58]
0x14006df8e  test    rcx, rcx
0x14006df91  jz      short loc_14006DFBB
0x14006df93  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006df98  xorps   xmm0, xmm0
0x14006df9b  xor     eax, eax
0x14006df9d  mov     [rbp+1E0h+Src], rax
0x14006dfa4  movups  [rbp+1E0h+var_68], xmm0
0x14006dfab  movsd   xmm0, [rbp+1E0h+Src]
0x14006dfb3  movsd   [rbp+1E0h+var_58], xmm0
0x14006dfbb  mov     rcx, [rsp+2E0h+var_280]
0x14006dfc0  test    rcx, rcx
0x14006dfc3  jz      short loc_14006DFCA
0x14006dfc5  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006dfca  mov     eax, ebx
0x14006dfcc  jmp     loc_14006DC1E
0x14006dfd1  mov     rcx, [r15+8]
0x14006dfd5  lea     r8, [rbp+1E0h+var_50]
0x14006dfdc  lea     rdx, _GUID_55eab610_3945_4595_b7f9_75bebf9486f4
0x14006dfe3  mov     [rbp+1E0h+var_50], r13
0x14006dfea  mov     rbx, r13
0x14006dfed  mov     rax, [rcx]
0x14006dff0  mov     rax, [rax+8]
0x14006dff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006dff9  mov     esi, eax
0x14006dffb  test    eax, eax
0x14006dffd  js      short loc_14006E017
0x14006dfff  mov     rbx, [rbp+1E0h+var_50]
0x14006e006  test    rbx, rbx
0x14006e009  jnz     short loc_14006E012
0x14006e00b  mov     esi, 0C00002B9h
0x14006e010  jmp     short loc_14006E04C
0x14006e012  mov     rcx, r13
0x14006e015  jmp     short loc_14006E01E
0x14006e017  mov     rcx, [rbp+1E0h+var_50]
0x14006e01e  test    rcx, rcx
0x14006e021  jz      short loc_14006E035
0x14006e023  mov     [rbp+1E0h+var_50], r13
0x14006e02a  mov     rax, [rcx]
0x14006e02d  mov     rax, [rax]
0x14006e030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e035  test    esi, esi
0x14006e037  jns     short loc_14006E0A3
0x14006e039  test    rbx, rbx
0x14006e03c  jz      short loc_14006E04C
0x14006e03e  mov     rax, [rbx]
0x14006e041  mov     rcx, rbx
0x14006e044  mov     rax, [rax]
0x14006e047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e04c  test    r14, r14
0x14006e04f  jz      short loc_14006E059
0x14006e051  mov     rcx, r14
0x14006e054  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006e059  mov     rcx, [rbp+1E0h+var_58]
0x14006e060  test    rcx, rcx
0x14006e063  jz      short loc_14006E08D
0x14006e065  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006e06a  xorps   xmm0, xmm0
0x14006e06d  xor     eax, eax
0x14006e06f  mov     [rbp+1E0h+Src], rax
0x14006e076  movups  [rbp+1E0h+var_68], xmm0
0x14006e07d  movsd   xmm0, [rbp+1E0h+Src]
0x14006e085  movsd   [rbp+1E0h+var_58], xmm0
0x14006e08d  mov     rcx, [rsp+2E0h+var_280]
0x14006e092  test    rcx, rcx
0x14006e095  jz      short loc_14006E09C
0x14006e097  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x14006e09c  mov     eax, esi
0x14006e09e  jmp     loc_14006DC1E
0x14006e0a3  mov     rsi, [rsp+2E0h+var_280]
0x14006e0a8  mov     r12, qword ptr [rsp+2E0h+var_290]
0x14006e0ad  mov     rcx, [r15+8]
0x14006e0b1  lea     r9, [rbp+1E0h+Size]
0x14006e0b8  mov     r8, r14
0x14006e0bb  mov     edx, 400h
0x14006e0c0  mov     rax, [rcx]
0x14006e0c3  mov     rax, [rax+10h]
0x14006e0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e0cc  mov     r13d, eax
0x14006e0cf  test    eax, eax
0x14006e0d1  js      loc_14006E219
0x14006e0d7  mov     rax, [rbp+1E0h+Size]
0x14006e0de  xor     r13d, r13d
0x14006e0e1  test    rax, rax
  ... truncated ...
```
