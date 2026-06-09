# Mso::SVG::TextRenderer::MergeTextChunkAndItems(Mso::SVG::TextChunk const &,std::vector<tag_SCRIPT_ITEM,std::allocator<tag_SCRIPT_ITEM>> &,Mso::SVG::WritingMode,double &,double &,void (*)(void *,Mso::SVG::TextChunkItem const &,Mso::SVG::TextAnchor,GEL::Font const &,tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,bool,std::vector<ushort,std::allocator<ushort>> const &,std::vector<float,std::allocator<float>> const &,std::vector<float,std::allocator<float>> const &,std::vector<GEL::Vector,std::allocator<GEL::Vector>> const &,float,float,float,float,std::vector<ushort,std::allocator<ushort>> const &,Math::TAffine3x3<double> const &,Mso::SVG::TextRenderingParams const &),void *,Mso::SVG::TextRenderingParams const &)

- ea: `0x1801352c4`
- end: `0x180135ab5`
- name: `?MergeTextChunkAndItems@TextRenderer@SVG@Mso@@CAXAEBUTextChunk@23@AEAV?$vector@Utag_SCRIPT_ITEM@@V?$allocator@Utag_SCRIPT_ITEM@@@std@@@std@@W4WritingMode@23@AEAN3P6AXPEAXAEBUTextChunkItem@23@W4TextAnchor@23@AEBUFont@GEL@@AEBUtag_SCRIPT_ANALYSIS@@PEB_WI_N_NAEBV?$vector@GV?$allocator@G@std@@@6@AEBV?$vector@MV?$allocator@M@std@@@6@AEBV?$vector@MV?$allocator@M@std@@@6@AEBV?$vector@UVector@GEL@@V?$allocator@UVector@GEL@@@std@@@6@MMMMAEBV?$vector@GV?$allocator@G@std@@@6@AEBU?$TAffine3x3@N@Math@@AEBUTextRenderingParams@23@@Z4AEBUTextRenderingParams@23@@Z`
- size: `2033`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180135ab8`

## callees

- `0x180008a80`
- `0x180009320`
- `0x18000bb10`
- `0x18003a314`
- `0x18005b958`
- `0x18006129c`
- `0x180134eb0`
- `0x1801352c4`
- `0x1801369b0`
- `0x180137a04`
- `0x180138194`
- `0x180138890`
- `0x18013ba2c`
- `0x18013e72c`

## import_xrefs

- `mso40uiWin32Client!__imp_MsoScriptLayout` at `0x1801356dc`
- `mso40uiWin32Client!__imp_MsoScriptLayout` at `0x1801356dc`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1801356c3`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1801356c3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135692`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801356b4`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180135692`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801356b4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135336`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135480`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135675`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801358a8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135a8f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135336`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135480`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135675`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1801358a8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180135a8f`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x18013560e`
- `gfx!?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ` at `0x18013560e`

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
      sub_1801369B0(&v79, 0, 0);
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
0x1801352c4  mov     rax, rsp
0x1801352c7  mov     [rax+8], rbx
0x1801352cb  mov     [rax+20h], r9
0x1801352cf  mov     [rax+18h], r8d
0x1801352d3  push    rbp
0x1801352d4  push    rsi
0x1801352d5  push    rdi
0x1801352d6  push    r12
0x1801352d8  push    r13
0x1801352da  push    r14
0x1801352dc  push    r15
0x1801352de  lea     rbp, [rax-48h]
0x1801352e2  sub     rsp, 110h
0x1801352e9  mov     r15d, r8d
0x1801352ec  mov     r13, rdx
0x1801352ef  mov     rsi, rcx
0x1801352f2  mov     rcx, [rdx+8]
0x1801352f6  mov     rdi, [rdx]
0x1801352f9  mov     r10, rcx
0x1801352fc  sub     r10, rdi
0x1801352ff  jz      loc_180135A62
0x180135305  mov     r14, [rsi+20h]
0x180135309  mov     rax, [rsi+28h]
0x18013530d  sub     rax, r14
0x180135310  sar     rax, 3
0x180135314  mov     rdx, 84BDA12F684BDA13h
0x18013531e  imul    rax, rdx
0x180135322  test    rax, rax
0x180135325  jnz     short loc_18013533D
0x180135327  mov     [rsp+140h+Reserved], rax; Reserved
0x18013532c  xor     r9d, r9d; LineNo
0x18013532f  xor     r8d, r8d; FileName
0x180135332  xor     edx, edx; FunctionName
0x180135334  xor     ecx, ecx; Expression
0x180135336  call    cs:__imp__invoke_watson
0x18013533d  xorps   xmm0, xmm0
0x180135340  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm0
0x180135346  mov     [rbp+40h+var_C0], 0
0x18013534e  xor     r8d, r8d
0x180135351  sar     r10, 3
0x180135355  cmp     r10, 1
0x180135359  jz      loc_180135487
0x18013535f  mov     r15d, r8d
0x180135362  sub     rcx, rdi
0x180135365  sar     rcx, 3
0x180135369  cmp     r15, rcx
0x18013536c  jnb     loc_18013546D
0x180135372  mov     edx, [rdi+r15*8]
0x180135376  lea     eax, [r8+1]
0x18013537a  mov     r8d, eax
0x18013537d  mov     dword ptr [rbp+40h+arg_8], eax
0x180135380  mov     [rbp+40h+var_A8], rax
0x180135384  cmp     rax, rcx
0x180135387  jnb     loc_18013546D
0x18013538d  mov     r12d, [rdi+rax*8]
0x180135391  mov     eax, 4000h
0x180135396  or      [rdi+r15*8+4], ax
0x18013539c  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801353a1  cmp     edx, r12d
0x1801353a4  jnb     loc_180135448
0x1801353aa  mov     r8, r14
0x1801353ad  mov     qword ptr [rbp+40h+var_70], r14
0x1801353b1  mov     eax, [rdi+r15*8+4]
0x1801353b6  mov     dword ptr [rbp+40h+var_70+8], eax
0x1801353b9  mov     dword ptr [rbp+40h+var_70+0Ch], edx
0x1801353bc  mov     edx, [r14+80h]
0x1801353c3  add     edx, [r14+84h]
0x1801353ca  mov     eax, r12d
0x1801353cd  cmp     edx, r12d
0x1801353d0  cmovb   eax, edx
0x1801353d3  mov     dword ptr [rbp+40h+var_60], eax
0x1801353d6  xor     eax, eax
0x1801353d8  mov     dword ptr [rbp+40h+var_60+4], eax
0x1801353db  cmp     rbx, [rbp+40h+var_C0]
0x1801353df  jz      short loc_180135402
0x1801353e1  movups  xmm0, [rbp+40h+var_70]
0x1801353e5  movups  xmmword ptr [rbx], xmm0
0x1801353e8  movsd   xmm1, [rbp+40h+var_60]
0x1801353ed  movsd   qword ptr [rbx+10h], xmm1
0x1801353f2  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801353f7  add     rbx, 18h
0x1801353fb  mov     qword ptr [rsp+140h+var_D8+10h], rbx
0x180135400  jmp     short loc_18013541B
0x180135402  lea     r8, [rbp+40h+var_70]
0x180135406  mov     rdx, rbx
0x180135409  lea     rcx, [rsp+140h+var_D8+8]
0x18013540e  call    ??$_Emplace_reallocate@UTextRun@SVG@Mso@@@?$vector@UTextRun@SVG@Mso@@V?$allocator@UTextRun@SVG@Mso@@@std@@@std@@AEAAPEAUTextRun@SVG@Mso@@QEAU234@$$QEAU234@@Z; std::vector<Mso::SVG::TextRun>::_Emplace_reallocate<Mso::SVG::TextRun>(Mso::SVG::TextRun * const,Mso::SVG::TextRun &&)
0x180135413  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x180135418  mov     r8, r14
0x18013541b  mov     edx, [r14+84h]
0x180135422  add     edx, [r14+80h]
0x180135429  lea     r14, [r8+0D8h]
0x180135430  cmp     r12d, edx
0x180135433  cmovb   r14, r8
0x180135437  cmovb   edx, r12d
0x18013543b  cmp     edx, r12d
0x18013543e  jb      loc_1801353AA
0x180135444  mov     r8d, dword ptr [rbp+40h+arg_8]
0x180135448  mov     rcx, [r13+8]
0x18013544c  mov     rdi, [r13+0]
0x180135450  mov     rax, rcx
0x180135453  sub     rax, rdi
0x180135456  sar     rax, 3
0x18013545a  dec     rax
0x18013545d  cmp     [rbp+40h+var_A8], rax
0x180135461  jb      loc_18013535F
0x180135467  mov     r15d, [rbp+40h+arg_10]
0x18013546b  jmp     short loc_18013548C
0x18013546d  mov     [rsp+140h+Reserved], 0; Reserved
0x180135476  xor     r9d, r9d; LineNo
0x180135479  xor     r8d, r8d; FileName
0x18013547c  xor     edx, edx; FunctionName
0x18013547e  xor     ecx, ecx; Expression
0x180135480  call    cs:__imp__invoke_watson
0x180135487  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x18013548c  mov     rdi, rbx
0x18013548f  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x180135494  sub     rdi, rcx
0x180135497  sar     rdi, 3
0x18013549b  mov     r12, 0AAAAAAAAAAAAAAABh
0x1801354a5  imul    rdi, r12
0x1801354a9  xorps   xmm0, xmm0
0x1801354ac  movdqu  xmmword ptr [rbp+40h+var_88], xmm0
0x1801354b1  xor     r13d, r13d
0x1801354b4  mov     [rbp+40h+var_78], r13
0x1801354b8  test    rdi, rdi
0x1801354bb  jz      short loc_1801354F9
0x1801354bd  mov     rdx, rdi
0x1801354c0  lea     rcx, [rbp+40h+var_88]
0x1801354c4  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x1801354c9  mov     rbx, [rbp+40h+var_88]
0x1801354cd  mov     r8, rdi; Size
0x1801354d0  xor     edx, edx; Val
0x1801354d2  mov     rcx, rbx; void *
0x1801354d5  call    memset_0
0x1801354da  lea     rax, [rbx+rdi]
0x1801354de  mov     [rbp+40h+var_88+8], rax
0x1801354e2  mov     [rbp+40h+arg_8], r13
0x1801354e6  lea     rcx, [rbp+40h+arg_8]
0x1801354ea  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x1801354ef  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801354f4  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x1801354f9  mov     r9d, r13d
0x1801354fc  mov     rax, rbx
0x1801354ff  sub     rax, rcx
0x180135502  sar     rax, 3
0x180135506  imul    rax, r12
0x18013550a  test    rax, rax
0x18013550d  jz      short loc_180135563
0x18013550f  mov     rdx, r13
0x180135512  cmp     rdx, rax
0x180135515  jnb     loc_180135666
0x18013551b  lea     rax, [rdx+rdx*2]
0x18013551f  mov     r8b, [rcx+rax*8+0Ah]
0x180135524  and     r8b, 1Fh
0x180135528  mov     rax, [rbp+40h+var_88+8]
0x18013552c  mov     rcx, [rbp+40h+var_88]
0x180135530  sub     rax, rcx
0x180135533  cmp     rdx, rax
0x180135536  jnb     loc_180135666
0x18013553c  mov     [rcx+rdx], r8b
0x180135540  inc     r9d
0x180135543  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x180135548  mov     rax, rbx
0x18013554b  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x180135550  sub     rax, rcx
0x180135553  sar     rax, 3
0x180135557  imul    rax, r12
0x18013555b  mov     edx, r9d
0x18013555e  cmp     rdx, rax
0x180135561  jb      short loc_18013551B
0x180135563  mov     rax, rbx
0x180135566  sub     rax, rcx
0x180135569  sar     rax, 3
0x18013556d  imul    rax, r12
0x180135571  xorps   xmm0, xmm0
0x180135574  movdqu  [rbp+40h+var_A0], xmm0
0x180135579  mov     [rbp+40h+var_90], r13
0x18013557d  test    rax, rax
0x180135580  jz      short loc_1801355DD
0x180135582  mov     rcx, 3FFFFFFFFFFFFFFFh
0x18013558c  cmp     rax, rcx
0x18013558f  ja      loc_180135AA9
0x180135595  lea     rdi, ds:0[rax*4]
0x18013559d  test    rdi, rdi
0x1801355a0  jnz     loc_18013567C
0x1801355a6  mov     rax, r13
0x1801355a9  mov     qword ptr [rbp+40h+var_A0], rax
0x1801355ad  lea     rbx, [rax+rdi]
0x1801355b1  mov     [rbp+40h+var_90], rbx
0x1801355b5  mov     r8, rdi; Size
0x1801355b8  xor     edx, edx; Val
0x1801355ba  mov     rcx, rax; void *
0x1801355bd  call    memset_0
0x1801355c2  mov     qword ptr [rbp+40h+var_A0+8], rbx
0x1801355c6  mov     [rbp+40h+arg_8], r13
0x1801355ca  lea     rcx, [rbp+40h+arg_8]
0x1801355ce  call    ??1?$_Tidy_guard@V?$vector@MV?$allocator@M@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<float>>::~_Tidy_guard<std::vector<float>>(void)
0x1801355d3  mov     rbx, qword ptr [rsp+140h+var_D8+10h]
0x1801355d8  mov     rcx, qword ptr [rsp+140h+var_D8+8]
0x1801355dd  mov     r14, qword ptr [rbp+40h+var_A0]
0x1801355e1  mov     rax, qword ptr [rbp+40h+var_A0+8]
0x1801355e5  sub     rax, r14
0x1801355e8  sar     rax, 2
0x1801355ec  test    rax, rax
0x1801355ef  jz      loc_180135A80
0x1801355f5  mov     rdi, [rbp+40h+var_88]
0x1801355f9  cmp     [rbp+40h+var_88+8], rdi
0x1801355fd  jz      loc_180135A80
0x180135603  sub     rbx, rcx
0x180135606  sar     rbx, 3
0x18013560a  imul    rbx, r12
0x18013560e  call    cs:__imp_?GetConfig@Immediate@Gfx@@YAAEBVConfig@2@XZ; Gfx::Immediate::GetConfig(void)
0x180135614  cmp     [rax+3Eh], r13b
0x180135618  jz      loc_1801356D1
0x18013561e  mov     dword ptr [rbp+40h+var_70+4], r13d
0x180135622  mov     [rbp+40h+var_4C], r13d
0x180135626  test    ebx, ebx
0x180135628  jz      loc_1801356CA
0x18013562e  test    rdi, rdi
0x180135631  jz      loc_1801356CA
0x180135637  test    r14, r14
0x18013563a  jz      loc_1801356CA
0x180135640  mov     dword ptr [rbp+40h+var_70], ebx
0x180135643  mov     qword ptr [rbp+40h+var_70+8], rdi
0x180135647  mov     [rbp+40h+var_60], r14
0x18013564b  mov     [rbp+40h+var_58], r13
0x18013564f  mov     [rbp+40h+var_50], r13d
0x180135653  xor     r8d, r8d
0x180135656  xor     edx, edx
0x180135658  lea     rcx, [rbp+40h+var_70]
0x18013565c  call    sub_1801369B0
0x180135661  mov     eax, r13d
0x180135664  jmp     short loc_1801356E2
0x180135666  mov     [rsp+140h+Reserved], r13; Reserved
0x18013566b  xor     r9d, r9d; LineNo
0x18013566e  xor     r8d, r8d; FileName
0x180135671  xor     edx, edx; FunctionName
0x180135673  xor     ecx, ecx; Expression
0x180135675  call    cs:__imp__invoke_watson
0x18013567c  cmp     rdi, 1000h
0x180135683  jb      short loc_1801356B1
0x180135685  lea     rcx, [rdi+27h]; Size
0x180135689  cmp     rcx, rdi
0x18013568c  jbe     loc_180135AAF
0x180135692  call    cs:__imp_malloc
0x180135698  mov     rcx, rax
0x18013569b  test    rax, rax
0x18013569e  jz      short loc_1801356C3
0x1801356a0  add     rax, 27h ; '''
0x1801356a4  and     rax, 0FFFFFFFFFFFFFFE0h
0x1801356a8  mov     [rax-8], rcx
0x1801356ac  jmp     loc_1801355A9
0x1801356b1  mov     rcx, rdi; Size
0x1801356b4  call    cs:__imp_malloc
0x1801356ba  test    rax, rax
0x1801356bd  jnz     loc_1801355A9
0x1801356c3  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1801356c9  nop
0x1801356ca  mov     eax, 80070057h
0x1801356cf  jmp     short loc_1801356E2
0x1801356d1  xor     r9d, r9d
0x1801356d4  mov     r8, r14
0x1801356d7  mov     rdx, rdi
0x1801356da  mov     ecx, ebx
0x1801356dc  call    cs:__imp_MsoScriptLayout
0x1801356e2  test    eax, eax
0x1801356e4  js      loc_180135A96
0x1801356ea  xorps   xmm1, xmm1
0x1801356ed  movsd   [rbp+40h+var_48], xmm1
0x1801356f2  mov     eax, [rsi+58h]
0x1801356f5  mov     r12, [rbp+40h+arg_38]
0x1801356fc  cmp     eax, 1
0x1801356ff  jz      short loc_180135780
0x180135701  cmp     eax, 2
0x180135704  jz      short loc_180135780
0x180135706  mov     rcx, qword ptr [rsp+140h+var_D8+10h]
0x18013570b  mov     r10, qword ptr [rsp+140h+var_D8+8]
0x180135710  mov     r14, 0AAAAAAAAAAAAAAABh
0x18013571a  cmp     [rsi+40h], r13b
0x18013571e  lea     rdx, [rsi+38h]
0x180135722  jnz     short loc_180135728
0x180135724  mov     rdx, [rbp+40h+arg_18]
0x180135728  movsd   xmm0, qword ptr [rdx]
0x18013572c  mov     rdi, [rbp+40h+arg_20]
0x180135730  cmp     [rsi+50h], r13b
0x180135734  lea     rdx, [rsi+48h]
0x180135738  jnz     short loc_18013573D
0x18013573a  mov     rdx, rdi
0x18013573d  movsd   xmm2, qword ptr [rdx]
0x180135741  movsd   [rbp+40h+var_B8], xmm0
0x180135746  movsd   [rbp+40h+var_B0], xmm2
0x18013574b  cmp     eax, 1
0x18013574e  jnz     loc_1801358B5
0x180135754  mulsd   xmm1, cs:__real@3fe0000000000000
0x18013575c  cmp     r15d, 2
0x180135760  jz      loc_1801358BF
0x180135766  cmp     r15d, eax
0x180135769  jnz     loc_1801358AF
0x18013576f  addsd   xmm1, xmm0
  ... truncated ...
```
