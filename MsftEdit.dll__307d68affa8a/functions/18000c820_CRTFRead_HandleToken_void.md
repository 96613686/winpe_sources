# CRTFRead::HandleToken(void)

- ea: `0x18000c820`
- end: `0x18000ff4f`
- name: `?HandleToken@CRTFRead@@AEAAHXZ`
- size: `14127`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `71`
- tags: ``

## callers

- `0x18000be3c`

## callees

- `0x1800091d8`
- `0x18000a65c`
- `0x18000ab18`
- `0x18000ab88`
- `0x18000b550`
- `0x18000c820`
- `0x18000ff58`
- `0x1800108c4`
- `0x180011cd0`
- `0x180012f50`
- `0x180016b80`
- `0x18002d2bc`
- `0x180038ad4`
- `0x18003a828`
- `0x18003af70`
- `0x18003b4b4`
- `0x18003b7a8`
- `0x18003be20`
- `0x18003c0b0`
- `0x18003c384`
- `0x18003cabc`
- `0x18003cb94`
- `0x180049c8c`
- `0x18004d378`
- `0x18004eadc`
- `0x18004f7a0`
- `0x18005f2e8`
- `0x180060670`
- `0x1800613f4`
- `0x180067f60`
- `0x1800693d4`
- `0x18006e770`
- `0x180071a84`
- `0x180078188`
- `0x18007e0f0`
- `0x180093e8c`
- `0x1800c10fc`
- `0x1800e1110`
- `0x1800e1378`
- `0x1800e5578`
- `0x1800fdf88`
- `0x180100924`
- `0x180105fe0`
- `0x18010769c`
- `0x180108048`
- `0x180109d04`
- `0x18010f990`
- `0x1801164b4`
- `0x18014c948`
- `0x180155260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d88d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000d88d`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18000f2fd`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18000f2fd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000eaeb`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000eaeb`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleToken(CRTFRead *this)
{
  __int64 v2; // rsi
  _WORD *v3; // r10
  int v4; // ecx
  _WORD *v5; // r15
  struct STATE *v6; // rdx
  unsigned int v7; // ecx
  _DWORD *v8; // r9
  int v9; // r13d
  int v10; // edi
  char v11; // al
  int v12; // r11d
  int v13; // r14d
  bool v14; // zf
  __int64 result; // rax
  int v16; // edx
  _BYTE *v17; // rax
  __int64 v18; // rcx
  char v19; // r9
  __int16 v20; // dx
  char v21; // cl
  __int16 v22; // dx
  __int64 v23; // rax
  int v24; // eax
  __int16 v25; // cx
  __int16 v26; // dx
  __int64 v27; // rax
  int v28; // edx
  _BYTE *v29; // rax
  unsigned __int8 v30; // al
  __int64 v31; // r10
  unsigned __int16 v32; // ax
  _WORD *v33; // r10
  int v34; // edx
  _BYTE *v35; // rax
  _BYTE *v36; // r10
  int v37; // edx
  _WORD *v38; // rax
  int v39; // edx
  _BYTE *v40; // rax
  unsigned __int16 v41; // dx
  __int64 v42; // rdx
  __int64 v43; // rax
  unsigned int Color; // eax
  int v45; // edx
  __int16 v46; // r11
  int v47; // edx
  __int64 v48; // r10
  int v49; // eax
  int v50; // edx
  _WORD *v51; // rax
  __int64 v52; // r10
  __int64 v53; // rdx
  int v54; // edx
  _WORD *v55; // rax
  __int64 v56; // r10
  int v57; // r8d
  char *v58; // rax
  char *v59; // rdi
  const struct CCharFormat *CF; // rax
  __int64 v61; // rdx
  const unsigned __int16 *FontName; // rax
  int v63; // r8d
  unsigned __int16 *v64; // rdx
  unsigned __int16 v65; // cx
  unsigned __int16 *v66; // rcx
  int v67; // edx
  char v68; // cl
  __int64 v69; // rcx
  unsigned __int16 v70; // dx
  enum __MIDL___MIDL_itf_tom_0000_0000_0002 v71; // r8d
  __int64 v72; // rcx
  int v73; // r14d
  int v74; // edx
  __int64 v75; // rcx
  int v76; // eax
  CTxtEdit *v77; // rcx
  struct _textfont *TextFont; // rax
  unsigned __int8 v79; // al
  __int64 v80; // r10
  int v81; // edx
  unsigned int *v82; // r8
  struct _textfont *v83; // rax
  char v84; // r8
  CRTFRead *v85; // rcx
  void **p_Block; // rdx
  void *v87; // rdi
  int v88; // eax
  void *v89; // rcx
  CRTFRead *v90; // rcx
  void **v91; // rdx
  int v92; // edx
  char v93; // al
  unsigned __int8 StandardColorIndex; // al
  __int16 v95; // dx
  int v96; // ecx
  char v97; // al
  char v98; // al
  int v99; // r14d
  __int16 v100; // ax
  char v101; // al
  int v102; // edx
  _WORD *v103; // rax
  __int64 v104; // r10
  int v105; // r8d
  int v106; // edx
  __int64 v107; // rcx
  int v108; // eax
  char v109; // al
  unsigned int v110; // r8d
  int v111; // r8d
  int v112; // r8d
  char v113; // cl
  int v114; // eax
  int v115; // eax
  char v116; // r10
  unsigned __int8 v117; // cl
  int v118; // eax
  int v119; // edx
  char v120; // cl
  int CellColorIndex; // eax
  char v122; // r11
  unsigned int v123; // eax
  unsigned __int8 v124; // r9
  int v125; // eax
  char v126; // r9
  unsigned __int8 v127; // cl
  __int16 v128; // ax
  __int16 v129; // dx
  int v130; // r8d
  int v131; // edx
  int v132; // r10d
  _WORD *v133; // rax
  __int64 v134; // r10
  __int64 v135; // rdx
  char v136; // al
  int v137; // edx
  _WORD *v138; // rax
  __int64 v139; // r10
  int v140; // edx
  _WORD *v141; // rax
  __int64 v142; // r10
  int v143; // edx
  _BYTE *v144; // rax
  CArrayBase *v145; // rcx
  int v146; // r10d
  int v147; // edx
  _DWORD *v148; // rax
  int v149; // r10d
  int i; // r11d
  _WORD *v151; // rax
  __int16 v152; // r11
  int v153; // eax
  _WORD *v154; // rax
  __int16 v155; // r10
  _WORD *v156; // r15
  __int64 v157; // rdx
  __int16 v158; // ax
  int v159; // ecx
  _WORD *v160; // rax
  int v161; // r8d
  __int16 v162; // cx
  int v163; // eax
  __int16 v164; // ax
  __int16 v165; // ax
  int v166; // edx
  CTxtRange *v167; // rcx
  bool v168; // dl
  int v169; // ecx
  int v170; // edx
  int v171; // ecx
  char v173; // r15
  int v174; // ecx
  struct CDocInfo *DocInfo; // rax
  struct CDocInfo *v176; // rdi
  void *v177; // rcx
  void *v178; // rcx
  __int64 v179; // rcx
  const unsigned __int16 *v180; // rdx
  int v181; // r8d
  _BYTE *v182; // rax
  __int16 v183; // dx
  __int16 v184; // r8
  _WORD *v185; // rax
  __int16 v186; // ax
  __int64 v187; // r11
  __int16 *v188; // rax
  __int16 v189; // ax
  __int64 v190; // r11
  __int64 v191; // rax
  int v192; // ecx
  CRTFRead *v193; // rcx
  _WORD *v194; // rax
  __int16 v195; // cx
  _QWORD **v196; // rdx
  int v197; // eax
  __int64 v198; // rcx
  char *v199; // r14
  int v200; // ecx
  int v201; // eax
  _WORD *v202; // rax
  int v203; // eax
  __int64 *v204; // rdi
  __int64 v205; // rax
  _QWORD *v206; // rsi
  int v207; // ecx
  __int64 v208; // rax
  __int16 v209; // dx
  __int16 v210; // r10
  char v211; // al
  char v212; // al
  char v213; // al
  struct CDocInfo *v214; // rax
  struct CDocInfo *v215; // rax
  struct CDocInfo *v216; // rdx
  int v217; // eax
  CTxtEdit *v218; // rcx
  int v219; // esi
  __int16 *v220; // r10
  __int64 v221; // r11
  int v222; // edx
  const struct CFontOptions *FontOptions; // rax
  __int64 v224; // r10
  CDocInfo *v225; // r11
  struct CDocInfo *v226; // rcx
  int v227; // edi
  int v228; // eax
  struct CDocInfo *v229; // rax
  struct CDocInfo *v230; // rax
  char v231; // cl
  char v232; // dl
  __int64 v233; // rax
  __int16 v234; // cx
  __int16 v235; // dx
  __int64 v236; // rax
  struct STATE *v237; // rdx
  CRTFRead *v238; // rcx
  __int64 v239; // rax
  struct STATE *v240; // rdx
  char v241; // cl
  char v242; // cl
  bool v243; // [rsp+20h] [rbp-49h]
  unsigned __int8 *v244; // [rsp+28h] [rbp-41h]
  __int64 v245; // [rsp+50h] [rbp-19h]
  __int64 v246; // [rsp+60h] [rbp-9h] BYREF
  __int64 v247; // [rsp+68h] [rbp-1h]
  char v248; // [rsp+D0h] [rbp+67h]
  void *Block; // [rsp+D8h] [rbp+6Fh] BYREF
  char *v250; // [rsp+E0h] [rbp+77h]
  __int64 v251; // [rsp+E8h] [rbp+7Fh]

  v2 = *((_QWORD *)this + 38);
  v3 = (_WORD *)((char *)this + 244);
  v251 = *(_QWORD *)(*((_QWORD *)this + 13) + 24LL);
  v250 = (char *)this + 244;
  v245 = v251 - 8;
  if ( v2 )
  {
    v250 = (char *)this + 244;
  }
  else if ( *v3 != 261 )
  {
LABEL_16:
    result = 24;
    *((_DWORD *)this + 31) = 24;
    return result;
  }
  v4 = (unsigned __int16)*v3;
  LODWORD(Block) = v4;
  if ( (unsigned int)(v4 - 579) > 0x24 )
  {
    v5 = v3;
LABEL_5:
    v6 = (struct STATE *)(unsigned __int16)v4;
    v246 = (__int64)v5;
    v7 = v4 - 256;
    v248 = 0;
    v8 = (_DWORD *)((char *)this + 240);
    v9 = 2048;
    v10 = *((_DWORD *)this + 60);
    v11 = 4;
    v12 = 4096;
    v13 = 1;
    switch ( v7 )
    {
      case 0u:
      case 1u:
        if ( (*((_BYTE *)this + 1523) & 0x20) == 0 )
          goto LABEL_13;
        if ( !*(_WORD *)(v2 + 10) )
        {
          v182 = (_BYTE *)*((_QWORD *)this + 31);
          if ( *v182 == 32 && !v182[1] )
          {
            *v5 = *((_WORD *)this + 123);
            v248 = 1;
            goto LABEL_13;
          }
        }
        if ( *((_WORD *)this + 123) != 527 )
        {
LABEL_13:
          CRTFRead::HandleTextToken(this, (struct STATE *)v2);
          goto LABEL_14;
        }
LABEL_148:
        *((_DWORD *)this + 31) = 24;
        goto LABEL_14;
      case 2u:
        v14 = *((_WORD *)this + 123) == 527;
        goto LABEL_7;
      case 3u:
      case 4u:
      case 0x64u:
      case 0x7Au:
      case 0x8Bu:
      case 0x8Cu:
      case 0x99u:
      case 0x9Au:
      case 0x9Bu:
      case 0x9Cu:
      case 0x9Du:
      case 0x9Eu:
      case 0x9Fu:
      case 0xB4u:
      case 0x115u:
      case 0x12Eu:
      case 0x12Fu:
      case 0x136u:
      case 0x138u:
      case 0x139u:
      case 0x13Au:
      case 0x13Bu:
      case 0x16Cu:
      case 0x18Au:
      case 0x18Du:
      case 0x18Eu:
      case 0x18Fu:
      case 0x195u:
      case 0x198u:
      case 0x19Au:
      case 0x19Bu:
      case 0x19Cu:
      case 0x1A9u:
      case 0x1AAu:
      case 0x1ABu:
      case 0x1ACu:
      case 0x1AEu:
      case 0x1AFu:
      case 0x1B1u:
      case 0x1B3u:
      case 0x1B4u:
      case 0x1B6u:
      case 0x1B8u:
      case 0x1C7u:
      case 0x1CBu:
      case 0x1CCu:
      case 0x1CDu:
      case 0x1CEu:
      case 0x1CFu:
      case 0x1D0u:
      case 0x1D1u:
      case 0x1D2u:
      case 0x1D3u:
      case 0x1D4u:
      case 0x1D5u:
      case 0x1D6u:
      case 0x1D7u:
      case 0x1DBu:
      case 0x1DCu:
      case 0x1DDu:
      case 0x1DEu:
      case 0x1DFu:
      case 0x1E0u:
      case 0x1E1u:
      case 0x1E2u:
      case 0x1E3u:
      case 0x1E4u:
      case 0x1E5u:
        goto LABEL_14;
      case 5u:
        CRTFRead::HandleStartGroup(this);
        v20 = *((_WORD *)this + 760);
        if ( (v20 & 0x100) == 0 )
        {
          v248 = 1;
          goto LABEL_14;
        }
        v2 = *((_QWORD *)this + 38);
        *((_WORD *)this + 760) = v20 & 0xFEFF;
LABEL_84:
        if ( *(_QWORD *)(v2 + 32) )
          goto LABEL_16;
        *(_WORD *)(v2 + 10) = 0;
        if ( !*((_DWORD *)this + 2) && !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 762) = 0;
        v58 = (char *)CArrayBase::Elem(this, 0);
        *(_DWORD *)(v2 + 16) = 0;
        v59 = v58;
        CF = CRchTxtPtr::GetCF((CRchTxtPtr *)(*((_QWORD *)this + 13) + 8LL));
        v59[2] = *((_BYTE *)CF + 4);
        v59[3] = *((_BYTE *)CF + 5);
        *((_WORD *)v59 + 38) = CW32System::CodePageFromCharRep(*((_BYTE *)CF + 4));
        v59[78] = (*(_DWORD *)v61 & 0x80000) != 0;
        FontName = CFICache::GetFontName(*(_WORD *)(v61 + 6));
        v63 = 32;
        v64 = (unsigned __int16 *)(v59 + 6);
        while ( 1 )
        {
          v65 = *FontName;
          *v64 = *FontName;
          if ( !v65 )
            break;
          v66 = v64;
          ++FontName;
          ++v64;
          if ( !--v63 )
          {
            *v66 = 0;
            break;
          }
        }
        *((_WORD *)v59 + 34) = 0;
        *(_WORD *)v2 = 1;
        goto LABEL_14;
      case 6u:
        CRTFRead::HandleFieldEndGroup(this);
        CRTFRead::HandleEndGroup(this);
        v26 = *((_WORD *)this + 822);
        if ( (v26 & 0x100) == 0 )
          goto LABEL_14;
        v27 = *(_QWORD *)(v2 + 32);
        if ( !v27 || *(_WORD *)(v27 + 10) != 7 )
          goto LABEL_14;
        *((_WORD *)this + 822) = v26 & 0xFEFF;
        goto LABEL_8;
      case 7u:
        v202 = (_WORD *)*((_QWORD *)this + 193);
        if ( !v202 || *v202 == 11 )
        {
          *((_WORD *)this + 760) |= 1u;
        }
        else
        {
          v203 = CRTFRead::ObjectReadFromEditStream(this);
          *((_WORD *)this + 760) &= ~1u;
          *((_WORD *)this + 760) |= v203 != 0;
        }
        goto LABEL_647;
      case 8u:
        if ( !CRTFRead::StaticObjectReadFromEditStream(this, 0) && *((_DWORD *)this + 31) )
          goto LABEL_14;
LABEL_647:
        if ( !(unsigned int)CRTFRead::SkipToEndOfGroup(this) )
          goto LABEL_11;
        goto LABEL_14;
      case 9u:
        *((_WORD *)this + 61) = 0;
        *((_DWORD *)this + 30) |= 0xFDE90020;
        STATE::SetCodePage((STATE *)v2, 0xFDE9u);
        goto LABEL_84;
      case 0xAu:
        *((_DWORD *)this + 30) |= 0x800u;
        goto LABEL_84;
      case 0xBu:
        goto LABEL_84;
      case 0xCu:
        *((_BYTE *)this + 198) = 0;
        goto LABEL_14;
      case 0xDu:
        *((_WORD *)this + 760) |= 0x4000u;
        goto LABEL_14;
      case 0xEu:
        if ( (*((_BYTE *)this + 120) & 0x20) == 0 )
        {
          *((_WORD *)this + 768) = v10;
          STATE::SetCodePage((STATE *)v2, v10);
        }
        goto LABEL_14;
      case 0xFu:
        v76 = *((_DWORD *)this + 30);
        if ( (v76 & 0x8000) == 0 && (v76 & 0xFFFF0020) == 0xFDE90020 )
          CTxtEdit::SetViewKind(*((CTxtEdit **)this + 12), v10);
        goto LABEL_14;
      case 0x10u:
        if ( (*((_DWORD *)this + 30) & 0xA000) == 0x2000 )
        {
          v77 = (CTxtEdit *)*((_QWORD *)this + 12);
          if ( (*((_BYTE *)v77 + 276) & 0x40) == 0 )
            CTxtEdit::SetViewScale(v77, v10);
        }
        goto LABEL_14;
      case 0x11u:
        if ( v10 < 0 || (*((_BYTE *)this + 1520) & 0x40) != 0 )
          goto LABEL_14;
        if ( !*((_DWORD *)this + 2) && !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 762) = v10;
        v47 = 0;
        goto LABEL_107;
      case 0x12u:
        if ( v10 < 0 || *((_DWORD *)this + 2) != 1 )
          goto LABEL_14;
        if ( !CArrayBase::ArAdd(this, 1, 0) )
          goto LABEL_87;
        *((_WORD *)this + 763) = v10;
        v47 = 1;
LABEL_107:
        *(_WORD *)CArrayBase::Elem(this, v47) = v10;
        goto LABEL_14;
      case 0x13u:
        *((_WORD *)this + 764) = v10;
        goto LABEL_14;
      case 0x14u:
        *((_WORD *)this + 765) = v10;
        goto LABEL_14;
      case 0x15u:
        *((_WORD *)this + 766) = v10;
        goto LABEL_14;
      case 0x16u:
        if ( *(_WORD *)(v2 + 10) != 12 && *(_WORD *)(v2 + 10) != 24 )
          CRTFRead::Pard(this, (struct STATE *)v2);
        goto LABEL_14;
      case 0x17u:
        CRTFRead::SetPlain(this, v6);
        goto LABEL_14;
      case 0x18u:
        *((_WORD *)this + 822) |= 0x400u;
        goto LABEL_181;
      case 0x19u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
          *(_WORD *)(*((_QWORD *)this + 12) + 358LL) &= ~0x100u;
        goto LABEL_14;
      case 0x1Au:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 2);
        *(_DWORD *)(v2 + 16) = -1;
        goto LABEL_14;
      case 0x1Bu:
        if ( *(_WORD *)(v2 + 10) != 2 )
        {
          if ( *((_DWORD *)this + 2) && *(_WORD *)(v2 + 10) != 18 && v10 != -1 )
          {
            CRTFRead::SelectCurrentFont(this, v10, 0);
            v16 = *(_DWORD *)(v2 + 16);
            if ( v16 < 0 || v16 >= *((_DWORD *)this + 2) )
            {
              v18 = 1;
            }
            else
            {
              v17 = CArrayBase::Elem(this, v16);
              v18 = 1;
              if ( v17 )
              {
                if ( (unsigned int)CW32System::IsBiDiCharRep(v17[2]) )
                {
                  *((_BYTE *)this + 1617) = v19;
                  if ( *(_BYTE *)(v2 + 23) == 1 )
                    *(_BYTE *)(v2 + 23) = 2;
                  v18 = 2;
                }
                else
                {
                  v18 = 1;
                  if ( *(_BYTE *)(v2 + 23) == 2 && v19 == 11 )
                    *(_BYTE *)(v2 + 23) = 0;
                }
              }
            }
            *(_WORD *)(v2 + 4 * v18 + 62) = 0;
            *(_WORD *)(v2 + 4 * v18 + 60) = v10;
            *(_DWORD *)(v2 + 4) |= 0x10u;
          }
          goto LABEL_14;
        }
        if ( v10 == -1 )
          goto LABEL_8;
        if ( v10 == *((__int16 *)this + 762) )
        {
          *((_WORD *)this + 760) |= 0x20u;
          v13 = 0;
          v37 = 0;
        }
        else
        {
          v37 = 1;
          if ( v10 != *((__int16 *)this + 763) )
          {
            v38 = CArrayBase::ArAdd(this, 1, 0);
            if ( !v38 )
            {
LABEL_87:
              v42 = *((_QWORD *)this + 12) & -(__int64)(*(_WORD *)(*((_QWORD *)this + 12) + 56LL) != 0);
              v43 = v42 + 60;
              if ( !v42 )
                v43 = 12;
              *(_DWORD *)v43 |= 0x40u;
LABEL_90:
              *((_DWORD *)this + 31) = 9;
              goto LABEL_14;
            }
            v13 = *((_DWORD *)this + 2) - 1;
LABEL_72:
            *(_DWORD *)(v2 + 16) = v13;
            *v38 = v10;
            v38[3] = 0;
            v38[1] = 9;
            *((_DWORD *)v38 + 19) = 0xFFFF;
            goto LABEL_14;
          }
        }
        v38 = CArrayBase::Elem(this, v37);
        if ( !v38 )
          goto LABEL_209;
        goto LABEL_72;
      case 0x1Cu:
        *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 60) = v10;
        LOWORD(v10) = 0;
        goto LABEL_30;
      case 0x1Du:
LABEL_30:
        *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 62) = v10;
        goto LABEL_14;
      case 0x1Eu:
      case 0x1Fu:
      case 0x20u:
      case 0x21u:
      case 0x22u:
      case 0x23u:
      case 0x24u:
      case 0x25u:
        v34 = *(_DWORD *)(v2 + 16);
        if ( v34 >= 0 && v34 < *((_DWORD *)this + 2) )
        {
          v35 = CArrayBase::Elem(this, v34);
          if ( v35 )
          {
            v35[3] = v35[3] & 0xF | (16 * (*v36 + 2));
            if ( *(_WORD *)v36 == 292 && v35[2] == 9 )
              v35[2] = 10;
          }
        }
        goto LABEL_14;
      case 0x26u:
        v28 = *(_DWORD *)(v2 + 16);
        if ( v28 < 0 )
          goto LABEL_14;
        if ( v28 >= *((_DWORD *)this + 2) )
          goto LABEL_14;
        v29 = CArrayBase::Elem(this, v28);
        if ( !v29 )
          goto LABEL_14;
        v30 = v29[2];
        if ( v30 != 10 )
        {
          v30 = CW32System::CharRepFromCharSet(v10);
          *(_BYTE *)(v31 + 2) = v30;
        }
        v32 = CW32System::CodePageFromCharRep(v30);
        v33[38] = v32;
        if ( *(_WORD *)(v2 + 12) == 0xFDE9 )
        {
          v32 = -535;
        }
        else
        {
          *(_WORD *)(v2 + 12) = v32;
          if ( v32 == 42 )
            goto LABEL_56;
        }
        if ( *((_WORD *)this + 768) == 0xFFFF )
          *((_WORD *)this + 768) = v32;
LABEL_56:
        if ( (unsigned int)(unsigned __int8)v10 - 177 <= 1 )
        {
          if ( *((_WORD *)this + 763) == 0xFFFF )
            *((_WORD *)this + 763) = *v33;
          if ( !(unsigned int)CW32System::IsBiDiCharRep(*((_BYTE *)this + 1617)) )
            *((_BYTE *)this + 1617) = *(_BYTE *)(v48 + 2);
        }
        *((_WORD *)this + 760) |= 0x80u;
        if ( v10 )
          *((_BYTE *)this + 1523) |= 8u;
        goto LABEL_14;
      case 0x27u:
        v39 = *(_DWORD *)(v2 + 16);
        if ( v39 >= 0 && v39 < *((_DWORD *)this + 2) )
        {
          v40 = CArrayBase::Elem(this, v39);
          if ( v40 )
          {
            v40[3] &= 0xF0u;
            v40[3] |= v10;
          }
        }
        goto LABEL_14;
      case 0x28u:
        v57 = 13;
        goto LABEL_135;
      case 0x29u:
        STATE::SetCodePage((STATE *)v2, v10);
        if ( *(_WORD *)(v2 + 10) == 2 )
        {
          TextFont = CRTFRead::GetTextFont(this, *(_DWORD *)(v2 + 16));
          if ( TextFont )
          {
            *((_WORD *)TextFont + 38) = v10;
            v79 = CW32System::CharRepFromCodePage(v10);
            *(_BYTE *)(v80 + 2) = v79;
            if ( *((_WORD *)this + 768) == 0xFFFF )
              *((_WORD *)this + 768) = v10;
          }
        }
        goto LABEL_14;
      case 0x2Au:
        goto LABEL_36;
      case 0x2Bu:
        *((_DWORD *)this + 83) |= 0x400000u;
        if ( (unsigned __int8)v10 <= 9u )
        {
          *((_BYTE *)this + 191) &= 0xF0u;
          *((_BYTE *)this + 191) |= v10;
        }
        goto LABEL_14;
      case 0x2Cu:
        *((_DWORD *)this + 81) |= 0x400000u;
        *((_WORD *)this + 72) = v10;
        goto LABEL_14;
      case 0x2Du:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 1);
        *((_WORD *)this + 760) &= ~8u;
        goto LABEL_14;
      case 0x2Eu:
      case 0x30u:
        *((_DWORD *)this + 37) = CRTFRead::GetColor(this, 0x4000000u);
        goto LABEL_14;
      case 0x2Fu:
        Color = CRTFRead::GetColor(this, 0x40000000u);
        goto LABEL_92;
      case 0x31u:
        *(_BYTE *)(v2 + 20) = v10;
        goto LABEL_228;
      case 0x32u:
        *(_BYTE *)(v2 + 21) = v10;
        goto LABEL_228;
      case 0x33u:
        *(_BYTE *)(v2 + 22) = v10;
LABEL_228:
        *((_WORD *)this + 760) |= 8u;
        goto LABEL_14;
      case 0x34u:
      case 0x35u:
      case 0x37u:
      case 0x38u:
      case 0x39u:
      case 0x3Bu:
      case 0x41u:
      case 0x42u:
        goto LABEL_97;
      case 0x36u:
        v93 = 1;
        goto LABEL_268;
      case 0x3Au:
      case 0x3Du:
      case 0x3Eu:
      case 0x3Fu:
      case 0x40u:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        v3 = v250;
        v8 = (_DWORD *)((char *)this + 240);
        goto LABEL_97;
      case 0x3Cu:
        if ( *(_WORD *)(v2 + 10) != 12 )
          goto LABEL_97;
        goto LABEL_14;
      case 0x43u:
        v45 = 0x200000;
        *((_DWORD *)this + 82) = 0x200000;
        goto LABEL_98;
      case 0x44u:
        *((_DWORD *)this + 32) &= ~4u;
        *((_DWORD *)this + 81) |= 4u;
        goto LABEL_14;
      case 0x45u:
      case 0x46u:
      case 0x47u:
      case 0x48u:
      case 0x49u:
      case 0x4Au:
      case 0x4Bu:
      case 0x4Cu:
      case 0x4Du:
      case 0x4Eu:
      case 0x4Fu:
      case 0x50u:
      case 0x51u:
      case 0x52u:
      case 0x53u:
      case 0x54u:
      case 0x55u:
        v8 = (_DWORD *)((char *)this + 240);
        v93 = *(_BYTE *)v3 - 67;
        *v3 = 310;
LABEL_268:
        *((_BYTE *)this + 164) = v93;
        *((_DWORD *)this + 81) |= 0x800000u;
LABEL_97:
        v45 = 1 << (*v3 - 52);
        *((_DWORD *)this + 81) |= v45;
LABEL_98:
        *((_DWORD *)this + 32) &= ~v45;
        v46 = *((_WORD *)this + 760) & 0x1000;
        if ( !v46 || *v8 )
          *((_DWORD *)this + 32) |= v45;
        *((_BYTE *)this + 1659) |= *((_BYTE *)this + 128) & 3;
        if ( v46 && !*v8 )
          *((_BYTE *)this + 1659) &= ~(_BYTE)v45;
        goto LABEL_14;
      case 0x56u:
        StandardColorIndex = CRTFRead::GetStandardColorIndex(this);
        *((_BYTE *)this + 167) = StandardColorIndex;
        if ( StandardColorIndex > 1u )
          *((_DWORD *)this + 81) |= 0x800004u;
        goto LABEL_14;
      case 0x57u:
        v95 = -10;
        goto LABEL_281;
      case 0x58u:
        v95 = 10;
LABEL_281:
        if ( (*((_WORD *)this + 760) & 0x1000) == 0 )
          LOWORD(v10) = 6;
        *((_DWORD *)this + 81) |= 0x10000000u;
        *((_WORD *)this + 69) = v95 * v10;
        goto LABEL_14;
      case 0x59u:
        v96 = 0x10000;
        goto LABEL_287;
      case 0x5Au:
        v96 = 0;
        goto LABEL_287;
      case 0x5Bu:
        v96 = 0x20000;
LABEL_287:
        *((_DWORD *)this + 81) |= 0x30000u;
        *((_DWORD *)this + 32) &= 0xFFFCFFFF;
        *((_DWORD *)this + 32) |= v96;
        goto LABEL_14;
      case 0x5Cu:
        *((_DWORD *)this + 81) |= 0x40000u;
        *((_BYTE *)this + 165) = v10;
        CRTFRead::CheckNotifyLowFiRTF(this, 1);
        goto LABEL_14;
      case 0x5Du:
        *((_WORD *)this + 73) = v10;
        *((_DWORD *)this + 81) |= 0x200000u;
        if ( v10 )
          CTxtEdit::OnSetTypographyOptions(*((CTxtEdit **)this + 12), 1u, 1);
        goto LABEL_14;
      case 0x5Eu:
        *((_DWORD *)this + 81) |= 0x100000u;
        *((_WORD *)this + 81) = 10 * v10;
        goto LABEL_14;
      case 0x5Fu:
        v81 = *((_DWORD *)this + 81);
        v82 = (unsigned int *)((char *)this + 152);
        if ( (v81 & 0x2000000) == 0 || !CLangTagTable::IsValidIndex(*v82) )
        {
          *((_DWORD *)this + 81) = v81 | 0x2000000;
          *((_DWORD *)this + 38) = (unsigned __int16)v10;
          *(_DWORD *)(v2 + 56) = (unsigned __int16)v10;
          if ( (unsigned int)CW32System::IsBiDiLcid(*v82) )
          {
            *((_BYTE *)this + 1617) = CCharFormat::CharRepFromLang((CRTFRead *)((char *)this + 128));
            if ( *(_BYTE *)(v2 + 23) == 1 )
              *(_BYTE *)(v2 + 23) = 2;
            if ( *((_BYTE *)this + 1617) > 0x13u && (*((_DWORD *)this + 81) & 0x20000000) != 0 )
            {
              v83 = CRTFRead::GetTextFont(this, *(_DWORD *)(v2 + 16));
              if ( v83 )
                *((_BYTE *)v83 + 2) = v84;
            }
          }
        }
        goto LABEL_14;
      case 0x60u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 38);
        *((_DWORD *)this + 81) &= 0x2000000u;
        goto LABEL_14;
      case 0x61u:
        v14 = *(_WORD *)(v2 + 10) == 18;
LABEL_7:
        if ( v14 )
          goto LABEL_8;
        goto LABEL_14;
      case 0x62u:
        if ( (unsigned int)v10 <= 0xFF )
        {
          *((_DWORD *)this + 83) |= 0x2000000u;
          *((_BYTE *)this + 189) = v10;
        }
        goto LABEL_14;
      case 0x63u:
        if ( v251 )
          v69 = *(_QWORD *)(v245 + 48);
        else
          v69 = 0;
        if ( (*(_BYTE *)(v69 + 358) & 0x40) == 0 || *(_BYTE *)(v2 + 84) == 2 )
          goto LABEL_14;
        *(_BYTE *)(v2 + 84) = 2;
        v70 = -558;
        *(_BYTE *)(v2 + 86) = 0;
        v71 = tomHorzVert;
        goto LABEL_238;
      case 0x65u:
        if ( v251 )
          v72 = *(_QWORD *)(v245 + 48);
        else
          v72 = 0;
        if ( (*(_BYTE *)(v72 + 358) & 0x40) != 0 )
        {
          *(_BYTE *)(v2 + 84) = 5;
          *(_BYTE *)(v2 + 86) = 0;
          ++*((_BYTE *)this + 201);
          CRTFRead::StoreDestination(this, (struct STATE *)v2, 39);
          *((_BYTE *)this + 1647) = v10;
          *(_DWORD *)((char *)this + 1650) = 9645;
        }
        goto LABEL_14;
      case 0x66u:
        *((_WORD *)this + 825) = v10;
        goto LABEL_14;
      case 0x67u:
        *((_WORD *)this + 826) = v10;
        goto LABEL_14;
      case 0x68u:
        if ( !*(_QWORD *)(v2 + 32) )
          goto LABEL_14;
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 40);
        v70 = -555;
        v71 = *(unsigned __int8 *)(*(_QWORD *)(v2 + 32) + 84LL);
LABEL_238:
        CRTFRead::DelimitILSObject(this, v70, v71, 0);
        goto LABEL_14;
      case 0x69u:
        *((_DWORD *)this + 83) |= 0x20000000u;
        if ( v10 <= 255 )
          LOBYTE(v13) = v10;
        *((_BYTE *)this + 184) = v13;
        goto LABEL_14;
      case 0x6Au:
      case 0x6Bu:
      case 0x6Cu:
        *((_DWORD *)this + 83) |= 0x20000000u;
        *((_BYTE *)this + 184) = *(_BYTE *)v3 - 106;
        goto LABEL_14;
      case 0x6Du:
        v97 = *(_BYTE *)v8;
        *((_DWORD *)this + 83) |= 0x40000000u;
        *((_BYTE *)this + 186) = v97;
        goto LABEL_14;
      case 0x6Eu:
        v98 = *(_BYTE *)v8;
        *((_DWORD *)this + 83) |= 0x80000000;
        *((_BYTE *)this + 185) = v98;
        goto LABEL_14;
      case 0x6Fu:
      case 0x70u:
      case 0x71u:
        *((_DWORD *)this + 83) |= 0x10000000u;
        *((_BYTE *)this + 187) = (_BYTE)v6 - 111;
        goto LABEL_14;
      case 0x72u:
      case 0x73u:
      case 0x74u:
      case 0x75u:
      case 0x76u:
      case 0x77u:
      case 0x79u:
      case 0x7Bu:
        goto LABEL_296;
      case 0x78u:
        if ( (*((_WORD *)this + 760) & 0x1000) != 0 )
        {
LABEL_296:
          if ( *(_WORD *)(v2 + 10) != 18 )
          {
            v99 = 1 << ((_BYTE)v6 - 114);
            *((_DWORD *)this + 83) |= v99;
            v100 = *((_WORD *)this + 90) & ~(_WORD)v99;
            *((_WORD *)this + 90) = v100;
            if ( (*((_WORD *)this + 760) & 0x1000) == 0 || v10 )
              *((_WORD *)this + 90) = v99 | v100;
          }
        }
        goto LABEL_14;
      case 0x7Cu:
        goto LABEL_523;
      case 0x7Du:
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
        {
          if ( *((_BYTE *)this + 1658) )
          {
            v41 = 64;
LABEL_82:
            CRTFRead::HandleChar(this, v41);
            goto LABEL_14;
          }
          *((_WORD *)this + 822) |= 0x10u;
        }
        else if ( *(_WORD *)(v2 + 10) != 18 )
        {
          v41 = 11;
          goto LABEL_82;
        }
LABEL_14:
        result = *((unsigned int *)this + 31);
        *((_BYTE *)this + 1523) ^= (*((_BYTE *)this + 1523) ^ (32 * v248)) & 0x20;
        return result;
      case 0x7Eu:
        *((_DWORD *)this + 85) += v10 + *((_DWORD *)this + 87);
        *((_DWORD *)this + 101) |= 5u;
        *((_DWORD *)this + 87) = -v10;
        goto LABEL_14;
      case 0x7Fu:
      case 0x80u:
        v111 = *((_DWORD *)this + 101);
        if ( ((_WORD)v6 == 383) == ((*((_DWORD *)this + 84) & 0x1001) == 1) )
        {
          *((_DWORD *)this + 86) = v10;
          v112 = v111 | 2;
        }
        else
        {
          *((_DWORD *)this + 85) = v10 - *((_DWORD *)this + 87);
          v112 = v111 | 1;
        }
        *((_DWORD *)this + 101) = v112;
        goto LABEL_14;
      case 0x81u:
      case 0x82u:
      case 0x83u:
      case 0x84u:
      case 0x85u:
      case 0x86u:
        v113 = *((_BYTE *)this + 352) ^ (*(_BYTE *)v5 ^ *((_BYTE *)this + 352)) & 0xF;
        *((_DWORD *)this + 101) |= 8u;
        *((_BYTE *)this + 352) = v113;
        goto LABEL_14;
      case 0x87u:
        *((_DWORD *)this + 101) |= 0x40u;
        *((_DWORD *)this + 89) = v10;
        goto LABEL_14;
      case 0x88u:
        *((_DWORD *)this + 90) = v10;
        v49 = 128;
        goto LABEL_117;
      case 0x89u:
        v108 = -v10;
        if ( v10 > 0 )
          v108 = *((_DWORD *)this + 60);
        *((_DWORD *)this + 91) = v108;
        if ( !v10 || v10 == 1000 )
          v109 = 0;
        else
          v109 = (v10 <= 0) + 3;
        *((_BYTE *)this + 370) = v109;
        goto LABEL_116;
      case 0x8Au:
        if ( !v10 )
          goto LABEL_14;
        *((_BYTE *)this + 370) = 5;
        *((int *)this + 91) /= 12;
LABEL_116:
        v49 = 256;
LABEL_117:
        *((_DWORD *)this + 101) |= v49;
        goto LABEL_14;
      case 0x8Du:
        *((_WORD *)this + 135) = v10;
        if ( *(_WORD *)(v2 + 10) == 18 )
          goto LABEL_14;
        *((_BYTE *)this + 371) |= 1u;
        *((_WORD *)this + 184) = -1;
        v110 = 0;
        while ( v10 != *((unsigned __int8 *)this + v110 + 260) )
        {
          if ( (int)++v110 >= 10 )
            goto LABEL_338;
        }
        *((_BYTE *)this + 371) = 2 * v110 - 2;
        *((_WORD *)this + 184) = ~(_WORD)v110;
LABEL_338:
        *((_DWORD *)this + 101) |= 0xD7FFFDFF;
        goto LABEL_14;
      case 0x8Eu:
        *((_DWORD *)this + 84) &= ~1u;
        *((_DWORD *)this + 101) |= 0x10000u;
        goto LABEL_14;
      case 0x8Fu:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        *((_DWORD *)this + 101) |= 0x4000000u;
        *((_DWORD *)this + 84) |= 0x400u;
        *((_BYTE *)this + 1616) = 0;
        goto LABEL_14;
      case 0x90u:
        v107 = *((_QWORD *)this + 12);
        v246 = 1;
        v247 = 0;
        CTxtEdit::OrCharFlags(v107, &v246, 0);
        goto LABEL_165;
      case 0x91u:
      case 0x92u:
      case 0x93u:
      case 0x94u:
      case 0x95u:
      case 0x96u:
      case 0x97u:
      case 0x98u:
      case 0xA0u:
      case 0xA1u:
      case 0xA2u:
      case 0xA3u:
      case 0xA4u:
      case 0xA5u:
      case 0xA6u:
LABEL_165:
        v73 = 1 << (*v5 + 112);
        *((_DWORD *)this + 84) |= v73;
        *((_DWORD *)this + 101) |= v73 << 16;
        *((_DWORD *)this + 102) |= (unsigned __int16)v73;
        if ( (*(_BYTE *)(*((_QWORD *)this + 12) + 358LL) & 0x20) == 0 )
          *((_DWORD *)this + 102) &= 0xFFFFFFCF;
        goto LABEL_14;
      case 0xA7u:
      case 0xABu:
      case 0xACu:
      case 0xADu:
      case 0xAEu:
        goto LABEL_351;
      case 0xA8u:
      case 0xA9u:
      case 0xAAu:
        if ( (**((_BYTE **)&rgKeyword + 2 * *((__int16 *)this + 767)) | 0x20) != 0x74 )
          CRTFRead::CheckNotifyLowFiRTF(this, 0);
LABEL_351:
        *((_BYTE *)this + 1616) = *(_BYTE *)v5 + 89;
        goto LABEL_14;
      case 0xAFu:
        v123 = (unsigned int)CRTFRead::GetCellColorIndex(this) << 20;
        goto LABEL_361;
      case 0xB0u:
        v123 = (unsigned int)CRTFRead::GetCellColorIndex(this) << 25;
        goto LABEL_361;
      case 0xB1u:
        *((_DWORD *)this + 365) = v10 / 50;
        goto LABEL_14;
      case 0xB2u:
      case 0xB3u:
        v11 = *(_BYTE *)v5 + 79;
        goto LABEL_508;
      case 0xB5u:
        *((_BYTE *)this + 1618) |= 0x40u;
        goto LABEL_14;
      case 0xB6u:
      case 0xB7u:
      case 0xB8u:
        *((_DWORD *)this + 97) |= 1 << ((_BYTE)Block + 94);
        v114 = *((_DWORD *)this + 97);
        goto LABEL_347;
      case 0xB9u:
      case 0xBAu:
      case 0xBBu:
      case 0xBCu:
      case 0xBDu:
      case 0xBEu:
      case 0xBFu:
      case 0xC0u:
        v117 = *((_BYTE *)this + 1616);
        if ( v117 >= 4u )
          goto LABEL_14;
        v118 = (unsigned __int16)v6 - 441;
        v119 = 15;
        if ( v118 < 15 )
          v119 = v118;
        v120 = 4 * v117;
        if ( v119 <= 0 )
          LOWORD(v119) = 0;
        *((_WORD *)this + 193) = *((_WORD *)this + 193) & ~(15 << v120) | ((_WORD)v119 << v120);
        goto LABEL_153;
      case 0xC1u:
        if ( *((_BYTE *)this + 1616) < 4u )
        {
          v115 = CRTFRead::GetStandardColorIndex(this);
          v114 = *((_DWORD *)this + 97) & ~(31 << v116) | (v115 << v116);
          *((_DWORD *)this + 97) = v114;
LABEL_347:
          *((_DWORD *)this + 363) = v114;
        }
        else
        {
          CellColorIndex = CRTFRead::GetCellColorIndex(this);
          v123 = CellColorIndex << (5 * (*((_BYTE *)this + 1616) - v122));
LABEL_361:
          *((_DWORD *)this + 364) |= v123;
        }
        goto LABEL_14;
      case 0xC2u:
        v124 = *((_BYTE *)this + 1616);
        if ( v124 >= 4u )
        {
          v125 = CheckTwips(v10);
          *((_DWORD *)this + 400) |= v125 << (8 * v126 - 32);
        }
        else
        {
          if ( v10 > 0 )
          {
            v74 = (v10 + 3) / 5;
            if ( v74 >= 15 )
              v74 = 15;
          }
          else
          {
            v74 = 0;
          }
          if ( v74 <= 0 )
            LOWORD(v74) = 0;
          *((_WORD *)this + 192) = *((_WORD *)this + 192) & ~(15 << (4 * v124)) | ((_WORD)v74 << (4 * v124));
LABEL_153:
          *((_DWORD *)this + 101) |= 0x800u;
        }
        goto LABEL_14;
      case 0xC3u:
        v127 = *((_BYTE *)this + 1616);
        if ( v127 >= 4u )
          goto LABEL_14;
        if ( v10 < 300 )
          v67 = v10 / 20;
        else
          v67 = 15;
        v68 = 4 * v127;
        if ( v67 <= 0 )
          LOWORD(v67) = 0;
        *((_WORD *)this + 191) = *((_WORD *)this + 191) & ~(15 << v68) | ((_WORD)v67 << v68);
        goto LABEL_153;
      case 0xC4u:
        v128 = (unsigned __int16)CRTFRead::GetStandardColorIndex(this) << 11;
        v129 = 2047;
        goto LABEL_373;
      case 0xC5u:
        v128 = (unsigned __int16)CRTFRead::GetStandardColorIndex(this) << 6;
        v129 = -1985;
LABEL_373:
        *((_WORD *)this + 187) = v129 & *((_WORD *)this + 187) | v128;
        goto LABEL_370;
      case 0xC6u:
        *((_WORD *)this + 186) = v10;
        goto LABEL_370;
      case 0xC7u:
        if ( (*((_DWORD *)this + 30) & 0x8000) != 0 )
          goto LABEL_8;
        DocInfo = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
        v176 = DocInfo;
        if ( DocInfo )
        {
          v177 = (void *)*((_QWORD *)DocInfo + 11);
          if ( v177 )
          {
            CW32System::GlobalFree(v177);
            *((_QWORD *)v176 + 11) = 0;
          }
          v178 = (void *)*((_QWORD *)v176 + 12);
          if ( v178 )
          {
            DeleteObject(v178);
            *((_QWORD *)v176 + 12) = 0;
          }
          v179 = *((_QWORD *)v176 + 13);
          if ( v179 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v179 + 16LL))(v179);
            *((_QWORD *)v176 + 13) = 0;
          }
          *((_DWORD *)v176 + 32) = -9999999;
          *(_DWORD *)(v2 + 4) |= 4u;
        }
        goto LABEL_14;
      case 0xC8u:
      case 0xC9u:
      case 0xCAu:
      case 0xCBu:
      case 0xCCu:
      case 0xCDu:
      case 0xCEu:
      case 0xCFu:
      case 0xD0u:
      case 0xD1u:
      case 0xD2u:
      case 0xD3u:
        *((_WORD *)this + 187) &= 0xFFC0u;
        *((_WORD *)this + 187) |= (_WORD)v6 - 455;
LABEL_370:
        *((_DWORD *)this + 101) |= v12;
        goto LABEL_14;
      case 0xD4u:
        goto LABEL_302;
      case 0xD5u:
        *((_BYTE *)this + 1612) = 4;
LABEL_302:
        v101 = *((_BYTE *)this + 1523);
        if ( (v101 & 0x10) != 0 )
        {
          *((_WORD *)this + 822) |= 2u;
          *((_WORD *)this + 190) = v10;
          *((_BYTE *)this + 1523) = v101 & 0xEF;
          *((_DWORD *)this + 101) |= 0x4000u;
          if ( *(_WORD *)(v2 + 10) == 22 )
          {
            v102 = *((_DWORD *)this + 18);
            if ( v102 > 0 && *((_WORD *)this + 98) <= 8u )
            {
              v103 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v102 - 1);
              v103[5 * v104 + 7] = v10;
            }
          }
        }
        else
        {
          if ( (v101 & 4) != 0 && !*((_BYTE *)this + 199) )
            CRTFRead::DelimitRow(this, &szRowStart);
          if ( *((int *)this + 103) < 32 && (unsigned int)v10 < 0x1000000 )
          {
            v105 = *((unsigned __int8 *)this + 1613);
            v106 = *((unsigned __int8 *)this + 1612);
            LOBYTE(Block) = *((_BYTE *)this + 412);
            if ( !(unsigned int)AddTabHelper(
                                  v10 & 0xFFFFFF,
                                  v106,
                                  v105,
                                  (int *)this + 109,
                                  252,
                                  (unsigned __int8 *)&Block) )
            {
              *((_DWORD *)this + 101) |= 0x10u;
              *((_DWORD *)this + 103) = (unsigned __int8)Block;
              if ( *((_BYTE *)this + 1612) || *((_BYTE *)this + 1613) )
                CTxtEdit::OnSetTypographyOptions(*((CTxtEdit **)this + 12), 1u, 1);
            }
          }
          *((_WORD *)this + 806) = 0;
          *((_DWORD *)this + 105) = 0;
        }
        goto LABEL_14;
      case 0xD6u:
        v5 = v3;
        goto LABEL_320;
      case 0xD7u:
      case 0xD8u:
      case 0xD9u:
      case 0xDAu:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
LABEL_320:
        *((_BYTE *)this + 1613) = *(_BYTE *)v5 + 43;
        goto LABEL_14;
      case 0xDBu:
      case 0xDCu:
      case 0xDDu:
        *((_BYTE *)this + 1612) = *(_BYTE *)v3 + 38;
        goto LABEL_14;
      case 0xDEu:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 11) )
          goto LABEL_14;
        *(_DWORD *)(v2 + 4) &= ~1u;
        *((_WORD *)this + 188) = 0;
        goto LABEL_432;
      case 0xDFu:
        if ( *(_WORD *)(v2 + 10) == 11 )
          *(_WORD *)(v2 + 8) = v10;
        goto LABEL_14;
      case 0xE0u:
        if ( *((int *)this + 395) >= 0 )
          *((_WORD *)this + 804) = 0;
        *v5 = 483;
        goto LABEL_446;
      case 0xE1u:
        CRTFRead::ContinueList(this);
        goto LABEL_14;
      case 0xE2u:
        if ( (unsigned int)(v10 - 1) <= 8 )
        {
          *((_WORD *)this + 804) &= 0xFB0Fu;
          *((_WORD *)this + 804) |= 16 * (v10 - 1);
        }
        goto LABEL_14;
      case 0xE3u:
      case 0xE4u:
        *((_WORD *)this + 804) &= 0xFFFCu;
        *((_WORD *)this + 804) |= (_WORD)v6 - 482;
        goto LABEL_14;
      case 0xE5u:
        *((_WORD *)this + 804) = 0;
        goto LABEL_446;
      case 0xE6u:
      case 0xE7u:
      case 0xE8u:
      case 0xE9u:
      case 0xEAu:
      case 0xEBu:
      case 0xECu:
      case 0xEDu:
      case 0xEEu:
      case 0xEFu:
      case 0xF0u:
      case 0xF1u:
      case 0xF2u:
      case 0xF3u:
      case 0xF4u:
      case 0xF5u:
      case 0xF6u:
      case 0xF7u:
      case 0xF8u:
      case 0xF9u:
      case 0xFAu:
      case 0xFBu:
        if ( *((_WORD *)this + 196) != 1 || (*(_BYTE *)(v2 + 4) & 1) == 0 )
        {
LABEL_446:
          if ( *(_WORD *)(v2 + 10) == 11 )
          {
            v165 = *((_WORD *)this + 122);
            *((_DWORD *)this + 101) |= 0x20u;
            *((_WORD *)this + 196) = v165 - 484;
            *(_DWORD *)(v2 + 4) |= 1u;
          }
        }
        goto LABEL_14;
      case 0xFCu:
        if ( (unsigned int)(*(__int16 *)(v2 + 10) - 8) <= 2
          && ((*(_BYTE *)(v2 + 4) & 0x20) == 0
           || !(unsigned int)CTxtPtr::IsAfterHardEOP((CTxtPtr *)(*((_QWORD *)this + 13) + 24LL))) )
        {
          goto LABEL_8;
        }
        *((_WORD *)this + 760) &= ~0x400u;
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 12) )
          goto LABEL_14;
        if ( *((char *)this + 1523) < 0 )
        {
          v166 = *((_DWORD *)this + 395);
          if ( v166 != -1 )
          {
            v167 = (CTxtRange *)*((_QWORD *)this + 13);
            if ( v166 < *((_DWORD *)v167 + 10) )
            {
              CTxtRange::SetCp(v167, v166, 1);
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, int, _DWORD))(**((_QWORD **)this + 13)
                                                                                                  + 888LL))(
                *((_QWORD *)this + 13),
                0,
                0,
                0,
                0,
                0,
                224,
                0);
            }
          }
        }
        *((_BYTE *)this + 1523) |= 0x80u;
LABEL_378:
        *((_DWORD *)this + 395) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        goto LABEL_14;
      case 0xFDu:
        if ( *(_WORD *)(v2 + 10) != 11 )
          goto LABEL_14;
        *((_WORD *)this + 188) = v10;
LABEL_432:
        *((_DWORD *)this + 101) |= 0x8000u;
        goto LABEL_14;
      case 0xFEu:
      case 0xFFu:
      case 0x129u:
      case 0x1E6u:
        goto LABEL_8;
      case 0x100u:
        goto LABEL_414;
      case 0x101u:
        v136 = *((_BYTE *)this + 1644);
        *((_BYTE *)this + 1523) &= ~0x10u;
        *((_BYTE *)this + 1523) |= ~(8 * v136) & 0x10;
        goto LABEL_14;
      case 0x102u:
        v50 = *((_DWORD *)this + 18);
        if ( v50 && (unsigned int)v10 <= 2 && *((_WORD *)this + 98) <= 8u )
        {
          v51 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v50 - 1);
          v53 = 5 * (v52 + 1);
          v51[v53] &= 0xFFFCu;
          v51[v53] |= v10;
        }
        goto LABEL_14;
      case 0x103u:
        v54 = *((_DWORD *)this + 18);
        if ( v54 && (unsigned int)v10 <= 0xFF && *((_WORD *)this + 98) <= 8u )
        {
          v55 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v54 - 1);
          if ( v10 < 5 )
          {
            LOWORD(v10) = *((unsigned __int8 *)&dword_1802ACABC + v10);
          }
          else if ( v10 == 23 )
          {
            LOWORD(v10) = 1;
          }
          v55[5 * v56 + 4] = v10;
        }
        goto LABEL_14;
      case 0x104u:
        v140 = *((_DWORD *)this + 18);
        if ( v140 && *((_WORD *)this + 98) <= 8u )
        {
          v141 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v140 - 1);
          v141[5 * v142 + 6] = v10;
        }
        goto LABEL_14;
      case 0x105u:
        CArrayBase::ArAdd((CRTFRead *)((char *)this + 64), 1, 0);
        *((_WORD *)this + 98) = -1;
        goto LABEL_14;
      case 0x106u:
        v145 = (CRTFRead *)((char *)this + 64);
        v146 = *((_DWORD *)this + 18);
        if ( *(_WORD *)(v2 + 10) == 22 )
        {
          if ( v146 > 0 )
            *(_DWORD *)CArrayBase::Elem(v145, v146 - 1) = v10;
        }
        else
        {
          v147 = *((__int16 *)this + 754);
          if ( v147 >= v146 )
          {
            CArrayBase::Clear(v145, 2);
            goto LABEL_14;
          }
          if ( (v147 & 0x8000u) == 0 )
          {
            v148 = CArrayBase::Elem(v145, 0);
            for ( i = 0; ; ++i )
            {
              if ( i >= v149 )
                goto LABEL_408;
              if ( v10 == *v148 )
                break;
              v148 += 25;
            }
            v151 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), *((__int16 *)this + 754));
            v151[2] = v152;
LABEL_408:
            ++*((_WORD *)this + 754);
            goto LABEL_14;
          }
        }
        goto LABEL_14;
      case 0x107u:
        v131 = *((_DWORD *)this + 18);
        if ( v131 )
        {
          v132 = *((__int16 *)this + 98);
          if ( (unsigned int)(v132 + 1) <= 8 )
          {
            *((_WORD *)this + 98) = v132 + 1;
            v133 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v131 - 1);
            v135 = 5 * v134;
            *(_DWORD *)&v133[v135 + 10] = 0x10000;
            v133[v135 + 13] = -1;
          }
        }
        goto LABEL_14;
      case 0x108u:
        if ( !*((_DWORD *)this + 18) )
          goto LABEL_8;
        v130 = 25;
LABEL_375:
        if ( CRTFRead::StoreDestination(this, (struct STATE *)v2, v130) )
          goto LABEL_378;
        goto LABEL_14;
      case 0x109u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 23);
        *((_WORD *)this + 754) = 0;
        goto LABEL_14;
      case 0x10Au:
        v143 = *((_DWORD *)this + 18);
        if ( v143 )
        {
          v144 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v143 - 1);
          v144[6] |= 1u;
        }
        goto LABEL_14;
      case 0x10Bu:
        v57 = 22;
        goto LABEL_135;
      case 0x10Cu:
        v130 = 24;
        goto LABEL_375;
      case 0x10Du:
        if ( v10 < 1 )
          goto LABEL_14;
        if ( v10 > *((_DWORD *)this + 18) )
          goto LABEL_14;
        if ( *(_WORD *)(v2 + 10) == 23 )
          goto LABEL_14;
        *((_WORD *)this + 755) = *((_WORD *)this + 754);
        *((_WORD *)this + 754) = *((_WORD *)CArrayBase::Elem((CRTFRead *)((char *)this + 64), v10 - 1) + 2);
        if ( *((char *)this + 1523) < 0 )
          goto LABEL_14;
        v10 = 0;
        *((_WORD *)this + 804) = 0;
LABEL_414:
        if ( *((char *)this + 1523) >= 0 && (unsigned int)v10 <= 8 )
        {
          v153 = *((__int16 *)this + 754);
          if ( *((__int16 *)this + 754) >= 0 && v153 < *((_DWORD *)this + 18) )
          {
            *((_WORD *)this + 98) = v10;
            v154 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v153);
            v156 = v154;
            if ( (v154[3] & 2) != 0 )
            {
              *((_WORD *)this + 196) = v155;
            }
            else
            {
              v157 = 5LL * v10;
              v158 = v154[5 * v10 + 4];
              Block = (void *)v157;
              *((_WORD *)this + 196) = v158;
              if ( v158 == -4 )
              {
                *((_WORD *)this + 196) = 1;
                CRTFRead::CheckNotifyLowFiRTF(this, 0);
                v157 = (__int64)Block;
                v155 = 0;
              }
              *((_WORD *)this + 804) &= 0x400u;
              if ( *((_WORD *)this + 196) > 6u )
              {
                *((_WORD *)this + 196) = v155;
                *((_BYTE *)v156 + 6) |= 2u;
              }
              else
              {
                v159 = (__int16)v156[v157 + 7];
                v160 = (_WORD *)((char *)this + 380);
                v161 = *((_DWORD *)this + 85);
                if ( v159 > v161 && *v160 == v155 )
                {
                  v162 = v159 - v161;
                  *v160 = v162;
                  *((_DWORD *)this + 101) |= 0x4000u;
                  *(_WORD *)(v2 + 8) = v162;
                }
                else
                {
                  v163 = (unsigned __int16)*v160;
                  if ( v163 > v161 )
                    *(_WORD *)(v2 + 8) = v163 - *((_WORD *)this + 170);
                }
                *((_WORD *)this + 804) |= v156[v157 + 5] | (unsigned __int16)(16 * v10);
                v164 = v156[v157 + 6];
                *((_DWORD *)this + 101) |= 0xA020u;
                *((_WORD *)this + 188) = v164;
              }
            }
          }
        }
        goto LABEL_14;
      case 0x10Eu:
        v137 = *((_DWORD *)this + 18);
        if ( v137 && *((_WORD *)this + 98) <= 8u )
        {
          v138 = CArrayBase::Elem((CRTFRead *)((char *)this + 64), v137 - 1);
          v138[5 * v139 + 4] = -4;
        }
        goto LABEL_14;
      case 0x10Fu:
        v248 = *((_BYTE *)this + 1523) >> 5;
        goto LABEL_14;
      case 0x110u:
        if ( (unsigned __int16)(*(_WORD *)(v2 + 10) - 14) <= 2u )
          goto LABEL_8;
        v57 = 8;
        goto LABEL_135;
      case 0x111u:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 9) )
          goto LABEL_14;
        v180 = (const unsigned __int16 *)&dword_1802ACAFC;
        goto LABEL_544;
      case 0x112u:
        if ( (*((_BYTE *)this + 1523) & 0x20) != 0
          && !(unsigned int)CRTFRead::AddText(this, &dword_1802ACAEC, 2, 0, 0, 0) )
        {
          *(_WORD *)(v2 + 10) = 10;
        }
        goto LABEL_14;
      case 0x113u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 18);
        *((_WORD *)this + 135) = 0;
        goto LABEL_14;
      case 0x114u:
        CRTFRead::CheckNotifyLowFiRTF(this, 0);
        if ( !*(_WORD *)(*(_QWORD *)(v2 + 40) + 56LL) )
        {
          *((_WORD *)this + 760) &= ~0x400u;
LABEL_523:
          CRTFRead::HandleEndOfPara(this);
        }
        goto LABEL_14;
      case 0x116u:
        v57 = 16;
        goto LABEL_135;
      case 0x117u:
        if ( *(_WORD *)(v2 + 10) > 0x1Cu )
          goto LABEL_209;
        v169 = 352326145;
        if ( !_bittest(&v169, *(__int16 *)(v2 + 10)) )
          goto LABEL_209;
        if ( !*((_DWORD *)this + 106) && !*((_BYTE *)this + 199) )
        {
          CRTFRead::DelimitRow(this, &szRowStart);
          if ( *(_WORD *)(v2 + 10) == 24 || *(_WORD *)(v2 + 10) == 12 )
            *((_DWORD *)this + 395) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        }
        *((_BYTE *)this + 1523) &= ~4u;
        goto LABEL_14;
      case 0x118u:
        if ( (*((_BYTE *)this + 1523) & 4) != 0 && !*((_BYTE *)this + 199) )
          CRTFRead::DelimitRow(this, &szRowStart);
        goto LABEL_472;
      case 0x119u:
LABEL_472:
        CRTFRead::HandleCell(this);
        goto LABEL_14;
      case 0x11Au:
        if ( (unsigned int)v10 > 0xFF )
          v10 = 108;
        *((_DWORD *)this + 104) = v10;
        goto LABEL_14;
      case 0x11Bu:
        CRTFRead::HandleCellx(this, v10);
        goto LABEL_14;
      case 0x11Cu:
        goto LABEL_495;
      case 0x11Du:
        *((_WORD *)this + 760) |= 0x800u;
LABEL_495:
        if ( *((_BYTE *)this + 199) )
        {
          while ( *((_DWORD *)this + 106) < *((_DWORD *)this + 105) && CRTFRead::HandleCell(this) )
            ;
          CRTFRead::DelimitRow(this, &szRowEnd);
          if ( !*((_BYTE *)this + 199) )
          {
            if ( *((__int16 *)this + 805) >= 0 )
              (*(void (__fastcall **)(CTabsArray *))(*(_QWORD *)qword_1802DF5B8 + 8LL))(qword_1802DF5B8);
            *((_WORD *)this + 805) = -1;
          }
          if ( (*((_WORD *)this + 760) & 0x800) != 0 && !*((_BYTE *)this + 199) )
          {
            CRTFRead::InitializeTableRowParms(this);
            *((_DWORD *)this + 106) = 0;
          }
        }
        goto LABEL_14;
      case 0x11Eu:
        v170 = *(_DWORD *)(*((_QWORD *)this + 12) + 176LL);
        if ( (v170 & 0x10) != 0
          || *((char *)this + 201) + *((char *)this + 202)
          || *(_WORD *)(v2 + 10) == 12
          || *(_WORD *)(v2 + 10) == 24 )
        {
          goto LABEL_209;
        }
        if ( *((_WORD *)this + 123) == 527 )
          goto LABEL_8;
        v171 = *((_DWORD *)this + 394);
        if ( v171 == *(_DWORD *)(*((_QWORD *)this + 13) + 40LL)
          && *((_DWORD *)this + 80) != v171
          && !((v170 & 0x80000) != 0
             ? CRTFRead::HandleText(this, byte_1802A3221, 1, (int)v8)
             : (unsigned int)CRTFRead::HandleChar(this, 0xDu)) )
        {
          *((_DWORD *)this + 80) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        }
        CRTFRead::InitializeTableRowParms(this);
        *((_BYTE *)this + 1523) |= 4u;
        *((_DWORD *)this + 109) = 0;
        goto LABEL_14;
      case 0x11Fu:
        *((_DWORD *)this + 401) = v10;
        goto LABEL_14;
      case 0x120u:
        *((_DWORD *)this + 362) = v10;
        goto LABEL_14;
      case 0x121u:
      case 0x122u:
        *((_BYTE *)this + 1622) = *(_BYTE *)v5 - 31;
        goto LABEL_14;
      case 0x123u:
        *((_BYTE *)this + 1618) |= 0x20u;
        goto LABEL_14;
      case 0x124u:
        v173 = 16;
        goto LABEL_511;
      case 0x125u:
LABEL_508:
        *((_BYTE *)this + 1618) |= v11;
        goto LABEL_14;
      case 0x126u:
        v173 = 8;
LABEL_511:
        *((_BYTE *)this + 1618) |= v173;
        goto LABEL_14;
      case 0x127u:
        if ( (*(_BYTE *)(v2 + 4) & 8) != 0 )
          goto LABEL_14;
        if ( !v10 )
          goto LABEL_124;
        if ( *(_WORD *)(v2 + 10) > 0x1Au )
          goto LABEL_16;
        v174 = 67109377;
        if ( !_bittest(&v174, *(__int16 *)(v2 + 10))
          || v10 > 127
          || (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x10) != 0 )
        {
          goto LABEL_16;
        }
        *((_WORD *)this + 735) = -1;
        *((_DWORD *)this + 105) = 0;
        while ( v10 > *((char *)this + 199) && (unsigned int)CRTFRead::DelimitRow(this, &szRowStart) )
          ;
LABEL_124:
        *((_WORD *)this + 760) |= 0x800u;
        goto LABEL_14;
      case 0x128u:
        v57 = 26;
        goto LABEL_135;
      case 0x12Au:
        *((_BYTE *)this + 1523) |= 2u;
        goto LABEL_14;
      case 0x12Bu:
        CRTFRead::HandleUN(this, (struct STATE *)v2);
        goto LABEL_14;
      case 0x12Cu:
        if ( (unsigned int)v10 <= 2 )
          *(_WORD *)v2 = v10;
        goto LABEL_14;
      case 0x12Du:
        *((_WORD *)this + 822) |= 1u;
        goto LABEL_14;
      case 0x130u:
      case 0x131u:
      case 0x133u:
      case 0x134u:
        goto LABEL_32;
      case 0x132u:
        *(_DWORD *)(v2 + 4) ^= (*(_DWORD *)(v2 + 4) ^ (16 * *((unsigned __int8 *)this + 203))) & 0x10;
LABEL_32:
        v21 = *(_BYTE *)v3 - 47;
        *(_BYTE *)(v2 + 23) = v21;
        if ( (unsigned int)(v21 - 1) <= 1 )
        {
          v22 = *(_WORD *)(v2 + 4LL * v21 + 60);
          if ( v22 != -1 )
          {
            CRTFRead::SelectCurrentFont(this, v22, 0);
            CRTFRead::HandleNumber(this);
            v23 = *(char *)(v2 + 23);
            v10 = *(__int16 *)(v2 + 4 * v23 + 62);
            if ( *(_WORD *)(v2 + 4 * v23 + 62) )
            {
              v3 = v250;
LABEL_36:
              v24 = -v10;
              if ( v10 > 0 )
                v24 = v10;
              if ( v24 <= 10000 )
              {
                *(_WORD *)(v2 + 4LL * *(char *)(v2 + 23) + 62) = v10;
                *((_DWORD *)this + 81) |= 0x80000000;
                v25 = *((_WORD *)this + 822);
                *((_WORD *)this + 68) = 10 * v10;
                if ( (v25 & 8) != 0 && *v3 == 298 )
                {
                  *((_WORD *)this + 828) = 10 * v10;
                  *((_WORD *)this + 822) = v25 & 0xFFF7;
                }
              }
            }
          }
        }
        goto LABEL_14;
      case 0x135u:
        *((_BYTE *)this + 1522) = 1;
        goto LABEL_14;
      case 0x137u:
        *((_BYTE *)this + 1522) = 2;
LABEL_181:
        v75 = *((_QWORD *)this + 12);
        v246 = 1;
        v247 = 0;
        CTxtEdit::OrCharFlags(v75, &v246, 0);
        goto LABEL_14;
      case 0x13Cu:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 14) )
          goto LABEL_14;
        v14 = (*((_DWORD *)this + 30) & 0x8000) == 0;
        p_Block = &Block;
        Block = 0;
        if ( !v14 )
          p_Block = 0;
        if ( !(unsigned int)CRTFRead::ReadRawText(v85, (char **)p_Block) )
          goto LABEL_251;
        v87 = Block;
        if ( !Block )
          goto LABEL_14;
        v88 = CTxtEdit::SetFollowingPunct(*((CTxtEdit **)this + 12), (char *)Block);
        goto LABEL_249;
      case 0x13Du:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 15) )
          goto LABEL_14;
        v14 = (*((_DWORD *)this + 30) & 0x8000) == 0;
        v91 = &Block;
        Block = 0;
        if ( !v14 )
          v91 = 0;
        if ( (unsigned int)CRTFRead::ReadRawText(v90, (char **)v91) )
        {
          v87 = Block;
          if ( !Block )
            goto LABEL_14;
          v88 = CTxtEdit::SetLeadingPunct(*((CTxtEdit **)this + 12), (char *)Block);
LABEL_249:
          if ( !v88 )
            goto LABEL_14;
          v89 = v87;
        }
        else
        {
LABEL_251:
          v89 = Block;
          if ( !Block )
            goto LABEL_14;
        }
        free(v89);
        goto LABEL_14;
      case 0x13Eu:
        if ( (*((_DWORD *)this + 30) & 0x8000) != 0 )
          goto LABEL_14;
        v92 = 1;
        goto LABEL_262;
      case 0x13Fu:
        v183 = *((_WORD *)this + 760);
        v184 = *((_WORD *)this + 822);
        if ( ((v183 & 1) == 0 || (v184 & 4) != 0) && (v183 & 4) == 0 )
        {
          *((_WORD *)this + 760) = v183 & 0xFFFE;
          *((_WORD *)this + 822) = v184 & 0xFFFB;
          goto LABEL_14;
        }
        *((_WORD *)this + 760) = v183 & 0xFFFE;
        *((_WORD *)this + 822) = v184 & 0xFFFB;
        goto LABEL_8;
      case 0x140u:
        v185 = (_WORD *)*((_QWORD *)this + 193);
        if ( v185 && (*v185 <= 4u || *v185 == 9) )
          goto LABEL_8;
        goto LABEL_14;
      case 0x141u:
        *((_WORD *)this + 760) |= 1u;
        *((_WORD *)this + 822) &= ~4u;
        goto LABEL_583;
      case 0x142u:
LABEL_583:
        if ( (*(_BYTE *)(v2 + 4) & 8) == 0 )
          CRTFRead::FreeRtfObject(this);
        v191 = *((_QWORD *)this + 38);
        *((_WORD *)this + 822) &= ~0x100u;
        if ( (unsigned int)(*(__int16 *)(v191 + 10) - 1) <= 6 )
          goto LABEL_209;
        v192 = 7;
        if ( *(_WORD *)v246 != 578 )
          v192 = 3;
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, v192) )
          goto LABEL_14;
        if ( !CRTFRead::CheckRtfObject(v193) )
          goto LABEL_87;
        *(_DWORD *)(*((_QWORD *)this + 193) + 36LL) = 100;
        *(_DWORD *)(*((_QWORD *)this + 193) + 32LL) = 100;
        *(_WORD *)(*((_QWORD *)this + 193) + 4LL) = 1;
        *(_WORD *)(*((_QWORD *)this + 193) + 6LL) = 1;
        *(_QWORD *)(*((_QWORD *)this + 193) + 72LL) = 0;
        *(_QWORD *)(*((_QWORD *)this + 193) + 80LL) = 0;
        **((_WORD **)this + 193) = -1;
        CRTFRead::CheckListText(this, *(struct STATE **)(v2 + 32));
        goto LABEL_14;
      case 0x143u:
      case 0x144u:
      case 0x145u:
      case 0x146u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 4LL * (int)Block - 2264) = v10;
        goto LABEL_14;
      case 0x147u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 24LL) = v10;
        goto LABEL_14;
      case 0x148u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 20LL) = v10;
        goto LABEL_14;
      case 0x149u:
        *(_DWORD *)(*((_QWORD *)this + 193) + 32LL) = v10;
        goto LABEL_14;
      case 0x14Au:
        *(_DWORD *)(*((_QWORD *)this + 193) + 36LL) = v10;
        goto LABEL_14;
      case 0x14Bu:
        *(_WORD *)(*((_QWORD *)this + 193) + 42LL) = v10;
        goto LABEL_14;
      case 0x14Cu:
        *(_WORD *)(*((_QWORD *)this + 193) + 40LL) = v10;
        goto LABEL_14;
      case 0x14Du:
        *((_WORD *)this + 822) &= 0xFE3Fu;
        *((_BYTE *)this + 1623) = 0;
        *((_QWORD *)this + 203) = 0;
        *((_QWORD *)this + 204) = 0;
        *((_DWORD *)this + 410) = -9999997;
        v57 = 29;
        goto LABEL_135;
      case 0x14Eu:
        *(_DWORD *)(*((_QWORD *)this + 193) + 28LL) = v10;
        goto LABEL_14;
      case 0x14Fu:
      case 0x150u:
      case 0x151u:
      case 0x152u:
      case 0x153u:
        **((_WORD **)this + 193) = (_WORD)v6 - 591;
        goto LABEL_619;
      case 0x154u:
        **((_WORD **)this + 193) = 9;
LABEL_619:
        *(_WORD *)(*((_QWORD *)this + 193) + 2LL) = v10;
        goto LABEL_14;
      case 0x155u:
        *((_DWORD *)this + 68) = v10;
        v196 = (_QWORD **)((char *)this + 208);
        **((_QWORD **)this + 26) = RTFGetBinaryDataFromStream;
        v197 = *((_DWORD *)this + 68);
        if ( v197 < 0 )
          goto LABEL_209;
        if ( v197 <= 125829120 )
        {
          v199 = (char *)this + 208;
        }
        else
        {
          v198 = *(_QWORD *)(*((_QWORD *)this + 12) + 240LL);
          if ( !v198 || !*(_QWORD *)(v198 + 24) )
          {
LABEL_209:
            *((_DWORD *)this + 31) = 16;
            goto LABEL_14;
          }
          v199 = (char *)this + 208;
        }
        switch ( *(_WORD *)(v2 + 10) )
        {
          case 6:
            v201 = CRTFRead::ObjectReadFromEditStream(this);
            *((_WORD *)this + 760) &= ~1u;
            *((_WORD *)this + 760) |= v201 != 0;
            break;
          case 7:
            CRTFRead::StaticObjectReadFromEditStream(this, v10);
            break;
          case 0x15:
            v200 = CRTFRead::BlobObjectReadFromEditStream((CTxtEdit **)this, v10);
            if ( v200 >= 0 )
            {
              *((_WORD *)this + 760) &= ~1u;
              *((_WORD *)this + 760) |= v200 != 0;
            }
            else
            {
              *((_DWORD *)this + 31) = 16;
            }
            break;
          default:
            goto LABEL_640;
        }
        v196 = (_QWORD **)v199;
LABEL_640:
        **v196 = RTFGetFromStream;
        goto LABEL_14;
      case 0x156u:
      case 0x157u:
        goto LABEL_458;
      case 0x158u:
        *(_WORD *)(*((_QWORD *)this + 193) + 4LL) = v10;
        goto LABEL_14;
      case 0x159u:
        *(_WORD *)(*((_QWORD *)this + 193) + 6LL) = v10;
        goto LABEL_14;
      case 0x15Au:
        *(_WORD *)(*((_QWORD *)this + 193) + 8LL) = v10;
        goto LABEL_14;
      case 0x15Bu:
      case 0x15Cu:
      case 0x15Du:
      case 0x15Eu:
        **((_WORD **)this + 193) = (_WORD)v6 - 598;
        v194 = (_WORD *)*((_QWORD *)this + 193);
        if ( *v194 == 8 && v10 == 1 )
          *v194 = 12;
        goto LABEL_14;
      case 0x15Fu:
        v57 = 4;
        goto LABEL_135;
      case 0x160u:
        if ( !CRTFRead::StoreDestination(this, (struct STATE *)v2, 6) )
          goto LABEL_14;
        if ( ((**((_WORD **)this + 193) - 8) & 0xFFFB) != 0 )
        {
          if ( (*((_DWORD *)this + 30) & 0x8000) == 0 && (unsigned int)CW32System::SkipObjectData()
            || **((_WORD **)this + 193) == 10 )
          {
            *((_WORD *)this + 822) |= 4u;
LABEL_8:
            if ( !(unsigned int)CRTFRead::SkipToEndOfGroup(this) )
            {
              if ( ((*(_WORD *)(v2 + 10) - 2) & 0xFFEF) == 0 )
                *(_WORD *)(v2 + 10) = 17;
LABEL_11:
              CRTFRead::HandleEndGroup(this);
            }
          }
        }
        else
        {
          *(_WORD *)(v2 + 10) = 21;
        }
        goto LABEL_14;
      case 0x161u:
      case 0x163u:
      case 0x165u:
        **((_WORD **)this + 193) = 10;
        goto LABEL_14;
      case 0x162u:
        v57 = 5;
        goto LABEL_135;
      case 0x164u:
        *(_BYTE *)(*((_QWORD *)this + 193) + 14LL) = 1;
        goto LABEL_14;
      case 0x166u:
        v195 = *((_WORD *)this + 760);
        if ( (v195 & 0x4000) == 0 && **((_WORD **)this + 193) != 10 && (v195 & 5) == 0 )
          goto LABEL_8;
        *(_WORD *)(v2 + 10) = 0;
        goto LABEL_14;
      case 0x167u:
        **((_WORD **)this + 193) = 11;
        goto LABEL_14;
      case 0x168u:
      case 0x169u:
        if ( (*(_BYTE *)(v2 + 4) & 4) == 0 )
          CRTFRead::CheckNotifyLowFiRTF(this, 1);
        *(_DWORD *)(v2 + 4) |= 8u;
        *((_DWORD *)this + 388) = 0;
        CRTFRead::CheckRtfObject(this);
        goto LABEL_14;
      case 0x16Au:
        *(_WORD *)(v2 + 10) = 27;
        goto LABEL_14;
      case 0x16Bu:
        if ( *((_QWORD *)this + 193) )
        {
          v186 = CW32System::MulDivFunc(v10, 127, 72);
          *(_WORD *)(v187 + 44) = v186;
        }
        goto LABEL_14;
      case 0x16Du:
        *(_WORD *)(v2 + 10) = 19;
        goto LABEL_14;
      case 0x16Eu:
        v188 = (__int16 *)*((_QWORD *)this + 193);
        if ( !v188 || (unsigned int)(*v188 - 3) > 1 )
          goto LABEL_14;
        goto LABEL_8;
      case 0x16Fu:
        *(_WORD *)(v2 + 10) = 28;
        goto LABEL_14;
      case 0x170u:
        if ( *((_QWORD *)this + 193) )
        {
          v189 = CW32System::MulDivFunc(v10, 127, 72);
          *(_WORD *)(v190 + 46) = v189;
        }
        goto LABEL_14;
      case 0x171u:
        *(_WORD *)(v2 + 10) = 20;
        goto LABEL_14;
      case 0x172u:
        if ( (unsigned int)(v10 - 1) <= 4 && v10 != 3 )
        {
          *((_DWORD *)this + 388) |= 0x200u;
          if ( v10 == 1 )
            *((_DWORD *)this + 388) |= 0x1000u;
        }
        goto LABEL_14;
      case 0x173u:
        *((_DWORD *)this + 388) |= 0x100u;
        goto LABEL_14;
      case 0x174u:
      case 0x175u:
      case 0x176u:
      case 0x177u:
      case 0x178u:
      case 0x179u:
      case 0x17Au:
      case 0x17Bu:
      case 0x17Cu:
      case 0x17Du:
      case 0x17Eu:
      case 0x17Fu:
      case 0x180u:
      case 0x181u:
      case 0x182u:
      case 0x183u:
      case 0x184u:
      case 0x185u:
      case 0x186u:
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
        {
          *(_BYTE *)(v2 + 86) = 0;
          v233 = *((unsigned __int16 *)this + 122);
          *(_WORD *)(v2 + 10) = 35;
          v234 = 41;
          *(_BYTE *)(v2 + 84) = *((_BYTE *)L"adee" + v233);
          *((_WORD *)this + 822) &= ~0x20u;
          ++*((_BYTE *)this + 201);
          v235 = *((_WORD *)this + 122);
          *((_BYTE *)this + 1647) = 0;
          *((_WORD *)this + 825) = *(&szRowStart + *(unsigned __int8 *)(v2 + 84));
          if ( v235 != 632 )
            v234 = 0;
          *((_WORD *)this + 826) = v234;
          *((_WORD *)this + 827) = 0;
          if ( v235 != 633 && v235 != 639 )
            LOBYTE(v13) = 0;
          *((_BYTE *)this + 1649) = v13;
        }
        goto LABEL_14;
      case 0x187u:
      case 0x188u:
        v239 = *(_QWORD *)(v2 + 32);
        if ( !v239
          || (unsigned int)(*(__int16 *)(v239 + 10) - 34) > 1
          || !CRTFRead::StoreDestination(this, (struct STATE *)v2, 30) )
        {
          goto LABEL_148;
        }
        v241 = *(_BYTE *)(*(_QWORD *)(v2 + 32) + 86LL);
        *((_BYTE *)this + 172) = *((_BYTE *)this + 201) + *((_BYTE *)this + 202);
        *((_BYTE *)this + 174) = v241;
        v242 = *(_BYTE *)(*(_QWORD *)(v2 + 32) + 84LL);
        *((_DWORD *)this + 82) |= 0x1000080u;
        *((_BYTE *)this + 173) = v242;
        if ( v242 != 20 )
          CRTFRead::CheckStartObject(this, v240);
        *((_BYTE *)this + 1659) = 0;
        goto LABEL_14;
      case 0x189u:
        v211 = *((_BYTE *)this + 203);
        if ( (v211 & 4) != 0 )
          goto LABEL_14;
        *((_DWORD *)this + 82) |= 0x8000000u;
        v212 = v211 | 4;
        *((_DWORD *)this + 32) = 0x8000000;
        goto LABEL_669;
      case 0x18Bu:
      case 0x18Cu:
        if ( (unsigned int)v10 <= 2 && (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v226 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v226 )
          {
            if ( *v5 == 651 )
              v227 = v10 << 16;
            else
              v227 = v10 << 18;
            v228 = -196609;
            if ( *v5 != 651 )
              v228 = -786433;
            *((_DWORD *)v226 + 47) = v227 | *((_DWORD *)v226 + 47) & v228;
          }
        }
        goto LABEL_14;
      case 0x190u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v214 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v214 )
          {
            *((_DWORD *)v214 + 47) &= 0xFFFFFFFC;
            if ( (unsigned int)(v10 - 3) <= 1 )
              *((_DWORD *)v214 + 47) |= (v10 != 3) + 2;
          }
        }
        goto LABEL_14;
      case 0x191u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v215 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          v216 = v215;
          if ( v215 )
          {
            *((_DWORD *)v215 + 47) &= 0xFFFFFCFF;
            if ( (unsigned int)(v10 - 1) <= 1 )
            {
              v217 = 256;
              if ( v10 != 1 )
                v217 = 768;
              *((_DWORD *)v216 + 47) |= v217;
            }
          }
        }
        goto LABEL_14;
      case 0x192u:
        goto LABEL_706;
      case 0x193u:
        v218 = (CTxtEdit *)*((_QWORD *)this + 12);
        if ( (*((_DWORD *)v218 + 70) & 0x200) != 0 )
          goto LABEL_14;
        v219 = *((_DWORD *)this + 2);
        CTxtEdit::GetDocInfo(v218);
        v220 = (__int16 *)CArrayBase::Elem(this, 0);
        v222 = 0;
        if ( v219 <= 0 )
          goto LABEL_14;
        while ( v10 != *v220 )
        {
          v220 += 40;
          if ( ++v222 >= v219 )
            goto LABEL_14;
        }
        if ( v221 )
        {
          FontOptions = (const struct CFontOptions *)CTxtEdit::GetFontOptions(*((_QWORD *)this + 12), &v246);
          CDocInfo::SetMathFont(v225, (const unsigned __int16 *)(v224 + 6), FontOptions);
          *((_WORD *)this + 102) = v10;
        }
        goto LABEL_14;
      case 0x194u:
        if ( v10 <= 4 )
        {
          *((_BYTE *)this + 352) &= 0xFu;
          *((_BYTE *)this + 352) |= 16 * (_BYTE)v10;
          *((_DWORD *)this + 102) |= 0x1000000u;
        }
        goto LABEL_14;
      case 0x196u:
        if ( CTxtEdit::FDisableMath(*((CTxtEdit **)this + 12)) )
          goto LABEL_8;
        if ( (*((_BYTE *)this + 203) & 1) != 0 )
          goto LABEL_14;
        *((_DWORD *)this + 82) |= 0x10000000u;
        *((_DWORD *)this + 32) = 0x10000000;
        v209 = *((_WORD *)this + 102);
        if ( v209 == -1 )
        {
          CW32System::IsDefaultFontDefined(0x33u, -1, 0, (__int16 *)this + 67, v243, (const struct IDpiAccessor *)v244);
          *((_BYTE *)this + 133) = v210;
          *((_DWORD *)this + 81) |= 0x20000000u;
        }
        else
        {
          CRTFRead::SelectCurrentFont(this, v209, 0);
          v210 = 0;
        }
        *((_BYTE *)this + 203) |= 1u;
        *((_WORD *)this + 822) |= 8u;
        *((_WORD *)this + 828) = v210;
        *((_BYTE *)this + 1659) = v210;
        v57 = 36;
        goto LABEL_135;
      case 0x197u:
        *((_BYTE *)this + 352) &= 0xFu;
        v57 = 37;
        *((_DWORD *)this + 102) |= 0x1000000u;
        goto LABEL_135;
      case 0x199u:
        if ( CTxtEdit::FDisableMath(*((CTxtEdit **)this + 12)) )
          goto LABEL_14;
LABEL_458:
        v168 = 1;
        goto LABEL_460;
      case 0x19Du:
        v9 = 4;
        goto LABEL_706;
      case 0x19Eu:
        v9 = 8;
        goto LABEL_706;
      case 0x19Fu:
        v9 = 1024;
LABEL_706:
        if ( (unsigned int)v10 <= 1 && (*((_DWORD *)this + 30) & 0x8000) == 0 )
        {
          v230 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v230 )
          {
            *((_DWORD *)v230 + 47) &= ~v9;
            if ( v10 )
              *((_DWORD *)v230 + 47) |= v9;
          }
        }
        goto LABEL_14;
      case 0x1A0u:
      case 0x1A1u:
      case 0x1A2u:
      case 0x1A3u:
      case 0x1A4u:
      case 0x1A5u:
      case 0x1A6u:
      case 0x1A7u:
      case 0x1A8u:
        if ( (unsigned int)IsValidTwip(v10) )
        {
          v229 = CTxtEdit::GetDocInfo(*((CTxtEdit **)this + 12));
          if ( v229 )
            *((_DWORD *)v229 + (unsigned __int16)*v5 - 624) = v10;
        }
        goto LABEL_14;
      case 0x1ADu:
        v236 = *(_QWORD *)(v2 + 32);
        if ( !v236 || *(_WORD *)(v236 + 10) != 35 )
          goto LABEL_148;
        *(_BYTE *)(v2 + 86) = *(_BYTE *)(v236 + 86);
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 34);
        CRTFRead::CheckStartObject(v238, v237);
        goto LABEL_14;
      case 0x1B0u:
        if ( *(_BYTE *)(v2 + 85) )
          goto LABEL_14;
        v180 = L"&";
        v181 = 1;
        goto LABEL_545;
      case 0x1B2u:
        v57 = 31;
        goto LABEL_135;
      case 0x1B5u:
        if ( (unsigned int)v10 > 0x7D )
          goto LABEL_148;
        if ( *(_BYTE *)(v2 + 85) )
          goto LABEL_14;
        if ( !*((_BYTE *)this + 1658) )
          *((_BYTE *)this + 1658) = v10 + 1;
        v180 = L"@&";
LABEL_544:
        v181 = 2;
LABEL_545:
        CRTFRead::AddText(this, v180, v181, 0, 0, 0);
        goto LABEL_14;
      case 0x1B7u:
        v213 = *((_BYTE *)this + 203);
        if ( (v213 & 2) == 0 )
        {
          *((_DWORD *)this + 82) |= 0x20000000u;
          v212 = v213 | 2;
          *((_DWORD *)this + 32) = 0x20000000;
LABEL_669:
          *((_BYTE *)this + 203) = v212;
        }
        goto LABEL_14;
      case 0x1B9u:
        v231 = 0;
        if ( (unsigned int)v10 <= 0xC )
          v231 = *((_DWORD *)this + 60);
        *((_BYTE *)this + 1646) = v231;
        goto LABEL_14;
      case 0x1BAu:
        v232 = 0;
        if ( (unsigned int)(v10 - 1) <= 2 )
          v232 = *((_DWORD *)this + 60);
        *((_BYTE *)this + 1646) |= 16 * v232;
        goto LABEL_14;
      case 0x1BBu:
        *((_BYTE *)this + 1648) = v10;
        *((_WORD *)this + 822) |= 0x20u;
        goto LABEL_14;
      case 0x1BCu:
      case 0x1BDu:
      case 0x1BEu:
      case 0x1BFu:
      case 0x1C1u:
      case 0x1C2u:
      case 0x1C3u:
      case 0x1C4u:
      case 0x1C5u:
      case 0x1C6u:
      case 0x1C9u:
      case 0x1CAu:
        goto LABEL_734;
      case 0x1C0u:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, 32);
        *((_DWORD *)this + 32) = 0;
        *((_DWORD *)this + 81) |= 3u;
        goto LABEL_14;
      case 0x1C8u:
        *((_BYTE *)this + 1647) = 1;
LABEL_734:
        v57 = 33;
LABEL_135:
        CRTFRead::StoreDestination(this, (struct STATE *)v2, v57);
        goto LABEL_14;
      case 0x1D8u:
        *((_WORD *)this + 825) = 0;
        goto LABEL_14;
      case 0x1D9u:
        *((_WORD *)this + 826) = 0;
        goto LABEL_14;
      case 0x1DAu:
        *((_WORD *)this + 827) = 0;
        goto LABEL_14;
      case 0x1E7u:
        if ( (*((_DWORD *)this + 30) & 0x8000) == 0 && (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x80000) == 0 )
        {
          v92 = *((_DWORD *)this + 60);
LABEL_262:
          CRTFRead::HandleSTextFlow(this, v92);
        }
        goto LABEL_14;
      case 0x1E8u:
        if ( v10 > 0 )
        {
          *((_DWORD *)this + 32) &= ~0x40000000u;
          *((_DWORD *)this + 81) |= 0x40000000u;
          Color = *((_DWORD *)&rgcrRevisions + (((_BYTE)v10 - 1) & 7));
LABEL_92:
          *((_DWORD *)this + 35) = Color;
        }
        goto LABEL_14;
      case 0x1E9u:
        if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 272LL) & 0x2000000) == 0 )
          goto LABEL_14;
        v204 = (__int64 *)((char *)this + 1584);
        if ( *((_QWORD *)this + 198) )
        {
          v206 = (_QWORD *)((char *)this + 1584);
        }
        else
        {
          v205 = mallocTypeZeroed<long>(32, v6, (v251 - 8) & -(__int64)(v251 != 0));
          *v204 = v205;
          if ( !v205 )
            goto LABEL_90;
          *((_QWORD *)this + 199) = 8;
          v206 = (_QWORD *)((char *)this + 1584);
        }
        v207 = *((_DWORD *)this + 398);
        *((_DWORD *)this + 398) = v207 - 1;
        if ( v207 > 0 )
        {
          v206 = (_QWORD *)((char *)this + 1584);
        }
        else
        {
          v208 = _o_realloc(*v204, 4LL * (*((_DWORD *)this + 399) + 8));
          if ( !v208 )
            goto LABEL_90;
          *v204 = v208;
          *((_DWORD *)this + 398) = 7;
        }
        *(_DWORD *)(*v206 + 4LL * (int)(*((_DWORD *)this + 399))++) = *(_DWORD *)(*((_QWORD *)this + 13) + 40LL);
        goto LABEL_14;
      case 0x1EAu:
        v168 = 0;
LABEL_460:
        CRTFRead::CheckNotifyLowFiRTF(this, v168);
        goto LABEL_8;
      default:
        if ( v7 <= 0x1EC )
          goto LABEL_14;
        if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 176LL) & 0x80000) == 0
          || (unsigned int)(unsigned __int16)v6 - 8216 > 5 )
        {
          goto LABEL_79;
        }
        if ( (_WORD)v6 == 8216 )
          goto LABEL_752;
        if ( (_WORD)v6 == 8217 )
        {
          v5 = (_WORD *)((char *)this + 244);
LABEL_752:
          *v5 = 39;
        }
        else if ( (unsigned __int16)(*((_WORD *)this + 122) - 8220) <= 1u )
        {
          *((_WORD *)this + 122) = 34;
        }
LABEL_79:
        if ( CRTFRead::IsLowMergedCell(this) )
          goto LABEL_14;
        if ( (*((_DWORD *)this + 81) & 0xA000000) == 0xA000000
          && (unsigned int)CW32System::IsBiDiLcid(*((_DWORD *)this + 38))
          && !*((_BYTE *)this + 132) )
        {
          *((_BYTE *)this + 132) = CCharFormat::CharRepFromLang((CRTFRead *)((char *)this + 128));
        }
        v41 = *((_WORD *)this + 122);
        goto LABEL_82;
    }
  }
  if ( *((_QWORD *)this + 193) )
  {
    v5 = (_WORD *)((char *)this + 244);
    goto LABEL_5;
  }
  *((_DWORD *)this + 31) = 16;
  return 16;
}

```

