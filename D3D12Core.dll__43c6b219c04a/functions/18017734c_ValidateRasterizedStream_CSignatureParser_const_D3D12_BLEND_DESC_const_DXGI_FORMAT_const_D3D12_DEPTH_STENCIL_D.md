# ValidateRasterizedStream(CSignatureParser const *,D3D12_BLEND_DESC const *,DXGI_FORMAT const *,D3D12_DEPTH_STENCIL_DESC2 const *,DXGI_FORMAT,long (*)(D3D12_FEATURE,void *,uint,void *),void *,void *,void (*)(void *,D3D12_MESSAGE_ID,char const *),void (*)(void *,D3D12_MESSAGE_ID,char const *),char const *)

- ea: `0x18017734c`
- end: `0x1801784d9`
- name: `?ValidateRasterizedStream@@YAIPEBVCSignatureParser@@PEBUD3D12_BLEND_DESC@@PEBW4DXGI_FORMAT@@PEBUD3D12_DEPTH_STENCIL_DESC2@@W43@P6AJW4D3D12_FEATURE@@PEAXI6@Z66P6AX6W4D3D12_MESSAGE_ID@@PEBD@ZP6AX689@Z9@Z`
- size: `4493`
- prototype: `unsigned int __fastcall(const struct CSignatureParser *, const struct D3D12_BLEND_DESC *, const enum DXGI_FORMAT *, const struct D3D12_DEPTH_STENCIL_DESC2 *, enum DXGI_FORMAT, int (*)(enum D3D12_FEATURE, void *, unsigned int, void *), void *, void *, void (*)(void *, enum D3D12_MESSAGE_ID, const char *), void (*)(void *, enum D3D12_MESSAGE_ID, const char *), const char *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18015055c`
- `0x18016cbe0`

## callees

- `0x18003f820`
- `0x18003f8b0`
- `0x1800489a0`
- `0x18005e09c`
- `0x18009fd4c`
- `0x1800abc10`
- `0x1800bb480`
- `0x1800cc130`
- `0x1800e85b0`
- `0x1800eb674`
- `0x180102704`
- `0x18017734c`
- `0x180262020`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18017768f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z` at `0x18017768f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177537`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177742`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177849`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177863`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177944`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177a4b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177a65`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177e29`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177e44`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f4f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f6a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f85`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177fc6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017809e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801780b9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178312`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017832d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178424`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177537`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177742`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177849`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177863`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177944`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177a4b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177a65`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177e29`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177e44`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f4f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f6a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177f85`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180177fc6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017809e`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x1801780b9`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178312`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18017832d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180178424`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1801774a5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180177b93`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1801774a5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180177b93`

## string_xrefs

