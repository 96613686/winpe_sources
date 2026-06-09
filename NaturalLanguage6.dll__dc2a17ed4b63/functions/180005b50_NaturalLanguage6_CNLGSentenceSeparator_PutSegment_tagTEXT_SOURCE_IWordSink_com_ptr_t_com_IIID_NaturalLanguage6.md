# NaturalLanguage6::CNLGSentenceSeparator::PutSegment(tagTEXT_SOURCE *,IWordSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,bool &)

- ea: `0x180005b50`
- end: `0x180007a18`
- name: `?PutSegment@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJPEAUtagTEXT_SOURCE@@PEAUIWordSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@AEA_N@Z`
- size: `7880`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005380`
- `0x180036940`

## callees

- `0x180003d38`
- `0x180003edc`
- `0x180005160`
- `0x180005b50`
- `0x180007a20`
- `0x180008680`
- `0x180008890`
- `0x1800088b0`
- `0x1800088e0`
- `0x1800096d0`
- `0x18000a550`
- `0x18000ada0`
- `0x180023940`
- `0x180035f30`
- `0x180036b04`
- `0x180036b9c`
- `0x1800374d8`
- `0x18003eac8`
- `0x18005a3e0`
- `0x18005c720`
- `0x18009e300`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NaturalLanguage6::CNLGSentenceSeparator::PutSegment(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IUnknown **a4,
        _BYTE *a5)
{
  __int64 *v5; // rdi
  __int64 v7; // r13
  struct IUnknown *v8; // rbx
  int v9; // eax
  struct IUnknown *v10; // rbx
  __int64 v11; // r9
  unsigned int v12; // ecx
  unsigned int v13; // r12d
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  __int64 (__fastcall *v17)(__int64); // r10
  int v18; // ebx
  int i; // esi
  __int64 v20; // rcx
  __int64 v21; // r14
  __int64 v22; // rdx
  __int64 *v23; // r9
  unsigned int v24; // r14d
  unsigned int v25; // edi
  __int64 v26; // rcx
  unsigned int v27; // edx
  int v29; // eax
  int v30; // eax
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // edx
  struct IUnknown *v34; // r11
  unsigned int v35; // eax
  unsigned int v36; // r9d
  unsigned int v37; // r8d
  __int64 v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // r10d
  unsigned int v41; // ecx
  unsigned __int16 *v42; // r8
  struct IUnknown *v43; // rcx
  __int64 v44; // rdx
  unsigned int v45; // r8d
  struct IUnknown *v46; // r11
  unsigned int v47; // eax
  unsigned int v48; // r9d
  __int64 v49; // rcx
  unsigned int v50; // edx
  unsigned int v51; // eax
  unsigned int v52; // r10d
  CSentence *QueryInterface; // rdi
  struct IUnknown *lpVtbl; // r11
  __int64 v55; // rcx
  char *v56; // r10
  unsigned __int16 v57; // si
  int v58; // eax
  __int64 v59; // r10
  __int64 v60; // r10
  char v61; // r8
  int v62; // r14d
  unsigned int v63; // ecx
  __int64 v64; // rdx
  __int64 v65; // r8
  unsigned int v66; // ecx
  unsigned int v67; // edi
  unsigned int v68; // r11d
  struct IUnknown *v69; // r9
  unsigned int v70; // eax
  unsigned int v71; // r8d
  unsigned int v72; // edx
  __int64 v73; // rcx
  unsigned int v74; // eax
  unsigned int v75; // r10d
  _WORD *v76; // r8
  int v77; // ebx
  __int64 *v78; // rcx
  __int64 v79; // rcx
  struct IUnknown *v80; // rcx
  __int64 v81; // rbx
  __int64 v82; // rdx
  unsigned int v83; // r8d
  struct IUnknown *v84; // r11
  unsigned int v85; // eax
  unsigned int v86; // r10d
  __int64 v87; // rcx
  unsigned int v88; // r9d
  unsigned int v89; // eax
  unsigned int v90; // edx
  bool v91; // al
  __int64 v92; // rdx
  unsigned int v93; // r8d
  struct IUnknown *v94; // r11
  unsigned int v95; // eax
  unsigned int v96; // r10d
  __int64 v97; // rcx
  unsigned int v98; // r9d
  unsigned int v99; // eax
  unsigned int v100; // edx
  int v101; // ebx
  __int64 *v102; // rax
  _QWORD *v103; // r8
  __int64 NextPropertyFor; // rax
  __int64 v105; // r11
  __int64 v106; // rdx
  __int64 v107; // rbx
  __int64 v108; // rdx
  unsigned int v109; // r8d
  unsigned int v110; // r11d
  unsigned int v111; // eax
  unsigned int v112; // r10d
  __int64 v113; // rcx
  unsigned int v114; // r9d
  unsigned int v115; // eax
  unsigned int v116; // edx
  __int64 v117; // r10
  unsigned int v118; // ecx
  unsigned int v119; // edx
  unsigned __int16 v120; // r8
  int v121; // eax
  unsigned __int16 v122; // ax
  int v123; // eax
  unsigned int v124; // r8d
  __int64 v125; // rcx
  unsigned int v126; // r9d
  unsigned int v127; // r11d
  unsigned int v128; // edx
  __int64 j; // rcx
  unsigned int v130; // r10d
  char *v131; // r8
  int v132; // eax
  bool v133; // zf
  __int64 v134; // r9
  unsigned int v135; // eax
  unsigned int k; // edi
  __int64 v137; // r14
  unsigned int v138; // edx
  __int64 v139; // r8
  __int64 v140; // rcx
  int v141; // eax
  unsigned int v142; // r9d
  unsigned int v143; // r11d
  unsigned int v144; // r8d
  __int64 v145; // rcx
  unsigned int v146; // r10d
  _WORD *v147; // r8
  unsigned int v148; // r8d
  char *v149; // rbx
  int v150; // r9d
  unsigned int v151; // ebx
  int v152; // r9d
  unsigned int v153; // r11d
  char *v154; // rsi
  int v155; // r8d
  unsigned int v156; // ebx
  int v157; // r9d
  unsigned int v158; // ebx
  int v159; // r10d
  unsigned int v160; // r11d
  int v161; // r8d
  unsigned int v162; // r11d
  __int64 v163; // rsi
  int v164; // edx
  unsigned int v165; // ebx
  int v166; // r10d
  unsigned int v167; // r11d
  char *v168; // rdi
  int v169; // r10d
  struct ILanguageData *LanguageData; // rdi
  LSP *v171; // r14
  __int64 QueryInterface_high; // r8
  const unsigned __int16 *v173; // rsi
  const struct CWordNode *v174; // rax
  __int64 v175; // rcx
  unsigned int v176; // [rsp+20h] [rbp-728h]
  unsigned int v177; // [rsp+20h] [rbp-728h]
  int v178; // [rsp+28h] [rbp-720h]
  char v179[4]; // [rsp+30h] [rbp-718h]
  BOOL v180; // [rsp+40h] [rbp-708h]
  bool v181[4]; // [rsp+40h] [rbp-708h]
  bool v182[4]; // [rsp+40h] [rbp-708h]
  bool v183[4]; // [rsp+40h] [rbp-708h]
  bool v184[4]; // [rsp+40h] [rbp-708h]
  bool v185[4]; // [rsp+40h] [rbp-708h]
  bool v186[4]; // [rsp+40h] [rbp-708h]
  bool v187; // [rsp+44h] [rbp-704h]
  unsigned int v188; // [rsp+48h] [rbp-700h]
  int v189; // [rsp+48h] [rbp-700h]
  unsigned int v190; // [rsp+48h] [rbp-700h]
  int v191; // [rsp+48h] [rbp-700h]
  int v192; // [rsp+48h] [rbp-700h]
  int v193; // [rsp+48h] [rbp-700h]
  unsigned int v194; // [rsp+48h] [rbp-700h]
  unsigned int v195; // [rsp+48h] [rbp-700h]
  bool v196; // [rsp+4Ch] [rbp-6FCh]
  unsigned int v197; // [rsp+50h] [rbp-6F8h] BYREF
  char v198; // [rsp+54h] [rbp-6F4h]
  int v199; // [rsp+58h] [rbp-6F0h]
  unsigned int v200; // [rsp+5Ch] [rbp-6ECh]
  unsigned int v201; // [rsp+60h] [rbp-6E8h]
  unsigned int v202; // [rsp+64h] [rbp-6E4h]
  __int64 v203; // [rsp+68h] [rbp-6E0h] BYREF
  struct IUnknown *v204; // [rsp+70h] [rbp-6D8h] BYREF
  char v205; // [rsp+78h] [rbp-6D0h]
  __int64 v206; // [rsp+80h] [rbp-6C8h] BYREF
  __int64 v207; // [rsp+88h] [rbp-6C0h] BYREF
  int v208; // [rsp+90h] [rbp-6B8h]
  BOOL v209; // [rsp+94h] [rbp-6B4h] BYREF
  __int64 v210; // [rsp+98h] [rbp-6B0h]
  __int64 *v211; // [rsp+A0h] [rbp-6A8h]
  bool v212; // [rsp+A8h] [rbp-6A0h]
  char v213; // [rsp+A9h] [rbp-69Fh]
  __int64 v214; // [rsp+B0h] [rbp-698h]
  __int64 (__fastcall *v215)(__int64); // [rsp+B8h] [rbp-690h]
  __int64 v216; // [rsp+C0h] [rbp-688h] BYREF
  __int64 v217; // [rsp+C8h] [rbp-680h]
  struct IUnknown *v218; // [rsp+D0h] [rbp-678h] BYREF
  int v219; // [rsp+D8h] [rbp-670h]
  unsigned int v220; // [rsp+DCh] [rbp-66Ch]
  __int64 v221; // [rsp+E0h] [rbp-668h]
  unsigned int v222; // [rsp+E8h] [rbp-660h]
  __int64 v223; // [rsp+F0h] [rbp-658h] BYREF
  int v224; // [rsp+F8h] [rbp-650h]
  unsigned int v225; // [rsp+FCh] [rbp-64Ch]
  unsigned int v226; // [rsp+100h] [rbp-648h]
  __int64 *v227; // [rsp+108h] [rbp-640h]
  __int64 (__fastcall *v228)(__int64); // [rsp+110h] [rbp-638h]
  __int64 v229; // [rsp+118h] [rbp-630h]
  __int64 v230; // [rsp+120h] [rbp-628h]
  __int64 v231; // [rsp+130h] [rbp-618h]
  __int64 v232; // [rsp+138h] [rbp-610h]
  __int64 *v233; // [rsp+140h] [rbp-608h]
  __int64 *v234; // [rsp+148h] [rbp-600h]
  _BYTE *v235; // [rsp+158h] [rbp-5F0h]
  struct IUnknown **v236; // [rsp+160h] [rbp-5E8h]
  _com_error *v237[35]; // [rsp+168h] [rbp-5E0h] BYREF
  _WORD v238[64]; // [rsp+280h] [rbp-4C8h] BYREF
  _WORD v239[192]; // [rsp+300h] [rbp-448h] BYREF
  _WORD v240[64]; // [rsp+480h] [rbp-2C8h] BYREF
  unsigned __int16 v241[128]; // [rsp+500h] [rbp-248h] BYREF
  unsigned __int16 v242[128]; // [rsp+600h] [rbp-148h] BYREF
  void *retaddr; // [rsp+748h] [rbp+0h]

  v237[2] = (_com_error *)-2LL;
  v5 = (__int64 *)a4;
  v211 = (__int64 *)a4;
  v210 = a3;
  v217 = a2;
  v7 = a1;
  v231 = a1;
  v232 = a2;
  v233 = (__int64 *)a4;
  v235 = a5;
  v209 = 0;
  v8 = *a4;
  if ( !*a4 )
    goto LABEL_308;
  v216 = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v8->lpVtbl[1].AddRef)(v8, &v216);
  if ( v9 < 0 )
    _com_issue_errorex(v9, v8, &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56);
  if ( !HIDWORD(v216) )
  {
    _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v5);
    return 0;
  }
  v10 = (struct IUnknown *)*v5;
  v11 = *(_QWORD *)(*v5 + 40) + *(int *)(*(_QWORD *)(*(_QWORD *)(*v5 + 40) + 8LL) + 4LL);
  v12 = *(_DWORD *)(v11 + 8);
  v13 = v12 >> 27;
  v222 = v12 >> 27;
  v215 =  IWordFormSink::`vcall'{32,{flat}};
  v14 = 0;
  v199 = 0;
  v187 = 1;
  v196 = 0;
  v198 = v12 >> 27 == 13;
  if ( v12 >> 27 == 9 )
  {
    v14 = BYTE1(v12);
    v199 = BYTE1(v12);
    v196 = (((v12 & 0x7FF0000) - 10813440) & 0xFFFCFFFF) == 0;
    if ( BYTE1(v12) <= 6u )
    {
      v29 = 74;
      if ( _bittest(&v29, BYTE1(v12)) )
        v215 =  IWordFormSink::`vcall'{24,{flat}};
    }
    goto LABEL_7;
  }
  if ( v13 == 10 )
  {
    if ( CMorphNode::NotUnfound((CMorphNode *)(v11 + 8)) && (*(_DWORD *)(v134 + 72) & 0xFF000000) != 0 )
    {
      v91 = 1;
      v187 = 1;
    }
    else
    {
      v91 = 0;
      v187 = 1;
    }
  }
  else
  {
    if ( v13 != 14 )
      goto LABEL_7;
    v91 = (*(_DWORD *)(v11 + 72) & 0xFFFFFFu) - 16777214 > 1 && (*(_DWORD *)(v11 + 72) & 0xFF000000) != 0;
    v187 = 0;
  }
  v17 =  IWordFormSink::`vcall'{24,{flat}};
  v215 =  IWordFormSink::`vcall'{24,{flat}};
  if ( !v91 )
  {
LABEL_7:
    if ( v10 )
    {
      v197 = 0;
      v15 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v10->lpVtbl[2].AddRef)(v10, &v197);
      if ( v15 < 0 )
        _com_issue_errorex(v15, v10, &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56);
      v16 = v197;
      v17 = v215;
      goto LABEL_10;
    }
LABEL_308:
    _com_raise_error(-2147467261, 0);
  }
  v16 = 0;
LABEL_10:
  v219 = v16;
  v225 = v13;
  v229 = v7;
  v223 = a2;
  v221 = v210;
  v230 = v210;
  v18 = 0;
  v180 = 0;
  v220 = v13;
  v226 = v13;
  v213 = v198;
  v228 = v17;
  v224 = v14;
  for ( i = 0; ; ++i )
  {
    v208 = i;
    if ( i >= v16 )
    {
      if ( !v187 || v14 == 1 && v16 )
      {
        v21 = v217;
      }
      else
      {
        v236 = (struct IUnknown **)&v223;
        v20 = *v5;
        v223 = v20;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v21 = v217;
        v18 = NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
                v7,
                v217,
                v210,
                (unsigned int)&v223,
                (__int64)&v209,
                (__int64)&v216,
                0);
        if ( v18 < 0 )
        {
LABEL_26:
          if ( *v5 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)*v5 + 16LL))(*v5);
          return (unsigned int)v18;
        }
      }
      if ( !v209 )
      {
        v22 = *(unsigned int *)(v7 + 72);
        v219 = v216 + v22;
        v23 = (__int64 *)(*(_QWORD *)(v21 + 8) + 2 * (v22 + (int)v216));
        v227 = v23;
        v24 = HIDWORD(v216);
        v18 = 0;
        LODWORD(v214) = *(_DWORD *)(v7 + 44);
        v25 = 0;
        v26 = (unsigned int)v214;
        while ( v25 < v24 )
        {
          v27 = v26;
          if ( v24 - v25 <= (unsigned int)v26 )
            v27 = v24 - v25;
          if ( (_DWORD)v26 != 1
            || (v26 = 10240, LOWORD(v26) = *((_WORD *)v23 + v25) + 10240, (unsigned __int16)v26 > 0x7FFu) )
          {
            if ( v13 == 13 && v27 < 0x40 )
            {
              v148 = 0;
              if ( v27 )
              {
                v149 = (char *)v23 + 2 * v25;
                do
                {
                  v150 = *(unsigned __int16 *)&v149[2 * v148];
                  v26 = (unsigned int)(v150 - 8216);
                  if ( v150 == 8216
                    || (v26 = (unsigned int)(v150 - 8217), v150 == 8217)
                    || (v26 = (unsigned int)(v150 - 8242), v150 == 8242)
                    || v150 == 65287 )
                  {
                    LOWORD(v150) = 39;
                  }
                  v241[v148++ + 64] = v150;
                }
                while ( v148 < v27 );
              }
              if ( 2 * (unsigned __int64)v148 >= 0x80 )
                _report_rangecheckfailure(v26);
              v241[v148 + 64] = 0;
            }
            v18 =  IWordFormSink::`vcall'{24,{flat}}(v221);
            if ( v18 < 0 )
            {
              v5 = v211;
              goto LABEL_26;
            }
            v23 = v227;
          }
          v26 = *(unsigned int *)(v7 + 44);
          v25 += v26;
        }
        v5 = v211;
        v21 = v217;
      }
      *(_DWORD *)(v21 + 20) = HIDWORD(v216) + v216 + *(_DWORD *)(v7 + 72);
      *v235 = 1;
      goto LABEL_26;
    }
    if ( !*v5 )
      _com_raise_error(-2147467261, 0);
    NaturalLanguage6::ITextSegment::GetItem((struct IUnknown *)*v5);
    v204 = v218;
    if ( !v218 )
      _com_raise_error(-2147467261, 0);
    v207 = 0;
    v30 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v218->lpVtbl[1].AddRef)(v218, &v207);
    if ( v30 < 0 )
      _com_issue_errorex(v30, v204, &GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56);
    if ( !*(_DWORD *)(v7 + 1680) )
    {
      v209 = v228 ==  IWordFormSink::`vcall'{24,{flat}};
      if ( !v187 || i && v14 != 1 || v228 !=  IWordFormSink::`vcall'{24,{flat}} )
        goto LABEL_41;
      if ( i )
        goto LABEL_114;
      v44 = *(unsigned int *)(v7 + 72);
      v201 = v44 + v216;
      v45 = HIDWORD(v216);
      LODWORD(v203) = HIDWORD(v216);
      v46 = (struct IUnknown *)(*(_QWORD *)(v217 + 8) + 2 * ((int)v216 + v44));
      v204 = v46;
      v47 = HIDWORD(v216);
      *(_DWORD *)v181 = HIDWORD(v216);
      v18 = 0;
      v48 = *(_DWORD *)(v7 + 44);
      v197 = v48;
      v49 = 0;
      v50 = v48;
      while ( 1 )
      {
        v189 = v49;
        if ( (unsigned int)v49 >= v47 )
          break;
        v51 = v47 - v49;
        v52 = v50;
        if ( v51 <= v50 )
          v52 = v51;
        if ( (unsigned int)v203 > v48 )
          v45 = v52;
        v200 = v45;
        if ( v50 == 1 )
        {
          if ( (unsigned __int16)(*((_WORD *)&v46->lpVtbl + (unsigned int)v49) + 10240) <= 0x7FFu )
            goto LABEL_143;
          v49 = (unsigned int)v49;
        }
        if ( v13 == 13 && v52 < 0x40 )
        {
          v156 = 0;
          if ( v52 )
          {
            do
            {
              v157 = *((unsigned __int16 *)&v46->lpVtbl + (unsigned int)v49 + v156);
              if ( v157 == 8216 || v157 == 8217 || v157 == 8242 || v157 == 65287 )
                LOWORD(v157) = 39;
              v239[v156++ + 64] = v157;
            }
            while ( v156 < v52 );
            v5 = v211;
            v14 = v199;
          }
          if ( 2 * (unsigned __int64)v156 >= 0x80 )
            _report_rangecheckfailure(v49);
          v239[v156 + 64] = 0;
        }
        v18 =  IWordFormSink::`vcall'{32,{flat}}(v221);
        if ( v18 < 0 )
          goto LABEL_75;
        v45 = v200;
        v48 = v197;
        v46 = v204;
LABEL_143:
        v50 = *(_DWORD *)(v7 + 44);
        v49 = v50 + v189;
        v47 = *(_DWORD *)v181;
      }
      v180 = v18;
LABEL_114:
      if ( v220 == 10 )
        goto LABEL_41;
      if ( v14 != 1 && v14 != 6 )
      {
        v77 = 1;
        v227 = &v206;
        goto LABEL_118;
      }
      if ( i )
      {
        v81 = v217;
        goto LABEL_129;
      }
      v236 = &v204;
      v80 = (struct IUnknown *)*v5;
      v204 = v80;
      if ( v80 )
        ((void (__fastcall *)(struct IUnknown *))v80->lpVtbl->AddRef)(v80);
      v81 = v217;
      LODWORD(v203) = NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
                        v7,
                        v217,
                        v210,
                        (unsigned int)&v204,
                        (__int64)&v209,
                        (__int64)&v216,
                        1);
      if ( (int)v203 < 0 )
      {
        if ( v218 )
          goto LABEL_254;
        goto LABEL_255;
      }
LABEL_129:
      if ( v14 == 6 && !i )
      {
        v82 = *(unsigned int *)(v7 + 72);
        v201 = v82 + v207;
        v83 = HIDWORD(v207);
        LODWORD(v203) = HIDWORD(v207);
        v84 = (struct IUnknown *)(*(_QWORD *)(v81 + 8) + 2 * ((int)v207 + v82));
        v204 = v84;
        v85 = HIDWORD(v207);
        *(_DWORD *)v182 = HIDWORD(v207);
        v18 = 0;
        v86 = *(_DWORD *)(v7 + 44);
        v197 = v86;
        v87 = 0;
        v88 = v86;
        while ( 1 )
        {
          v191 = v87;
          if ( (unsigned int)v87 >= v85 )
            goto LABEL_123;
          v89 = v85 - v87;
          v90 = v88;
          if ( v89 <= v88 )
            v90 = v89;
          if ( (unsigned int)v203 > v86 )
            v83 = v90;
          v200 = v83;
          if ( v88 == 1 )
          {
            if ( (unsigned __int16)(*((_WORD *)&v84->lpVtbl + (unsigned int)v87) + 10240) <= 0x7FFu )
              goto LABEL_141;
            v87 = (unsigned int)v87;
          }
          if ( v13 == 13 && v90 < 0x40 )
          {
            v158 = 0;
            if ( v90 )
            {
              do
              {
                v159 = *((unsigned __int16 *)&v84->lpVtbl + (unsigned int)v87 + v158);
                if ( v159 == 8216 || v159 == 8217 || v159 == 8242 || v159 == 65287 )
                  LOWORD(v159) = 39;
                v239[v158++ + 128] = v159;
              }
              while ( v158 < v90 );
              v5 = v211;
              v14 = v199;
            }
            if ( 2 * (unsigned __int64)v158 >= 0x80 )
              _report_rangecheckfailure(v87);
            v239[v158 + 128] = 0;
          }
          v18 =  IWordFormSink::`vcall'{24,{flat}}(v221);
          if ( v18 < 0 )
            goto LABEL_123;
          v83 = v200;
          v86 = v197;
          v84 = v204;
LABEL_141:
          v88 = *(_DWORD *)(v7 + 44);
          v87 = v88 + v191;
          v85 = *(_DWORD *)v182;
        }
      }
      v227 = &v206;
      v77 = 0;
      if ( v14 != 1 )
      {
LABEL_118:
        if ( v14 != 6 )
        {
          v78 = v5;
          goto LABEL_120;
        }
      }
      v78 = (__int64 *)&v218;
