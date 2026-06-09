# LiteCryptUtilities::HmacEncapsulateString(INgcFunctions *,SessionKeyTypes::Type,uchar *,ulong,long,char const *,char * *)

- ea: `0x180028a10`
- end: `0x180029598`
- name: `?HmacEncapsulateString@LiteCryptUtilities@@YAJPEAVINgcFunctions@@W4Type@SessionKeyTypes@@PEAEKJPEBDPEAPEAD@Z`
- size: `2952`
- prototype: `__int64 __fastcall(LiteCryptUtilities *, int, unsigned __int8 *, unsigned int, int, char *, char **)`
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x18000e75c`

## callees

- `0x180003160`
- `0x18000741c`
- `0x180008440`
- `0x18000baac`
- `0x18000d824`
- `0x18000d91c`
- `0x18000e08c`
- `0x180010830`
- `0x180011080`
- `0x18001200c`
- `0x180023b5c`
- `0x180023c04`
- `0x180025e30`
- `0x180025e9c`
- `0x180026c8c`
- `0x180027f64`
- `0x180027fc0`
- `0x180028050`
- `0x180028144`
- `0x180028178`
- `0x18002819c`
- `0x18002896c`
- `0x180028a10`
- `0x1800295a0`
- `0x18002964c`
- `0x180029834`
- `0x18002aee0`
- `0x18002e3ac`
- `0x18002e3fc`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028da6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800292b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028da6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800292b5`

## string_xrefs

