# ValidateSignature(CSignatureParser const *,CSignatureParser const *,PipelineStage,PipelineStage,CSignatureParser const *,void *,void (*)(void *,D3D12_MESSAGE_ID,char const *),char const *)

- ea: `0x180178910`
- end: `0x1801793c8`
- name: `?ValidateSignature@@YAIPEBVCSignatureParser@@0W4PipelineStage@@10PEAXP6AX2W4D3D12_MESSAGE_ID@@PEBD@Z4@Z`
- size: `2744`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18015055c`
- `0x18016d260`
- `0x18016d57c`

## callees

- `0x18009fd4c`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x180102704`
- `0x1801762e4`
- `0x180178910`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178afa`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178c01`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178d01`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178e4d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178f4b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017905c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179169`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179322`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178afa`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178c01`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178d01`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178e4d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178f4b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017905c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179169`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180179322`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1801789d9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180178a21`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179200`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017921e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179236`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017924e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179266`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017927e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1801789d9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180178a21`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179200`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017921e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179236`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017924e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180179266`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18017927e`

## string_xrefs

- `0x180178e56`: `' of the input stage has a hardware register component mask that does not match the output of the previous stage.`
- `0x180178f54`: `' of the input stage has a hardware register component mask that is not a subset of the output of the previous stage.`
- `0x180179065`: `' is always read by the downstream shader, but never written by the upstream shader (even though the semantic is present in its output signature).`
- `0x180178abe`: ` linkage error: Signatures between stages are incompatible. `
- `0x180178bc5`: ` linkage error: Signatures between stages are incompatible. `
- `0x180178cc5`: ` linkage error: Signatures between stages are incompatible. `
- `0x180178e11`: ` linkage error: Signatures between stages are incompatible. `
- `0x180178f0f`: ` linkage error: Signatures between stages are incompatible. `
- `0x180179020`: ` linkage error: Signatures between stages are incompatible. `
- `0x18017912d`: ` linkage error: Signatures between stages are incompatible. `
- `0x1801792e7`: ` linkage error: Signatures between stages are incompatible. `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ValidateSignature(
        __int64 *a1,
        __int64 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 *a5,
        __int64 a6,
        void (__fastcall *a7)(__int64, __int64, _QWORD *))
{
  __int64 v7; // r12
  __int64 v8; // rsi
  unsigned int v9; // r9d
  __int64 v10; // rdx
  unsigned int v11; // ecx
  unsigned int v12; // ebx
  __int64 v13; // r15
  _QWORD *v14; // rdi
  __int64 v15; // r14
  __int64 v16; // r15
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // r15d
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  _QWORD *v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  _QWORD *v49; // r8
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // r8
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  _QWORD *v65; // r8
  unsigned int v66; // edi
  unsigned int v67; // edx
  unsigned int v68; // r15d
  unsigned int v69; // r12d
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rax
  __int64 v78; // r8
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  _QWORD *v85; // r8
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rax
  __int64 v89; // r8
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rax
  __int64 v94; // r8
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  _QWORD *v101; // r8
  __int64 v102; // rax
  unsigned int v103; // edi
  __int64 v104; // rdx
  __int64 v105; // rax
  __int64 v106; // r8
  __int64 v107; // rax
  __int64 v108; // rax
  unsigned int v109; // r15d
  __int64 v110; // rdx
  __int64 v111; // rax
  __int64 v112; // r8
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rax
  _QWORD *v119; // r8
  __int64 v120; // rax
  __int64 v121; // rdx
  __int64 v122; // rax
  __int64 v123; // r8
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rax
  __int64 v128; // r8
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 v134; // rax
  _QWORD *v135; // r8
  __int64 v136; // rax
  __int64 v137; // rdx
  __int64 PipelineStageName; // rax
  __int64 v139; // r8
  __int64 v140; // rax
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rax
  __int64 v144; // r8
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  _QWORD *v151; // r8
  unsigned int v155; // [rsp+28h] [rbp-D8h]
  unsigned int v156; // [rsp+2Ch] [rbp-D4h]
  unsigned int v157; // [rsp+38h] [rbp-C8h]
  unsigned int v158; // [rsp+3Ch] [rbp-C4h]
  unsigned int v159; // [rsp+40h] [rbp-C0h]
  __int64 v160; // [rsp+48h] [rbp-B8h]
  __int64 v161; // [rsp+50h] [rbp-B0h]
  _BYTE v162[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v163[232]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v164[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v165; // [rsp+168h] [rbp+68h]

  v7 = a6;
  v8 = *a2;
  v9 = *((_DWORD *)a2 + 4);
  v159 = v9;
  if ( a1 )
  {
    v10 = *a1;
    v11 = *((_DWORD *)a1 + 4);
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  v156 = v11;
  v160 = v10;
  if ( a5 )
  {
    v161 = *a5;
    v157 = *((_DWORD *)a5 + 4);
  }
  else
  {
    v161 = 0;
    v157 = 0;
  }
  v12 = 0;
  v158 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      v13 = 0;
      v14 = (_QWORD *)(v8 + 8);
      while ( 1 )
      {
        if ( (unsigned int)v13 >= v11 )
          goto LABEL_14;
        v15 = v10 + 40 * v13;
        v14 = (_QWORD *)(v8 + 8);
        if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v8 + 8), *(_QWORD *)(v15 + 8))
          && *(_DWORD *)(v8 + 16) == *(_DWORD *)(v15 + 16) )
        {
          break;
        }
        v13 = (unsigned int)(v13 + 1);
        v11 = v156;
        v10 = v160;
      }
      if ( !v15 )
      {
LABEL_14:
        v16 = 0;
        while ( (unsigned int)v16 < v157 )
        {
          v15 = v161 + 40 * v16;
          if ( !(unsigned int)_o__stricmp(*v14, *(_QWORD *)(v15 + 8)) && *(_DWORD *)(v8 + 16) == *(_DWORD *)(v15 + 16) )
          {
            if ( v15 )
              goto LABEL_20;
            break;
          }
          v16 = (unsigned int)(v16 + 1);
          v14 = (_QWORD *)(v8 + 8);
        }
        if ( a4 - 4 > 1
          || (((a3 - 1) & 0xFFFFFFFD) != 0 || (unsigned int)_o__stricmp(*v14, "SV_PrimitiveID"))
          && (a4 != 5
           || (unsigned int)_o__stricmp(*v14, "SV_IsFrontFace")
           && (unsigned int)_o__stricmp(*v14, "SV_SampleIndex")
           && (unsigned int)_o__stricmp(*v14, "SV_Coverage")
           && (unsigned int)_o__stricmp(*v14, "SV_Barycentrics")
           && (unsigned int)_o__stricmp(*v14, "SV_ShadingRate")) )
        {
          std::ostringstream::ostringstream(v162);
          v136 = std::operator<<<std::char_traits<char>>(v162, Src);
          PipelineStageName = GetPipelineStageName(a3, v137, v136);
          v140 = std::operator<<<std::char_traits<char>>(v139, PipelineStageName);
          v141 = std::operator<<<std::char_traits<char>>(v140, " - ");
          v143 = GetPipelineStageName(a4, v142, v141);
          v145 = std::operator<<<std::char_traits<char>>(v144, v143);
          v146 = std::operator<<<std::char_traits<char>>(
                   v145,
                   " linkage error: Signatures between stages are incompatible. ");
          v147 = std::operator<<<std::char_traits<char>>(v146, "The input stage requires Semantic / Index(");
          v148 = std::operator<<<std::char_traits<char>>(v147, *v14);
          v149 = std::operator<<<std::char_traits<char>>(v148, ", ");
          v150 = std::ostream::operator<<(v149, *(unsigned int *)(v8 + 16));
          std::operator<<<std::char_traits<char>>(v150, ") as input, but it is not provided by the output stage.");
          if ( a7 )
          {
            std::stringbuf::str(v163, v164);
            v151 = v164;
            if ( v165 > 0xF )
              v151 = (_QWORD *)v164[0];
            a7(v7, 666, v151);
            std::string::_Tidy_deallocate(v164);
          }
          goto LABEL_74;
        }
        goto LABEL_90;
      }
LABEL_20:
      if ( a3 == 6 || *(_DWORD *)(v8 + 28) == *(_DWORD *)(v15 + 28) )
      {
        v23 = a4;
      }
      else
      {
        std::ostringstream::ostringstream(v162);
        v17 = std::operator<<<std::char_traits<char>>(v162, Src);
        v19 = GetPipelineStageName(a3, v18, v17);
        v21 = std::operator<<<std::char_traits<char>>(v20, v19);
        v22 = std::operator<<<std::char_traits<char>>(v21, " - ");
        v23 = a4;
        v25 = GetPipelineStageName(a4, v24, v22);
        v27 = std::operator<<<std::char_traits<char>>(v26, v25);
        v28 = std::operator<<<std::char_traits<char>>(
                v27,
                " linkage error: Signatures between stages are incompatible. ");
        v29 = std::operator<<<std::char_traits<char>>(v28, "Semantic '");
        v30 = std::operator<<<std::char_traits<char>>(v29, *(_QWORD *)(v8 + 8));
        v31 = std::operator<<<std::char_traits<char>>(v30, "', Index '");
        v32 = std::ostream::operator<<(v31, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v32,
          "' is defined for mismatched hardware registers between the output stage and input stage.");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v33 = v164;
          if ( v165 > 0xF )
            v33 = (_QWORD *)v164[0];
          a7(v7, 660, v33);
          std::string::_Tidy_deallocate(v164);
        }
        std::ostringstream::`vbase destructor'(v162);
        ++v12;
      }
      if ( *(_DWORD *)(v8 + 24) != *(_DWORD *)(v15 + 24) )
      {
        std::ostringstream::ostringstream(v162);
        v34 = std::operator<<<std::char_traits<char>>(v162, Src);
        v36 = GetPipelineStageName(a3, v35, v34);
        v38 = std::operator<<<std::char_traits<char>>(v37, v36);
        v39 = std::operator<<<std::char_traits<char>>(v38, " - ");
        v41 = GetPipelineStageName(v23, v40, v39);
        v43 = std::operator<<<std::char_traits<char>>(v42, v41);
        v44 = std::operator<<<std::char_traits<char>>(
                v43,
                " linkage error: Signatures between stages are incompatible. ");
        v45 = std::operator<<<std::char_traits<char>>(v44, "Semantic '");
        v46 = std::operator<<<std::char_traits<char>>(v45, *(_QWORD *)(v8 + 8));
        v47 = std::operator<<<std::char_traits<char>>(v46, "', Index '");
        v48 = std::ostream::operator<<(v47, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v48,
          "' has mismatched data types between the output stage and input stage.");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v49 = v164;
          if ( v165 > 0xF )
            v49 = (_QWORD *)v164[0];
          a7(v7, 661, v49);
          std::string::_Tidy_deallocate(v164);
        }
        std::ostringstream::`vbase destructor'(v162);
        ++v12;
      }
      if ( *(_DWORD *)(v8 + 20) != *(_DWORD *)(v15 + 20) )
      {
        std::ostringstream::ostringstream(v162);
        v50 = std::operator<<<std::char_traits<char>>(v162, Src);
        v52 = GetPipelineStageName(a3, v51, v50);
        v54 = std::operator<<<std::char_traits<char>>(v53, v52);
        v55 = std::operator<<<std::char_traits<char>>(v54, " - ");
        v57 = GetPipelineStageName(v23, v56, v55);
        v59 = std::operator<<<std::char_traits<char>>(v58, v57);
        v60 = std::operator<<<std::char_traits<char>>(
                v59,
                " linkage error: Signatures between stages are incompatible. ");
        v61 = std::operator<<<std::char_traits<char>>(v60, "Semantic '");
        v62 = std::operator<<<std::char_traits<char>>(v61, *(_QWORD *)(v8 + 8));
        v63 = std::operator<<<std::char_traits<char>>(v62, "', Index '");
        v64 = std::ostream::operator<<(v63, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v64,
          "' has a different system value defined in the output stage vs input stage.");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v65 = v164;
          if ( v165 > 0xF )
            v65 = (_QWORD *)v164[0];
          a7(v7, 663, v65);
          std::string::_Tidy_deallocate(v164);
        }
        std::ostringstream::`vbase destructor'(v162);
        ++v12;
      }
      v66 = *(unsigned __int8 *)(v8 + 32);
      v67 = *(unsigned __int8 *)(v8 + 33);
      v155 = v67;
      v68 = *(unsigned __int8 *)(v15 + 32);
      v69 = *(unsigned __int8 *)(v15 + 33);
      if ( a3 == 6 )
        break;
      if ( (v66 & v68) != v66 )
      {
        std::ostringstream::ostringstream(v162);
        v86 = std::operator<<<std::char_traits<char>>(v162, Src);
        v88 = GetPipelineStageName(a3, v87, v86);
        v90 = std::operator<<<std::char_traits<char>>(v89, v88);
        v91 = std::operator<<<std::char_traits<char>>(v90, " - ");
        v93 = GetPipelineStageName(a4, v92, v91);
        v95 = std::operator<<<std::char_traits<char>>(v94, v93);
        v96 = std::operator<<<std::char_traits<char>>(
                v95,
                " linkage error: Signatures between stages are incompatible. ");
        v97 = std::operator<<<std::char_traits<char>>(v96, "Semantic '");
        v98 = std::operator<<<std::char_traits<char>>(v97, *(_QWORD *)(v8 + 8));
        v99 = std::operator<<<std::char_traits<char>>(v98, "', Index '");
        v100 = std::ostream::operator<<(v99, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v100,
          "' of the input stage has a hardware register component mask that is not a subset of the output of the previous stage.");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v101 = v164;
          if ( v165 > 0xF )
            v101 = (_QWORD *)v164[0];
          a7(a6, 662, v101);
          std::string::_Tidy_deallocate(v164);
        }
LABEL_60:
        std::ostringstream::`vbase destructor'(v162);
        v67 = v155;
        ++v12;
      }
