# StateRepository::Entity::PackageLocation::RowToObject(StateRepository::Statement const &,StateRepository::Entity::PackageLocation &,__int64)

- ea: `0x180042190`
- end: `0x1800430a1`
- name: `?RowToObject@PackageLocation@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z`
- size: `3857`
- prototype: `static int(const struct StateRepository::Statement *, struct StateRepository::Entity::PackageLocation *, __int64)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019324`
- `0x18001a070`
- `0x1800f8dd4`
- `0x1802324ac`
- `0x180232618`

## callees

- `0x180017a58`
- `0x18001a9e0`
- `0x180042190`
- `0x1800430a8`
- `0x180078ca0`
- `0x1800ad7dc`
- `0x18018fb5c`
- `0x18019914d`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x1800425cc`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042659`
- `StateRepository.Core!sqlite3_db_handle` at `0x1800426d8`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004273b`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004279e`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042ac3`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042b13`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042b6d`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042c00`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042c8f`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042d16`
- `StateRepository.Core!sqlite3_db_handle` at `0x1800425cc`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042659`
- `StateRepository.Core!sqlite3_db_handle` at `0x1800426d8`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004273b`
- `StateRepository.Core!sqlite3_db_handle` at `0x18004279e`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042ac3`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042b13`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042b6d`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042c00`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042c8f`
- `StateRepository.Core!sqlite3_db_handle` at `0x180042d16`
- `StateRepository.Core!sqlite3_column_blob` at `0x180042aa9`
- `StateRepository.Core!sqlite3_column_blob` at `0x180042aa9`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042348`
- `StateRepository.Core!sqlite3_column_text16` at `0x1800424a8`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042824`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042969`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042348`
- `StateRepository.Core!sqlite3_column_text16` at `0x1800424a8`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042824`
- `StateRepository.Core!sqlite3_column_text16` at `0x180042969`
- `StateRepository.Core!sqlite3_column_bytes` at `0x180042afa`
- `StateRepository.Core!sqlite3_column_bytes` at `0x180042afa`
- `StateRepository.Core!sqlite3_column_int64` at `0x18004229d`
- `StateRepository.Core!sqlite3_column_int64` at `0x1800422c5`
- `StateRepository.Core!sqlite3_column_int64` at `0x1800422e4`
- `StateRepository.Core!sqlite3_column_int64` at `0x180042302`
- `StateRepository.Core!sqlite3_column_int64` at `0x18004231f`
- `StateRepository.Core!sqlite3_column_int64` at `0x18004229d`
- `StateRepository.Core!sqlite3_column_int64` at `0x1800422c5`
- `StateRepository.Core!sqlite3_column_int64` at `0x1800422e4`
- `StateRepository.Core!sqlite3_column_int64` at `0x180042302`
- `StateRepository.Core!sqlite3_column_int64` at `0x18004231f`
- `StateRepository.Core!sqlite3_errcode` at `0x1800425d5`
- `StateRepository.Core!sqlite3_errcode` at `0x180042662`
- `StateRepository.Core!sqlite3_errcode` at `0x1800426e1`
- `StateRepository.Core!sqlite3_errcode` at `0x180042744`
- `StateRepository.Core!sqlite3_errcode` at `0x1800427a7`
- `StateRepository.Core!sqlite3_errcode` at `0x180042acc`
- `StateRepository.Core!sqlite3_errcode` at `0x180042b1c`
- `StateRepository.Core!sqlite3_errcode` at `0x180042b76`
- `StateRepository.Core!sqlite3_errcode` at `0x180042c09`
- `StateRepository.Core!sqlite3_errcode` at `0x180042c98`
- `StateRepository.Core!sqlite3_errcode` at `0x180042d1f`
- `StateRepository.Core!sqlite3_errcode` at `0x1800425d5`
- `StateRepository.Core!sqlite3_errcode` at `0x180042662`
- `StateRepository.Core!sqlite3_errcode` at `0x1800426e1`
- `StateRepository.Core!sqlite3_errcode` at `0x180042744`
- `StateRepository.Core!sqlite3_errcode` at `0x1800427a7`
- `StateRepository.Core!sqlite3_errcode` at `0x180042acc`
- `StateRepository.Core!sqlite3_errcode` at `0x180042b1c`
- `StateRepository.Core!sqlite3_errcode` at `0x180042b76`
- `StateRepository.Core!sqlite3_errcode` at `0x180042c09`
- `StateRepository.Core!sqlite3_errcode` at `0x180042c98`
- `StateRepository.Core!sqlite3_errcode` at `0x180042d1f`

## string_xrefs