- `0x18017844b`: `This is OK, as writes of an unbound Render Target View are discarded. `
- `0x180177e72`: `) with component(s) of signed or unsigned integer type. This happens to be well defined:`
- `0x1801780e7`: `) with component(s) of some other type. This happens to be well defined:`
- `0x18017835b`: `) with component(s) of some other type. This happens to be well defined:`
- `0x180177f73`: ` components, while the corresponding RenderTarget slot [`
- `0x180177fcf`: ` component(s). This results in undefined contents in the unwritten channels of the render target.`
- `0x180178222`: `This is OK, as reads of an unbound Depth Stencil View are defined to return 0; and writes are discarded. `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ValidateRasterizedStream(
        const struct CSignatureParser *a1,
        const struct D3D12_BLEND_DESC *a2,
        const enum DXGI_FORMAT *a3,
        const struct D3D12_DEPTH_STENCIL_DESC2 *a4,
        enum DXGI_FORMAT a5,
        int (*a6)(enum D3D12_FEATURE, void *, unsigned int, void *),
        void *a7,
        void *a8,
        void (*a9)(void *, enum D3D12_MESSAGE_ID, const char *),
        void (*a10)(void *, enum D3D12_MESSAGE_ID, const char *))
{
  const struct CSignatureParser *v11; // r12
  void *v12; // rsi
  void (*v13)(void *, enum D3D12_MESSAGE_ID, const char *); // rdi
  unsigned int v14; // r15d
  char v15; // r13
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rsi
  __int64 v19; // rdi
  unsigned int v20; // r15d
  enum DXGI_FORMAT v21; // r9d
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  _QWORD *v25; // r8
  __int64 v26; // rcx
  char v27; // r13
  __int64 v28; // rax
  char v29; // r8
  bool v30; // al
  __int64 v31; // rax
  __int64 v32; // rax
  void (*v33)(void *, enum D3D12_MESSAGE_ID, const char *); // r15
  _QWORD *v34; // r8
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  bool v38; // dl
  const char *Name; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  _QWORD *v44; // r8
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  _QWORD *v55; // r8
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  bool v59; // dl
  const char *v60; // rax
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  _QWORD *v65; // r8
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  _QWORD *v75; // r8
  char v76; // r14
  __int64 v77; // r15
  unsigned int v78; // r12d
  __int64 v79; // rax
  __int64 v80; // r13
  __int64 v81; // r14
  unsigned int v82; // edi
  enum DXGI_FORMAT v83; // r12d
  unsigned int NumComponentsInFormat; // eax
  __int64 v85; // r8
  unsigned int v86; // r15d
  unsigned __int8 i; // dl
  unsigned int v88; // ecx
  __int64 v89; // rsi
  __int64 v90; // rdi
  unsigned int j; // r14d
  int ComponentName; // eax
  D3D12_BLEND SrcBlend; // eax
  int v94; // ecx
  bool v95; // r9
  bool v96; // r8
  int v97; // r10d
  D3D12_BLEND SrcBlendAlpha; // eax
  int v99; // ecx
  bool v100; // zf
  unsigned int v101; // edi
  unsigned int v102; // eax
  int FormatComponentInterpretation; // eax
  int v104; // ecx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  bool v111; // dl
  const char *v112; // rax
  __int64 v113; // r8
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  _QWORD *v117; // r8
  __int64 v118; // rax
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 v125; // rax
  bool v126; // dl
  const char *v127; // rax
  __int64 v128; // r8
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  _QWORD *v132; // r8
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rax
  __int64 v138; // rax
  bool v139; // dl
  const char *v140; // rax
  __int64 v141; // r8
  __int64 v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
  _QWORD *v145; // r8
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  _QWORD *v151; // r8
  __int64 v153; // rax
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  __int64 v158; // rax
  bool v159; // dl
  const char *v160; // rax
  __int64 v161; // r8
  __int64 v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  _QWORD *v165; // r8
  __int64 v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rax
  _QWORD *v173; // r8
  char v174; // [rsp+30h] [rbp-D0h]
  char v175; // [rsp+30h] [rbp-D0h]
  char v176; // [rsp+31h] [rbp-CFh]
  unsigned int v177; // [rsp+34h] [rbp-CCh]
  unsigned int v178; // [rsp+38h] [rbp-C8h]
  int v179; // [rsp+38h] [rbp-C8h]
  enum DXGI_FORMAT v180; // [rsp+3Ch] [rbp-C4h]
  enum DXGI_FORMAT v181; // [rsp+3Ch] [rbp-C4h]
  unsigned int v182; // [rsp+40h] [rbp-C0h]
  int v183; // [rsp+40h] [rbp-C0h]
  __int64 v184; // [rsp+58h] [rbp-A8h]
  __int64 v185; // [rsp+60h] [rbp-A0h]
  unsigned int v186; // [rsp+60h] [rbp-A0h]
  __int64 v187; // [rsp+68h] [rbp-98h]
  char v191[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v192[232]; // [rsp+98h] [rbp-68h] BYREF
  char v193[8]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v194[232]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v195[3]; // [rsp+270h] [rbp+170h] BYREF
  unsigned __int64 v196; // [rsp+288h] [rbp+188h]
  __int128 v197; // [rsp+290h] [rbp+190h] BYREF
  __int64 v198; // [rsp+2A0h] [rbp+1A0h]

  v11 = a1;
  v12 = a8;
  v13 = a10;
  v14 = 0;
  v177 = 0;
  v15 = 0;
  v176 = 0;
  v198 = 0;
  if ( a2 )
  {
    if ( a2->RenderTarget[0].SrcBlend == D3D12_BLEND_SRC1_COLOR
      || a2->RenderTarget[0].SrcBlend == D3D12_BLEND_INV_SRC1_COLOR
      || (unsigned int)(a2->RenderTarget[0].SrcBlend - 18) <= 1 )
    {
      v15 = 1;
      v176 = 1;
    }
    if ( a2->RenderTarget[0].DestBlend == D3D12_BLEND_SRC1_COLOR
      || a2->RenderTarget[0].DestBlend == D3D12_BLEND_INV_SRC1_COLOR
      || (unsigned int)(a2->RenderTarget[0].DestBlend - 18) <= 1 )
    {
      v15 = 1;
      v176 = 1;
    }
    if ( a2->RenderTarget[0].SrcBlendAlpha == D3D12_BLEND_SRC1_ALPHA
      || a2->RenderTarget[0].SrcBlendAlpha == D3D12_BLEND_INV_SRC1_ALPHA )
    {
      v15 = 1;
      v176 = 1;
    }
    if ( a2->RenderTarget[0].DestBlendAlpha == D3D12_BLEND_SRC1_ALPHA
      || a2->RenderTarget[0].DestBlendAlpha == D3D12_BLEND_INV_SRC1_ALPHA )
    {
      v15 = 1;
      v176 = 1;
    }
  }
  if ( a1 )
  {
    v16 = *(_QWORD *)a1;
    v178 = *((_DWORD *)a1 + 4);
    v182 = 0;
    if ( v178 )
    {
      v17 = 0;
      v185 = 0;
      while ( 1 )
      {
        v18 = 5 * v17;
        v19 = *(unsigned int *)(v16 + 40 * v17 + 28);
        if ( a2 && a2->IndependentBlendEnable )
          v20 = *(_DWORD *)(v16 + 40 * v17 + 28);
        else
          v20 = 0;
        if ( (unsigned int)_o__stricmp(*(_QWORD *)(v16 + 40 * v17 + 8), "SV_Depth") )
        {
          if ( (unsigned int)v19 < 8 )
          {
            if ( a3 )
            {
              v21 = a3[v19];
              v180 = v21;
              if ( v21 )
              {
                if ( v15 && (_DWORD)v19 )
                {
                  *((_BYTE *)&v198 + v19) = 1;
                  std::ostringstream::ostringstream(v191);
                  v22 = std::operator<<<std::char_traits<char>>(v191, Src);
                  v23 = std::operator<<<std::char_traits<char>>(
                          v22,
                          "Dual Source Blending (use of D3D12_BLEND_SRC1_COLOR, D3D12_BLEND_INV_SRC1_COLOR, D3D12_BLEND_S"
                          "RC1_ALPHA or D3D12_BLEND_INV_SRC1_ALPHA in the Blend Desc)");
                  v24 = std::operator<<<std::char_traits<char>>(
                          v23,
                          " means only a single RenderTarget may be bound and must be a slot 0. The PSO description indic"
                          "ates that there will be a RenderTarget bound to slot ");
                  std::ostream::operator<<(v24, (unsigned int)v19);
                  if ( a9 )
                  {
                    std::stringbuf::str(v192, v195);
                    v25 = v195;
                    if ( v196 > 0xF )
                      v25 = (_QWORD *)v195[0];
                    ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 675, v25);
                    std::string::_Tidy_deallocate(v195);
                  }
                  std::ostringstream::`vbase destructor'(v191);
                  ++v177;
                }
                else if ( a6 )
                {
                  if ( a2
                    && (v26 = v20, a2->RenderTarget[v20].BlendEnable)
                    && a2->RenderTarget[v20].RenderTargetWriteMask )
                  {
                    v27 = 1;
LABEL_40:
                    v28 = v26;
                    if ( a2->RenderTarget[v26].LogicOpEnable && a2->RenderTarget[v28].RenderTargetWriteMask )
                    {
                      v29 = 1;
                      goto LABEL_44;
                    }
                  }
                  else
                  {
                    v27 = 0;
                    v26 = v20;
                    if ( a2 )
                      goto LABEL_40;
                  }
                  v29 = 0;
                  v28 = v26;
LABEL_44:
                  v174 = v29;
                  v30 = v27 || v29 || a2 && !a2->RenderTarget[v28].RenderTargetWriteMask;
                  *((_BYTE *)&v198 + v19) = v30;
                  *(_QWORD *)((char *)&v197 + 4) = 0;
                  LODWORD(v197) = v21;
                  if ( ((int (__fastcall *)(__int64, __int128 *, __int64, void *))a6)(3, &v197, 12, a7) >= 0 )
                  {
                    v33 = a9;
                  }
                  else
                  {
                    std::ostringstream::ostringstream(v191);
                    v31 = std::operator<<<std::char_traits<char>>(v191, Src);
                    v32 = std::operator<<<std::char_traits<char>>(v31, "Failed to determine format support for format ");
                    std::ostream::operator<<(v32, (unsigned int)v180);
                    v33 = a9;
                    if ( a9 )
                    {
                      std::stringbuf::str(v192, v195);
                      v34 = v195;
                      if ( v196 > 0xF )
                        v34 = (_QWORD *)v195[0];
                      ((void (__fastcall *)(void *, __int64, _QWORD *))a9)(a8, 676, v34);
                      std::string::_Tidy_deallocate(v195);
                    }
                    std::ostringstream::`vbase destructor'(v191);
                    ++v177;
                  }
                  if ( v27 )
                  {
                    if ( (WORD2(v197) & 0x8000) == 0 )
                    {
                      std::ostringstream::ostringstream(v191);
                      v35 = std::operator<<<std::char_traits<char>>(v191, Src);
                      v36 = std::operator<<<std::char_traits<char>>(v35, "The render target format at slot ");
                      v37 = std::ostream::operator<<(v36, (unsigned int)v19);
                      std::operator<<<std::char_traits<char>>(v37, " is format (");
                      Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v180, v38);
                      v41 = std::operator<<<std::char_traits<char>>(v40, Name);
                      v42 = std::operator<<<std::char_traits<char>>(v41, ").  This format does not support blending. ");
                      v43 = std::operator<<<std::char_traits<char>>(
                              v42,
                              "The Pixel Shader output signature indicates this output could be written, ");
                      std::operator<<<std::char_traits<char>>(
                        v43,
                        "and the Blend State indicates blending is enabled for this slot.");
                      if ( v33 )
                      {
                        std::stringbuf::str(v192, v195);
                        v44 = v195;
                        if ( v196 > 0xF )
                          v44 = (_QWORD *)v195[0];
                        ((void (__fastcall *)(void *, __int64, _QWORD *))v33)(a8, 676, v44);
                        std::string::_Tidy_deallocate(v195);
                      }
                      std::ostringstream::`vbase destructor'(v191);
                      ++v177;
                    }
                    v45 = *(_DWORD *)(v16 + 8 * v18 + 24);
                    if ( v45 && v45 != 3 )
                    {
                      std::ostringstream::ostringstream(v191);
                      v46 = std::operator<<<std::char_traits<char>>(v191, Src);
                      v47 = std::operator<<<std::char_traits<char>>(v46, "Pixel Shader output '");
                      v48 = std::operator<<<std::char_traits<char>>(v47, *(_QWORD *)(v16 + 8 * v18 + 8));
                      v49 = std::ostream::operator<<(v48, *(unsigned int *)(v16 + 8 * v18 + 16));
                      v50 = std::operator<<<std::char_traits<char>>(
                              v49,
                              "' has type that is NOT float, while the corresponding Output Merger RenderTarget slot [");
                      v51 = std::ostream::operator<<(v50, (unsigned int)v19);
                      v52 = std::operator<<<std::char_traits<char>>(v51, "] has ");
                      v53 = std::operator<<<std::char_traits<char>>(
                              v52,
                              "blending enabled. This happens to be well defined: the raw bits output from the shader ");
                      v54 = std::operator<<<std::char_traits<char>>(
                              v53,
                              "will simply be interpreted as float bits in the blender without any data conversion. This warning ");
                      std::operator<<<std::char_traits<char>>(
                        v54,
                        "is to check that the application developer really intended to rely on this behavior.");
                      if ( a10 )
                      {
                        std::stringbuf::str(v192, v195);
                        v55 = v195;
                        if ( v196 > 0xF )
                          v55 = (_QWORD *)v195[0];
                        ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 677, v55);
                        std::string::_Tidy_deallocate(v195);
                      }
                      std::ostringstream::`vbase destructor'(v191);
                    }
                  }
                  if ( v174 )
                  {
                    if ( (WORD4(v197) & 0x100) == 0 )
                    {
                      std::ostringstream::ostringstream(v191);
                      v56 = std::operator<<<std::char_traits<char>>(v191, Src);
                      v57 = std::operator<<<std::char_traits<char>>(v56, "The render target format at slot ");
                      v58 = std::ostream::operator<<(v57, (unsigned int)v19);
                      std::operator<<<std::char_traits<char>>(v58, " is format (");
                      v60 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v180, v59);
                      v62 = std::operator<<<std::char_traits<char>>(v61, v60);
                      v63 = std::operator<<<std::char_traits<char>>(v62, ").  This format does not support logic ops. ");
                      v64 = std::operator<<<std::char_traits<char>>(
                              v63,
                              "The Pixel Shader output signature indicates this output could be written, ");
                      std::operator<<<std::char_traits<char>>(
                        v64,
                        "and the Blend State indicates logic op is enabled for this slot.");
                      if ( v33 )
                      {
                        std::stringbuf::str(v192, v195);
                        v65 = v195;
                        if ( v196 > 0xF )
                          v65 = (_QWORD *)v195[0];
                        ((void (__fastcall *)(void *, __int64, _QWORD *))v33)(a8, 678, v65);
                        std::string::_Tidy_deallocate(v195);
                      }
                      std::ostringstream::`vbase destructor'(v191);
                      ++v177;
                    }
                    if ( *(_DWORD *)(v16 + 8 * v18 + 24) >= 2u )
                    {
                      std::ostringstream::ostringstream(v191);
                      v66 = std::operator<<<std::char_traits<char>>(v191, Src);
                      v67 = std::operator<<<std::char_traits<char>>(v66, "Pixel Shader output '");
                      v68 = std::operator<<<std::char_traits<char>>(v67, *(_QWORD *)(v16 + 8 * v18 + 8));
                      v69 = std::ostream::operator<<(v68, *(unsigned int *)(v16 + 8 * v18 + 16));
                      v70 = std::operator<<<std::char_traits<char>>(
                              v69,
                              "' has type that is NOT unsigned int, while the corresponding Output Merger RenderTarget slot [");
                      v71 = std::ostream::operator<<(v70, (unsigned int)v19);
                      v72 = std::operator<<<std::char_traits<char>>(v71, "] has ");
                      v73 = std::operator<<<std::char_traits<char>>(
                              v72,
                              "logic op enabled. This happens to be well defined: the raw bits output from the shader ");
                      v74 = std::operator<<<std::char_traits<char>>(
                              v73,
                              "will simply be interpreted as UINT bits in the blender without any data conversion. This warning ");
                      std::operator<<<std::char_traits<char>>(
                        v74,
                        "is to check that the application developer really intended to rely on this behavior.");
                      if ( a10 )
                      {
                        std::stringbuf::str(v192, v195);
                        v75 = v195;
                        if ( v196 > 0xF )
                          v75 = (_QWORD *)v195[0];
                        ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 677, v75);
                        std::string::_Tidy_deallocate(v195);
                      }
                      std::ostringstream::`vbase destructor'(v191);
                    }
                  }
                }
              }
            }
          }
        }
        ++v182;
        v17 = ++v185;
        v15 = v176;
        if ( v182 >= v178 )
        {
          v76 = 0;
          v175 = 0;
          v11 = a1;
          v13 = a10;
          v12 = a8;
          goto LABEL_87;
        }
      }
    }
  }
  v76 = 0;
  v175 = 0;
  if ( a1 )
  {
LABEL_87:
    v77 = *(_QWORD *)v11;
    v184 = *(_QWORD *)v11;
    v186 = *((_DWORD *)v11 + 4);
    v78 = 0;
    v179 = 0;
    if ( !v186 )
      goto LABEL_175;
    v79 = 0;
    v187 = 0;
    while ( 1 )
    {
      v80 = 5 * v79;
      if ( !(unsigned int)_o__stricmp(*(_QWORD *)(v77 + 40 * v79 + 8), "SV_Depth") )
      {
        v76 = 1;
        v175 = 1;
        goto LABEL_174;
      }
      v81 = *(unsigned int *)(v77 + 8 * v80 + 28);
      v183 = *(_DWORD *)(v77 + 8 * v80 + 28);
      if ( a2 && a2->IndependentBlendEnable )
        v82 = *(_DWORD *)(v77 + 8 * v80 + 28);
      else
        v82 = 0;
      if ( (unsigned int)v81 >= 8 )
        goto LABEL_172;
      if ( !a3 )
        goto LABEL_193;
      v83 = a3[v81];
      if ( v83 == DXGI_FORMAT_UNKNOWN )
      {
        v78 = v179;
LABEL_193:
        if ( !v176 )
        {
          std::ostringstream::ostringstream(v193);
          v166 = std::operator<<<std::char_traits<char>>(v193, Src);
          v167 = std::operator<<<std::char_traits<char>>(
                   v166,
                   "The Pixel Shader expects a Render Target View bound to slot ");
          v168 = std::ostream::operator<<(v167, (unsigned int)v81);
          v169 = std::operator<<<std::char_traits<char>>(v168, ", but the graphics pipeline state ");
          v170 = std::operator<<<std::char_traits<char>>(v169, "indicates that none will be bound. ");
          v171 = std::operator<<<std::char_traits<char>>(
                   v170,
                   "This is OK, as writes of an unbound Render Target View are discarded. ");
          v172 = std::operator<<<std::char_traits<char>>(
                   v171,
                   "It is also possible the developer knows the data will not be used anyway. ");
          std::operator<<<std::char_traits<char>>(
            v172,
            "This is only a problem if the developer actually intended to bind a Render Target View here.");
          v13 = a10;
          if ( a10 )
          {
            std::stringbuf::str(v194, v195);
            v173 = v195;
            if ( v196 > 0xF )
              v173 = (_QWORD *)v195[0];
            ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(v12, 679, v173);
            std::string::_Tidy_deallocate(v195);
          }
          std::ostringstream::`vbase destructor'(v193);
          goto LABEL_173;
        }
LABEL_172:
        v13 = a10;
        goto LABEL_173;
      }
      NumComponentsInFormat = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetNumComponentsInFormat(v83);
      v181 = NumComponentsInFormat;
      v86 = 0;
      for ( i = *(_BYTE *)(v184 + 8 * v80 + 32); i; i >>= 1 )
      {
        v88 = v86 + 1;
        if ( (i & 1) == 0 )
          v88 = v86;
        v86 = v88;
      }
      if ( NumComponentsInFormat <= v86 )
        goto LABEL_143;
      if ( !a2 )
        goto LABEL_155;
      v89 = v82;
      if ( !a2->RenderTarget[v82].BlendEnable )
        goto LABEL_155;
      v197 = 0;
      v90 = 0;
      for ( j = 0; j < 4; ++j )
      {
        ComponentName = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetComponentName((unsigned int)v83, j, v85);
        switch ( ComponentName )
        {
          case -4:
            *((_DWORD *)&v197 + v90) = 1;
            break;
          case -3:
            *((_DWORD *)&v197 + v90) = 2;
            break;
          case -2:
            *((_DWORD *)&v197 + v90) = 3;
            break;
          case -1:
            *((_DWORD *)&v197 + v90) = 4;
            break;
          default:
            continue;
        }
        v90 = (unsigned int)(v90 + 1);
      }
      SrcBlend = a2->RenderTarget[v89].SrcBlend;
      v95 = 0;
      if ( (unsigned int)SrcBlend <= (D3D12_BLEND_INV_SRC1_COLOR|D3D12_BLEND_INV_SRC_COLOR) )
      {
        v94 = 3194882;
        if ( _bittest(&v94, SrcBlend) )
          v95 = 1;
      }
      NumComponentsInFormat = v181;
      if ( v181 == v86 )
      {
        LODWORD(v81) = v183;
        goto LABEL_143;
      }
      v96 = 0;
      v97 = 0;
      while ( 2 )
      {
        if ( !v96 )
        {
          if ( *((_DWORD *)&v197 + (unsigned int)(v90 - v97 - 1)) == 1 )
          {
            if ( (a2->RenderTarget[v89].RenderTargetWriteMask & 1) != 0 )
              v96 = !v95;
            goto LABEL_140;
          }
          if ( *((_DWORD *)&v197 + (unsigned int)(v90 - v97 - 1)) == 2 )
          {
            v100 = (a2->RenderTarget[v89].RenderTargetWriteMask & 2) == 0;
          }
          else
          {
            if ( *((_DWORD *)&v197 + (unsigned int)(v90 - v97 - 1)) != 3 )
            {
              if ( *((_DWORD *)&v197 + (unsigned int)(v90 - v97 - 1)) == 4 )
              {
                if ( (unsigned int)(a2->RenderTarget[v89].SrcBlend - 5) <= 1 )
                  goto LABEL_132;
                if ( (a2->RenderTarget[v89].RenderTargetWriteMask & 8) != 0 )
                {
                  SrcBlendAlpha = a2->RenderTarget[v89].SrcBlendAlpha;
                  if ( (unsigned int)SrcBlendAlpha > (D3D12_BLEND_INV_SRC1_COLOR|D3D12_BLEND_INV_SRC_COLOR) )
                    goto LABEL_132;
                  v99 = 3194882;
                  if ( !_bittest(&v99, SrcBlendAlpha) )
                    goto LABEL_132;
                }
              }
              goto LABEL_140;
            }
            v100 = (a2->RenderTarget[v89].RenderTargetWriteMask & 4) == 0;
          }
          if ( !v100 && !v95 )
LABEL_132:
            v96 = 1;
LABEL_140:
          if ( ++v97 >= v181 - v86 )
          {
            LODWORD(v81) = v183;
            if ( !v96 )
              goto LABEL_142;
            goto LABEL_155;
          }
          continue;
        }
        break;
      }
      LODWORD(v81) = v183;
LABEL_155:
      std::ostringstream::ostringstream(v191);
      v118 = std::operator<<<std::char_traits<char>>(v191, Src);
      v119 = std::operator<<<std::char_traits<char>>(v118, "Pixel Shader output '");
      v120 = std::operator<<<std::char_traits<char>>(v119, *(_QWORD *)(v184 + 8 * v80 + 8));
      v121 = std::ostream::operator<<(v120, *(unsigned int *)(v184 + 8 * v80 + 16));
      v122 = std::operator<<<std::char_traits<char>>(v121, "' is writing to ");
      v123 = std::ostream::operator<<(v122, v86);
      v124 = std::operator<<<std::char_traits<char>>(v123, " components, while the corresponding RenderTarget slot [");
      v125 = std::ostream::operator<<(v124, (unsigned int)v81);
      std::operator<<<std::char_traits<char>>(v125, "] has format (");
      v127 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v83, v126);
      v129 = std::operator<<<std::char_traits<char>>(v128, v127);
      v130 = std::operator<<<std::char_traits<char>>(v129, ") with ");
      v131 = std::ostream::operator<<(v130, (unsigned int)v181);
      std::operator<<<std::char_traits<char>>(
        v131,
        " component(s). This results in undefined contents in the unwritten channels of the render target.");
      if ( a10 )
      {
        std::stringbuf::str(v192, v195);
        v132 = v195;
        if ( v196 > 0xF )
          v132 = (_QWORD *)v195[0];
        ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 974, v132);
        std::string::_Tidy_deallocate(v195);
      }
      std::ostringstream::`vbase destructor'(v191);
LABEL_142:
      NumComponentsInFormat = v181;
LABEL_143:
      v77 = v184;
      if ( *((_BYTE *)&v198 + (unsigned int)v81) || (v101 = 0, !NumComponentsInFormat) )
      {
LABEL_171:
        v78 = v179;
        goto LABEL_172;
      }
      while ( 2 )
      {
        v102 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::Sequential2AbsoluteComponentIndex(v83, v101);
        FormatComponentInterpretation = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetFormatComponentInterpretation(
                                          (unsigned int)v83,
                                          v102);
        v104 = *(_DWORD *)(v184 + 8 * v80 + 24);
        if ( v104 == 3 )
        {
          if ( (unsigned int)(FormatComponentInterpretation + 3) > 1
            && FormatComponentInterpretation != 2
            && FormatComponentInterpretation != -4 )
          {
            std::ostringstream::ostringstream(v193);
            v105 = std::operator<<<std::char_traits<char>>(v193, Src);
            v106 = std::operator<<<std::char_traits<char>>(v105, "Pixel Shader output '");
            v107 = std::operator<<<std::char_traits<char>>(v106, *(_QWORD *)(v184 + 8 * v80 + 8));
            v108 = std::ostream::operator<<(v107, *(unsigned int *)(v184 + 8 * v80 + 16));
            v109 = std::operator<<<std::char_traits<char>>(
                     v108,
                     "' has float type, while the corresponding RenderTarget slot [");
            v110 = std::ostream::operator<<(v109, (unsigned int)v81);
            std::operator<<<std::char_traits<char>>(v110, "] has format (");
            v112 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v83, v111);
            v114 = std::operator<<<std::char_traits<char>>(v113, v112);
            v115 = std::operator<<<std::char_traits<char>>(
                     v114,
                     ") with component(s) of signed or unsigned integer type. This happens to be well defined:");
            v116 = std::operator<<<std::char_traits<char>>(
                     v115,
                     " the raw bits output from the shader starting from the least significant bit will simply be dumped "
                     "to the output storage without any data conversion. ");
            std::operator<<<std::char_traits<char>>(
              v116,
              "This warning is to check that the application developer really intended to rely on this behavior.");
            v13 = a10;
            if ( a10 )
            {
              std::stringbuf::str(v194, v195);
              v117 = v195;
              if ( v196 > 0xF )
                v117 = (_QWORD *)v195[0];
              ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 677, v117);
              std::string::_Tidy_deallocate(v195);
            }
            goto LABEL_153;
          }
          goto LABEL_170;
        }
        if ( v104 == 1 )
        {
          if ( FormatComponentInterpretation != 1 )
          {
            std::ostringstream::ostringstream(v193);
            v133 = std::operator<<<std::char_traits<char>>(v193, Src);
            v134 = std::operator<<<std::char_traits<char>>(v133, "Pixel Shader output '");
            v135 = std::operator<<<std::char_traits<char>>(v134, *(_QWORD *)(v184 + 8 * v80 + 8));
            v136 = std::ostream::operator<<(v135, *(unsigned int *)(v184 + 8 * v80 + 16));
            v137 = std::operator<<<std::char_traits<char>>(
                     v136,
                     "' has unsigned integer type, while the corresponding RenderTarget slot [");
            v138 = std::ostream::operator<<(v137, (unsigned int)v81);
            std::operator<<<std::char_traits<char>>(v138, "] has format (");
            v140 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v83, v139);
            v142 = std::operator<<<std::char_traits<char>>(v141, v140);
            v143 = std::operator<<<std::char_traits<char>>(
                     v142,
                     ") with component(s) of some other type. This happens to be well defined:");
            v144 = std::operator<<<std::char_traits<char>>(
                     v143,
                     " the raw bits output from the shader starting from the least significant bit will simply be dumped "
                     "to the output storage without any data conversion. ");
            std::operator<<<std::char_traits<char>>(
              v144,
              "This warning is to check that the application developer really intended to rely on this behavior.");
            v13 = a10;
            if ( a10 )
            {
              std::stringbuf::str(v194, v195);
              v145 = v195;
              if ( v196 > 0xF )
                v145 = (_QWORD *)v195[0];
              ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 677, v145);
              std::string::_Tidy_deallocate(v195);
            }
            goto LABEL_153;
          }
          goto LABEL_170;
        }
        if ( v104 != 2 || FormatComponentInterpretation == -1 )
        {
LABEL_170:
          if ( ++v101 >= v181 )
            goto LABEL_171;
          continue;
        }
        break;
      }
      std::ostringstream::ostringstream(v193);
      v153 = std::operator<<<std::char_traits<char>>(v193, Src);
      v154 = std::operator<<<std::char_traits<char>>(v153, "Pixel Shader output '");
      v155 = std::operator<<<std::char_traits<char>>(v154, *(_QWORD *)(v184 + 8 * v80 + 8));
      v156 = std::ostream::operator<<(v155, *(unsigned int *)(v184 + 8 * v80 + 16));
      v157 = std::operator<<<std::char_traits<char>>(
               v156,
               "' has signed integer type, while the corresponding RenderTarget slot [");
      v158 = std::ostream::operator<<(v157, (unsigned int)v81);
      std::operator<<<std::char_traits<char>>(v158, "] has format (");
      v160 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v83, v159);
      v162 = std::operator<<<std::char_traits<char>>(v161, v160);
      v163 = std::operator<<<std::char_traits<char>>(
               v162,
               ") with component(s) of some other type. This happens to be well defined:");
      v164 = std::operator<<<std::char_traits<char>>(
               v163,
               " the raw bits output from the shader starting from the least significant bit will simply be dumped to the"
               " output storage without any data conversion. ");
      std::operator<<<std::char_traits<char>>(
        v164,
        "This warning is to check that the application developer really intended to rely on this behavior.");
      v13 = a10;
      if ( a10 )
      {
        std::stringbuf::str(v194, v195);
        v165 = v195;
        if ( v196 > 0xF )
          v165 = (_QWORD *)v195[0];
        ((void (__fastcall *)(void *, __int64, _QWORD *))a10)(a8, 677, v165);
        std::string::_Tidy_deallocate(v195);
      }
