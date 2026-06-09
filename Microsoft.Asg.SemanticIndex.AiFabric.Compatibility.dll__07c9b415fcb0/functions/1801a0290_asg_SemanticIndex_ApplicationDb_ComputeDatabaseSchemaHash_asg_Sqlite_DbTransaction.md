# asg::SemanticIndex::ApplicationDb::ComputeDatabaseSchemaHash(asg::Sqlite::DbTransaction &)

- ea: `0x1801a0290`
- end: `0x1801a1517`
- name: `?ComputeDatabaseSchemaHash@ApplicationDb@SemanticIndex@asg@@SA_KAEAVDbTransaction@Sqlite@3@@Z`
- size: `4743`
- prototype: `unsigned __int64 __fastcall(struct asg::Sqlite::DbTransaction *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801a3630`

## callees

- `0x1800076f0`
- `0x1800079a0`
- `0x180007a00`
- `0x180018080`
- `0x18017bd20`
- `0x18017bd90`
- `0x18017bf60`
- `0x18017d4c0`
- `0x18017e310`
- `0x180180bd0`
- `0x1801a0290`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7680`
- `0x180206ec0`
- `0x1802421a0`
- `0x180242d80`

## string_xrefs

- `0x1801a0d25`: `on_update`
- `0x1801a0d99`: `on_delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall asg::SemanticIndex::ApplicationDb::ComputeDatabaseSchemaHash(struct asg::Sqlite::DbTransaction *a1)
{
  unsigned __int64 v1; // r13
  int v2; // r12d
  __m128i si128; // xmm6
  std::_Ref_count_base *v4; // r15
  int v5; // eax
  __int64 v6; // r15
  unsigned int ColumnIndex; // eax
  __int64 v8; // r15
  unsigned int v9; // eax
  __int64 v10; // r15
  unsigned int v11; // eax
  __int64 v12; // r15
  unsigned int v13; // eax
  void **v14; // rax
  size_t v15; // r12
  _QWORD *v16; // rax
  unsigned __int64 v17; // rcx
  __int128 *v18; // rax
  __int128 *appended; // rax
  void *v20; // rax
  std::_Ref_count_base *v21; // r15
  int v22; // eax
  __int64 v23; // r15
  unsigned int v24; // eax
  __int64 v25; // r13
  __int64 v26; // r15
  unsigned int v27; // eax
  __int64 v28; // r15
  unsigned int v29; // eax
  __int64 v30; // r15
  unsigned int v31; // eax
  size_t v32; // r12
  const void *p_Src; // r9
  unsigned __int64 v34; // rcx
  __int128 *v35; // r15
  char *v36; // r15
  __int128 *v37; // rax
  void *v38; // r12
  __int64 v39; // r15
  unsigned int v40; // eax
  void *v41; // r12
  const char *v42; // r15
  void *v43; // r12
  const char *v44; // r15
  void *v45; // rax
  void *v46; // r12
  const char *v47; // r15
  _BYTE *v48; // rcx
  _BYTE *v49; // rcx
  void *v50; // rcx
  _QWORD *v51; // rax
  std::_Ref_count_base *v52; // r15
  int v53; // eax
  unsigned __int64 v54; // rcx
  __int128 *v55; // r15
  _BYTE *v56; // r15
  __int128 *v57; // r12
  __int64 v58; // r15
  unsigned int v59; // eax
  void *v60; // rax
  void *v61; // r12
  __int64 v62; // r15
  unsigned int v63; // eax
  void *v64; // rax
  void *v65; // r12
  __int64 v66; // r15
  unsigned int v67; // eax
  void *v68; // rax
  void *v69; // r12
  __int64 v70; // r15
  unsigned int v71; // eax
  void *v72; // rax
  void *v73; // r12
  __int64 v74; // r15
  unsigned int v75; // eax
  void *v76; // rax
  void *v77; // r12
  __int64 v78; // r15
  unsigned int v79; // eax
  void *v80; // rax
  _BYTE *v81; // rcx
  _BYTE *v82; // rcx
  void *v83; // rcx
  _BYTE *v84; // rcx
  void *v85; // rcx
  _BYTE *v86; // rcx
  void **v87; // r9
  unsigned __int64 v88; // r13
  __int128 *v89; // r15
  __int128 *v90; // rax
  void *v91; // rax
  void *v92; // rax
  void *v93; // rax
  void *v94; // rax
  void *v95; // rax
  void *v96; // rax
  void *v97; // rcx
  void *v98; // rcx
  void *v99; // rcx
  void *v100; // rcx
  __int128 *v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rbx
  int v105; // [rsp+3Ch] [rbp-CCh]
  void *Src; // [rsp+40h] [rbp-C8h] BYREF
  size_t Size_8[2]; // [rsp+50h] [rbp-B8h]
  _BYTE *v108; // [rsp+60h] [rbp-A8h] BYREF
  __m128i v109; // [rsp+70h] [rbp-98h]
  __int128 v110; // [rsp+88h] [rbp-80h] BYREF
  __m128i v111; // [rsp+98h] [rbp-70h]
  asg::Sqlite::DbTransaction *v112; // [rsp+A8h] [rbp-60h]
  __int128 v113; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE *v114; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v115; // [rsp+D8h] [rbp-30h]
  _BYTE *v116; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v117; // [rsp+100h] [rbp-8h]
  _QWORD v118[2]; // [rsp+108h] [rbp+0h] BYREF
  _QWORD v119[2]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v120; // [rsp+128h] [rbp+20h]
  const char *v121; // [rsp+138h] [rbp+30h]
  __int64 v122; // [rsp+140h] [rbp+38h]
  _QWORD v123[2]; // [rsp+148h] [rbp+40h] BYREF
  _QWORD v124[2]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v125[2]; // [rsp+168h] [rbp+60h] BYREF
  _QWORD v126[2]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v127[2]; // [rsp+188h] [rbp+80h] BYREF
  __int128 v128; // [rsp+198h] [rbp+90h]
  const char *v129; // [rsp+1A8h] [rbp+A0h]
  __int64 v130; // [rsp+1B0h] [rbp+A8h]
  _QWORD v131[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _QWORD v132[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _QWORD v133[2]; // [rsp+1D8h] [rbp+D0h] BYREF
  _QWORD v134[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  _QWORD v135[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _QWORD v136[2]; // [rsp+208h] [rbp+100h] BYREF
  _QWORD v137[2]; // [rsp+218h] [rbp+110h] BYREF
  const char *v138; // [rsp+228h] [rbp+120h] BYREF
  _QWORD *v139; // [rsp+230h] [rbp+128h]
  __int64 v140; // [rsp+238h] [rbp+130h]
  char v141; // [rsp+270h] [rbp+168h]
  __int128 v142; // [rsp+278h] [rbp+170h] BYREF
  unsigned __int64 v143; // [rsp+288h] [rbp+180h]
  unsigned __int64 v144; // [rsp+290h] [rbp+188h]
  _QWORD v145[2]; // [rsp+298h] [rbp+190h] BYREF
  __int64 v146; // [rsp+2A8h] [rbp+1A0h]
  unsigned __int64 v147; // [rsp+2B0h] [rbp+1A8h]
  std::_Ref_count_base *v148[2]; // [rsp+2B8h] [rbp+1B0h]
  std::_Ref_count_base *v149[2]; // [rsp+2C8h] [rbp+1C0h]
  _QWORD v150[3]; // [rsp+2D8h] [rbp+1D0h] BYREF
  unsigned __int64 v151; // [rsp+2F0h] [rbp+1E8h]
  _QWORD v152[2]; // [rsp+2F8h] [rbp+1F0h] BYREF
  __m128i v153; // [rsp+308h] [rbp+200h]
  std::_Ref_count_base *v154[2]; // [rsp+318h] [rbp+210h]
  _QWORD v155[3]; // [rsp+328h] [rbp+220h] BYREF
  unsigned __int64 v156; // [rsp+340h] [rbp+238h]
  void *v157[2]; // [rsp+348h] [rbp+240h] BYREF
  size_t v158; // [rsp+358h] [rbp+250h]
  unsigned __int64 v159; // [rsp+360h] [rbp+258h]

  v112 = a1;
  v1 = 0;
  v2 = 0;
  *(_OWORD *)v154 = 0;
  v113 = 0;
  v148[0] = (std::_Ref_count_base *)"SELECT name, tbl_name, sql, type FROM sqlite_schema WHERE tbl_name LIKE 'si_%' ORDER"
                                    " BY type, tbl_name, name";
  v148[1] = (std::_Ref_count_base *)108;
  asg::Sqlite::DbTransaction::ExecuteQuery(a1, 0);
  v142 = 0;
  v143 = 0;
  v144 = 15;
  LOBYTE(v142) = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v4 = v154[0];
    if ( *((_DWORD *)v154[0] + 4) != 100 )
      break;
    if ( *((_BYTE *)v154[0] + 21) )
    {
      *((_BYTE *)v154[0] + 21) = 0;
      v5 = 100;
    }
    else
    {
      v5 = asg::Sqlite::DbReader::Step(v154[0]);
      *((_DWORD *)v4 + 4) = v5;
    }
    if ( v5 != 100 )
      break;
    v6 = *(_QWORD *)v154[0];
    v136[0] = "type";
    v136[1] = 4;
    ColumnIndex = asg::Sqlite::DbStatement::GetColumnIndex(v6, v136);
    asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v6, v157, ColumnIndex);
    v8 = *(_QWORD *)v154[0];
    v137[0] = "name";
    v137[1] = 4;
    v9 = asg::Sqlite::DbStatement::GetColumnIndex(v8, v137);
    asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v8, v155, v9);
    v10 = *(_QWORD *)v154[0];
    v118[0] = "tbl_name";
    v118[1] = 8;
    v11 = asg::Sqlite::DbStatement::GetColumnIndex(v10, v118);
    asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v10, v145, v11);
    v12 = *(_QWORD *)v154[0];
    v119[0] = "sql";
    v119[1] = 3;
    v13 = asg::Sqlite::DbStatement::GetColumnIndex(v12, v119);
    asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v12, v150, v13);
    v105 = v2 | 0x3FC0000;
    v14 = v157;
    if ( v159 > 0xF )
      v14 = (void **)v157[0];
    v15 = v158;
    if ( v158 == 5 && *(_DWORD *)v14 == 1818386804 && *((_BYTE *)v14 + 4) == 101 )
    {
      *(_OWORD *)v148 = 0;
      v138 = ":tableName";
      v16 = v145;
      if ( v147 > 0xF )
        v16 = (_QWORD *)v145[0];
      v139 = v16;
      v140 = v146;
      v141 = 4;
      *(_QWORD *)&v120 = &v138;
      *((_QWORD *)&v120 + 1) = 1;
      v110 = v120;
      v121 = "SELECT * FROM pragma_table_xinfo(:tableName) ORDER BY name";
      v122 = 58;
      asg::Sqlite::DbTransaction::ExecuteQuery(v112, 0);
      `eh vector destructor iterator'(
        &v138,
        0x50u,
        1u,
        std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
      v17 = v143;
      if ( v144 == v143 )
      {
        appended = (__int128 *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__QEAAAEAV34_QEB_Q_K_Z_PEB_Q_K___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_Q0_Z_PEB_Q_K_Z(
                                 &v142,
                                 1u);
      }
      else
      {
        ++v143;
        v18 = &v142;
        if ( v144 > 0xF )
          v18 = (__int128 *)v142;
        *(_WORD *)((char *)v18 + v17) = 10;
        appended = &v142;
      }
      v20 = (void *)std::basic_string<char8_t>::append(appended);
      std::basic_string<char8_t>::append(v20);
      while ( 1 )
      {
        v21 = v148[0];
        if ( *((_DWORD *)v148[0] + 4) != 100 )
          break;
        if ( *((_BYTE *)v148[0] + 21) )
        {
          *((_BYTE *)v148[0] + 21) = 0;
          v22 = 100;
        }
        else
        {
          v22 = asg::Sqlite::DbReader::Step(v148[0]);
          *((_DWORD *)v21 + 4) = v22;
        }
        if ( v22 != 100 )
          break;
        v23 = *(_QWORD *)v148[0];
        v123[0] = "notnull";
        v123[1] = 7;
        v24 = asg::Sqlite::DbStatement::GetColumnIndex(v23, v123);
        v25 = asg::Sqlite::DbStatement::Get<__int64>(v23, v24);
        v26 = *(_QWORD *)v148[0];
        v124[0] = "dflt_value";
        v124[1] = 10;
        v27 = asg::Sqlite::DbStatement::GetColumnIndex(v26, v124);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v26, v152, v27);
        v28 = *(_QWORD *)v148[0];
        v125[0] = "pk";
        v125[1] = 2;
        v29 = asg::Sqlite::DbStatement::GetColumnIndex(v28, v125);
        *(_QWORD *)&v110 = asg::Sqlite::DbStatement::Get<__int64>(v28, v29);
        v30 = *(_QWORD *)v148[0];
        v126[0] = "type";
        v126[1] = 4;
        v31 = asg::Sqlite::DbStatement::GetColumnIndex(v30, v126);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v30, &Src, v31);
        v32 = Size_8[0];
        p_Src = &Src;
        if ( Size_8[1] > 0xF )
          p_Src = Src;
        v34 = v143;
        if ( Size_8[0] > v144 - v143 )
        {
          _mm_lfence();
          v37 = (__int128 *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__QEAAAEAV34_QEB_Q_K_Z_PEB_Q_K___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_Q0_Z_PEB_Q_K_Z(
                              &v142,
                              Size_8[0]);
        }
        else
        {
          v143 += Size_8[0];
          v35 = &v142;
          if ( v144 > 0xF )
            v35 = (__int128 *)v142;
          v36 = (char *)v35 + v34;
          memmove(v36, p_Src, Size_8[0]);
          v36[v32] = 0;
          v37 = &v142;
        }
        v38 = (void *)std::basic_string<char8_t>::append(v37);
        v39 = *(_QWORD *)v148[0];
        v127[0] = "name";
        v127[1] = 4;
        v40 = asg::Sqlite::DbStatement::GetColumnIndex(v39, v127);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v39, &v108, v40);
        v105 |= 0x3F000u;
        v41 = (void *)std::basic_string<char8_t>::append(v38);
        v42 = " NULL";
        if ( v25 )
          v42 = " NOT NULL";
        strlen(v42);
        v43 = (void *)std::basic_string<char8_t>::append(v41);
        v44 = " DEFAULT ";
        if ( !v153.m128i_i64[0] )
          v44 = (const char *)&byte_1802990D8;
        strlen(v44);
        v45 = (void *)std::basic_string<char8_t>::append(v43);
        v46 = (void *)std::basic_string<char8_t>::append(v45);
        v47 = "\n";
        if ( (_QWORD)v110 )
          v47 = " PRIMARY KEY\n";
        strlen(v47);
        std::basic_string<char8_t>::append(v46);
        if ( v109.m128i_i64[1] > 0xFuLL )
        {
          v48 = v108;
          if ( (unsigned __int64)(v109.m128i_i64[1] + 1) >= 0x1000 )
          {
            v48 = (_BYTE *)*((_QWORD *)v108 - 1);
            if ( (unsigned __int64)(v108 - v48 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v48);
        }
        v109 = si128;
        LOBYTE(v108) = 0;
        if ( Size_8[1] > 0xF )
        {
          v49 = Src;
          if ( Size_8[1] + 1 >= 0x1000 )
          {
            v49 = (_BYTE *)*((_QWORD *)Src - 1);
            if ( (unsigned __int64)((_BYTE *)Src - v49 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v49);
        }
        *(__m128i *)Size_8 = si128;
        LOBYTE(Src) = 0;
        if ( v153.m128i_i64[1] > 0xFuLL )
        {
          v50 = (void *)v152[0];
          if ( (unsigned __int64)(v153.m128i_i64[1] + 1) >= 0x1000 )
          {
            v50 = *(void **)(v152[0] - 8LL);
            if ( (unsigned __int64)(v152[0] - (_QWORD)v50 - 8LL) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v50);
        }
      }
      *(_OWORD *)v149 = 0;
      v138 = ":tableName";
      v51 = v145;
      if ( v147 > 0xF )
        v51 = (_QWORD *)v145[0];
      v139 = v51;
      v140 = v146;
      v141 = 4;
      *(_QWORD *)&v128 = &v138;
      *((_QWORD *)&v128 + 1) = 1;
      v110 = v128;
      v129 = "SELECT * FROM pragma_foreign_key_list(:tableName)";
      v130 = 49;
      v1 = 0;
      asg::Sqlite::DbTransaction::ExecuteQuery(v112, 0);
      `eh vector destructor iterator'(
        &v138,
        0x50u,
        1u,
        std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
      while ( 1 )
      {
        v52 = v149[0];
        if ( *((_DWORD *)v149[0] + 4) != 100 )
          break;
        if ( *((_BYTE *)v149[0] + 21) )
        {
          *((_BYTE *)v149[0] + 21) = 0;
          v53 = 100;
        }
        else
        {
          v53 = asg::Sqlite::DbReader::Step(v149[0]);
          *((_DWORD *)v52 + 4) = v53;
        }
        if ( v53 != 100 )
          break;
        v54 = v143;
        if ( v144 - v143 < 0xC )
        {
          v57 = (__int128 *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__QEAAAEAV34_QEB_Q_K_Z_PEB_Q_K___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_Q0_Z_PEB_Q_K_Z(
                              &v142,
                              0xCu);
        }
        else
        {
          v143 += 12LL;
          v55 = &v142;
          if ( v144 > 0xF )
            v55 = (__int128 *)v142;
          v56 = (char *)v55 + v54;
          memmove(v56, "FOREIGN KEY\n", 0xCu);
          v56[12] = 0;
          v57 = &v142;
        }
        v58 = *(_QWORD *)v149[0];
        v131[0] = "from";
        v131[1] = 4;
        v59 = asg::Sqlite::DbStatement::GetColumnIndex(v58, v131);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v58, &v116, v59);
        v60 = (void *)std::basic_string<char8_t>::append(v57);
        v61 = (void *)std::basic_string<char8_t>::append(v60);
        v62 = *(_QWORD *)v149[0];
        v132[0] = "table";
        v132[1] = 5;
        v63 = asg::Sqlite::DbStatement::GetColumnIndex(v62, v132);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v62, v152, v63);
        v64 = (void *)std::basic_string<char8_t>::append(v61);
        v65 = (void *)std::basic_string<char8_t>::append(v64);
        v66 = *(_QWORD *)v149[0];
        v133[0] = "to";
        v133[1] = 2;
        v67 = asg::Sqlite::DbStatement::GetColumnIndex(v66, v133);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v66, &v114, v67);
        v68 = (void *)std::basic_string<char8_t>::append(v65);
        v69 = (void *)std::basic_string<char8_t>::append(v68);
        v70 = *(_QWORD *)v149[0];
        v134[0] = "on_update";
        v134[1] = 9;
        v71 = asg::Sqlite::DbStatement::GetColumnIndex(v70, v134);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v70, &v110, v71);
        v72 = (void *)std::basic_string<char8_t>::append(v69);
        v73 = (void *)std::basic_string<char8_t>::append(v72);
        v74 = *(_QWORD *)v149[0];
        v135[0] = "on_delete";
        v135[1] = 9;
        v75 = asg::Sqlite::DbStatement::GetColumnIndex(v74, v135);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v74, &v108, v75);
        v76 = (void *)std::basic_string<char8_t>::append(v73);
        v77 = (void *)std::basic_string<char8_t>::append(v76);
        v78 = *(_QWORD *)v149[0];
        *(_QWORD *)&v113 = "match";
        *((_QWORD *)&v113 + 1) = 5;
        v79 = asg::Sqlite::DbStatement::GetColumnIndex(v78, &v113);
        asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(v78, &Src, v79);
        v105 |= 0xFFFu;
        v80 = (void *)std::basic_string<char8_t>::append(v77);
        std::basic_string<char8_t>::append(v80);
        if ( Size_8[1] > 0xF )
        {
          v81 = Src;
          if ( Size_8[1] + 1 >= 0x1000 )
          {
            v81 = (_BYTE *)*((_QWORD *)Src - 1);
            if ( (unsigned __int64)((_BYTE *)Src - v81 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v81);
        }
        *(__m128i *)Size_8 = si128;
        LOBYTE(Src) = 0;
        if ( v109.m128i_i64[1] > 0xFuLL )
        {
          v82 = v108;
          if ( (unsigned __int64)(v109.m128i_i64[1] + 1) >= 0x1000 )
          {
            v82 = (_BYTE *)*((_QWORD *)v108 - 1);
            if ( (unsigned __int64)(v108 - v82 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v82);
        }
        v109 = si128;
        LOBYTE(v108) = 0;
        if ( v111.m128i_i64[1] > 0xFuLL )
        {
          v83 = (void *)v110;
          if ( (unsigned __int64)(v111.m128i_i64[1] + 1) >= 0x1000 )
          {
            v83 = *(void **)(v110 - 8);
            if ( (unsigned __int64)(v110 - (_QWORD)v83 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v83);
        }
        v111 = si128;
        LOBYTE(v110) = 0;
        if ( v115.m128i_i64[1] > 0xFuLL )
        {
          v84 = v114;
          if ( (unsigned __int64)(v115.m128i_i64[1] + 1) >= 0x1000 )
          {
            v84 = (_BYTE *)*((_QWORD *)v114 - 1);
            if ( (unsigned __int64)(v114 - v84 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v84);
        }
        v115 = si128;
        LOBYTE(v114) = 0;
        if ( v153.m128i_i64[1] > 0xFuLL )
        {
          v85 = (void *)v152[0];
          if ( (unsigned __int64)(v153.m128i_i64[1] + 1) >= 0x1000 )
          {
            v85 = *(void **)(v152[0] - 8LL);
            if ( (unsigned __int64)(v152[0] - (_QWORD)v85 - 8LL) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v85);
        }
        v153 = si128;
        LOBYTE(v152[0]) = 0;
        if ( v117 > 0xF )
        {
          v86 = v116;
          if ( v117 + 1 >= 0x1000 )
          {
            v86 = (_BYTE *)*((_QWORD *)v116 - 1);
            if ( (unsigned __int64)(v116 - v86 - 8) > 0x1F )
              invoke_watson(0, 0, 0, 0, 0);
          }
          _mm_lfence();
          operator delete(v86);
        }
      }
      if ( v149[1] )
        std::_Ref_count_base::_Decref(v149[1]);
      if ( v148[1] )
        std::_Ref_count_base::_Decref(v148[1]);
      if ( v151 > 0xF )
      {
        _mm_lfence();
        std::basic_string<char8_t>::_Deallocate_for_capacity(v150, v150[0], v151);
      }
      LOBYTE(v150[0]) = 0;
    }
    else
    {
      v87 = v157;
      if ( v159 > 0xF )
        v87 = (void **)v157[0];
      v88 = v143;
      if ( v158 > v144 - v143 )
      {
        _mm_lfence();
        v90 = (__int128 *)____Reallocate_grow_by_V_lambda_1___1__append___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__QEAAAEAV34_QEB_Q_K_Z_PEB_Q_K___basic_string__QU__char_traits__Q_std__V__allocator__Q_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_QEB_Q0_Z_PEB_Q_K_Z(
                            &v142,
                            v158);
      }
      else
      {
        v143 += v158;
        v89 = &v142;
        if ( v144 > 0xF )
          v89 = (__int128 *)v142;
        memmove((char *)v89 + v88, v87, v158);
        *((_BYTE *)v89 + v15 + v88) = 0;
        v90 = &v142;
      }
      v91 = (void *)std::basic_string<char8_t>::append(v90);
      v92 = (void *)std::basic_string<char8_t>::append(v91);
      v93 = (void *)std::basic_string<char8_t>::append(v92);
      v94 = (void *)std::basic_string<char8_t>::append(v93);
      v95 = (void *)std::basic_string<char8_t>::append(v94);
      v96 = (void *)std::basic_string<char8_t>::append(v95);
      std::basic_string<char8_t>::append(v96);
      if ( v151 > 0xF )
      {
        v97 = (void *)v150[0];
        if ( v151 + 1 >= 0x1000 )
        {
          v97 = *(void **)(v150[0] - 8LL);
          if ( (unsigned __int64)(v150[0] - (_QWORD)v97 - 8LL) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        _mm_lfence();
        operator delete(v97);
      }
      v1 = 0;
      LOBYTE(v150[0]) = 0;
    }
    v151 = 15;
    v150[2] = 0;
    if ( v147 > 0xF )
    {
      v98 = (void *)v145[0];
      if ( v147 + 1 >= 0x1000 )
      {
        v98 = *(void **)(v145[0] - 8LL);
        if ( (unsigned __int64)(v145[0] - (_QWORD)v98 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v98);
    }
    LOBYTE(v145[0]) = 0;
    v147 = 15;
    v146 = 0;
    if ( v156 > 0xF )
    {
      v99 = (void *)v155[0];
      if ( v156 + 1 >= 0x1000 )
      {
        v99 = *(void **)(v155[0] - 8LL);
        if ( (unsigned __int64)(v155[0] - (_QWORD)v99 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v99);
    }
    LOBYTE(v155[0]) = 0;
    v156 = 15;
    v155[2] = 0;
    if ( v159 > 0xF )
    {
      v100 = v157[0];
      if ( v159 + 1 >= 0x1000 )
      {
        v100 = (void *)*((_QWORD *)v157[0] - 1);
        if ( (unsigned __int64)((char *)v157[0] - (char *)v100 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v100);
    }
    v2 = v105;
  }
  v101 = &v142;
  if ( v144 > 0xF )
    v101 = (__int128 *)v142;
  v102 = 0xCBF29CE484222325uLL;
  if ( v143 )
  {
    do
      v102 = 0x100000001B3LL * (*((unsigned __int8 *)v101 + v1++) ^ (unsigned __int64)v102);
    while ( v1 < v143 );
  }
  v103 = v102 + 2654435769LL;
  std::basic_string<char8_t>::_Tidy_deallocate(&v142);
  if ( v154[1] )
    std::_Ref_count_base::_Decref(v154[1]);
  return v103;
}

```

## disassembly

```asm
0x1801a0290  mov     rax, rsp
0x1801a0293  mov     [rax+10h], rbx
0x1801a0297  mov     [rax+18h], rsi
0x1801a029b  mov     [rax+20h], rdi
0x1801a029f  push    rbp
0x1801a02a0  push    r12
0x1801a02a2  push    r13
0x1801a02a4  push    r14
0x1801a02a6  push    r15
0x1801a02a8  lea     rbp, [rax-2A8h]
0x1801a02af  sub     rsp, 380h
0x1801a02b6  movaps  xmmword ptr [rax-38h], xmm6
0x1801a02ba  mov     rax, cs:__security_cookie
0x1801a02c1  xor     rax, rsp
0x1801a02c4  mov     [rbp+2A0h+var_40], rax
0x1801a02cb  mov     [rbp+2A0h+var_300], rcx
0x1801a02cf  xor     r13d, r13d
0x1801a02d2  mov     r12d, r13d
0x1801a02d5  mov     dword ptr [rsp+3A0h+var_370+4], r13d
0x1801a02da  xorps   xmm0, xmm0
0x1801a02dd  movups  xmmword ptr [rbp+2A0h+var_90], xmm0
0x1801a02e4  xorps   xmm1, xmm1
0x1801a02e7  movdqa  [rbp+2A0h+var_2F0], xmm1
0x1801a02ec  lea     rax, aSelectNameTblN; "SELECT name, tbl_name, sql, type FROM s"...
0x1801a02f3  mov     [rbp+2A0h+var_F0], rax
0x1801a02fa  mov     [rbp+2A0h+var_F0+8], 6Ch ; 'l'
0x1801a0305  mov     dword ptr [rsp+3A0h+Reserved], r13d; int
0x1801a030a  lea     r9, [rbp+2A0h+var_2F0]
0x1801a030e  lea     r8, [rbp+2A0h+var_F0]
0x1801a0315  lea     rdx, [rbp+2A0h+var_90]
0x1801a031c  call    ?ExecuteQuery@DbTransaction@Sqlite@asg@@QEAA?AV?$shared_ptr@VDbReader@Sqlite@asg@@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@UDbParameters@23@W4DbStatementOptions@23@@Z; asg::Sqlite::DbTransaction::ExecuteQuery(std::u8string_view,asg::Sqlite::DbParameters,asg::Sqlite::DbStatementOptions)
0x1801a0321  nop
0x1801a0322  xorps   xmm0, xmm0
0x1801a0325  movups  [rbp+2A0h+var_130], xmm0
0x1801a032c  mov     [rbp+2A0h+var_120], r13
0x1801a0333  mov     [rbp+2A0h+var_118], 0Fh
0x1801a033e  mov     byte ptr [rbp+2A0h+var_130], r13b
0x1801a0345  movzx   ebx, byte ptr [rsp+3A0h+var_370]
0x1801a034a  movzx   edi, byte ptr [rsp+3A0h+var_370]
0x1801a034f  movzx   r14d, byte ptr [rsp+3A0h+var_370]
0x1801a0355  movzx   esi, byte ptr [rsp+3A0h+var_370]
0x1801a035a  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1801a0362  lea     rcx, aType; "type"
0x1801a0369  mov     r15, [rbp+2A0h+var_90]
0x1801a0370  cmp     dword ptr [r15+10h], 64h ; 'd'
0x1801a0375  jnz     loc_1801A134A
0x1801a037b  cmp     byte ptr [r15+15h], 0
0x1801a0380  jz      short loc_1801A038E
0x1801a0382  mov     byte ptr [r15+15h], 0
0x1801a0387  mov     eax, 64h ; 'd'
0x1801a038c  jmp     short loc_1801A03A1
0x1801a038e  mov     rcx, r15; this
0x1801a0391  call    ?Step@DbReader@Sqlite@asg@@AEAAHXZ; asg::Sqlite::DbReader::Step(void)
0x1801a0396  mov     [r15+10h], eax
0x1801a039a  lea     rcx, aType; "type"
0x1801a03a1  cmp     eax, 64h ; 'd'
0x1801a03a4  jnz     loc_1801A134A
0x1801a03aa  mov     rax, [rbp+2A0h+var_90]
0x1801a03b1  mov     r15, [rax]
0x1801a03b4  mov     [rbp+2A0h+var_1A0], rcx
0x1801a03bb  mov     [rbp+2A0h+var_198], 4
0x1801a03c6  lea     rdx, [rbp+2A0h+var_1A0]
0x1801a03cd  mov     rcx, r15
0x1801a03d0  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a03d5  mov     r8d, eax
0x1801a03d8  lea     rdx, [rbp+2A0h+var_60]
0x1801a03df  mov     rcx, r15
0x1801a03e2  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a03e7  or      r12d, 0C00000h
0x1801a03ee  mov     rax, [rbp+2A0h+var_90]
0x1801a03f5  mov     r15, [rax]
0x1801a03f8  lea     rax, aName; "name"
0x1801a03ff  mov     [rbp+2A0h+var_190], rax
0x1801a0406  mov     [rbp+2A0h+var_188], 4
0x1801a0411  lea     rdx, [rbp+2A0h+var_190]
0x1801a0418  mov     rcx, r15
0x1801a041b  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a0420  mov     r8d, eax
0x1801a0423  lea     rdx, [rbp+2A0h+var_80]
0x1801a042a  mov     rcx, r15
0x1801a042d  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a0432  nop
0x1801a0433  mov     rax, [rbp+2A0h+var_90]
0x1801a043a  mov     r15, [rax]
0x1801a043d  lea     rax, aTblName; "tbl_name"
0x1801a0444  mov     [rbp+2A0h+var_2A0], rax
0x1801a0448  mov     [rbp+2A0h+var_298], 8
0x1801a0450  lea     rdx, [rbp+2A0h+var_2A0]
0x1801a0454  mov     rcx, r15
0x1801a0457  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a045c  mov     r8d, eax
0x1801a045f  lea     rdx, [rbp+2A0h+var_110]
0x1801a0466  mov     rcx, r15
0x1801a0469  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a046e  nop
0x1801a046f  mov     rax, [rbp+2A0h+var_90]
0x1801a0476  mov     r15, [rax]
0x1801a0479  lea     rax, aSql; "sql"
0x1801a0480  mov     [rbp+2A0h+var_290], rax
0x1801a0484  mov     [rbp+2A0h+var_288], 3
0x1801a048c  lea     rdx, [rbp+2A0h+var_290]
0x1801a0490  mov     rcx, r15
0x1801a0493  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a0498  mov     r8d, eax
0x1801a049b  lea     rdx, [rbp+2A0h+var_D0]
0x1801a04a2  mov     rcx, r15
0x1801a04a5  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a04aa  or      r12d, 33C0000h
0x1801a04b1  mov     dword ptr [rsp+3A0h+var_370+4], r12d
0x1801a04b6  lea     rax, [rbp+2A0h+var_60]
0x1801a04bd  mov     rcx, [rbp+2A0h+var_60]
0x1801a04c4  mov     rdx, [rbp+2A0h+var_48]
0x1801a04cb  cmp     rdx, 0Fh
0x1801a04cf  cmova   rax, rcx
0x1801a04d3  mov     r12, [rbp+2A0h+var_50]
0x1801a04da  cmp     r12, 5
0x1801a04de  jnz     loc_1801A1092
0x1801a04e4  cmp     dword ptr [rax], 6C626174h
0x1801a04ea  jnz     loc_1801A1092
0x1801a04f0  cmp     byte ptr [rax+4], 65h ; 'e'
0x1801a04f4  jnz     loc_1801A1092
0x1801a04fa  xorps   xmm0, xmm0
0x1801a04fd  movups  xmmword ptr [rbp+2A0h+var_F0], xmm0
0x1801a0504  lea     r12, aTablename; ":tableName"
0x1801a050b  mov     [rbp+2A0h+var_180], r12
0x1801a0512  lea     rax, [rbp+2A0h+var_110]
0x1801a0519  cmp     [rbp+2A0h+var_F8], 0Fh
0x1801a0521  cmova   rax, [rbp+2A0h+var_110]
0x1801a0529  mov     [rbp+2A0h+var_178], rax
0x1801a0530  mov     rax, [rbp+2A0h+var_100]
0x1801a0537  mov     [rbp+2A0h+var_170], rax
0x1801a053e  mov     [rbp+2A0h+var_138], 4
0x1801a0545  lea     rax, [rbp+2A0h+var_180]
0x1801a054c  mov     qword ptr [rbp+2A0h+var_280], rax
0x1801a0550  mov     qword ptr [rbp+2A0h+var_280+8], 1
0x1801a0558  movaps  xmm0, [rbp+2A0h+var_280]
0x1801a055c  movdqa  [rbp+2A0h+var_320], xmm0
0x1801a0561  lea     rax, aSelectFromPrag; "SELECT * FROM pragma_table_xinfo(:table"...
0x1801a0568  mov     [rbp+2A0h+var_270], rax
0x1801a056c  mov     [rbp+2A0h+var_268], 3Ah ; ':'
0x1801a0574  mov     dword ptr [rsp+3A0h+Reserved], r13d; int
0x1801a0579  lea     r9, [rbp+2A0h+var_320]
0x1801a057d  lea     r8, [rbp+2A0h+var_270]
0x1801a0581  lea     rdx, [rbp+2A0h+var_F0]
0x1801a0588  mov     rcx, [rbp+2A0h+var_300]; this
0x1801a058c  call    ?ExecuteQuery@DbTransaction@Sqlite@asg@@QEAA?AV?$shared_ptr@VDbReader@Sqlite@asg@@@std@@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@UDbParameters@23@W4DbStatementOptions@23@@Z; asg::Sqlite::DbTransaction::ExecuteQuery(std::u8string_view,asg::Sqlite::DbParameters,asg::Sqlite::DbStatementOptions)
0x1801a0591  nop
0x1801a0592  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x1801a0599  mov     edx, 50h ; 'P'; unsigned __int64
0x1801a059e  mov     r8d, 1; unsigned __int64
0x1801a05a4  lea     rcx, [rbp+2A0h+var_180]; void *
0x1801a05ab  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801a05b0  mov     rcx, [rbp+2A0h+var_120]
0x1801a05b7  mov     rdx, [rbp+2A0h+var_118]
0x1801a05be  mov     rax, rdx
0x1801a05c1  sub     rax, rcx
0x1801a05c4  cmp     rax, 1
0x1801a05c8  jb      short loc_1801A05F7
0x1801a05ca  lea     rax, [rcx+1]
0x1801a05ce  mov     [rbp+2A0h+var_120], rax
0x1801a05d5  lea     rax, [rbp+2A0h+var_130]
0x1801a05dc  cmp     rdx, 0Fh
0x1801a05e0  cmova   rax, qword ptr [rbp+2A0h+var_130]
0x1801a05e8  mov     word ptr [rax+rcx], 0Ah
0x1801a05ee  lea     rax, [rbp+2A0h+var_130]
0x1801a05f5  jmp     short loc_1801A061C
0x1801a05f7  mov     [rsp+3A0h+Reserved], 1; Size
0x1801a0600  lea     r9, asc_180275D14; "\n"
0x1801a0607  movzx   r8d, sil
0x1801a060b  mov     edx, 1
0x1801a0610  lea     rcx, [rbp+2A0h+var_130]; Src
0x1801a0617  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV34@QEB_Q_K@Z@PEB_Q_K@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_Q0@Z@PEB_Q_K@Z; std::basic_string<char8_t>::_Reallocate_grow_by<`std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)'::`2'::_lambda_1_,char8_t const *,unsigned __int64>(unsigned __int64,`std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)'::`2'::_lambda_1_,char8_t const *,unsigned __int64)
0x1801a061c  lea     rdx, [rbp+2A0h+var_110]
0x1801a0623  cmp     [rbp+2A0h+var_F8], 0Fh
0x1801a062b  cmova   rdx, [rbp+2A0h+var_110]
0x1801a0633  mov     r8, [rbp+2A0h+var_100]
0x1801a063a  mov     rcx, rax; Src
0x1801a063d  call    ?append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV12@QEB_Q_K@Z; std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)
0x1801a0642  mov     r8d, 1
0x1801a0648  lea     rdx, asc_180275D14; "\n"
0x1801a064f  mov     rcx, rax; Src
0x1801a0652  call    ?append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV12@QEB_Q_K@Z; std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)
0x1801a0657  nop     word ptr [rax+rax+00000000h]
0x1801a0660  mov     r15, [rbp+2A0h+var_F0]
0x1801a0667  cmp     dword ptr [r15+10h], 64h ; 'd'
0x1801a066c  jnz     loc_1801A0A1F
0x1801a0672  cmp     byte ptr [r15+15h], 0
0x1801a0677  jz      short loc_1801A0685
0x1801a0679  mov     byte ptr [r15+15h], 0
0x1801a067e  mov     eax, 64h ; 'd'
0x1801a0683  jmp     short loc_1801A0691
0x1801a0685  mov     rcx, r15; this
0x1801a0688  call    ?Step@DbReader@Sqlite@asg@@AEAAHXZ; asg::Sqlite::DbReader::Step(void)
0x1801a068d  mov     [r15+10h], eax
0x1801a0691  cmp     eax, 64h ; 'd'
0x1801a0694  jnz     loc_1801A0A1F
0x1801a069a  mov     rax, [rbp+2A0h+var_F0]
0x1801a06a1  mov     r15, [rax]
0x1801a06a4  lea     rax, aNotnull; "notnull"
0x1801a06ab  mov     [rbp+2A0h+var_260], rax
0x1801a06af  mov     [rbp+2A0h+var_258], 7
0x1801a06b7  lea     rdx, [rbp+2A0h+var_260]
0x1801a06bb  mov     rcx, r15
0x1801a06be  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a06c3  mov     edx, eax
0x1801a06c5  mov     rcx, r15
0x1801a06c8  call    ??$Get@_J@DbStatement@Sqlite@asg@@QEBA_JH@Z; asg::Sqlite::DbStatement::Get<__int64>(int)
0x1801a06cd  mov     r13, rax
0x1801a06d0  mov     rcx, [rbp+2A0h+var_F0]
0x1801a06d7  mov     r15, [rcx]
0x1801a06da  lea     rax, aDfltValue; "dflt_value"
0x1801a06e1  mov     [rbp+2A0h+var_250], rax
0x1801a06e5  mov     [rbp+2A0h+var_248], 0Ah
0x1801a06ed  lea     rdx, [rbp+2A0h+var_250]
0x1801a06f1  mov     rcx, r15
0x1801a06f4  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a06f9  mov     r8d, eax
0x1801a06fc  lea     rdx, [rbp+2A0h+var_B0]
0x1801a0703  mov     rcx, r15
0x1801a0706  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a070b  nop
0x1801a070c  mov     rcx, [rbp+2A0h+var_F0]
0x1801a0713  mov     r15, [rcx]
0x1801a0716  lea     rax, aPk; "pk"
0x1801a071d  mov     [rbp+2A0h+var_240], rax
0x1801a0721  mov     [rbp+2A0h+var_238], 2
0x1801a0729  lea     rdx, [rbp+2A0h+var_240]
0x1801a072d  mov     rcx, r15
0x1801a0730  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a0735  mov     edx, eax
0x1801a0737  mov     rcx, r15
0x1801a073a  call    ??$Get@_J@DbStatement@Sqlite@asg@@QEBA_JH@Z; asg::Sqlite::DbStatement::Get<__int64>(int)
0x1801a073f  mov     qword ptr [rbp+2A0h+var_320], rax
0x1801a0743  mov     rcx, [rbp+2A0h+var_F0]
0x1801a074a  mov     r15, [rcx]
0x1801a074d  lea     rax, aType; "type"
0x1801a0754  mov     [rbp+2A0h+var_230], rax
0x1801a0758  mov     [rbp+2A0h+var_228], 4
0x1801a0760  lea     rdx, [rbp+2A0h+var_230]
0x1801a0764  mov     rcx, r15
0x1801a0767  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a076c  mov     r8d, eax
0x1801a076f  lea     rdx, [rsp+3A0h+Src]
0x1801a0774  mov     rcx, r15
0x1801a0777  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a077c  nop
0x1801a077d  mov     r12, [rsp+3A0h+Size+8]
0x1801a0782  lea     r9, [rsp+3A0h+Src]
0x1801a0787  cmp     [rsp+3A0h+var_350], 0Fh
0x1801a078d  cmova   r9, [rsp+3A0h+Src]
0x1801a0793  mov     rcx, [rbp+2A0h+var_120]
0x1801a079a  mov     rdx, [rbp+2A0h+var_118]
0x1801a07a1  mov     rax, rdx
0x1801a07a4  sub     rax, rcx
0x1801a07a7  cmp     r12, rax
0x1801a07aa  ja      short loc_1801A07E9
0x1801a07ac  lea     rax, [rcx+r12]
0x1801a07b0  mov     [rbp+2A0h+var_120], rax
0x1801a07b7  lea     r15, [rbp+2A0h+var_130]
0x1801a07be  cmp     rdx, 0Fh
0x1801a07c2  cmova   r15, qword ptr [rbp+2A0h+var_130]
0x1801a07ca  add     r15, rcx
0x1801a07cd  mov     r8, r12; Size
0x1801a07d0  mov     rdx, r9; Src
0x1801a07d3  mov     rcx, r15; void *
0x1801a07d6  call    memmove
0x1801a07db  mov     byte ptr [r12+r15], 0
0x1801a07e0  lea     rax, [rbp+2A0h+var_130]
0x1801a07e7  jmp     short loc_1801A0804
0x1801a07e9  lfence
0x1801a07ec  mov     [rsp+3A0h+Reserved], r12; Size
0x1801a07f1  movzx   r8d, dil
0x1801a07f5  mov     rdx, r12
0x1801a07f8  lea     rcx, [rbp+2A0h+var_130]; Src
0x1801a07ff  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV34@QEB_Q_K@Z@PEB_Q_K@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@QEB_Q0@Z@PEB_Q_K@Z; std::basic_string<char8_t>::_Reallocate_grow_by<`std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)'::`2'::_lambda_1_,char8_t const *,unsigned __int64>(unsigned __int64,`std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)'::`2'::_lambda_1_,char8_t const *,unsigned __int64)
0x1801a0804  mov     r8d, 1
0x1801a080a  lea     rdx, asc_180273654; " "
0x1801a0811  mov     rcx, rax; Src
0x1801a0814  call    ?append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV12@QEB_Q_K@Z; std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)
0x1801a0819  mov     r12, rax
0x1801a081c  mov     rcx, [rbp+2A0h+var_F0]
0x1801a0823  mov     r15, [rcx]
0x1801a0826  lea     rax, aName; "name"
0x1801a082d  mov     [rbp+2A0h+var_220], rax
0x1801a0834  mov     [rbp+2A0h+var_218], 4
0x1801a083f  lea     rdx, [rbp+2A0h+var_220]
0x1801a0846  mov     rcx, r15
0x1801a0849  call    ?GetColumnIndex@DbStatement@Sqlite@asg@@AEBAHV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@@Z; asg::Sqlite::DbStatement::GetColumnIndex(std::u8string_view)
0x1801a084e  mov     r8d, eax
0x1801a0851  lea     rdx, [rsp+3A0h+var_348]
0x1801a0856  mov     rcx, r15
0x1801a0859  call    ??$Get@V?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@@DbStatement@Sqlite@asg@@QEBA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@H@Z; asg::Sqlite::DbStatement::Get<std::basic_string<char8_t>>(int)
0x1801a085e  or      dword ptr [rsp+3A0h+var_370+4], 3F000h
0x1801a0866  lea     rdx, [rsp+3A0h+var_348]
0x1801a086b  cmp     [rsp+3A0h+var_330], 0Fh
0x1801a0871  cmova   rdx, [rsp+3A0h+var_348]
0x1801a0877  mov     r8, qword ptr [rsp+3A0h+var_340+8]
0x1801a087c  mov     rcx, r12; Src
0x1801a087f  call    ?append@?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@QEAAAEAV12@QEB_Q_K@Z; std::basic_string<char8_t>::append(char8_t const * const,unsigned __int64)
0x1801a0884  mov     r12, rax
  ... truncated ...
```