- `0x180042460`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1800425ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042926`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042a64`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042e32`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042e4e`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042e74`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042e90`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042eb6`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042ed2`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042ef8`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042f14`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042faf`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180042fed`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x18004302b`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180043067`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1800421bc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042624`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x1800426b1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042714`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042777`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x1800427da`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042bc5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042c58`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042ccb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042d6e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x180042dcf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packagelocation.cpp`
- `0x18004260b`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042698`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042bac`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042c3f`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042d55`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042db6`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042def`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180042f3a`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`
- `0x180042f56`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`
- `0x180043085`: `onecore\base\appmodel\staterepository\dataaccesslayer\blob.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageLocation::RowToObject(
        const struct StateRepository::Statement *a1,
        struct StateRepository::Entity::PackageLocation *a2,
        __int64 a3)
{
  int v3; // r15d
  __int64 v5; // rcx
  unsigned __int64 v8; // rdx
  void *v9; // rbx
  signed int v10; // ebx
  __int64 v11; // rbx
  unsigned int v12; // ebx
  __int64 v13; // rdi
  unsigned int v14; // edi
  __int64 v15; // rbx
  unsigned int v16; // edi
  __int64 v17; // rbx
  __int64 v18; // rbx
  unsigned int v19; // ebp
  unsigned __int64 v20; // rdx
  _WORD *v21; // rbx
  __int64 v22; // r14
  __int64 v23; // r9
  __int64 v24; // r15
  _WORD *v25; // rax
  __int64 v26; // rcx
  signed int v27; // edi
  unsigned __int64 v28; // rsi
  unsigned __int64 v29; // rax
  _WORD *v30; // rax
  unsigned __int64 v31; // rdx
  _WORD *v32; // rdi
  _WORD *v33; // r8
  __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  _WORD *v36; // rax
  void *v37; // rcx
  unsigned int v38; // ebp
  unsigned __int64 v39; // rdx
  _WORD *v40; // rbx
  __int64 v41; // rcx
  _WORD *v42; // rax
  signed int v43; // edi
  unsigned __int64 v44; // rsi
  unsigned __int64 v45; // rax
  _WORD *v46; // rax
  unsigned __int64 v47; // rdx
  _WORD *v48; // rdi
  _WORD *v49; // r8
  __int64 v50; // rcx
  unsigned __int64 v51; // rdx
  _WORD *v52; // rax
  __int64 v53; // r9
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rax
  int v57; // eax
  unsigned int v58; // esi
  __int64 v59; // rax
  int v60; // eax
  unsigned int v61; // esi
  __int64 v62; // rax
  int v63; // eax
  unsigned int v64; // esi
  __int64 v65; // rax
  int v66; // eax
  unsigned int v67; // esi
  void *v68; // rcx
  unsigned __int64 v69; // rdx
  _WORD *v70; // rbx
  __int64 v71; // rcx
  _WORD *v72; // rax
  signed int v73; // edi
  unsigned __int64 v74; // rsi
  unsigned __int64 v75; // rax
  _WORD *v76; // rax
  unsigned __int64 v77; // rdx
  _WORD *v78; // rdi
  _WORD *v79; // r8
  __int64 v80; // rcx
  unsigned __int64 v81; // rdx
  _WORD *v82; // rax
  __int64 v83; // r9
  void *v84; // rcx
  unsigned int v85; // esi
  unsigned __int64 v86; // rdx
  _WORD *v87; // rbx
  _WORD *v88; // rax
  signed int v89; // edi
  unsigned __int64 v90; // rbp
  unsigned __int64 v91; // rax
  _WORD *v92; // rax
  unsigned __int64 v93; // rdx
  _WORD *v94; // rdi
  _WORD *v95; // rdx
  __int64 v96; // rcx
  _WORD *v97; // rax
  unsigned int v98; // eax
  void *v99; // rcx
  unsigned int v100; // esi
  const void *v101; // rbp
  __int64 v102; // rax
  int v103; // eax
  int v104; // eax
  unsigned __int64 v105; // rdx
  size_t v106; // rdi
  __int64 v107; // rax
  int v108; // eax
  void *v109; // rcx
  __int64 v110; // rax
  int v111; // eax
  __int64 v112; // rax
  __int64 v113; // rax
  int v114; // eax
  __int64 v115; // rax
  int v116; // eax
  unsigned int v117; // edi
  int v118; // eax
  int v119; // [rsp+20h] [rbp-38h]
  int v120; // [rsp+20h] [rbp-38h]
  int v121; // [rsp+20h] [rbp-38h]
  int v122; // [rsp+20h] [rbp-38h]
  int v123; // [rsp+20h] [rbp-38h]
  int v124; // [rsp+20h] [rbp-38h]
  int v125; // [rsp+20h] [rbp-38h]
  int v126; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = *(_QWORD *)a1;
  if ( !v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x301,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
      (const char *)0x8007139FLL,
      v119);
    return 2147947423LL;
  }
  if ( a3 )
  {
    *(_QWORD *)a2 = a3;
    v12 = 0;
  }
  else
  {
    v11 = sqlite3_column_int64(v5, 0);
    if ( v11
      || (!*(_QWORD *)a1 ? (v115 = 0) : (v115 = sqlite3_db_handle()),
          (v116 = sqlite3_errcode(v115), (v117 = v116) == 0) || v116 == 100) )
    {
      *(_QWORD *)a2 = v11;
    }
    else
    {
      if ( v116 > 0 )
        v117 = (unsigned __int16)v116 | 0x87AF0000;
      if ( (v117 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30A,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
          (const char *)v117,
          v119);
        return v117;
      }
    }
    v12 = 1;
  }
  v13 = sqlite3_column_int64(*(_QWORD *)a1, v12);
  if ( !v13 )
  {
    v56 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v57 = sqlite3_errcode(v56);
    v58 = v57;
    if ( v57 )
    {
      if ( v57 != 100 )
      {
        v13 = 0;
        if ( v57 > 0 )
          v58 = (unsigned __int16)v57 | 0x87AF0000;
        if ( (v58 & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x297,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)v58,
            v119);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30C,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
            (const char *)v58,
            v120);
          return v58;
        }
      }
    }
  }
  *((_QWORD *)a2 + 1) = v13;
  v14 = v12 + 1;
  v15 = sqlite3_column_int64(*(_QWORD *)a1, v12 + 1);
  if ( v15
    || (!*(_QWORD *)a1 ? (v59 = 0) : (v59 = sqlite3_db_handle()),
        (v60 = sqlite3_errcode(v59), (v61 = v60) == 0) || v60 == 100) )
  {
    *((_QWORD *)a2 + 2) = v15;
  }
  else
  {
    if ( v60 > 0 )
      v61 = (unsigned __int16)v60 | 0x87AF0000;
    if ( (v61 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
        (const char *)v61,
        v119);
      return v61;
    }
  }
  v16 = v14 + 1;
  v17 = sqlite3_column_int64(*(_QWORD *)a1, v16);
  if ( v17
    || (!*(_QWORD *)a1 ? (v62 = 0) : (v62 = sqlite3_db_handle()),
        (v63 = sqlite3_errcode(v62), (v64 = v63) == 0) || v63 == 100) )
  {
    *((_QWORD *)a2 + 3) = v17;
  }
  else
  {
    if ( v63 > 0 )
      v64 = (unsigned __int16)v63 | 0x87AF0000;
    if ( (v64 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
        (const char *)v64,
        v119);
      return v64;
    }
  }
  v18 = sqlite3_column_int64(*(_QWORD *)a1, v16 + 1);
  if ( v18
    || (!*(_QWORD *)a1 ? (v65 = 0) : (v65 = sqlite3_db_handle()),
        (v66 = sqlite3_errcode(v65), (v67 = v66) == 0) || v66 == 100) )
  {
    *((_QWORD *)a2 + 4) = v18;
  }
  else
  {
    if ( v66 > 0 )
      v67 = (unsigned __int16)v66 | 0x87AF0000;
    if ( (v67 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
        (const char *)v67,
        v119);
      return v67;
    }
  }
  v19 = v16 + 2;
  v126 = v3;
  v21 = (_WORD *)sqlite3_column_text16(*(_QWORD *)a1, v16 + 2);
  if ( !v21 )
  {
    v54 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v55 = sqlite3_errcode(v54);
    v27 = v55;
    if ( v55 )
    {
      if ( v55 != 100 )
      {
        v21 = 0;
        if ( v55 > 0 )
          v27 = (unsigned __int16)v55 | 0x87AF0000;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FD,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v27,
            v3);
          goto LABEL_80;
        }
      }
    }
  }
  v22 = 2147483646;
  v23 = 2147942522LL;
  if ( !v21 )
  {
    v37 = (void *)*((_QWORD *)a2 + 5);
    if ( v37 )
    {
      operator delete(v37, v20);
      *((_QWORD *)a2 + 5) = 0;
      *((_QWORD *)a2 + 6) = 0;
    }
    v24 = 500000000;
LABEL_49:
    v27 = 0;
    goto LABEL_50;
  }
  v24 = 500000000;
  v25 = v21;
  v26 = 500000000;
  do
  {
    if ( !*v25 )
      break;
    ++v25;
    --v26;
  }
  while ( v26 );
  v27 = -2147024809;
  if ( v26 )
  {
    v28 = 500000001 - v26;
    if ( (unsigned __int64)(500000001 - v26) <= *((_QWORD *)a2 + 6) )
    {
LABEL_36:
      v33 = (_WORD *)*((_QWORD *)a2 + 5);
      if ( !v28 )
      {
        v23 = 2147942487LL;
        goto LABEL_45;
      }
      if ( v28 > 0x7FFFFFFF )
      {
        v23 = 2147942487LL;
        *v33 = 0;
        goto LABEL_45;
      }
      v34 = 2147483646;
      v35 = v28;
      do
      {
        if ( !v34 )
          break;
        if ( !*v21 )
          break;
        *v33++ = *v21++;
        --v34;
        --v35;
      }
      while ( v35 );
      v36 = v33 - 1;
      if ( v35 )
      {
        v36 = v33;
        v23 = 0;
      }
      *v36 = 0;
      if ( !v35 )
LABEL_45:
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
          (const char *)v23,
          v126);
      *((_QWORD *)a2 + 6) = v28;
      goto LABEL_49;
    }
    v29 = 2 * v28;
    if ( !is_mul_ok(v28, 2u) )
      v29 = -1;
    v30 = operator new[](v29, (const struct std::nothrow_t *)&std::nothrow);
    v32 = v30;
    if ( v30 )
    {
      *v30 = 0;
      operator delete(*((void **)a2 + 5), v31);
      v23 = 2147942522LL;
      *((_QWORD *)a2 + 5) = v32;
      *((_QWORD *)a2 + 6) = v28;
      goto LABEL_36;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v126);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v121);
    v27 = -2147024882;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x80070057LL,
      v126);
  }