LABEL_153:
      std::ostringstream::`vbase destructor'(v193);
      v78 = v179;
LABEL_173:
      v76 = v175;
LABEL_174:
      v179 = ++v78;
      v79 = ++v187;
      if ( v78 >= v186 )
      {
LABEL_175:
        v14 = v177;
        break;
      }
      v12 = a8;
    }
  }
  if ( (a4 && (*(_DWORD *)a4 || *((_DWORD *)a4 + 3)) || v76) && a5 == DXGI_FORMAT_UNKNOWN )
  {
    std::ostringstream::ostringstream(v193);
    v146 = std::operator<<<std::char_traits<char>>(v193, Src);
    v147 = std::operator<<<std::char_traits<char>>(
             v146,
             "The depth stencil unit or pixel shader expects a Depth Stencil View, but the graphics pipeline state ");
    v148 = std::operator<<<std::char_traits<char>>(v147, "indicates that none will be bound. ");
    v149 = std::operator<<<std::char_traits<char>>(
             v148,
             "This is OK, as reads of an unbound Depth Stencil View are defined to return 0; and writes are discarded. ");
    v150 = std::operator<<<std::char_traits<char>>(
             v149,
             "It is also possible the developer knows the data will not be used anyway. ");
    std::operator<<<std::char_traits<char>>(
      v150,
      "This is only a problem if the developer actually intended to bind a Depth Stencil View here.");
    if ( v13 )
    {
      std::stringbuf::str(v194, v195);
      v151 = v195;
      if ( v196 > 0xF )
        v151 = (_QWORD *)v195[0];
      ((void (__fastcall *)(void *, __int64, _QWORD *))v13)(a8, 680, v151);
      std::string::_Tidy_deallocate(v195);
    }
    std::ostringstream::`vbase destructor'(v193);
  }
  return v14;
}