LABEL_120:
      v79 = *v78;
      v206 = v79;
      if ( v79 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 8LL))(v79);
      v18 = NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
              v7,
              v217,
              v210,
              (unsigned int)&v206,
              (__int64)&v209,
              (__int64)&v207,
              v77);
LABEL_123:
      v180 = v18;
      if ( v18 < 0 )
        goto LABEL_75;
      v187 = v14 == 1;
LABEL_41:
      if ( (i > 0 || v14 != 6) && v14 != 1 )
      {
        v31 = *(unsigned int *)(v229 + 72);
        v32 = *(_QWORD *)(v223 + 8);
        v18 = 0;
        if ( v196 )
        {
          LODWORD(v203) = v31 + v207;
          v117 = v32 + 2 * (v31 + (int)v207);
          v206 = v117;
          v118 = HIDWORD(v207);
          v197 = HIDWORD(v207);
          v119 = 0;
          while ( 1 )
          {
            *(_DWORD *)v185 = v119;
            if ( v119 >= v118 )
              break;
            do
            {
              v120 = *(_WORD *)(v117 + 2LL * v119);
              if ( (v120 & 0xFF00) != 0 )
              {
                v121 = UlGetTypeFlags(v120) & 0x1000000;
                v119 = *(_DWORD *)v185;
                v118 = v197;
                v117 = v206;
              }
              else
              {
                v121 = *((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v120) & 0x10;
              }
              if ( !v121 )
                break;
              *(_DWORD *)v185 = ++v119;
            }
            while ( v119 < v118 );
            v200 = v119 + v203;
            v194 = 0;
            i = v208;
            if ( v119 >= v118 )
              break;
            while ( 1 )
            {
              v122 = *(_WORD *)(v117 + 2LL * v119);
              LOWORD(v202) = v122;
              if ( (v122 & 0xFF00) != 0 )
              {
                v123 = UlGetTypeFlags(v122) & 0x1000000;
                v119 = *(_DWORD *)v185;
              }
              else
              {
                v123 = *((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v122) & 0x10;
              }
              if ( v123 && (_WORD)v202 != 95 )
                break;
              v124 = ++v194;
              *(_DWORD *)v185 = ++v119;
              v117 = v206;
              if ( v119 >= v197 )
                goto LABEL_217;
            }
            v124 = v194;
LABEL_217:
            v14 = v199;
            if ( !v124 )
              break;
            while ( v119 )
            {
              v125 = v119 - 1;
              if ( *(_WORD *)(v206 + 2 * v125) != 95 )
                break;
              v133 = v124-- == 1;
              v194 = v124;
              if ( v133 )
                goto LABEL_54;
              --v119;
              *(_DWORD *)v185 = v125;
            }
            v126 = v124;
            v204 = (struct IUnknown *)(v206 + 2 * (v119 - (unsigned __int64)v124));
            v18 = 0;
            v127 = *(_DWORD *)(v7 + 44);
            LODWORD(v214) = v127;
            v128 = 0;
            for ( j = v127; ; v128 += j )
            {
              v202 = v128;
              if ( v128 >= v124 )
                break;
              v130 = j;
              if ( v124 - v128 <= (unsigned int)j )
                v130 = v124 - v128;
              if ( v124 > v127 )
                v126 = v130;
              v201 = v126;
              if ( (_DWORD)j != 1
                || (j = 10240,
                    LOWORD(j) = *((_WORD *)&v204->lpVtbl + v128) + 10240,
                    v5 = v211,
                    (unsigned __int16)j > 0x7FFu) )
              {
                if ( v13 == 13 && v130 < 0x40 )
                {
                  v153 = 0;
                  if ( v130 )
                  {
                    v154 = (char *)v204 + 2 * v128;
                    do
                    {
                      v155 = *(unsigned __int16 *)&v154[2 * v153];
                      j = (unsigned int)(v155 - 8216);
                      if ( v155 == 8216
                        || (j = (unsigned int)(v155 - 8217), v155 == 8217)
                        || (j = (unsigned int)(v155 - 8242), v155 == 8242)
                        || v155 == 65287 )
                      {
                        LOWORD(v155) = 39;
                      }
                      v240[v153++] = v155;
                    }
                    while ( v153 < v130 );
                    i = v208;
                    v14 = v199;
                  }
                  if ( 2 * (unsigned __int64)v153 >= 0x80 )
                    _report_rangecheckfailure(j);
                  v240[v153] = 0;
                  v131 = (char *)v240;
                }
                else
                {
                  v131 = (char *)v204 + 2 * v128;
                }
                v18 = ((__int64 (__fastcall *)(__int64, _QWORD, char *))v215)(v210, v130, v131);
                if ( v18 < 0 )
                  goto LABEL_54;
                v124 = v194;
                v128 = v202;
                v126 = v201;
                v127 = v214;
              }
              j = *(unsigned int *)(v7 + 44);
            }
            v119 = *(_DWORD *)v185 + 1;
            v118 = v197;
            v117 = v206;
          }
        }
        else
        {
          v200 = v31 + v207;
          v33 = HIDWORD(v207);
          LODWORD(v214) = HIDWORD(v207);
          v34 = (struct IUnknown *)(v32 + 2 * (v31 + (int)v207));
          v204 = v34;
          v35 = HIDWORD(v207);
          v188 = HIDWORD(v207);
          v36 = *(_DWORD *)(v7 + 44);
          v201 = v36;
          v37 = 0;
          v38 = v36;
          while ( 1 )
          {
            v197 = v37;
            if ( v37 >= v35 )
              break;
            v39 = v35 - v37;
            v40 = v38;
            if ( v39 <= (unsigned int)v38 )
              v40 = v39;
            if ( (unsigned int)v214 > v36 )
              v33 = v40;
            LODWORD(v203) = v33;
            if ( (_DWORD)v38 != 1
              || (v38 = 10240, LOWORD(v38) = *((_WORD *)&v34->lpVtbl + v37) + 10240, (unsigned __int16)v38 > 0x7FFu) )
            {
              if ( v13 == 13 && v40 < 0x40 )
              {
                v151 = 0;
                if ( v40 )
                {
                  do
                  {
                    v152 = *((unsigned __int16 *)&v34->lpVtbl + v37 + v151);
                    v38 = (unsigned int)(v152 - 8216);
                    if ( v152 == 8216
                      || (v38 = (unsigned int)(v152 - 8217), v152 == 8217)
                      || (v38 = (unsigned int)(v152 - 8242), v152 == 8242)
                      || v152 == 65287 )
                    {
                      LOWORD(v152) = 39;
                    }
                    v241[v151++] = v152;
                  }
                  while ( v151 < v40 );
                  v5 = v211;
                  v14 = v199;
                }
                if ( 2 * (unsigned __int64)v151 >= 0x80 )
                  _report_rangecheckfailure(v38);
                v241[v151] = 0;
                v176 = v37 + v200;
                v42 = v241;
              }
              else
              {
                v41 = v37 + v200;
                v42 = (unsigned __int16 *)v34 + v37;
                v176 = v41;
              }
              v18 = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 *, _QWORD, unsigned int))v215)(
                      v210,
                      v40,
                      v42,
                      v33,
                      v176);
              if ( v18 < 0 )
                break;
              v33 = v203;
              v37 = v197;
              v36 = v201;
              v34 = v204;
            }
            v38 = *(unsigned int *)(v7 + 44);
            v37 += v38;
            v35 = v188;
          }
        }
