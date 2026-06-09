# yy_reduce

- ea: `0x18001bc30`
- end: `0x18001e998`
- name: `yy_reduce`
- size: `11624`
- prototype: ``
- caller_count: `1`
- callee_count: `106`
- tags: `file_ops, installer_update`

## callers

- `0x18001b670`

## callees

- `0x180008860`
- `0x18000ab80`
- `0x180014464`
- `0x18001450c`
- `0x180014750`
- `0x180015e80`
- `0x180016bf4`
- `0x18001bc30`
- `0x18001e9a0`
- `0x18001ece0`
- `0x18001ed34`
- `0x18002b8ec`
- `0x18002d694`
- `0x18002f9a4`
- `0x180032130`
- `0x180033f04`
- `0x1800363dc`
- `0x180036538`
- `0x1800367a0`
- `0x1800399d0`
- `0x18003b8a0`
- `0x18003c328`
- `0x18003f5a8`
- `0x18003f960`
- `0x180041b80`
- `0x180042110`
- `0x180042130`
- `0x1800424b4`
- `0x180042d74`
- `0x180052514`
- `0x180054118`
- `0x180055e04`
- `0x180058924`
- `0x18005e230`
- `0x18006fb5c`
- `0x18006fbcc`
- `0x18007652c`
- `0x180076628`
- `0x1800766e0`
- `0x180076818`
- `0x1800769a8`
- `0x180076a1c`
- `0x180076c64`
- `0x180076e24`
- `0x18007732c`
- `0x1800776a4`
- `0x180077910`
- `0x180077d78`
- `0x180078aa4`
- `0x180078b7c`

## string_xrefs

- `0x18001dcd9`: `qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers`
- `0x18001dcf3`: `the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers`
- `0x18001dd08`: `the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers`

## pseudocode