```

## disassembly

```asm
0x18017734c  push    rbp
0x18017734e  push    rbx
0x18017734f  push    rsi
0x180177350  push    rdi
0x180177351  push    r12
0x180177353  push    r13
0x180177355  push    r14
0x180177357  push    r15
0x180177359  lea     rbp, [rsp-1B8h]
0x180177361  sub     rsp, 2B8h
0x180177368  mov     rax, cs:__security_cookie
0x18017736f  xor     rax, rsp
0x180177372  mov     [rbp+1F0h+var_48], rax
0x180177379  mov     [rbp+1F0h+var_268], r9
0x18017737d  mov     [rsp+2F0h+var_280], r8
0x180177382  mov     rbx, rdx
0x180177385  mov     r12, rcx
0x180177388  mov     [rbp+1F0h+var_270], rcx
0x18017738c  mov     r10, [rbp+1F0h+arg_28]
0x180177393  mov     [rsp+2F0h+var_288], r10
0x180177398  mov     rax, [rbp+1F0h+arg_30]
0x18017739f  mov     [rsp+2F0h+var_278], rax
0x1801773a4  mov     rsi, [rbp+1F0h+arg_38]
0x1801773ab  mov     [rsp+2F0h+var_2A8], rsi
0x1801773b0  mov     r15, [rbp+1F0h+arg_40]
0x1801773b7  mov     [rsp+2F0h+var_298], r15
0x1801773bc  mov     rdi, [rbp+1F0h+arg_48]
0x1801773c3  mov     [rsp+2F0h+var_2A0], rdi
0x1801773c8  xor     r15d, r15d
0x1801773cb  mov     [rsp+2F0h+var_2BC], r15d
0x1801773d0  xor     r13b, r13b
0x1801773d3  mov     [rsp+2F0h+var_2BF], r13b
0x1801773d8  mov     [rbp+1F0h+var_50], r15
0x1801773df  lea     r14d, [r15+1]
0x1801773e3  test    rdx, rdx
0x1801773e6  jz      short loc_180177450
0x1801773e8  mov     ecx, [rdx+10h]
0x1801773eb  sub     ecx, 10h
0x1801773ee  jz      short loc_1801773FF
0x1801773f0  sub     ecx, r14d
0x1801773f3  jz      short loc_1801773FF
0x1801773f5  sub     ecx, r14d
0x1801773f8  jz      short loc_1801773FF
0x1801773fa  cmp     ecx, r14d
0x1801773fd  jnz     short loc_180177407
0x1801773ff  mov     r13b, r14b
0x180177402  mov     [rsp+2F0h+var_2BF], r14b
0x180177407  mov     ecx, [rdx+14h]
0x18017740a  sub     ecx, 10h
0x18017740d  jz      short loc_18017741E
0x18017740f  sub     ecx, r14d
0x180177412  jz      short loc_18017741E
0x180177414  sub     ecx, r14d
0x180177417  jz      short loc_18017741E
0x180177419  cmp     ecx, r14d
0x18017741c  jnz     short loc_180177426
0x18017741e  mov     r13b, r14b
0x180177421  mov     [rsp+2F0h+var_2BF], r14b
0x180177426  mov     ecx, [rdx+1Ch]
0x180177429  sub     ecx, 12h
0x18017742c  jz      short loc_180177433
0x18017742e  cmp     ecx, r14d
0x180177431  jnz     short loc_18017743B
0x180177433  mov     r13b, r14b
0x180177436  mov     [rsp+2F0h+var_2BF], r14b
0x18017743b  mov     ecx, [rdx+20h]
0x18017743e  sub     ecx, 12h
0x180177441  jz      short loc_180177448
0x180177443  cmp     ecx, r14d
0x180177446  jnz     short loc_180177450
0x180177448  mov     r13b, r14b
0x18017744b  mov     [rsp+2F0h+var_2BF], r14b
0x180177450  test    r12, r12
0x180177453  jz      loc_180177B42
0x180177459  mov     r14, [r12]
0x18017745d  mov     eax, [r12+10h]
0x180177462  mov     [rsp+2F0h+var_2B8], eax
0x180177466  mov     [rsp+2F0h+var_2B0], r15d
0x18017746b  test    eax, eax
0x18017746d  jz      loc_180177B42
0x180177473  xor     eax, eax
0x180177475  mov     [rsp+2F0h+var_290], rax
0x18017747a  mov     r12, rdi
0x18017747d  lea     rsi, [rax+rax*4]
0x180177481  mov     edi, [r14+rsi*8+1Ch]
0x180177486  test    rbx, rbx
0x180177489  jz      short loc_180177496
0x18017748b  cmp     dword ptr [rbx+4], 0
0x18017748f  jz      short loc_180177496
0x180177491  mov     r15d, edi
0x180177494  jmp     short loc_180177499
0x180177496  xor     r15d, r15d
0x180177499  lea     rdx, aSvDepth; "SV_Depth"
0x1801774a0  mov     rcx, [r14+rsi*8+8]
0x1801774a5  call    cs:__imp__o__stricmp
0x1801774ab  test    eax, eax
0x1801774ad  jz      loc_180177AFD
0x1801774b3  cmp     edi, 8
0x1801774b6  jnb     loc_180177AFD
0x1801774bc  mov     r8, [rsp+2F0h+var_280]
0x1801774c1  test    r8, r8
0x1801774c4  jz      loc_180177AFD
0x1801774ca  mov     r9d, [r8+rdi*4]
0x1801774ce  mov     [rsp+2F0h+var_2B4], r9d
0x1801774d3  test    r9d, r9d
0x1801774d6  jz      loc_180177AFD
0x1801774dc  test    r13b, r13b
0x1801774df  jz      loc_1801775A1
0x1801774e5  test    edi, edi
0x1801774e7  jz      loc_1801775A1
0x1801774ed  mov     esi, 1
0x1801774f2  mov     byte ptr [rbp+rdi+1F0h+var_50], sil
0x1801774fa  lea     rcx, [rbp+1F0h+var_260]
0x1801774fe  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180177503  nop
0x180177504  lea     rdx, Src
0x18017750b  lea     rcx, [rbp+1F0h+var_260]
0x18017750f  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177514  mov     rcx, rax
0x180177517  lea     rdx, aDualSourceBlen; "Dual Source Blending (use of D3D12_BLEN"...
0x18017751e  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177523  mov     rcx, rax
0x180177526  lea     rdx, aMeansOnlyASing; " means only a single RenderTarget may b"...
0x18017752d  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177532  mov     edx, edi
0x180177534  mov     rcx, rax
0x180177537  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x18017753d  mov     r15, [rsp+2F0h+var_298]
0x180177542  test    r15, r15
0x180177545  jz      short loc_18017758F
0x180177547  lea     rdx, [rbp+1F0h+var_80]
0x18017754e  lea     rcx, [rbp+1F0h+var_258]
0x180177552  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180177557  nop
0x180177558  lea     r8, [rbp+1F0h+var_80]
0x18017755f  cmp     [rbp+1F0h+var_68], 0Fh
0x180177567  cmova   r8, [rbp+1F0h+var_80]
0x18017756f  mov     edx, 2A3h
0x180177574  mov     rcx, [rsp+2F0h+var_2A8]
0x180177579  mov     rax, r15
0x18017757c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177581  nop
0x180177582  lea     rcx, [rbp+1F0h+var_80]
0x180177589  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18017758e  nop
0x18017758f  lea     rcx, [rbp+1F0h+var_260]
0x180177593  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180177598  add     [rsp+2F0h+var_2BC], esi
0x18017759c  jmp     loc_180177AFD
0x1801775a1  mov     r10, [rsp+2F0h+var_288]
0x1801775a6  test    r10, r10
0x1801775a9  jz      loc_180177AFD
0x1801775af  test    rbx, rbx
0x1801775b2  jz      short loc_1801775CE
0x1801775b4  mov     ecx, r15d
0x1801775b7  lea     rax, [rcx+rcx*4]
0x1801775bb  cmp     dword ptr [rbx+rax*8+8], 0
0x1801775c0  jz      short loc_1801775CE
0x1801775c2  cmp     byte ptr [rbx+rax*8+2Ch], 0
0x1801775c7  jz      short loc_1801775CE
0x1801775c9  mov     r13b, 1
0x1801775cc  jmp     short loc_1801775D9
0x1801775ce  xor     r13b, r13b
0x1801775d1  mov     ecx, r15d
0x1801775d4  test    rbx, rbx
0x1801775d7  jz      short loc_1801775F4
0x1801775d9  lea     rax, [rcx+rcx*4]
0x1801775dd  shl     rax, 3
0x1801775e1  cmp     dword ptr [rax+rbx+0Ch], 0
0x1801775e6  jz      short loc_1801775F4
0x1801775e8  cmp     byte ptr [rax+rbx+2Ch], 0
0x1801775ed  jz      short loc_1801775F4
0x1801775ef  mov     r8b, 1
0x1801775f2  jmp     short loc_1801775FF
0x1801775f4  xor     r8b, r8b
0x1801775f7  lea     rax, [rcx+rcx*4]
0x1801775fb  shl     rax, 3
0x1801775ff  mov     [rsp+2F0h+var_2C0], r8b
0x180177604  test    r13b, r13b
0x180177607  jnz     short loc_18017761E
0x180177609  test    r8b, r8b
0x18017760c  jnz     short loc_18017761E
0x18017760e  test    rbx, rbx
0x180177611  jz      short loc_18017761A
0x180177613  cmp     [rax+rbx+2Ch], r13b
0x180177618  jz      short loc_18017761E
0x18017761a  xor     al, al
0x18017761c  jmp     short loc_180177620
0x18017761e  mov     al, 1
0x180177620  mov     byte ptr [rbp+rdi+1F0h+var_50], al
0x180177627  mov     qword ptr [rbp+1F0h+var_60+4], 0
0x180177632  mov     dword ptr [rbp+1F0h+var_60], r9d
0x180177639  mov     r9, [rsp+2F0h+var_278]
0x18017763e  mov     r8d, 0Ch
0x180177644  lea     rdx, [rbp+1F0h+var_60]
0x18017764b  lea     ecx, [r8-9]
0x18017764f  mov     rax, r10
0x180177652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180177657  test    eax, eax
0x180177659  jns     loc_1801776F6
0x18017765f  lea     rcx, [rbp+1F0h+var_260]
0x180177663  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180177668  nop
0x180177669  lea     rdx, Src
0x180177670  lea     rcx, [rbp+1F0h+var_260]
0x180177674  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177679  mov     rcx, rax
0x18017767c  lea     rdx, aFailedToDeterm_0; "Failed to determine format support for "...
0x180177683  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177688  mov     edx, [rsp+2F0h+var_2B4]
0x18017768c  mov     rcx, rax
0x18017768f  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@H@Z; std::ostream::operator<<(int)
0x180177695  mov     r15, [rsp+2F0h+var_298]
0x18017769a  test    r15, r15
0x18017769d  jz      short loc_1801776E7
0x18017769f  lea     rdx, [rbp+1F0h+var_80]
0x1801776a6  lea     rcx, [rbp+1F0h+var_258]
0x1801776aa  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1801776af  nop
0x1801776b0  lea     r8, [rbp+1F0h+var_80]
0x1801776b7  cmp     [rbp+1F0h+var_68], 0Fh
0x1801776bf  cmova   r8, [rbp+1F0h+var_80]
0x1801776c7  mov     edx, 2A4h
0x1801776cc  mov     rcx, [rsp+2F0h+var_2A8]
0x1801776d1  mov     rax, r15
0x1801776d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801776d9  nop
0x1801776da  lea     rcx, [rbp+1F0h+var_80]
0x1801776e1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801776e6  nop
0x1801776e7  lea     rcx, [rbp+1F0h+var_260]
0x1801776eb  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1801776f0  inc     [rsp+2F0h+var_2BC]
0x1801776f4  jmp     short loc_1801776FB
0x1801776f6  mov     r15, [rsp+2F0h+var_298]
0x1801776fb  test    r13b, r13b
0x1801776fe  jz      loc_1801778FB
0x180177704  test    dword ptr [rbp+1F0h+var_60+4], 8000h
0x18017770e  jnz     loc_1801777F5
0x180177714  lea     rcx, [rbp+1F0h+var_260]
0x180177718  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18017771d  nop
0x18017771e  lea     rdx, Src
0x180177725  lea     rcx, [rbp+1F0h+var_260]
0x180177729  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017772e  mov     rcx, rax
0x180177731  lea     rdx, aTheRenderTarge; "The render target format at slot "
0x180177738  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017773d  mov     edx, edi
0x18017773f  mov     rcx, rax
0x180177742  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180177748  mov     rcx, rax
0x18017774b  lea     rdx, aIsFormat; " is format ("
0x180177752  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180177757  mov     r8, rax
0x18017775a  mov     ecx, [rsp+2F0h+var_2B4]; enum DXGI_FORMAT
0x18017775e  call    ?GetName@D3D12_PROPERTY_LAYOUT_FORMAT_TABLE@@SAPEBDW4DXGI_FORMAT@@_N@Z; D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(DXGI_FORMAT,bool)
0x180177763  mov     rdx, rax
0x180177766  mov     rcx, r8
0x180177769  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017776e  mov     rcx, rax
0x180177771  lea     rdx, aThisFormatDoes_0; ").  This format does not support blendi"...
0x180177778  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017777d  mov     rcx, rax
0x180177780  lea     rdx, aThePixelShader_0; "The Pixel Shader output signature indic"...
0x180177787  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017778c  mov     rcx, rax
0x18017778f  lea     rdx, aAndTheBlendSta_0; "and the Blend State indicates blending "...
0x180177796  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18017779b  test    r15, r15
0x18017779e  jz      short loc_1801777E8
0x1801777a0  lea     rdx, [rbp+1F0h+var_80]
0x1801777a7  lea     rcx, [rbp+1F0h+var_258]
0x1801777ab  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1801777b0  nop
0x1801777b1  lea     r8, [rbp+1F0h+var_80]
0x1801777b8  cmp     [rbp+1F0h+var_68], 0Fh
0x1801777c0  cmova   r8, [rbp+1F0h+var_80]
0x1801777c8  mov     edx, 2A4h
0x1801777cd  mov     rcx, [rsp+2F0h+var_2A8]
0x1801777d2  mov     rax, r15
0x1801777d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801777da  nop
0x1801777db  lea     rcx, [rbp+1F0h+var_80]
0x1801777e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801777e7  nop
0x1801777e8  lea     rcx, [rbp+1F0h+var_260]
0x1801777ec  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1801777f1  inc     [rsp+2F0h+var_2BC]
0x1801777f5  mov     eax, [r14+rsi*8+18h]
0x1801777fa  test    eax, eax
0x1801777fc  jz      loc_1801778FB
0x180177802  cmp     eax, 3
0x180177805  jz      loc_1801778FB
0x18017780b  lea     rcx, [rbp+1F0h+var_260]
0x18017780f  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180177814  nop
0x180177815  lea     rdx, Src
0x18017781c  lea     rcx, [rbp+1F0h+var_260]
0x180177820  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
  ... truncated ...
```