LABEL_61:
      if ( (v67 & v68 & v69 & v66) != 0 )
      {
        std::ostringstream::ostringstream(v162);
        v102 = std::operator<<<std::char_traits<char>>(v162, Src);
        v103 = a3;
        v105 = GetPipelineStageName(a3, v104, v102);
        v107 = std::operator<<<std::char_traits<char>>(v106, v105);
        v108 = std::operator<<<std::char_traits<char>>(v107, " - ");
        v109 = a4;
        v111 = GetPipelineStageName(a4, v110, v108);
        v113 = std::operator<<<std::char_traits<char>>(v112, v111);
        v114 = std::operator<<<std::char_traits<char>>(
                 v113,
                 " linkage error: Signatures between stages are incompatible. ");
        v115 = std::operator<<<std::char_traits<char>>(v114, "Semantic '");
        v116 = std::operator<<<std::char_traits<char>>(v115, *(_QWORD *)(v8 + 8));
        v117 = std::operator<<<std::char_traits<char>>(v116, "', Index '");
        v118 = std::ostream::operator<<(v117, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v118,
          "' is always read by the downstream shader, but never written by the upstream shader (even though the semantic "
          "is present in its output signature).");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v119 = v164;
          if ( v165 > 0xF )
            v119 = (_QWORD *)v164[0];
          a7(a6, 664, v119);
          std::string::_Tidy_deallocate(v164);
        }
        std::ostringstream::`vbase destructor'(v162);
        ++v12;
      }
      else
      {
        v103 = a3;
        v109 = a4;
      }
      if ( *(_DWORD *)(v8 + 36) != *(_DWORD *)(v15 + 36) )
      {
        std::ostringstream::ostringstream(v162);
        v120 = std::operator<<<std::char_traits<char>>(v162, Src);
        v122 = GetPipelineStageName(v103, v121, v120);
        v124 = std::operator<<<std::char_traits<char>>(v123, v122);
        v125 = std::operator<<<std::char_traits<char>>(v124, " - ");
        v127 = GetPipelineStageName(v109, v126, v125);
        v129 = std::operator<<<std::char_traits<char>>(v128, v127);
        v130 = std::operator<<<std::char_traits<char>>(
                 v129,
                 " linkage error: Signatures between stages are incompatible. ");
        v131 = std::operator<<<std::char_traits<char>>(v130, "Semantic '");
        v132 = std::operator<<<std::char_traits<char>>(v131, *(_QWORD *)(v8 + 8));
        v133 = std::operator<<<std::char_traits<char>>(v132, "', Index '");
        v134 = std::ostream::operator<<(v133, *(unsigned int *)(v8 + 16));
        std::operator<<<std::char_traits<char>>(
          v134,
          "' in each signature have different min precision levels, when they must be identical.");
        if ( a7 )
        {
          std::stringbuf::str(v163, v164);
          v135 = v164;
          if ( v165 > 0xF )
            v135 = (_QWORD *)v164[0];
          v7 = a6;
          a7(a6, 665, v135);
          std::string::_Tidy_deallocate(v164);
        }
        else
        {
          v7 = a6;
        }
LABEL_74:
        std::ostringstream::`vbase destructor'(v162);
        ++v12;
        goto LABEL_90;
      }
      v7 = a6;
