# SDK::ActiveLicense::EditGlobalInformation(ABI::Windows::Storage::Streams::IRandomAccessStream *,int,int)

- ea: `0x180014a60`
- end: `0x180015622`
- name: `?EditGlobalInformation@ActiveLicense@SDK@@UEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@HH@Z`
- size: `3010`
- prototype: `__int64 __fastcall(SDK::ActiveLicense *__hidden this, struct ABI::Windows::Storage::Streams::IRandomAccessStream *, int, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003cc4`
- `0x180003d30`
- `0x180003d3c`
- `0x180004110`
- `0x1800076d0`
- `0x180014870`
- `0x180014a60`
- `0x180015630`
- `0x1800157a0`
- `0x1800a023c`
- `0x1800a02eb`
- `0x1800a02f7`
- `0x1800abad8`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180014d76`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180014fdf`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015268`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015407`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001544e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015490`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800154de`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015525`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015567`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800155b5`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180014d76`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180014fdf`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015268`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015407`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001544e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015490`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800154de`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015525`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180015567`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800155b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015296`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015296`

## string_xrefs

- `0x1800151fe`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall SDK::ActiveLicense::EditGlobalInformation(
        SDK::ActiveLicense *this,
        struct ABI::Windows::Storage::Streams::IRandomAccessStream *a2,
        int a3,
        int a4)
{
  int v4; // r8d
  int v5; // r14d
  float v6; // xmm6_4
  unsigned int v7; // r13d
  unsigned int v8; // r12d
  size_t v9; // r8
  size_t v10; // rsi
  void **v11; // r9
  void **v12; // rax
  size_t v13; // r9
  size_t v14; // rdx
  void **v15; // rbx
  char *v16; // rbx
  size_t v17; // r8
  size_t v18; // rdi
  void **v19; // r9
  void **v20; // rax
  size_t v21; // r9
  size_t v22; // rdx
  void **v23; // rbx
  char *v24; // rbx
  size_t v25; // rsi
  void **v26; // r15
  size_t v27; // r14
  unsigned __int64 v28; // rbx
  void **v29; // rdi
  void **v30; // rdx
  __int64 v31; // rax
  void *v32; // rcx
  size_t v33; // r8
  size_t v34; // rsi
  void **v35; // r9
  void **v36; // rax
  size_t v37; // r9
  size_t v38; // rdx
  void **v39; // rbx
  char *v40; // rbx
  size_t v41; // r8
  size_t v42; // rdi
  void **v43; // r9
  void **v44; // rax
  size_t v45; // r9
  size_t v46; // rdx
  void **v47; // rbx
  char *v48; // rbx
  size_t v49; // rsi
  void **v50; // r15
  size_t v51; // r14
  unsigned __int64 v52; // rbx
  void **v53; // rdi
  void **v54; // rdx
  __int64 v55; // rax
  void *v56; // rcx
  unsigned __int64 v57; // r8
  size_t v58; // rdi
  void **v59; // r9
  void **v60; // rax
  unsigned __int64 v61; // r9
  size_t v62; // rdx
  void **v63; // rbx
  char *v64; // rbx
  unsigned int ActivationFactory; // ebx
  __int64 v66; // rcx
  char *v67; // rdi
  unsigned __int64 v68; // r13
  void **v69; // r14
  unsigned __int64 v70; // r15
  void **v71; // rsi
  _OWORD *v72; // rax
  char *v73; // rdx
  __int64 v74; // rcx
  void **v75; // rcx
  void **v76; // rcx
  void **v77; // rax
  const WCHAR *p_sourceString_8; // rcx
  void *v79; // rcx
  HRESULT v80; // eax
  HSTRING v81; // rcx
  struct ABI::Windows::Storage::Streams::IRandomAccessStream *v82; // r12
  __int64 v83; // rcx
  __int64 v84; // rcx
  void *v85; // rcx
  void **v86; // rax
  void *v87; // rcx
  void *v88; // rcx
  void **v89; // rax
  void *v90; // rcx
  void *v91; // rcx
  void *Block_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  __m128i si128; // [rsp+48h] [rbp-C0h]
  void *v95[2]; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v96; // [rsp+68h] [rbp-A0h]
  __int128 sourceString_8; // [rsp+78h] [rbp-90h] BYREF
  UINT32 length[4]; // [rsp+88h] [rbp-80h]
  struct ABI::Windows::Storage::Streams::IRandomAccessStream *v99; // [rsp+98h] [rbp-70h]
  HSTRING string; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v101; // [rsp+A8h] [rbp-60h] BYREF
  void *v102[2]; // [rsp+B0h] [rbp-58h] BYREF
  size_t v103; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v104; // [rsp+C8h] [rbp-40h]
  void *v105[2]; // [rsp+D0h] [rbp-38h] BYREF
  size_t v106; // [rsp+E0h] [rbp-28h]
  unsigned __int64 v107; // [rsp+E8h] [rbp-20h]
  void *v108[2]; // [rsp+F0h] [rbp-18h] BYREF
  size_t v109; // [rsp+100h] [rbp-8h]
  unsigned __int64 v110; // [rsp+108h] [rbp+0h]
  __int64 v111; // [rsp+110h] [rbp+8h] BYREF
  void *v112[2]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int64 v113; // [rsp+128h] [rbp+20h]
  unsigned __int64 v114; // [rsp+130h] [rbp+28h]
  void *Src[2]; // [rsp+138h] [rbp+30h] BYREF
  size_t Size; // [rsp+148h] [rbp+40h]
  unsigned __int64 v117; // [rsp+150h] [rbp+48h]
  char v118[8]; // [rsp+158h] [rbp+50h] BYREF
  __int64 v119; // [rsp+160h] [rbp+58h] BYREF
  __int64 v120; // [rsp+168h] [rbp+60h] BYREF
  void *v121[2]; // [rsp+170h] [rbp+68h] BYREF
  __int128 v122; // [rsp+180h] [rbp+78h]
  void *v123[2]; // [rsp+190h] [rbp+88h] BYREF
  __int128 v124; // [rsp+1A0h] [rbp+98h]

  v99 = a2;
  v4 = (int)(float)((float)((float)a3 / 25400.0) * 72.0);
  v5 = (int)(float)((float)((float)a4 / 25400.0) * 72.0);
  v6 = FLOAT_16_0;
  if ( v4 < 200 )
    v6 = FLOAT_10_0;
  if ( v4 < 125 )
    v6 = FLOAT_6_0;
  v7 = v5 / 2;
  v8 = 0;
  if ( v4 / 2 - (int)(float)(v6 * 12.5) / 2 >= 0 )
    v8 = v4 / 2 - (int)(float)(v6 * 12.5) / 2;
  std::to_string(Src, (unsigned int)v4);
  v9 = Size;
  v10 = 5 - Size;
  v11 = Src;
  if ( v117 >= 0x10 )
    v11 = (void **)Src[0];
  v12 = Src;
  if ( v117 >= 0x10 )
    v12 = (void **)Src[0];
  v13 = (char *)v11 - (char *)v12;
  if ( Size < v13 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v14 = v117 - Size;
  _mm_lfence();
  if ( v10 > v14 )
  {
    std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(
      Src,
      5 - Size,
      48);
  }
  else
  {
    Size = 5;
    v15 = Src;
    if ( v117 >= 0x10 )
      v15 = (void **)Src[0];
    v16 = (char *)v15 + v13;
    memmove_0(&v16[v10], v16, v9 - v13 + 1);
    memset_0(v16, 48, v10);
  }
  std::to_string(v108, (unsigned int)v5);
  v17 = v109;
  v18 = 5 - v109;
  v19 = v108;
  if ( v110 >= 0x10 )
    v19 = (void **)v108[0];
  v20 = v108;
  if ( v110 >= 0x10 )
    v20 = (void **)v108[0];
  v21 = (char *)v19 - (char *)v20;
  if ( v109 < v21 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v22 = v110 - v109;
  _mm_lfence();
  if ( v18 > v22 )
  {
    std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(
      v108,
      v18,
      48);
  }
  else
  {
    v109 = 5;
    v23 = v108;
    if ( v110 >= 0x10 )
      v23 = (void **)v108[0];
    v24 = (char *)v23 + v21;
    memmove_0(&v24[v18], v24, v17 - v21 + 1);
    memset_0(v24, 48, v18);
  }
  v25 = Size;
  if ( Size == 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  v26 = Src;
  if ( v117 >= 0x10 )
    v26 = (void **)Src[0];
  *(_OWORD *)Block_8 = 0;
  si128 = 0;
  v27 = Size + 1;
  v28 = 15;
  v29 = Block_8;
  if ( Size + 1 > 0xF )
  {
    v28 = v27 | 0xF;
    if ( (v27 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( v28 < 0x16 )
        v28 = 22;
    }
    else
    {
      v28 = 0x7FFFFFFFFFFFFFFFLL;
    }
    v29 = (void **)std::_Allocate<16,std::_Default_allocate_traits,0>(v28 + 1);
    Block_8[0] = v29;
  }
  si128.m128i_i64[0] = v25 + 1;
  si128.m128i_i64[1] = v28;
  memcpy_0(v29, v26, v25);
  *((_BYTE *)v29 + v25) = 32;
  *((_BYTE *)v29 + v27) = 0;
  v30 = v108;
  if ( v110 >= 0x10 )
    v30 = (void **)v108[0];
  v31 = std::string::append(Block_8, v30, v109);
  *(_OWORD *)v121 = *(_OWORD *)v31;
  v122 = *(_OWORD *)(v31 + 16);
  *(_QWORD *)(v31 + 16) = 0;
  *(_QWORD *)(v31 + 24) = 15;
  *(_BYTE *)v31 = 0;
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v32 = Block_8[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v32 = (void *)*((_QWORD *)Block_8[0] - 1);
      if ( (unsigned __int64)((char *)Block_8[0] - (char *)v32 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v32, si128.m128i_i64[1] + 40);
        __debugbreak();
      }
    }
    operator delete(v32);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(Block_8[0]) = 0;
  std::to_string(v105, v8);
  v33 = v106;
  v34 = 4 - v106;
  v35 = v105;
  if ( v107 >= 0x10 )
    v35 = (void **)v105[0];
  v36 = v105;
  if ( v107 >= 0x10 )
    v36 = (void **)v105[0];
  v37 = (char *)v35 - (char *)v36;
  if ( v106 < v37 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v38 = v107 - v106;
  _mm_lfence();
  if ( v34 > v38 )
  {
    std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(
      v105,
      4 - v106,
      48);
  }
  else
  {
    v106 = 4;
    v39 = v105;
    if ( v107 >= 0x10 )
      v39 = (void **)v105[0];
    v40 = (char *)v39 + v37;
    memmove_0(&v40[v34], v40, v33 - v37 + 1);
    memset_0(v40, 48, v34);
  }
  std::to_string(v102, v7);
  v41 = v103;
  v42 = 4 - v103;
  v43 = v102;
  if ( v104 >= 0x10 )
    v43 = (void **)v102[0];
  v44 = v102;
  if ( v104 >= 0x10 )
    v44 = (void **)v102[0];
  v45 = (char *)v43 - (char *)v44;
  if ( v103 < v45 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v46 = v104 - v103;
  _mm_lfence();
  if ( v42 > v46 )
  {
    std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(
      v102,
      v42,
      48);
  }
  else
  {
    v103 = 4;
    v47 = v102;
    if ( v104 >= 0x10 )
      v47 = (void **)v102[0];
    v48 = (char *)v47 + v45;
    memmove_0(&v48[v42], v48, v41 - v45 + 1);
    memset_0(v48, 48, v42);
  }
  v49 = v106;
  if ( v106 == 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  v50 = v105;
  if ( v107 >= 0x10 )
    v50 = (void **)v105[0];
  *(_OWORD *)v95 = 0;
  v96 = 0;
  v51 = v106 + 1;
  v52 = 15;
  v53 = v95;
  if ( v106 + 1 > 0xF )
  {
    v52 = v51 | 0xF;
    if ( (v51 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      if ( v52 < 0x16 )
        v52 = 22;
    }
    else
    {
      v52 = 0x7FFFFFFFFFFFFFFFLL;
    }
    v53 = (void **)std::_Allocate<16,std::_Default_allocate_traits,0>(v52 + 1);
    v95[0] = v53;
  }
  v96.m128i_i64[0] = v49 + 1;
  v96.m128i_i64[1] = v52;
  memcpy_0(v53, v50, v49);
  *((_BYTE *)v53 + v49) = 32;
  *((_BYTE *)v53 + v51) = 0;
  v54 = v102;
  if ( v104 >= 0x10 )
    v54 = (void **)v102[0];
  v55 = std::string::append(v95, v54, v103);
  *(_OWORD *)v123 = *(_OWORD *)v55;
  v124 = *(_OWORD *)(v55 + 16);
  *(_QWORD *)(v55 + 16) = 0;
  *(_QWORD *)(v55 + 24) = 15;
  *(_BYTE *)v55 = 0;
  if ( v96.m128i_i64[1] >= 0x10uLL )
  {
    v56 = v95[0];
    if ( (unsigned __int64)(v96.m128i_i64[1] + 1) >= 0x1000 )
    {
      v56 = (void *)*((_QWORD *)v95[0] - 1);
      if ( (unsigned __int64)((char *)v95[0] - (char *)v56 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v56, v96.m128i_i64[1] + 40);
        __debugbreak();
      }
    }
    operator delete(v56);
  }
  v96 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v95[0]) = 0;
  std::to_string(v112, (unsigned int)(int)v6);
  v57 = v113;
  v58 = 3 - v113;
  v59 = v112;
  if ( v114 >= 0x10 )
    v59 = (void **)v112[0];
  v60 = v112;
  if ( v114 >= 0x10 )
    v60 = (void **)v112[0];
  v61 = (char *)v59 - (char *)v60;
  if ( v113 < v61 )
    std::_String_val<std::_Simple_types<char>>::_Xran();
  v62 = v114 - v113;
  _mm_lfence();
  if ( v58 > v62 )
  {
    std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(
      v112,
      3 - v113,
      48);
  }
  else
  {
    v113 = 3;
    v63 = v112;
    if ( v114 >= 0x10 )
      v63 = (void **)v112[0];
    v64 = (char *)v63 + v61;
    memmove_0(&v64[v58], v64, v57 - v61 + 1);
    memset_0(v64, 48, v58);
  }
  ActivationFactory = -2147024882;
  v67 = (char *)operator new[](0x302u, (const struct std::nothrow_t *)&std::nothrow);
  v68 = *((_QWORD *)&v122 + 1);
  v69 = (void **)v121[0];
  v70 = *((_QWORD *)&v124 + 1);
  v71 = (void **)v123[0];
  if ( v67 )
  {
    v72 = (_OWORD *)xmmword_18012A020;
    if ( !(_QWORD)xmmword_18012A020 )
    {
      v72 = (_OWORD *)(*(__int64 (__fastcall **)(__int64 *))(qword_18012A010 + 32))(&qword_18012A010);
      *(_QWORD *)&xmmword_18012A020 = v72;
    }
    v73 = v67;
    v74 = 6;
    do
    {
      *(_OWORD *)v73 = *v72;
      *((_OWORD *)v73 + 1) = v72[1];
      *((_OWORD *)v73 + 2) = v72[2];
      *((_OWORD *)v73 + 3) = v72[3];
      *((_OWORD *)v73 + 4) = v72[4];
      *((_OWORD *)v73 + 5) = v72[5];
      *((_OWORD *)v73 + 6) = v72[6];
      v73 += 128;
      *((_OWORD *)v73 - 1) = v72[7];
      v72 += 8;
      --v74;
    }
    while ( v74 );
    *(_WORD *)v73 = *(_WORD *)v72;
    v75 = v121;
    if ( v68 >= 0x10 )
      v75 = v69;
    *((_QWORD *)v67 + 32) = *v75;
    *((_WORD *)v67 + 132) = *((_WORD *)v75 + 4);
    v67[266] = *((_BYTE *)v75 + 10);
    v76 = v112;
    if ( v114 >= 0x10 )
      v76 = (void **)v112[0];
    *(_WORD *)(v67 + 357) = *(_WORD *)v76;
    v67[359] = *((_BYTE *)v76 + 2);
    v77 = v123;
    if ( v70 >= 0x10 )
      v77 = v71;
    *(_QWORD *)(v67 + 365) = *v77;
    v67[373] = *((_BYTE *)v77 + 8);
    v120 = 0;
    v119 = 0;
    string = 0;
    sourceString_8 = 0;
    *(_OWORD *)length = 0;
    std::wstring::_Construct<1,wchar_t const *>(&sourceString_8, L"Windows.Security.Cryptography.CryptographicBuffer");
    string = 0;
    p_sourceString_8 = (const WCHAR *)&sourceString_8;
    if ( *(_QWORD *)&length[2] >= 8u )
      p_sourceString_8 = (const WCHAR *)sourceString_8;
    WindowsCreateString_0(p_sourceString_8, length[0], &string);
    if ( *(_QWORD *)&length[2] >= 8u )
    {
      v79 = (void *)sourceString_8;
      if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
      {
        v79 = *(void **)(sourceString_8 - 8);
        if ( (unsigned __int64)(sourceString_8 - (_QWORD)v79 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v79, 2LL * *(_QWORD *)&length[2] + 41);
          __debugbreak();
        }
      }
      operator delete(v79);
    }
    *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(sourceString_8) = 0;
    ActivationFactory = RoGetActivationFactory(string, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v119);
    if ( !ActivationFactory )
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, char *, __int64 *))(*(_QWORD *)v119 + 72LL))(
                            v119,
                            770,
                            v67,
                            &v120);
    v80 = WindowsDeleteString_0(string);
    v81 = string;
    if ( !v80 )
      v81 = 0;
    string = v81;
    if ( v119 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
    if ( !ActivationFactory )
    {
      v111 = 0;
      v82 = v99;
      ActivationFactory = (*(__int64 (__fastcall **)(struct ABI::Windows::Storage::Streams::IRandomAccessStream *, _QWORD, __int64 *))(*(_QWORD *)v99 + 72LL))(
                            v99,
                            0,
                            &v111);
      v83 = v111;
      if ( !ActivationFactory && v111 )
      {
        v101 = 0;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v111 + 48LL))(
                              v111,
                              v120,
                              &v101);
        v84 = v101;
        if ( !ActivationFactory && v101 )
        {
          while ( (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v84 + 80LL))(v84, v118) == -2147483634 )
            v84 = v101;
          (*(void (__fastcall **)(struct ABI::Windows::Storage::Streams::IRandomAccessStream *, _QWORD))(*(_QWORD *)v82 + 88LL))(
            v82,
            0);
          v84 = v101;
        }
        if ( v84 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
        v83 = v111;
      }
      if ( v83 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    }
    operator delete(v67);
    v66 = v120;
    if ( v120 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
  }
  if ( v114 >= 0x10 )
  {
    v85 = v112[0];
    if ( v114 + 1 >= 0x1000 )
    {
      v85 = (void *)*((_QWORD *)v112[0] - 1);
      if ( (unsigned __int64)((char *)v112[0] - (char *)v85 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v85, v114 + 40);
        __debugbreak();
      }
    }
    operator delete(v85);
  }
  v113 = 0;
  v114 = 15;
  LOBYTE(v112[0]) = 0;
  if ( v70 >= 0x10 )
  {
    v86 = v71;
    if ( v70 + 1 >= 0x1000 )
    {
      v71 = (void **)*(v71 - 1);
      if ( (unsigned __int64)((char *)v86 - (char *)v71 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v66, v70 + 40);
        __debugbreak();
      }
    }
    operator delete(v71);
  }
  if ( v104 >= 0x10 )
  {
    v87 = v102[0];
    if ( v104 + 1 >= 0x1000 )
    {
      v87 = (void *)*((_QWORD *)v102[0] - 1);
      if ( (unsigned __int64)((char *)v102[0] - (char *)v87 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v87, v104 + 40);
        __debugbreak();
      }
    }
    operator delete(v87);
  }
  v103 = 0;
  v104 = 15;
  LOBYTE(v102[0]) = 0;
  if ( v107 >= 0x10 )
  {
    v88 = v105[0];
    if ( v107 + 1 >= 0x1000 )
    {
      v88 = (void *)*((_QWORD *)v105[0] - 1);
      if ( (unsigned __int64)((char *)v105[0] - (char *)v88 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v88, v107 + 40);
        __debugbreak();
      }
    }
    operator delete(v88);
  }
  v106 = 0;
  v107 = 15;
  LOBYTE(v105[0]) = 0;
  if ( v68 >= 0x10 )
  {
    v89 = v69;
    if ( v68 + 1 >= 0x1000 )
    {
      v69 = (void **)*(v69 - 1);
      if ( (unsigned __int64)((char *)v89 - (char *)v69 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v66, v68 + 40);
        __debugbreak();
      }
    }
    operator delete(v69);
  }
  if ( v110 >= 0x10 )
  {
    v90 = v108[0];
    if ( v110 + 1 >= 0x1000 )
    {
      v90 = (void *)*((_QWORD *)v108[0] - 1);
      if ( (unsigned __int64)((char *)v108[0] - (char *)v90 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v90, v110 + 40);
        __debugbreak();
      }
    }
    operator delete(v90);
  }
  v109 = 0;
  v110 = 15;
  LOBYTE(v108[0]) = 0;
  if ( v117 >= 0x10 )
  {
    v91 = Src[0];
    if ( v117 + 1 >= 0x1000 )
    {
      v91 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v91 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v91, v117 + 40);
        __debugbreak();
      }
    }
    operator delete(v91);
  }
  return ActivationFactory;
}

```