## disassembly

```asm
0x18000c820  push    rbp
0x18000c822  push    rbx
0x18000c823  push    rsi
0x18000c824  push    rdi
0x18000c825  push    r12
0x18000c827  push    r13
0x18000c829  push    r14
0x18000c82b  push    r15
0x18000c82d  lea     rbp, [rsp-1Fh]
0x18000c832  sub     rsp, 88h
0x18000c839  mov     rax, [rcx+68h]
0x18000c83d  mov     rbx, rcx
0x18000c840  mov     rsi, [rcx+130h]
0x18000c847  mov     rax, [rax+18h]
0x18000c84b  lea     r10, [rbx+0F4h]
0x18000c852  mov     [rbp+57h+arg_18], rax
0x18000c856  mov     [rbp+57h+arg_10], r10
0x18000c85a  lea     rcx, [rax-8]
0x18000c85e  neg     rax
0x18000c861  mov     [rbp+57h+var_70], rcx
0x18000c865  sbb     r8, r8
0x18000c868  xor     r12d, r12d
0x18000c86b  and     r8, rcx
0x18000c86e  test    rsi, rsi
0x18000c871  jz      loc_18000C976
0x18000c877  mov     [rbp+57h+arg_10], r10
0x18000c87b  movzx   ecx, word ptr [r10]
0x18000c87f  mov     dword ptr [rbp+57h+Block], ecx
0x18000c882  lea     eax, [rcx-243h]
0x18000c888  cmp     eax, 24h ; '$'
0x18000c88b  jbe     loc_18000D36F
0x18000c891  mov     r15, r10
0x18000c894  movzx   edx, cx; struct STATE *
0x18000c897  mov     [rbp+57h+var_60], r15
0x18000c89b  add     ecx, 0FFFFFF00h; switch 491 cases
0x18000c8a1  mov     [rbp+57h+arg_0], r12b
0x18000c8a5  cmp     ecx, 1EAh
0x18000c8ab  ja      def_18000C8F2; jumptable 000000018000C8F2 default case
0x18000c8b1  lea     r11, __ImageBase
0x18000c8b8  movsxd  rax, ecx
0x18000c8bb  lea     r9, [rbx+0F0h]; int
0x18000c8c2  mov     r13d, 800h
0x18000c8c8  mov     edi, [r9]
0x18000c8cb  movzx   eax, ds:(byte_18000FD64 - 180000000h)[r11+rax]
0x18000c8d4  mov     ecx, ds:(jpt_18000C8F2 - 180000000h)[r11+rax*4]
0x18000c8dc  mov     eax, 4
0x18000c8e1  add     rcx, r11
0x18000c8e4  mov     r11d, 1000h
0x18000c8ea  lea     r12d, [rax-2]
0x18000c8ee  lea     r14d, [rax-3]
0x18000c8f2  jmp     rcx; switch jump
0x18000c8f4  mov     eax, 20Fh; jumptable 000000018000C8F2 case 258
0x18000c8f9  cmp     [rbx+0F6h], ax
0x18000c900  jnz     short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c902  mov     rcx, rbx; jumptable 000000018000C8F2 cases 510,511,553,742
0x18000c905  call    ?SkipToEndOfGroup@CRTFRead@@AEAAHXZ; CRTFRead::SkipToEndOfGroup(void)
0x18000c90a  test    eax, eax
0x18000c90c  jnz     short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c90e  movzx   eax, word ptr [rsi+0Ah]
0x18000c912  mov     ecx, 0FFEFh
0x18000c917  sub     ax, r12w
0x18000c91b  test    cx, ax
0x18000c91e  jz      loc_18000D08F
0x18000c924  mov     rcx, rbx; this
0x18000c927  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x18000c92c  jmp     short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c92e  test    byte ptr [rbx+5F3h], 20h; jumptable 000000018000C8F2 cases 256,257
0x18000c935  jnz     loc_18000EBDF
0x18000c93b  mov     rdx, rsi; struct STATE *
0x18000c93e  mov     rcx, rbx; this
0x18000c941  call    ?HandleTextToken@CRTFRead@@AEAAHPEAUSTATE@@@Z; CRTFRead::HandleTextToken(STATE *)
0x18000c946  mov     al, [rbx+5F3h]; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c94c  mov     cl, [rbp+57h+arg_0]
0x18000c94f  shl     cl, 5
0x18000c952  xor     cl, al
0x18000c954  and     cl, 20h
0x18000c957  xor     cl, al
0x18000c959  mov     eax, [rbx+7Ch]
0x18000c95c  mov     [rbx+5F3h], cl
0x18000c962  add     rsp, 88h
0x18000c969  pop     r15
0x18000c96b  pop     r14
0x18000c96d  pop     r13
0x18000c96f  pop     r12
0x18000c971  pop     rdi
0x18000c972  pop     rsi
0x18000c973  pop     rbx
0x18000c974  pop     rbp
0x18000c975  retn
0x18000c976  mov     eax, 105h
0x18000c97b  cmp     [r10], ax
0x18000c97f  jz      loc_18000C87B
0x18000c985  mov     eax, 18h
0x18000c98a  mov     [rbx+7Ch], eax
0x18000c98d  jmp     short loc_18000C962
0x18000c98f  cmp     [rsi+0Ah], r12w; jumptable 000000018000C8F2 case 283
0x18000c994  jz      loc_18000CCB9
0x18000c99a  xor     r15d, r15d
0x18000c99d  cmp     [rbx+8], r15d
0x18000c9a1  jz      short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c9a3  lea     r8d, [r15+12h]
0x18000c9a7  cmp     [rsi+0Ah], r8w
0x18000c9ac  jz      short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c9ae  or      ecx, 0FFFFFFFFh
0x18000c9b1  cmp     edi, ecx
0x18000c9b3  jz      short loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000c9b5  xor     r8d, r8d; struct CCharFormat *
0x18000c9b8  movzx   edx, di; __int16
0x18000c9bb  mov     rcx, rbx; this
0x18000c9be  call    ?SelectCurrentFont@CRTFRead@@AEAA_NFPEAVCCharFormat@@@Z; CRTFRead::SelectCurrentFont(short,CCharFormat *)
0x18000c9c3  mov     edx, [rsi+10h]; int
0x18000c9c6  test    edx, edx
0x18000c9c8  js      loc_18000D1C1
0x18000c9ce  cmp     edx, [rbx+8]
0x18000c9d1  jge     loc_18000D1C1
0x18000c9d7  mov     rcx, rbx; this
0x18000c9da  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18000c9df  mov     rcx, r14
0x18000c9e2  test    rax, rax
0x18000c9e5  jz      short loc_18000CA08
0x18000c9e7  mov     r9b, [rax+2]
0x18000c9eb  mov     cl, r9b; unsigned __int8
0x18000c9ee  call    ?IsBiDiCharRep@CW32System@@SAHE@Z; CW32System::IsBiDiCharRep(uchar)
0x18000c9f3  test    eax, eax
0x18000c9f5  jnz     loc_18000D5C8
0x18000c9fb  mov     rcx, r14
0x18000c9fe  cmp     [rsi+17h], r12b
0x18000ca02  jz      loc_18000CF69
0x18000ca08  mov     [rsi+rcx*4+3Eh], r15w
0x18000ca0e  mov     r15d, 10h
0x18000ca14  mov     [rsi+rcx*4+3Ch], di
0x18000ca19  or      [rsi+4], r15d
0x18000ca1d  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ca22  mov     rcx, rbx; jumptable 000000018000C8F2 case 261
0x18000ca25  call    ?HandleStartGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleStartGroup(void)
0x18000ca2a  movzx   edx, word ptr [rbx+5F0h]
0x18000ca31  bt      dx, 8
0x18000ca36  jb      loc_18000CDDA
0x18000ca3c  mov     [rbp+57h+arg_0], r14b
0x18000ca40  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ca45  movsx   rax, byte ptr [rsi+17h]; jumptable 000000018000C8F2 case 284
0x18000ca4a  xor     r13d, r13d
0x18000ca4d  mov     [rsi+rax*4+3Ch], di
0x18000ca52  mov     edi, r13d
0x18000ca55  movsx   rax, byte ptr [rsi+17h]; jumptable 000000018000C8F2 case 285
0x18000ca5a  mov     [rsi+rax*4+3Eh], di
0x18000ca5f  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ca64  movzx   eax, byte ptr [rbx+0CBh]; jumptable 000000018000C8F2 case 562
0x18000ca6b  shl     eax, 4
0x18000ca6e  xor     eax, [rsi+4]
0x18000ca71  and     eax, 10h
0x18000ca74  xor     [rsi+4], eax
0x18000ca77  mov     cl, [r10]; jumptable 000000018000C8F2 cases 560,561,563,564
0x18000ca7a  sub     cl, 2Fh ; '/'
0x18000ca7d  movsx   eax, cl
0x18000ca80  sub     eax, r14d
0x18000ca83  mov     [rsi+17h], cl
0x18000ca86  cmp     eax, r14d
0x18000ca89  ja      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ca8f  movsx   rax, cl
0x18000ca93  or      ecx, 0FFFFFFFFh
0x18000ca96  movzx   edx, word ptr [rsi+rax*4+3Ch]; __int16
0x18000ca9b  cmp     dx, cx
0x18000ca9e  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000caa4  xor     r8d, r8d; struct CCharFormat *
0x18000caa7  mov     rcx, rbx; this
0x18000caaa  call    ?SelectCurrentFont@CRTFRead@@AEAA_NFPEAVCCharFormat@@@Z; CRTFRead::SelectCurrentFont(short,CCharFormat *)
0x18000caaf  mov     rcx, rbx; this
0x18000cab2  call    ?HandleNumber@CRTFRead@@AEAAHXZ; CRTFRead::HandleNumber(void)
0x18000cab7  movsx   rax, byte ptr [rsi+17h]
0x18000cabc  movsx   ecx, word ptr [rsi+rax*4+3Eh]
0x18000cac1  mov     edi, ecx
0x18000cac3  test    cx, cx
0x18000cac6  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cacc  mov     r10, [rbp+57h+arg_10]
0x18000cad0  mov     eax, edi; jumptable 000000018000C8F2 case 298
0x18000cad2  neg     eax
0x18000cad4  cmovs   eax, edi
0x18000cad7  cmp     eax, 2710h
0x18000cadc  jg      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cae2  movsx   rax, byte ptr [rsi+17h]
0x18000cae7  mov     r15d, 8
0x18000caed  mov     [rsi+rax*4+3Eh], di
0x18000caf2  movzx   eax, di
0x18000caf5  bts     dword ptr [rbx+144h], 1Fh
0x18000cafd  movzx   ecx, word ptr [rbx+66Ch]
0x18000cb04  shl     di, 2
0x18000cb08  add     ax, di
0x18000cb0b  add     ax, ax
0x18000cb0e  mov     [rbx+88h], ax
0x18000cb15  test    r15b, cl
0x18000cb18  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb1e  mov     edx, 12Ah
0x18000cb23  cmp     [r10], dx
0x18000cb27  jnz     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb2d  mov     [rbx+678h], ax
0x18000cb34  mov     eax, 0FFF7h
0x18000cb39  and     cx, ax
0x18000cb3c  mov     [rbx+66Ch], cx
0x18000cb43  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb48  mov     rcx, rbx; jumptable 000000018000C8F2 case 262
0x18000cb4b  call    ?HandleFieldEndGroup@CRTFRead@@AEAAXXZ; CRTFRead::HandleFieldEndGroup(void)
0x18000cb50  mov     rcx, rbx; this
0x18000cb53  call    ?HandleEndGroup@CRTFRead@@AEAAHXZ; CRTFRead::HandleEndGroup(void)
0x18000cb58  movzx   edx, word ptr [rbx+66Ch]
0x18000cb5f  bt      dx, 8
0x18000cb64  jnb     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb6a  mov     rax, [rsi+20h]
0x18000cb6e  test    rax, rax
0x18000cb71  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb77  mov     ecx, 7
0x18000cb7c  cmp     [rax+0Ah], cx
0x18000cb80  jnz     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cb86  mov     ecx, 0FEFFh
0x18000cb8b  and     dx, cx
0x18000cb8e  mov     [rbx+66Ch], dx
0x18000cb95  jmp     loc_18000C902; jumptable 000000018000C8F2 cases 510,511,553,742
0x18000cb9a  mov     al, [rbx+5F3h]; jumptable 000000018000C8F2 case 527
0x18000cba0  shr     al, 5
0x18000cba3  mov     [rbp+57h+arg_0], al
0x18000cba6  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cbab  mov     edx, [rsi+10h]; jumptable 000000018000C8F2 case 294
0x18000cbae  test    edx, edx
0x18000cbb0  js      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cbb6  cmp     edx, [rbx+8]
0x18000cbb9  jge     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cbbf  mov     rcx, rbx; this
0x18000cbc2  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18000cbc7  mov     r10, rax
0x18000cbca  test    rax, rax
0x18000cbcd  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cbd3  mov     al, [rax+2]
0x18000cbd6  mov     edx, 0Ah
0x18000cbdb  cmp     al, dl
0x18000cbdd  jz      short loc_18000CBEB
0x18000cbdf  mov     cl, dil; unsigned __int8
0x18000cbe2  call    ?CharRepFromCharSet@CW32System@@SAEE@Z; CW32System::CharRepFromCharSet(uchar)
0x18000cbe7  mov     [r10+2], al
0x18000cbeb  mov     cl, al; unsigned __int8
0x18000cbed  call    ?CodePageFromCharRep@CW32System@@SAGE@Z; CW32System::CodePageFromCharRep(uchar)
0x18000cbf2  mov     edx, 0FDE9h
0x18000cbf7  mov     [r10+4Ch], ax
0x18000cbfc  cmp     [rsi+0Ch], dx
0x18000cc00  jz      loc_18000D586
0x18000cc06  mov     [rsi+0Ch], ax
0x18000cc0a  cmp     ax, 2Ah ; '*'
0x18000cc0e  jz      short loc_18000CC22
0x18000cc10  mov     ecx, 0FFFFh
0x18000cc15  cmp     [rbx+600h], cx
0x18000cc1c  jz      loc_18000D58D
0x18000cc22  movzx   eax, dil
0x18000cc26  sub     eax, 0B1h
0x18000cc2b  cmp     eax, r14d
0x18000cc2e  jbe     loc_18000CF37
0x18000cc34  mov     eax, 80h
0x18000cc39  or      [rbx+5F0h], ax
0x18000cc40  test    edi, edi
0x18000cc42  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cc48  lea     r15d, [rax-78h]
0x18000cc4c  or      [rbx+5F3h], r15b
0x18000cc53  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cc58  mov     edx, [rsi+10h]; jumptable 000000018000C8F2 cases 286-293
0x18000cc5b  test    edx, edx
0x18000cc5d  js      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cc63  cmp     edx, [rbx+8]
0x18000cc66  jge     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cc6c  mov     rcx, rbx; this
0x18000cc6f  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18000cc74  test    rax, rax
0x18000cc77  jz      loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cc7d  mov     cl, [rax+3]
0x18000cc80  mov     dl, [r10]
0x18000cc83  and     cl, 0Fh
0x18000cc86  add     dl, r12b
0x18000cc89  shl     dl, 4
0x18000cc8c  or      dl, cl
0x18000cc8e  mov     ecx, 124h
0x18000cc93  mov     [rax+3], dl
0x18000cc96  cmp     cx, [r10]
0x18000cc9a  jnz     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000cca0  mov     r8d, 9
0x18000cca6  cmp     [rax+2], r8b
0x18000ccaa  jnz     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ccb0  mov     byte ptr [rax+2], 0Ah
0x18000ccb4  jmp     loc_18000C946; jumptable 000000018000C8F2 cases 259,260,356,378,395,396,409-415,436,533,558,559,566,568-571,620,650,653-655,661,664,666-668,681-684,686,687,689,691,692,694,696,711,715-727,731-741
0x18000ccb9  or      ecx, 0FFFFFFFFh
0x18000ccbc  cmp     edi, ecx
0x18000ccbe  jz      loc_18000C902; jumptable 000000018000C8F2 cases 510,511,553,742
0x18000ccc4  movsx   eax, word ptr [rbx+5F4h]
0x18000cccb  cmp     edi, eax
0x18000cccd  jz      short loc_18000CD03
0x18000cccf  movsx   eax, word ptr [rbx+5F6h]
0x18000ccd6  mov     edx, r14d; int
0x18000ccd9  cmp     edi, eax
0x18000ccdb  jz      loc_18000D5B4
0x18000cce1  xor     r8d, r8d; int *
0x18000cce4  mov     rcx, rbx; this
0x18000cce7  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18000ccec  xor     r13d, r13d
0x18000ccef  test    rax, rax
  ... truncated ...
```