```c
__int64 __fastcall yy_reduce(__int64 *a1, unsigned int a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  __int64 v5; // r13
  __int64 v6; // rbx
  __int64 v7; // rcx
  const char *v8; // r9
  int v9; // r8d
  int v10; // esi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // r14
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  bool v23; // zf
  __int64 v24; // rdi
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  int *v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r10
  _DWORD *v33; // rdx
  int *v34; // rax
  __int64 v35; // rdx
  int *v36; // r8
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdi
  __int64 v41; // rax
  _QWORD *v42; // r14
  __int64 v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r9
  __int64 v48; // r8
  __int64 v49; // rax
  int *v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rsi
  __int64 v54; // rdi
  __int64 v55; // rax
  __int64 v56; // r14
  __int64 v57; // rdi
  __int64 v58; // rax
  __int64 v59; // rdi
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // rax
  _BYTE *v63; // rax
  __int64 v64; // rax
  unsigned int v65; // esi
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // r8
  __int64 v69; // rdi
  __int64 v70; // rdi
  __int64 v71; // rdi
  __int64 v72; // rdi
  __int64 v73; // rdi
  __int64 v74; // rax
  int v75; // edi
  __int64 v76; // r8
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  int v80; // edi
  __int64 v81; // r8
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // r9
  unsigned __int8 *v87; // rax
  unsigned __int8 v88; // cl
  __int64 v89; // rax
  __int64 v90; // rax
  _QWORD *v91; // rdi
  __int64 v92; // rax
  __int64 v93; // rsi
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  const char *v97; // r8
  __int64 v98; // rax
  __int64 v99; // r15
  _QWORD *v100; // rdi
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rax
  __int64 v106; // rsi
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // r8
  __int64 v110; // rsi
  __int64 v111; // r15
  __int64 v112; // rax
  __int64 v113; // r14
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // rax
  __int64 v119; // r8
  __int64 v120; // rax
  __int64 v121; // r8
  int v122; // esi
  __int64 v123; // r14
  int v124; // r15d
  _DWORD *v125; // r12
  __int64 v126; // rax
  _QWORD *v127; // rdx
  int v128; // r9d
  int v129; // r8d
  int v130; // edx
  __int64 v131; // rdx
  unsigned int v132; // eax
  __int64 v133; // rcx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  _QWORD *v137; // rdi
  __int64 v138; // r8
  _QWORD *v139; // rdi
  __int64 v140; // r9
  __int64 v141; // rax
  __int64 v142; // rcx
  __int64 v143; // rax
  __int64 v144; // rdx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rdi
  __int64 v149; // rax
  int v150; // r8d
  _WORD *v151; // rcx
  __int64 result; // rax
  __int128 v153; // [rsp+60h] [rbp-21h] BYREF
  __int128 v154; // [rsp+70h] [rbp-11h] BYREF
  char v155; // [rsp+80h] [rbp-1h] BYREF
  __int16 v156; // [rsp+81h] [rbp+0h]
  char v157; // [rsp+83h] [rbp+2h]
  __int128 v158; // [rsp+84h] [rbp+3h]
  int v159; // [rsp+94h] [rbp+13h]
  __int128 v160; // [rsp+98h] [rbp+17h]

  v5 = *a1;
  v6 = a2;
  switch ( a2 )
  {
    case 2u:
      sqlite3FinishCoding(a5, &_ImageBase);
      break;
    case 0xF1u:
LABEL_385:
      *(_DWORD *)(v5 + 32) = 0;
      break;
    case 0x83u:
LABEL_384:
      *(_QWORD *)(v5 + 32) = 0;
      *(_DWORD *)(v5 + 40) = 0;
      break;
    case 0x89u:
      v46 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
      *(_QWORD *)(v5 - 40) = v46;
LABEL_154:
      sqlite3ExprListSetSortOrder(v46, *(unsigned int *)(v5 - 16), *(unsigned int *)(v5 + 8));
      break;
    default:
      switch ( a2 )
      {
        case 0u:
          if ( !a5[42] )
            *((_BYTE *)a5 + 307) = 1;
          goto LABEL_387;
        case 1u:
          if ( !a5[42] )
            *((_BYTE *)a5 + 307) = 2;
          goto LABEL_387;
        case 3u:
          sqlite3BeginTransaction(a5, *(unsigned int *)(v5 - 16));
          goto LABEL_387;
        case 4u:
          *(_DWORD *)(v5 + 32) = 7;
          goto LABEL_387;
        case 5u:
        case 6u:
        case 7u:
        case 0x59u:
        case 0x5Bu:
        case 0x106u:
        case 0x144u:
          *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
          goto LABEL_387;
        case 8u:
        case 9u:
          sqlite3EndTransaction(a5, *(unsigned __int16 *)(v5 - 22));
          goto LABEL_387;
        case 0xAu:
          sqlite3Savepoint(a5, 0, v5 + 8);
          goto LABEL_387;
        case 0xBu:
          sqlite3Savepoint(a5, 1, v5 + 8);
          goto LABEL_387;
        case 0xCu:
          sqlite3Savepoint(a5, 2, v5 + 8);
          goto LABEL_387;
        case 0xDu:
          sqlite3StartTable(a5, v5 - 16, v5 + 8, *(_DWORD *)(v5 - 88), 0, 0, *(_DWORD *)(v5 - 40));
          goto LABEL_387;
        case 0xEu:
          ++*((_BYTE *)a5 + 36);
          v7 = *a5;
          ++*(_DWORD *)(v7 + 416);
          *(_WORD *)(v7 + 420) = 0;
          goto LABEL_387;
        case 0xFu:
        case 0x12u:
        case 0x15u:
        case 0x2Fu:
        case 0x31u:
        case 0x3Eu:
        case 0x48u:
        case 0x51u:
        case 0x64u:
        case 0xF6u:
          goto LABEL_385;
        case 0x10u:
          *(_DWORD *)(v5 - 40) = 1;
          goto LABEL_387;
        case 0x11u:
          *(_DWORD *)(v5 + 8) = *(_BYTE *)(*a5 + 197LL) == 0;
          goto LABEL_387;
        case 0x13u:
          sqlite3EndTable((_DWORD)a5, v5 - 40, v5 - 16, *(_DWORD *)(v5 + 8), 0);
          goto LABEL_387;
        case 0x14u:
          sqlite3EndTable((_DWORD)a5, 0, 0, 0, *(_QWORD *)(v5 + 8));
          sqlite3SelectDeleteGeneric(*a5, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x16u:
          *(_DWORD *)(v5 - 40) |= *(_DWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x17u:
          if ( *(_DWORD *)(v5 + 16) != 5 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "rowid", 5) )
          {
            v8 = *(const char **)(v5 + 8);
            v9 = *(_DWORD *)(v5 + 16);
            *(_DWORD *)(v5 - 16) = 0;
            sqlite3ErrorMsg(a5, "unknown table option: %.*s", v9, v8);
          }
          else
          {
            *(_DWORD *)(v5 - 16) = 640;
          }
          goto LABEL_387;
        case 0x18u:
          if ( *(_DWORD *)(v5 + 16) != 6 || (unsigned int)sqlite3_strnicmp(*(_QWORD *)(v5 + 8), "strict", 6) )
          {
            v10 = 0;
            sqlite3ErrorMsg(a5, "unknown table option: %.*s", *(_DWORD *)(v5 + 16), *(const char **)(v5 + 8));
          }
          else
          {
            v10 = 0x10000;
          }
          *(_DWORD *)(v5 + 8) = v10;
          goto LABEL_387;
        case 0x19u:
          v153 = *(_OWORD *)(v5 + 8);
          v154 = *(_OWORD *)(v5 - 16);
          sqlite3AddColumn(a5, &v154, &v153);
          goto LABEL_387;
        case 0x1Au:
        case 0x41u:
        case 0x6Au:
          *(_DWORD *)(v5 + 40) = 0;
          *(_QWORD *)(v5 + 32) = 0;
          goto LABEL_387;
        case 0x1Bu:
          *(_DWORD *)(v5 - 56) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 64);
          goto LABEL_387;
        case 0x1Cu:
          *(_DWORD *)(v5 - 104) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 112);
          goto LABEL_387;
        case 0x1Du:
          *(_DWORD *)(v5 - 8) = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_DWORD *)(v5 - 16);
          goto LABEL_387;
        case 0x1Eu:
          *(_QWORD *)(v5 + 32) = *a4;
          goto LABEL_387;
        case 0x1Fu:
          *(_OWORD *)(v5 + 32) = *(_OWORD *)a4;
          goto LABEL_387;
        case 0x20u:
        case 0x43u:
          *((_OWORD *)a5 + 7) = *(_OWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x21u:
          sqlite3AddDefaultValue(
            a5,
            *(_QWORD *)(v5 + 8),
            *(_QWORD *)(v5 - 16),
            *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
          goto LABEL_387;
        case 0x22u:
          sqlite3AddDefaultValue(a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40) + 1LL, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x23u:
          sqlite3AddDefaultValue(
            a5,
            *(_QWORD *)(v5 + 8),
            *(_QWORD *)(v5 - 40),
            *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
          goto LABEL_387;
        case 0x24u:
          v11 = sqlite3PExpr(a5, 174, *(_QWORD *)(v5 + 8), 0);
          sqlite3AddDefaultValue(a5, v11, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16) + *(unsigned int *)(v5 - 8));
          goto LABEL_387;
        case 0x25u:
          v154 = *(_OWORD *)(v5 + 8);
          v12 = tokenExpr(a5, 117, &v154);
          v13 = v12;
          if ( v12 )
            sqlite3ExprIdToTrueFalse(v12);
          sqlite3AddDefaultValue(a5, v13, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 + 8) + *(unsigned int *)(v5 + 16));
          goto LABEL_387;
        case 0x26u:
          sqlite3AddNotNull(a5, *(unsigned int *)(v5 + 8));
          goto LABEL_387;
        case 0x27u:
          sqlite3AddPrimaryKey((_DWORD)a5, 0, *(_DWORD *)(v5 - 16), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40));
          goto LABEL_387;
        case 0x28u:
          sqlite3CreateIndex(a5, 0, 0, 0, 0, *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
          goto LABEL_387;
        case 0x29u:
          sqlite3AddCheckConstraint(a5, *(_QWORD *)(v5 - 16), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x2Au:
          sqlite3CreateForeignKey((_DWORD)a5, 0, v5 - 40, *(_QWORD *)(v5 - 16), *(_DWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x2Bu:
          goto LABEL_72;
        case 0x2Cu:
          sqlite3AddCollateType(a5, v5 + 8);
          goto LABEL_387;
        case 0x2Du:
          sqlite3AddGenerated(a5, *(_QWORD *)(v5 - 16), 0);
          goto LABEL_387;
        case 0x2Eu:
          sqlite3AddGenerated(a5, *(_QWORD *)(v5 - 40), v5 + 8);
          goto LABEL_387;
        case 0x30u:
        case 0x62u:
        case 0x7Cu:
        case 0x8Bu:
        case 0x119u:
          *(_DWORD *)(v5 + 8) = 1;
          goto LABEL_387;
        case 0x32u:
          *(_DWORD *)(v5 - 16) = *(_DWORD *)(v5 + 8) | *(_DWORD *)(v5 - 16) & ~*(_DWORD *)(v5 + 12);
          goto LABEL_387;
        case 0x33u:
          goto LABEL_165;
        case 0x34u:
          *(_QWORD *)(v5 - 40) = 0;
          goto LABEL_387;
        case 0x35u:
          *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
          *(_DWORD *)(v5 - 36) = 255;
          goto LABEL_387;
        case 0x36u:
          *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8) << 8;
          *(_DWORD *)(v5 - 36) = 65280;
          goto LABEL_387;
        case 0x37u:
          *(_DWORD *)(v5 - 16) = 8;
          goto LABEL_387;
        case 0x38u:
          *(_DWORD *)(v5 - 16) = 9;
          goto LABEL_387;
        case 0x39u:
          *(_DWORD *)(v5 + 8) = 10;
          goto LABEL_387;
        case 0x3Au:
          *(_DWORD *)(v5 + 8) = 7;
          goto LABEL_387;
        case 0x3Bu:
        case 0x40u:
        case 0x8Du:
          *(_DWORD *)(v5 - 16) = 0;
          goto LABEL_387;
        case 0x3Cu:
          *(_DWORD *)(v5 - 40) = 0;
          goto LABEL_387;
        case 0x3Du:
        case 0x4Cu:
        case 0xADu:
          *(_DWORD *)(v5 - 16) = *(_DWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x3Fu:
        case 0x50u:
        case 0x8Eu:
        case 0xDBu:
        case 0xDEu:
        case 0xF7u:
          *(_DWORD *)(v5 - 16) = 1;
          goto LABEL_387;
        case 0x42u:
          *((_DWORD *)a5 + 30) = 0;
          goto LABEL_387;
        case 0x44u:
          sqlite3AddPrimaryKey((_DWORD)a5, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 - 40), 0);
          goto LABEL_387;
        case 0x45u:
          sqlite3CreateIndex(a5, 0, 0, 0, *(_DWORD **)(v5 - 40), *(_DWORD *)(v5 + 8), 0, 0, 0, 0, 1u);
          goto LABEL_387;
        case 0x46u:
          sqlite3AddCheckConstraint(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0x47u:
          sqlite3CreateForeignKey(
            (_DWORD)a5,
            *(_QWORD *)(v5 - 136),
            v5 - 64,
            *(_QWORD *)(v5 - 40),
            *(_DWORD *)(v5 - 16));
LABEL_72:
          sqlite3DeferForeignKey(a5, *(unsigned int *)(v5 + 8));
          goto LABEL_387;
        case 0x49u:
        case 0x4Bu:
          *(_DWORD *)(v5 + 32) = 11;
          goto LABEL_387;
        case 0x4Au:
          *(_DWORD *)(v5 - 40) = *(_DWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x4Du:
          *(_DWORD *)(v5 + 8) = 4;
          goto LABEL_387;
        case 0x4Eu:
        case 0xAEu:
          *(_DWORD *)(v5 + 8) = 5;
          goto LABEL_387;
        case 0x4Fu:
          sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), 0, *(unsigned int *)(v5 - 16));
          goto LABEL_387;
        case 0x52u:
          sqlite3CreateView(
            (_DWORD)a5,
            v5 - 184,
            v5 - 88,
            v5 - 64,
            *(_QWORD *)(v5 - 40),
            *(_QWORD *)(v5 + 8),
            *(_DWORD *)(v5 - 160),
            *(_DWORD *)(v5 - 112));
          goto LABEL_387;
        case 0x53u:
          sqlite3DropTable(a5, *(_QWORD *)(v5 + 8), 1, *(unsigned int *)(v5 - 16));
          goto LABEL_387;
        case 0x54u:
          v14 = *(_QWORD *)(v5 + 8);
          v155 = 9;
          v156 = 0;
          v157 = 0;
          v158 = 0;
          v159 = 0;
          v160 = 0;
          sqlite3Select(a5, v14, &v155);
          sqlite3SelectDeleteGeneric(*a5, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x55u:
          *(_QWORD *)(v5 - 40) = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0x56u:
          *(_QWORD *)(v5 - 64) = attachWithToSelect(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0x57u:
          v15 = *(_QWORD *)(v5 + 8);
          if ( v15 )
            parserDoubleLinkSelect(a5, v15);
          goto LABEL_387;
        case 0x58u:
          v16 = *(_QWORD *)(v5 + 8);
          v17 = *(_QWORD *)(v5 - 40);
          if ( v16
            && (!*(_QWORD *)(v16 + 80)
             || (v18 = *(_QWORD *)(v5 + 8),
                 v154 = 0,
                 parserDoubleLinkSelect(a5, v18),
                 v19 = sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v154, v16, 0),
                 (v16 = sqlite3SelectNew((_DWORD)a5, 0, v19, 0, 0, 0, 0, 0, 0)) != 0)) )
          {
            *(_BYTE *)v16 = *(_BYTE *)(v5 - 16);
            *(_QWORD *)(v16 + 80) = v17;
            if ( v17 )
              *(_DWORD *)(v17 + 4) &= ~0x400u;
            *(_DWORD *)(v16 + 4) &= ~0x400u;
            if ( *(_DWORD *)(v5 - 16) != 135 )
              *((_BYTE *)a5 + 34) = 1;
          }
          else
          {
            sqlite3SelectDeleteGeneric(*a5, v17);
          }
          goto LABEL_93;
        case 0x5Au:
          *(_DWORD *)(v5 - 16) = 135;
          goto LABEL_387;
        case 0x5Cu:
          *(_QWORD *)(v5 - 184) = sqlite3SelectNew(
                                    (_DWORD)a5,
                                    *(_QWORD *)(v5 - 136),
                                    *(_QWORD *)(v5 - 112),
                                    *(_QWORD *)(v5 - 88),
                                    *(_QWORD *)(v5 - 64),
                                    *(_QWORD *)(v5 - 40),
                                    *(_QWORD *)(v5 - 16),
                                    *(_DWORD *)(v5 - 160),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x5Du:
          v20 = sqlite3SelectNew(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 160),
                  *(_QWORD *)(v5 - 136),
                  *(_QWORD *)(v5 - 112),
                  *(_QWORD *)(v5 - 88),
                  *(_QWORD *)(v5 - 64),
                  *(_QWORD *)(v5 - 16),
                  *(_DWORD *)(v5 - 184),
                  *(_QWORD *)(v5 + 8));
          v21 = *(_QWORD *)(v5 - 40);
          *(_QWORD *)(v5 - 208) = v20;
          if ( v20 )
            *(_QWORD *)(v20 + 120) = v21;
          else
            sqlite3WindowListDelete(*a5, v21);
          goto LABEL_387;
        case 0x5Eu:
          *(_QWORD *)(v5 - 64) = sqlite3SelectNew((_DWORD)a5, *(_QWORD *)(v5 - 16), 0, 0, 0, 0, 0, 512, 0);
          goto LABEL_387;
        case 0x5Fu:
          sqlite3MultiValuesEnd(a5, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x60u:
        case 0x61u:
          *(_QWORD *)(v5 - 88) = sqlite3MultiValues(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0x63u:
        case 0xF0u:
        case 0x11Au:
          *(_DWORD *)(v5 + 8) = 2;
          goto LABEL_387;
        case 0x65u:
        case 0x6Bu:
        case 0x6Eu:
        case 0x86u:
        case 0x90u:
        case 0x92u:
        case 0x94u:
        case 0x99u:
        case 0x9Bu:
        case 0xA6u:
        case 0xAFu:
        case 0xE8u:
        case 0xE9u:
        case 0xEAu:
        case 0xEDu:
        case 0xF2u:
        case 0xFCu:
        case 0x10Cu:
        case 0x11Fu:
          *(_QWORD *)(v5 + 32) = 0;
          goto LABEL_387;
        case 0x66u:
          v22 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
          v23 = *(_DWORD *)(v5 + 16) == 0;
          *(_QWORD *)(v5 - 88) = v22;
          if ( !v23 )
            sqlite3ExprListSetName(a5, v22, v5 + 8, 1);
          sqlite3ExprListSetSpan(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0x67u:
          v24 = sqlite3Expr(*a5, 180, 0);
          sqlite3ExprSetErrorOffset(v24, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
          *(_QWORD *)(v5 - 40) = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 40), v24);
          goto LABEL_387;
        case 0x68u:
          v25 = sqlite3PExpr(a5, 180, 0, 0);
          sqlite3ExprSetErrorOffset(v25, (unsigned int)(*(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86)));
          v154 = *(_OWORD *)(v5 - 40);
          v26 = tokenExpr(a5, 59, &v154);
          v27 = sqlite3PExpr(a5, 141, v26, v25);
          *(_QWORD *)(v5 - 88) = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), v27);
          goto LABEL_387;
        case 0x69u:
        case 0x75u:
        case 0x102u:
        case 0x103u:
          *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x6Cu:
          *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
          sqlite3SrcListShiftJoinType(a5);
          goto LABEL_387;
        case 0x6Du:
          v28 = *(int **)(v5 - 16);
          if ( v28 )
          {
            v29 = *v28;
            if ( (int)v29 > 0 )
              LOBYTE(v28[26 * v29 - 9]) = *(_BYTE *)(v5 + 8);
          }
          goto LABEL_387;
        case 0x6Fu:
          *(_QWORD *)(v5 - 88) = sqlite3SrcListAppendFromTerm(
                                   (_DWORD)a5,
                                   *(_QWORD *)(v5 - 88),
                                   (int)v5 - 64,
                                   (int)v5 - 40,
                                   v5 - 16,
                                   0,
                                   v5 + 8);
          goto LABEL_387;
        case 0x70u:
          v30 = sqlite3SrcListAppendFromTerm(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 112),
                  (int)v5 - 88,
                  (int)v5 - 64,
                  v5 - 40,
                  0,
                  v5 + 8);
          *(_QWORD *)(v5 - 112) = v30;
          sqlite3SrcListIndexedBy(a5, v30, v5 - 16);
          goto LABEL_387;
        case 0x71u:
          v31 = sqlite3SrcListAppendFromTerm(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 160),
                  (int)v5 - 136,
                  (int)v5 - 112,
                  v5 - 16,
                  0,
                  v5 + 8);
          *(_QWORD *)(v5 - 160) = v31;
          sqlite3SrcListFuncArgs(a5, v31);
          goto LABEL_387;
        case 0x72u:
          *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendFromTerm(
                                    (_DWORD)a5,
                                    *(_QWORD *)(v5 - 112),
                                    0,
                                    0,
                                    v5 - 16,
                                    *(_QWORD *)(v5 - 64),
                                    v5 + 8);
          goto LABEL_387;
        case 0x73u:
          v32 = *(_QWORD *)(v5 - 112);
          if ( v32 || *(_DWORD *)(v5 - 8) || *(_QWORD *)(v5 + 8) || *(_QWORD *)(v5 + 16) )
          {
            v33 = *(_DWORD **)(v5 - 64);
            if ( v33 && *v33 == 1 )
            {
              v34 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, v32, 0, 0, v5 - 16, 0, v5 + 8);
              *(_QWORD *)(v5 - 112) = v34;
              if ( v34 )
              {
                v35 = *(_QWORD *)(v5 - 64);
                v36 = &v34[26 * *v34];
                *((_QWORD *)v36 - 10) = *(_QWORD *)(v35 + 24);
                *((_QWORD *)v36 - 11) = *(_QWORD *)(v35 + 16);
                v37 = *(_QWORD *)(v35 + 48);
                *((_QWORD *)v36 - 7) = v37;
                if ( v37 && (*(_DWORD *)(v37 + 4) & 0x800) != 0 )
                  *(v36 - 8) |= 0x2000u;
                if ( (*(_BYTE *)(v35 + 72) & 4) != 0 )
                {
                  *((_QWORD *)v36 - 1) = *(_QWORD *)(v35 + 96);
                  *(_DWORD *)(v35 + 72) &= ~4u;
                  *(_QWORD *)(v35 + 96) = 0;
                  *(v36 - 8) |= 4u;
                }
                *(_QWORD *)(v35 + 16) = 0;
                *(_QWORD *)(v35 + 24) = 0;
                *(_QWORD *)(v35 + 48) = 0;
              }
              sqlite3SrcListDelete(*a5, *(_QWORD *)(v5 - 64));
            }
            else
            {
              sqlite3SrcListShiftJoinType(a5);
              v38 = sqlite3SelectNew((_DWORD)a5, 0, *(_QWORD *)(v5 - 64), 0, 0, 0, 0, 2048, 0);
              *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendFromTerm(
                                        (_DWORD)a5,
                                        *(_QWORD *)(v5 - 112),
                                        0,
                                        0,
                                        v5 - 16,
                                        v38,
                                        v5 + 8);
            }
          }
          else
          {
            *(_QWORD *)(v5 - 112) = *(_QWORD *)(v5 - 64);
          }
          goto LABEL_387;
        case 0x74u:
          goto LABEL_384;
        case 0x76u:
          v39 = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
          v40 = v39;
          if ( *((_BYTE *)a5 + 308) >= 2u && v39 )
            sqlite3RenameTokenMap(a5, *(_QWORD *)(v39 + 24), v5 + 8);
          goto LABEL_135;
        case 0x77u:
          v41 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
          v16 = v41;
          if ( *((_BYTE *)a5 + 308) >= 2u && v41 )
          {
            sqlite3RenameTokenMap(a5, *(_QWORD *)(v41 + 24), v5 + 8);
            *(_QWORD *)(v5 - 40) = v16;
          }
          else
          {
LABEL_93:
            *(_QWORD *)(v5 - 40) = v16;
          }
          goto LABEL_387;
        case 0x78u:
          *(_QWORD *)(v5 + 8) = sqlite3SrcListAppend(a5, 0, v5 + 8, 0);
          goto LABEL_387;
        case 0x79u:
          *(_QWORD *)(v5 - 40) = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 + 8);
          goto LABEL_387;
        case 0x7Au:
          v42 = a5;
          v43 = sqlite3SrcListAppend(a5, 0, v5 - 88, v5 - 40);
          v44 = v43;
          *(_QWORD *)(v5 - 88) = v43;
          goto LABEL_142;
        case 0x7Bu:
          v42 = a5;
          v43 = sqlite3SrcListAppend(a5, 0, v5 - 40, 0);
          v44 = v43;
          *(_QWORD *)(v5 - 40) = v43;
LABEL_142:
          if ( v43 )
            *(_QWORD *)(v44 + 32) = sqlite3NameFromToken(*v42, v5 + 8);
          goto LABEL_387;
        case 0x7Du:
          *(_DWORD *)(v5 - 16) = sqlite3JoinType(a5, v5 - 16, 0, 0);
          goto LABEL_387;
        case 0x7Eu:
          *(_DWORD *)(v5 - 40) = sqlite3JoinType(a5, v5 - 40, v5 - 16, 0);
          goto LABEL_387;
        case 0x7Fu:
          *(_DWORD *)(v5 - 64) = sqlite3JoinType(a5, v5 - 64, v5 - 40, v5 - 16);
          goto LABEL_387;
        case 0x80u:
          *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
          *(_QWORD *)(v5 - 8) = 0;
          goto LABEL_387;
        case 0x81u:
          v45 = *(_QWORD *)(v5 - 16);
          *(_QWORD *)(v5 - 64) = 0;
          *(_QWORD *)(v5 - 56) = v45;
          goto LABEL_387;
        case 0x82u:
          *(_QWORD *)(v5 + 32) = 0;
          *(_QWORD *)(v5 + 40) = 0;
          goto LABEL_387;
        case 0x84u:
          *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x85u:
          *(_DWORD *)(v5 - 8) = 1;
          *(_QWORD *)(v5 - 16) = 0;
          goto LABEL_387;
        case 0x87u:
        case 0x91u:
          goto LABEL_351;
        case 0x88u:
          v46 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
          *(_QWORD *)(v5 - 88) = v46;
          goto LABEL_154;
        case 0x8Au:
        case 0xDAu:
        case 0xDDu:
          *(_DWORD *)(v5 + 8) = 0;
          goto LABEL_387;
        case 0x8Cu:
        case 0x8Fu:
          *(_DWORD *)(v5 + 32) = -1;
          goto LABEL_387;
        case 0x93u:
        case 0x9Au:
        case 0x9Cu:
        case 0xE7u:
        case 0xFBu:
        case 0x10Du:
        case 0x120u:
        case 0x150u:
          goto LABEL_375;
        case 0x95u:
          *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, 148, *(_QWORD *)(v5 + 8), 0);
          goto LABEL_387;
        case 0x96u:
          v47 = *(_QWORD *)(v5 + 8);
          v48 = *(_QWORD *)(v5 - 40);
          goto LABEL_160;
        case 0x97u:
          v47 = *(_QWORD *)(v5 - 40);
          v48 = *(_QWORD *)(v5 + 8);
LABEL_160:
          v49 = sqlite3PExpr(a5, 148, v48, v47);
          goto LABEL_161;
        case 0x98u:
          sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 40), v5 - 16);
          sqlite3DeleteFrom((_DWORD)a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8), 0, 0);
          goto LABEL_387;
        case 0x9Du:
          sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
LABEL_165:
          *(_QWORD *)(v5 - 16) = 0;
          goto LABEL_387;
        case 0x9Eu:
          sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
          v49 = *(_QWORD *)(v5 - 40);
          goto LABEL_161;
        case 0x9Fu:
          sqlite3SrcListIndexedBy(a5, *(_QWORD *)(v5 - 112), v5 - 88);
          sqlite3ExprListCheckLength(a5, *(_QWORD *)(v5 - 40), "set list");
          v50 = *(int **)(v5 - 16);
          if ( v50 )
          {
            if ( *v50 > 1 )
            {
              v153 = 0;
              v51 = sqlite3SelectNew((_DWORD)a5, 0, (_DWORD)v50, 0, 0, 0, 0, 2048, 0);
              DWORD2(v153) = 0;
              *(_QWORD *)&v153 = 0;
              v50 = (int *)sqlite3SrcListAppendFromTerm((_DWORD)a5, 0, 0, 0, (__int64)&v153, v51, 0);
            }
            *(_QWORD *)(v5 - 112) = sqlite3SrcListAppendList(a5, *(_QWORD *)(v5 - 112), v50);
          }
          sqlite3Update(
            (_DWORD)a5,
            *(_QWORD *)(v5 - 112),
            *(_QWORD *)(v5 - 40),
            *(_QWORD *)(v5 + 8),
            *(_DWORD *)(v5 - 136),
            0,
            0,
            0);
          goto LABEL_387;
        case 0xA0u:
          v52 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 88) = v52;
          sqlite3ExprListSetName(a5, v52, v5 - 40, 1);
          goto LABEL_387;
        case 0xA1u:
          *(_QWORD *)(v5 - 136) = sqlite3ExprListAppendVector(
                                    a5,
                                    *(_QWORD *)(v5 - 136),
                                    *(_QWORD *)(v5 - 64),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xA2u:
          v53 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
          sqlite3ExprListSetName(a5, v53, v5 - 40, 1);
          *(_QWORD *)(v5 - 40) = v53;
          goto LABEL_387;
        case 0xA3u:
          *(_QWORD *)(v5 - 88) = sqlite3ExprListAppendVector(a5, 0, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xA4u:
          sqlite3Insert(
            (_DWORD)a5,
            *(_QWORD *)(v5 - 64),
            *(_QWORD *)(v5 - 16),
            *(_QWORD *)(v5 - 40),
            *(_DWORD *)(v5 - 112),
            *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xA5u:
          sqlite3Insert((_DWORD)a5, *(_QWORD *)(v5 - 88), 0, *(_QWORD *)(v5 - 64), *(_DWORD *)(v5 - 136), 0);
          goto LABEL_387;
        case 0xA7u:
          *(_QWORD *)(v5 - 16) = 0;
          goto LABEL_179;
        case 0xA8u:
          *(_QWORD *)(v5 - 256) = sqlite3UpsertNew(
                                    *a5,
                                    *(_QWORD *)(v5 - 184),
                                    *(_QWORD *)(v5 - 136),
                                    *(_QWORD *)(v5 - 40),
                                    *(_QWORD *)(v5 - 16),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xA9u:
          *(_QWORD *)(v5 - 184) = sqlite3UpsertNew(
                                    *a5,
                                    *(_QWORD *)(v5 - 112),
                                    *(_QWORD *)(v5 - 64),
                                    0,
                                    0,
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xAAu:
          *(_QWORD *)(v5 - 88) = sqlite3UpsertNew(*a5, 0, 0, 0, 0, 0);
          goto LABEL_387;
        case 0xABu:
          *(_QWORD *)(v5 - 160) = sqlite3UpsertNew(*a5, 0, 0, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
          goto LABEL_387;
        case 0xACu:
LABEL_179:
          sqlite3AddReturning(a5, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xB0u:
        case 0xB3u:
        case 0xEEu:
        case 0xF3u:
          *(_QWORD *)(v5 - 40) = *(_QWORD *)(v5 - 16);
          goto LABEL_387;
        case 0xB1u:
          *(_QWORD *)(v5 - 40) = sqlite3IdListAppend(a5, *(_QWORD *)(v5 - 40), v5 + 8);
          goto LABEL_387;
        case 0xB2u:
          *(_QWORD *)(v5 + 8) = sqlite3IdListAppend(a5, 0, v5 + 8);
          goto LABEL_387;
        case 0xB4u:
          v154 = *(_OWORD *)(v5 + 8);
          *(_QWORD *)(v5 + 8) = tokenExpr(a5, 59, &v154);
          goto LABEL_387;
        case 0xB5u:
          v154 = *(_OWORD *)(v5 - 40);
          v54 = tokenExpr(a5, 59, &v154);
          v154 = *(_OWORD *)(v5 + 8);
          v55 = tokenExpr(a5, 59, &v154);
          *(_QWORD *)(v5 - 40) = sqlite3PExpr(a5, 141, v54, v55);
          goto LABEL_387;
        case 0xB6u:
          v154 = *(_OWORD *)(v5 - 88);
          v56 = tokenExpr(a5, 59, &v154);
          v154 = *(_OWORD *)(v5 - 40);
          v57 = tokenExpr(a5, 59, &v154);
          v154 = *(_OWORD *)(v5 + 8);
          v58 = tokenExpr(a5, 59, &v154);
          v59 = sqlite3PExpr(a5, 141, v57, v58);
          if ( *((_BYTE *)a5 + 308) >= 2u )
            sqlite3RenameTokenRemap(a5, 0, v56, v60);
          *(_QWORD *)(v5 - 88) = sqlite3PExpr(a5, 141, v56, v59);
          goto LABEL_387;
        case 0xB7u:
        case 0xB8u:
          v61 = *(unsigned __int16 *)(v5 + 2);
          v154 = *(_OWORD *)(v5 + 8);
          *(_QWORD *)(v5 + 8) = tokenExpr(a5, v61, &v154);
          goto LABEL_387;
        case 0xB9u:
          v62 = sqlite3ExprAlloc(*a5, 155, v5 + 8, 1);
          if ( v62 )
            *(_DWORD *)(v62 + 52) = *(_DWORD *)(v5 + 8) - *((_DWORD *)a5 + 86);
          *(_QWORD *)(v5 + 8) = v62;
          goto LABEL_387;
        case 0xBAu:
          v63 = *(_BYTE **)(v5 + 8);
          if ( *v63 == 35 && (*((_BYTE *)&qword_1800ADE90 + (unsigned __int8)v63[1]) & 4) != 0 )
          {
            v23 = *((_BYTE *)a5 + 30) == 0;
            v153 = *(_OWORD *)(v5 + 8);
            if ( v23 )
            {
              sqlite3ErrorMsg(a5, "near \"%T\": syntax error", &v153);
              *(_QWORD *)(v5 + 8) = 0;
            }
            else
            {
              v64 = sqlite3PExpr(a5, 176, 0, 0);
              *(_QWORD *)(v5 + 8) = v64;
              if ( v64 )
                sqlite3GetInt32(v153 + 1, v64 + 44);
            }
          }
          else
          {
            v65 = *(_DWORD *)(v5 + 16);
            v154 = *(_OWORD *)(v5 + 8);
            v66 = tokenExpr(a5, 156, &v154);
            *(_QWORD *)(v5 + 8) = v66;
            sqlite3ExprAssignVarNumber(a5, v66, v65);
          }
          goto LABEL_387;
        case 0xBBu:
          *(_QWORD *)(v5 - 40) = sqlite3ExprAddCollateToken(a5, *(_QWORD *)(v5 - 40), v5 + 8, 1);
          goto LABEL_387;
        case 0xBCu:
          v67 = sqlite3ExprAlloc(*a5, 36, v5 - 16, 1);
          v68 = *(_QWORD *)(v5 - 64);
          *(_QWORD *)(v5 - 112) = v67;
          sqlite3ExprAttachSubtrees(*a5, v67, v68, 0);
          goto LABEL_387;
        case 0xBDu:
          *(_QWORD *)(v5 - 88) = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 16), v5 - 88, *(unsigned int *)(v5 - 40));
          goto LABEL_387;
        case 0xBEu:
          v69 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 88), v5 - 160, *(unsigned int *)(v5 - 112));
          sqlite3ExprAddFunctionOrderBy(a5, v69, *(_QWORD *)(v5 - 16));
          *(_QWORD *)(v5 - 160) = v69;
          goto LABEL_387;
        case 0xBFu:
          v49 = sqlite3ExprFunction(a5, 0, v5 - 64, 0);
          goto LABEL_161;
        case 0xC0u:
          v70 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 40), v5 - 112, *(unsigned int *)(v5 - 64));
          sqlite3WindowAttach(a5, v70, *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 112) = v70;
          goto LABEL_387;
        case 0xC1u:
          v71 = sqlite3ExprFunction(a5, *(_QWORD *)(v5 - 112), v5 - 184, *(unsigned int *)(v5 - 136));
          sqlite3WindowAttach(a5, v71, *(_QWORD *)(v5 + 8));
          sqlite3ExprAddFunctionOrderBy(a5, v71, *(_QWORD *)(v5 - 40));
          *(_QWORD *)(v5 - 184) = v71;
          goto LABEL_387;
        case 0xC2u:
          v72 = sqlite3ExprFunction(a5, 0, v5 - 88, 0);
          sqlite3WindowAttach(a5, v72, *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 88) = v72;
          goto LABEL_387;
        case 0xC3u:
          *(_QWORD *)(v5 + 8) = sqlite3ExprFunction(a5, 0, v5 + 8, 0);
          goto LABEL_387;
        case 0xC4u:
          v73 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 - 16));
          v74 = sqlite3PExpr(a5, 177, 0, 0);
          *(_QWORD *)(v5 - 88) = v74;
          if ( v74 )
          {
            *(_QWORD *)(v74 + 32) = v73;
            if ( *(_DWORD *)v73 )
              *(_DWORD *)(*(_QWORD *)(v5 - 88) + 4LL) |= *(_DWORD *)(*(_QWORD *)(v73 + 8) + 4LL) & 0x400208;
          }
          else
          {
            sqlite3ExprListDeleteGeneric(*a5, v73);
          }
          goto LABEL_387;
        case 0xC5u:
          *(_QWORD *)(v5 - 40) = sqlite3ExprAnd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xC6u:
        case 0xC7u:
        case 0xC8u:
        case 0xC9u:
        case 0xCAu:
        case 0xCBu:
        case 0xCCu:
          *(_QWORD *)(v5 - 40) = sqlite3PExpr(
                                   a5,
                                   *(unsigned __int16 *)(v5 - 22),
                                   *(_QWORD *)(v5 - 40),
                                   *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xCDu:
          *(_OWORD *)(v5 - 16) = *(_OWORD *)(v5 + 8);
          *(_DWORD *)(v5 - 8) |= 0x80000000;
          goto LABEL_387;
        case 0xCEu:
          v75 = *(_DWORD *)(v5 - 8);
          v76 = *(_QWORD *)(v5 + 8);
          *(_DWORD *)(v5 - 8) = v75 & 0x7FFFFFFF;
          v77 = sqlite3ExprListAppend(a5, 0, v76);
          v78 = sqlite3ExprListAppend(a5, v77, *(_QWORD *)(v5 - 40));
          v79 = sqlite3ExprFunction(a5, v78, v5 - 16, 0);
          *(_QWORD *)(v5 - 40) = v79;
          if ( v75 < 0 )
          {
            v79 = sqlite3PExpr(a5, 19, v79, 0);
            *(_QWORD *)(v5 - 40) = v79;
          }
          goto LABEL_221;
        case 0xCFu:
          v80 = *(_DWORD *)(v5 - 56);
          v81 = *(_QWORD *)(v5 - 40);
          *(_DWORD *)(v5 - 56) = v80 & 0x7FFFFFFF;
          v82 = sqlite3ExprListAppend(a5, 0, v81);
          v83 = sqlite3ExprListAppend(a5, v82, *(_QWORD *)(v5 - 88));
          v84 = sqlite3ExprListAppend(a5, v83, *(_QWORD *)(v5 + 8));
          v79 = sqlite3ExprFunction(a5, v84, v5 - 64, 0);
          *(_QWORD *)(v5 - 88) = v79;
          if ( v80 < 0 )
          {
            v79 = sqlite3PExpr(a5, 19, v79, 0);
            *(_QWORD *)(v5 - 88) = v79;
          }
LABEL_221:
          if ( v79 )
            *(_DWORD *)(v79 + 4) |= 0x100u;
          goto LABEL_387;
        case 0xD0u:
          *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, *(unsigned __int16 *)(v5 + 2), *(_QWORD *)(v5 - 16), 0);
          goto LABEL_387;
        case 0xD1u:
          *(_QWORD *)(v5 - 40) = sqlite3PExpr(a5, 51, *(_QWORD *)(v5 - 40), 0);
          goto LABEL_387;
        case 0xD2u:
          v85 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 40) = v85;
          goto LABEL_228;
        case 0xD3u:
          v85 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 64), *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 64) = v85;
          v86 = 51;
          goto LABEL_229;
        case 0xD4u:
          v85 = sqlite3PExpr(a5, 45, *(_QWORD *)(v5 - 112), *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 112) = v85;
LABEL_228:
          v86 = 50;
          goto LABEL_229;
        case 0xD5u:
          v85 = sqlite3PExpr(a5, 171, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 88) = v85;
          v86 = 51;
LABEL_229:
          binaryToUnaryIfNull(a5, *(_QWORD *)(v5 + 8), v85, v86);
          goto LABEL_387;
        case 0xD6u:
        case 0xD7u:
          *(_QWORD *)(v5 - 16) = sqlite3PExpr(a5, *(unsigned __int16 *)(v5 - 22), *(_QWORD *)(v5 + 8), 0);
          goto LABEL_387;
        case 0xD8u:
          v87 = *(unsigned __int8 **)(v5 + 8);
          v88 = *(_BYTE *)(v5 - 22) + 67;
          if ( v87 && *v87 == 0xAD )
            *v87 = v88;
          else
            v87 = (unsigned __int8 *)sqlite3PExpr(a5, v88, *(_QWORD *)(v5 + 8), 0);
          *(_QWORD *)(v5 - 16) = v87;
          goto LABEL_387;
        case 0xD9u:
          v89 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
          v90 = sqlite3ExprListAppend(a5, v89, *(_QWORD *)(v5 + 8));
          *(_QWORD *)(v5 - 40) = sqlite3ExprFunction(a5, v90, v5 - 16, 0);
          goto LABEL_387;
        case 0xDCu:
          v91 = a5;
          v92 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
          v93 = sqlite3ExprListAppend(a5, v92, *(_QWORD *)(v5 + 8));
          v94 = sqlite3PExpr(a5, 48, *(_QWORD *)(v5 - 88), 0);
          *(_QWORD *)(v5 - 88) = v94;
          if ( v94 )
            *(_QWORD *)(v94 + 32) = v93;
          else
            sqlite3ExprListDeleteGeneric(*a5, v93);
          goto LABEL_244;
        case 0xDFu:
          v96 = *(_QWORD *)(v5 - 16);
          if ( v96 )
          {
            v99 = *(_QWORD *)(v96 + 8);
            if ( *(_DWORD *)v96 == 1
              && (unsigned int)exprIsConst(a5, *(_QWORD *)(v96 + 8), 1)
              && (v100 = (_QWORD *)(v5 - 88), **(_BYTE **)(v5 - 88) != 0xB1) )
            {
              *(_QWORD *)(*(_QWORD *)(v5 - 16) + 8LL) = 0;
              sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
              v101 = sqlite3PExpr(a5, 173, v99, 0);
              *v100 = sqlite3PExpr(a5, 53, *v100, v101);
            }
            else if ( **(_DWORD **)(v5 - 16) == 1 && *(_BYTE *)v99 == 0x8A )
            {
              v100 = (_QWORD *)(v5 - 88);
              v102 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
              *(_QWORD *)(v5 - 88) = v102;
              sqlite3PExprAddSelect(a5, v102, *(_QWORD *)(v99 + 32));
              *(_QWORD *)(v99 + 32) = 0;
              sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
            }
            else
            {
              v100 = (_QWORD *)(v5 - 88);
              v103 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
              *(_QWORD *)(v5 - 88) = v103;
              if ( v103 )
              {
                v104 = *(_QWORD *)(v103 + 16);
                if ( *(_BYTE *)v104 == 0xB1 )
                {
                  v105 = sqlite3ExprListToValues(a5, **(unsigned int **)(v104 + 32), *(_QWORD *)(v5 - 16));
                  v106 = v105;
                  if ( v105 )
                  {
                    parserDoubleLinkSelect(a5, v105);
                    sqlite3PExprAddSelect(a5, *v100, v106);
                  }
                }
                else
                {
                  *(_QWORD *)(v103 + 32) = *(_QWORD *)(v5 - 16);
                  sqlite3ExprSetHeightAndFlags(a5, *v100);
                }
              }
              else
              {
                sqlite3ExprListDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
              }
            }
            if ( *(_DWORD *)(v5 - 64) )
              *v100 = sqlite3PExpr(a5, 19, *v100, 0);
          }
          else
          {
            sqlite3ExprUnmapAndDelete(a5, *(_QWORD *)(v5 - 88));
            v97 = "true";
            if ( !*(_DWORD *)(v5 - 64) )
              v97 = "false";
            v98 = sqlite3Expr(*a5, 117, v97);
            *(_QWORD *)(v5 - 88) = v98;
            if ( v98 )
              sqlite3ExprIdToTrueFalse(v98);
          }
          goto LABEL_387;
        case 0xE0u:
          v107 = sqlite3PExpr(a5, 138, 0, 0);
          *(_QWORD *)(v5 - 40) = v107;
          goto LABEL_268;
        case 0xE1u:
          v91 = a5;
          v108 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
          v109 = *(_QWORD *)(v5 - 16);
          *(_QWORD *)(v5 - 88) = v108;
          sqlite3PExprAddSelect(a5, v108, v109);
          goto LABEL_244;
        case 0xE2u:
          v91 = a5;
          v110 = 0;
          v111 = sqlite3SrcListAppend(a5, 0, v5 - 40, v5 - 16);
          v112 = sqlite3SelectNew((_DWORD)a5, 0, v111, 0, 0, 0, 0, 0, 0);
          v113 = v112;
          if ( *(_QWORD *)(v5 + 8) )
          {
            if ( v112 )
              v110 = v111;
            sqlite3SrcListFuncArgs(a5, v110);
          }
          v114 = sqlite3PExpr(a5, 49, *(_QWORD *)(v5 - 88), 0);
          *(_QWORD *)(v5 - 88) = v114;
          sqlite3PExprAddSelect(a5, v114, v113);
LABEL_244:
          if ( !*(_DWORD *)(v5 - 64) )
            goto LABEL_387;
          v95 = sqlite3PExpr(v91, 19, *(_QWORD *)(v5 - 88), 0);
          goto LABEL_246;
        case 0xE3u:
          v107 = sqlite3PExpr(a5, 20, 0, 0);
          *(_QWORD *)(v5 - 64) = v107;
LABEL_268:
          sqlite3PExprAddSelect(a5, v107, *(_QWORD *)(v5 - 16));
          goto LABEL_387;
        case 0xE4u:
          v115 = sqlite3PExpr(a5, 157, *(_QWORD *)(v5 - 64), 0);
          v116 = *(_QWORD *)(v5 - 40);
          *(_QWORD *)(v5 - 88) = v115;
          if ( v115 )
          {
            v117 = *(_QWORD *)(v5 - 16);
            if ( v117 )
              v116 = sqlite3ExprListAppend(a5, v116, v117);
            *(_QWORD *)(*(_QWORD *)(v5 - 88) + 32LL) = v116;
            sqlite3ExprSetHeightAndFlags(a5, *(_QWORD *)(v5 - 88));
          }
          else
          {
            sqlite3ExprListDeleteGeneric(*a5, v116);
            sqlite3ExprDeleteGeneric(*a5, *(_QWORD *)(v5 - 16));
          }
          goto LABEL_387;
        case 0xE5u:
          v118 = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 88), *(_QWORD *)(v5 - 40));
          v119 = *(_QWORD *)(v5 + 8);
          *(_QWORD *)(v5 - 88) = v118;
          v95 = sqlite3ExprListAppend(a5, v118, v119);
          goto LABEL_246;
        case 0xE6u:
          v120 = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 - 40));
          v121 = *(_QWORD *)(v5 + 8);
          *(_QWORD *)(v5 - 64) = v120;
          v49 = sqlite3ExprListAppend(a5, v120, v121);
          goto LABEL_161;
        case 0xEBu:
          *(_QWORD *)(v5 - 40) = sqlite3ExprListAppend(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xECu:
          *(_QWORD *)(v5 + 8) = sqlite3ExprListAppend(a5, 0, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xEFu:
          v122 = *(_DWORD *)(v5 - 184);
          v123 = *(_QWORD *)(v5 + 8);
          v124 = *(_DWORD *)(v5 - 232);
          v125 = *(_DWORD **)(v5 - 40);
          v126 = sqlite3SrcListAppend(a5, 0, v5 - 88, 0);
          sqlite3CreateIndex(a5, v5 - 160, v5 - 136, v126, v125, v124, v5 - 256, v123, 0, v122, 0);
          if ( *((_BYTE *)a5 + 308) >= 2u )
          {
            v127 = (_QWORD *)a5[45];
            if ( v127 )
              sqlite3RenameTokenMap(a5, *v127, v5 - 88);
          }
          goto LABEL_387;
        case 0xF4u:
          v95 = parserAddExprIdListTerm(
                  (_DWORD)a5,
                  *(_QWORD *)(v5 - 88),
                  (int)v5 - 40,
                  *(_DWORD *)(v5 - 16),
                  *(_DWORD *)(v5 + 8));
          goto LABEL_246;
        case 0xF5u:
          *(_QWORD *)(v5 - 40) = parserAddExprIdListTerm(
                                   (_DWORD)a5,
                                   0,
                                   (int)v5 - 40,
                                   *(_DWORD *)(v5 - 16),
                                   *(_DWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xF8u:
          sqlite3DropIndex(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
          goto LABEL_387;
        case 0xF9u:
          sqlite3Vacuum(a5, 0, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xFAu:
          sqlite3Vacuum(a5, v5 - 16, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0xFDu:
          sqlite3Pragma((_DWORD)a5, v5 - 16, v5 + 8, 0, 0);
          goto LABEL_387;
        case 0xFEu:
          v128 = v5 + 8;
          v129 = v5 - 40;
          v130 = v5 - 64;
          goto LABEL_296;
        case 0xFFu:
          v128 = v5 - 16;
          v129 = v5 - 64;
          v130 = v5 - 88;
LABEL_296:
          sqlite3Pragma((_DWORD)a5, v130, v129, v128, 0);
          goto LABEL_387;
        case 0x100u:
          sqlite3Pragma((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, 1);
          goto LABEL_387;
        case 0x101u:
          sqlite3Pragma((_DWORD)a5, v5 - 88, v5 - 64, v5 - 16, 1);
          goto LABEL_387;
        case 0x104u:
          v131 = *(_QWORD *)(v5 - 16);
          v132 = *(_DWORD *)(v5 + 8) + *(_DWORD *)(v5 + 16) - *(_QWORD *)(v5 - 64);
          *(_QWORD *)&v153 = *(_QWORD *)(v5 - 64);
          *((_QWORD *)&v153 + 1) = v132;
          sqlite3FinishTrigger(a5, v131, &v153);
          goto LABEL_387;
        case 0x105u:
          sqlite3BeginTrigger(
            a5,
            v5 - 160,
            v5 - 136,
            *(_DWORD *)(v5 - 112),
            *(_DWORD *)(v5 - 88),
            *(_QWORD *)(v5 - 80),
            *(_QWORD *)(v5 - 40),
            *(_QWORD *)(v5 + 8),
            *(_DWORD *)(v5 - 232),
            *(_DWORD *)(v5 - 184));
          v133 = 160;
          if ( *(_DWORD *)(v5 - 128) )
            v133 = 136;
          *(_OWORD *)(v5 - 232) = *(_OWORD *)(v5 - v133);
          goto LABEL_387;
        case 0x107u:
          *(_DWORD *)(v5 - 16) = 65;
          goto LABEL_387;
        case 0x108u:
          *(_DWORD *)(v5 + 32) = 33;
          goto LABEL_387;
        case 0x109u:
        case 0x10Au:
          *(_DWORD *)(v5 + 8) = *(unsigned __int16 *)(v5 + 2);
          *(_QWORD *)(v5 + 16) = 0;
          goto LABEL_387;
        case 0x10Bu:
          *(_QWORD *)(v5 - 32) = *(_QWORD *)(v5 + 8);
          *(_DWORD *)(v5 - 40) = 129;
          goto LABEL_387;
        case 0x10Eu:
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) + 80LL) = *(_QWORD *)(v5 - 16);
          *(_QWORD *)(*(_QWORD *)(v5 - 40) + 88LL) = *(_QWORD *)(v5 - 16);
          goto LABEL_387;
        case 0x10Fu:
          *(_QWORD *)(*(_QWORD *)(v5 - 16) + 88LL) = *(_QWORD *)(v5 - 16);
          goto LABEL_387;
        case 0x110u:
          *(_OWORD *)(v5 - 40) = *(_OWORD *)(v5 + 8);
          sqlite3ErrorMsg(
            a5,
            "qualified table names are not allowed on INSERT, UPDATE, and DELETE statements within triggers");
          goto LABEL_387;
        case 0x111u:
          sqlite3ErrorMsg(a5, "the INDEXED BY clause is not allowed on UPDATE or DELETE statements within triggers");
          goto LABEL_387;
        case 0x112u:
          sqlite3ErrorMsg(a5, "the NOT INDEXED clause is not allowed on UPDATE or DELETE statements within triggers");
          goto LABEL_387;
        case 0x113u:
          *(_QWORD *)(v5 - 184) = sqlite3TriggerUpdateStep(
                                    (_DWORD)a5,
                                    (int)v5 - 136,
                                    *(_QWORD *)(v5 - 40),
                                    *(_QWORD *)(v5 - 64),
                                    *(_QWORD *)(v5 - 16),
                                    *(_BYTE *)(v5 - 160),
                                    *(_QWORD *)(v5 - 184),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x114u:
          *(_QWORD *)(v5 - 160) = sqlite3TriggerInsertStep(
                                    (_DWORD)a5,
                                    (int)v5 - 88,
                                    *(_QWORD *)(v5 - 64),
                                    *(_QWORD *)(v5 - 40),
                                    *(_BYTE *)(v5 - 136),
                                    *(_QWORD *)(v5 - 16),
                                    *(_QWORD *)(v5 - 160),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x115u:
          *(_QWORD *)(v5 - 112) = sqlite3TriggerDeleteStep(
                                    (_DWORD)a5,
                                    (int)v5 - 64,
                                    *(_QWORD *)(v5 - 16),
                                    *(_QWORD *)(v5 - 112),
                                    *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x116u:
          *(_QWORD *)(v5 - 40) = sqlite3TriggerSelectStep(
                                   *a5,
                                   *(_QWORD *)(v5 - 16),
                                   *(_QWORD *)(v5 - 40),
                                   *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x117u:
          v134 = sqlite3PExpr(a5, 71, 0, 0);
          *(_QWORD *)(v5 - 64) = v134;
          if ( v134 )
            *(_BYTE *)(v134 + 1) = 4;
          goto LABEL_387;
        case 0x118u:
          v135 = sqlite3ExprAlloc(*a5, 71, v5 - 16, 1);
          *(_QWORD *)(v5 - 112) = v135;
          if ( v135 )
            *(_BYTE *)(v135 + 1) = *(_BYTE *)(v5 - 64);
          goto LABEL_387;
        case 0x11Bu:
          *(_DWORD *)(v5 + 8) = 3;
          goto LABEL_387;
        case 0x11Cu:
          sqlite3DropTrigger(a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 - 16));
          goto LABEL_387;
        case 0x11Du:
          codeAttach(
            (_DWORD)a5,
            24,
            (unsigned int)qword_1800A96B0,
            *(_QWORD *)(v5 - 64),
            *(_QWORD *)(v5 - 64),
            *(_QWORD *)(v5 - 16),
            *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x11Eu:
          codeAttach((_DWORD)a5, 25, (unsigned int)qword_1800A9590, *(_QWORD *)(v5 + 8), 0, 0, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x121u:
          sqlite3Reindex(a5, 0, 0);
          goto LABEL_387;
        case 0x122u:
          sqlite3Reindex(a5, v5 - 16, v5 + 8);
          goto LABEL_387;
        case 0x123u:
          sqlite3Analyze(a5, 0, 0);
          goto LABEL_387;
        case 0x124u:
          sqlite3Analyze(a5, v5 - 16, v5 + 8);
          goto LABEL_387;
        case 0x125u:
          sqlite3AlterRenameTable(a5, *(_QWORD *)(v5 - 64), v5 + 8);
          goto LABEL_387;
        case 0x126u:
          *(_DWORD *)(v5 - 8) = *((_DWORD *)a5 + 72) + *((_DWORD *)a5 + 74) - *(_DWORD *)(v5 - 16);
          sqlite3AlterFinishAddColumn();
          goto LABEL_387;
        case 0x127u:
          sqlite3AlterDropColumn(a5, *(_QWORD *)(v5 - 64), v5 + 8);
          goto LABEL_387;
        case 0x128u:
          ++*((_BYTE *)a5 + 36);
          v136 = *a5;
          ++*(_DWORD *)(v136 + 416);
          *(_WORD *)(v136 + 420) = 0;
          sqlite3AlterBeginAddColumn(a5, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x129u:
          sqlite3AlterRenameColumn(a5, *(_QWORD *)(v5 - 112), v5 - 40, v5 + 8);
          goto LABEL_387;
        case 0x12Au:
          sqlite3VtabFinishParse(a5, 0);
          goto LABEL_387;
        case 0x12Bu:
          sqlite3VtabFinishParse(a5, v5 + 8);
          goto LABEL_387;
        case 0x12Cu:
          sqlite3VtabBeginParse((_DWORD)a5, v5 - 64, v5 - 40, v5 + 8, *(_DWORD *)(v5 - 88));
          goto LABEL_387;
        case 0x12Du:
          addArgumentToVtab(a5, &_ImageBase);
          a5[48] = 0;
          *((_DWORD *)a5 + 98) = 0;
          goto LABEL_387;
        case 0x12Eu:
        case 0x12Fu:
        case 0x130u:
          sqlite3VtabArgExtend(a5, v5 + 8);
          goto LABEL_387;
        case 0x131u:
        case 0x132u:
          LOBYTE(a3) = 1;
          sqlite3WithPush(a5, *(_QWORD *)(v5 + 8), a3);
          goto LABEL_387;
        case 0x133u:
          *(_BYTE *)(v5 + 8) = 1;
          goto LABEL_387;
        case 0x134u:
          *(_BYTE *)(v5 - 16) = 0;
          goto LABEL_387;
        case 0x135u:
          *(_BYTE *)(v5 - 40) = 2;
          goto LABEL_387;
        case 0x136u:
          *(_QWORD *)(v5 - 112) = sqlite3CteNew(
                                    (_DWORD)a5,
                                    (int)v5 - 112,
                                    *(_QWORD *)(v5 - 88),
                                    *(_QWORD *)(v5 - 16),
                                    *(_BYTE *)(v5 - 64));
          goto LABEL_387;
        case 0x137u:
          *((_BYTE *)a5 + 39) = 1;
          goto LABEL_387;
        case 0x138u:
          *(_QWORD *)(v5 + 8) = sqlite3WithAdd(a5, 0, *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x139u:
          *(_QWORD *)(v5 - 40) = sqlite3WithAdd(a5, *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 + 8));
          goto LABEL_387;
        case 0x13Au:
          sqlite3WindowChain(a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40));
          *(_QWORD *)(*(_QWORD *)(v5 + 8) + 64LL) = *(_QWORD *)(v5 - 40);
LABEL_351:
          *(_QWORD *)(v5 - 40) = *(_QWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x13Bu:
          v137 = *(_QWORD **)(v5 - 16);
          if ( v137 )
            *v137 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 - 88), *(unsigned int *)(v5 - 80));
          goto LABEL_354;
        case 0x13Cu:
          v95 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), *(_QWORD *)(v5 - 40), *(_QWORD *)(v5 - 16), 0);
          goto LABEL_246;
        case 0x13Du:
          v138 = *(_QWORD *)(v5 - 40);
          v139 = (_QWORD *)(v5 - 112);
          goto LABEL_357;
        case 0x13Eu:
          v49 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), 0, *(_QWORD *)(v5 - 16), 0);
          goto LABEL_161;
        case 0x13Fu:
          v139 = (_QWORD *)(v5 - 88);
          LODWORD(v138) = 0;
LABEL_357:
          v140 = *(_QWORD *)(v5 - 16);
          goto LABEL_358;
        case 0x140u:
          LODWORD(v140) = 0;
          v139 = (_QWORD *)(v5 - 16);
          LODWORD(v138) = 0;
LABEL_358:
          v141 = sqlite3WindowAssemble((_DWORD)a5, *(_QWORD *)(v5 + 8), v138, v140, (__int64)v139);
          goto LABEL_359;
        case 0x141u:
          *(_QWORD *)(v5 + 32) = sqlite3WindowAlloc((_DWORD)a5, 0, 90, 0, 85, 0, 0);
          goto LABEL_387;
        case 0x142u:
          *(_QWORD *)(v5 - 40) = sqlite3WindowAlloc(
                                   (_DWORD)a5,
                                   *(_DWORD *)(v5 - 40),
                                   *(_DWORD *)(v5 - 16),
                                   *(_QWORD *)(v5 - 8),
                                   85,
                                   0,
                                   *(_BYTE *)(v5 + 8));
          goto LABEL_387;
        case 0x143u:
          *(_QWORD *)(v5 - 112) = sqlite3WindowAlloc(
                                    (_DWORD)a5,
                                    *(_DWORD *)(v5 - 112),
                                    *(_DWORD *)(v5 - 64),
                                    *(_QWORD *)(v5 - 56),
                                    *(_DWORD *)(v5 - 16),
                                    *(_QWORD *)(v5 - 8),
                                    *(_BYTE *)(v5 + 8));
          goto LABEL_387;
        case 0x146u:
        case 0x148u:
        case 0x14Au:
          LODWORD(v153) = *(unsigned __int16 *)(v5 - 22);
          *(_QWORD *)(v5 - 16) = v153;
          *(_QWORD *)(v5 - 8) = 0;
          goto LABEL_387;
        case 0x149u:
          v142 = *(_QWORD *)(v5 - 16);
          LODWORD(v153) = *(unsigned __int16 *)(v5 + 2);
          *(_QWORD *)(v5 - 16) = v153;
          *(_QWORD *)(v5 - 8) = v142;
          goto LABEL_387;
        case 0x14Bu:
          *(_BYTE *)(v5 + 32) = 0;
          goto LABEL_387;
        case 0x14Cu:
          *(_BYTE *)(v5 - 16) = *(_BYTE *)(v5 + 8);
          goto LABEL_387;
        case 0x14Du:
        case 0x14Eu:
          *(_BYTE *)(v5 - 16) = *(_BYTE *)(v5 - 22);
          goto LABEL_387;
        case 0x14Fu:
          *(_BYTE *)(v5 + 8) = *(_BYTE *)(v5 + 2);
          goto LABEL_387;
        case 0x151u:
          v143 = *(_QWORD *)(v5 + 8);
          v144 = *(_QWORD *)(v5 - 16);
          if ( v143 )
            *(_QWORD *)(v143 + 72) = v144;
          else
            sqlite3ExprDeleteGeneric(*a5, v144);
LABEL_375:
          *(_QWORD *)(v5 - 16) = *(_QWORD *)(v5 + 8);
          goto LABEL_387;
        case 0x153u:
          v145 = sqlite3DbMallocZero(*a5, 144);
          v40 = v145;
          if ( v145 )
          {
            *(_BYTE *)(v145 + 32) = -90;
            *(_QWORD *)(v145 + 72) = *(_QWORD *)(v5 + 8);
LABEL_135:
            *(_QWORD *)(v5 + 8) = v40;
          }
          else
          {
            sqlite3ExprDeleteGeneric(*a5, *(_QWORD *)(v5 + 8));
            *(_QWORD *)(v5 + 8) = 0;
          }
          goto LABEL_387;
        case 0x154u:
          v49 = *(_QWORD *)(v5 - 16);
LABEL_161:
          *(_QWORD *)(v5 - 64) = v49;
          goto LABEL_387;
        case 0x155u:
          v146 = sqlite3DbMallocZero(*a5, 144);
          *(_QWORD *)(v5 - 16) = v146;
          v139 = (_QWORD *)v146;
          if ( !v146 )
            goto LABEL_387;
          v141 = sqlite3DbStrNDup(*a5, *(_QWORD *)(v5 + 8), *(unsigned int *)(v5 + 16));
LABEL_359:
          *v139 = v141;
          break;
        case 0x156u:
LABEL_354:
          v95 = *(_QWORD *)(v5 - 16);
LABEL_246:
          *(_QWORD *)(v5 - 88) = v95;
          goto LABEL_387;
        case 0x157u:
          v147 = *(unsigned __int16 *)(v5 + 2);
          v154 = *(_OWORD *)(v5 + 8);
          v148 = tokenExpr(a5, v147, &v154);
          sqlite3DequoteNumber(a5, v148);
          *(_QWORD *)(v5 + 8) = v148;
          goto LABEL_387;
        default:
          goto LABEL_387;
      }
      break;
  }
LABEL_387:
  v149 = *((char *)qword_1800B6DC0 + v6);
  v150 = (unsigned __int16)word_1800B75B0[v6];
  v151 = (_WORD *)(24 * v149 + v5 + 24);
  result = (unsigned __int16)word_1800B7930[v150 + word_1800B71C0[*(unsigned __int16 *)(24 * v149 + v5)]];
  *a1 = (__int64)v151;
  *v151 = result;
  v151[1] = v150;
  return result;
}

```