LABEL_50:
  if ( v27 < 0 )
  {
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x310,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
      (const char *)(unsigned int)v27,
      v126);
    return (unsigned int)v27;
  }
  v38 = v19 + 1;
  v40 = (_WORD *)sqlite3_column_text16(*(_QWORD *)a1, v38);
  if ( !v40 )
  {
    v110 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v111 = sqlite3_errcode(v110);
    v43 = v111;
    if ( v111 )
    {
      if ( v111 != 100 )
      {
        v40 = 0;
        if ( v111 > 0 )
          v43 = (unsigned __int16)v111 | 0x87AF0000;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FD,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v43,
            v126);
          goto LABEL_193;
        }
      }
    }
  }
  if ( !v40 )
  {
    v68 = (void *)*((_QWORD *)a2 + 7);
    if ( v68 )
    {
      operator delete(v68, v39);
      *((_QWORD *)a2 + 7) = 0;
      *((_QWORD *)a2 + 8) = 0;
    }
LABEL_116:
    v43 = 0;
    goto LABEL_117;
  }
  v41 = 500000000;
  v42 = v40;
  do
  {
    if ( !*v42 )
      break;
    ++v42;
    --v41;
  }
  while ( v41 );
  v43 = -2147024809;
  if ( v41 )
  {
    v44 = 500000001 - v41;
    if ( (unsigned __int64)(500000001 - v41) <= *((_QWORD *)a2 + 8) )
    {
LABEL_62:
      v49 = (_WORD *)*((_QWORD *)a2 + 7);
      if ( !v44 )
      {
        v53 = 2147942487LL;
        goto LABEL_71;
      }
      if ( v44 > 0x7FFFFFFF )
      {
        v53 = 2147942487LL;
        *v49 = 0;
        goto LABEL_71;
      }
      v50 = 2147483646;
      v51 = v44;
      do
      {
        if ( !v50 )
          break;
        if ( !*v40 )
          break;
        *v49++ = *v40++;
        --v50;
        --v51;
      }
      while ( v51 );
      v52 = v49 - 1;
      v53 = 2147942522LL;
      if ( v51 )
      {
        v52 = v49;
        v53 = 0;
      }
      *v52 = 0;
      if ( !v51 )
LABEL_71:
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
          (const char *)v53,
          v126);
      *((_QWORD *)a2 + 8) = v44;
      goto LABEL_116;
    }
    v45 = 2 * v44;
    if ( !is_mul_ok(v44, 2u) )
      v45 = -1;
    v46 = operator new[](v45, (const struct std::nothrow_t *)&std::nothrow);
    v48 = v46;
    if ( v46 )
    {
      *v46 = 0;
      operator delete(*((void **)a2 + 7), v47);
      *((_QWORD *)a2 + 7) = v48;
      *((_QWORD *)a2 + 8) = v44;
      goto LABEL_62;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v126);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v122);
    v43 = -2147024882;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x80070057LL,
      v126);
  }