LABEL_54:
        v180 = v18;
      }
      goto LABEL_55;
    }
    QueryInterface = (CSentence *)v218[2].lpVtbl[1].QueryInterface;
    lpVtbl = (struct IUnknown *)v218[5].lpVtbl;
    v204 = lpVtbl;
    v55 = 128;
    v214 = 128;
    v206 = 128;
    try
    {
      if ( lpVtbl )
      {
        v56 = (char *)lpVtbl + SHIDWORD(lpVtbl[1].lpVtbl->QueryInterface);
        if ( (*((_DWORD *)v56 + 18) & 0xFF000000) <= 0x1000000 )
        {
          v57 = *(_WORD *)(v7 + 100) & 0x3FF;
          v58 = *((_DWORD *)v56 + 2) >> 27;
          LOBYTE(v55) = v58 == 7;
          v212 = v58 == 7;
          if ( v58 != 7 )
          {
            v103 = (_QWORD *)*((_QWORD *)v56 + 11);
            if ( v103 )
            {
              if ( v57 != 17 && v57 != 4 )
              {
                NextPropertyFor = CNodeProperties::FindNextPropertyFor(v55, 4379, *v103);
                if ( NextPropertyFor )
                {
                  v106 = *(_QWORD *)(NextPropertyFor + 16);
                  LOBYTE(v55) = v105 != v106
                             && (*(_DWORD *)(*(int *)(*(_QWORD *)(v106 + 8) + 4LL) + v106 + 8) & 0xF8000000) == 0x50000000;
                  v212 = v55;
                }
              }
            }
          }
          if ( (_BYTE)v55
            && CMorphNode::NotUnfound((CMorphNode *)(v56 + 8))
            && v57 != 17
            && v57 != 4
            && !LSP::LexEntryData::IsInAnyDialect((LSP::LexEntryData *)(v59 + 16))
            && *(_DWORD *)(v60 + 24) )
          {
            LanguageData = CSentence::GetLanguageData(QueryInterface);
            v171 = (LSP *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)LanguageData + 2) + 64LL))((__int64)LanguageData + 16);
            LOBYTE(LanguageData) = (*(__int64 (__fastcall **)(struct ILanguageData *, _QWORD))(*(_QWORD *)LanguageData
                                                                                             + 232LL))(
                                     LanguageData,
                                     v57);
            QueryInterface_high = SHIDWORD(v204[1].lpVtbl->QueryInterface);
            v173 = *(const unsigned __int16 **)((char *)&v204[10].lpVtbl + QueryInterface_high);
            v174 = (const struct CWordNode *)LSP::CName::ToString((LSP::CName *)((char *)&v204[6] + QueryInterface_high));
            if ( LSP::LemmaFor(
                   v171,
                   (const struct INLTopLexicon *)v204,
                   v174,
                   v173,
                   v242,
                   (unsigned __int16 *)0x80,
                   (char)LanguageData,
                   1,
                   v180) )
            {
              v175 = -1;
              do
                v214 = ++v175;
              while ( v242[v175] );
              v206 = v175;
              v61 = 1;
              goto LABEL_92;
            }
            v214 = 0;
            v206 = 0;
          }
        }
      }
      v61 = 0;