- `0x180029498`: `hr = StringCchCopyA(spBuffer, rawPayloadSizeBytes, pPayLoadString)`
- `0x180028cf9`: `hr = StringCchLengthA(pEncapsulationTempate, STRSAFE_MAX_CCH, &templateSizeCharacters)`
- `0x180028e54`: `hr = StringCchPrintfExA( spUnsignedEncapsulatedPayload, bufferSizeCharacters, nullptr, &remainingSizeCharacters, STRSAFE_FILL_BEHIND_NULL, pEncapsulationTempate, currentTime, SHA256_ALGORITHM, pPayLoadString, static_cast<LPCSTR>(spEscapedRandom))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LiteCryptUtilities::HmacEncapsulateString(
        LiteCryptUtilities *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        int a5,
        char *a6,
        char **a7)
{
  struct INgcFunctions *v10; // rdx
  signed int v11; // eax
  char **v12; // r9
  const char *v13; // rcx
  unsigned int v14; // r8d
  void *p_lpMultiByteStr; // rcx
  char **v16; // r8
  unsigned __int64 v17; // rdx
  int v18; // eax
  unsigned __int64 v19; // rdx
  const char *v20; // rbx
  int v21; // eax
  unsigned __int64 v22; // rdx
  int v23; // eax
  SIZE_T v24; // r12
  char *v25; // r14
  int v26; // eax
  int v27; // eax
  char **v28; // r9
  const char *v29; // rcx
  unsigned int v30; // r8d
  char **v31; // r8
  char v32; // si
  __int64 v33; // rbx
  __int64 v34; // rdi
  bool v35; // r9
  int v36; // ebx
  char **v37; // r8
  int v38; // eax
  unsigned __int64 v39; // rdx
  int v40; // eax
  const char *v41; // rcx
  unsigned int v42; // r8d
  __int64 v43; // rdi
  unsigned __int8 *v44; // rdi
  char *v45; // rbx
  unsigned __int8 *v46; // rbx
  __int64 v47; // rcx
  char *v48; // r10
  unsigned int v49; // ebx
  __int64 v50; // rdx
  int v51; // r8d
  char *v53; // [rsp+20h] [rbp-248h]
  int v54; // [rsp+28h] [rbp-240h]
  int v55; // [rsp+60h] [rbp-208h] BYREF
  char *v56; // [rsp+68h] [rbp-200h] BYREF
  unsigned __int8 *v57; // [rsp+70h] [rbp-1F8h]
  __int64 v58; // [rsp+78h] [rbp-1F0h]
  unsigned __int64 v59; // [rsp+80h] [rbp-1E8h] BYREF
  LPCCH v60; // [rsp+88h] [rbp-1E0h] BYREF
  unsigned __int8 *v61; // [rsp+90h] [rbp-1D8h] BYREF
  __int64 v62; // [rsp+98h] [rbp-1D0h] BYREF
  LPCCH lpMultiByteStr; // [rsp+A0h] [rbp-1C8h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-1C0h]
  __int64 v65; // [rsp+B0h] [rbp-1B8h]
  DWORD cbBinary[2]; // [rsp+B8h] [rbp-1B0h] BYREF
  unsigned int v67; // [rsp+C0h] [rbp-1A8h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-1A0h] BYREF
  int v69; // [rsp+D0h] [rbp-198h] BYREF
  __int64 CurrentTimeInSeconds; // [rsp+D8h] [rbp-190h] BYREF
  LPCCH v71[3]; // [rsp+E0h] [rbp-188h] BYREF
  char *v72[3]; // [rsp+F8h] [rbp-170h] BYREF
  int v73; // [rsp+110h] [rbp-158h] BYREF
  int v74; // [rsp+118h] [rbp-150h] BYREF
  __int64 v75; // [rsp+120h] [rbp-148h]
  int v76; // [rsp+128h] [rbp-140h]
  _QWORD v77[3]; // [rsp+130h] [rbp-138h] BYREF
  char *v78[3]; // [rsp+148h] [rbp-120h] BYREF
  int v79; // [rsp+160h] [rbp-108h] BYREF
  __int64 v80; // [rsp+168h] [rbp-100h]
  int v81; // [rsp+170h] [rbp-F8h]
  int v82; // [rsp+178h] [rbp-F0h]
  _QWORD v83[3]; // [rsp+180h] [rbp-E8h] BYREF
  _BYTE v84[24]; // [rsp+198h] [rbp-D0h] BYREF
  int *v85[4]; // [rsp+1B0h] [rbp-B8h] BYREF
  _QWORD v86[4]; // [rsp+1D0h] [rbp-98h] BYREF
  BYTE v87[32]; // [rsp+1F0h] [rbp-78h] BYREF
  BYTE pbBinary[16]; // [rsp+210h] [rbp-58h] BYREF
  __int64 v89; // [rsp+220h] [rbp-48h]

  v67 = a4;
  v61 = a3;
  v69 = a2;
  v55 = 0;
  memset(v84, 0, sizeof(v84));
  memset(v78, 0, sizeof(v78));
  memset(v72, 0, sizeof(v72));
  memset(v77, 0, sizeof(v77));
  v83[0] = &SymmetricSessionKeyFunctions::`vftable';
  v83[1] = &ObfuscatedSessionKeyFunctions::`vftable';
  v83[2] = &TpmSessionKeyFunctions::`vftable';
  v80 = 0;
  v79 = 0;
  v81 = 0;
  CBytePtr::Empty((CBytePtr *)&v79);
  v82 = 0;
  *(_OWORD *)pbBinary = 0;
  v89 = 0;
  v86[0] = "LiteCryptUtilities::HmacEncapsulateString";
  v86[1] = &v55;
  v86[2] = 0;
  v86[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::HmacEncapsulateString",
    (const char *)0x2AF,
    0,
    (const unsigned __int16 *)v53);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v85,
    "LiteCryptUtilities::HmacEncapsulateString",
    &v55,
    12,
    &qword_180041DE8);
  if ( !a6 || !a7 )
  {
    v55 = -2147024809;
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::HmacEncapsulateString",
      0x2BB,
      -2147024809,
      "hr = E_INVALIDARG");
    goto LABEL_68;
  }
  *a7 = 0;
  if ( !a2 || !a3 )
  {
    v56 = 0;
    v58 = 0;
    v57 = 0;
    v61 = 0;
    v40 = StringCchLengthA(a6, (unsigned __int64)v10, (unsigned __int64 *)&v61);
    v55 = v40;
    if ( v40 >= 0 )
    {
      v46 = v61 + 1;
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v56);
      v40 = LocalAllocFunctor<char *>::Allocate(v47, &v56, v46);
      v55 = v40;
      if ( v40 < 0 )
      {
        v41 = "hr = spBuffer.Allocate(rawPayloadSizeBytes)";
        v42 = 710;
      }
      else
      {
        v57 = v46;
        v40 = StringCchCopyA(v56, (unsigned __int64)v46, a6);
        v55 = v40;
        if ( v40 >= 0 )
        {
          v56 = 0;
          v57 = 0;
          *a7 = v48;
          goto LABEL_60;
        }
        v41 = "hr = StringCchCopyA(spBuffer, rawPayloadSizeBytes, pPayLoadString)";
        v42 = 711;
      }
    }
    else
    {
      v41 = "hr = StringCchLengthA(pPayLoadString, STRSAFE_MAX_CCH, &rawPayloadSizeCharacters)";
      v42 = 708;
    }
    goto LABEL_59;
  }
  CurrentTimeInSeconds = LiteCryptUtilities::GetCurrentTimeInSeconds(a1, v10);
  lpMultiByteStr = 0;
  v65 = 0;
  v64 = 0;
  v11 = (*(__int64 (__fastcall **)(LiteCryptUtilities *, _QWORD, BYTE *, __int64, int))(*(_QWORD *)a1 + 176LL))(
          a1,
          0,
          pbBinary,
          24,
          2);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  v55 = v11;
  if ( v11 < 0 )
  {
    v13 = "hr = HRESULT_FROM_WIN32(pNgcFunctions->BCryptGenRandom(nullptr, randomBytes, sizeof(randomBytes), BCRYPT_USE_S"
          "YSTEM_PREFERRED_RNG))";
    v14 = 728;
LABEL_9:
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::HmacEncapsulateString",
      v14,
      v11,
      v13);
    p_lpMultiByteStr = &lpMultiByteStr;
