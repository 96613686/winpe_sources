# Mso::SVG::TextRenderer::MergeTextChunkAndItems(Mso::SVG::TextChunk const &,std::vector<tag_SCRIPT_ITEM,std::allocator<tag_SCRIPT_ITEM>> &,Mso::SVG::WritingMode,double &,double &,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,Mso::SVG::TextRenderingParams const &)

- ea: `0x180135284`
- end: `0x180135a75`
- name: `?MergeTextChunkAndItems@TextRenderer@SVG@Mso@@CAXAEBUTextChunk@23@AEAV?$vector@Utag_SCRIPT_ITEM@@V?$allocator@Utag_SCRIPT_ITEM@@@std@@@std@@W4WritingMode@23@AEAN3P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N_NAEBV?$vector@GV?$allocator@G@std@@@6@AEBV?$vector@MV?$allocator@M@std@@@6@AEBV?$vector@MV?$allocator@M@std@@@6@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@6@MMMMAEBV?$vector@GV?$allocator@G@std@@@6@AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z4AEBUTextRenderingParams@23@@Z`
- size: `2033`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180135a78`

## callees

- `0x180008a80`
- `0x180009320`
- `0x18000bb10`
- `0x18003a314`
- `0x18005b938`
- `0x18006127c`
- `0x180134e70`
- `0x180135284`
- `0x180136970`
- `0x1801379c4`
- `0x180138154`
- `0x180138850`
- `0x18013b97c`
- `0x18013e67c`

## import_xrefs

- `mso40uiWin32Client!__imp_MsoScriptLayout` at `0x18013569c`
- `mso40uiWin32Client!__imp_MsoScriptLayout` at `0x18013569c`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135683`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x180135683`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135652`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135674`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135652`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135674`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801352f6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135440`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135635`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135868`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135a4f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801352f6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135440`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135635`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135868`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135a4f`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x1801355ce`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x1801355ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_UNKNOWN **__fastcall Mso::SVG::TextRenderer::MergeTextChunkAndItems(
        __int64 *a1,
        __int64 *a2,
        int a3,
        double *a4,
        double *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  _UNKNOWN **result; // rax
  int v9; // r15d
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // r10
  __int64 v15; // r14
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r15
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned int v21; // r12d
  __int128 v22; // rcx
  __int64 v23; // r8
  unsigned int v24; // eax
  size_t v25; // rdi
  char *v26; // rbx
  __int64 v27; // r9
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  size_t v30; // rdi
  char *v31; // rax
  char *v32; // rbx
  __int64 v33; // r14
  void *v34; // rdi
  int v36; // eax
  void *v37; // rax
  void *v38; // rcx
  double v39; // xmm1_8
  int v40; // eax
  __int64 v41; // r12
  __int64 v42; // rcx
  __int64 v43; // r10
  double *v44; // rdx
  double v45; // xmm0_8
  double *v46; // rdi
  double *v47; // rdx
  double v48; // xmm2_8
  unsigned int v49; // ebx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // r8
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // r11
  __int64 *v55; // rdx
  __int64 v56; // rax
  __int64 v57; // rdx
  unsigned int v58; // ebx
  unsigned __int64 v59; // rcx
  __int64 v60; // r14
  __int64 v61; // r15
  int v62; // r13d
  __int64 v63; // rdx
  unsigned int v64; // eax
  unsigned __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // r11
  __int64 *v68; // rdx
  __int64 v69; // rax
  _QWORD v70[3]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v71; // [rsp+88h] [rbp-80h]
  double v72; // [rsp+90h] [rbp-78h] BYREF
  double v73; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v74; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v75; // [rsp+A8h] [rbp-60h] BYREF
  char *v76; // [rsp+B8h] [rbp-50h]
  void *v77[2]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-38h]
  __int128 v79; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v80; // [rsp+E8h] [rbp-20h]
  __int64 v81; // [rsp+F0h] [rbp-18h]
  int v82; // [rsp+F8h] [rbp-10h]
  int v83; // [rsp+FCh] [rbp-Ch]
  double v84[9]; // [rsp+100h] [rbp-8h] BYREF
  _UNKNOWN *retaddr; // [rsp+150h] [rbp+48h] BYREF
  __int64 v86; // [rsp+160h] [rbp+58h] BYREF
  int v87; // [rsp+168h] [rbp+60h]
  double *v88; // [rsp+170h] [rbp+68h]

  result = &retaddr;
  v88 = a4;
  v87 = a3;
  v9 = a3;
  v12 = a2[1];
  v13 = *a2;
  v14 = v12 - *a2;
  if ( !v14 )
    return result;
  v15 = a1[4];
  v16 = 0x84BDA12F684BDA13uLL;
  if ( !(0x84BDA12F684BDA13uLL * ((a1[5] - v15) >> 3)) )
    _invoke_watson(0, 0, 0, 0, 0);
  *(_OWORD *)&v70[1] = 0;
  v71 = 0;
  v17 = 0;
  if ( v14 >> 3 == 1 )
  {
    *((_QWORD *)&v22 + 1) = v70[2];
  }
  else
  {
    do
    {
      v18 = (unsigned int)v17;
      v19 = (v12 - v13) >> 3;
      if ( (unsigned int)v17 >= v19
        || (v16 = *(unsigned int *)(v13 + 8LL * (unsigned int)v17),
            v20 = (unsigned int)(v17 + 1),
            v17 = (unsigned int)v20,
            LODWORD(v86) = v20,
            v74 = v20,
            v20 >= v19) )
      {
        _invoke_watson(0, 0, 0, 0, 0);
      }
      v21 = *(_DWORD *)(v13 + 8 * v20);
      *(_WORD *)(v13 + 8 * v18 + 4) |= 0x4000u;
      *((_QWORD *)&v22 + 1) = v70[2];
      if ( (unsigned int)v16 < v21 )
      {
        do
        {
          v23 = v15;
          *(_QWORD *)&v79 = v15;
          DWORD2(v79) = *(_DWORD *)(v13 + 8 * v18 + 4);
          HIDWORD(v79) = v16;
          v24 = v21;
          if ( *(_DWORD *)(v15 + 132) + *(_DWORD *)(v15 + 128) < v21 )
            v24 = *(_DWORD *)(v15 + 132) + *(_DWORD *)(v15 + 128);
          v80 = v24;
          if ( *((_QWORD *)&v22 + 1) == v71 )
          {
            std::vector<Mso::SVG::TextRun>::_Emplace_reallocate<Mso::SVG::TextRun>(&v70[1], *((_QWORD *)&v22 + 1), &v79);
            *((_QWORD *)&v22 + 1) = v70[2];
            v23 = v15;
          }
          else
          {
            **((_OWORD **)&v22 + 1) = v79;
            *(_QWORD *)(*((_QWORD *)&v22 + 1) + 16LL) = v80;
            *((_QWORD *)&v22 + 1) = v70[2] + 24LL;
            v70[2] += 24LL;
          }
          v16 = (unsigned int)(*(_DWORD *)(v15 + 128) + *(_DWORD *)(v15 + 132));
          v15 = v23 + 216;
          if ( v21 < (unsigned int)v16 )
          {
            v15 = v23;
            v16 = v21;
          }
        }
        while ( (unsigned int)v16 < v21 );
        v17 = (unsigned int)v86;
      }
      v12 = a2[1];
      v13 = *a2;
    }
    while ( v74 < ((v12 - *a2) >> 3) - 1 );
    v9 = v87;
  }
  *(_QWORD *)&v22 = v70[1];
  v25 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v70[1]) >> 3);
  *(_OWORD *)v77 = 0;
  v78 = 0;
  if ( v25 )
  {
    std::vector<unsigned char>::_Buy_nonzero(
      v77,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v70[1]) >> 3),
      v17);
    v26 = (char *)v77[0];
    memset_0(v77[0], 0, v25);
    v77[1] = &v26[v25];
    v86 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v86);
    v22 = *(_OWORD *)&v70[1];
  }
  v27 = 0;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3) )
  {
    v16 = 0;
    do
    {
      LOBYTE(v17) = *(_BYTE *)(v22 + 24 * v16 + 10) & 0x1F;
      if ( v16 >= (char *)v77[1] - (char *)v77[0] )
        _invoke_watson(0, 0, 0, 0, 0);
      *((_BYTE *)v77[0] + v16) = v17;
      v27 = (unsigned int)(v27 + 1);
      v22 = *(_OWORD *)&v70[1];
      v16 = (unsigned int)v27;
    }
    while ( (unsigned int)v27 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v70[2] - v70[1]) >> 3) );
  }
  v28 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
  v75 = 0;
  v76 = 0;
  if ( v28 )
  {
    v29 = 0x3FFFFFFFFFFFFFFFLL;
    if ( v28 > 0x3FFFFFFFFFFFFFFFLL )
      goto LABEL_94;
    v30 = 4 * v28;
    if ( !(4 * v28) )
    {
      v31 = 0;
LABEL_31:
      *(_QWORD *)&v75 = v31;
      v32 = &v31[v30];
      v76 = &v31[v30];
      memset_0(v31, 0, v30);
      *((_QWORD *)&v75 + 1) = v32;
      v86 = 0;
      std::_Tidy_guard<std::vector<float>>::~_Tidy_guard<std::vector<float>>(&v86);
      v22 = *(_OWORD *)&v70[1];
      goto LABEL_32;
    }
    if ( v30 < 0x1000 )
    {
      v31 = (char *)malloc(4 * v28);
      if ( v31 )
        goto LABEL_31;
    }
    else
    {
      if ( v30 + 39 < v30 )
        std::_Throw_bad_array_new_length();
      v37 = malloc(v30 + 39);
      v38 = v37;
      if ( v37 )
      {
        v31 = (char *)(((unsigned __int64)v37 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *((_QWORD *)v31 - 1) = v38;
        goto LABEL_31;
      }
    }
    std::_Xbad_alloc();
LABEL_46:
    v36 = -2147024809;
    goto LABEL_48;
  }
LABEL_32:
  v33 = v75;
  if ( !((__int64)(*((_QWORD *)&v75 + 1) - v75) >> 2) )
    goto LABEL_92;
  v34 = v77[0];
  if ( v77[1] == v77[0] )
    goto LABEL_92;
  *((_QWORD *)&v22 + 1) = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
  if ( *((_BYTE *)Gfx::Immediate::GetConfig((Gfx::Immediate *)v22) + 62) )
  {
    DWORD1(v79) = 0;
    v83 = 0;
    if ( DWORD2(v22) && v34 && v33 )
    {
      LODWORD(v79) = DWORD2(v22);
      *((_QWORD *)&v79 + 1) = v34;
      v80 = v33;
      v81 = 0;
      v82 = 0;
      sub_180136970(&v79, 0, 0);
      v36 = 0;
      goto LABEL_48;
    }
    goto LABEL_46;
  }
  v36 = MsoScriptLayout(DWORD2(v22), v34, v33, 0);
LABEL_48:
  if ( v36 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v36, 0x138D8CBu);
LABEL_94:
    std::vector<Mso::TCntPtr<Mso::SVG::ISVGShape>>::_Xlength(v29, v16, v17, v27);
  }
  v39 = 0.0;
  v84[0] = 0.0;
  v40 = *((_DWORD *)a1 + 22);
  v41 = a8;
  if ( v40 == 1 || v40 == 2 )
  {
    v74 = 0;
    v86 = 0;
    v49 = 0;
    v42 = v70[2];
    v43 = v70[1];
    v50 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v70[2] - v70[1]) >> 3);
    if ( v50 )
    {
      v51 = 0;
      do
      {
        if ( v51 >= (__int64)(*((_QWORD *)&v75 + 1) - v75) >> 2 || (v52 = *(unsigned int *)(v75 + 4 * v51), v52 >= v50) )
          _invoke_watson(0, 0, 0, 0, 0);
        v53 = 3 * v52;
        v54 = *(_QWORD *)(v43 + 24 * v52);
        v55 = a1;
        if ( (unsigned __int64)a1[3] > 7 )
          v55 = (__int64 *)*a1;
        v56 = *(unsigned int *)(v43 + 24 * v52 + 12);
        Mso::SVG::TextRenderer::ProcessTextRun(
          (unsigned int)&v74,
          (unsigned int)&v86,
          0,
          0,
          v54,
          *(_DWORD *)(v54 + 128) == (_DWORD)v56,
          v49++ == 0,
          v43 + 8 + 8 * v53,
          (__int64)v55 + 2 * v56,
          *(_DWORD *)(v43 + 8 * v53 + 16) - v56,
          (__int64)Mso::SVG::TextRenderer::MeasureTextItem,
          (__int64)v84,
          v41);
        v42 = v70[2];
        v43 = v70[1];
        v50 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v70[2] - v70[1]) >> 3);
        v51 = v49;
      }
      while ( v49 < v50 );
      v40 = *((_DWORD *)a1 + 22);
      v39 = v84[0];
    }
  }
  else
  {
    v42 = v70[2];
    v43 = v70[1];
  }
  v44 = (double *)(a1 + 7);
  if ( !*((_BYTE *)a1 + 64) )
    v44 = v88;
  v45 = *v44;
  v46 = a5;
  v47 = (double *)(a1 + 9);
  if ( !*((_BYTE *)a1 + 80) )
    v47 = a5;
  v48 = *v47;
  v72 = v45;
  v73 = v48;
  if ( v40 != 1 )
  {
    if ( v40 != 2 )
      goto LABEL_78;
    if ( v9 == 2 )
    {
LABEL_72:
      v48 = v48 - v39;
      v73 = v48;
      goto LABEL_78;
    }
    if ( v9 == 1 )
    {
LABEL_76:
      v45 = v45 + v39;
      goto LABEL_77;
    }
    v57 = a1[4];
    if ( 0x84BDA12F684BDA13uLL * ((a1[5] - v57) >> 3) )
    {
      if ( *(_DWORD *)(v57 + 16) != 1 )
        goto LABEL_69;
      goto LABEL_76;
    }
LABEL_92:
    _invoke_watson(0, 0, 0, 0, 0);
  }
  v39 = v39 * 0.5;
  if ( v9 == 2 )
    goto LABEL_72;
  if ( v9 != 1 )
  {
LABEL_69:
    v45 = v45 - v39;
LABEL_77:
    v72 = v45;
    goto LABEL_78;
  }
  v45 = v39 + v45;
  v72 = v45;
LABEL_78:
  v58 = 0;
  v59 = 0xAAAAAAAAAAAAAAABuLL * ((v42 - v43) >> 3);
  if ( v59 )
  {
    v60 = a7;
    v61 = a6;
    v62 = v87;
    do
    {
      v63 = a1[4];
      if ( !(0x84BDA12F684BDA13uLL * ((a1[5] - v63) >> 3)) )
        goto LABEL_92;
      v64 = *(_DWORD *)(v63 + 16) == 1 ? v59 - v58 - 1 : v58;
      if ( v64 >= (unsigned __int64)((__int64)(*((_QWORD *)&v75 + 1) - v75) >> 2) )
        goto LABEL_92;
      v65 = *(unsigned int *)(v75 + 4LL * v64);
      if ( v65 >= v59 )
        goto LABEL_92;
      v66 = 3 * v65;
      v67 = *(_QWORD *)(v43 + 24 * v65);
      v68 = a1;
      if ( (unsigned __int64)a1[3] > 7 )
        v68 = (__int64 *)*a1;
      v69 = *(unsigned int *)(v43 + 24 * v65 + 12);
      Mso::SVG::TextRenderer::ProcessTextRun(
        (unsigned int)&v72,
        (unsigned int)&v73,
        *((_DWORD *)a1 + 22),
        v62,
        v67,
        *(_DWORD *)(v67 + 128) == (_DWORD)v69,
        v58++ == 0,
        v43 + 8 + 8 * v66,
        (__int64)v68 + 2 * v69,
        *(_DWORD *)(v43 + 8 * v66 + 16) - v69,
        v61,
        v60,
        v41);
      v43 = v70[1];
      v59 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v70[2] - v70[1]) >> 3);
    }
    while ( v58 < v59 );
    v45 = v72;
    v48 = v73;
  }
  *v88 = v45;
  *v46 = v48;
  std::vector<unsigned long>::~vector<unsigned long>(&v75);
  std::vector<char>::~vector<char>(v77);
  return (_UNKNOWN **)std::vector<Mso::SVG::TextRun>::~vector<Mso::SVG::TextRun>(&v70[1]);
}

```