LABEL_92:
      LOBYTE(v202) = v61;
      v205 = v61;
    }
    catch ( _com_error *v237 )
    {
      ImxTraceCatch(1, *((unsigned int *)v237[0] + 2), retaddr);
      v205 = 0;
      v18 = v180;
      v214 = v206;
      v61 = 0;
      LOBYTE(v202) = 0;
      v62 = v224;
      v199 = v224;
      v221 = v230;
      v210 = v230;
      v7 = v231;
      v217 = v232;
      v5 = v233;
      v211 = v233;
      v13 = v225;
      v222 = v225;
      v198 = v213;
      goto LABEL_94;
    }
    v5 = v211;
    v62 = v199;
LABEL_94:
    v209 = v228 ==  IWordFormSink::`vcall'{24,{flat}};
    i = v208;
    if ( v187 && (!v208 || v62 == 1) && v228 ==  IWordFormSink::`vcall'{24,{flat}} )
    {
      if ( v208 )
        goto LABEL_171;
      v92 = *(unsigned int *)(v7 + 72);
      v197 = v92 + v216;
      v93 = HIDWORD(v216);
      v200 = HIDWORD(v216);
      v94 = (struct IUnknown *)(*(_QWORD *)(v217 + 8) + 2 * ((int)v216 + v92));
      v204 = v94;
      v95 = HIDWORD(v216);
      LODWORD(v203) = HIDWORD(v216);
      v18 = 0;
      v96 = *(_DWORD *)(v7 + 44);
      v201 = v96;
      v97 = 0;
      v98 = v96;
      while ( 1 )
      {
        v192 = v97;
        if ( (unsigned int)v97 >= v95 )
          break;
        v99 = v95 - v97;
        v100 = v98;
        if ( v99 <= v98 )
          v100 = v99;
        if ( v200 > v96 )
          v93 = v100;
        *(_DWORD *)v183 = v93;
        if ( v98 == 1 )
        {
          if ( (unsigned __int16)(*((_WORD *)&v94->lpVtbl + (unsigned int)v97) + 10240) <= 0x7FFu )
            goto LABEL_166;
          v97 = (unsigned int)v97;
        }
        if ( v13 == 13 && v100 < 0x40 )
        {
          v165 = 0;
          if ( v100 )
          {
            do
            {
              v166 = *((unsigned __int16 *)&v94->lpVtbl + (unsigned int)v97 + v165);
              if ( v166 == 8216 || v166 == 8217 || v166 == 8242 || v166 == 65287 )
                LOWORD(v166) = 39;
              *((_WORD *)&v237[3] + v165++) = v166;
            }
            while ( v165 < v100 );
            v5 = v211;
            v62 = v199;
          }
          if ( 2 * (unsigned __int64)v165 >= 0x80 )
            _report_rangecheckfailure(v97);
          *((_WORD *)&v237[3] + v165) = 0;
        }
        v18 =  IWordFormSink::`vcall'{32,{flat}}(v221);
        if ( v18 < 0 )
          goto LABEL_75;
        v93 = *(_DWORD *)v183;
        v96 = v201;
        v94 = v204;
LABEL_166:
        v98 = *(_DWORD *)(v7 + 44);
        v97 = v98 + v192;
        v95 = v203;
      }
      v180 = v18;
      v61 = v202;
LABEL_171:
      if ( v226 != 10 )
        break;
    }
LABEL_95:
    v14 = v199;
    if ( (i > 0 || v199 != 6) && v199 != 1 )
    {
      v63 = *(_DWORD *)(v229 + 72);
      if ( v61 )
      {
        *(_DWORD *)v179 = v207 + v63;
        if ( v196 )
          v132 = NaturalLanguage6::CNLGSentenceSeparator::PutCheckedBrokenWord(
                   v7,
                   v210,
                   (_DWORD)v215,
                   v214,
                   (__int64)v242,
                   v178,
                   *(_DWORD *)v179,
                   v198);
        else
          v132 = NaturalLanguage6::CNLGSentenceSeparator::PutCheckedWord(
                   v7,
                   v210,
                   (_DWORD)v215,
                   v214,
                   (__int64)v242,
                   HIDWORD(v207),
                   *(_DWORD *)v179,
                   v198);
        v18 = v132;
        v180 = v132;
      }
      else
      {
        v64 = *(_QWORD *)(v223 + 8);
        v65 = v63;
        v18 = 0;
        v66 = v207 + v63;
        if ( v196 )
        {
          LODWORD(v203) = v66;
          v206 = v64 + 2 * (v65 + (int)v207);
          v135 = HIDWORD(v207);
          *(_DWORD *)v186 = HIDWORD(v207);
          for ( k = 0; k < v135; ++k )
          {
            v137 = v206;
            do
            {
              if ( !(unsigned int)CMN_IsCharPunctW(*(unsigned __int16 *)(v137 + 2LL * k)) )
                break;
              ++k;
            }
            while ( k < *(_DWORD *)v186 );
            v197 = k + v203;
            v138 = 0;
            v195 = 0;
            i = v208;
            v14 = v199;
            if ( k >= *(_DWORD *)v186 )
              break;
            v139 = v206;
            do
            {
              v140 = *(unsigned __int16 *)(v139 + 2LL * k);
              LOWORD(v202) = v140;
              if ( (v140 & 0xFF00) != 0 )
              {
                v141 = UlGetTypeFlags(v140) & 0x1000000;
                LOWORD(v140) = v202;
                v138 = v195;
                v139 = v206;
              }
              else
              {
                v141 = *((_BYTE *)k_rgbLexTab1 + (unsigned __int8)v140) & 0x10;
              }
              if ( v141 && (_WORD)v140 != 95 )
                break;
              v195 = ++v138;
              ++k;
            }
            while ( k < *(_DWORD *)v186 );
            v13 = v222;
            i = v208;
            v14 = v199;
            if ( !v138 )
              break;
            while ( k && *(_WORD *)(v139 + 2LL * (k - 1)) == 95 )
            {
              v133 = v138-- == 1;
              v195 = v138;
              if ( v133 )
                goto LABEL_109;
              --k;
            }
            v142 = v138;
            v214 = v139 + 2 * (k - (unsigned __int64)v138);
            v18 = 0;
            v143 = *(_DWORD *)(v7 + 44);
            v200 = v143;
            v144 = 0;
            v202 = 0;
            v145 = v143;
            while ( v144 < v138 )
            {
              v146 = v145;
              if ( v138 - v144 <= (unsigned int)v145 )
                v146 = v138 - v144;
              if ( v138 > v143 )
                v142 = v146;
              v201 = v142;
              if ( (_DWORD)v145 != 1
                || (v145 = 10240,
                    LOWORD(v145) = *(_WORD *)(v214 + 2LL * v144) + 10240,
                    v14 = v199,
                    (unsigned __int16)v145 > 0x7FFu) )
              {
                if ( v13 == 13 && v146 < 0x40 )
                {
                  v162 = 0;
                  if ( v146 )
                  {
                    v163 = v214 + 2LL * v144;
                    do
                    {
                      v164 = *(unsigned __int16 *)(v163 + 2LL * v162);
                      v145 = (unsigned int)(v164 - 8216);
                      if ( v164 == 8216
                        || (v145 = (unsigned int)(v164 - 8217), v164 == 8217)
                        || (v145 = (unsigned int)(v164 - 8242), v164 == 8242)
                        || v164 == 65287 )
                      {
                        LOWORD(v164) = 39;
                      }
                      v238[v162++] = v164;
                    }
                    while ( v162 < v146 );
                    i = v208;
                    v14 = v199;
                  }
                  if ( 2 * (unsigned __int64)v162 >= 0x80 )
                    _report_rangecheckfailure(v145);
                  v238[v162] = 0;
                  v147 = v238;
                }
                else
                {
                  v147 = (_WORD *)(v214 + 2LL * v144);
                }
                v18 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *))v215)(v210, v146, v147);
                if ( v18 < 0 )
                  goto LABEL_109;
                v138 = v195;
                v144 = v202;
                v142 = v201;
                v143 = v200;
              }
              v145 = *(unsigned int *)(v7 + 44);
              v144 += v145;
              v202 = v144;
            }
            v135 = *(_DWORD *)v186;
          }
        }
        else
        {
          v197 = v66;
          v67 = HIDWORD(v207);
          v68 = HIDWORD(v207);
          v201 = HIDWORD(v207);
          v69 = (struct IUnknown *)(v64 + 2 * (v65 + (int)v207));
          v204 = v69;
          v70 = HIDWORD(v207);
          v200 = HIDWORD(v207);
          v71 = *(_DWORD *)(v7 + 44);
          LODWORD(v203) = v71;
          v72 = 0;
          v73 = v71;
          while ( 1 )
          {
            v190 = v72;
            if ( v72 >= v70 )
              break;
            v74 = v70 - v72;
            v75 = v73;
            if ( v74 <= (unsigned int)v73 )
              v75 = v74;
            if ( v68 > v71 )
              v67 = v75;
            if ( (_DWORD)v73 != 1
              || (v73 = 10240, LOWORD(v73) = *((_WORD *)&v69->lpVtbl + v72) + 10240, (unsigned __int16)v73 > 0x7FFu) )
            {
              if ( v13 == 13 && v75 < 0x40 )
              {
                v160 = 0;
                if ( v75 )
                {
                  do
                  {
                    v161 = *((unsigned __int16 *)&v69->lpVtbl + v72 + v160);
                    v73 = (unsigned int)(v161 - 8216);
                    if ( v161 == 8216
                      || (v73 = (unsigned int)(v161 - 8217), v161 == 8217)
                      || (v73 = (unsigned int)(v161 - 8242), v161 == 8242)
                      || v161 == 65287 )
                    {
                      LOWORD(v161) = 39;
                    }
                    v239[v160++] = v161;
                  }
                  while ( v160 < v75 );
                  v14 = v199;
                }
                if ( 2 * (unsigned __int64)v160 >= 0x80 )
                  _report_rangecheckfailure(v73);
                v239[v160] = 0;
                v177 = v72 + v197;
                v76 = v239;
              }
              else
              {
                v76 = (_WORD *)v69 + v72;
                v177 = v72 + v197;
              }
              v18 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, _QWORD, unsigned int))v215)(
                      v210,
                      v75,
                      v76,
                      v67,
                      v177);
              if ( v18 < 0 )
                break;
              v72 = v190;
              v71 = v203;
              v69 = v204;
              v68 = v201;
            }
            v73 = *(unsigned int *)(v7 + 44);
            v72 += v73;
            v70 = v200;
          }
        }
LABEL_109:
        v180 = v18;
      }
    }
    v5 = v211;
LABEL_55:
    v43 = v218;
    if ( v18 < 0 )
      goto LABEL_76;
    if ( v218 )
      ((void (*)(void))v218->lpVtbl->Release)();
    v16 = v219;
  }
  if ( v62 != 1 && v62 != 6 )
  {
    v101 = 1;
    v234 = &v203;
    goto LABEL_175;
  }
  if ( i )
  {
    v107 = v217;
    goto LABEL_190;
  }
  v237[1] = (_com_error *)&v206;
  v206 = *v5;
  _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(&v206);
  v107 = v217;
  LODWORD(v203) = NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
                    v7,
                    v217,
                    v210,
                    (unsigned int)&v206,
                    (__int64)&v209,
                    (__int64)&v216,
                    1);
  if ( (int)v203 >= 0 )
  {
LABEL_190:
    if ( v62 == 6 && !i )
    {
      v108 = *(unsigned int *)(v7 + 72);
      LODWORD(v203) = v108 + v207;
      v109 = HIDWORD(v207);
      v110 = HIDWORD(v207);
      v197 = HIDWORD(v207);
      v204 = (struct IUnknown *)(*(_QWORD *)(v107 + 8) + 2 * ((int)v207 + v108));
      v111 = HIDWORD(v207);
      *(_DWORD *)v184 = HIDWORD(v207);
      v18 = 0;
      v112 = *(_DWORD *)(v7 + 44);
      v200 = v112;
      v113 = 0;
      v114 = v112;
      while ( 1 )
      {
        v193 = v113;
        if ( (unsigned int)v113 >= v111 )
          goto LABEL_178;
        v115 = v111 - v113;
        v116 = v114;
        if ( v115 <= v114 )
          v116 = v115;
        if ( v110 > v112 )
          v109 = v116;
        v201 = v109;
        if ( v114 == 1 )
        {
          if ( (unsigned __int16)(*((_WORD *)&v204->lpVtbl + (unsigned int)v113) + 10240) <= 0x7FFu )
            goto LABEL_202;
          v113 = (unsigned int)v113;
        }
        if ( v13 == 13 && v116 < 0x40 )
        {
          v167 = 0;
          if ( v116 )
          {
            v168 = (char *)v204 + 2 * (unsigned int)v113;
            do
            {
              v169 = *(unsigned __int16 *)&v168[2 * v167];
              if ( v169 == 8216 || v169 == 8217 || v169 == 8242 || v169 == 65287 )
                LOWORD(v169) = 39;
              *((_WORD *)&v237[19] + v167++) = v169;
            }
            while ( v167 < v116 );
            v5 = v211;
            v62 = v199;
          }
          if ( 2 * (unsigned __int64)v167 >= 0x80 )
            _report_rangecheckfailure(v113);
          *((_WORD *)&v237[19] + v167) = 0;
        }
        v18 =  IWordFormSink::`vcall'{24,{flat}}(v221);
        if ( v18 < 0 )
          goto LABEL_178;
        v109 = v201;
        v112 = v200;
        v110 = v197;
LABEL_202:
        v114 = *(_DWORD *)(v7 + 44);
        v113 = v114 + v193;
        v111 = *(_DWORD *)v184;
      }
    }
    v234 = &v203;
    v101 = 0;
    if ( v62 == 1 )
    {
LABEL_247:
      v102 = (__int64 *)&v218;
    }
    else
    {
LABEL_175:
      if ( v62 == 6 )
        goto LABEL_247;
      v102 = v5;
    }
    v203 = *v102;
    _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(&v203);
    v18 = NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(
            v7,
            v217,
            v210,
            (unsigned int)&v203,
            (__int64)&v209,
            (__int64)&v207,
            v101);