LABEL_61:
    Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)p_lpMultiByteStr);
    goto LABEL_68;
  }
  v11 = LiteCryptUtilities::Base64EncodeA(pbBinary, 0x18u, (unsigned int)&lpMultiByteStr, v12);
  v55 = v11;
  if ( v11 < 0 )
  {
    v13 = "hr = Base64EncodeA(randomBytes, sizeof(randomBytes), &spEncodedRandom)";
    v14 = 729;
    goto LABEL_9;
  }
  v11 = LiteCryptUtilities::UrlEscapeStringA(lpMultiByteStr, (const char *)v78, v16);
  v55 = v11;
  if ( v11 < 0 )
  {
    v13 = "hr = UrlEscapeStringA(spEncodedRandom, &spEscapedRandom)";
    v14 = 730;
    goto LABEL_9;
  }
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)&lpMultiByteStr);
  *(_QWORD *)cbBinary = 0;
  v60 = 0;
  v59 = 0;
  v68 = 0;
  v18 = StringCchLengthA("ct=%I64u&hashalg=%s&%s&nonce=%s", v17, (unsigned __int64 *)cbBinary);
  v55 = v18;
  if ( v18 >= 0 )
  {
    v20 = v78[0];
    v21 = StringCchLengthA(v78[0], v19, (unsigned __int64 *)&v60);
    v55 = v21;
    if ( v21 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacEncapsulateString",
        0x2EB,
        v21,
        "hr = StringCchLengthA(spEscapedRandom, STRSAFE_MAX_CCH, &nonceSizeCharacters)");
      goto LABEL_68;
    }
    v23 = StringCchLengthA(a6, v22, &v59);
    v55 = v23;
    if ( v23 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacEncapsulateString",
        0x2EC,
        v23,
        "hr = StringCchLengthA(pPayLoadString, STRSAFE_MAX_CCH, &rawPayloadSizeCharacters)");
      goto LABEL_68;
    }
    v24 = (SIZE_T)&v60[v59 + 27 + *(_QWORD *)cbBinary];
    v25 = (char *)LocalAlloc(0x40u, v24);
    Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v77);
    v77[0] = v25;
    if ( !v25 )
    {
      v55 = -2147024882;
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacEncapsulateString",
        0x2F3,
        -2147024882,
        "hr = E_OUTOFMEMORY");
      goto LABEL_68;
    }
    v26 = StringCchPrintfExA(
            v25,
            v24,
            0,
            &v68,
            0x200u,
            "ct=%I64u&hashalg=%s&%s&nonce=%s",
            CurrentTimeInSeconds - a5,
            "SHA256",
            a6,
            v20);
    v55 = v26;
    if ( v26 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacEncapsulateString",
        0x300,
        v26,
        "hr = StringCchPrintfExA( spUnsignedEncapsulatedPayload, bufferSizeCharacters, nullptr, &remainingSizeCharacters,"
        " STRSAFE_FILL_BEHIND_NULL, pEncapsulationTempate, currentTime, SHA256_ALGORITHM, pPayLoadString, static_cast<LPC"
        "STR>(spEscapedRandom))");
      goto LABEL_68;
    }
    cbBinary[0] = 0;
    lpMultiByteStr = 0;
    v65 = 0;
    v64 = 0;
    memset(v71, 0, sizeof(v71));
    if ( a2 == 2 )
    {
      v27 = (*(__int64 (__fastcall **)(LiteCryptUtilities *, unsigned __int8 *, _QWORD, const char *, int, BYTE *, int, char *, int, LPCCH *, DWORD *))(*(_QWORD *)a1 + 88LL))(
              a1,
              v61,
              v67,
              "WS-SecureConversation",
              21,
              pbBinary,
              24,
              v25,
              (int)v24 - (int)v68,
              &lpMultiByteStr,
              cbBinary);
      v55 = v27;
      if ( v27 < 0 )
      {
        v29 = "hr = pNgcFunctions->NgcSignWithSymmetricPopKey( pSessionKey, sessionKeyLength, reinterpret_cast<const BYTE"
              "*>(LiteCryptUtilities::SeedLabel::SecureConversation), static_cast<DWORD>(strlen(LiteCryptUtilities::SeedL"
              "abel::SecureConversation) * sizeof(CHAR)), randomBytes, sizeof(randomBytes), reinterpret_cast<PBYTE>(stati"
              "c_cast<CHAR*>(spUnsignedEncapsulatedPayload)), static_cast<DWORD>(unsignedEncapsulatedPayloadSize), &spHas"
              "hValue, &hashSize)";
        v30 = 793;
LABEL_27:
        Telemetry::IfFailExit(
          (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
          "LiteCryptUtilities::HmacEncapsulateString",
          v30,
          v27,
          v29);
LABEL_28:
        Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v71);
        Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&lpMultiByteStr);
        goto LABEL_68;
      }
      v27 = LiteCryptUtilities::Base64EncodeA((BYTE *)lpMultiByteStr, cbBinary[0], (unsigned int)v71, v28);
      v55 = v27;
      if ( v27 < 0 )
      {
        v29 = "hr = Base64EncodeA(spHashValue, hashSize, &spEncodedHash)";
        v30 = 795;
        goto LABEL_27;
      }
      v27 = LiteCryptUtilities::UrlEscapeStringA(v71[0], (const char *)v72, v31);
      v55 = v27;
      if ( v27 < 0 )
      {
        v29 = "hr = UrlEscapeStringA(spEncodedHash, &spEscapedHash)";
        v30 = 796;
        goto LABEL_27;
      }
      v32 = 0;
