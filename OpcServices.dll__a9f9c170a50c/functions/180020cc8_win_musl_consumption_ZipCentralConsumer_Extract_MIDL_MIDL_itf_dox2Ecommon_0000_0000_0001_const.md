# win_musl::consumption::ZipCentralConsumer::Extract(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 const &)

- ea: `0x180020cc8`
- end: `0x1800221a6`
- name: `?Extract@ZipCentralConsumer@consumption@win_musl@@QEAA?AU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@AEBU4@@Z`
- size: `5342`
- prototype: `__m128i *__fastcall(__int64, __m128i *, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020bb0`

## callees

- `0x1800079d8`
- `0x1800204f0`
- `0x180020cc8`
- `0x1800222b4`
- `0x180022648`
- `0x180022ee8`
- `0x180022f9c`
- `0x180023238`
- `0x180025528`
- `0x1800263e4`
- `0x180026448`
- `0x1800294ac`
- `0x1800517a0`
- `0x180075ec0`
- `0x18008e058`
- `0x18008e2fc`
- `0x18008e328`
- `0x180090838`
- `0x1800b696c`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180020e65`
- `msvcrt!memmove_s` at `0x180020f7a`
- `msvcrt!memmove_s` at `0x18002103f`
- `msvcrt!memmove_s` at `0x1800210c8`
- `msvcrt!memmove_s` at `0x18002115a`
- `msvcrt!memmove_s` at `0x1800211ce`
- `msvcrt!memmove_s` at `0x180021265`
- `msvcrt!memmove_s` at `0x180020e65`
- `msvcrt!memmove_s` at `0x180020f7a`
- `msvcrt!memmove_s` at `0x18002103f`
- `msvcrt!memmove_s` at `0x1800210c8`
- `msvcrt!memmove_s` at `0x18002115a`
- `msvcrt!memmove_s` at `0x1800211ce`
- `msvcrt!memmove_s` at `0x180021265`

## string_xrefs

- `0x18002191c`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18002195b`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18002200d`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x180021910`: `win_musl::consumption::readExtras`
- `0x18002194f`: `win_musl::consumption::readExtras`
- `0x180022006`: `win_musl::consumption::readExtras`
- `0x180021b6f`: `win_musl::detail::vector_read`
- `0x180021c1c`: `win_musl::detail::vector_read`
- `0x180021cb7`: `win_musl::detail::vector_read`
- `0x180021d52`: `win_musl::detail::vector_read`
- `0x180021ded`: `win_musl::detail::vector_read`
- `0x180021e72`: `win_musl::detail::vector_read`
- `0x180021f06`: `win_musl::detail::vector_read`
- `0x180021c7b`: `currentEntryByteSizeComment`
- `0x180021f43`: `central directory entry too big. Total size must not be more than 65,535.`
- `0x18002215c`: `Unexpected bytes remaining during extraction.`

## pseudocode

