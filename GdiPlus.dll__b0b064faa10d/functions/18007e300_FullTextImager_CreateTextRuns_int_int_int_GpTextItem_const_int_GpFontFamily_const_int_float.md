# FullTextImager::CreateTextRuns(int,int,int,GpTextItem const &,int,GpFontFamily const *,int,float)

- ea: `0x18007e300`
- end: `0x18007f0b1`
- name: `?CreateTextRuns@FullTextImager@@AEAA?AW4Status@@HHHAEBVGpTextItem@@HPEBVGpFontFamily@@HM@Z`
- size: `3505`
- prototype: `enum Status __high(int, int, int, const struct GpTextItem *, int, const struct GpFontFamily *, int, float)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18007daf0`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x1800204a4`
- `0x1800782bc`
- `0x18007e300`
- `0x18007fa14`
- `0x18007fef8`
- `0x1800823f4`
- `0x1800a6348`
- `0x1800bb5fc`
- `0x1800bc0d0`
- `0x1800d220c`
- `0x1800d83d4`
- `0x1800fe680`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e3d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e3ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e422`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e44e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e650`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e764`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e78f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e9ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e3d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e3ff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e422`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e44e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e650`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e764`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e78f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e7e8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007e9ce`

## pseudocode

```c
__int64 __fastcall FullTextImager::CreateTextRuns(
        __int64 a1,
        unsigned int a2,
        int a3,
        signed int a4,
        __int64 *a5,
        int a6,
        GpFontFamily *a7,
        int a8,
        float a9)
{
  char v10; // bl
  int v11; // eax
  struct GpFontFace *v12; // r12
  unsigned int v13; // esi
  int v14; // eax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rax
  unsigned __int64 v17; // kr00_8
  unsigned __int16 *v18; // r13
  SIZE_T v19; // rax
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v20; // rbx
  SIZE_T v21; // rax
  unsigned __int16 *v22; // r14
  SIZE_T v23; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v24; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v25; // rdi
  __int64 v26; // rax
  int v27; // ecx
  unsigned __int16 *v28; // rdx
  int GlyphsWithHotKeys; // r12d
  unsigned int v30; // edi
  unsigned int v31; // edx
  __int16 v32; // r8
  __int64 v33; // r12
  __int64 v34; // rdi
  signed int v35; // edx
  bool i; // cc
  _DWORD *v38; // rax
  _DWORD *v39; // r14
  _DWORD *v40; // r9
  __int64 *v41; // rax
  __int64 v42; // rcx
  struct GpFontFace *v43; // rax
  __int64 v44; // rcx
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v45; // rax
  unsigned int v46; // r13d
  __int64 v47; // rdx
  unsigned int v48; // edx
  unsigned int v49; // ebx
  SIZE_T v50; // rax
  unsigned __int64 v51; // rbx
  SIZE_T v52; // rax
  SIZE_T v53; // rax
  unsigned __int16 *v54; // r14
  SIZE_T v55; // rax
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v56; // r12
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v57; // rbx
  FullTextImager *v58; // rcx
  struct GpFamilyFallback *FamilyFallback; // r10
  unsigned int UniformFallbackFace; // edi
  __int64 v61; // r8
  struct GpFontFace *v62; // rdi
  __int16 v63; // ax
  __int64 v64; // rdx
  __int64 v65; // rax
  int v66; // eax
  char *v67; // rax
  char *v68; // rbx
  __int64 v69; // rcx
  unsigned int v70; // eax
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v71; // rax
  char *v72; // r9
  unsigned int v73; // ebx
  unsigned int v74; // r13d
  __int64 v75; // r9
  _BYTE *v76; // r8
  int v77; // r14d
  __int64 v78; // r9
  __int64 v79; // r11
  unsigned int v80; // eax
  struct GpFontFace *v81; // r10
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v82; // r11
  signed int v83; // r9d
  __int64 v84; // rdi
  __int64 v85; // rcx
  _BYTE *v86; // r8
  unsigned __int16 *v87; // rcx
  __int64 v88; // rax
  unsigned __int64 v89; // rdi
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // rax
  __int64 v95; // rax
  unsigned __int64 v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  signed int v103; // eax
  signed int v104; // eax
  const unsigned __int16 *v105; // [rsp+40h] [rbp-E8h]
  struct IDWriteNumberSubstitution *v106; // [rsp+48h] [rbp-E0h]
  struct DWRITE_TYPOGRAPHIC_FEATURES **v107; // [rsp+50h] [rbp-D8h]
  unsigned int *v108; // [rsp+58h] [rbp-D0h]
  unsigned int v109; // [rsp+60h] [rbp-C8h]
  unsigned __int16 v110; // [rsp+A8h] [rbp-80h] BYREF
  unsigned __int16 v111; // [rsp+AAh] [rbp-7Eh]
  unsigned int v112; // [rsp+ACh] [rbp-7Ch] BYREF
  unsigned int v113; // [rsp+B0h] [rbp-78h]
  int v114; // [rsp+B4h] [rbp-74h]
  signed int v115; // [rsp+B8h] [rbp-70h]
  unsigned int v116; // [rsp+BCh] [rbp-6Ch] BYREF
  struct DWRITE_SHAPING_GLYPH_PROPERTIES *v117; // [rsp+C0h] [rbp-68h] BYREF
  __int16 v118; // [rsp+C8h] [rbp-60h]
  int v119; // [rsp+CCh] [rbp-5Ch]
  int v120; // [rsp+D0h] [rbp-58h]
  unsigned int v121; // [rsp+D4h] [rbp-54h]
  __int64 v122; // [rsp+D8h] [rbp-50h] BYREF
  unsigned __int16 *v123; // [rsp+E0h] [rbp-48h] BYREF
  struct DWRITE_SHAPING_TEXT_PROPERTIES *v124; // [rsp+E8h] [rbp-40h]
  __int16 v125; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v126; // [rsp+F8h] [rbp-30h]
  struct GpFontFace *Face; // [rsp+100h] [rbp-28h]
  __int64 *v128; // [rsp+108h] [rbp-20h]
  unsigned __int16 *v129; // [rsp+110h] [rbp-18h] BYREF
  unsigned int v130; // [rsp+118h] [rbp-10h]
  struct GpFontFace *j; // [rsp+120h] [rbp-8h]
  struct GpFontFace *v132; // [rsp+128h] [rbp+0h] BYREF
  GpFontFamily *v133; // [rsp+130h] [rbp+8h]
  int v134; // [rsp+138h] [rbp+10h] BYREF
  _BYTE *v135; // [rsp+140h] [rbp+18h]
  _BYTE v136[128]; // [rsp+148h] [rbp+20h] BYREF

  v128 = a5;
  v126 = a1;
  v10 = *((_BYTE *)a5 + 4);
  v11 = *((_BYTE *)a5 + 1) & 8;
  v121 = a2;
  v120 = v11;
  v114 = a3;
  v133 = a7;
  v130 = a8;
  Face = GpFontFamily::GetFace(a7, a8);
  v12 = Face;
  if ( !Face )
    return 1;
  v13 = 1;
  v119 = v10 & 1;
  while ( 1 )
  {
    if ( a4 <= 0 )
      return 0;
    v14 = 3 * a4 / 2 + 16;
    v115 = v14;
    if ( (unsigned int)v14 > 0xFFFF )
      return 2;
    v15 = v14;
    v17 = v14;
    v16 = 2LL * v14;
    if ( !is_mul_ok(v17, 2u) )
      v16 = -1;
    v18 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v16);
    v129 = v18;
    v19 = 2LL * a4;
    if ( !is_mul_ok(a4, 2u) )
      v19 = -1;
    v20 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v19);
    v21 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v21 = -1;
    v22 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v21);
    v123 = v22;
    v23 = 2 * v15;
    if ( !is_mul_ok(v15, 2u) )
      v23 = -1;
    v24 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v23);
    v112 = 0;
    v25 = v24;
    v117 = v24;
    if ( !v18 || !v20 || !v22 || !v24 )
    {
LABEL_91:
      v13 = 3;
LABEL_85:
      GpFree(v25);
      GpFree(v22);
      GpFree(v20);
LABEL_86:
      GpFree(v18);
      return v13;
    }
    v122 = 0;
    LOWORD(v122) = GdipScriptToDWriteScript((unsigned int)*(char *)v128);
    HIDWORD(v122) = 0;
    while ( 1 )
    {
      if ( *(_BYTE *)v128 == 44 )
      {
        v118 = 0;
        v109 = 0;
        v108 = 0;
        v107 = 0;
        v106 = 0;
        v105 = 0;
        v75 = *((_QWORD *)v12 + 1);
        v125 = 8203;
        if ( (*(int (__fastcall **)(struct IDWriteTextAnalyzer *, __int16 *, __int64, __int64, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
               Globals::g_DWriteTextAnalyzer,
               &v125,
               1,
               v75,
               v120,
               v119,
               &v122) < 0 )
          goto LABEL_85;
        v134 = 32;
        v76 = v136;
        v135 = v136;
        if ( a4 > 32 )
        {
          AutoBuffer<unsigned int,32>::SetSize(&v134, (unsigned int)a4);
          v76 = v135;
          if ( v134 < 0 || v134 > 32 && v135 == v136 )
          {
            if ( v135 != v136 )
              GpFree(v135);
            v134 = -1;
            v135 = v136;
            goto LABEL_91;
          }
        }
        v77 = v114;
        v78 = 0;
        v79 = v126;
        while ( 1 )
        {
          *(_DWORD *)&v76[4 * v78] = *(unsigned __int16 *)(*(_QWORD *)(v79 + 24) + 2LL * (v77 + (int)v78));
          v78 = (unsigned int)(v78 + 1);
          if ( (int)v78 >= a4 )
            break;
          v76 = v135;
        }
        v22 = v123;
        v80 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned __int16 *))(**((_QWORD **)v12 + 1) + 88LL))(
                *((_QWORD *)v12 + 1),
                v135,
                (unsigned int)a4,
                v123);
        v81 = Face;
        v82 = v117;
        v83 = 0;
        LODWORD(v124) = v80;
        v113 = v80 >> 31;
        v84 = v126;
        v85 = 0;
        do
        {
          v18[v85] = v83;
          *((_WORD *)v82 + v85) = 16;
          v86 = v135;
          *((_WORD *)v20 + v85) = 0;
          if ( (a6 & 0x20) == 0
            && ((unsigned int)(*(_DWORD *)&v86[4 * v85] - 8203) < 5 || *(_DWORD *)&v86[4 * v85] == 65279)
            || v22[v85] == *((_WORD *)v81 + 50)
            || *(_DWORD *)&v86[4 * v85] == 0xFFFF && (v88 = *(_QWORD *)(v84 + 184)) != 0 && *(_DWORD *)(v88 + 68) )
          {
            v22[v85] = *((_WORD *)v81 + 51);
            *((_WORD *)v82 + v85) = v118;
            v86 = v135;
          }
          ++v83;
          ++v85;
        }
        while ( v83 < a4 );
        v30 = v113;
        GlyphsWithHotKeys = (int)v124;
        v31 = a4;
        v112 = a4;
        if ( v86 != v136 )
        {
          GpFree(v86);
          v31 = v112;
        }
        v134 = -1;
        v135 = v136;
      }
      else
      {
        v26 = *(_QWORD *)(v126 + 184);
        v27 = v26 ? *(_DWORD *)(v26 + 68) : 0;
        v28 = (unsigned __int16 *)(*(_QWORD *)(v126 + 24) + 2LL * v114);
        if ( v27 )
        {
          GlyphsWithHotKeys = FullTextImager::GetGlyphsWithHotKeys(
                                (FullTextImager *)(unsigned int)v115,
                                v28,
                                a4,
                                v12,
                                v120,
                                v119,
                                (const struct DWRITE_SCRIPT_ANALYSIS *)&v122,
                                v105,
                                v106,
                                v107,
                                v108,
                                v109,
                                v115,
                                v18,
                                v20,
                                v22,
                                v25,
                                &v112);
          v30 = (unsigned int)GlyphsWithHotKeys >> 31;
        }
        else
        {
          v109 = 0;
          v108 = 0;
          v107 = 0;
          v106 = 0;
          v105 = 0;
          GlyphsWithHotKeys = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, unsigned __int16 *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
                                Globals::g_DWriteTextAnalyzer,
                                v28,
                                (unsigned int)a4,
                                *((_QWORD *)v12 + 1),
                                v120,
                                v119,
                                &v122);
          if ( GlyphsWithHotKeys >= 0 )
          {
            v31 = v112;
            goto LABEL_27;
          }
          v30 = 1;
        }
        v31 = v112;
      }
      if ( GlyphsWithHotKeys != -2147024774 )
        break;
      v103 = v115;
      if ( v115 >= 0x10000 )
        goto LABEL_115;
      v115 *= 2;
      v89 = 2 * v103;
      v90 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v90 = -1;
      v91 = GpMallocEx(v90, 0);
      AutoArray<PointF>::operator=(&v129, v91);
      v92 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v92 = -1;
      v93 = GpMallocEx(v92, 0);
      AutoArray<PointF>::operator=(&v123, v93);
      v94 = 2 * v89;
      if ( !is_mul_ok(v89, 2u) )
        v94 = -1;
      v95 = GpMallocEx(v94, 0);
      AutoArray<PointF>::operator=(&v117, v95);
      v18 = v129;
      v22 = v123;
      v25 = v117;
      if ( !v129 || !v123 || !v117 )
        goto LABEL_91;
      v12 = Face;
    }
    if ( GlyphsWithHotKeys < 0 )
    {
LABEL_115:
      v13 = v30;
      v25 = v117;
      goto LABEL_85;
    }
LABEL_27:
    v113 = a4;
    if ( (a6 & 0x400) == 0 && !*((_DWORD *)Face + 27) )
      break;
    LODWORD(v33) = v31;
LABEL_41:
    LODWORD(v34) = a4;
LABEL_45:
    v38 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
    v39 = v38;
    if ( !v38 )
    {
      v22 = v123;
      v25 = v117;
      goto LABEL_91;
    }
    *v38 = 0;
    v40 = v38;
    v38[1] = v114;
    v41 = v128;
    v39[2] = v34;
    v42 = *v41;
    v39[5] = a6;
    v43 = Face;
    *(_QWORD *)(v39 + 3) = v42;
    v44 = v126;
    *((_QWORD *)v39 + 4) = 0;
    *((_WORD *)v39 + 40) = 0;
    *(_QWORD *)(v39 + 21) = 0;
    *((_BYTE *)v39 + 92) = 0;
    *((_QWORD *)v39 + 3) = v43;
    *((_QWORD *)v39 + 6) = v123;
    v45 = v117;
    *((_QWORD *)v39 + 7) = v18;
    v46 = v121;
    v47 = v121;
    *((_QWORD *)v39 + 9) = v45;
    *((float *)v39 + 8) = a9;
    v39[10] = v33;
    *((_QWORD *)v39 + 8) = v20;
    v49 = SpanVector<lsrun *>::SetSpan(v44 + 440, v47, (unsigned int)v34, v40);
    if ( v49 )
    {
      lsrun::`scalar deleting destructor'((lsrun *)v39, v48);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      GpFree(0);
      return v49;
    }
    v114 += v34;
    a4 -= v34;
    v121 = v34 + v46;
    if ( a4 > 0 )
      goto LABEL_51;
    v12 = Face;