## disassembly

```asm
0x180014a60  mov     rax, rsp
0x180014a63  mov     [rax+8], rbx
0x180014a67  mov     [rax+18h], rsi
0x180014a6b  mov     [rax+20h], rdi
0x180014a6f  push    rbp
0x180014a70  push    r12
0x180014a72  push    r13
0x180014a74  push    r14
0x180014a76  push    r15
0x180014a78  lea     rbp, [rax-0E8h]
0x180014a7f  sub     rsp, 1C0h
0x180014a86  movaps  xmmword ptr [rax-38h], xmm6
0x180014a8a  mov     rax, cs:__security_cookie
0x180014a91  xor     rax, rsp
0x180014a94  mov     [rbp+0E0h+var_38], rax
0x180014a9b  mov     [rbp+0E0h+var_150], rdx
0x180014a9f  xor     r10d, r10d
0x180014aa2  movd    xmm0, r8d
0x180014aa7  cvtdq2ps xmm0, xmm0
0x180014aaa  divss   xmm0, cs:__real@46c67000
0x180014ab2  mulss   xmm0, cs:__real@42900000
0x180014aba  cvttss2si r8d, xmm0
0x180014abf  movd    xmm0, r9d
0x180014ac4  cvtdq2ps xmm0, xmm0
0x180014ac7  divss   xmm0, cs:__real@46c67000
0x180014acf  mulss   xmm0, cs:__real@42900000
0x180014ad7  cvttss2si r14d, xmm0
0x180014adc  movss   xmm6, cs:__real@41800000
0x180014ae4  cmp     r8d, 0C8h
0x180014aeb  jge     short loc_180014AF5
0x180014aed  movss   xmm6, cs:__real@41200000
0x180014af5  cmp     r8d, 7Dh ; '}'
0x180014af9  jge     short loc_180014B03
0x180014afb  movss   xmm6, cs:__real@40c00000
0x180014b03  movaps  xmm0, xmm6
0x180014b06  mulss   xmm0, cs:__real@41480000
0x180014b0e  cvttss2si ecx, xmm0
0x180014b12  mov     eax, r14d
0x180014b15  cdq
0x180014b16  sub     eax, edx
0x180014b18  sar     eax, 1
0x180014b1a  mov     r13d, eax
0x180014b1d  mov     eax, ecx
0x180014b1f  cdq
0x180014b20  sub     eax, edx
0x180014b22  sar     eax, 1
0x180014b24  mov     ecx, eax
0x180014b26  mov     eax, r8d
0x180014b29  cdq
0x180014b2a  sub     eax, edx
0x180014b2c  sar     eax, 1
0x180014b2e  sub     eax, ecx
0x180014b30  mov     r12d, r10d
0x180014b33  cmovns  r12d, eax
0x180014b37  mov     edx, r8d
0x180014b3a  lea     rcx, [rbp+0E0h+Src]
0x180014b3e  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x180014b43  nop
0x180014b44  mov     edi, 5
0x180014b49  mov     esi, edi
0x180014b4b  mov     r8, [rbp+0E0h+Size]
0x180014b4f  sub     rsi, r8
0x180014b52  lea     r9, [rbp+0E0h+Src]
0x180014b56  mov     rdx, [rbp+0E0h+var_98]
0x180014b5a  cmp     rdx, 10h
0x180014b5e  cmovnb  r9, [rbp+0E0h+Src]
0x180014b63  lea     rax, [rbp+0E0h+Src]
0x180014b67  cmovnb  rax, [rbp+0E0h+Src]
0x180014b6c  sub     r9, rax
0x180014b6f  cmp     r8, r9
0x180014b72  jb      loc_1800155FE
0x180014b78  sub     rdx, r8
0x180014b7b  lfence
0x180014b7e  cmp     rsi, rdx
0x180014b81  ja      short loc_180014BBA
0x180014b83  add     [rbp+0E0h+Size], rsi
0x180014b87  lea     rbx, [rbp+0E0h+Src]
0x180014b8b  cmp     [rbp+0E0h+var_98], 10h
0x180014b90  cmovnb  rbx, [rbp+0E0h+Src]
0x180014b95  add     rbx, r9
0x180014b98  lea     rcx, [rbx+rsi]; void *
0x180014b9c  sub     r8, r9
0x180014b9f  inc     r8; Size
0x180014ba2  mov     rdx, rbx; Src
0x180014ba5  call    memmove_0
0x180014baa  mov     r8, rsi; Size
0x180014bad  lea     edx, [rdi+2Bh]; Val
0x180014bb0  mov     rcx, rbx; void *
0x180014bb3  call    memset_0
0x180014bb8  jmp     short loc_180014BD3
0x180014bba  mov     byte ptr [rsp+1E0h+Block], 30h ; '0'; char
0x180014bbf  mov     [rsp+1E0h+var_1C0], rsi; Size
0x180014bc4  xor     r8d, r8d
0x180014bc7  mov     rdx, rsi
0x180014bca  lea     rcx, [rbp+0E0h+Src]; Src
0x180014bce  call    ??$_Reallocate_grow_by@V_lambda_b986da8d428e4af07c64af60eec09b61_@@_K_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_b986da8d428e4af07c64af60eec09b61_@@_K2D@Z; std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(unsigned __int64,_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char)
0x180014bd3  mov     edx, r14d
0x180014bd6  lea     rcx, [rbp+0E0h+var_F8]
0x180014bda  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x180014bdf  nop
0x180014be0  mov     r8, [rbp+0E0h+var_E8]
0x180014be4  sub     rdi, r8
0x180014be7  lea     r9, [rbp+0E0h+var_F8]
0x180014beb  mov     rdx, [rbp+0E0h+var_E0]
0x180014bef  cmp     rdx, 10h
0x180014bf3  cmovnb  r9, [rbp+0E0h+var_F8]
0x180014bf8  lea     rax, [rbp+0E0h+var_F8]
0x180014bfc  cmovnb  rax, [rbp+0E0h+var_F8]
0x180014c01  sub     r9, rax
0x180014c04  cmp     r8, r9
0x180014c07  jb      loc_180015604
0x180014c0d  sub     rdx, r8
0x180014c10  lfence
0x180014c13  cmp     rdi, rdx
0x180014c16  ja      short loc_180014C51
0x180014c18  add     [rbp+0E0h+var_E8], rdi
0x180014c1c  lea     rbx, [rbp+0E0h+var_F8]
0x180014c20  cmp     [rbp+0E0h+var_E0], 10h
0x180014c25  cmovnb  rbx, [rbp+0E0h+var_F8]
0x180014c2a  add     rbx, r9
0x180014c2d  lea     rcx, [rbx+rdi]; void *
0x180014c31  sub     r8, r9
0x180014c34  inc     r8; Size
0x180014c37  mov     rdx, rbx; Src
0x180014c3a  call    memmove_0
0x180014c3f  mov     r8, rdi; Size
0x180014c42  mov     edx, 30h ; '0'; Val
0x180014c47  mov     rcx, rbx; void *
0x180014c4a  call    memset_0
0x180014c4f  jmp     short loc_180014C6A
0x180014c51  mov     byte ptr [rsp+1E0h+Block], 30h ; '0'; char
0x180014c56  mov     [rsp+1E0h+var_1C0], rdi; Size
0x180014c5b  xor     r8d, r8d
0x180014c5e  mov     rdx, rdi
0x180014c61  lea     rcx, [rbp+0E0h+var_F8]; Src
0x180014c65  call    ??$_Reallocate_grow_by@V_lambda_b986da8d428e4af07c64af60eec09b61_@@_K_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_b986da8d428e4af07c64af60eec09b61_@@_K2D@Z; std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(unsigned __int64,_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char)
0x180014c6a  mov     rsi, [rbp+0E0h+Size]
0x180014c6e  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180014c78  mov     rax, rcx
0x180014c7b  sub     rax, rsi
0x180014c7e  cmp     rax, 1
0x180014c82  jb      loc_18001560A
0x180014c88  lea     r15, [rbp+0E0h+Src]
0x180014c8c  cmp     [rbp+0E0h+var_98], 10h
0x180014c91  cmovnb  r15, [rbp+0E0h+Src]
0x180014c96  xorps   xmm0, xmm0
0x180014c99  movups  xmmword ptr [rsp+1E0h+Block+8], xmm0
0x180014c9e  xorps   xmm1, xmm1
0x180014ca1  movdqu  [rsp+1E0h+var_1A8+8], xmm1
0x180014ca7  lea     r14, [rsi+1]
0x180014cab  mov     ebx, 0Fh
0x180014cb0  lea     rdi, [rsp+1E0h+Block+8]
0x180014cb5  lea     eax, [rbx+7]
0x180014cb8  cmp     r14, rbx
0x180014cbb  jbe     short loc_180014CE6
0x180014cbd  mov     rbx, r14
0x180014cc0  or      rbx, 0Fh
0x180014cc4  cmp     rbx, rcx
0x180014cc7  jbe     short loc_180014CCE
0x180014cc9  mov     rbx, rcx
0x180014ccc  jmp     short loc_180014CD5
0x180014cce  cmp     rbx, rax
0x180014cd1  cmovb   rbx, rax
0x180014cd5  lea     rcx, [rbx+1]
0x180014cd9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@$0A@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits,0>(unsigned __int64)
0x180014cde  mov     rdi, rax
0x180014ce1  mov     [rsp+1E0h+Block+8], rax
0x180014ce6  mov     qword ptr [rsp+1E0h+var_1A8+8], r14
0x180014ceb  mov     [rsp+1E0h+var_198], rbx
0x180014cf0  mov     r8, rsi; Size
0x180014cf3  mov     rdx, r15; Src
0x180014cf6  mov     rcx, rdi; void *
0x180014cf9  call    memcpy_0
0x180014cfe  mov     byte ptr [rdi+rsi], 20h ; ' '
0x180014d02  mov     byte ptr [rdi+r14], 0
0x180014d07  lea     rdx, [rbp+0E0h+var_F8]
0x180014d0b  cmp     [rbp+0E0h+var_E0], 10h
0x180014d10  cmovnb  rdx, [rbp+0E0h+var_F8]; void *
0x180014d15  mov     r8, [rbp+0E0h+var_E8]; Size
0x180014d19  lea     rcx, [rsp+1E0h+Block+8]; Src
0x180014d1e  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x180014d23  movups  xmm0, xmmword ptr [rax]
0x180014d26  movups  xmmword ptr [rbp+0E0h+var_78], xmm0
0x180014d2a  movups  xmm1, xmmword ptr [rax+10h]
0x180014d2e  movups  [rbp+0E0h+var_68], xmm1
0x180014d32  xor     edx, edx
0x180014d34  mov     [rax+10h], rdx
0x180014d38  mov     qword ptr [rax+18h], 0Fh
0x180014d40  mov     [rax], dl
0x180014d42  mov     rdx, [rsp+1E0h+var_198]
0x180014d47  cmp     rdx, 10h
0x180014d4b  jb      short loc_180014D82
0x180014d4d  inc     rdx
0x180014d50  mov     rcx, [rsp+1E0h+Block+8]; Block
0x180014d55  mov     rax, rcx
0x180014d58  cmp     rdx, 1000h
0x180014d5f  jb      short loc_180014D7D
0x180014d61  add     rdx, 27h ; '''
0x180014d65  mov     rcx, [rcx-8]
0x180014d69  sub     rax, rcx
0x180014d6c  add     rax, 0FFFFFFFFFFFFFFF8h
0x180014d70  cmp     rax, 1Fh
0x180014d74  jbe     short loc_180014D7D
0x180014d76  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180014d7c  int     3; Trap to Debugger
0x180014d7d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014d82  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180014d8a  movdqu  [rsp+1E0h+var_1A8+8], xmm0
0x180014d90  mov     byte ptr [rsp+1E0h+Block+8], 0
0x180014d95  mov     edx, r12d
0x180014d98  lea     rcx, [rbp+0E0h+var_118]
0x180014d9c  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x180014da1  nop
0x180014da2  mov     edi, 4
0x180014da7  mov     esi, edi
0x180014da9  mov     r8, [rbp+0E0h+var_108]
0x180014dad  sub     rsi, r8
0x180014db0  lea     r9, [rbp+0E0h+var_118]
0x180014db4  mov     rdx, [rbp+0E0h+var_100]
0x180014db8  cmp     rdx, 10h
0x180014dbc  cmovnb  r9, [rbp+0E0h+var_118]
0x180014dc1  lea     rax, [rbp+0E0h+var_118]
0x180014dc5  cmovnb  rax, [rbp+0E0h+var_118]
0x180014dca  sub     r9, rax
0x180014dcd  cmp     r8, r9
0x180014dd0  jb      loc_180015610
0x180014dd6  sub     rdx, r8
0x180014dd9  lfence
0x180014ddc  cmp     rsi, rdx
0x180014ddf  ja      short loc_180014E18
0x180014de1  add     [rbp+0E0h+var_108], rsi
0x180014de5  lea     rbx, [rbp+0E0h+var_118]
0x180014de9  cmp     [rbp+0E0h+var_100], 10h
0x180014dee  cmovnb  rbx, [rbp+0E0h+var_118]
0x180014df3  add     rbx, r9
0x180014df6  lea     rcx, [rbx+rsi]; void *
0x180014dfa  sub     r8, r9
0x180014dfd  inc     r8; Size
0x180014e00  mov     rdx, rbx; Src
0x180014e03  call    memmove_0
0x180014e08  mov     r8, rsi; Size
0x180014e0b  lea     edx, [rdi+2Ch]; Val
0x180014e0e  mov     rcx, rbx; void *
0x180014e11  call    memset_0
0x180014e16  jmp     short loc_180014E31
0x180014e18  mov     byte ptr [rsp+1E0h+Block], 30h ; '0'; char
0x180014e1d  mov     [rsp+1E0h+var_1C0], rsi; Size
0x180014e22  xor     r8d, r8d
0x180014e25  mov     rdx, rsi
0x180014e28  lea     rcx, [rbp+0E0h+var_118]; Src
0x180014e2c  call    ??$_Reallocate_grow_by@V_lambda_b986da8d428e4af07c64af60eec09b61_@@_K_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_b986da8d428e4af07c64af60eec09b61_@@_K2D@Z; std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(unsigned __int64,_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char)
0x180014e31  mov     edx, r13d
0x180014e34  lea     rcx, [rbp+0E0h+var_138]
0x180014e38  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::to_string(int)
0x180014e3d  nop
0x180014e3e  mov     r8, [rbp+0E0h+var_128]
0x180014e42  sub     rdi, r8
0x180014e45  lea     r9, [rbp+0E0h+var_138]
0x180014e49  mov     rdx, [rbp+0E0h+var_120]
0x180014e4d  cmp     rdx, 10h
0x180014e51  cmovnb  r9, [rbp+0E0h+var_138]
0x180014e56  lea     rax, [rbp+0E0h+var_138]
0x180014e5a  cmovnb  rax, [rbp+0E0h+var_138]
0x180014e5f  sub     r9, rax
0x180014e62  cmp     r8, r9
0x180014e65  jb      loc_180015616
0x180014e6b  sub     rdx, r8
0x180014e6e  lfence
0x180014e71  cmp     rdi, rdx
0x180014e74  ja      short loc_180014EAF
0x180014e76  add     [rbp+0E0h+var_128], rdi
0x180014e7a  lea     rbx, [rbp+0E0h+var_138]
0x180014e7e  cmp     [rbp+0E0h+var_120], 10h
0x180014e83  cmovnb  rbx, [rbp+0E0h+var_138]
0x180014e88  add     rbx, r9
0x180014e8b  lea     rcx, [rbx+rdi]; void *
0x180014e8f  sub     r8, r9
0x180014e92  inc     r8; Size
0x180014e95  mov     rdx, rbx; Src
0x180014e98  call    memmove_0
0x180014e9d  mov     r8, rdi; Size
0x180014ea0  mov     edx, 30h ; '0'; Val
0x180014ea5  mov     rcx, rbx; void *
0x180014ea8  call    memset_0
0x180014ead  jmp     short loc_180014EC8
0x180014eaf  mov     byte ptr [rsp+1E0h+Block], 30h ; '0'; char
0x180014eb4  mov     [rsp+1E0h+var_1C0], rdi; Size
0x180014eb9  xor     r8d, r8d
0x180014ebc  mov     rdx, rdi
0x180014ebf  lea     rcx, [rbp+0E0h+var_138]; Src
0x180014ec3  call    ??$_Reallocate_grow_by@V_lambda_b986da8d428e4af07c64af60eec09b61_@@_K_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_b986da8d428e4af07c64af60eec09b61_@@_K2D@Z; std::string::_Reallocate_grow_by<_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char>(unsigned __int64,_lambda_b986da8d428e4af07c64af60eec09b61_,unsigned __int64,unsigned __int64,char)
0x180014ec8  mov     rsi, [rbp+0E0h+var_108]
0x180014ecc  mov     rcx, 7FFFFFFFFFFFFFFFh
0x180014ed6  mov     rax, rcx
0x180014ed9  sub     rax, rsi
0x180014edc  cmp     rax, 1
0x180014ee0  jb      loc_18001561C
0x180014ee6  lea     r15, [rbp+0E0h+var_118]
0x180014eea  cmp     [rbp+0E0h+var_100], 10h
0x180014eef  cmovnb  r15, [rbp+0E0h+var_118]
  ... truncated ...
```