LABEL_117:
  if ( v43 < 0 )
  {
LABEL_193:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
      (const char *)(unsigned int)v43,
      v126);
    return (unsigned int)v43;
  }
  v70 = (_WORD *)sqlite3_column_text16(*(_QWORD *)a1, v38 + 1);
  if ( !v70 )
  {
    v112 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v118 = sqlite3_errcode(v112);
    v73 = v118;
    if ( v118 )
    {
      if ( v118 != 100 )
      {
        v70 = 0;
        if ( v118 > 0 )
          v73 = (unsigned __int16)v118 | 0x87AF0000;
        if ( v73 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FD,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v73,
            v126);
          goto LABEL_228;
        }
      }
    }
  }
  if ( !v70 )
  {
    v84 = (void *)*((_QWORD *)a2 + 9);
    if ( v84 )
    {
      operator delete(v84, v69);
      *((_QWORD *)a2 + 9) = 0;
      *((_QWORD *)a2 + 10) = 0;
    }
LABEL_141:
    v73 = 0;
    goto LABEL_142;
  }
  v71 = 500000000;
  v72 = v70;
  do
  {
    if ( !*v72 )
      break;
    ++v72;
    --v71;
  }
  while ( v71 );
  v73 = -2147024809;
  if ( v71 )
  {
    v74 = 500000001 - v71;
    if ( (unsigned __int64)(500000001 - v71) <= *((_QWORD *)a2 + 10) )
    {
LABEL_129:
      v79 = (_WORD *)*((_QWORD *)a2 + 9);
      if ( !v74 )
      {
        v83 = 2147942487LL;
        goto LABEL_138;
      }
      if ( v74 > 0x7FFFFFFF )
      {
        v83 = 2147942487LL;
        *v79 = 0;
        goto LABEL_138;
      }
      v80 = 2147483646;
      v81 = v74;
      do
      {
        if ( !v80 )
          break;
        if ( !*v70 )
          break;
        *v79++ = *v70++;
        --v80;
        --v81;
      }
      while ( v81 );
      v82 = v79 - 1;
      v83 = 2147942522LL;
      if ( v81 )
      {
        v82 = v79;
        v83 = 0;
      }
      *v82 = 0;
      if ( !v81 )
LABEL_138:
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
          (const char *)v83,
          v126);
      *((_QWORD *)a2 + 10) = v74;
      goto LABEL_141;
    }
    v75 = 2 * v74;
    if ( !is_mul_ok(v74, 2u) )
      v75 = -1;
    v76 = operator new[](v75, (const struct std::nothrow_t *)&std::nothrow);
    v78 = v76;
    if ( v76 )
    {
      *v76 = 0;
      operator delete(*((void **)a2 + 9), v77);
      *((_QWORD *)a2 + 9) = v78;
      *((_QWORD *)a2 + 10) = v74;
      goto LABEL_129;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v126);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v123);
    v73 = -2147024882;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x80070057LL,
      v126);
  }