```c
__m128i *__fastcall win_musl::consumption::ZipCentralConsumer::Extract(__int64 a1, __m128i *a2, unsigned int *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // r9
  __int64 v9; // r10
  __m128i v10; // xmm6
  _QWORD *v11; // rdi
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // edx
  __int64 v16; // r9
  __int64 v17; // r11
  unsigned __int16 v18; // r8
  unsigned __int16 v19; // r10
  char v20; // cl
  __m128i *v21; // rdi
  __int64 v22; // rsi
  __int32 v23; // eax
  char *v24; // rbx
  char *v25; // rcx
  char *v26; // rdx
  __int64 v27; // rsi
  unsigned int v28; // edi
  unsigned int v29; // r14d
  char v30; // al
  unsigned int v31; // ecx
  __m128i *v32; // rbx
  __int64 v33; // rsi
  __int32 v34; // eax
  char *v35; // rdi
  char *v36; // rcx
  char *v37; // rdx
  __m128i v38; // xmm0
  __int64 v39; // rsi
  __int32 v40; // eax
  char *v41; // rdi
  char *v42; // rcx
  char *v43; // rdx
  __int64 v44; // rsi
  __int32 v45; // eax
  char *v46; // rdi
  char *v47; // rcx
  char *v48; // rdx
  __int64 v49; // rsi
  __int32 v50; // eax
  char *v51; // rdi
  char *v52; // rcx
  char *v53; // rdx
  __int64 v54; // rsi
  __int32 v55; // eax
  char *v56; // rdi
  char *v57; // rcx
  char *v58; // rdx
  __int64 v59; // rsi
  __int32 v60; // eax
  char *v61; // rdi
  char *v62; // rcx
  char *v63; // rdx
  unsigned int v64; // edx
  char v65; // al
  unsigned int v66; // r12d
  __m128i *v67; // r13
  unsigned __int64 v68; // rdi
  unsigned __int64 v69; // rbx
  _QWORD *v70; // rsi
  char *v71; // r14
  _QWORD *v72; // rcx
  unsigned __int64 v73; // rcx
  char v74; // al
  unsigned int v75; // r13d
  __m128i *v76; // rbx
  unsigned __int64 v77; // r14
  unsigned __int64 v78; // rsi
  unsigned int v79; // ecx
  unsigned __int64 v80; // rcx
  unsigned int i; // eax
  unsigned __int64 v82; // rcx
  char v83; // al
  __m128i *v84; // r13
  unsigned __int64 v85; // r12
  unsigned __int64 v86; // rdi
  void **v87; // rcx
  char *v88; // rsi
  void **v89; // rbx
  void **v90; // rax
  unsigned __int64 v91; // rcx
  __int64 v92; // rax
  __m128i *v93; // rbx
  __int16 Then; // bx
  __int64 v96; // r12
  unsigned __int64 v97; // rdi
  unsigned __int64 v98; // rax
  __int64 v99; // rax
  unsigned __int64 v100; // rax
  __int64 v101; // r8
  __int64 v102; // r9
  unsigned __int64 v103; // rdx
  __int64 v104; // rbx
  __int64 v105; // rbx
  __m128i v106; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v107; // [rsp+58h] [rbp-B0h] BYREF
  int Destination; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v109; // [rsp+60h] [rbp-A8h] BYREF
  __m128i *v110; // [rsp+68h] [rbp-A0h] BYREF
  int v111; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 v112; // [rsp+74h] [rbp-94h] BYREF
  __m128i v113; // [rsp+78h] [rbp-90h] BYREF
  __m128i v114; // [rsp+88h] [rbp-80h] BYREF
  _QWORD *v115; // [rsp+98h] [rbp-70h]
  __m128i v116; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v117; // [rsp+B8h] [rbp-50h] BYREF
  __m128i *v118; // [rsp+C8h] [rbp-40h]
  __int64 v119; // [rsp+D0h] [rbp-38h]
  __int16 v120; // [rsp+D8h] [rbp-30h] BYREF
  int v121; // [rsp+DAh] [rbp-2Eh]
  __int16 v122; // [rsp+DEh] [rbp-2Ah]
  void *v123; // [rsp+E0h] [rbp-28h]
  __int64 v124; // [rsp+E8h] [rbp-20h]
  __int64 v125; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v126; // [rsp+F8h] [rbp-10h]
  void **v127; // [rsp+108h] [rbp+0h] BYREF
  char v128; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v129[2]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v130; // [rsp+128h] [rbp+20h]
  unsigned __int64 v131; // [rsp+130h] [rbp+28h]
  char v132[8]; // [rsp+140h] [rbp+38h] BYREF
  unsigned __int64 v133; // [rsp+148h] [rbp+40h]
  unsigned __int64 v134; // [rsp+150h] [rbp+48h]
  _BYTE v135[16]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v136; // [rsp+170h] [rbp+68h]
  int v137; // [rsp+188h] [rbp+80h]
  unsigned int v138; // [rsp+18Ch] [rbp+84h]
  __int64 v139; // [rsp+1C0h] [rbp+B8h]
  char v140; // [rsp+1D5h] [rbp+CDh]
  char v141; // [rsp+1D8h] [rbp+D0h] BYREF
  void *Block[2]; // [rsp+1E0h] [rbp+D8h] BYREF
  __int64 v143; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v144; // [rsp+1F8h] [rbp+F0h]
  _BYTE pExceptionObject[160]; // [rsp+208h] [rbp+100h] BYREF

  v119 = -2;
  v118 = a2;
  v5 = a1 + 80;
  v6 = *(_QWORD *)(v5 + 8);
  if ( v6 )
    v7 = *(_QWORD *)(v5 + 16) - v6;
  else
    v7 = 0;
  v8 = *(unsigned int *)(a1 + 112);
  v9 = *a3;
  if ( v9 + v7 < v8 )
  {
    std::vector<unsigned char>::_Insert<unsigned char const *>(
      v5,
      *(_QWORD *)(a1 + 96),
      *((_QWORD *)a3 + 1),
      *((_QWORD *)a3 + 1) + v9);
    a2->m128i_i64[0] = 0;
    a2->m128i_i64[1] = 0;
    return a2;
  }
  v10 = *(__m128i *)a3;
  v116 = *(__m128i *)a3;
  v11 = (_QWORD *)(a1 + 96);
  v115 = (_QWORD *)(a1 + 96);
  if ( v6 )
  {
    v12 = *v11 - v6;
    if ( *v11 != v6 )
    {
      if ( v12 < v8 )
      {
        v105 = v116.m128i_i64[1] + (unsigned int)(v8 - v12);
        std::vector<unsigned char>::_Insert<unsigned char const *>(v5, *v11, v116.m128i_i64[1], v105);
        v10 = *(__m128i *)win_musl::detail::get_vector_tail_private(
                            &v117,
                            &v116,
                            v105,
                            "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
                            336,
                            "win_musl::consumption::ZipCentralConsumer::Extract",
                            L"new_begin is out-of-range: vector expression (earlyReturnVector), new_begin expression (bytesEnd)");
      }
      v115 = (_QWORD *)(a1 + 96);
    }
  }
  v114 = v10;
  v13 = *(_QWORD *)(a1 + 88);
  if ( v13 )
    v14 = *v11 - v13;
  else
    LODWORD(v14) = 0;
  v106 = (__m128i)(unsigned int)v14;
  if ( v13 && *v11 != v13 )
    v106.m128i_i64[1] = v13;
  v113 = v106;
  win_musl::ZipFileLocal::ZipFileLocal((win_musl::ZipFileLocal *)&v127);
  v127 = &win_musl::ZipFileCentral::`vftable';
  v144 = 15;
  v143 = 0;
  LOBYTE(Block[0]) = 0;
  v18 = 0;
  v111 = 0;
  LOWORD(v109) = 0;
  v19 = 0;
  LODWORD(v110) = 0;
  v112 = 0;
  if ( v15 && v16 )
  {
    v20 = 0;
  }
  else
  {
    v20 = 1;
    v15 = _mm_cvtsi128_si32(v10);
  }
  v21 = &v113;
  if ( v20 )
    v21 = &v114;
  if ( v15 < 4 || !*(_BYTE *)(a1 + 116) )
  {
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
LABEL_173:
    v29 = v114.m128i_i32[0];
    goto LABEL_33;
  }
  v22 = v21->m128i_u32[0];
  v23 = v21->m128i_i32[1];
  v24 = (char *)v21->m128i_i64[1];
  if ( (unsigned int)v22 < 4 )
  {
    v106.m128i_i32[0] = v21->m128i_i32[0];
    v106.m128i_i32[1] = v23;
    v106.m128i_i64[1] = (__int64)v24;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      357,
      v17,
      "signatureCheck",
      4,
      &v106);
  }
  Destination = 0;
  memmove_s(&Destination, 4u, v24, 4u);
  if ( !v24 || (v25 = v24 + 4, v26 = &v24[v22], &v24[v22] == v24 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v24 > v25 || v25 > v26 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v26 - (_DWORD)v25);
    v106.m128i_i64[1] = (__int64)(v24 + 4);
  }
  *v21 = v106;
  LOWORD(v107) = 255;
  if ( Destination != 33639248 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(a1 + 8) + 40LL))(a1 + 8, *(_QWORD *)(a1 + 32));
    win_dox::ByteSender::StopSend((win_dox::ByteSender *)(a1 + 64));
    a2->m128i_i64[0] = 0;
    a2->m128i_i64[1] = 0;