LABEL_49:
    GpFree(0);
    GpFree(0);
    GpFree(0);
    GpFree(0);
  }
  v32 = *((_WORD *)Face + 50);
  v33 = 0;
  if ( !v31 )
    goto LABEL_41;
  do
  {
    if ( v22[v33] == v32 )
      break;
    v33 = (unsigned int)(v33 + 1);
  }
  while ( (unsigned int)v33 < v31 );
  if ( (unsigned int)v33 >= v31 )
    goto LABEL_41;
  v34 = 0;
  do
  {
    if ( v18[v34] >= (unsigned int)v33 )
      break;
    v34 = (unsigned int)(v34 + 1);
  }
  while ( (int)v34 < a4 );
  v35 = v34;
  for ( i = (int)v34 < a4; ; i = v35 < a4 )
  {
    v113 = v35;
    if ( !i )
      break;
    if ( v22[v18[v35]] != v32 )
      goto LABEL_43;
    ++v35;
  }
  if ( (_DWORD)v34 == a4 )
  {
LABEL_154:
    v34 = (unsigned int)(v34 - 1);
    LODWORD(v33) = v18[(int)v34];
    while ( (int)v34 > 0 )
    {
      if ( v18[v34 - 1] != (_DWORD)v33 )
        goto LABEL_45;
      v34 = (unsigned int)(v34 - 1);
    }
    goto LABEL_50;
  }
