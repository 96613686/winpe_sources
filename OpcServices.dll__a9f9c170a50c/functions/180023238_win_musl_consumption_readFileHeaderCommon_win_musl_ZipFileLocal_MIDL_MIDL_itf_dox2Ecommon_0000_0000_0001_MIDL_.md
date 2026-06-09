# win_musl::consumption::readFileHeaderCommon(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,ushort *,ushort *)

- ea: `0x180023238`
- end: `0x1800240ff`
- name: `?readFileHeaderCommon@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU4@PEAG3@Z`
- size: `3783`
- prototype: `char __fastcall(__int64, unsigned int *, _OWORD *, _WORD *, _WORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a17c`
- `0x180020cc8`

## callees

- `0x18001a810`
- `0x180023238`
- `0x1800460f0`
- `0x1800517a0`
- `0x1800654b0`
- `0x18006980c`
- `0x1800b696c`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800232b2`
- `msvcrt!memmove_s` at `0x180023358`
- `msvcrt!memmove_s` at `0x1800233ea`
- `msvcrt!memmove_s` at `0x180023491`
- `msvcrt!memmove_s` at `0x18002352b`
- `msvcrt!memmove_s` at `0x1800235c6`
- `msvcrt!memmove_s` at `0x18002366a`
- `msvcrt!memmove_s` at `0x18002370e`
- `msvcrt!memmove_s` at `0x1800237ad`
- `msvcrt!memmove_s` at `0x180023846`
- `msvcrt!memmove_s` at `0x1800232b2`
- `msvcrt!memmove_s` at `0x180023358`
- `msvcrt!memmove_s` at `0x1800233ea`
- `msvcrt!memmove_s` at `0x180023491`
- `msvcrt!memmove_s` at `0x18002352b`
- `msvcrt!memmove_s` at `0x1800235c6`
- `msvcrt!memmove_s` at `0x18002366a`
- `msvcrt!memmove_s` at `0x18002370e`
- `msvcrt!memmove_s` at `0x1800237ad`
- `msvcrt!memmove_s` at `0x180023846`

## string_xrefs

- `0x180023edf`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180023f1a`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180023f55`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180023f90`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180023fcb`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180024006`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180024041`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x18002407c`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x1800240b7`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x1800240f2`: `onecore\printscan\dox\opc\zipio_lca_restricted\lib\external\win7.zipio\zipmodelreaders.cpp`
- `0x180023a06`: `win_musl::detail::vector_read`
- `0x180023a5f`: `win_musl::detail::vector_read`
- `0x180023aba`: `win_musl::detail::vector_read`
- `0x180023ba4`: `win_musl::detail::vector_read`
- `0x180023bfd`: `win_musl::detail::vector_read`
- `0x180023c56`: `win_musl::detail::vector_read`
- `0x180023ca9`: `win_musl::detail::vector_read`
- `0x180023cfc`: `win_musl::detail::vector_read`
- `0x180023d4f`: `win_musl::detail::vector_read`
- `0x180023da8`: `win_musl::detail::vector_read`
- `0x180023ed3`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023f0e`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023f49`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023f84`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023fbf`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023ffa`: `win_musl::consumption::readFileHeaderCommon`
- `0x180024035`: `win_musl::consumption::readFileHeaderCommon`
- `0x180024070`: `win_musl::consumption::readFileHeaderCommon`
- `0x1800240ab`: `win_musl::consumption::readFileHeaderCommon`
- `0x1800240e6`: `win_musl::consumption::readFileHeaderCommon`
- `0x180023f7d`: `compressed`
- `0x180023b00`: `Unsupported file compression (%{Option}): Only Deflate and Store compression options are supported`
- `0x180023f42`: `uncompressed`
- `0x180023e6d`: `central directory encryption unsupported `

## pseudocode

```c
char __fastcall win_musl::consumption::readFileHeaderCommon(
        __int64 a1,
        unsigned int *a2,
        _OWORD *a3,
        _WORD *a4,
        _WORD *a5)
{
  __int64 v9; // rsi
  unsigned int v10; // eax
  char *v11; // rdi
  char *v12; // rcx
  char *v13; // rdx
  char v14; // cl
  __int64 v15; // rsi
  unsigned int v16; // eax
  char *v17; // rdi
  char *v18; // rcx
  char *v19; // rdx
  char v20; // r15
  __int64 v21; // rsi
  unsigned int v22; // eax
  char *v23; // rdi
  char *v24; // rcx
  char *v25; // rdx
  int v26; // eax
  __int64 v27; // rsi
  unsigned int v28; // eax
  char *v29; // rdi
  char *v30; // rcx
  char *v31; // rdx
  __int64 v32; // rsi
  unsigned int v33; // eax
  char *v34; // rdi
  char *v35; // rcx
  char *v36; // rdx
  __int64 v37; // rsi
  unsigned int v38; // eax
  char *v39; // rdi
  char *v40; // rcx
  char *v41; // rdx
  unsigned int v42; // eax
  __int64 v43; // rsi
  unsigned int v44; // eax
  char *v45; // rdi
  char *v46; // rcx
  char *v47; // rdx
  __int64 v48; // rsi
  unsigned int v49; // eax
  char *v50; // rdi
  char *v51; // rcx
  char *v52; // rdx
  __int64 v53; // rsi
  unsigned int v54; // eax
  char *v55; // rdi
  char *v56; // rcx
  char *v57; // rdx
  __int64 v58; // rsi
  unsigned int v59; // eax
  char *v60; // rdi
  char *v61; // rcx
  char *v62; // rdx
  __int128 v63; // xmm0
  unsigned __int16 v64; // cx
  unsigned __int16 v65; // cx
  char result; // al
  __int16 v67; // cx
  __int64 v68; // rbx
  win_musl::Formatter *v69; // rax
  struct win_musl::TStringEllipseBase *v70; // rax
  unsigned int v71; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Destination[6]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v73; // [rsp+50h] [rbp-B0h] BYREF
  int v74; // [rsp+60h] [rbp-A0h] BYREF
  _WORD *v75; // [rsp+68h] [rbp-98h]
  __int64 v76; // [rsp+70h] [rbp-90h]
  _BYTE v77[160]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v78[40]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v79[40]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+170h] [rbp+70h] BYREF

  v76 = -2;
  v75 = a5;
  v9 = *a2;
  v10 = a2[1];
  v11 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v9 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v10;
    *((_QWORD *)&v73 + 1) = v11;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      41,
      "win_musl::consumption::readFileHeaderCommon",
      "OsAndVersion",
      2,
      &v73);
  }
  Destination[0] = 0;
  memmove_s(Destination, 2u, v11, 2u);
  if ( !v11 || (v12 = v11 + 2, v13 = &v11[v9], &v11[v9] == v11 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v11 > v12 || v12 > v13 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v13 - (_DWORD)v12);
    *((_QWORD *)&v73 + 1) = v11 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v71) = 255;
  v14 = Destination[0];
  *(_DWORD *)(a1 + 200) = HIBYTE(Destination[0]);
  *(_BYTE *)(a1 + 204) = v14;
  v15 = *a2;
  v16 = a2[1];
  v17 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v15 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v16;
    *((_QWORD *)&v73 + 1) = v17;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      48,
      "win_musl::consumption::readFileHeaderCommon",
      "generalPurposeBitFlag",
      2,
      &v73);
  }
  Destination[0] = 0;
  memmove_s(Destination, 2u, v17, 2u);
  if ( !v17 || (v18 = v17 + 2, v19 = &v17[v15], &v17[v15] == v17 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v17 > v18 || v18 > v19 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v19 - (_DWORD)v18);
    *((_QWORD *)&v73 + 1) = v17 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v71) = 255;
  v20 = Destination[0];
  v21 = *a2;
  v22 = a2[1];
  v23 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v21 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v22;
    *((_QWORD *)&v73 + 1) = v23;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      52,
      "win_musl::consumption::readFileHeaderCommon",
      "method",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v23, 2u);
  if ( !v23 || (v24 = v23 + 2, v25 = &v23[v21], &v23[v21] == v23 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v23 > v24 || v24 > v25 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v25 - (_DWORD)v24);
    *((_QWORD *)&v73 + 1) = v23 + 2;
  }
  *(_OWORD *)a2 = v73;
  v26 = (unsigned __int16)v71;
  v74 = (unsigned __int16)v71;
  *(_DWORD *)(a1 + 140) = (unsigned __int16)v71;
  if ( v26 && v26 != 8 )
  {
    std::wstring::wstring(
      v78,
      L"Unsupported file compression (%{Option}): Only Deflate and Store compression options are supported",
      0);
    v68 = win_musl::Formatter::Formatter(pExceptionObject, v78);
    std::wstring::wstring(v79, L"Option");
    v69 = (win_musl::Formatter *)win_musl::Formatter::insert<unsigned int>(v68, v79, &v74);
    v70 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v69);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0x41u,
      0x80511008,
      v70);
    throw (SplException::THResultException *)v77;
  }
  v27 = *a2;
  v28 = a2[1];
  v29 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v27 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v28;
    *((_QWORD *)&v73 + 1) = v29;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      69,
      "win_musl::consumption::readFileHeaderCommon",
      "entry->header.timeLastModified",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v29, 2u);
  if ( !v29 || (v30 = v29 + 2, v31 = &v29[v27], &v29[v27] == v29 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v29 > v30 || v30 > v31 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v31 - (_DWORD)v30);
    *((_QWORD *)&v73 + 1) = v29 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_WORD *)(a1 + 144) = v71;
  v32 = *a2;
  v33 = a2[1];
  v34 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v32 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v33;
    *((_QWORD *)&v73 + 1) = v34;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      72,
      "win_musl::consumption::readFileHeaderCommon",
      "entry->header.dateLastModified",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v34, 2u);
  if ( !v34 || (v35 = v34 + 2, v36 = &v34[v32], &v34[v32] == v34 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v34 > v35 || v35 > v36 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v36 - (_DWORD)v35);
    *((_QWORD *)&v73 + 1) = v34 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_WORD *)(a1 + 146) = v71;
  v37 = *a2;
  v38 = a2[1];
  v39 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v37 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v38;
    *((_QWORD *)&v73 + 1) = v39;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      76,
      "win_musl::consumption::readFileHeaderCommon",
      "crc",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v39, 4u);
  if ( !v39 || (v40 = v39 + 4, v41 = &v39[v37], &v39[v37] == v39 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v39 > v40 || v40 > v41 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v41 - (_DWORD)v40);
    *((_QWORD *)&v73 + 1) = v39 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  v42 = v71;
  *(_DWORD *)(a1 + 192) = 2;
  *(_DWORD *)(a1 + 196) = v42;
  v43 = *a2;
  v44 = a2[1];
  v45 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v43 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v44;
    *((_QWORD *)&v73 + 1) = v45;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      81,
      "win_musl::consumption::readFileHeaderCommon",
      "compressed",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v45, 4u);
  if ( !v45 || (v46 = v45 + 4, v47 = &v45[v43], &v45[v43] == v45 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v45 > v46 || v46 > v47 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v47 - (_DWORD)v46);
    *((_QWORD *)&v73 + 1) = v45 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_QWORD *)(a1 + 168) = 2;
  *(_QWORD *)(a1 + 176) = v71;
  v48 = *a2;
  v49 = a2[1];
  v50 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v48 < 4 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v49;
    *((_QWORD *)&v73 + 1) = v50;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      86,
      "win_musl::consumption::readFileHeaderCommon",
      "uncompressed",
      4,
      &v73);
  }
  v71 = 0;
  memmove_s(&v71, 4u, v50, 4u);
  if ( !v50 || (v51 = v50 + 4, v52 = &v50[v48], &v50[v48] == v50 + 4) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v50 > v51 || v51 > v52 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v52 - (_DWORD)v51);
    *((_QWORD *)&v73 + 1) = v50 + 4;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *(_QWORD *)(a1 + 152) = 2;
  *(_QWORD *)(a1 + 160) = v71;
  v53 = *a2;
  v54 = a2[1];
  v55 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v53 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v54;
    *((_QWORD *)&v73 + 1) = v55;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      90,
      "win_musl::consumption::readFileHeaderCommon",
      "*bytesNeededName",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v55, 2u);
  if ( !v55 || (v56 = v55 + 2, v57 = &v55[v53], &v55[v53] == v55 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v55 > v56 || v56 > v57 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v57 - (_DWORD)v56);
    *((_QWORD *)&v73 + 1) = v55 + 2;
  }
  *(_OWORD *)a2 = v73;
  LOWORD(v74) = 255;
  *a4 = v71;
  v58 = *a2;
  v59 = a2[1];
  v60 = (char *)*((_QWORD *)a2 + 1);
  if ( (unsigned int)v58 < 2 )
  {
    LODWORD(v73) = *a2;
    DWORD1(v73) = v59;
    *((_QWORD *)&v73 + 1) = v60;
    win_musl::detail::ThrowReadError(
      "onecore\\printscan\\dox\\opc\\zipio_lca_restricted\\lib\\external\\win7.zipio\\zipmodelreaders.cpp",
      93,
      "win_musl::consumption::readFileHeaderCommon",
      "*bytesNeededExtra",
      2,
      &v73);
  }
  LOWORD(v71) = 0;
  memmove_s(&v71, 2u, v60, 2u);
  if ( !v60 || (v61 = v60 + 2, v62 = &v60[v58], &v60[v58] == v60 + 2) )
  {
    v73 = 0u;
  }
  else
  {
    if ( v60 > v61 || v61 > v62 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v77,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)v77;
    }
    *(_QWORD *)&v73 = (unsigned int)((_DWORD)v62 - (_DWORD)v61);
    *((_QWORD *)&v73 + 1) = v60 + 2;
  }
  v63 = v73;
  LOWORD(v74) = 255;
  *v75 = v71;
  if ( (v20 & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0x65u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"Unsupported file type: it is Encrypted");
    throw (SplException::THResultException *)v77;
  }
  v64 = Destination[0] >> 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 140) - 8) <= 1 )
    *(_DWORD *)(a1 + 136) = v64 & 3;
  v65 = v64 >> 2;
  result = v65 & 1;
  *(_BYTE *)(a1 + 206) = v65 & 1;
  v67 = v65 >> 3;
  if ( (v67 & 1) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0xA4u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"file encryption unsupported");
    throw (SplException::THResultException *)v77;
  }
  if ( (v67 & 0x80u) != 0 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v77,
      0xC0u,
      0x80511008,
      (struct win_musl::TStringEllipseBase *)L"central directory encryption unsupported ");
    throw (SplException::THResultException *)v77;
  }
  *a3 = v63;
  return result;
}