LABEL_196:
    win_musl::ZipFileCentral::~ZipFileCentral((win_musl::ZipFileCentral *)&v127);
    return a2;
  }
  *(_DWORD *)(a1 + 112) = 46;
  v27 = v113.m128i_i64[1];
  v28 = v113.m128i_i32[0];
  if ( v113.m128i_i32[0] )
  {
    if ( v113.m128i_i64[1] && v113.m128i_i32[0] < 0x2Au )
      goto LABEL_217;
    if ( v113.m128i_i64[1] )
    {
      v18 = v111;
      v19 = (unsigned __int16)v110;
      goto LABEL_173;
    }
  }
  v29 = v114.m128i_i32[0];
  if ( v114.m128i_i32[0] < 0x2Au )
    goto LABEL_217;
  v18 = v111;
  v19 = (unsigned __int16)v110;
LABEL_33:
  v107 = 0;
  v111 = 0;
  if ( v28 && v27 )
  {
    v30 = 0;
    v31 = v28;
  }
  else
  {
    v30 = 1;
    v31 = v29;
  }
  v32 = &v113;
  if ( v30 )
    v32 = &v114;
  if ( v31 < 0x2A )
    goto LABEL_83;
  v33 = v32->m128i_u32[0];
  v34 = v32->m128i_i32[1];
  v35 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v33 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v34;
    v106.m128i_i64[1] = (__int64)v35;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      413,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "versionMadeBy",
      2,
      &v106);
  }
  LOWORD(Destination) = 0;
  memmove_s(&Destination, 2u, v35, 2u);
  if ( !v35 || (v36 = v35 + 2, v37 = &v35[v33], &v35[v33] == v35 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v35 > v36 || v36 > v37 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v37 - (_DWORD)v36);
    v106.m128i_i64[1] = (__int64)(v35 + 2);
  }
  v38 = v106;
  *v32 = v106;
  LOWORD(v107) = 255;
  v140 = Destination;
  v137 = BYTE1(Destination);
  v116 = v38;
  win_musl::consumption::readFileHeaderCommon(&v127, &v116, v32, &v109, &v112);
  v39 = v32->m128i_u32[0];
  v40 = v32->m128i_i32[1];
  v41 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v39 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v40;
    v106.m128i_i64[1] = (__int64)v41;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      427,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "currentEntryByteSizeComment",
      2,
      &v106);
  }
  LOWORD(Destination) = 0;
  memmove_s(&Destination, 2u, v41, 2u);
  if ( !v41 || (v42 = v41 + 2, v43 = &v41[v39], &v41[v39] == v41 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v41 > v42 || v42 > v43 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v43 - (_DWORD)v42);
    v106.m128i_i64[1] = (__int64)(v41 + 2);
  }
  *v32 = v106;
  LOWORD(v107) = 255;
  v44 = v32->m128i_u32[0];
  v45 = v32->m128i_i32[1];
  v46 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v44 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v45;
    v106.m128i_i64[1] = (__int64)v46;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      430,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "diskStartNumber",
      2,
      &v106);
  }
  LOWORD(v107) = 0;
  memmove_s(&v107, 2u, v46, 2u);
  if ( !v46 || (v47 = v46 + 2, v48 = &v46[v44], &v46[v44] == v46 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v46 > v47 || v47 > v48 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v48 - (_DWORD)v47);
    v106.m128i_i64[1] = (__int64)(v46 + 2);
  }
  *v32 = v106;
  LOWORD(v110) = 255;
  v111 = (unsigned __int16)v107;
  v49 = v32->m128i_u32[0];
  v50 = v32->m128i_i32[1];
  v51 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v49 < 2 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v50;
    v106.m128i_i64[1] = (__int64)v51;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      434,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "internalAttributes",
      2,
      &v106);
  }
  LOWORD(v110) = 0;
  memmove_s(&v110, 2u, v51, 2u);
  if ( !v51 || (v52 = v51 + 2, v53 = &v51[v49], &v51[v49] == v51 + 2) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v51 > v52 || v52 > v53 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v53 - (_DWORD)v52);
    v106.m128i_i64[1] = (__int64)(v51 + 2);
  }
  *v32 = v106;
  v54 = v32->m128i_u32[0];
  v55 = v32->m128i_i32[1];
  v56 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v54 < 4 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v55;
    v106.m128i_i64[1] = (__int64)v56;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      437,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "entry.header.attributes",
      4,
      &v106);
  }
  v107 = 0;
  memmove_s(&v107, 4u, v56, 4u);
  if ( !v56 || (v57 = v56 + 4, v58 = &v56[v54], &v56[v54] == v56 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v56 > v57 || v57 > v58 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v58 - (_DWORD)v57);
    v106.m128i_i64[1] = (__int64)(v56 + 4);
  }
  *v32 = v106;
  LOWORD(v110) = 255;
  v138 = v107;
  v59 = v32->m128i_u32[0];
  v60 = v32->m128i_i32[1];
  v61 = (char *)v32->m128i_i64[1];
  if ( (unsigned int)v59 < 4 )
  {
    v106.m128i_i32[0] = v32->m128i_i32[0];
    v106.m128i_i32[1] = v60;
    v106.m128i_i64[1] = (__int64)v61;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipentryconsumer.cpp",
      440,
      "win_musl::consumption::ZipCentralConsumer::Extract",
      "entry.header.header_offset",
      4,
      &v106);
  }
  v107 = 0;
  memmove_s(&v107, 4u, v61, 4u);
  if ( !v61 || (v62 = v61 + 4, v63 = &v61[v59], &v61[v59] == v61 + 4) )
  {
    v106 = 0u;
  }
  else
  {
    if ( v61 > v62 || v62 > v63 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v106.m128i_i64[0] = (unsigned int)((_DWORD)v63 - (_DWORD)v62);
    v106.m128i_i64[1] = (__int64)(v61 + 4);
  }
  *v32 = v106;
  v139 = v107;
  v19 = v112;
  LODWORD(v110) = v112;
  v18 = v109;
  v64 = (unsigned __int16)v109 + v112 + (unsigned __int16)Destination;
  if ( v64 + 46 > 0xFFFF )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1C4u,
      0x80511009,
      (struct win_musl::TStringEllipseBase *)L"central directory entry too big. Total size must not be more than 65,535.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 112) = v64 + 42;
  if ( *(_BYTE *)(a1 + 116) )
    *(_DWORD *)(a1 + 112) = v64 + 46;
  v27 = v113.m128i_i64[1];
  v28 = v113.m128i_i32[0];
  if ( v113.m128i_i32[0] && v113.m128i_i64[1] && v113.m128i_i32[0] < v64 )
    goto LABEL_217;
  v107 = (unsigned __int16)Destination;
  if ( !v113.m128i_i32[0] || !v113.m128i_i64[1] )
  {
    v29 = v114.m128i_i32[0];
    if ( v114.m128i_i32[0] >= v64 )
      goto LABEL_83;
LABEL_217:
    *a2 = v10;
    goto LABEL_196;
  }
  v29 = v114.m128i_i32[0];
LABEL_83:
  if ( v28 && v27 )
  {
    v65 = 0;
    v66 = v28;
  }
  else
  {
    v65 = 1;
    v66 = v29;
  }
  v67 = &v113;
  if ( v65 )
    v67 = &v114;
  if ( v66 >= v18 )
  {
    v68 = v67->m128i_u64[1];
    v69 = v68 + v18;
    if ( v131 < 0x10 )
    {
      v70 = v129;
      v71 = (char *)v129 + v130;
    }
    else
    {
      v70 = (_QWORD *)v129[0];
      v71 = (char *)(v129[0] + v130);
    }
    v126 = 15;
    v125 = 0;
    LOBYTE(v123) = 0;
    std::string::_Construct<unsigned char const *>(&v120, v68, v68 + v18);
    v72 = v129;
    if ( v131 >= 0x10 )
      LODWORD(v72) = v129[0];
    std::string::replace(
      (unsigned int)&v128,
      v70 != 0 ? (_DWORD)v70 - (_DWORD)v72 : 0,
      v71 != 0 ? (_DWORD)v71 - (_DWORD)v70 : 0,
      (unsigned int)&v120,
      0,
      -1);
    if ( v126 >= 0x10 )
      operator delete(v123);
    if ( v66 && v68 && (v73 = v68 + v66, v73 != v69) )
    {
      if ( v68 > v69 || v69 > v73 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x1FCu,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)(v73 - v69);
      v106.m128i_i64[1] = v69;
    }
    else
    {
      v106 = 0u;
    }
    *v67 = v106;
    v29 = v114.m128i_i32[0];
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
    v19 = (unsigned __int16)v110;
  }
  if ( v28 && v27 )
  {
    v74 = 0;
    v75 = v28;
  }
  else
  {
    v74 = 1;
    v75 = v29;
  }
  v76 = &v113;
  if ( v74 )
    v76 = &v114;
  v110 = v76;
  if ( v75 >= v19 )
  {
    v77 = v76->m128i_u64[1];
    v78 = v77 + v19;
    if ( v133 != v134 )
      v134 = v133;
    std::vector<unsigned char>::_Insert<unsigned char const *>(v132, v133, v77, v77 + v19);
    if ( v133 )
      v79 = v134 - v133;
    else
      v79 = 0;
    v106 = (__m128i)v79;
    v80 = 0;
    if ( v133 && v134 != v133 )
    {
      v106.m128i_i64[1] = v133;
      v80 = v133;
    }
    for ( i = v106.m128i_i32[0]; ; v106.m128i_i64[0] = i )
    {
      v106.m128i_i64[1] = v80;
      if ( !i || !v80 )
        break;
      v117 = v106;
      Then = win_musl::detail::readThenLog<unsigned short>(
               (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
               65,
               (unsigned int)"win_musl::consumption::readExtras",
               (unsigned int)"type",
               (__int64)&v117,
               (__int64)&v106);
      v117 = v106;
      LOWORD(v109) = win_musl::detail::readThenLog<unsigned short>(
                       (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
                       69,
                       (unsigned int)"win_musl::consumption::readExtras",
                       (unsigned int)"size",
                       (__int64)&v117,
                       (__int64)&v106);
      v96 = v106.m128i_u32[0];
      if ( (unsigned int)(unsigned __int16)v109 > v106.m128i_i32[0] )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x4Cu,
          0x80511002,
          (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v121 = 0;
      v122 = 0;
      v120 = Then;
      HIDWORD(v123) = v106.m128i_i32[1];
      v97 = v106.m128i_u64[1];
      v124 = v106.m128i_i64[1];
      LODWORD(v123) = (unsigned __int16)v109;
      if ( Then == 1 )
      {
        v116.m128i_i32[0] = (unsigned __int16)v109;
        v116.m128i_i32[1] = v106.m128i_i32[1];
        v116.m128i_i64[1] = v106.m128i_i64[1];
        win_musl::consumption::readZip64Extra(&v127, &v116, &v111);
      }
      else
      {
        v99 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(v135);
        v100 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(v135, v99);
        if ( v103 >= v100 )
        {
          std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(v135, v136, v101, &v120);
        }
        else
        {
          v104 = v136;
          std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
            v136,
            v102,
            &v120);
          v136 = v104 + 24;
        }
      }
      if ( (_DWORD)v96 && v97 && (v80 = v97 + (unsigned __int16)v109, v98 = v97 + v96, v97 + v96 != v80) )
      {
        if ( v97 > v80 || v80 > v98 )
        {
          win_musl::detail::ThrowBuilder<SplException::THResultException>(
            (SplException::TSystemException *)pExceptionObject,
            0x65u,
            0x80070057,
            (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (extraCursor), new_begin"
                                                    " expression (dd::vector_begin(extraCursor) + size)");
          throw (SplException::THResultException *)pExceptionObject;
        }
        i = v98 - v80;
      }
      else
      {
        v80 = 0;
        i = 0;
      }
    }
    if ( v75 && v77 && (v82 = v77 + v75, v82 != v78) )
    {
      if ( v77 > v78 || v78 > v82 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x218u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)(v82 - v78);
      v106.m128i_i64[1] = v78;
    }
    else
    {
      v106 = 0u;
    }
    *v110 = v106;
    v29 = v114.m128i_i32[0];
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
  }
  if ( v111 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x224u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Disk number start must be 0 - only support single disk archives.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v28 && v27 )
  {
    v83 = 0;
    v29 = v28;
  }
  else
  {
    v83 = 1;
  }
  v84 = &v113;
  if ( v83 )
    v84 = &v114;
  if ( v29 >= (unsigned __int16)v107 )
  {
    v85 = v84->m128i_u64[1];
    v86 = v85 + (unsigned __int16)v107;
    v87 = Block;
    if ( v144 >= 0x10 )
      v87 = (void **)Block[0];
    v88 = (char *)v87 + v143;
    v89 = Block;
    if ( v144 >= 0x10 )
      v89 = (void **)Block[0];
    v126 = 15;
    v125 = 0;
    LOBYTE(v123) = 0;
    std::string::_Construct<unsigned char const *>(&v120, v85, v86);
    if ( v88 )
      LODWORD(v88) = (_DWORD)v88 - (_DWORD)v89;
    v90 = Block;
    if ( v144 >= 0x10 )
      LODWORD(v90) = Block[0];
    if ( v89 )
      LODWORD(v89) = (_DWORD)v89 - (_DWORD)v90;
    std::string::replace((unsigned int)&v141, (_DWORD)v89, (_DWORD)v88, (unsigned int)&v120, 0, -1);
    if ( v126 >= 0x10 )
      operator delete(v123);
    if ( v29 && v85 && (v91 = v85 + v29, v91 != v86) )
    {
      if ( v85 > v86 || v86 > v91 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x238u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (currentByteSource), new_b"
                                                  "egin expression (endBytes)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v106.m128i_i64[0] = (unsigned int)(v91 - v86);
      v106.m128i_i64[1] = v86;
    }
    else
    {
      v106 = 0u;
    }
    *v84 = v106;
    v27 = v113.m128i_i64[1];
    v28 = v113.m128i_i32[0];
  }
  *(_QWORD *)(a1 + 32) += *(unsigned int *)(a1 + 112);
  win_musl::consumption::ZipCentralConsumer::AddFile(
    (win_musl::consumption::ZipCentralConsumer *)a1,
    (const struct win_musl::ZipFileCentral *)&v127);
  *(_DWORD *)(a1 + 112) = 4;
  *(_BYTE *)(a1 + 116) = 1;
  if ( v28 && v27 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x24Bu,
      0x80511001,
      (struct win_musl::TStringEllipseBase *)L"Unexpected bytes remaining during extraction.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  v92 = *(_QWORD *)(a1 + 88);
  if ( v92 != *v115 )
    *v115 = v92;
  v93 = v118;
  *v118 = v114;
  v127 = &win_musl::ZipFileCentral::`vftable';
  if ( v144 >= 0x10 )
    operator delete(Block[0]);
  v144 = 15;
  v143 = 0;
  LOBYTE(Block[0]) = 0;
  win_musl::ZipFileLocal::~ZipFileLocal((win_musl::ZipFileLocal *)&v127);
  return v93;
}

```

## disassembly

```asm
0x180020cc8  mov     rax, rsp
0x180020ccb  push    rbp
0x180020ccc  push    rsi
0x180020ccd  push    rdi
0x180020cce  push    r12
0x180020cd0  push    r13
0x180020cd2  push    r14
0x180020cd4  push    r15
0x180020cd6  lea     rbp, [rax-1F8h]
0x180020cdd  sub     rsp, 2C0h
0x180020ce4  mov     [rbp+1F0h+var_228], 0FFFFFFFFFFFFFFFEh
0x180020cec  mov     [rax+20h], rbx
0x180020cf0  movaps  xmmword ptr [rax-48h], xmm6
0x180020cf4  mov     rax, cs:__security_cookie
0x180020cfb  xor     rax, rsp
0x180020cfe  mov     [rbp+1F0h+var_50], rax
0x180020d05  mov     r12, rdx
0x180020d08  mov     [rbp+1F0h+var_230], rdx
0x180020d0c  mov     r15, rcx
0x180020d0f  add     rcx, 50h ; 'P'
0x180020d13  mov     rdx, [rcx+8]
0x180020d17  xor     r13d, r13d
0x180020d1a  test    rdx, rdx
0x180020d1d  jz      loc_1800217ED
0x180020d23  mov     rax, [rcx+10h]
0x180020d27  sub     rax, rdx
0x180020d2a  mov     r9d, [r15+70h]
0x180020d2e  mov     r10d, [r8]
0x180020d31  add     rax, r10
0x180020d34  cmp     rax, r9
0x180020d37  jb      loc_180021A6B
0x180020d3d  movups  xmm6, xmmword ptr [r8]
0x180020d41  movaps  [rbp+1F0h+var_250], xmm6
0x180020d45  lea     r11, aWinMuslConsump_2; "win_musl::consumption::ZipCentralConsum"...
0x180020d4c  lea     rdi, [r15+60h]
0x180020d50  mov     [rbp+1F0h+var_260], rdi
0x180020d54  test    rdx, rdx
0x180020d57  jz      short loc_180020D6E
0x180020d59  mov     rax, [rdi]
0x180020d5c  sub     rax, rdx
0x180020d5f  jz      short loc_180020D6E
0x180020d61  cmp     rax, r9
0x180020d64  jb      loc_180021ABE
0x180020d6a  mov     [rbp+1F0h+var_260], rdi
0x180020d6e  movdqa  [rbp+1F0h+var_270], xmm6
0x180020d73  mov     rcx, [r15+58h]
0x180020d77  test    rcx, rcx
0x180020d7a  jz      loc_1800217F5
0x180020d80  mov     rdx, [rdi]
0x180020d83  sub     rdx, rcx
0x180020d86  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180020d8a  xor     eax, eax
0x180020d8c  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x180020d90  mov     qword ptr [rsp+2F0h+var_2A8], r13
0x180020d95  mov     r9, r13
0x180020d98  test    rcx, rcx
0x180020d9b  jz      short loc_180020DAA
0x180020d9d  cmp     [rdi], rcx
0x180020da0  jz      short loc_180020DAA
0x180020da2  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x180020da7  mov     r9, rcx
0x180020daa  movaps  xmm0, [rsp+2F0h+var_2B8+8]
0x180020daf  movdqa  [rsp+2F0h+var_288+8], xmm0
0x180020db5  lea     rcx, [rbp+1F0h+var_1F0]; this
0x180020db9  call    ??0ZipFileLocal@win_musl@@QEAA@XZ; win_musl::ZipFileLocal::ZipFileLocal(void)
0x180020dbe  lea     rax, ??_7ZipFileCentral@win_musl@@6B@; const win_musl::ZipFileCentral::`vftable'
0x180020dc5  mov     [rbp+1F0h+var_1F0], rax
0x180020dc9  mov     [rbp+1F0h+var_100], 0Fh
0x180020dd4  mov     [rbp+1F0h+var_108], r13
0x180020ddb  mov     byte ptr [rbp+1F0h+Block], r13b
0x180020de2  mov     r8d, r13d
0x180020de5  mov     dword ptr [rsp+2F0h+var_288], r13d
0x180020dea  mov     word ptr [rsp+2F0h+var_298], r13w
0x180020df0  mov     r10d, r13d
0x180020df3  mov     dword ptr [rsp+2F0h+var_290], r13d
0x180020df8  mov     word ptr [rsp+2F0h+var_288+4], r13w
0x180020dfe  mov     ebx, 1
0x180020e03  test    edx, edx
0x180020e05  jz      short loc_180020E10
0x180020e07  test    r9, r9
0x180020e0a  jnz     loc_1800218BE
0x180020e10  mov     cl, bl
0x180020e12  movd    edx, xmm6
0x180020e16  lea     rdi, [rsp+2F0h+var_288+8]
0x180020e1b  lea     rax, [rbp+1F0h+var_270]
0x180020e1f  test    cl, cl
0x180020e21  cmovnz  rdi, rax
0x180020e25  mov     ecx, 4
0x180020e2a  mov     r14d, 0FF00h
0x180020e30  cmp     edx, ecx
0x180020e32  jb      loc_18002189B
0x180020e38  cmp     [r15+74h], r13b
0x180020e3c  jz      loc_18002189B
0x180020e42  mov     esi, [rdi]
0x180020e44  mov     eax, [rdi+4]
0x180020e47  mov     rbx, [rdi+8]
0x180020e4b  cmp     esi, ecx
0x180020e4d  jb      loc_180021B1C
0x180020e53  mov     [rsp+2F0h+Destination], r13d
0x180020e58  mov     r9d, ecx; SourceSize
0x180020e5b  mov     r8, rbx; Source
0x180020e5e  mov     edx, ecx; DestinationSize
0x180020e60  lea     rcx, [rsp+2F0h+Destination]; Destination
0x180020e65  call    cs:__imp_memmove_s
0x180020e6b  test    rbx, rbx
0x180020e6e  jz      loc_180021805
0x180020e74  lea     rcx, [rbx+4]
0x180020e78  lea     rdx, [rbx+rsi]
0x180020e7c  cmp     rdx, rcx
0x180020e7f  jz      loc_180021805
0x180020e85  cmp     rbx, rcx
0x180020e88  ja      loc_180021B53
0x180020e8e  cmp     rcx, rdx
0x180020e91  ja      loc_180021B53
0x180020e97  sub     edx, ecx
0x180020e99  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180020e9d  xor     eax, eax
0x180020e9f  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x180020ea3  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x180020ea8  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x180020ead  movdqu  xmmword ptr [rdi], xmm0
0x180020eb1  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x180020eb8  cmp     word ptr [rsp+2F0h+var_2A0], r14w
0x180020ebe  jz      loc_180021B9D
0x180020ec4  cmp     [rsp+2F0h+Destination], 2014B50h
0x180020ecc  jnz     loc_180021A87
0x180020ed2  mov     dword ptr [r15+70h], 2Eh ; '.'
0x180020eda  mov     rsi, [rsp+2F0h+var_278]
0x180020edf  mov     edi, dword ptr [rsp+2F0h+var_288+8]
0x180020ee3  test    edi, edi
0x180020ee5  jz      short loc_180020EFD
0x180020ee7  test    rsi, rsi
0x180020eea  jnz     loc_180021BAC
0x180020ef0  test    edi, edi
0x180020ef2  jz      short loc_180020EFD
0x180020ef4  test    rsi, rsi
0x180020ef7  jnz     loc_1800218AD
0x180020efd  mov     r14d, dword ptr [rbp+1F0h+var_270]
0x180020f01  cmp     r14d, 2Ah ; '*'
0x180020f05  jb      loc_180021F95
0x180020f0b  mov     r8d, dword ptr [rsp+2F0h+var_288]
0x180020f10  mov     r10d, dword ptr [rsp+2F0h+var_290]
0x180020f15  mov     ebx, 1
0x180020f1a  mov     [rsp+2F0h+var_2A0], r13d
0x180020f1f  mov     dword ptr [rsp+2F0h+var_288], r13d
0x180020f24  test    edi, edi
0x180020f26  jz      short loc_180020F31
0x180020f28  test    rsi, rsi
0x180020f2b  jnz     loc_180021BBA
0x180020f31  mov     al, bl
0x180020f33  mov     ecx, r14d
0x180020f36  lea     rbx, [rsp+2F0h+var_288+8]
0x180020f3b  lea     rdx, [rbp+1F0h+var_270]
0x180020f3f  test    al, al
0x180020f41  cmovnz  rbx, rdx
0x180020f45  cmp     ecx, 2Ah ; '*'
0x180020f48  jb      loc_180021347
0x180020f4e  mov     esi, [rbx]
0x180020f50  mov     eax, [rbx+4]
0x180020f53  mov     rdi, [rbx+8]
0x180020f57  mov     r14d, 2
0x180020f5d  cmp     esi, r14d
0x180020f60  jb      loc_180021BC4
0x180020f66  mov     word ptr [rsp+2F0h+Destination], r13w
0x180020f6c  mov     r9d, r14d; SourceSize
0x180020f6f  mov     r8, rdi; Source
0x180020f72  mov     edx, r14d; DestinationSize
0x180020f75  lea     rcx, [rsp+2F0h+Destination]; Destination
0x180020f7a  call    cs:__imp_memmove_s
0x180020f80  test    rdi, rdi
0x180020f83  jz      loc_180021841
0x180020f89  lea     rcx, [rdi+2]
0x180020f8d  lea     rdx, [rdi+rsi]
0x180020f91  cmp     rdx, rcx
0x180020f94  jz      loc_180021841
0x180020f9a  cmp     rdi, rcx
0x180020f9d  ja      loc_180021C00
0x180020fa3  cmp     rcx, rdx
0x180020fa6  ja      loc_180021C00
0x180020fac  sub     edx, ecx
0x180020fae  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180020fb2  xor     eax, eax
0x180020fb4  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x180020fb8  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x180020fbd  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x180020fc2  movdqu  xmmword ptr [rbx], xmm0
0x180020fc6  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x180020fcd  mov     eax, 0FF00h
0x180020fd2  cmp     word ptr [rsp+2F0h+var_2A0], ax
0x180020fd7  jz      loc_180021C4A
0x180020fdd  mov     cl, byte ptr [rsp+2F0h+Destination]
0x180020fe1  mov     [rbp+1F0h+var_123], cl
0x180020fe7  movzx   eax, word ptr [rsp+2F0h+Destination]
0x180020fec  shr     eax, 8
0x180020fef  mov     [rbp+1F0h+var_170], eax
0x180020ff5  movdqu  [rbp+1F0h+var_250], xmm0
0x180020ffa  lea     rax, [rsp+2F0h+var_288+4]
0x180020fff  mov     qword ptr [rsp+2F0h+var_2D0], rax
0x180021004  lea     r9, [rsp+2F0h+var_298]
0x180021009  mov     r8, rbx
0x18002100c  lea     rdx, [rbp+1F0h+var_250]
0x180021010  lea     rcx, [rbp+1F0h+var_1F0]
0x180021014  call    ?readFileHeaderCommon@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU4@PEAG3@Z; win_musl::consumption::readFileHeaderCommon(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,ushort *,ushort *)
0x180021019  mov     esi, [rbx]
0x18002101b  mov     eax, [rbx+4]
0x18002101e  mov     rdi, [rbx+8]
0x180021022  cmp     esi, r14d
0x180021025  jb      loc_180021C5F
0x18002102b  mov     word ptr [rsp+2F0h+Destination], r13w
0x180021031  mov     r9, r14; SourceSize
0x180021034  mov     r8, rdi; Source
0x180021037  mov     rdx, r14; DestinationSize
0x18002103a  lea     rcx, [rsp+2F0h+Destination]; Destination
0x18002103f  call    cs:__imp_memmove_s
0x180021045  test    rdi, rdi
0x180021048  jz      loc_180021850
0x18002104e  lea     rcx, [rdi+2]
0x180021052  lea     rdx, [rdi+rsi]
0x180021056  cmp     rdx, rcx
0x180021059  jz      loc_180021850
0x18002105f  cmp     rdi, rcx
0x180021062  ja      loc_180021C9B
0x180021068  cmp     rcx, rdx
0x18002106b  ja      loc_180021C9B
0x180021071  sub     edx, ecx
0x180021073  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180021077  xor     eax, eax
0x180021079  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x18002107d  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x180021082  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x180021087  movdqu  xmmword ptr [rbx], xmm0
0x18002108b  mov     word ptr [rsp+2F0h+var_2A0], 0FFh
0x180021092  mov     eax, 0FF00h
0x180021097  cmp     word ptr [rsp+2F0h+var_2A0], ax
0x18002109c  jz      loc_180021CE5
0x1800210a2  mov     esi, [rbx]
0x1800210a4  mov     eax, [rbx+4]
0x1800210a7  mov     rdi, [rbx+8]
0x1800210ab  cmp     esi, r14d
0x1800210ae  jb      loc_180021CFA
0x1800210b4  mov     word ptr [rsp+2F0h+var_2A0], r13w
0x1800210ba  mov     r9, r14; SourceSize
0x1800210bd  mov     r8, rdi; Source
0x1800210c0  mov     rdx, r14; DestinationSize
0x1800210c3  lea     rcx, [rsp+2F0h+var_2A0]; Destination
0x1800210c8  call    cs:__imp_memmove_s
0x1800210ce  test    rdi, rdi
0x1800210d1  jz      loc_18002185F
0x1800210d7  lea     rcx, [rdi+2]
0x1800210db  lea     rdx, [rdi+rsi]
0x1800210df  cmp     rdx, rcx
0x1800210e2  jz      loc_18002185F
0x1800210e8  cmp     rdi, rcx
0x1800210eb  ja      loc_180021D36
0x1800210f1  cmp     rcx, rdx
0x1800210f4  ja      loc_180021D36
0x1800210fa  sub     edx, ecx
0x1800210fc  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180021100  xor     eax, eax
0x180021102  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x180021106  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18002110b  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x180021110  movdqu  xmmword ptr [rbx], xmm0
0x180021114  mov     word ptr [rsp+2F0h+var_290], 0FFh
0x18002111b  mov     eax, 0FF00h
0x180021120  cmp     word ptr [rsp+2F0h+var_290], ax
0x180021125  jz      loc_180021D80
0x18002112b  movzx   eax, word ptr [rsp+2F0h+var_2A0]
0x180021130  mov     dword ptr [rsp+2F0h+var_288], eax
0x180021134  mov     esi, [rbx]
0x180021136  mov     eax, [rbx+4]
0x180021139  mov     rdi, [rbx+8]
0x18002113d  cmp     esi, r14d
0x180021140  jb      loc_180021D95
0x180021146  mov     word ptr [rsp+2F0h+var_290], r13w
0x18002114c  mov     r9, r14; SourceSize
0x18002114f  mov     r8, rdi; Source
0x180021152  mov     rdx, r14; DestinationSize
0x180021155  lea     rcx, [rsp+2F0h+var_290]; Destination
0x18002115a  call    cs:__imp_memmove_s
0x180021160  test    rdi, rdi
0x180021163  jz      loc_18002186E
0x180021169  lea     rcx, [rdi+2]
0x18002116d  lea     rdx, [rdi+rsi]
0x180021171  cmp     rdx, rcx
0x180021174  jz      loc_18002186E
0x18002117a  cmp     rdi, rcx
0x18002117d  ja      loc_180021DD1
0x180021183  cmp     rcx, rdx
0x180021186  ja      loc_180021DD1
0x18002118c  sub     edx, ecx
0x18002118e  mov     dword ptr [rsp+2F0h+var_2B8+8], edx
0x180021192  xor     eax, eax
0x180021194  mov     dword ptr [rsp+2F0h+var_2B8+0Ch], eax
0x180021198  mov     qword ptr [rsp+2F0h+var_2A8], rcx
0x18002119d  movups  xmm0, [rsp+2F0h+var_2B8+8]
0x1800211a2  movdqu  xmmword ptr [rbx], xmm0
0x1800211a6  mov     esi, [rbx]
0x1800211a8  mov     eax, [rbx+4]
0x1800211ab  mov     rdi, [rbx+8]
  ... truncated ...
```