LABEL_142:
  if ( v73 < 0 )
  {
LABEL_228:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x312,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
      (const char *)(unsigned int)v73,
      v126);
    return (unsigned int)v73;
  }
  v85 = v38 + 2;
  v87 = (_WORD *)sqlite3_column_text16(*(_QWORD *)a1, v38 + 2);
  if ( !v87 )
  {
    v113 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v114 = sqlite3_errcode(v113);
    v89 = v114;
    if ( v114 )
    {
      if ( v114 != 100 )
      {
        v87 = 0;
        if ( v114 > 0 )
          v89 = (unsigned __int16)v114 | 0x87AF0000;
        if ( v89 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2FD,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v89,
            v126);
          goto LABEL_204;
        }
      }
    }
  }
  if ( !v87 )
  {
    v99 = (void *)*((_QWORD *)a2 + 11);
    if ( v99 )
    {
      operator delete(v99, v86);
      *((_QWORD *)a2 + 11) = 0;
      *((_QWORD *)a2 + 12) = 0;
    }
    goto LABEL_167;
  }
  v88 = v87;
  do
  {
    if ( !*v88 )
      break;
    ++v88;
    --v24;
  }
  while ( v24 );
  v89 = -2147024809;
  if ( v24 )
  {
    v90 = 500000001 - v24;
    if ( (unsigned __int64)(500000001 - v24) <= *((_QWORD *)a2 + 12) )
      goto LABEL_154;
    v91 = 2 * v90;
    if ( !is_mul_ok(v90, 2u) )
      v91 = -1;
    v92 = operator new[](v91, (const struct std::nothrow_t *)&std::nothrow);
    v94 = v92;
    if ( v92 )
    {
      *v92 = 0;
      operator delete(*((void **)a2 + 11), v93);
      *((_QWORD *)a2 + 11) = v94;
      *((_QWORD *)a2 + 12) = v90;
LABEL_154:
      v95 = (_WORD *)*((_QWORD *)a2 + 11);
      if ( v90 )
      {
        if ( v90 > 0x7FFFFFFF )
        {
          v98 = -2147024809;
          *v95 = 0;
        }
        else
        {
          v96 = 500000001 - v24;
          do
          {
            if ( !v22 )
              break;
            if ( !*v87 )
              break;
            *v95++ = *v87++;
            --v22;
            --v96;
          }
          while ( v96 );
          v97 = v95 - 1;
          if ( v96 )
            v97 = v95;
          *v97 = 0;
          v98 = -2147024774;
          if ( v96 )
          {
            *((_QWORD *)a2 + 12) = v90;
LABEL_167:
            v89 = 0;
            goto LABEL_168;
          }
        }
      }
      else
      {
        v98 = -2147024809;
      }
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)v98,
        v126);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v126);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x8007000ELL,
      v124);
    v89 = -2147024882;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)0x80070057LL,
      v126);
  }
LABEL_168:
  if ( v89 < 0 )
  {
LABEL_204:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
      (const char *)(unsigned int)v89,
      v126);
    return (unsigned int)v89;
  }
  v100 = v85 + 1;
  v101 = (const void *)sqlite3_column_blob(*(_QWORD *)a1, v100);
  if ( !v101 )
  {
    v102 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v103 = sqlite3_errcode(v102);
    v10 = v103;
    if ( v103 )
    {
      if ( v103 != 100 )
      {
        v101 = 0;
        if ( v103 > 0 )
          v10 = (unsigned __int16)v103 | 0x87AF0000;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x333,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v10,
            v126);
          goto LABEL_235;
        }
      }
    }
  }
  v104 = sqlite3_column_bytes(*(_QWORD *)a1, v100);
  v106 = v104;
  if ( !v104 )
  {
    v107 = *(_QWORD *)a1 ? sqlite3_db_handle() : 0LL;
    v108 = sqlite3_errcode(v107);
    v10 = v108;
    if ( v108 )
    {
      if ( v108 != 100 )
      {
        v106 = 0;
        if ( v108 > 0 )
          v10 = (unsigned __int16)v108 | 0x87AF0000;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x335,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v10,
            v126);
          goto LABEL_235;
        }
      }
    }
  }
  if ( !v106 )
  {
    v109 = (void *)*((_QWORD *)a2 + 13);
    if ( v109 )
    {
      operator delete(v109, v105);
      *((_QWORD *)a2 + 13) = 0;
      *((_QWORD *)a2 + 14) = 0;
      *((_QWORD *)a2 + 15) = 0;
    }
    goto LABEL_9;
  }
  if ( !v101 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
      (const char *)0x80070057LL,
      v126);
  if ( v106 <= *((_QWORD *)a2 + 15) )
  {
LABEL_8:
    memcpy_0(*((void **)a2 + 13), v101, v106);
    *((_QWORD *)a2 + 14) = v106;
LABEL_9:
    v10 = 0;
    goto LABEL_10;
  }
  v9 = operator new[](v106, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    operator delete(*((void **)a2 + 13), v8);
    *((_QWORD *)a2 + 13) = v9;
    *((_QWORD *)a2 + 14) = 0;
    *((_QWORD *)a2 + 15) = v106;
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
    (const char *)0x8007000ELL,
    v126);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\blob.cpp",
    (const char *)0x8007000ELL,
    v125);
  v10 = -2147024882;