LABEL_43:
  if ( v18[(int)v34] > (unsigned int)v33 )
    goto LABEL_154;
  if ( (int)v34 > 0 )
    goto LABEL_45;
LABEL_50:
  GpFree(v22);
  GpFree(v18);
  GpFree(v117);
  GpFree(v20);
LABEL_51:
  v50 = 2LL * (unsigned int)a4;
  if ( !is_mul_ok((unsigned int)a4, 2u) )
    v50 = -1;
  v124 = (struct DWRITE_SHAPING_TEXT_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v50);
  GpFree(0);
  v51 = v115;
  v52 = 2LL * v115;
  if ( !is_mul_ok(v115, 2u) )
    v52 = -1;
  v18 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v52);
  GpFree(0);
  v53 = 2 * v51;
  v129 = v18;
  if ( !is_mul_ok(v51, 2u) )
    v53 = -1;
  v54 = (unsigned __int16 *)HeapAlloc(GpRuntime::GpMemHeap, 0, v53);
  GpFree(0);
  v123 = v54;
  v55 = 2 * v51;
  if ( !is_mul_ok(v51, 2u) )
    v55 = -1;
  v56 = (struct DWRITE_SHAPING_GLYPH_PROPERTIES *)HeapAlloc(GpRuntime::GpMemHeap, 0, v55);
  GpFree(0);
  v57 = v124;
  v117 = v56;
  if ( !v18 || !v124 || !v54 || !v56 )
  {
    UniformFallbackFace = 3;
    goto LABEL_112;
  }
  j = 0;
  v132 = 0;
  v116 = 0;
  v111 = 0;
  v110 = 0;
  FamilyFallback = GpFontFamily::GetFamilyFallback(v133);
  if ( FamilyFallback )
  {
    v106 = (struct IDWriteNumberSubstitution *)((char *)&v110 + 1);
    v105 = &v110;
    UniformFallbackFace = GpFamilyFallback::GetUniformFallbackFace(
                            FamilyFallback,
                            *(_QWORD *)(v126 + 24) + 2LL * v114,
                            v113 - (unsigned int)v34,
                            v130,
                            *(char *)v128,
                            &v132,
                            &v116);
    if ( !UniformFallbackFace )
    {
      LOBYTE(v58) = HIBYTE(v110);
      v61 = v116;
      v62 = v132;
      v111 = v110;
      v113 = v116;
      goto LABEL_66;
    }
LABEL_112:
    GpFree(v56);
    GpFree(v54);
    GpFree(v57);
    v87 = v18;
  }
  else
  {
    v62 = j;
    v61 = (unsigned int)a4;
    v113 = a4;
LABEL_66:
    if ( (int)v61 <= 0 )
    {
      UniformFallbackFace = 1;
      goto LABEL_112;
    }
    if ( !v62 )
      v62 = Face;
    if ( v62 == Face )
    {
      v63 = 0;
    }
    else
    {
      v63 = GdipScriptToDWriteScript((unsigned int)*(char *)v128);
      v61 = v113;
    }
    v64 = 2LL * v114;
    LOWORD(v122) = v63;
    for ( j = (struct GpFontFace *)v64; ; v64 = (__int64)j )
    {
      v65 = *(_QWORD *)(v126 + 184);
      if ( v65 && *(_DWORD *)(v65 + 68) )
      {
        v66 = FullTextImager::GetGlyphsWithHotKeys(
                v58,
                (unsigned __int16 *)(*(_QWORD *)(v126 + 24) + v64),
                v61,
                v62,
                v120,
                v119,
                (const struct DWRITE_SCRIPT_ANALYSIS *)&v122,
                v105,
                v106,
                v107,
                v108,
                v109,
                v115,
                v18,
                v57,
                v54,
                v56,
                &v112);
        v116 = (unsigned int)v66 >> 31;
      }
      else
      {
        v109 = 0;
        v108 = 0;
        v107 = 0;
        v106 = 0;
        v105 = 0;
        v66 = (*(__int64 (__fastcall **)(struct IDWriteTextAnalyzer *, __int64, __int64, _QWORD, int, int, __int64 *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 56LL))(
                Globals::g_DWriteTextAnalyzer,
                *(_QWORD *)(v126 + 24) + v64,
                v61,
                *((_QWORD *)v62 + 1),
                v120,
                v119,
                &v122);
        if ( v66 >= 0 )
          goto LABEL_78;
        v116 = 1;
      }
      if ( v66 != -2147024774 )
        break;
      v104 = v115;
      if ( v115 >= 0x10000 )
        goto LABEL_95;
      v115 *= 2;
      v96 = 2 * v104;
      v97 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v97 = -1;
      v98 = GpMallocEx(v97, 0);
      AutoArray<PointF>::operator=(&v129, v98);
      v99 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v99 = -1;
      v100 = GpMallocEx(v99, 0);
      AutoArray<PointF>::operator=(&v123, v100);
      v101 = 2 * v96;
      if ( !is_mul_ok(v96, 2u) )
        v101 = -1;
      v102 = GpMallocEx(v101, 0);
      AutoArray<PointF>::operator=(&v117, v102);
      v18 = v129;
      v54 = v123;
      v56 = v117;
      if ( !v129 || !v123 || !v117 )
        goto LABEL_96;
      v61 = v113;
      v57 = v124;
    }
    if ( v66 < 0 )
    {
LABEL_95:
      GpFree(v56);
      GpFree(v54);
      GpFree(v57);
      v13 = v116;
      goto LABEL_86;
    }
LABEL_78:
    v67 = (char *)HeapAlloc(GpRuntime::GpMemHeap, 0, 0x60u);
    v68 = v67;
    if ( !v67 )
    {
LABEL_96:
      GpFree(v56);
      GpFree(v54);
      GpFree(v124);
      v13 = 3;
      goto LABEL_86;
    }
    *(_DWORD *)v67 = 0;
    *((_DWORD *)v67 + 1) = v114;
    *((_DWORD *)v67 + 2) = v113;
    v69 = *v128;
    *((_DWORD *)v67 + 5) = a6;
    *(_QWORD *)(v67 + 12) = v69;
    *((_QWORD *)v67 + 4) = 0;
    *((_DWORD *)v67 + 10) = 0;
    *((_QWORD *)v67 + 6) = 0;
    *((_QWORD *)v67 + 7) = 0;
    *((_QWORD *)v67 + 8) = 0;
    *((_QWORD *)v67 + 9) = 0;
    *((_WORD *)v67 + 40) = 0;
    *(_QWORD *)(v67 + 84) = 0;
    v67[92] = 0;
    *((_QWORD *)v67 + 3) = v62;
    v70 = v112;
    *((_QWORD *)v68 + 9) = v56;
    v12 = Face;
    *((_DWORD *)v68 + 10) = v70;
    v71 = v124;
    *((_QWORD *)v68 + 6) = v54;
    *((_QWORD *)v68 + 7) = v18;
    *((_QWORD *)v68 + 8) = v71;
    if ( v62 != v12 )
      v68[92] = (32 * HIBYTE(v111)) | v111 & 0x1F;
    FullTextImager::GetFallbackFontSize((FullTextImager *)(v68 + 32), v12, a9, v62, (float *)v68 + 8, (float *)v68 + 9);
    v72 = v68;
    v73 = v113;
    v74 = v121;
    UniformFallbackFace = SpanVector<lsrun *>::SetSpan(v126 + 440, v121, v113, v72);
    if ( !UniformFallbackFace )
    {
      v114 += v73;
      v121 = v73 + v74;
      a4 -= v73;
      goto LABEL_49;
    }
    GpFree(0);
    GpFree(0);
    GpFree(0);
    v87 = 0;
  }
  GpFree(v87);
  return UniformFallbackFace;
}