```

## disassembly

```asm
0x180023238  push    rbp
0x18002323a  push    rbx
0x18002323b  push    rsi
0x18002323c  push    rdi
0x18002323d  push    r12
0x18002323f  push    r13
0x180023241  push    r14
0x180023243  push    r15
0x180023245  lea     rbp, [rsp-128h]
0x18002324d  sub     rsp, 228h
0x180023254  mov     [rsp+260h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x18002325d  mov     rax, cs:__security_cookie
0x180023264  xor     rax, rsp
0x180023267  mov     [rbp+160h+var_50], rax
0x18002326e  mov     r12, r9
0x180023271  mov     r13, r8
0x180023274  mov     rbx, rdx
0x180023277  mov     r14, rcx
0x18002327a  mov     rax, [rbp+160h+arg_20]
0x180023281  mov     [rsp+260h+var_1F8], rax
0x180023286  mov     esi, [rdx]
0x180023288  mov     eax, [rdx+4]
0x18002328b  mov     rdi, [rdx+8]
0x18002328f  mov     ecx, 2
0x180023294  cmp     esi, ecx
0x180023296  jb      loc_1800240C4
0x18002329c  xor     r15d, r15d
0x18002329f  mov     [rsp+260h+Destination], r15w
0x1800232a5  mov     r9d, ecx; SourceSize
0x1800232a8  mov     r8, rdi; Source
0x1800232ab  mov     edx, ecx; DestinationSize
0x1800232ad  lea     rcx, [rsp+260h+Destination]; Destination
0x1800232b2  call    cs:__imp_memmove_s
0x1800232b8  test    rdi, rdi
0x1800232bb  jz      loc_18002392C
0x1800232c1  lea     rcx, [rdi+2]
0x1800232c5  lea     rdx, [rdi+rsi]
0x1800232c9  cmp     rdx, rcx
0x1800232cc  jz      loc_18002392C
0x1800232d2  cmp     rdi, rcx
0x1800232d5  ja      loc_1800239EA
0x1800232db  cmp     rcx, rdx
0x1800232de  ja      loc_1800239EA
0x1800232e4  sub     edx, ecx
0x1800232e6  mov     dword ptr [rsp+260h+var_210], edx
0x1800232ea  xor     eax, eax
0x1800232ec  mov     dword ptr [rsp+260h+var_210+4], eax
0x1800232f0  mov     qword ptr [rsp+260h+var_210+8], rcx
0x1800232f5  movups  xmm0, [rsp+260h+var_210]
0x1800232fa  movdqu  xmmword ptr [rbx], xmm0
0x1800232fe  mov     word ptr [rsp+260h+var_220], 0FFh
0x180023305  mov     eax, 0FF00h
0x18002330a  cmp     word ptr [rsp+260h+var_220], ax
0x18002330f  jz      loc_180023A2E
0x180023315  mov     cl, byte ptr [rsp+260h+Destination]
0x180023319  movzx   eax, [rsp+260h+Destination]
0x18002331e  shr     eax, 8
0x180023321  mov     [r14+0C8h], eax
0x180023328  mov     [r14+0CCh], cl
0x18002332f  mov     esi, [rbx]
0x180023331  mov     eax, [rbx+4]
0x180023334  mov     rdi, [rbx+8]
0x180023338  mov     ecx, 2
0x18002333d  cmp     esi, ecx
0x18002333f  jb      loc_180024089
0x180023345  mov     [rsp+260h+Destination], r15w
0x18002334b  mov     r9d, ecx; SourceSize
0x18002334e  mov     r8, rdi; Source
0x180023351  mov     edx, ecx; DestinationSize
0x180023353  lea     rcx, [rsp+260h+Destination]; Destination
0x180023358  call    cs:__imp_memmove_s
0x18002335e  test    rdi, rdi
0x180023361  jz      loc_18002393B
0x180023367  lea     rcx, [rdi+2]
0x18002336b  lea     rdx, [rdi+rsi]
0x18002336f  cmp     rdx, rcx
0x180023372  jz      loc_18002393B
0x180023378  cmp     rdi, rcx
0x18002337b  ja      loc_180023A43
0x180023381  cmp     rcx, rdx
0x180023384  ja      loc_180023A43
0x18002338a  sub     edx, ecx
0x18002338c  mov     dword ptr [rsp+260h+var_210], edx
0x180023390  xor     eax, eax
0x180023392  mov     dword ptr [rsp+260h+var_210+4], eax
0x180023396  mov     qword ptr [rsp+260h+var_210+8], rcx
0x18002339b  movups  xmm0, [rsp+260h+var_210]
0x1800233a0  movdqu  xmmword ptr [rbx], xmm0
0x1800233a4  mov     word ptr [rsp+260h+var_220], 0FFh
0x1800233ab  mov     eax, 0FF00h
0x1800233b0  cmp     word ptr [rsp+260h+var_220], ax
0x1800233b5  jz      loc_180023A87
0x1800233bb  mov     r15b, byte ptr [rsp+260h+Destination]
0x1800233c0  mov     esi, [rbx]
0x1800233c2  mov     eax, [rbx+4]
0x1800233c5  mov     rdi, [rbx+8]
0x1800233c9  mov     ecx, 2
0x1800233ce  cmp     esi, ecx
0x1800233d0  jb      loc_18002404E
0x1800233d6  xor     eax, eax
0x1800233d8  mov     word ptr [rsp+260h+var_220], ax
0x1800233dd  mov     r9d, ecx; SourceSize
0x1800233e0  mov     r8, rdi; Source
0x1800233e3  mov     edx, ecx; DestinationSize
0x1800233e5  lea     rcx, [rsp+260h+var_220]; Destination
0x1800233ea  call    cs:__imp_memmove_s
0x1800233f0  xor     r8d, r8d
0x1800233f3  test    rdi, rdi
0x1800233f6  jz      loc_18002394A
0x1800233fc  lea     rcx, [rdi+2]
0x180023400  lea     rdx, [rdi+rsi]
0x180023404  cmp     rdx, rcx
0x180023407  jz      loc_18002394A
0x18002340d  cmp     rdi, rcx
0x180023410  ja      loc_180023A9E
0x180023416  cmp     rcx, rdx
0x180023419  ja      loc_180023A9E
0x18002341f  sub     edx, ecx
0x180023421  mov     dword ptr [rsp+260h+var_210], edx
0x180023425  xor     eax, eax
0x180023427  mov     dword ptr [rsp+260h+var_210+4], eax
0x18002342b  mov     qword ptr [rsp+260h+var_210+8], rcx
0x180023430  movups  xmm0, [rsp+260h+var_210]
0x180023435  movdqu  xmmword ptr [rbx], xmm0
0x180023439  mov     word ptr [rsp+260h+var_200], 0FFh
0x180023440  mov     eax, 0FF00h
0x180023445  cmp     word ptr [rsp+260h+var_200], ax
0x18002344a  jz      loc_180023AE2
0x180023450  movzx   eax, word ptr [rsp+260h+var_220]
0x180023455  mov     [rsp+260h+var_200], eax
0x180023459  mov     [r14+8Ch], eax
0x180023460  test    eax, eax
0x180023462  jnz     loc_180023AF7
0x180023468  mov     esi, [rbx]
0x18002346a  mov     eax, [rbx+4]
0x18002346d  mov     rdi, [rbx+8]
0x180023471  mov     ecx, 2
0x180023476  cmp     esi, ecx
0x180023478  jb      loc_180024013
0x18002347e  mov     word ptr [rsp+260h+var_220], r8w
0x180023484  mov     r9d, ecx; SourceSize
0x180023487  mov     r8, rdi; Source
0x18002348a  mov     edx, ecx; DestinationSize
0x18002348c  lea     rcx, [rsp+260h+var_220]; Destination
0x180023491  call    cs:__imp_memmove_s
0x180023497  test    rdi, rdi
0x18002349a  jz      loc_180023959
0x1800234a0  lea     rcx, [rdi+2]
0x1800234a4  lea     rdx, [rdi+rsi]
0x1800234a8  cmp     rdx, rcx
0x1800234ab  jz      loc_180023959
0x1800234b1  cmp     rdi, rcx
0x1800234b4  ja      loc_180023B88
0x1800234ba  cmp     rcx, rdx
0x1800234bd  ja      loc_180023B88
0x1800234c3  sub     edx, ecx
0x1800234c5  mov     dword ptr [rsp+260h+var_210], edx
0x1800234c9  xor     eax, eax
0x1800234cb  mov     dword ptr [rsp+260h+var_210+4], eax
0x1800234cf  mov     qword ptr [rsp+260h+var_210+8], rcx
0x1800234d4  movups  xmm0, [rsp+260h+var_210]
0x1800234d9  movdqu  xmmword ptr [rbx], xmm0
0x1800234dd  mov     word ptr [rsp+260h+var_200], 0FFh
0x1800234e4  mov     eax, 0FF00h
0x1800234e9  cmp     word ptr [rsp+260h+var_200], ax
0x1800234ee  jz      loc_180023BCC
0x1800234f4  movzx   eax, word ptr [rsp+260h+var_220]
0x1800234f9  mov     [r14+90h], ax
0x180023501  mov     esi, [rbx]
0x180023503  mov     eax, [rbx+4]
0x180023506  mov     rdi, [rbx+8]
0x18002350a  mov     ecx, 2
0x18002350f  cmp     esi, ecx
0x180023511  jb      loc_180023FD8
0x180023517  xor     eax, eax
0x180023519  mov     word ptr [rsp+260h+var_220], ax
0x18002351e  mov     r9d, ecx; SourceSize
0x180023521  mov     r8, rdi; Source
0x180023524  mov     edx, ecx; DestinationSize
0x180023526  lea     rcx, [rsp+260h+var_220]; Destination
0x18002352b  call    cs:__imp_memmove_s
0x180023531  xor     r8d, r8d
0x180023534  test    rdi, rdi
0x180023537  jz      loc_180023970
0x18002353d  lea     rcx, [rdi+2]
0x180023541  lea     rdx, [rdi+rsi]
0x180023545  cmp     rdx, rcx
0x180023548  jz      loc_180023970
0x18002354e  cmp     rdi, rcx
0x180023551  ja      loc_180023BE1
0x180023557  cmp     rcx, rdx
0x18002355a  ja      loc_180023BE1
0x180023560  sub     edx, ecx
0x180023562  mov     dword ptr [rsp+260h+var_210], edx
0x180023566  xor     eax, eax
0x180023568  mov     dword ptr [rsp+260h+var_210+4], eax
0x18002356c  mov     qword ptr [rsp+260h+var_210+8], rcx
0x180023571  movups  xmm0, [rsp+260h+var_210]
0x180023576  movdqu  xmmword ptr [rbx], xmm0
0x18002357a  mov     word ptr [rsp+260h+var_200], 0FFh
0x180023581  mov     eax, 0FF00h
0x180023586  cmp     word ptr [rsp+260h+var_200], ax
0x18002358b  jz      loc_180023C25
0x180023591  movzx   eax, word ptr [rsp+260h+var_220]
0x180023596  mov     [r14+92h], ax
0x18002359e  mov     esi, [rbx]
0x1800235a0  mov     eax, [rbx+4]
0x1800235a3  mov     rdi, [rbx+8]
0x1800235a7  mov     ecx, 4
0x1800235ac  cmp     esi, ecx
0x1800235ae  jb      loc_180023F9D
0x1800235b4  mov     [rsp+260h+var_220], r8d
0x1800235b9  mov     r9d, ecx; SourceSize
0x1800235bc  mov     r8, rdi; Source
0x1800235bf  mov     edx, ecx; DestinationSize
0x1800235c1  lea     rcx, [rsp+260h+var_220]; Destination
0x1800235c6  call    cs:__imp_memmove_s
0x1800235cc  test    rdi, rdi
0x1800235cf  jz      loc_18002397F
0x1800235d5  lea     rcx, [rdi+4]
0x1800235d9  lea     rdx, [rdi+rsi]
0x1800235dd  cmp     rdx, rcx
0x1800235e0  jz      loc_18002397F
0x1800235e6  cmp     rdi, rcx
0x1800235e9  ja      loc_180023C3A
0x1800235ef  cmp     rcx, rdx
0x1800235f2  ja      loc_180023C3A
0x1800235f8  sub     edx, ecx
0x1800235fa  mov     dword ptr [rsp+260h+var_210], edx
0x1800235fe  xor     eax, eax
0x180023600  mov     dword ptr [rsp+260h+var_210+4], eax
0x180023604  mov     qword ptr [rsp+260h+var_210+8], rcx
0x180023609  movups  xmm0, [rsp+260h+var_210]
0x18002360e  movdqu  xmmword ptr [rbx], xmm0
0x180023612  mov     word ptr [rsp+260h+var_200], 0FFh
0x180023619  mov     eax, 0FF00h
0x18002361e  cmp     word ptr [rsp+260h+var_200], ax
0x180023623  jz      loc_180023C7E
0x180023629  mov     eax, [rsp+260h+var_220]
0x18002362d  mov     dword ptr [r14+0C0h], 2
0x180023638  mov     [r14+0C4h], eax
0x18002363f  mov     esi, [rbx]
0x180023641  mov     eax, [rbx+4]
0x180023644  mov     rdi, [rbx+8]
0x180023648  mov     ecx, 4
0x18002364d  cmp     esi, ecx
0x18002364f  jb      loc_180023F62
0x180023655  mov     [rsp+260h+var_220], 0
0x18002365d  mov     r9d, ecx; SourceSize
0x180023660  mov     r8, rdi; Source
0x180023663  mov     edx, ecx; DestinationSize
0x180023665  lea     rcx, [rsp+260h+var_220]; Destination
0x18002366a  call    cs:__imp_memmove_s
0x180023670  test    rdi, rdi
0x180023673  jz      loc_180023996
0x180023679  lea     rcx, [rdi+4]
0x18002367d  lea     rdx, [rdi+rsi]
0x180023681  cmp     rdx, rcx
0x180023684  jz      loc_180023996
0x18002368a  cmp     rdi, rcx
0x18002368d  ja      loc_180023C8D
0x180023693  cmp     rcx, rdx
0x180023696  ja      loc_180023C8D
0x18002369c  sub     edx, ecx
0x18002369e  mov     dword ptr [rsp+260h+var_210], edx
0x1800236a2  xor     eax, eax
0x1800236a4  mov     dword ptr [rsp+260h+var_210+4], eax
0x1800236a8  mov     qword ptr [rsp+260h+var_210+8], rcx
0x1800236ad  movups  xmm0, [rsp+260h+var_210]
0x1800236b2  movdqu  xmmword ptr [rbx], xmm0
0x1800236b6  mov     word ptr [rsp+260h+var_200], 0FFh
0x1800236bd  mov     eax, 0FF00h
0x1800236c2  cmp     word ptr [rsp+260h+var_200], ax
0x1800236c7  jz      loc_180023CD1
0x1800236cd  mov     qword ptr [r14+0A8h], 2
0x1800236d8  mov     eax, [rsp+260h+var_220]
0x1800236dc  mov     [r14+0B0h], rax
0x1800236e3  mov     esi, [rbx]
0x1800236e5  mov     eax, [rbx+4]
0x1800236e8  mov     rdi, [rbx+8]
0x1800236ec  mov     ecx, 4
0x1800236f1  cmp     esi, ecx
0x1800236f3  jb      loc_180023F27
0x1800236f9  mov     [rsp+260h+var_220], 0
0x180023701  mov     r9d, ecx; SourceSize
0x180023704  mov     r8, rdi; Source
0x180023707  mov     edx, ecx; DestinationSize
0x180023709  lea     rcx, [rsp+260h+var_220]; Destination
0x18002370e  call    cs:__imp_memmove_s
0x180023714  test    rdi, rdi
0x180023717  jz      loc_1800239AD
0x18002371d  lea     rcx, [rdi+4]
0x180023721  lea     rdx, [rdi+rsi]
0x180023725  cmp     rdx, rcx
0x180023728  jz      loc_1800239AD
0x18002372e  cmp     rdi, rcx
0x180023731  ja      loc_180023CE0
0x180023737  cmp     rcx, rdx
0x18002373a  ja      loc_180023CE0
0x180023740  sub     edx, ecx
  ... truncated ...
```