LABEL_178:
    v180 = v18;
    if ( v18 < 0 )
    {
LABEL_75:
      v43 = v218;
LABEL_76:
      if ( v43 )
        ((void (__fastcall *)(struct IUnknown *))v43->lpVtbl->Release)(v43);
      _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v5);
      return (unsigned int)v18;
    }
    v187 = v62 == 1;
    v61 = v202;
    goto LABEL_95;
  }
  if ( v218 )
LABEL_254:
    ((void (__fastcall *)(struct IUnknown *))v218->lpVtbl->Release)(v218);
LABEL_255:
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(v5);
  return (unsigned int)v203;
}

```

## disassembly

```asm
0x180005b50  push    rbx
0x180005b52  push    rsi
0x180005b53  push    rdi
0x180005b54  push    r12
0x180005b56  push    r13
0x180005b58  push    r14
0x180005b5a  push    r15
0x180005b5c  sub     rsp, 710h
0x180005b63  mov     [rsp+748h+var_5D0], 0FFFFFFFFFFFFFFFEh
0x180005b6f  mov     rax, cs:__security_cookie
0x180005b76  xor     rax, rsp
0x180005b79  mov     [rsp+748h+var_48], rax
0x180005b81  mov     rdi, r9
0x180005b84  mov     [rsp+748h+var_6A8], r9
0x180005b8c  mov     [rsp+748h+var_6B0], r8
0x180005b94  mov     rsi, rdx
0x180005b97  mov     [rsp+748h+var_680], rdx
0x180005b9f  mov     r13, rcx
0x180005ba2  mov     [rsp+748h+var_618], rcx
0x180005baa  mov     [rsp+748h+var_610], rdx
0x180005bb2  mov     [rsp+748h+var_608], r9
0x180005bba  mov     rax, [rsp+748h+arg_20]
0x180005bc2  mov     [rsp+748h+var_5F0], rax
0x180005bca  xor     r15d, r15d
0x180005bcd  mov     [rsp+748h+var_6B4], r15d
0x180005bd5  mov     rbx, [r9]
0x180005bd8  test    rbx, rbx
0x180005bdb  jz      loc_18000720D
0x180005be1  mov     [rsp+748h+var_688], r15
0x180005be9  mov     rax, [rbx]
0x180005bec  lea     rdx, [rsp+748h+var_688]
0x180005bf4  mov     rcx, rbx
0x180005bf7  mov     rax, [rax+20h]
0x180005bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c00  test    eax, eax
0x180005c02  js      loc_18000721A
0x180005c08  cmp     dword ptr [rsp+748h+var_688+4], r15d
0x180005c10  jz      loc_1800073F5
0x180005c16  mov     rbx, [rdi]
0x180005c19  mov     rdx, [rbx+28h]
0x180005c1d  mov     rax, [rdx+8]
0x180005c21  movsxd  r9, dword ptr [rax+4]
0x180005c25  add     r9, rdx
0x180005c28  mov     ecx, [r9+8]
0x180005c2c  mov     r12d, ecx
0x180005c2f  shr     r12d, 1Bh
0x180005c33  mov     [rsp+748h+var_660], r12d
0x180005c3b  lea     r10, ??_9IWordFormSink@@$BCA@AA; [thunk]: IWordFormSink::`vcall'{32,{flat}}
0x180005c42  mov     [rsp+748h+var_690], r10
0x180005c4a  mov     r14d, r15d
0x180005c4d  mov     [rsp+748h+var_6F0], r15d
0x180005c52  mov     [rsp+748h+var_704], 1
0x180005c57  mov     [rsp+748h+var_6FC], r14b
0x180005c5c  cmp     r12d, 0Dh
0x180005c60  setz    [rsp+748h+var_6F4]
0x180005c65  mov     edx, r12d
0x180005c68  sub     edx, 9
0x180005c6b  jz      loc_180005F11
0x180005c71  sub     edx, 1
0x180005c74  jz      loc_180006EB3
0x180005c7a  cmp     edx, 4
0x180005c7d  jz      loc_1800066BB
0x180005c83  test    rbx, rbx
0x180005c86  jz      loc_18000720D
0x180005c8c  mov     [rsp+748h+var_6F8], r15d
0x180005c91  mov     rax, [rbx]
0x180005c94  lea     rdx, [rsp+748h+var_6F8]
0x180005c99  mov     rcx, rbx
0x180005c9c  mov     rax, [rax+38h]
0x180005ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ca5  test    eax, eax
0x180005ca7  js      loc_18000722C
0x180005cad  mov     eax, [rsp+748h+var_6F8]
0x180005cb1  mov     r10, [rsp+748h+var_690]
0x180005cb9  mov     [rsp+748h+var_670], eax
0x180005cc0  mov     [rsp+748h+var_64C], r12d
0x180005cc8  mov     [rsp+748h+var_630], r13
0x180005cd0  mov     [rsp+748h+var_658], rsi
0x180005cd8  mov     rcx, [rsp+748h+var_6B0]
0x180005ce0  mov     [rsp+748h+var_668], rcx
0x180005ce8  mov     [rsp+748h+var_628], rcx
0x180005cf0  mov     ebx, r15d
0x180005cf3  mov     dword ptr [rsp+748h+var_708], ebx; bool
0x180005cf7  mov     [rsp+748h+var_66C], r12d
0x180005cff  mov     [rsp+748h+var_648], r12d
0x180005d07  movzx   ecx, [rsp+748h+var_6F4]
0x180005d0c  mov     [rsp+748h+var_69F], cl
0x180005d13  mov     [rsp+748h+var_638], r10
0x180005d1b  mov     [rsp+748h+var_650], r14d
0x180005d23  mov     esi, r15d
0x180005d26  mov     [rsp+748h+var_6B8], esi
0x180005d2d  cmp     esi, eax
0x180005d2f  jl      loc_180005F69
0x180005d35  cmp     [rsp+748h+var_704], 0
0x180005d3a  jz      loc_18000611D
0x180005d40  cmp     r14d, 1
0x180005d44  jz      loc_180006115
0x180005d4a  lea     rax, [rsp+748h+var_658]
0x180005d52  mov     [rsp+748h+var_5E8], rax
0x180005d5a  mov     rcx, [rdi]
0x180005d5d  mov     [rsp+748h+var_658], rcx
0x180005d65  test    rcx, rcx
0x180005d68  jz      short loc_180005D77
0x180005d6a  mov     rax, [rcx]
0x180005d6d  mov     rax, [rax+8]
0x180005d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d76  nop
0x180005d77  mov     dword ptr [rsp+748h+var_718], r15d
0x180005d7c  lea     rax, [rsp+748h+var_688]
0x180005d84  mov     [rsp+748h+var_720], rax
0x180005d89  lea     rax, [rsp+748h+var_6B4]
0x180005d91  mov     [rsp+748h+var_728], rax
0x180005d96  lea     r9, [rsp+748h+var_658]
0x180005d9e  mov     r8, [rsp+748h+var_6B0]
0x180005da6  mov     r14, [rsp+748h+var_680]
0x180005dae  mov     rdx, r14
0x180005db1  mov     rcx, r13
0x180005db4  call    ?OutputRepresentations@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJPEAUtagTEXT_SOURCE@@PEAUIWordSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@AEAHPEAUSTextRange@2@H@Z; NaturalLanguage6::CNLGSentenceSeparator::OutputRepresentations(tagTEXT_SOURCE *,IWordSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,int &,NaturalLanguage6::STextRange *,int)
0x180005db9  mov     ebx, eax
0x180005dbb  test    eax, eax
0x180005dbd  js      loc_180005EE9
0x180005dc3  cmp     [rsp+748h+var_6B4], 0
0x180005dcb  jnz     loc_180005EC8
0x180005dd1  mov     edx, [r13+48h]
0x180005dd5  mov     rax, [rsp+748h+var_688]
0x180005ddd  lea     r10d, [rax+rdx]
0x180005de1  mov     [rsp+748h+var_670], r10d
0x180005de9  mov     esi, dword ptr [rsp+748h+var_688+4]
0x180005df0  mov     r11d, esi
0x180005df3  movsxd  rcx, eax
0x180005df6  add     rcx, rdx
0x180005df9  mov     rax, [r14+8]
0x180005dfd  lea     r9, [rax+rcx*2]
0x180005e01  mov     [rsp+748h+var_640], r9
0x180005e09  mov     r14d, esi
0x180005e0c  mov     ebx, r15d
0x180005e0f  mov     r8d, [r13+2Ch]
0x180005e13  mov     dword ptr [rsp+748h+var_698], r8d
0x180005e1b  mov     edi, r15d
0x180005e1e  mov     ecx, r8d
0x180005e21  cmp     edi, r14d
0x180005e24  jnb     loc_180005EB4
0x180005e2a  mov     eax, r14d
0x180005e2d  sub     eax, edi
0x180005e2f  mov     edx, ecx
0x180005e31  cmp     eax, ecx
0x180005e33  cmovbe  edx, eax
0x180005e36  cmp     r11d, r8d
0x180005e39  cmova   esi, edx
0x180005e3c  cmp     ecx, 1
0x180005e3f  jz      loc_18000612A
0x180005e45  cmp     r12d, 0Dh
0x180005e49  jz      loc_180007137
0x180005e4f  mov     eax, edi
0x180005e51  lea     r8, [r9+rax*2]
0x180005e55  lea     eax, [r10+rdi]
0x180005e59  mov     dword ptr [rsp+748h+var_728], eax
0x180005e5d  mov     r9d, esi
0x180005e60  mov     rcx, [rsp+748h+var_668]
0x180005e68  call    ??_9IWordFormSink@@$BBI@AA; [thunk]: IWordFormSink::`vcall'{24,{flat}}
0x180005e6d  mov     ebx, eax
0x180005e6f  test    eax, eax
0x180005e71  jns     short loc_180005EEB
0x180005e73  mov     rdi, [rsp+748h+var_6A8]
0x180005e7b  mov     rcx, [rdi]
0x180005e7e  test    rcx, rcx
0x180005e81  jz      short loc_180005E8F
0x180005e83  mov     rax, [rcx]
0x180005e86  mov     rax, [rax+10h]
0x180005e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8f  mov     eax, ebx
0x180005e91  mov     rcx, [rsp+748h+var_48]
0x180005e99  xor     rcx, rsp; StackCookie
0x180005e9c  call    __security_check_cookie
0x180005ea1  add     rsp, 710h
0x180005ea8  pop     r15
0x180005eaa  pop     r14
0x180005eac  pop     r13
0x180005eae  pop     r12
0x180005eb0  pop     rdi
0x180005eb1  pop     rsi
0x180005eb2  pop     rbx
0x180005eb3  retn
0x180005eb4  test    ebx, ebx
0x180005eb6  js      short loc_180005E73
0x180005eb8  mov     rdi, [rsp+748h+var_6A8]
0x180005ec0  mov     r14, [rsp+748h+var_680]
0x180005ec8  mov     eax, [r13+48h]
0x180005ecc  add     eax, dword ptr [rsp+748h+var_688]
0x180005ed3  add     eax, dword ptr [rsp+748h+var_688+4]
0x180005eda  mov     [r14+14h], eax
0x180005ede  mov     rax, [rsp+748h+var_5F0]
0x180005ee6  mov     byte ptr [rax], 1
0x180005ee9  jmp     short loc_180005E7B
0x180005eeb  mov     r8d, dword ptr [rsp+748h+var_698]
0x180005ef3  mov     r9, [rsp+748h+var_640]
0x180005efb  mov     r10d, [rsp+748h+var_670]
0x180005f03  mov     r11d, r14d
0x180005f06  mov     ecx, [r13+2Ch]
0x180005f0a  add     edi, ecx
0x180005f0c  jmp     loc_180005E21
0x180005f11  mov     eax, ecx
0x180005f13  shr     eax, 8
0x180005f16  movzx   r14d, al
0x180005f1a  mov     [rsp+748h+var_6F0], r14d
0x180005f1f  and     ecx, 7FF0000h
0x180005f25  sub     ecx, 0A50000h
0x180005f2b  test    ecx, 0FFFCFFFFh
0x180005f31  jz      loc_1800066B1
0x180005f37  mov     [rsp+748h+var_6FC], 0
0x180005f3c  cmp     r14d, 6
0x180005f40  ja      loc_180005C83
0x180005f46  mov     eax, 4Ah ; 'J'
0x180005f4b  bt      eax, r14d
0x180005f4f  jnb     loc_180005C83
0x180005f55  lea     rax, ??_9IWordFormSink@@$BBI@AA; [thunk]: IWordFormSink::`vcall'{24,{flat}}
0x180005f5c  mov     [rsp+748h+var_690], rax
0x180005f64  jmp     loc_180005C83
0x180005f69  mov     rcx, [rdi]; struct IUnknown *
0x180005f6c  test    rcx, rcx
0x180005f6f  jz      loc_1800074C9
0x180005f75  mov     r8d, esi
0x180005f78  lea     rdx, [rsp+748h+var_678]
0x180005f80  call    ?GetItem@ITextSegment@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::ITextSegment::GetItem(long)
0x180005f85  nop
0x180005f86  mov     rcx, [rsp+748h+var_678]
0x180005f8e  mov     [rsp+748h+var_6D8], rcx
0x180005f93  test    rcx, rcx
0x180005f96  jz      loc_1800074D6
0x180005f9c  mov     [rsp+748h+var_6C0], r15
0x180005fa4  mov     rax, [rcx]
0x180005fa7  lea     rdx, [rsp+748h+var_6C0]
0x180005faf  mov     rax, [rax+20h]
0x180005fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb8  test    eax, eax
0x180005fba  js      loc_1800073E1
0x180005fc0  cmp     dword ptr [r13+690h], 0
0x180005fc8  jnz     loc_180006254
0x180005fce  mov     eax, r15d
0x180005fd1  lea     rcx, ??_9IWordFormSink@@$BBI@AA; [thunk]: IWordFormSink::`vcall'{24,{flat}}
0x180005fd8  mov     rdx, [rsp+748h+var_638]
0x180005fe0  cmp     rdx, rcx
0x180005fe3  setz    al
0x180005fe6  mov     [rsp+748h+var_6B4], eax
0x180005fed  cmp     [rsp+748h+var_704], 0
0x180005ff2  jnz     loc_180006149
0x180005ff8  test    esi, esi
0x180005ffa  jle     loc_180006245
0x180006000  cmp     r14d, 1
0x180006004  jz      loc_1800060E6
0x18000600a  mov     rax, [rsp+748h+var_630]
0x180006012  mov     r8d, [rax+48h]
0x180006016  mov     rax, [rsp+748h+var_658]
0x18000601e  mov     r9, [rax+8]
0x180006022  mov     rax, [rsp+748h+var_6C0]
0x18000602a  mov     ebx, r15d
0x18000602d  lea     ecx, [r8+rax]
0x180006031  cmp     [rsp+748h+var_6FC], 0
0x180006036  jnz     loc_180006B46
0x18000603c  mov     [rsp+748h+var_6EC], ecx
0x180006040  mov     edx, dword ptr [rsp+748h+var_6C0+4]
0x180006047  mov     dword ptr [rsp+748h+var_698], edx
0x18000604e  movsxd  rcx, eax
0x180006051  add     rcx, r8
0x180006054  lea     r11, [r9+rcx*2]
0x180006058  mov     [rsp+748h+var_6D8], r11
0x18000605d  mov     eax, edx
0x18000605f  mov     [rsp+748h+var_700], edx
0x180006063  mov     r9d, [r13+2Ch]
0x180006067  mov     [rsp+748h+var_6E8], r9d
0x18000606c  mov     r8d, r15d
0x18000606f  mov     ecx, r9d
0x180006072  mov     [rsp+748h+var_6F8], r8d
0x180006077  cmp     r8d, eax
0x18000607a  jnb     short loc_1800060E2
0x18000607c  sub     eax, r8d
0x18000607f  mov     r10d, ecx
0x180006082  cmp     eax, ecx
0x180006084  cmovbe  r10d, eax
0x180006088  cmp     dword ptr [rsp+748h+var_698], r9d
0x180006090  cmova   edx, r10d
0x180006094  mov     dword ptr [rsp+748h+var_6E0], edx
0x180006098  cmp     ecx, 1
0x18000609b  jz      loc_1800066FA
0x1800060a1  cmp     r12d, 0Dh
0x1800060a5  jz      loc_180007281
0x1800060ab  mov     ecx, [rsp+748h+var_6EC]
0x1800060af  add     ecx, r8d
0x1800060b2  mov     eax, r8d
0x1800060b5  lea     r8, [r11+rax*2]
0x1800060b9  mov     dword ptr [rsp+748h+var_728], ecx
0x1800060bd  mov     r9d, edx
0x1800060c0  mov     edx, r10d
0x1800060c3  mov     rcx, [rsp+748h+var_6B0]
0x1800060cb  mov     rax, [rsp+748h+var_690]
0x1800060d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d8  mov     ebx, eax
0x1800060da  test    eax, eax
0x1800060dc  jns     loc_180006441
0x1800060e2  mov     dword ptr [rsp+748h+var_708], ebx
  ... truncated ...
```