LABEL_40:
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v71);
      Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&lpMultiByteStr);
      v56 = 0;
      v58 = 0;
      v57 = 0;
      v61 = 0;
      v40 = StringCchLengthA(v72[0], v39, (unsigned __int64 *)&v61);
      v55 = v40;
      if ( v40 < 0 )
      {
        v41 = "hr = StringCchLengthA(spEscapedHash, STRSAFE_MAX_CCH, &hashSize)";
        v42 = 841;
LABEL_59:
        Telemetry::IfFailExit(
          (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
          "LiteCryptUtilities::HmacEncapsulateString",
          v42,
          v40,
          v41);
        goto LABEL_60;
      }
      v43 = 13;
      if ( v32 != 1 )
        v43 = 7;
      v44 = &v61[v43 + v24];
      v45 = (char *)LocalAlloc(0x40u, (SIZE_T)v44);
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v56);
      v56 = v45;
      if ( v45 )
      {
        *v45 = 0;
        v40 = StringCchCatA(v45, (unsigned __int64)v44, v25);
        v55 = v40;
        if ( v40 < 0 )
        {
          v41 = "hr = StringCchCatA(spBuffer, bufferSizeCharacters, spUnsignedEncapsulatedPayload)";
          v42 = 858;
          goto LABEL_59;
        }
        v40 = StringCchCatA(v45, (unsigned __int64)v44, "&hash=");
        v55 = v40;
        if ( v40 < 0 )
        {
          v41 = "hr = StringCchCatA(spBuffer, bufferSizeCharacters, \"&\"PPCRL_OTC_HASH\"=\")";
          v42 = 859;
          goto LABEL_59;
        }
        v40 = StringCchCatA(v45, (unsigned __int64)v44, v72[0]);
        v55 = v40;
        if ( v40 < 0 )
        {
          v41 = "hr = StringCchCatA(spBuffer, bufferSizeCharacters, spEscapedHash)";
          v42 = 860;
          goto LABEL_59;
        }
        if ( v32 == 1 )
        {
          v40 = StringCchCatA(v45, (unsigned __int64)v44, "&dd=1");
          v55 = v40;
          if ( v40 < 0 )
          {
            v41 = "hr = StringCchCatA(spBuffer, bufferSizeCharacters, \"&\"PPCRL_OTC_DOUBLE_DERIVATION)";
            v42 = 865;
            goto LABEL_59;
          }
        }
        v56 = 0;
        v57 = 0;
        *a7 = v45;
      }
      else
      {
        v55 = -2147024882;
        Telemetry::IfFailExit(
          (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
          "LiteCryptUtilities::HmacEncapsulateString",
          0x355,
          -2147024882,
          "hr = E_OUTOFMEMORY");
      }
LABEL_60:
      p_lpMultiByteStr = &v56;
      goto LABEL_61;
    }
    SessionKeyExecutionContext::SessionKeyExecutionContext((SessionKeyExecutionContext *)&v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v60);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v59);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v33 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
              &v68,
              v25);
      v34 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
              &CurrentTimeInSeconds,
              "WS-SecureConversation");
      v75 = 0;
      v74 = 0;
      v76 = 0;
      CBytePtr::Attach((CBytePtr *)&v74, pbBinary, 0x18u, v35);
      SessionKey::SessionKey((SessionKey *)v87, v61, v67, (const enum SessionKeyTypes::Type *)&v69);
      v36 = SessionKeyManager::SignWithSessionKey(
              (SessionKeyManager *)v83,
              v34,
              v54,
              v33,
              (__int64)&v60,
              (__int64)&v59,
              (__int64)&v62);
      v55 = v36;
      CBytePtr::Empty((CBytePtr *)v87);
      CBytePtr::Empty((CBytePtr *)&v74);
      ATL::CStringData::Release((ATL::CStringData *)(CurrentTimeInSeconds - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v68 - 24));
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v73) )
      {
        v55 = v73;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800293B9);
        goto LABEL_56;
      }
    }
    if ( v36 < 0 )
    {
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacEncapsulateString",
        0x330,
        v36,
        "hr = sessionKeyManager.SignWithSessionKey( &sessionKeyExecutionContext, SessionKey(pSessionKey, sessionKeyLength"
        ", static_cast<SessionKeyTypes::Type>(sessionKeyType)), CBytePtr(randomBytes, ARRAYSIZE(randomBytes), false), CSt"
        "ringA(LiteCryptUtilities::SeedLabel::SecureConversation), PPCRL_NGC_DERIVED_KEY_LENGTH_BYTES, CStringA(spUnsigne"
        "dEncapsulatedPayload), encodedHash, derivedKeyAlgorithm, needsDeviceDARefresh)");
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
      SessionKeyExecutionContext::~SessionKeyExecutionContext((SessionKeyExecutionContext *)&v56);
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v71);
      Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&lpMultiByteStr);
      goto LABEL_68;
    }
    v32 = ATL::operator==(&v59);
    v38 = LiteCryptUtilities::UrlEscapeStringA(v60, (const char *)v72, v37);
    v55 = v38;
    if ( v38 >= 0 )
    {
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
      SessionKeyExecutionContext::~SessionKeyExecutionContext((SessionKeyExecutionContext *)&v56);
      goto LABEL_40;
    }
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
      "LiteCryptUtilities::HmacEncapsulateString",
      0x33E,
      v38,
      "hr = UrlEscapeStringA(encodedHash, &spEscapedHash)");