LABEL_10:
  if ( v10 >= 0 )
  {
    if ( a3 )
    {
      if ( v100 == 8 )
        return 0;
    }
    else if ( v100 == 9 )
    {
      return 0;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 0;
  }
LABEL_235:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x314,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packagelocation.cpp",
    (const char *)(unsigned int)v10,
    v126);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180042190  mov     [rsp+arg_10], r8
0x180042195  mov     [rsp+arg_0], rcx
0x18004219a  push    r12
0x18004219c  push    r14
0x18004219e  sub     rsp, 48h
0x1800421a2  mov     r14, rcx
0x1800421a5  mov     rax, r8
0x1800421a8  mov     rcx, [rcx]
0x1800421ab  mov     r12, rdx
0x1800421ae  test    rcx, rcx
0x1800421b1  jnz     loc_180042283
0x1800421b7  mov     rcx, [rsp+58h]; this
0x1800421bc  lea     r8, aOnecoreBaseApp_167; "onecore\\base\\appmodel\\staterepositor"...
0x1800421c3  mov     r9d, 8007139Fh; char *
0x1800421c9  mov     edx, 301h; void *
0x1800421ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800421d3  mov     eax, 8007139Fh
0x1800421d8  add     rsp, 48h
0x1800421dc  pop     r14
0x1800421de  pop     r12
0x1800421e0  retn
0x1800421e1  test    rbp, rbp
0x1800421e4  jz      loc_180043080
0x1800421ea  cmp     rdi, [r12+78h]
0x1800421ef  jbe     short loc_180042225
0x1800421f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800421f8  mov     rcx, rdi; unsigned __int64
0x1800421fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042200  mov     rbx, rax
0x180042203  test    rax, rax
0x180042206  jz      loc_180042F35
0x18004220c  mov     rcx, [r12+68h]; void *
0x180042211  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180042216  mov     [r12+68h], rbx
0x18004221b  mov     [r12+70h], r13
0x180042220  mov     [r12+78h], rdi
0x180042225  mov     rcx, [r12+68h]; void *
0x18004222a  mov     r8, rdi; Size
0x18004222d  mov     rdx, rbp; Src
0x180042230  call    memcpy_0
0x180042235  mov     [r12+70h], rdi
0x18004223a  mov     ebx, r13d
0x18004223d  test    ebx, ebx
0x18004223f  js      loc_180042DCA
0x180042245  cmp     [rsp+58h+arg_10], 0
0x18004224b  jnz     loc_180042F77
0x180042251  cmp     esi, 9
0x180042254  jnz     loc_180042F80
0x18004225a  xor     eax, eax
0x18004225c  mov     rbp, [rsp+58h+var_18]
0x180042261  mov     r15, qword ptr [rsp+58h+var_38]
0x180042266  mov     rsi, [rsp+58h+var_20]
0x18004226b  mov     rdi, [rsp+58h+var_28]
0x180042270  mov     rbx, [rsp+58h+arg_8]
0x180042275  mov     r13, [rsp+58h+var_30]
0x18004227a  add     rsp, 48h
0x18004227e  pop     r14
0x180042280  pop     r12
0x180042282  retn
0x180042283  mov     [rsp+58h+arg_8], rbx
0x180042288  mov     [rsp+58h+var_28], rdi
0x18004228d  mov     [rsp+58h+var_30], r13
0x180042292  test    rax, rax
0x180042295  jnz     loc_18004263F
0x18004229b  xor     edx, edx
0x18004229d  call    cs:__imp_sqlite3_column_int64
0x1800422a3  xor     r13d, r13d
0x1800422a6  mov     rbx, rax
0x1800422a9  test    rax, rax
0x1800422ac  jz      loc_180042C83
0x1800422b2  mov     [r12], rbx
0x1800422b6  mov     ebx, 1
0x1800422bb  mov     rcx, [r14]
0x1800422be  mov     edx, ebx
0x1800422c0  mov     [rsp+58h+var_20], rsi
0x1800422c5  call    cs:__imp_sqlite3_column_int64
0x1800422cb  mov     rdi, rax
0x1800422ce  test    rax, rax
0x1800422d1  jz      loc_18004264D
0x1800422d7  mov     [r12+8], rdi
0x1800422dc  lea     edi, [rbx+1]
0x1800422df  mov     rcx, [r14]
0x1800422e2  mov     edx, edi
0x1800422e4  call    cs:__imp_sqlite3_column_int64
0x1800422ea  mov     rbx, rax
0x1800422ed  test    rax, rax
0x1800422f0  jz      loc_1800426CC
0x1800422f6  mov     [r12+10h], rbx
0x1800422fb  mov     rcx, [r14]
0x1800422fe  inc     edi
0x180042300  mov     edx, edi
0x180042302  call    cs:__imp_sqlite3_column_int64
0x180042308  mov     rbx, rax
0x18004230b  test    rax, rax
0x18004230e  jz      loc_18004272F
0x180042314  mov     [r12+18h], rbx
0x180042319  mov     rcx, [r14]
0x18004231c  lea     edx, [rdi+1]
0x18004231f  call    cs:__imp_sqlite3_column_int64
0x180042325  mov     rbx, rax
0x180042328  test    rax, rax
0x18004232b  jz      loc_180042792
0x180042331  mov     [r12+20h], rbx
0x180042336  mov     rcx, [r14]
0x180042339  mov     [rsp+58h+var_18], rbp
0x18004233e  lea     ebp, [rdi+2]
0x180042341  mov     edx, ebp
0x180042343  mov     qword ptr [rsp+58h+var_38], r15; int
0x180042348  call    cs:__imp_sqlite3_column_text16
0x18004234e  mov     rbx, rax
0x180042351  test    rax, rax
0x180042354  jz      loc_1800425C0
0x18004235a  mov     r14d, 7FFFFFFEh
0x180042360  mov     r9d, 8007007Ah
0x180042366  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18004236d  test    rbx, rbx
0x180042370  jz      loc_180042472
0x180042376  mov     r15d, 1DCD6500h
0x18004237c  mov     rax, rbx
0x18004237f  mov     ecx, r15d
0x180042382  cmp     word ptr [rax], 0
0x180042386  jz      short loc_180042392
0x180042388  add     rax, 2
0x18004238c  sub     rcx, 1
0x180042390  jnz     short loc_180042382
0x180042392  test    rcx, rcx
0x180042395  mov     edi, 80070057h
0x18004239a  cmovnz  edi, r13d
0x18004239e  jz      loc_180042FAA
0x1800423a4  mov     esi, 1DCD6501h
0x1800423a9  sub     rsi, rcx
0x1800423ac  cmp     rsi, [r12+30h]
0x1800423b1  jbe     short loc_1800423F8
0x1800423b3  mov     eax, 2
0x1800423b8  mul     rsi
0x1800423bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800423c2  cmovb   rax, r8
0x1800423c6  mov     rcx, rax; unsigned __int64
0x1800423c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800423ce  mov     rdi, rax
0x1800423d1  test    rax, rax
0x1800423d4  jz      loc_180042E2D
0x1800423da  mov     [rax], r13w
0x1800423de  mov     rcx, [r12+28h]; void *
0x1800423e3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800423e8  mov     r9d, 8007007Ah
0x1800423ee  mov     [r12+28h], rdi
0x1800423f3  mov     [r12+30h], rsi
0x1800423f8  mov     r8, [r12+28h]
0x1800423fd  test    rsi, rsi
0x180042400  jz      loc_180042F92
0x180042406  cmp     rsi, 7FFFFFFFh
0x18004240d  ja      loc_180042F8A
0x180042413  mov     rcx, r14
0x180042416  mov     rdx, rsi
0x180042419  nop     dword ptr [rax+00000000h]
0x180042420  test    rcx, rcx
0x180042423  jz      short loc_180042442
0x180042425  movzx   eax, word ptr [rbx]
0x180042428  test    ax, ax
0x18004242b  jz      short loc_180042442
0x18004242d  mov     [r8], ax
0x180042431  add     rbx, 2
0x180042435  add     r8, 2
0x180042439  dec     rcx
0x18004243c  sub     rdx, 1
0x180042440  jnz     short loc_180042420
0x180042442  test    rdx, rdx
0x180042445  lea     rax, [r8-2]
0x180042449  cmovnz  rax, r8
0x18004244d  cmovnz  r9d, r13d; char *
0x180042451  mov     [rax], r13w
0x180042455  jnz     loc_180042E05
0x18004245b  mov     rcx, [rsp+58h]; this
0x180042460  lea     r8, aOnecoreBaseApp_398; "onecore\\base\\appmodel\\staterepositor"...
0x180042467  mov     edx, 1Eh; void *
0x18004246c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180042472  mov     rcx, [r12+28h]; void *
0x180042477  test    rcx, rcx
0x18004247a  jz      short loc_18004248B
0x18004247c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180042481  mov     [r12+28h], r13
0x180042486  mov     [r12+30h], r13
0x18004248b  mov     r15d, 1DCD6500h
0x180042491  mov     edi, r13d
0x180042494  test    edi, edi
0x180042496  js      loc_18004261F
0x18004249c  mov     rdi, [rsp+58h+arg_0]
0x1800424a1  inc     ebp
0x1800424a3  mov     edx, ebp
0x1800424a5  mov     rcx, [rdi]
0x1800424a8  call    cs:__imp_sqlite3_column_text16
0x1800424ae  mov     rbx, rax
0x1800424b1  test    rax, rax
0x1800424b4  jz      loc_180042B61
0x1800424ba  test    rbx, rbx
0x1800424bd  jz      loc_1800427F5
0x1800424c3  mov     rcx, r15
0x1800424c6  mov     rax, rbx
0x1800424c9  nop     dword ptr [rax+00000000h]
0x1800424d0  cmp     word ptr [rax], 0
0x1800424d4  jz      short loc_1800424E0
0x1800424d6  add     rax, 2
0x1800424da  sub     rcx, 1
0x1800424de  jnz     short loc_1800424D0
0x1800424e0  test    rcx, rcx
0x1800424e3  mov     edi, 80070057h
0x1800424e8  cmovnz  edi, r13d
0x1800424ec  jz      loc_180042FE8
0x1800424f2  mov     esi, 1DCD6501h
0x1800424f7  sub     rsi, rcx
0x1800424fa  cmp     rsi, [r12+40h]
0x1800424ff  jbe     short loc_180042547
0x180042501  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042508  mov     eax, 2
0x18004250d  mul     rsi
0x180042510  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042517  cmovb   rax, rcx
0x18004251b  mov     rcx, rax; unsigned __int64
0x18004251e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042523  mov     rdi, rax
0x180042526  test    rax, rax
0x180042529  jz      loc_180042E6F
0x18004252f  mov     [rax], r13w
0x180042533  mov     rcx, [r12+38h]; void *
0x180042538  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004253d  mov     [r12+38h], rdi
0x180042542  mov     [r12+40h], rsi
0x180042547  mov     r8, [r12+38h]
0x18004254c  test    rsi, rsi
0x18004254f  jz      loc_180042FD0
0x180042555  cmp     rsi, 7FFFFFFFh
0x18004255c  ja      loc_180042FC8
0x180042562  mov     rcx, r14
0x180042565  mov     rdx, rsi
0x180042568  test    rcx, rcx
0x18004256b  jz      short loc_18004258A
0x18004256d  movzx   eax, word ptr [rbx]
0x180042570  test    ax, ax
0x180042573  jz      short loc_18004258A
0x180042575  mov     [r8], ax
0x180042579  add     rbx, 2
0x18004257d  add     r8, 2
0x180042581  dec     rcx
0x180042584  sub     rdx, 1
0x180042588  jnz     short loc_180042568
0x18004258a  test    rdx, rdx
0x18004258d  lea     rax, [r8-2]
0x180042591  mov     r9d, 8007007Ah
0x180042597  cmovnz  rax, r8
0x18004259b  cmovnz  r9d, r13d; char *
0x18004259f  mov     [rax], r13w
0x1800425a3  jnz     loc_180042E0F
0x1800425a9  mov     rcx, [rsp+58h]; this
0x1800425ae  lea     r8, aOnecoreBaseApp_398; "onecore\\base\\appmodel\\staterepositor"...
0x1800425b5  mov     edx, 1Eh; void *
0x1800425ba  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800425c0  mov     rcx, [r14]
0x1800425c3  test    rcx, rcx
0x1800425c6  jz      loc_180042C7B
0x1800425cc  call    cs:__imp_sqlite3_db_handle
0x1800425d2  mov     rcx, rax
0x1800425d5  call    cs:__imp_sqlite3_errcode
0x1800425db  mov     edi, eax
0x1800425dd  test    eax, eax
0x1800425df  jz      loc_18004235A
0x1800425e5  cmp     eax, 64h ; 'd'
0x1800425e8  jz      loc_18004235A
0x1800425ee  mov     rbx, r13
0x1800425f1  test    eax, eax
0x1800425f3  jle     short loc_1800425FE
0x1800425f5  movzx   edi, ax
0x1800425f8  or      edi, 87AF0000h
0x1800425fe  test    edi, edi
0x180042600  jns     loc_18004235A
0x180042606  mov     rcx, [rsp+58h]; this
0x18004260b  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x180042612  mov     r9d, edi; char *
0x180042615  mov     edx, 2FDh; void *
0x18004261a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004261f  mov     rcx, [rsp+58h]; this
0x180042624  lea     r8, aOnecoreBaseApp_167; "onecore\\base\\appmodel\\staterepositor"...
0x18004262b  mov     r9d, edi; char *
0x18004262e  mov     edx, 310h; void *
0x180042633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042638  mov     eax, edi
0x18004263a  jmp     loc_18004225C
0x18004263f  xor     r13d, r13d
0x180042642  mov     [rdx], rax
0x180042645  mov     ebx, r13d
0x180042648  jmp     loc_1800422BB
0x18004264d  mov     rcx, [r14]
0x180042650  test    rcx, rcx
0x180042653  jz      loc_180042CEE
0x180042659  call    cs:__imp_sqlite3_db_handle
0x18004265f  mov     rcx, rax
0x180042662  call    cs:__imp_sqlite3_errcode
0x180042668  mov     esi, eax
0x18004266a  test    eax, eax
0x18004266c  jz      loc_1800422D7
  ... truncated ...
```