## disassembly

```asm
0x180135284  mov     rax, rsp
0x180135287  mov     [rax+8], rbx
0x18013528b  mov     [rax+20h], r9
0x18013528f  mov     [rax+18h], r8d
0x180135293  push    rbp
0x180135294  push    rsi
0x180135295  push    rdi
0x180135296  push    r12
0x180135298  push    r13
0x18013529a  push    r14
0x18013529c  push    r15
0x18013529e  lea     rbp, [rax-48h]
0x1801352a2  sub     rsp, 110h
0x1801352a9  mov     r15d, r8d
0x1801352ac  mov     r13, rdx
0x1801352af  mov     rsi, rcx
0x1801352b2  mov     rcx, [rdx+8]
0x1801352b6  mov     rdi, [rdx]
0x1801352b9  mov     r10, rcx
0x1801352bc  sub     r10, rdi
0x1801352bf  jz      loc_180135A22
0x1801352c5  mov     r14, [rsi+20h]
0x1801352c9  mov     rax, [rsi+28h]
0x1801352cd  sub     rax, r14
0x1801352d0  sar     rax, 3
0x1801352d4  mov     rdx, 84BDA12F684BDA13h
0x1801352de  imul    rax, rdx
0x1801352e2  test    rax, rax
0x1801352e5  jnz     short loc_1801352FD
0x1801352e7  mov     [rsp+140h+Reserved], rax; Reserved
0x1801352ec  xor     r9d, r9d; LineNo
0x1801352ef  xor     r8d, r8d; FileName
0x1801352f2  xor     edx, edx; FunctionName
0x1801352f4  xor     ecx, ecx; Expression
0x1801352f6  call    cs:__imp__invoke_watson
0x1801352fd  xorps   xmm0, xmm0
0x180135300  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x180135306  mov     [rbp+40h+var_C0], 0
0x18013530e  xor     r8d, r8d
0x180135311  sar     r10, 3
0x180135315  cmp     r10, 1
0x180135319  jz      loc_180135447
0x18013531f  mov     r15d, r8d
0x180135322  sub     rcx, rdi
0x180135325  sar     rcx, 3
0x180135329  cmp     r15, rcx
0x18013532c  jnb     loc_18013542D
0x180135332  mov     edx, [rdi+r15*8]
0x180135336  lea     eax, [r8+1]
0x18013533a  mov     r8d, eax
0x18013533d  mov     dword ptr [rbp+40h+arg_8], eax
0x180135340  mov     [rbp+40h+var_A8], rax
0x180135344  cmp     rax, rcx
0x180135347  jnb     loc_18013542D
0x18013534d  mov     r12d, [rdi+rax*8]
0x180135351  mov     eax, 4000h
0x180135356  or      [rdi+r15*8+4], ax
0x18013535c  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x180135361  cmp     edx, r12d
0x180135364  jnb     loc_180135408
0x18013536a  mov     r8, r14
0x18013536d  mov     qword ptr [rbp+40h+var_70], r14
0x180135371  mov     eax, [rdi+r15*8+4]
0x180135376  mov     dword ptr [rbp+40h+var_70+8], eax
0x180135379  mov     dword ptr [rbp+40h+var_70+0Ch], edx
0x18013537c  mov     edx, [r14+80h]
0x180135383  add     edx, [r14+84h]
0x18013538a  mov     eax, r12d
0x18013538d  cmp     edx, r12d
0x180135390  cmovb   eax, edx
0x180135393  mov     dword ptr [rbp+40h+var_60], eax
0x180135396  xor     eax, eax
0x180135398  mov     dword ptr [rbp+40h+var_60+4], eax
0x18013539b  cmp     rbx, [rbp+40h+var_C0]
0x18013539f  jz      short loc_1801353C2
0x1801353a1  movups  xmm0, [rbp+40h+var_70]
0x1801353a5  movups  xmmword ptr [rbx], xmm0
0x1801353a8  movsd   xmm1, [rbp+40h+var_60]
0x1801353ad  movsd   qword ptr [rbx+10h], xmm1
0x1801353b2  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801353b7  add     rbx, 18h
0x1801353bb  mov     qword ptr [rsp+140h+var_D8+10h], rbx
0x1801353c0  jmp     short loc_1801353DB
0x1801353c2  lea     r8, [rbp+40h+var_70]
0x1801353c6  mov     rdx, rbx
0x1801353c9  lea     rcx, [rsp+140h+var_D8+8]
0x1801353ce  call    ??$_Emplace_reallocate@UTextRun@SVG@Mso@@@?$vector@UTextRun@SVG@Mso@@V?$allocator@UTextRun@SVG@Mso@@@std@@@std@@AEAAPEAUTextRun@SVG@Mso@@QEAU234@$$QEAU234@@Z; std::vector<Mso::SVG::TextRun>::_Emplace_reallocate<Mso::SVG::TextRun>(Mso::SVG::TextRun * const,Mso::SVG::TextRun &&)
0x1801353d3  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801353d8  mov     r8, r14
0x1801353db  mov     edx, [r14+84h]
0x1801353e2  add     edx, [r14+80h]
0x1801353e9  lea     r14, [r8+0D8h]
0x1801353f0  cmp     r12d, edx
0x1801353f3  cmovb   r14, r8
0x1801353f7  cmovb   edx, r12d
0x1801353fb  cmp     edx, r12d
0x1801353fe  jb      loc_18013536A
0x180135404  mov     r8d, dword ptr [rbp+40h+arg_8]
0x180135408  mov     rcx, [r13+8]
0x18013540c  mov     rdi, [r13+0]
0x180135410  mov     rax, rcx
0x180135413  sub     rax, rdi
0x180135416  sar     rax, 3
0x18013541a  dec     rax
0x18013541d  cmp     [rbp+40h+var_A8], rax
0x180135421  jb      loc_18013531F
0x180135427  mov     r15d, [rbp+40h+arg_10]
0x18013542b  jmp     short loc_18013544C
0x18013542d  mov     [rsp+140h+Reserved], 0; Reserved
0x180135436  xor     r9d, r9d; LineNo
0x180135439  xor     r8d, r8d; FileName
0x18013543c  xor     edx, edx; FunctionName
0x18013543e  xor     ecx, ecx; Expression
0x180135440  call    cs:__imp__invoke_watson
0x180135447  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x18013544c  mov     rdi, rbx
0x18013544f  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x180135454  sub     rdi, rcx
0x180135457  sar     rdi, 3
0x18013545b  mov     r12, 0AAAAAAAAAAAAAAABh
0x180135465  imul    rdi, r12
0x180135469  xorps   xmm0, xmm0
0x18013546c  movdqu  xmmword ptr [rbp+40h+var_88], xmm0
0x180135471  xor     r13d, r13d
0x180135474  mov     [rbp+40h+var_78], r13
0x180135478  test    rdi, rdi
0x18013547b  jz      short loc_1801354B9
0x18013547d  mov     rdx, rdi
0x180135480  lea     rcx, [rbp+40h+var_88]
0x180135484  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180135489  mov     rbx, [rbp+40h+var_88]
0x18013548d  mov     r8, rdi; Size
0x180135490  xor     edx, edx; Val
0x180135492  mov     rcx, rbx; void *
0x180135495  call    memset_0
0x18013549a  lea     rax, [rbx+rdi]
0x18013549e  mov     [rbp+40h+var_88+8], rax
0x1801354a2  mov     [rbp+40h+arg_8], r13
0x1801354a6  lea     rcx, [rbp+40h+arg_8]
0x1801354aa  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x1801354af  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801354b4  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x1801354b9  mov     r9d, r13d
0x1801354bc  mov     rax, rbx
0x1801354bf  sub     rax, rcx
0x1801354c2  sar     rax, 3
0x1801354c6  imul    rax, r12
0x1801354ca  test    rax, rax
0x1801354cd  jz      short loc_180135523
0x1801354cf  mov     rdx, r13
0x1801354d2  cmp     rdx, rax
0x1801354d5  jnb     loc_180135626
0x1801354db  lea     rax, [rdx+rdx*2]
0x1801354df  mov     r8b, [rcx+rax*8+0Ah]
0x1801354e4  and     r8b, 1Fh
0x1801354e8  mov     rax, [rbp+40h+var_88+8]
0x1801354ec  mov     rcx, [rbp+40h+var_88]
0x1801354f0  sub     rax, rcx
0x1801354f3  cmp     rdx, rax
0x1801354f6  jnb     loc_180135626
0x1801354fc  mov     [rcx+rdx], r8b
0x180135500  inc     r9d
0x180135503  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x180135508  mov     rax, rbx
0x18013550b  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x180135510  sub     rax, rcx
0x180135513  sar     rax, 3
0x180135517  imul    rax, r12
0x18013551b  mov     edx, r9d
0x18013551e  cmp     rdx, rax
0x180135521  jb      short loc_1801354DB
0x180135523  mov     rax, rbx
0x180135526  sub     rax, rcx
0x180135529  sar     rax, 3
0x18013552d  imul    rax, r12
0x180135531  xorps   xmm0, xmm0
0x180135534  movdqu  [rbp+40h+var_A0], xmm0
0x180135539  mov     [rbp+40h+var_90], r13
0x18013553d  test    rax, rax
0x180135540  jz      short loc_18013559D
0x180135542  mov     rcx, 3FFFFFFFFFFFFFFFh
0x18013554c  cmp     rax, rcx
0x18013554f  ja      loc_180135A69
0x180135555  lea     rdi, ds:0[rax*4]
0x18013555d  test    rdi, rdi
0x180135560  jnz     loc_18013563C
0x180135566  mov     rax, r13
0x180135569  mov     qword ptr [rbp+40h+var_A0], rax
0x18013556d  lea     rbx, [rax+rdi]
0x180135571  mov     [rbp+40h+var_90], rbx
0x180135575  mov     r8, rdi; Size
0x180135578  xor     edx, edx; Val
0x18013557a  mov     rcx, rax; void *
0x18013557d  call    memset_0
0x180135582  mov     qword ptr [rbp+40h+var_A0+8], rbx
0x180135586  mov     [rbp+40h+arg_8], r13
0x18013558a  lea     rcx, [rbp+40h+arg_8]
0x18013558e  call    ??1?$_Tidy_guard@V?$vector@MV?$allocator@M@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<float>>::~_Tidy_guard<std::vector<float>>(void)
0x180135593  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x180135598  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x18013559d  mov     r14, qword ptr [rbp+40h+var_A0]
0x1801355a1  mov     rax, qword ptr [rbp+40h+var_A0+8]
0x1801355a5  sub     rax, r14
0x1801355a8  sar     rax, 2
0x1801355ac  test    rax, rax
0x1801355af  jz      loc_180135A40
0x1801355b5  mov     rdi, [rbp+40h+var_88]
0x1801355b9  cmp     [rbp+40h+var_88+8], rdi
0x1801355bd  jz      loc_180135A40
0x1801355c3  sub     rbx, rcx
0x1801355c6  sar     rbx, 3
0x1801355ca  imul    rbx, r12
0x1801355ce  call    cs:__imp_?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ; Gfx::Immediate::GetConfig(void)
0x1801355d4  cmp     [rax+3Eh], r13b
0x1801355d8  jz      loc_180135691
0x1801355de  mov     dword ptr [rbp+40h+var_70+4], r13d
0x1801355e2  mov     [rbp+40h+var_4C], r13d
0x1801355e6  test    ebx, ebx
0x1801355e8  jz      loc_18013568A
0x1801355ee  test    rdi, rdi
0x1801355f1  jz      loc_18013568A
0x1801355f7  test    r14, r14
0x1801355fa  jz      loc_18013568A
0x180135600  mov     dword ptr [rbp+40h+var_70], ebx
0x180135603  mov     qword ptr [rbp+40h+var_70+8], rdi
0x180135607  mov     [rbp+40h+var_60], r14
0x18013560b  mov     [rbp+40h+var_58], r13
0x18013560f  mov     [rbp+40h+var_50], r13d
0x180135613  xor     r8d, r8d
0x180135616  xor     edx, edx
0x180135618  lea     rcx, [rbp+40h+var_70]
0x18013561c  call    sub_180136970
0x180135621  mov     eax, r13d
0x180135624  jmp     short loc_1801356A2
0x180135626  mov     [rsp+140h+Reserved], r13; Reserved
0x18013562b  xor     r9d, r9d; LineNo
0x18013562e  xor     r8d, r8d; FileName
0x180135631  xor     edx, edx; FunctionName
0x180135633  xor     ecx, ecx; Expression
0x180135635  call    cs:__imp__invoke_watson
0x18013563c  cmp     rdi, 1000h
0x180135643  jb      short loc_180135671
0x180135645  lea     rcx, [rdi+27h]; Size
0x180135649  cmp     rcx, rdi
0x18013564c  jbe     loc_180135A6F
0x180135652  call    cs:__imp_malloc
0x180135658  mov     rcx, rax
0x18013565b  test    rax, rax
0x18013565e  jz      short loc_180135683
0x180135660  add     rax, 27h ; '''
0x180135664  and     rax, 0FFFFFFFFFFFFFFE0h
0x180135668  mov     [rax-8], rcx
0x18013566c  jmp     loc_180135569
0x180135671  mov     rcx, rdi; Size
0x180135674  call    cs:__imp_malloc
0x18013567a  test    rax, rax
0x18013567d  jnz     loc_180135569
0x180135683  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180135689  nop
0x18013568a  mov     eax, 80070057h
0x18013568f  jmp     short loc_1801356A2
0x180135691  xor     r9d, r9d
0x180135694  mov     r8, r14
0x180135697  mov     rdx, rdi
0x18013569a  mov     ecx, ebx
0x18013569c  call    cs:__imp_MsoScriptLayout
0x1801356a2  test    eax, eax
0x1801356a4  js      loc_180135A56
0x1801356aa  xorps   xmm1, xmm1
0x1801356ad  movsd   [rbp+40h+var_48], xmm1
0x1801356b2  mov     eax, [rsi+58h]
0x1801356b5  mov     r12, [rbp+40h+arg_38]
0x1801356bc  cmp     eax, 1
0x1801356bf  jz      short loc_180135740
0x1801356c1  cmp     eax, 2
0x1801356c4  jz      short loc_180135740
0x1801356c6  mov     rcx, qword ptr [rsp+140h+var_D8+10h]
0x1801356cb  mov     r10, qword ptr [rsp+140h+var_D8+8]
0x1801356d0  mov     r14, 0AAAAAAAAAAAAAAABh
0x1801356da  cmp     [rsi+40h], r13b
0x1801356de  lea     rdx, [rsi+38h]
0x1801356e2  jnz     short loc_1801356E8
0x1801356e4  mov     rdx, [rbp+40h+arg_18]
0x1801356e8  movsd   xmm0, qword ptr [rdx]
0x1801356ec  mov     rdi, [rbp+40h+arg_20]
0x1801356f0  cmp     [rsi+50h], r13b
0x1801356f4  lea     rdx, [rsi+48h]
0x1801356f8  jnz     short loc_1801356FD
0x1801356fa  mov     rdx, rdi
0x1801356fd  movsd   xmm2, qword ptr [rdx]
0x180135701  movsd   [rbp+40h+var_B8], xmm0
0x180135706  movsd   [rbp+40h+var_B0], xmm2
0x18013570b  cmp     eax, 1
0x18013570e  jnz     loc_180135875
0x180135714  mulsd   xmm1, cs:__real@3fe0000000000000
0x18013571c  cmp     r15d, 2
0x180135720  jz      loc_18013587F
0x180135726  cmp     r15d, eax
0x180135729  jnz     loc_18013586F
0x18013572f  addsd   xmm1, xmm0
  ... truncated ...
```