LABEL_90:
      ++v158;
      v8 += 40;
      v11 = v156;
      v10 = v160;
      if ( v158 >= v159 )
        return v12;
    }
    if ( *(_BYTE *)(v8 + 32) && (v66 & 1) == 0 )
    {
      do
      {
        v66 >>= 1;
        v67 >>= 1;
      }
      while ( (v66 & 1) == 0 );
      v155 = v67;
    }
    if ( *(_BYTE *)(v15 + 32) )
    {
      while ( (v68 & 1) == 0 )
      {
        v68 >>= 1;
        v69 >>= 1;
      }
    }
    if ( v66 == v68 )
      goto LABEL_61;
    std::ostringstream::ostringstream(v162);
    v70 = std::operator<<<std::char_traits<char>>(v162, Src);
    v72 = GetPipelineStageName(6, v71, v70);
    v74 = std::operator<<<std::char_traits<char>>(v73, v72);
    v75 = std::operator<<<std::char_traits<char>>(v74, " - ");
    v77 = GetPipelineStageName(a4, v76, v75);
    v79 = std::operator<<<std::char_traits<char>>(v78, v77);
    v80 = std::operator<<<std::char_traits<char>>(v79, " linkage error: Signatures between stages are incompatible. ");
    v81 = std::operator<<<std::char_traits<char>>(v80, "Semantic '");
    v82 = std::operator<<<std::char_traits<char>>(v81, *(_QWORD *)(v8 + 8));
    v83 = std::operator<<<std::char_traits<char>>(v82, "', Index '");
    v84 = std::ostream::operator<<(v83, *(unsigned int *)(v8 + 16));
    std::operator<<<std::char_traits<char>>(
      v84,
      "' of the input stage has a hardware register component mask that does not match the output of the previous stage.");
    if ( a7 )
    {
      std::stringbuf::str(v163, v164);
      v85 = v164;
      if ( v165 > 0xF )
        v85 = (_QWORD *)v164[0];
      a7(a6, 662, v85);
      std::string::_Tidy_deallocate(v164);
    }
    goto LABEL_60;
  }
  return v12;
}

