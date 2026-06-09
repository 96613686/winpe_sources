# Uev::CustomActionUri::CustomActionUri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x140089244`
- end: `0x140089d2e`
- name: `??0CustomActionUri@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `2794`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400628d0`

## callees

- `0x140003890`
- `0x140003e50`
- `0x140003e74`
- `0x140003f88`
- `0x140004ab4`
- `0x14000adb4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000c8d4`
- `0x14000d7b4`
- `0x14000ec94`
- `0x14000eccc`
- `0x14000f2f0`
- `0x14000f358`
- `0x1400133e4`
- `0x140013dc4`
- `0x1400230e8`
- `0x140026ef0`
- `0x140027544`
- `0x140038614`
- `0x14005e444`
- `0x1400890e4`
- `0x14008921c`
- `0x140089244`
- `0x140089d34`
- `0x14009b010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140089481`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400894fd`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x140089481`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x1400894fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400895c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400895fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400895c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400895fe`

## string_xrefs

- `0x140089a78`: `Invalid custom action URI format (4): %1%`
- `0x140089bb9`: `Invalid custom action URI format (3): %1%`
- `0x140089b4e`: `Invalid custom action URI format (2): %1%`
- `0x140089ae3`: `Invalid custom action URI format (1): %1%`
- `0x140089caa`: `Invalid custom action URI format (Missing value name: %1% in URI: %2%`
- `0x140089c24`: `Invalid custom action URI format (duplicate parameter): %1% in URI: %2%`
- `0x140089a0b`: `Invalid custom action URI format (5): %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::CustomActionUri::CustomActionUri(__int64 a1, __int64 a2)
{
  _QWORD *v3; // r14
  __int128 *v4; // rsi
  __int64 v5; // r15
  _QWORD *v6; // r13
  _QWORD *v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _WORD *v10; // rcx
  _QWORD *v11; // r15
  char *v12; // r12
  char *v13; // rsi
  void ***v14; // rax
  __int64 v15; // r15
  unsigned __int64 v16; // rax
  struct std::locale::_Locimp *v17; // rdi
  void (__fastcall ***v18)(_QWORD, __int64); // rax
  struct std::locale::_Locimp *v19; // rdi
  void (__fastcall ***v20)(_QWORD, __int64); // rax
  void ***v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  unsigned __int64 v24; // r9
  unsigned __int64 v25; // rcx
  _QWORD *v26; // r15
  __int64 v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rax
  char *v30; // rdi
  __int64 end_2; // rax
  unsigned __int64 v32; // r8
  __int128 *v33; // rdi
  __int64 v34; // rdi
  __int64 v35; // r14
  __int64 v36; // rsi
  __int64 v37; // rcx
  void ***v38; // rax
  __int64 v39; // rdi
  __int64 v40; // r15
  _QWORD *v41; // r12
  __int64 v42; // r14
  void ***v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rbx
  __int64 v46; // rdx
  __int64 v47; // rbx
  void *v48; // rcx
  void *v49; // rcx
  void *v50; // rcx
  void *v51; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // r8
  __int64 v70; // rax
  __int64 v71; // r9
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // r9
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  void *v82[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v83; // [rsp+30h] [rbp-D0h]
  __int64 v84; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v85; // [rsp+40h] [rbp-C0h]
  _QWORD *v86; // [rsp+48h] [rbp-B8h]
  __int64 v87; // [rsp+50h] [rbp-B0h]
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v89; // [rsp+68h] [rbp-98h]
  __int64 v90; // [rsp+70h] [rbp-90h]
  __int64 v91; // [rsp+78h] [rbp-88h]
  void *v92[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v93; // [rsp+90h] [rbp-70h]
  __int64 v94; // [rsp+98h] [rbp-68h]
  unsigned __int64 v95; // [rsp+A0h] [rbp-60h]
  _QWORD *v96; // [rsp+A8h] [rbp-58h] BYREF
  struct std::locale::_Locimp *v97; // [rsp+B0h] [rbp-50h]
  __int128 *v98; // [rsp+B8h] [rbp-48h]
  __int64 v99; // [rsp+C0h] [rbp-40h]
  __int64 v100; // [rsp+D0h] [rbp-30h]
  __int128 v101; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-10h]
  __int64 v103; // [rsp+F8h] [rbp-8h]
  _BYTE pExceptionObject[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v105; // [rsp+110h] [rbp+10h]
  _BYTE v106[32]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v107; // [rsp+140h] [rbp+40h] BYREF
  __int128 v108; // [rsp+150h] [rbp+50h]
  void *v109[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v110; // [rsp+170h] [rbp+70h]
  __int64 v111; // [rsp+178h] [rbp+78h]
  __int64 v112; // [rsp+180h] [rbp+80h]
  __int128 v113; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v114; // [rsp+1B0h] [rbp+B0h]
  __int64 v115; // [rsp+1B8h] [rbp+B8h]
  __int128 v116; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v117; // [rsp+1D0h] [rbp+D0h]
  __int64 v118; // [rsp+1D8h] [rbp+D8h]
  _BYTE v119[272]; // [rsp+1E0h] [rbp+E0h] BYREF

  v87 = a2;
  v99 = a1;
  v100 = a1;
  *(_QWORD *)a1 = &Uev::CustomActionUri::`vftable';
  v3 = (_QWORD *)(a1 + 8);
  v96 = (_QWORD *)(a1 + 8);
  std::wstring::wstring(a1 + 8, a2);
  v4 = (__int128 *)(a1 + 40);
  v98 = (__int128 *)(a1 + 40);
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_WORD *)(a1 + 40) = 0;
  v5 = a1 + 72;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v6 = (_QWORD *)(a1 + 104);
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  v7 = (_QWORD *)(a1 + 136);
  v86 = (_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  v8 = operator new(0x60u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *(_QWORD *)(a1 + 136) = v8;
  v9 = (_QWORD *)(a1 + 152);
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  v101 = 0;
  v102 = 0;
  v103 = 7;
  LOWORD(v101) = 0;
  v116 = 0;
  v117 = 0;
  v118 = 7;
  LOWORD(v116) = 0;
  v113 = 0;
  v114 = 0;
  v115 = 7;
  LOWORD(v113) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  if ( *(_QWORD *)(v5 + 24) <= 7u )
    v10 = (_WORD *)v5;
  else
    v10 = *(_WORD **)v5;
  *v10 = 0;
  v11 = (_QWORD *)*v7;
  v12 = *(char **)(*v7 + 8LL);
  if ( !v12[25] )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v86,
        v86,
        *((_QWORD *)v12 + 2));
      v13 = v12;
      v12 = *(char **)v12;
      std::wstring::_Tidy_deallocate(v13 + 64);
      std::wstring::_Tidy_deallocate(v13 + 32);
      operator delete(v13);
    }
    while ( !v12[25] );
    v3 = v96;
    v4 = v98;
    v7 = v86;
  }
  v11[1] = v11;
  *v11 = v11;
  v11[2] = v11;
  v7[1] = 0;
  *(_OWORD *)v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v14 = (void ***)operator new(0x10u);
  v14[1] = 0;
  v92[0] = v14;
  *v14 = v92;
  v15 = v87;
  Uev::Common::Split(v87, 63, v92);
  v16 = v95;
  if ( v95 > 2 )
  {
    v56 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
            v119,
            L"Invalid custom action URI format (4): %1%");
    v57 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
            v56,
            v87);
    v58 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v57);
    std::wstring::operator=(&v101, v58);
    boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
    Uev::ParseException::ParseException(v109, &v101);
    throw (Uev::ParseException *)v109;
  }
  if ( v95 )
  {
    std::wstring::operator=(&v116, *((_QWORD *)v92[1] + (v94 & (v93 - 1))));
    v17 = std::locale::_Init(1);
    v97 = v17;
    boost::algorithm::trim<std::wstring>(&v116, &v96);
    if ( v17 )
    {
      v18 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v18 )
        (**v18)(v18, 1);
    }
    v16 = v95;
  }
  if ( v16 == 2 )
  {
    std::wstring::operator=(&v113, *((_QWORD *)v92[1] + ((v93 - 1) & (v94 + 1))));
    v19 = std::locale::_Init(1);
    v97 = v19;
    boost::algorithm::trim<std::wstring>(&v113, &v96);
    if ( v19 )
    {
      v20 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v20 )
        (**v20)(v20, 1);
    }
  }
  *(_OWORD *)v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v21 = (void ***)operator new(0x10u);
  v21[1] = 0;
  v82[0] = v21;
  *v21 = v82;
  Uev::Common::Split(&v116, 47, v82);
  if ( v85 < 3 )
  {
    v59 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
            v119,
            L"Invalid custom action URI format (1): %1%");
    v60 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
            v59,
            v15);
    v61 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v60);
    std::wstring::operator=(&v101, v61);
    boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
    Uev::ParseException::ParseException(v109, &v101);
    throw (Uev::ParseException *)v109;
  }
  v22 = (_QWORD *)*((_QWORD *)v82[1] + (v84 & (v83 - 1)));
  if ( v22[3] > 7u )
    v22 = (_QWORD *)*v22;
  if ( (unsigned int)_o__wcsicmp(v22, L"custom:") )
  {
    v62 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
            v119,
            L"Invalid custom action URI format (2): %1%");
    v63 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
            v62,
            v15);
    v64 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v63);
    std::wstring::operator=(&v101, v64);
    boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
    Uev::ParseException::ParseException(v109, &v101);
    throw (Uev::ParseException *)v109;
  }
  v23 = (_QWORD *)*((_QWORD *)v82[1] + ((v83 - 1) & (v84 + 1)));
  if ( v23[3] > 7u )
    v23 = (_QWORD *)*v23;
  if ( (unsigned int)_o__wcsicmp(v23, &Data) )
  {
    v65 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
            v119,
            L"Invalid custom action URI format (3): %1%");
    v66 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
            v65,
            v15);
    v67 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v66);
    std::wstring::operator=(&v101, v67);
    boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
    Uev::ParseException::ParseException(v109, &v101);
    throw (Uev::ParseException *)v109;
  }
  std::wstring::operator=(v99 + 72, *((_QWORD *)v82[1] + ((v83 - 1) & (v84 + 2))));
  if ( v85 <= 3 )
  {
    std::wstring::operator=(v4, v3);
  }
  else
  {
    std::wstring::operator=(v6, *((_QWORD *)v82[1] + ((v83 - 1) & (v84 - 1 + v85))));
    v24 = v6[2];
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v25 = v3[2];
    if ( v3[3] <= 7u )
      v26 = v3;
    else
      v26 = (_QWORD *)*v3;
    v27 = -1;
    if ( v24 )
    {
      if ( v24 <= v25 )
      {
        v28 = v25 - v24;
        v29 = -1;
        if ( v28 != -1 )
          v29 = v28;
        v30 = (char *)v26 + 2 * v24 + 2 * v29;
        end_2 = _std_find_end_2(v26, v30, v6);
        if ( (char *)end_2 != v30 )
          v27 = (end_2 - (__int64)v26) >> 1;
      }
    }
    else if ( v25 != -1 )
    {
      v27 = v3[2];
    }
    v107 = 0;
    v108 = 0u;
    v32 = v3[2];
    if ( v32 >= v27 - 1 )
      v32 = v27 - 1;
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    std::wstring::_Construct<1,wchar_t *>(&v107, v3, v32);
    v33 = v98;
    if ( v98 != &v107 )
    {
      std::wstring::_Tidy_deallocate(v98);
      *v33 = v107;
      v33[1] = v108;
      *(_QWORD *)&v108 = 0;
      *((_QWORD *)&v108 + 1) = 7;
      LOWORD(v107) = 0;
    }
    std::wstring::_Tidy_deallocate(&v107);
  }
  v34 = v84;
  v35 = v84 + v85;
  if ( v82[0] )
    v36 = *(_QWORD *)v82[0];
  else
    v36 = 0;
  while ( v34 != v35 )
  {
    v37 = v34 & (*(_QWORD *)(v36 + 16) - 1LL);
    if ( v9[1] == v9[2] )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(
        v9,
        v9[1],
        *(_QWORD *)(*(_QWORD *)(v36 + 8) + 8 * v37));
    }
    else
    {
      std::wstring::wstring(v9[1], *(_QWORD *)(*(_QWORD *)(v36 + 8) + 8 * v37));
      v9[1] += 32LL;
    }
    ++v34;
  }
  if ( v114 )
  {
    *(_OWORD *)v109 = 0;
    v110 = 0;
    v111 = 0;
    v112 = 0;
    v38 = (void ***)operator new(0x10u);
    v38[1] = 0;
    v109[0] = v38;
    *v38 = v109;
    Uev::Common::Split(&v113, 38, v109);
    v39 = v111;
    v40 = v111 + v112;
    v41 = v86;
    while ( v39 != v40 )
    {
      v42 = *((_QWORD *)v109[1] + (v39 & (v110 - 1)));
      *(_OWORD *)Block = 0;
      v89 = 0;
      v90 = 0;
      v91 = 0;
      v43 = (void ***)operator new(0x10u);
      v43[1] = 0;
      Block[0] = v43;
      *v43 = Block;
      Uev::Common::Split(v42, 61, Block);
      if ( v91 != 2 )
      {
        v53 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
                v119,
                L"Invalid custom action URI format (5): %1%");
        v54 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
                v53,
                v87);
        v55 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v54);
        std::wstring::operator=(&v101, v55);
        boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
        Uev::ParseException::ParseException(pExceptionObject, &v101);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v44 = *((_QWORD *)Block[1] + (v90 & (v89 - 1)));
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        v41,
        pExceptionObject,
        v44);
      v45 = v105;
      if ( !*(_BYTE *)(v105 + 25) && !(unsigned __int8)std::operator<<wchar_t>(v44, v105 + 32) && v45 != *v41 )
      {
        v68 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
                v119,
                L"Invalid custom action URI format (duplicate parameter): %1% in URI: %2%");
        v70 = std::deque<std::wstring>::operator[](Block, 0, v69, v68);
        v72 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
                v71,
                v70);
        v73 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
                v72,
                v87);
        v74 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v73);
        std::wstring::operator=(&v101, v74);
        boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
        Uev::ParseException::ParseException(pExceptionObject, &v101);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v46 = *((_QWORD *)Block[1] + ((v89 - 1) & v90));
      if ( !*(_QWORD *)(v46 + 16) )
      {
        v75 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
                v119,
                L"Invalid custom action URI format (Missing value name: %1% in URI: %2%");
        v77 = std::deque<std::wstring>::operator[](Block, 0, v76, v75);
        v79 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
                v78,
                v77);
        v80 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<std::wstring>(
                v79,
                v42);
        v81 = boost::str<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(pExceptionObject, v80);
        std::wstring::operator=(&v101, v81);
        boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v119);
        Uev::ParseException::ParseException(pExceptionObject, &v101);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v47 = *((_QWORD *)Block[1] + ((v89 - 1) & (v90 + 1)));
      std::wstring::wstring((__int64)pExceptionObject, v46);
      std::wstring::wstring((__int64)v106, v47);
      std::map<std::wstring,std::wstring>::insert<std::pair<std::wstring,std::wstring>,0>(v41, &v96, pExceptionObject);
      std::wstring::_Tidy_deallocate(v106);
      std::wstring::_Tidy_deallocate(pExceptionObject);
      std::deque<std::wstring>::_Tidy(Block);
      v48 = Block[0];
      Block[0] = 0;
      operator delete(v48);
      ++v39;
    }
    std::deque<std::wstring>::_Tidy(v109);
    v49 = v109[0];
    v109[0] = 0;
    operator delete(v49);
  }
  std::deque<std::wstring>::_Tidy(v82);
  v50 = v82[0];
  v82[0] = 0;
  operator delete(v50);
  std::deque<std::wstring>::_Tidy(v92);
  v51 = v92[0];
  v92[0] = 0;
  operator delete(v51);
  std::wstring::_Tidy_deallocate(&v113);
  std::wstring::_Tidy_deallocate(&v116);
  std::wstring::_Tidy_deallocate(&v101);
  return v99;
}

```

## disassembly

```asm
0x140089244  mov     [rsp-8+arg_10], rbx
0x140089249  push    rbp
0x14008924a  push    rsi
0x14008924b  push    rdi
0x14008924c  push    r12
0x14008924e  push    r13
0x140089250  push    r14
0x140089252  push    r15
0x140089254  lea     rbp, [rsp-200h]
0x14008925c  sub     rsp, 300h
0x140089263  mov     rax, cs:__security_cookie
0x14008926a  xor     rax, rsp
0x14008926d  mov     [rbp+230h+var_40], rax
0x140089274  mov     [rsp+330h+var_2E0], rdx
0x140089279  mov     rbx, rcx
0x14008927c  mov     [rbp+230h+var_270], rcx
0x140089280  mov     [rbp+230h+var_260], rcx
0x140089284  xor     r12d, r12d
0x140089287  lea     rax, ??_7CustomActionUri@Uev@@6B@; const Uev::CustomActionUri::`vftable'
0x14008928e  mov     [rcx], rax
0x140089291  lea     r14, [rcx+8]
0x140089295  mov     [rbp+230h+var_288], r14
0x140089299  mov     rcx, r14
0x14008929c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400892a1  nop
0x1400892a2  lea     rsi, [rbx+28h]
0x1400892a6  mov     [rbp+230h+var_278], rsi
0x1400892aa  xorps   xmm0, xmm0
0x1400892ad  movups  xmmword ptr [rsi], xmm0
0x1400892b0  mov     [rsi+10h], r12
0x1400892b4  lea     ecx, [r12+7]
0x1400892b9  mov     [rsi+18h], rcx
0x1400892bd  mov     [rsi], r12w
0x1400892c1  lea     r15, [rbx+48h]
0x1400892c5  movups  xmmword ptr [r15], xmm0
0x1400892c9  mov     [r15+10h], r12
0x1400892cd  mov     [r15+18h], rcx
0x1400892d1  mov     [r15], r12w
0x1400892d5  lea     r13, [rbx+68h]
0x1400892d9  movups  xmmword ptr [r13+0], xmm0
0x1400892de  mov     [r13+10h], r12
0x1400892e2  mov     [r13+18h], rcx
0x1400892e6  mov     [r13+0], r12w
0x1400892eb  lea     rdi, [rbx+88h]
0x1400892f2  mov     [rsp+330h+var_2E8], rdi
0x1400892f7  mov     [rdi], r12
0x1400892fa  mov     [rdi+8], r12
0x1400892fe  lea     ecx, [r12+60h]; Size
0x140089303  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140089308  mov     [rax], rax
0x14008930b  mov     [rax+8], rax
0x14008930f  mov     [rax+10h], rax
0x140089313  mov     word ptr [rax+18h], 101h
0x140089319  mov     [rdi], rax
0x14008931c  add     rbx, 98h
0x140089323  mov     [rbx], r12
0x140089326  mov     [rbx+8], r12
0x14008932a  mov     [rbx+10h], r12
0x14008932e  xorps   xmm0, xmm0
0x140089331  movups  [rbp+230h+var_250], xmm0
0x140089335  mov     [rbp+230h+var_240], r12
0x140089339  lea     ecx, [r12+7]
0x14008933e  mov     [rbp+230h+var_238], rcx
0x140089342  mov     word ptr [rbp+230h+var_250], r12w
0x140089347  movups  [rbp+230h+var_170], xmm0
0x14008934e  mov     [rbp+230h+var_160], r12
0x140089355  mov     [rbp+230h+var_158], rcx
0x14008935c  mov     word ptr [rbp+230h+var_170], r12w
0x140089364  movups  [rbp+230h+var_190], xmm0
0x14008936b  mov     [rbp+230h+var_180], r12
0x140089372  mov     [rbp+230h+var_178], rcx
0x140089379  mov     word ptr [rbp+230h+var_190], r12w
0x140089381  mov     [r15+10h], r12
0x140089385  cmp     [r15+18h], rcx
0x140089389  jbe     short loc_140089390
0x14008938b  mov     rcx, [r15]
0x14008938e  jmp     short loc_140089393
0x140089390  mov     rcx, r15
0x140089393  mov     [rcx], r12w
0x140089397  mov     r15, [rdi]
0x14008939a  mov     r12, [r15+8]
0x14008939e  cmp     byte ptr [r12+19h], 0
0x1400893a4  jnz     short loc_1400893F6
0x1400893a6  mov     r14, [rsp+330h+var_2E8]
0x1400893ab  mov     r8, [r12+10h]
0x1400893b0  mov     rdx, r14
0x1400893b3  mov     rcx, r14
0x1400893b6  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1400893bb  mov     rsi, r12
0x1400893be  mov     r12, [r12]
0x1400893c2  lea     rcx, [rsi+40h]
0x1400893c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400893cb  lea     rcx, [rsi+20h]
0x1400893cf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400893d4  mov     edx, 60h ; '`'
0x1400893d9  mov     rcx, rsi; Block
0x1400893dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400893e1  cmp     byte ptr [r12+19h], 0
0x1400893e7  jz      short loc_1400893AB
0x1400893e9  mov     r14, [rbp+230h+var_288]
0x1400893ed  mov     rsi, [rbp+230h+var_278]
0x1400893f1  mov     rdi, [rsp+330h+var_2E8]
0x1400893f6  mov     [r15+8], r15
0x1400893fa  mov     [r15], r15
0x1400893fd  mov     [r15+10h], r15
0x140089401  xor     r12d, r12d
0x140089404  mov     [rdi+8], r12
0x140089408  xorps   xmm0, xmm0
0x14008940b  movdqu  xmmword ptr [rbp+230h+var_2B0], xmm0
0x140089410  mov     [rbp+230h+var_2A0], r12
0x140089414  mov     [rbp+230h+var_298], r12
0x140089418  mov     [rbp+230h+var_290], r12
0x14008941c  lea     ecx, [r12+10h]; Size
0x140089421  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140089426  mov     [rax+8], r12
0x14008942a  mov     [rbp+230h+var_2B0], rax
0x14008942e  lea     rcx, [rbp+230h+var_2B0]
0x140089432  mov     [rax], rcx
0x140089435  lea     edx, [r12+3Fh]
0x14008943a  lea     r8, [rbp+230h+var_2B0]
0x14008943e  mov     r15, [rsp+330h+var_2E0]
0x140089443  mov     rcx, r15
0x140089446  call    ?Split@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_WAEAV?$deque@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; Uev::Common::Split(std::wstring const &,wchar_t,std::deque<std::wstring> &)
0x14008944b  mov     rax, [rbp+230h+var_290]
0x14008944f  cmp     rax, 2
0x140089453  ja      loc_140089A78
0x140089459  cmp     rax, 1
0x14008945d  jb      short loc_1400894CF
0x14008945f  mov     rax, [rbp+230h+var_2A0]
0x140089463  dec     rax
0x140089466  and     rax, [rbp+230h+var_298]
0x14008946a  mov     rdx, [rbp+230h+var_2B0+8]
0x14008946e  mov     rdx, [rdx+rax*8]
0x140089472  lea     rcx, [rbp+230h+var_170]
0x140089479  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008947e  nop
0x14008947f  mov     cl, 1
0x140089481  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x140089487  mov     rdi, rax
0x14008948a  mov     [rbp+230h+var_280], rax
0x14008948e  lea     rdx, [rbp+230h+var_288]
0x140089492  lea     rcx, [rbp+230h+var_170]
0x140089499  call    ??$trim@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@algorithm@boost@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVlocale@3@@Z; boost::algorithm::trim<std::wstring>(std::wstring &,std::locale const &)
0x14008949e  nop
0x14008949f  test    rdi, rdi
0x1400894a2  jz      short loc_1400894CB
0x1400894a4  mov     rax, [rdi]
0x1400894a7  mov     rcx, rdi
0x1400894aa  mov     rax, [rax+10h]
0x1400894ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400894b3  mov     rcx, rax
0x1400894b6  test    rax, rax
0x1400894b9  jz      short loc_1400894CB
0x1400894bb  mov     rax, [rax]
0x1400894be  lea     edx, [r12+1]
0x1400894c3  mov     rax, [rax]
0x1400894c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400894cb  mov     rax, [rbp+230h+var_290]
0x1400894cf  cmp     rax, 2
0x1400894d3  jnz     short loc_140089547
0x1400894d5  mov     rcx, [rbp+230h+var_298]
0x1400894d9  inc     rcx
0x1400894dc  mov     rax, [rbp+230h+var_2A0]
0x1400894e0  dec     rax
0x1400894e3  and     rcx, rax
0x1400894e6  mov     rdx, [rbp+230h+var_2B0+8]
0x1400894ea  mov     rdx, [rdx+rcx*8]
0x1400894ee  lea     rcx, [rbp+230h+var_190]
0x1400894f5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400894fa  nop
0x1400894fb  mov     cl, 1
0x1400894fd  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x140089503  mov     rdi, rax
0x140089506  mov     [rbp+230h+var_280], rax
0x14008950a  lea     rdx, [rbp+230h+var_288]
0x14008950e  lea     rcx, [rbp+230h+var_190]
0x140089515  call    ??$trim@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@algorithm@boost@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVlocale@3@@Z; boost::algorithm::trim<std::wstring>(std::wstring &,std::locale const &)
0x14008951a  nop
0x14008951b  test    rdi, rdi
0x14008951e  jz      short loc_140089547
0x140089520  mov     rax, [rdi]
0x140089523  mov     rcx, rdi
0x140089526  mov     rax, [rax+10h]
0x14008952a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008952f  mov     rcx, rax
0x140089532  test    rax, rax
0x140089535  jz      short loc_140089547
0x140089537  mov     rax, [rax]
0x14008953a  mov     edx, 1
0x14008953f  mov     rax, [rax]
0x140089542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089547  xorps   xmm0, xmm0
0x14008954a  movdqu  xmmword ptr [rsp+330h+var_310], xmm0
0x140089550  mov     [rsp+330h+var_300], r12
0x140089555  mov     [rsp+330h+var_2F8], r12
0x14008955a  mov     [rsp+330h+var_2F0], r12
0x14008955f  mov     ecx, 10h; Size
0x140089564  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140089569  mov     [rax+8], r12
0x14008956d  mov     [rsp+330h+var_310], rax
0x140089572  lea     rcx, [rsp+330h+var_310]
0x140089577  mov     [rax], rcx
0x14008957a  mov     edx, 2Fh ; '/'
0x14008957f  lea     r8, [rsp+330h+var_310]
0x140089584  lea     rcx, [rbp+230h+var_170]
0x14008958b  call    ?Split@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_WAEAV?$deque@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@4@@Z; Uev::Common::Split(std::wstring const &,wchar_t,std::deque<std::wstring> &)
0x140089590  cmp     [rsp+330h+var_2F0], 3
0x140089596  jb      loc_140089AE3
0x14008959c  mov     rcx, [rsp+330h+var_300]
0x1400895a1  dec     rcx
0x1400895a4  and     rcx, [rsp+330h+var_2F8]
0x1400895a9  mov     rax, [rsp+330h+var_310+8]
0x1400895ae  mov     rcx, [rax+rcx*8]
0x1400895b2  cmp     qword ptr [rcx+18h], 7
0x1400895b7  jbe     short loc_1400895BC
0x1400895b9  mov     rcx, [rcx]
0x1400895bc  lea     rdx, aCustom; "custom:"
0x1400895c3  call    cs:__imp__o__wcsicmp
0x1400895c9  test    eax, eax
0x1400895cb  jnz     loc_140089B4E
0x1400895d1  mov     rcx, [rsp+330h+var_2F8]
0x1400895d6  inc     rcx
0x1400895d9  mov     rax, [rsp+330h+var_300]
0x1400895de  dec     rax
0x1400895e1  and     rcx, rax
0x1400895e4  mov     rax, [rsp+330h+var_310+8]
0x1400895e9  mov     rcx, [rax+rcx*8]
0x1400895ed  cmp     qword ptr [rcx+18h], 7
0x1400895f2  jbe     short loc_1400895F7
0x1400895f4  mov     rcx, [rcx]
0x1400895f7  lea     rdx, Data
0x1400895fe  call    cs:__imp__o__wcsicmp
0x140089604  test    eax, eax
0x140089606  jnz     loc_140089BB9
0x14008960c  mov     r8, [rsp+330h+var_2F8]
0x140089611  add     r8, 2
0x140089615  mov     rax, [rsp+330h+var_300]
0x14008961a  dec     rax
0x14008961d  and     r8, rax
0x140089620  mov     rdx, [rsp+330h+var_310+8]
0x140089625  mov     rdx, [rdx+r8*8]
0x140089629  mov     rcx, [rbp+230h+var_270]
0x14008962d  add     rcx, 48h ; 'H'
0x140089631  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140089636  mov     rcx, [rsp+330h+var_2F0]
0x14008963b  cmp     rcx, 3
0x14008963f  jbe     loc_140089749
0x140089645  mov     rax, [rsp+330h+var_2F8]
0x14008964a  dec     rax
0x14008964d  add     rcx, rax
0x140089650  mov     rax, [rsp+330h+var_300]
0x140089655  dec     rax
0x140089658  and     rcx, rax
0x14008965b  mov     rdx, [rsp+330h+var_310+8]
0x140089660  mov     rdx, [rdx+rcx*8]
0x140089664  mov     rcx, r13
0x140089667  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14008966c  mov     r9, [r13+10h]
0x140089670  cmp     qword ptr [r13+18h], 7
0x140089675  jbe     short loc_14008967B
0x140089677  mov     r13, [r13+0]
0x14008967b  mov     rcx, [r14+10h]
0x14008967f  cmp     qword ptr [r14+18h], 7
0x140089684  jbe     short loc_14008968B
0x140089686  mov     r15, [r14]
0x140089689  jmp     short loc_14008968E
0x14008968b  mov     r15, r14
0x14008968e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140089692  test    r9, r9
0x140089695  jnz     short loc_1400896A0
0x140089697  cmp     rcx, rsi
0x14008969a  cmovb   rsi, rcx
0x14008969e  jmp     short loc_1400896D5
0x1400896a0  cmp     r9, rcx
0x1400896a3  ja      short loc_1400896D5
0x1400896a5  sub     rcx, r9
0x1400896a8  mov     rax, rsi
0x1400896ab  cmp     rcx, rsi
0x1400896ae  cmovb   rax, rcx
0x1400896b2  add     rax, r9
0x1400896b5  lea     rdi, [r15+rax*2]
0x1400896b9  mov     r8, r13
0x1400896bc  mov     rdx, rdi
0x1400896bf  mov     rcx, r15
0x1400896c2  call    __std_find_end_2
0x1400896c7  cmp     rax, rdi
0x1400896ca  jz      short loc_1400896D5
0x1400896cc  mov     rsi, rax
0x1400896cf  sub     rsi, r15
0x1400896d2  sar     rsi, 1
0x1400896d5  xorps   xmm0, xmm0
0x1400896d8  movups  [rbp+230h+var_1F0], xmm0
0x1400896dc  mov     qword ptr [rbp+230h+var_1E0], r12
0x1400896e0  mov     qword ptr [rbp+230h+var_1E0+8], r12
0x1400896e4  lea     rax, [rsi-1]
0x1400896e8  mov     r8, [r14+10h]
0x1400896ec  cmp     r8, rax
0x1400896ef  cmovnb  r8, rax
0x1400896f3  cmp     qword ptr [r14+18h], 7
0x1400896f8  jbe     short loc_1400896FD
  ... truncated ...
```