## disassembly

```asm
0x18001bc30  mov     [rsp-8+arg_10], rbx
0x18001bc35  mov     [rsp-8+arg_18], rsi
0x18001bc3a  mov     [rsp-8+arg_0], rcx
0x18001bc3f  push    rbp
0x18001bc40  push    rdi
0x18001bc41  push    r13
0x18001bc43  push    r14
0x18001bc45  push    r15
0x18001bc47  lea     rbp, [rsp-2Fh]
0x18001bc4c  sub     rsp, 0B0h
0x18001bc53  mov     r13, [rcx]
0x18001bc56  mov     ebx, edx
0x18001bc58  lea     rdx, __ImageBase
0x18001bc5f  cmp     ebx, 2
0x18001bc62  jz      loc_18001E3BB
0x18001bc68  cmp     ebx, 0F1h
0x18001bc6e  jz      loc_18001E3B3; jumptable 000000018001BCA2 cases 15,18,21,47,49,62,72,81,100,246
0x18001bc74  cmp     ebx, 83h
0x18001bc7a  jz      loc_18001E3A7; jumptable 000000018001BCA2 case 116
0x18001bc80  cmp     ebx, 89h
0x18001bc86  jz      loc_18001E38F
0x18001bc8c  cmp     ebx, 157h; switch 344 cases
0x18001bc92  ja      def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bc98  mov     ecx, ds:(jpt_18001BCA2 - 180000000h)[rdx+rbx*4]
0x18001bc9f  add     rcx, rdx
0x18001bca2  jmp     rcx; switch jump
0x18001bca4  mov     rax, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 0
0x18001bca8  cmp     qword ptr [rax+150h], 0
0x18001bcb0  jnz     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bcb6  mov     byte ptr [rax+133h], 1
0x18001bcbd  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bcc2  mov     rax, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 1
0x18001bcc6  cmp     qword ptr [rax+150h], 0
0x18001bcce  jnz     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bcd4  mov     byte ptr [rax+133h], 2
0x18001bcdb  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bce0  mov     edx, [r13-10h]; jumptable 000000018001BCA2 case 3
0x18001bce4  mov     rcx, [rbp+4Fh+arg_20]
0x18001bce8  call    sqlite3BeginTransaction
0x18001bced  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bcf2  mov     dword ptr [r13+20h], 7; jumptable 000000018001BCA2 case 4
0x18001bcfa  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bcff  movzx   eax, word ptr [r13+2]; jumptable 000000018001BCA2 cases 5-7,89,91,262,324
0x18001bd04  mov     [r13+8], eax
0x18001bd08  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd0d  movzx   edx, word ptr [r13-16h]; jumptable 000000018001BCA2 cases 8,9
0x18001bd12  mov     rcx, [rbp+4Fh+arg_20]
0x18001bd16  call    sqlite3EndTransaction
0x18001bd1b  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd20  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 10
0x18001bd24  lea     r8, [r13+8]
0x18001bd28  xor     edx, edx
0x18001bd2a  call    sqlite3Savepoint
0x18001bd2f  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd34  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 11
0x18001bd38  lea     r8, [r13+8]
0x18001bd3c  mov     edx, 1
0x18001bd41  call    sqlite3Savepoint
0x18001bd46  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd4b  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 12
0x18001bd4f  lea     r8, [r13+8]
0x18001bd53  mov     edx, 2
0x18001bd58  call    sqlite3Savepoint
0x18001bd5d  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd62  mov     eax, [r13-28h]; jumptable 000000018001BCA2 case 13
0x18001bd66  lea     rdx, [r13-10h]
0x18001bd6a  mov     r9d, [r13-58h]
0x18001bd6e  lea     r8, [r13+8]
0x18001bd72  mov     rcx, [rbp+4Fh+arg_20]
0x18001bd76  xor     esi, esi
0x18001bd78  mov     dword ptr [rsp+0D0h+var_A0], eax
0x18001bd7c  mov     dword ptr [rsp+0D0h+var_A8], esi
0x18001bd80  mov     dword ptr [rsp+0D0h+var_B0], esi
0x18001bd84  call    sqlite3StartTable
0x18001bd89  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bd8e  mov     rax, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 14
0x18001bd92  inc     byte ptr [rax+24h]
0x18001bd95  mov     rcx, [rax]
0x18001bd98  inc     dword ptr [rcx+1A0h]
0x18001bd9e  xor     esi, esi
0x18001bda0  mov     [rcx+1A4h], si
0x18001bda7  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bdac  mov     dword ptr [r13-28h], 1; jumptable 000000018001BCA2 case 16
0x18001bdb4  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bdb9  mov     rax, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 17
0x18001bdbd  xor     esi, esi
0x18001bdbf  mov     rcx, [rax]
0x18001bdc2  cmp     [rcx+0C5h], sil
0x18001bdc9  setz    sil
0x18001bdcd  mov     [r13+8], esi
0x18001bdd1  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bdd6  mov     r9d, [r13+8]; jumptable 000000018001BCA2 case 19
0x18001bdda  lea     r8, [r13-10h]
0x18001bdde  mov     rcx, [rbp+4Fh+arg_20]
0x18001bde2  lea     rdx, [r13-28h]
0x18001bde6  xor     esi, esi
0x18001bde8  mov     [rsp+0D0h+var_B0], rsi
0x18001bded  call    sqlite3EndTable
0x18001bdf2  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bdf7  mov     rax, [r13+8]; jumptable 000000018001BCA2 case 20
0x18001bdfb  xor     r9d, r9d
0x18001bdfe  mov     rdi, [rbp+4Fh+arg_20]
0x18001be02  xor     r8d, r8d
0x18001be05  mov     rcx, rdi
0x18001be08  mov     [rsp+0D0h+var_B0], rax
0x18001be0d  xor     edx, edx
0x18001be0f  call    sqlite3EndTable
0x18001be14  mov     rdx, [r13+8]
0x18001be18  mov     rcx, [rdi]
0x18001be1b  call    sqlite3SelectDeleteGeneric
0x18001be20  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001be25  mov     eax, [r13+8]; jumptable 000000018001BCA2 case 22
0x18001be29  or      [r13-28h], eax
0x18001be2d  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001be32  cmp     dword ptr [r13+10h], 5; jumptable 000000018001BCA2 case 23
0x18001be37  jnz     short loc_18001BE60
0x18001be39  mov     rcx, [r13+8]
0x18001be3d  lea     rdx, aRowid_1; "rowid"
0x18001be44  mov     r8d, 5
0x18001be4a  call    sqlite3_strnicmp
0x18001be4f  test    eax, eax
0x18001be51  jnz     short loc_18001BE60
0x18001be53  mov     dword ptr [r13-10h], 280h
0x18001be5b  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001be60  mov     r9, [r13+8]
0x18001be64  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x18001be6b  mov     r8d, [r13+10h]
0x18001be6f  xor     esi, esi
0x18001be71  mov     rcx, [rbp+4Fh+arg_20]
0x18001be75  mov     [r13-10h], esi
0x18001be79  call    sqlite3ErrorMsg
0x18001be7e  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001be83  cmp     dword ptr [r13+10h], 6; jumptable 000000018001BCA2 case 24
0x18001be88  jnz     short loc_18001BEAB
0x18001be8a  mov     rcx, [r13+8]
0x18001be8e  lea     rdx, aStrict; "strict"
0x18001be95  mov     r8d, 6
0x18001be9b  call    sqlite3_strnicmp
0x18001bea0  test    eax, eax
0x18001bea2  jnz     short loc_18001BEAB
0x18001bea4  mov     esi, 10000h
0x18001bea9  jmp     short loc_18001BEC5
0x18001beab  mov     r9, [r13+8]
0x18001beaf  lea     rdx, aUnknownTableOp; "unknown table option: %.*s"
0x18001beb6  mov     r8d, [r13+10h]
0x18001beba  xor     esi, esi
0x18001bebc  mov     rcx, [rbp+4Fh+arg_20]
0x18001bec0  call    sqlite3ErrorMsg
0x18001bec5  mov     [r13+8], esi
0x18001bec9  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bece  movups  xmm0, xmmword ptr [r13+8]; jumptable 000000018001BCA2 case 25
0x18001bed3  mov     rcx, [rbp+4Fh+arg_20]
0x18001bed7  lea     r8, [rbp+4Fh+var_70]
0x18001bedb  lea     rdx, [rbp+4Fh+var_60]
0x18001bedf  movaps  [rbp+4Fh+var_70], xmm0
0x18001bee3  movups  xmm0, xmmword ptr [r13-10h]
0x18001bee8  movaps  [rbp+4Fh+var_60], xmm0
0x18001beec  call    sqlite3AddColumn
0x18001bef1  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bef6  xor     esi, esi; jumptable 000000018001BCA2 cases 26,65,106
0x18001bef8  mov     [r13+28h], esi
0x18001befc  mov     [r13+20h], rsi
0x18001bf00  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf05  mov     eax, [r13+10h]; jumptable 000000018001BCA2 case 27
0x18001bf09  sub     eax, [r13-40h]
0x18001bf0d  add     eax, [r13+8]
0x18001bf11  mov     [r13-38h], eax
0x18001bf15  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf1a  mov     eax, [r13+10h]; jumptable 000000018001BCA2 case 28
0x18001bf1e  sub     eax, [r13-70h]
0x18001bf22  add     eax, [r13+8]
0x18001bf26  mov     [r13-68h], eax
0x18001bf2a  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf2f  mov     eax, [r13+10h]; jumptable 000000018001BCA2 case 29
0x18001bf33  add     eax, [r13+8]
0x18001bf37  sub     eax, [r13-10h]
0x18001bf3b  mov     [r13-8], eax
0x18001bf3f  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf44  mov     rax, [r9]; jumptable 000000018001BCA2 case 30
0x18001bf47  mov     [r13+20h], rax
0x18001bf4b  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf50  movups  xmm0, xmmword ptr [r9]; jumptable 000000018001BCA2 case 31
0x18001bf54  movups  xmmword ptr [r13+20h], xmm0
0x18001bf59  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf5e  mov     rax, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 cases 32,67
0x18001bf62  movups  xmm0, xmmword ptr [r13+8]
0x18001bf67  movups  xmmword ptr [rax+70h], xmm0
0x18001bf6b  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf70  mov     r8, [r13-10h]; jumptable 000000018001BCA2 case 33
0x18001bf74  mov     r9d, [r13-8]
0x18001bf78  mov     rdx, [r13+8]
0x18001bf7c  add     r9, r8
0x18001bf7f  mov     rcx, [rbp+4Fh+arg_20]
0x18001bf83  call    sqlite3AddDefaultValue
0x18001bf88  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bf8d  mov     r8, [r13-28h]; jumptable 000000018001BCA2 case 34
0x18001bf91  mov     r9, [r13+8]
0x18001bf95  inc     r8
0x18001bf98  mov     rdx, [r13-10h]
0x18001bf9c  mov     rcx, [rbp+4Fh+arg_20]
0x18001bfa0  call    sqlite3AddDefaultValue
0x18001bfa5  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bfaa  mov     r9d, [r13-8]; jumptable 000000018001BCA2 case 35
0x18001bfae  add     r9, [r13-10h]
0x18001bfb2  mov     r8, [r13-28h]
0x18001bfb6  mov     rdx, [r13+8]
0x18001bfba  mov     rcx, [rbp+4Fh+arg_20]
0x18001bfbe  call    sqlite3AddDefaultValue
0x18001bfc3  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bfc8  mov     r8, [r13+8]; jumptable 000000018001BCA2 case 36
0x18001bfcc  xor     r9d, r9d
0x18001bfcf  mov     rcx, [rbp+4Fh+arg_20]
0x18001bfd3  mov     edx, 0AEh
0x18001bfd8  call    sqlite3PExpr
0x18001bfdd  mov     r9d, [r13-8]
0x18001bfe1  mov     rdx, rax
0x18001bfe4  add     r9, [r13-10h]
0x18001bfe8  mov     r8, [r13-28h]
0x18001bfec  mov     rcx, [rbp+4Fh+arg_20]
0x18001bff0  call    sqlite3AddDefaultValue
0x18001bff5  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001bffa  movups  xmm0, xmmword ptr [r13+8]; jumptable 000000018001BCA2 case 37
0x18001bfff  mov     rsi, [rbp+4Fh+arg_20]
0x18001c003  lea     r8, [rbp+4Fh+var_60]
0x18001c007  mov     edx, 75h ; 'u'
0x18001c00c  mov     rcx, rsi
0x18001c00f  movaps  [rbp+4Fh+var_60], xmm0
0x18001c013  call    tokenExpr
0x18001c018  mov     rdi, rax
0x18001c01b  test    rax, rax
0x18001c01e  jz      short loc_18001C028
0x18001c020  mov     rcx, rax
0x18001c023  call    sqlite3ExprIdToTrueFalse
0x18001c028  mov     r8, [r13+8]
0x18001c02c  mov     rdx, rdi
0x18001c02f  mov     r9d, [r13+10h]
0x18001c033  mov     rcx, rsi
0x18001c036  add     r9, r8
0x18001c039  call    sqlite3AddDefaultValue
0x18001c03e  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c043  mov     edx, [r13+8]; jumptable 000000018001BCA2 case 38
0x18001c047  mov     rcx, [rbp+4Fh+arg_20]
0x18001c04b  call    sqlite3AddNotNull
0x18001c050  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c055  mov     eax, [r13-28h]; jumptable 000000018001BCA2 case 39
0x18001c059  xor     edx, edx
0x18001c05b  mov     r9d, [r13+8]
0x18001c05f  mov     r8d, [r13-10h]
0x18001c063  mov     rcx, [rbp+4Fh+arg_20]
0x18001c067  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001c06b  call    sqlite3AddPrimaryKey
0x18001c070  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c075  mov     eax, [r13+8]; jumptable 000000018001BCA2 case 40
0x18001c079  xor     esi, esi
0x18001c07b  mov     [rsp+0D0h+var_80], 1
0x18001c080  mov     [rsp+0D0h+var_88], esi
0x18001c084  mov     dword ptr [rsp+0D0h+var_90], esi
0x18001c088  mov     [rsp+0D0h+var_98], rsi
0x18001c08d  mov     [rsp+0D0h+var_A0], rsi
0x18001c092  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001c096  mov     [rsp+0D0h+var_B0], rsi
0x18001c09b  mov     rcx, [rbp+4Fh+arg_20]
0x18001c09f  xor     r9d, r9d
0x18001c0a2  xor     r8d, r8d
0x18001c0a5  xor     edx, edx
0x18001c0a7  call    sqlite3CreateIndex
0x18001c0ac  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c0b1  mov     r9, [r13+8]; jumptable 000000018001BCA2 case 41
0x18001c0b5  mov     r8, [r13-28h]
0x18001c0b9  mov     rdx, [r13-10h]
0x18001c0bd  mov     rcx, [rbp+4Fh+arg_20]
0x18001c0c1  call    sqlite3AddCheckConstraint
0x18001c0c6  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c0cb  mov     eax, [r13+8]; jumptable 000000018001BCA2 case 42
0x18001c0cf  lea     r8, [r13-28h]
0x18001c0d3  mov     r9, [r13-10h]
0x18001c0d7  xor     edx, edx
0x18001c0d9  mov     rcx, [rbp+4Fh+arg_20]
0x18001c0dd  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001c0e1  call    sqlite3CreateForeignKey
0x18001c0e6  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c0eb  mov     rcx, [rbp+4Fh+arg_20]; jumptable 000000018001BCA2 case 44
0x18001c0ef  lea     rdx, [r13+8]
0x18001c0f3  call    sqlite3AddCollateType
0x18001c0f8  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c0fd  mov     rdx, [r13-10h]; jumptable 000000018001BCA2 case 45
0x18001c101  xor     r8d, r8d
0x18001c104  mov     rcx, [rbp+4Fh+arg_20]
0x18001c108  call    sqlite3AddGenerated
0x18001c10d  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c112  mov     rdx, [r13-28h]; jumptable 000000018001BCA2 case 46
0x18001c116  lea     r8, [r13+8]
0x18001c11a  mov     rcx, [rbp+4Fh+arg_20]
0x18001c11e  call    sqlite3AddGenerated
0x18001c123  jmp     def_18001BCA2; jumptable 000000018001BCA2 default case, cases 2,131,137,241,325,327,338
0x18001c128  mov     eax, [r13+0Ch]; jumptable 000000018001BCA2 case 50
0x18001c12c  not     eax
0x18001c12e  and     eax, [r13-10h]
0x18001c132  or      eax, [r13+8]
0x18001c136  mov     [r13-10h], eax
  ... truncated ...
```