```

## disassembly

```asm
0x180178910  mov     [rsp-8+arg_0], rbx
0x180178915  push    rbp
0x180178916  push    rsi
0x180178917  push    rdi
0x180178918  push    r12
0x18017891a  push    r13
0x18017891c  push    r14
0x18017891e  push    r15
0x180178920  lea     rbp, [rsp-80h]
0x180178925  sub     rsp, 180h
0x18017892c  mov     rax, cs:__security_cookie
0x180178933  xor     rax, rsp
0x180178936  mov     [rbp+0B0h+var_40], rax
0x18017893a  mov     [rsp+1B0h+var_190], r9d
0x18017893f  mov     [rsp+1B0h+var_18C], r8d
0x180178944  mov     r12, [rbp+0B0h+arg_28]
0x18017894b  mov     [rsp+1B0h+var_180], r12
0x180178950  mov     r13, [rbp+0B0h+arg_30]
0x180178957  mov     rsi, [rdx]
0x18017895a  mov     r9d, [rdx+10h]
0x18017895e  mov     [rsp+1B0h+var_170], r9d
0x180178963  test    rcx, rcx
0x180178966  jz      short loc_180178970
0x180178968  mov     rdx, [rcx]
0x18017896b  mov     ecx, [rcx+10h]
0x18017896e  jmp     short loc_180178974
0x180178970  xor     edx, edx
0x180178972  xor     ecx, ecx
0x180178974  mov     [rsp+1B0h+var_184], ecx
0x180178978  mov     [rsp+1B0h+var_168], rdx
0x18017897d  mov     rax, [rbp+0B0h+arg_20]
0x180178984  test    rax, rax
0x180178987  jz      short loc_18017899A
0x180178989  mov     r8, [rax]
0x18017898c  mov     [rsp+1B0h+var_160], r8
0x180178991  mov     eax, [rax+10h]
0x180178994  mov     [rsp+1B0h+var_178], eax
0x180178998  jmp     short loc_1801789AB
0x18017899a  mov     [rsp+1B0h+var_160], 0
0x1801789a3  mov     [rsp+1B0h+var_178], 0
0x1801789ab  xor     ebx, ebx
0x1801789ad  mov     [rsp+1B0h+var_174], ebx
0x1801789b1  test    r9d, r9d
0x1801789b4  jz      loc_18017939F
0x1801789ba  xor     r15d, r15d
0x1801789bd  lea     rdi, [rsi+8]
0x1801789c1  cmp     r15d, ecx
0x1801789c4  jnb     short loc_1801789FF
0x1801789c6  lea     rcx, [r15+r15*4]
0x1801789ca  lea     r14, [rdx+rcx*8]
0x1801789ce  lea     rdi, [rsi+8]
0x1801789d2  mov     rdx, [r14+8]
0x1801789d6  mov     rcx, [rdi]
0x1801789d9  call    cs:__imp__o__stricmp
0x1801789df  test    eax, eax
0x1801789e1  jnz     short loc_1801789EC
0x1801789e3  mov     eax, [r14+10h]
0x1801789e7  cmp     [rsi+10h], eax
0x1801789ea  jz      short loc_1801789FA
0x1801789ec  inc     r15d
0x1801789ef  mov     ecx, [rsp+1B0h+var_184]
0x1801789f3  mov     rdx, [rsp+1B0h+var_168]
0x1801789f8  jmp     short loc_1801789C1
0x1801789fa  test    r14, r14
0x1801789fd  jnz     short loc_180178A46
0x1801789ff  xor     r15d, r15d
0x180178a02  cmp     r15d, [rsp+1B0h+var_178]
0x180178a07  jnb     loc_1801791D7
0x180178a0d  lea     rcx, [r15+r15*4]
0x180178a11  mov     rax, [rsp+1B0h+var_160]
0x180178a16  lea     r14, [rax+rcx*8]
0x180178a1a  mov     rdx, [r14+8]
0x180178a1e  mov     rcx, [rdi]
0x180178a21  call    cs:__imp__o__stricmp
0x180178a27  test    eax, eax
0x180178a29  jnz     short loc_180178A34
0x180178a2b  mov     eax, [r14+10h]
0x180178a2f  cmp     [rsi+10h], eax
0x180178a32  jz      short loc_180178A3D
0x180178a34  inc     r15d
0x180178a37  lea     rdi, [rsi+8]
0x180178a3b  jmp     short loc_180178A02
0x180178a3d  test    r14, r14
0x180178a40  jz      loc_1801791D7
0x180178a46  mov     edi, [rsp+1B0h+var_18C]
0x180178a4a  cmp     edi, 6
0x180178a4d  jz      loc_180178B5A
0x180178a53  mov     eax, [r14+1Ch]
0x180178a57  cmp     [rsi+1Ch], eax
0x180178a5a  jz      loc_180178B5A
0x180178a60  lea     rcx, [rsp+1B0h+var_150]
0x180178a65  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180178a6a  nop
0x180178a6b  lea     rdx, Src
0x180178a72  lea     rcx, [rsp+1B0h+var_150]
0x180178a77  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178a7c  mov     r8, rax
0x180178a7f  mov     ecx, edi
0x180178a81  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178a86  mov     rdx, rax
0x180178a89  mov     rcx, r8
0x180178a8c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178a91  mov     rcx, rax
0x180178a94  lea     rdx, asc_1802D0670; " - "
0x180178a9b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178aa0  mov     r8, rax
0x180178aa3  mov     r15d, [rsp+1B0h+var_190]
0x180178aa8  mov     ecx, r15d
0x180178aab  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178ab0  mov     rdx, rax
0x180178ab3  mov     rcx, r8
0x180178ab6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178abb  mov     rcx, rax
0x180178abe  lea     rdx, aLinkageErrorSi; " linkage error: Signatures between stag"...
0x180178ac5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178aca  mov     rcx, rax
0x180178acd  lea     rdx, aSemantic; "Semantic '"
0x180178ad4  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178ad9  mov     rdx, [rsi+8]
0x180178add  mov     rcx, rax
0x180178ae0  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178ae5  mov     rcx, rax
0x180178ae8  lea     rdx, aIndex; "', Index '"
0x180178aef  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178af4  mov     edx, [rsi+10h]
0x180178af7  mov     rcx, rax
0x180178afa  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180178b00  mov     rcx, rax
0x180178b03  lea     rdx, aIsDefinedForMi; "' is defined for mismatched hardware re"...
0x180178b0a  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178b0f  test    r13, r13
0x180178b12  jz      short loc_180178B4C
0x180178b14  lea     rdx, [rbp+0B0h+var_60]
0x180178b18  lea     rcx, [rsp+1B0h+var_148]
0x180178b1d  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180178b22  nop
0x180178b23  lea     r8, [rbp+0B0h+var_60]
0x180178b27  cmp     [rbp+0B0h+var_48], 0Fh
0x180178b2c  cmova   r8, [rbp+0B0h+var_60]
0x180178b31  mov     edx, 294h
0x180178b36  mov     rcx, r12
0x180178b39  mov     rax, r13
0x180178b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178b41  nop
0x180178b42  lea     rcx, [rbp+0B0h+var_60]
0x180178b46  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180178b4b  nop
0x180178b4c  lea     rcx, [rsp+1B0h+var_150]
0x180178b51  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180178b56  inc     ebx
0x180178b58  jmp     short loc_180178B5F
0x180178b5a  mov     r15d, [rsp+1B0h+var_190]
0x180178b5f  mov     eax, [r14+18h]
0x180178b63  cmp     [rsi+18h], eax
0x180178b66  jz      loc_180178C5F
0x180178b6c  lea     rcx, [rsp+1B0h+var_150]
0x180178b71  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180178b76  nop
0x180178b77  lea     rdx, Src
0x180178b7e  lea     rcx, [rsp+1B0h+var_150]
0x180178b83  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178b88  mov     r8, rax
0x180178b8b  mov     ecx, edi
0x180178b8d  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178b92  mov     rdx, rax
0x180178b95  mov     rcx, r8
0x180178b98  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178b9d  mov     rcx, rax
0x180178ba0  lea     rdx, asc_1802D0670; " - "
0x180178ba7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178bac  mov     r8, rax
0x180178baf  mov     ecx, r15d
0x180178bb2  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178bb7  mov     rdx, rax
0x180178bba  mov     rcx, r8
0x180178bbd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178bc2  mov     rcx, rax
0x180178bc5  lea     rdx, aLinkageErrorSi; " linkage error: Signatures between stag"...
0x180178bcc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178bd1  mov     rcx, rax
0x180178bd4  lea     rdx, aSemantic; "Semantic '"
0x180178bdb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178be0  mov     rdx, [rsi+8]
0x180178be4  mov     rcx, rax
0x180178be7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178bec  mov     rcx, rax
0x180178bef  lea     rdx, aIndex; "', Index '"
0x180178bf6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178bfb  mov     edx, [rsi+10h]
0x180178bfe  mov     rcx, rax
0x180178c01  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180178c07  mov     rcx, rax
0x180178c0a  lea     rdx, aHasMismatchedD; "' has mismatched data types between the"...
0x180178c11  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178c16  test    r13, r13
0x180178c19  jz      short loc_180178C53
0x180178c1b  lea     rdx, [rbp+0B0h+var_60]
0x180178c1f  lea     rcx, [rsp+1B0h+var_148]
0x180178c24  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180178c29  nop
0x180178c2a  lea     r8, [rbp+0B0h+var_60]
0x180178c2e  cmp     [rbp+0B0h+var_48], 0Fh
0x180178c33  cmova   r8, [rbp+0B0h+var_60]
0x180178c38  mov     edx, 295h
0x180178c3d  mov     rcx, r12
0x180178c40  mov     rax, r13
0x180178c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178c48  nop
0x180178c49  lea     rcx, [rbp+0B0h+var_60]
0x180178c4d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180178c52  nop
0x180178c53  lea     rcx, [rsp+1B0h+var_150]
0x180178c58  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180178c5d  inc     ebx
0x180178c5f  mov     eax, [r14+14h]
0x180178c63  cmp     [rsi+14h], eax
0x180178c66  jz      loc_180178D5F
0x180178c6c  lea     rcx, [rsp+1B0h+var_150]
0x180178c71  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180178c76  nop
0x180178c77  lea     rdx, Src
0x180178c7e  lea     rcx, [rsp+1B0h+var_150]
0x180178c83  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178c88  mov     r8, rax
0x180178c8b  mov     ecx, edi
0x180178c8d  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178c92  mov     rdx, rax
0x180178c95  mov     rcx, r8
0x180178c98  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178c9d  mov     rcx, rax
0x180178ca0  lea     rdx, asc_1802D0670; " - "
0x180178ca7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178cac  mov     r8, rax
0x180178caf  mov     ecx, r15d
0x180178cb2  call    ?GetPipelineStageName@@YAPEBDW4PipelineStage@@@Z; GetPipelineStageName(PipelineStage)
0x180178cb7  mov     rdx, rax
0x180178cba  mov     rcx, r8
0x180178cbd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178cc2  mov     rcx, rax
0x180178cc5  lea     rdx, aLinkageErrorSi; " linkage error: Signatures between stag"...
0x180178ccc  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178cd1  mov     rcx, rax
0x180178cd4  lea     rdx, aSemantic; "Semantic '"
0x180178cdb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178ce0  mov     rdx, [rsi+8]
0x180178ce4  mov     rcx, rax
0x180178ce7  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178cec  mov     rcx, rax
0x180178cef  lea     rdx, aIndex; "', Index '"
0x180178cf6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178cfb  mov     edx, [rsi+10h]
0x180178cfe  mov     rcx, rax
0x180178d01  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180178d07  mov     rcx, rax
0x180178d0a  lea     rdx, aHasADifferentS; "' has a different system value defined "...
0x180178d11  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180178d16  test    r13, r13
0x180178d19  jz      short loc_180178D53
0x180178d1b  lea     rdx, [rbp+0B0h+var_60]
0x180178d1f  lea     rcx, [rsp+1B0h+var_148]
0x180178d24  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180178d29  nop
0x180178d2a  lea     r8, [rbp+0B0h+var_60]
0x180178d2e  cmp     [rbp+0B0h+var_48], 0Fh
0x180178d33  cmova   r8, [rbp+0B0h+var_60]
0x180178d38  mov     edx, 297h
0x180178d3d  mov     rcx, r12
0x180178d40  mov     rax, r13
0x180178d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180178d48  nop
0x180178d49  lea     rcx, [rbp+0B0h+var_60]
0x180178d4d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180178d52  nop
0x180178d53  lea     rcx, [rsp+1B0h+var_150]
0x180178d58  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180178d5d  inc     ebx
0x180178d5f  movzx   edi, byte ptr [rsi+20h]
0x180178d63  movzx   edx, byte ptr [rsi+21h]
0x180178d67  mov     [rsp+1B0h+var_188], edx
0x180178d6b  movzx   r15d, byte ptr [r14+20h]
0x180178d70  movzx   r12d, byte ptr [r14+21h]
0x180178d75  cmp     [rsp+1B0h+var_18C], 6
0x180178d7a  jnz     loc_180178EA6
0x180178d80  test    edi, edi
0x180178d82  jz      short loc_180178D98
0x180178d84  test    dil, 1
0x180178d88  jnz     short loc_180178D98
0x180178d8a  shr     edi, 1
0x180178d8c  shr     edx, 1
0x180178d8e  test    dil, 1
0x180178d92  jz      short loc_180178D8A
0x180178d94  mov     [rsp+1B0h+var_188], edx
0x180178d98  test    r15d, r15d
0x180178d9b  jz      short loc_180178DAB
0x180178d9d  jmp     short loc_180178DA5
0x180178d9f  shr     r15d, 1
0x180178da2  shr     r12d, 1
0x180178da5  test    r15b, 1
0x180178da9  jz      short loc_180178D9F
0x180178dab  cmp     edi, r15d
  ... truncated ...
```