LABEL_56:
    ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v60 - 24));
    SessionKeyExecutionContext::~SessionKeyExecutionContext((SessionKeyExecutionContext *)&v56);
    goto LABEL_28;
  }
  Telemetry::IfFailExit(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::HmacEncapsulateString",
    0x2EA,
    v18,
    "hr = StringCchLengthA(pEncapsulationTempate, STRSAFE_MAX_CCH, &templateSizeCharacters)");
LABEL_68:
  v49 = v55;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v85[3], *v85[2], (unsigned __int64)v85[1], v85[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v86, v50, v51);
  CBytePtr::Empty((CBytePtr *)&v79);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v77);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v72);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>((__int64)v78);
  Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptKeyFunctor<unsigned __int64>,DummyContext>(v84);
  return v49;
}

```

## disassembly

```asm
0x180028a10  mov     r11, rsp
0x180028a13  push    rbx
0x180028a14  push    rsi
0x180028a15  push    rdi
0x180028a16  push    r12
0x180028a18  push    r13
0x180028a1a  push    r14
0x180028a1c  push    r15
0x180028a1e  sub     rsp, 230h
0x180028a25  mov     rax, cs:__security_cookie
0x180028a2c  xor     rax, rsp
0x180028a2f  mov     [rsp+268h+var_40], rax
0x180028a37  mov     [rsp+268h+var_1A8], r9d
0x180028a3f  mov     rbx, r8
0x180028a42  mov     [rsp+268h+var_1D8], rbx
0x180028a4a  mov     r13d, edx
0x180028a4d  mov     rsi, rcx
0x180028a50  mov     [r11-198h], edx
0x180028a57  mov     rdi, [rsp+268h+arg_28]
0x180028a5f  mov     r15, [rsp+268h+arg_30]
0x180028a67  xor     r14d, r14d
0x180028a6a  mov     [rsp+268h+var_208], r14d
0x180028a6f  mov     [r11-0D0h], r14
0x180028a76  mov     [r11-0C0h], r14
0x180028a7d  mov     [r11-0C8h], r14
0x180028a84  mov     [r11-120h], r14
0x180028a8b  mov     [r11-110h], r14
0x180028a92  mov     [r11-118h], r14
0x180028a99  mov     [r11-170h], r14
0x180028aa0  mov     [r11-160h], r14
0x180028aa7  mov     [r11-168h], r14
0x180028aae  mov     [r11-138h], r14
0x180028ab5  mov     [r11-128h], r14
0x180028abc  mov     [r11-130h], r14
0x180028ac3  lea     rax, ??_7SymmetricSessionKeyFunctions@@6B@; const SymmetricSessionKeyFunctions::`vftable'
0x180028aca  mov     [r11-0E8h], rax
0x180028ad1  lea     rax, ??_7ObfuscatedSessionKeyFunctions@@6B@; const ObfuscatedSessionKeyFunctions::`vftable'
0x180028ad8  mov     [r11-0E0h], rax
0x180028adf  lea     rax, ??_7TpmSessionKeyFunctions@@6B@; const TpmSessionKeyFunctions::`vftable'
0x180028ae6  mov     [r11-0D8h], rax
0x180028aed  mov     [r11-100h], r14
0x180028af4  mov     [r11-108h], r14d
0x180028afb  mov     [r11-0F8h], r14d
0x180028b02  lea     rcx, [r11-108h]; this
0x180028b09  call    ?Empty@CBytePtr@@QEAAXXZ; CBytePtr::Empty(void)
0x180028b0e  mov     [rsp+268h+var_F0], r14d
0x180028b16  xorps   xmm0, xmm0
0x180028b19  xor     eax, eax
0x180028b1b  movups  xmmword ptr [rsp+268h+pbBinary], xmm0
0x180028b23  mov     [rsp+268h+var_48], rax
0x180028b2b  lea     r12, aLitecryptutili_3; "LiteCryptUtilities::HmacEncapsulateStri"...
0x180028b32  mov     [rsp+268h+var_98], r12
0x180028b3a  lea     rax, [rsp+268h+var_208]
0x180028b3f  mov     [rsp+268h+var_90], rax
0x180028b47  mov     [rsp+268h+var_88], r14
0x180028b4f  mov     [rsp+268h+var_80], r14
0x180028b57  xor     r9d, r9d; unsigned int
0x180028b5a  mov     r8d, 2AFh; char *
0x180028b60  mov     rdx, r12; char *
0x180028b63  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180028b6a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180028b6f  nop
0x180028b70  lea     rax, qword_180041DE8
0x180028b77  mov     [rsp+268h+var_248], rax; int *
0x180028b7c  lea     r9d, [r14+0Ch]; unsigned __int64
0x180028b80  lea     r8, [rsp+268h+var_208]; int *
0x180028b85  mov     rdx, r12; char *
0x180028b88  lea     rcx, [rsp+268h+var_B8]; this
0x180028b90  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180028b95  nop
0x180028b96  test    rdi, rdi
0x180028b99  jz      loc_1800294C8
0x180028b9f  test    r15, r15
0x180028ba2  jz      loc_1800294C8
0x180028ba8  mov     [r15], r14
0x180028bab  test    r13d, r13d
0x180028bae  jz      loc_1800293EC
0x180028bb4  test    rbx, rbx
0x180028bb7  jz      loc_1800293EC
0x180028bbd  mov     rcx, rsi; this
0x180028bc0  call    ?GetCurrentTimeInSeconds@LiteCryptUtilities@@YA_JPEAVINgcFunctions@@@Z; LiteCryptUtilities::GetCurrentTimeInSeconds(INgcFunctions *)
0x180028bc5  mov     [rsp+268h+var_190], rax
0x180028bcd  mov     [rsp+268h+lpMultiByteStr], r14
0x180028bd5  mov     [rsp+268h+var_1B8], r14
0x180028bdd  mov     [rsp+268h+var_1C0], r14
0x180028be5  mov     rax, [rsi]
0x180028be8  mov     dword ptr [rsp+268h+var_248], 2
0x180028bf0  lea     ebx, [r14+18h]
0x180028bf4  mov     r9d, ebx
0x180028bf7  lea     r8, [rsp+268h+pbBinary]
0x180028bff  xor     edx, edx
0x180028c01  mov     rcx, rsi
0x180028c04  mov     rax, [rax+0B0h]
0x180028c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c10  test    eax, eax
0x180028c12  jle     short loc_180028C1C
0x180028c14  movzx   eax, ax
0x180028c17  or      eax, 80070000h
0x180028c1c  mov     [rsp+268h+var_208], eax
0x180028c20  test    eax, eax
0x180028c22  jns     short loc_180028C56
0x180028c24  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(pNgcFunctions->"...
0x180028c2b  mov     r8d, 2D8h; unsigned int
0x180028c31  mov     [rsp+268h+var_248], rcx; char *
0x180028c36  mov     r9d, eax; int
0x180028c39  mov     rdx, r12; char *
0x180028c3c  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180028c43  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180028c48  nop
0x180028c49  lea     rcx, [rsp+268h+lpMultiByteStr]
0x180028c51  jmp     loc_180029444
0x180028c56  lea     r8, [rsp+268h+lpMultiByteStr]; unsigned int
0x180028c5e  mov     edx, ebx; cbBinary
0x180028c60  lea     rcx, [rsp+268h+pbBinary]; pbBinary
0x180028c68  call    ?Base64EncodeA@LiteCryptUtilities@@YAJPEBEKPEAPEAD@Z; LiteCryptUtilities::Base64EncodeA(uchar const *,ulong,char * *)
0x180028c6d  mov     [rsp+268h+var_208], eax
0x180028c71  test    eax, eax
0x180028c73  jns     short loc_180028C84
0x180028c75  lea     rcx, aHrBase64encode_0; "hr = Base64EncodeA(randomBytes, sizeof("...
0x180028c7c  mov     r8d, 2D9h
0x180028c82  jmp     short loc_180028C31
0x180028c84  lea     rdx, [rsp+268h+var_120]; char *
0x180028c8c  mov     rcx, [rsp+268h+lpMultiByteStr]; lpMultiByteStr
0x180028c94  call    ?UrlEscapeStringA@LiteCryptUtilities@@YAJPEBDPEAPEAD@Z; LiteCryptUtilities::UrlEscapeStringA(char const *,char * *)
0x180028c99  mov     [rsp+268h+var_208], eax
0x180028c9d  test    eax, eax
0x180028c9f  jns     short loc_180028CB0
0x180028ca1  lea     rcx, aHrUrlescapestr_0; "hr = UrlEscapeStringA(spEncodedRandom, "...
0x180028ca8  mov     r8d, 2DAh
0x180028cae  jmp     short loc_180028C31
0x180028cb0  lea     rcx, [rsp+268h+lpMultiByteStr]
0x180028cb8  call    ??1?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAA@XZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>(void)
0x180028cbd  mov     qword ptr [rsp+268h+cbBinary], r14
0x180028cc5  mov     [rsp+268h+var_1E0], r14
0x180028ccd  mov     [rsp+268h+var_1E8], r14
0x180028cd5  mov     [rsp+268h+var_1A0], r14
0x180028cdd  lea     r8, [rsp+268h+cbBinary]; unsigned __int64 *
0x180028ce5  lea     rcx, aCtI64uHashalgS; "ct=%I64u&hashalg=%s&%s&nonce=%s"
0x180028cec  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180028cf1  mov     [rsp+268h+var_208], eax
0x180028cf5  test    eax, eax
0x180028cf7  jns     short loc_180028D13
0x180028cf9  lea     rcx, aHrStringcchlen_0; "hr = StringCchLengthA(pEncapsulationTem"...
0x180028d00  mov     [rsp+268h+var_248], rcx
0x180028d05  mov     r9d, eax
0x180028d08  mov     r8d, 2EAh
0x180028d0e  jmp     loc_1800294E5
0x180028d13  lea     r8, [rsp+268h+var_1E0]; unsigned __int64 *
0x180028d1b  mov     rbx, [rsp+268h+var_120]
0x180028d23  mov     rcx, rbx; char *
0x180028d26  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180028d2b  mov     [rsp+268h+var_208], eax
0x180028d2f  test    eax, eax
0x180028d31  jns     short loc_180028D4D
0x180028d33  lea     rcx, aHrStringcchlen_4; "hr = StringCchLengthA(spEscapedRandom, "...
0x180028d3a  mov     [rsp+268h+var_248], rcx
0x180028d3f  mov     r9d, eax
0x180028d42  mov     r8d, 2EBh
0x180028d48  jmp     loc_1800294E5
0x180028d4d  lea     r8, [rsp+268h+var_1E8]; unsigned __int64 *
0x180028d55  mov     rcx, rdi; char *
0x180028d58  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180028d5d  mov     [rsp+268h+var_208], eax
0x180028d61  test    eax, eax
0x180028d63  jns     short loc_180028D7F
0x180028d65  lea     rcx, aHrStringcchlen_3; "hr = StringCchLengthA(pPayLoadString, S"...
0x180028d6c  mov     [rsp+268h+var_248], rcx
0x180028d71  mov     r9d, eax
0x180028d74  mov     r8d, 2ECh
0x180028d7a  jmp     loc_1800294E5
0x180028d7f  mov     rdx, [rsp+268h+var_1E8]
0x180028d87  add     rdx, [rsp+268h+var_1E0]
0x180028d8f  mov     r12, qword ptr [rsp+268h+cbBinary]
0x180028d97  add     r12, 1Bh
0x180028d9b  add     r12, rdx
0x180028d9e  mov     rdx, r12; uBytes
0x180028da1  mov     ecx, 40h ; '@'; uFlags
0x180028da6  call    cs:__imp_LocalAlloc
0x180028dac  mov     r14, rax
0x180028daf  lea     rcx, [rsp+268h+var_138]
0x180028db7  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180028dbc  mov     [rsp+268h+var_138], r14
0x180028dc4  test    r14, r14
0x180028dc7  jnz     short loc_180028DF2
0x180028dc9  mov     r9d, 8007000Eh
0x180028dcf  mov     [rsp+268h+var_208], r9d
0x180028dd4  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180028ddb  mov     [rsp+268h+var_248], rax
0x180028de0  mov     r8d, 2F3h
0x180028de6  lea     rdx, aLitecryptutili_3; "LiteCryptUtilities::HmacEncapsulateStri"...
0x180028ded  jmp     loc_1800294E8
0x180028df2  movsxd  rax, [rsp+268h+arg_20]
0x180028dfa  mov     rcx, [rsp+268h+var_190]
0x180028e02  sub     rcx, rax
0x180028e05  mov     [rsp+268h+var_220], rbx
0x180028e0a  mov     [rsp+268h+var_228], rdi
0x180028e0f  lea     rax, aSha256; "SHA256"
0x180028e16  mov     [rsp+268h+var_230], rax
0x180028e1b  mov     [rsp+268h+var_238], rcx
0x180028e20  lea     rax, aCtI64uHashalgS; "ct=%I64u&hashalg=%s&%s&nonce=%s"
0x180028e27  mov     [rsp+268h+var_240], rax; int
0x180028e2c  mov     dword ptr [rsp+268h+var_248], 200h; unsigned int
0x180028e34  lea     r9, [rsp+268h+var_1A0]; unsigned __int64 *
0x180028e3c  xor     r8d, r8d; char **
0x180028e3f  mov     rdx, r12; Size
0x180028e42  mov     rcx, r14; Buffer
0x180028e45  call    ?StringCchPrintfExA@@YAJPEAD_KPEAPEADPEA_KKPEBDZZ; StringCchPrintfExA(char *,unsigned __int64,char * *,unsigned __int64 *,ulong,char const *,...)
0x180028e4a  mov     [rsp+268h+var_208], eax
0x180028e4e  xor     ecx, ecx
0x180028e50  test    eax, eax
0x180028e52  jns     short loc_180028E6E
0x180028e54  lea     rcx, aHrStringcchpri_2; "hr = StringCchPrintfExA( spUnsignedEnca"...
0x180028e5b  mov     [rsp+268h+var_248], rcx
0x180028e60  mov     r9d, eax
0x180028e63  mov     r8d, 300h
0x180028e69  jmp     loc_180028DE6
0x180028e6e  mov     [rsp+268h+cbBinary], ecx
0x180028e75  mov     [rsp+268h+lpMultiByteStr], rcx
0x180028e7d  mov     [rsp+268h+var_1B8], rcx
0x180028e85  mov     [rsp+268h+var_1C0], rcx
0x180028e8d  mov     [rsp+268h+var_188], rcx
0x180028e95  mov     [rsp+268h+var_178], rcx
0x180028e9d  mov     [rsp+268h+var_180], rcx
0x180028ea5  cmp     r13d, 2
0x180028ea9  jnz     loc_180028FDF
0x180028eaf  mov     rax, [rsi]
0x180028eb2  mov     r9d, r12d
0x180028eb5  sub     r9d, dword ptr [rsp+268h+var_1A0]
0x180028ebd  lea     rdx, [rsp+268h+cbBinary]
0x180028ec5  mov     [rsp+268h+var_218], rdx
0x180028eca  lea     rdx, [rsp+268h+lpMultiByteStr]
0x180028ed2  mov     [rsp+268h+var_220], rdx
0x180028ed7  mov     dword ptr [rsp+268h+var_228], r9d
0x180028edc  mov     [rsp+268h+var_230], r14
0x180028ee1  mov     dword ptr [rsp+268h+var_238], 18h
0x180028ee9  lea     rdx, [rsp+268h+pbBinary]
0x180028ef1  mov     [rsp+268h+var_240], rdx
0x180028ef6  mov     dword ptr [rsp+268h+var_248], 15h
0x180028efe  lea     r9, aWsSecureconver; "WS-SecureConversation"
0x180028f05  mov     r8d, [rsp+268h+var_1A8]
0x180028f0d  mov     rdx, [rsp+268h+var_1D8]
0x180028f15  mov     rcx, rsi
0x180028f18  mov     rax, [rax+58h]
0x180028f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f21  mov     [rsp+268h+var_208], eax
0x180028f25  xor     r13d, r13d
0x180028f28  test    eax, eax
0x180028f2a  jns     short loc_180028F75
0x180028f2c  lea     rcx, aHrPngcfunction_1; "hr = pNgcFunctions->NgcSignWithSymmetri"...
0x180028f33  mov     r8d, 319h; unsigned int
0x180028f39  mov     [rsp+268h+var_248], rcx; char *
0x180028f3e  mov     r9d, eax; int
0x180028f41  lea     rdx, aLitecryptutili_3; "LiteCryptUtilities::HmacEncapsulateStri"...
0x180028f48  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180028f4f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180028f54  nop
0x180028f55  lea     rcx, [rsp+268h+var_188]
0x180028f5d  call    ??1?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAA@XZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::~Auto<char *,LocalAllocFunctor<char *>,DummyContext>(void)
0x180028f62  nop
0x180028f63  lea     rcx, [rsp+268h+lpMultiByteStr]
0x180028f6b  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180028f70  jmp     loc_1800294F4
0x180028f75  lea     r8, [rsp+268h+var_188]; unsigned int
0x180028f7d  mov     edx, [rsp+268h+cbBinary]; cbBinary
0x180028f84  mov     rcx, [rsp+268h+lpMultiByteStr]; pbBinary
0x180028f8c  call    ?Base64EncodeA@LiteCryptUtilities@@YAJPEBEKPEAPEAD@Z; LiteCryptUtilities::Base64EncodeA(uchar const *,ulong,char * *)
0x180028f91  mov     [rsp+268h+var_208], eax
0x180028f95  test    eax, eax
0x180028f97  jns     short loc_180028FA8
0x180028f99  lea     rcx, aHrBase64encode; "hr = Base64EncodeA(spHashValue, hashSiz"...
0x180028fa0  mov     r8d, 31Bh
0x180028fa6  jmp     short loc_180028F39
0x180028fa8  lea     rdx, [rsp+268h+var_170]; char *
0x180028fb0  mov     rcx, [rsp+268h+var_188]; lpMultiByteStr
0x180028fb8  call    ?UrlEscapeStringA@LiteCryptUtilities@@YAJPEBDPEAPEAD@Z; LiteCryptUtilities::UrlEscapeStringA(char const *,char * *)
0x180028fbd  mov     [rsp+268h+var_208], eax
0x180028fc1  test    eax, eax
0x180028fc3  jns     short loc_180028FD7
0x180028fc5  lea     rcx, aHrUrlescapestr_1; "hr = UrlEscapeStringA(spEncodedHash, &s"...
0x180028fcc  mov     r8d, 31Ch
0x180028fd2  jmp     loc_180028F39
0x180028fd7  mov     sil, r13b
0x180028fda  jmp     loc_180029223
0x180028fdf  lea     rcx, [rsp+268h+var_200]; this
0x180028fe4  call    ??0SessionKeyExecutionContext@@QEAA@XZ; SessionKeyExecutionContext::SessionKeyExecutionContext(void)
0x180028fe9  nop
0x180028fea  lea     rcx, [rsp+268h+var_1E0]
0x180028ff2  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180028ff7  nop
0x180028ff8  lea     rcx, [rsp+268h+var_1E8]
0x180029000  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180029005  nop
0x180029006  mov     rdx, r14
0x180029009  lea     rcx, [rsp+268h+var_1A0]
0x180029011  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *)
0x180029016  mov     rbx, rax
0x180029019  lea     rdx, aWsSecureconver; "WS-SecureConversation"
0x180029020  lea     rcx, [rsp+268h+var_190]
0x180029028  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *)
0x18002902d  mov     rdi, rax
  ... truncated ...
```