```

## disassembly

```asm
0x18007e300  mov     rax, rsp
0x18007e303  push    rbp
0x18007e304  push    rbx
0x18007e305  push    rsi
0x18007e306  push    rdi
0x18007e307  push    r12
0x18007e309  push    r13
0x18007e30b  push    r14
0x18007e30d  push    r15
0x18007e30f  lea     rbp, [rax-108h]
0x18007e316  sub     rsp, 1E8h
0x18007e31d  movaps  xmmword ptr [rax-58h], xmm6
0x18007e321  mov     rax, cs:__security_cookie
0x18007e328  xor     rax, rsp
0x18007e32b  mov     [rbp+100h+var_60], rax
0x18007e332  mov     rax, [rbp+100h+arg_20]
0x18007e339  mov     r15d, r9d
0x18007e33c  mov     [rbp+100h+var_120], rax
0x18007e340  mov     [rbp+100h+var_130], rcx
0x18007e344  mov     rcx, [rbp+100h+arg_30]; this
0x18007e34b  movzx   ebx, byte ptr [rax+4]
0x18007e34f  movsx   eax, byte ptr [rax+1]
0x18007e353  and     eax, 8
0x18007e356  mov     [rbp+100h+var_154], edx
0x18007e359  mov     edx, [rbp+100h+arg_38]; int
0x18007e35f  mov     [rbp+100h+var_158], eax
0x18007e362  mov     [rbp+100h+var_174], r8d
0x18007e366  mov     [rbp+100h+var_F8], rcx
0x18007e36a  mov     [rbp+100h+var_110], edx
0x18007e36d  call    ?GetFace@GpFontFamily@@QEBAPEAVGpFontFace@@H@Z; GpFontFamily::GetFace(int)
0x18007e372  mov     [rbp+100h+var_128], rax
0x18007e376  mov     r12, rax
0x18007e379  test    rax, rax
0x18007e37c  jz      loc_18007EFE5
0x18007e382  movss   xmm6, [rbp+100h+arg_40]
0x18007e38a  mov     esi, 1
0x18007e38f  and     ebx, esi
0x18007e391  mov     [rbp+100h+var_15C], ebx
0x18007e394  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007e398  lea     r14d, [rbx+3]
0x18007e39c  lea     ecx, [rbx+11h]
0x18007e39f  test    r15d, r15d
0x18007e3a2  jle     loc_18007E5EB
0x18007e3a8  lea     eax, [r15+r15*2]
0x18007e3ac  cdq
0x18007e3ad  idiv    r14d
0x18007e3b0  add     eax, ecx
0x18007e3b2  mov     dword ptr [rbp+100h+var_170], eax
0x18007e3b5  cmp     eax, 0FFFFh
0x18007e3ba  ja      loc_18007EBF9
0x18007e3c0  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e3c7  movsxd  rdi, eax
0x18007e3ca  mov     eax, r14d
0x18007e3cd  mul     rdi
0x18007e3d0  cmovb   rax, rbx
0x18007e3d4  xor     edx, edx; dwFlags
0x18007e3d6  mov     r8, rax; dwBytes
0x18007e3d9  call    cs:__imp_HeapAlloc
0x18007e3df  mov     r13, rax
0x18007e3e2  mov     [rbp+100h+var_118], rax
0x18007e3e6  movsxd  rcx, r15d
0x18007e3e9  mov     eax, r14d
0x18007e3ec  mul     rcx
0x18007e3ef  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e3f6  cmovb   rax, rbx
0x18007e3fa  xor     edx, edx; dwFlags
0x18007e3fc  mov     r8, rax; dwBytes
0x18007e3ff  call    cs:__imp_HeapAlloc
0x18007e405  mov     rbx, rax
0x18007e408  lea     rcx, [r14-3]
0x18007e40c  mov     eax, r14d
0x18007e40f  mul     rdi
0x18007e412  cmovb   rax, rcx
0x18007e416  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e41d  mov     r8, rax; dwBytes
0x18007e420  xor     edx, edx; dwFlags
0x18007e422  call    cs:__imp_HeapAlloc
0x18007e428  mov     r14, rax
0x18007e42b  mov     [rbp+100h+var_148], rax
0x18007e42f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007e436  mov     eax, 2
0x18007e43b  mul     rdi
0x18007e43e  cmovb   rax, rcx
0x18007e442  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e449  mov     r8, rax; dwBytes
0x18007e44c  xor     edx, edx; dwFlags
0x18007e44e  call    cs:__imp_HeapAlloc
0x18007e454  mov     [rbp+100h+var_17C], 0
0x18007e45b  mov     rdi, rax
0x18007e45e  mov     [rbp+100h+var_168], rax
0x18007e462  test    r13, r13
0x18007e465  jz      loc_18007EC09
0x18007e46b  test    rbx, rbx
0x18007e46e  jz      loc_18007EC09
0x18007e474  test    r14, r14
0x18007e477  jz      loc_18007EC09
0x18007e47d  test    rax, rax
0x18007e480  jz      loc_18007EC09
0x18007e486  mov     rax, [rbp+100h+var_120]
0x18007e48a  mov     [rbp+100h+var_150], 0
0x18007e492  movsx   ecx, byte ptr [rax]
0x18007e495  call    ?GdipScriptToDWriteScript@@YAGW4ItemScript@@@Z; GdipScriptToDWriteScript(ItemScript)
0x18007e49a  xor     r9d, r9d
0x18007e49d  mov     word ptr [rbp+100h+var_150], ax
0x18007e4a1  mov     dword ptr [rbp+100h+var_150+4], r9d
0x18007e4a5  mov     rax, [rbp+100h+var_120]
0x18007e4a9  cmp     byte ptr [rax], 2Ch ; ','
0x18007e4ac  jz      loc_18007EAC1
0x18007e4b2  mov     r8, [rbp+100h+var_130]
0x18007e4b6  mov     rax, [r8+0B8h]
0x18007e4bd  test    rax, rax
0x18007e4c0  jz      loc_18007EC23
0x18007e4c6  mov     ecx, [rax+44h]
0x18007e4c9  mov     rax, [r8+18h]
0x18007e4cd  mov     r8d, r15d; unsigned int
0x18007e4d0  movsxd  rdx, [rbp+100h+var_174]
0x18007e4d4  lea     rdx, [rax+rdx*2]; unsigned __int16 *
0x18007e4d8  test    ecx, ecx
0x18007e4da  jnz     loc_18007EBA3
0x18007e4e0  mov     r10, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x18007e4e7  mov     rcx, [r10]
0x18007e4ea  mov     rax, [rcx+38h]
0x18007e4ee  lea     rcx, [rbp+100h+var_17C]
0x18007e4f2  mov     [rsp+88h], rcx
0x18007e4fa  mov     ecx, dword ptr [rbp+100h+var_170]
0x18007e4fd  mov     [rsp+220h+var_1A0], rdi
0x18007e505  mov     [rsp+220h+var_1A8], r14
0x18007e50a  mov     [rsp+220h+var_1B0], rbx
0x18007e50f  mov     [rsp+220h+var_1B8], r13
0x18007e514  mov     [rsp+220h+var_1C0], ecx
0x18007e518  lea     rcx, [rbp+100h+var_150]
0x18007e51c  mov     [rsp+220h+var_1C8], r9d; unsigned int
0x18007e521  mov     [rsp+220h+var_1D0], r9; unsigned int *
0x18007e526  mov     [rsp+220h+var_1D8], r9; struct DWRITE_TYPOGRAPHIC_FEATURES **
0x18007e52b  mov     [rsp+220h+var_1E0], r9
0x18007e530  mov     [rsp+220h+var_1E8], r9
0x18007e535  mov     r9, [r12+8]
0x18007e53a  mov     [rsp+220h+var_1F0], rcx
0x18007e53f  mov     ecx, [rbp+100h+var_15C]
0x18007e542  mov     dword ptr [rsp+220h+var_1F8], ecx
0x18007e546  mov     ecx, [rbp+100h+var_158]
0x18007e549  mov     dword ptr [rsp+220h+var_200], ecx
0x18007e54d  mov     rcx, r10
0x18007e550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e555  mov     r12d, eax
0x18007e558  test    eax, eax
0x18007e55a  jns     loc_18007EAB9
0x18007e560  mov     edi, esi
0x18007e562  mov     edx, [rbp+100h+var_17C]
0x18007e565  cmp     r12d, 8007007Ah
0x18007e56c  jz      loc_18007F03B
0x18007e572  test    r12d, r12d
0x18007e575  js      loc_18007EE27
0x18007e57b  test    [rbp+100h+arg_28], 400h
0x18007e585  mov     [rbp+100h+var_178], r15d
0x18007e589  jnz     loc_18007E618
0x18007e58f  mov     rax, [rbp+100h+var_128]
0x18007e593  cmp     dword ptr [rax+6Ch], 0
0x18007e597  jnz     short loc_18007E618
0x18007e599  movzx   r8d, word ptr [rax+64h]
0x18007e59e  xor     r12d, r12d
0x18007e5a1  test    edx, edx
0x18007e5a3  jz      short loc_18007E61B
0x18007e5a5  cmp     [r14+r12*2], r8w
0x18007e5aa  jz      short loc_18007E5B4
0x18007e5ac  add     r12d, esi
0x18007e5af  cmp     r12d, edx
0x18007e5b2  jb      short loc_18007E5A5
0x18007e5b4  cmp     r12d, edx
0x18007e5b7  jnb     short loc_18007E61B
0x18007e5b9  xor     edi, edi
0x18007e5bb  movzx   ecx, word ptr [r13+rdi*2+0]
0x18007e5c1  cmp     ecx, r12d
0x18007e5c4  jb      loc_18007EC13
0x18007e5ca  mov     edx, edi
0x18007e5cc  cmp     edi, r15d
0x18007e5cf  mov     [rbp+100h+var_178], edx
0x18007e5d2  jge     short loc_18007E620
0x18007e5d4  movsxd  rax, edx
0x18007e5d7  movzx   ecx, word ptr [r13+rax*2+0]
0x18007e5dd  cmp     [r14+rcx*2], r8w
0x18007e5e2  jnz     short loc_18007E629
0x18007e5e4  add     edx, esi
0x18007e5e6  cmp     edx, r15d
0x18007e5e9  jmp     short loc_18007E5CF
0x18007e5eb  xor     eax, eax
0x18007e5ed  mov     rcx, [rbp+100h+var_60]
0x18007e5f4  xor     rcx, rsp; StackCookie
0x18007e5f7  call    __security_check_cookie
0x18007e5fc  movaps  xmm6, [rsp+220h+var_58+8]
0x18007e604  add     rsp, 1E8h
0x18007e60b  pop     r15
0x18007e60d  pop     r14
0x18007e60f  pop     r13
0x18007e611  pop     r12
0x18007e613  pop     rdi
0x18007e614  pop     rsi
0x18007e615  pop     rbx
0x18007e616  pop     rbp
0x18007e617  retn
0x18007e618  mov     r12d, edx
0x18007e61b  mov     edi, r15d
0x18007e61e  jmp     short loc_18007E643
0x18007e620  cmp     edi, r15d
0x18007e623  jz      loc_18007F04E
0x18007e629  movsxd  rax, edi
0x18007e62c  movzx   ecx, word ptr [r13+rax*2+0]
0x18007e632  cmp     ecx, r12d
0x18007e635  ja      loc_18007F04E
0x18007e63b  test    edi, edi
0x18007e63d  jle     loc_18007E71F
0x18007e643  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e64a  xor     edx, edx; dwFlags
0x18007e64c  lea     r8d, [rdx+60h]; dwBytes
0x18007e650  call    cs:__imp_HeapAlloc
0x18007e656  xor     edx, edx
0x18007e658  mov     r14, rax
0x18007e65b  test    rax, rax
0x18007e65e  jz      loc_18007EC01
0x18007e664  mov     [rax], edx
0x18007e666  mov     r9, r14
0x18007e669  mov     eax, [rbp+100h+var_174]
0x18007e66c  mov     r8d, edi
0x18007e66f  mov     [r14+4], eax
0x18007e673  mov     rax, [rbp+100h+var_120]
0x18007e677  mov     [r14+8], edi
0x18007e67b  mov     rcx, [rax]
0x18007e67e  mov     eax, [rbp+100h+arg_28]
0x18007e684  mov     [r14+14h], eax
0x18007e688  mov     rax, [rbp+100h+var_128]
0x18007e68c  mov     [r14+0Ch], rcx
0x18007e690  mov     rcx, [rbp+100h+var_130]
0x18007e694  mov     [r14+20h], rdx
0x18007e698  add     rcx, 1B8h
0x18007e69f  mov     [r14+50h], dx
0x18007e6a4  mov     [r14+54h], rdx
0x18007e6a8  mov     [r14+5Ch], dl
0x18007e6ac  mov     [r14+18h], rax
0x18007e6b0  mov     rax, [rbp+100h+var_148]
0x18007e6b4  mov     [r14+30h], rax
0x18007e6b8  mov     rax, [rbp+100h+var_168]
0x18007e6bc  mov     [r14+38h], r13
0x18007e6c0  mov     r13d, [rbp+100h+var_154]
0x18007e6c4  mov     edx, r13d
0x18007e6c7  mov     [r14+48h], rax
0x18007e6cb  movss   dword ptr [r14+20h], xmm6
0x18007e6d1  mov     [r14+28h], r12d
0x18007e6d5  mov     [r14+40h], rbx
0x18007e6d9  call    ?SetSpan@?$SpanVector@PEAUlsrun@@@@QEAA?AW4Status@@HHPEAUlsrun@@@Z; SpanVector<lsrun *>::SetSpan(int,int,lsrun *)
0x18007e6de  mov     ebx, eax
0x18007e6e0  test    eax, eax
0x18007e6e2  jnz     loc_18007EB78
0x18007e6e8  add     [rbp+100h+var_174], edi
0x18007e6eb  add     r13d, edi
0x18007e6ee  sub     r15d, edi
0x18007e6f1  mov     [rbp+100h+var_154], r13d
0x18007e6f5  test    r15d, r15d
0x18007e6f8  jg      short loc_18007E740
0x18007e6fa  mov     r12, [rbp+100h+var_128]
0x18007e6fe  xor     ecx, ecx
0x18007e700  call    GpFree
0x18007e705  xor     ecx, ecx
0x18007e707  call    GpFree
0x18007e70c  xor     ecx, ecx
0x18007e70e  call    GpFree
0x18007e713  xor     ecx, ecx
0x18007e715  call    GpFree
0x18007e71a  jmp     loc_18007E394
0x18007e71f  mov     rcx, r14
0x18007e722  call    GpFree
0x18007e727  mov     rcx, r13
0x18007e72a  call    GpFree
0x18007e72f  mov     rcx, [rbp+100h+var_168]
0x18007e733  call    GpFree
0x18007e738  mov     rcx, rbx
0x18007e73b  call    GpFree
0x18007e740  mov     r12d, 2
0x18007e746  mov     ecx, r15d
0x18007e749  mov     eax, r12d
0x18007e74c  mul     rcx
0x18007e74f  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e756  lea     r14, [r12-3]
0x18007e75b  cmovb   rax, r14
0x18007e75f  xor     edx, edx; dwFlags
0x18007e761  mov     r8, rax; dwBytes
0x18007e764  call    cs:__imp_HeapAlloc
0x18007e76a  xor     ecx, ecx
0x18007e76c  mov     [rbp+100h+var_140], rax
0x18007e770  call    GpFree
0x18007e775  movsxd  rbx, dword ptr [rbp+100h+var_170]
0x18007e779  mov     eax, r12d
0x18007e77c  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18007e783  mul     rbx
0x18007e786  cmovb   rax, r14
0x18007e78a  xor     edx, edx; dwFlags
0x18007e78c  mov     r8, rax; dwBytes
0x18007e78f  call    cs:__imp_HeapAlloc
0x18007e795  xor     ecx, ecx
0x18007e797  mov     r13, rax
0x18007e79a  call    GpFree
  ... truncated ...
```
